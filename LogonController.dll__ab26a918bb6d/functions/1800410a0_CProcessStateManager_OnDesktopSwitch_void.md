# CProcessStateManager::OnDesktopSwitch(void)

- ea: `0x1800410a0`
- end: `0x1800411f1`
- name: `?OnDesktopSwitch@CProcessStateManager@@UEAAJXZ`
- size: `337`
- prototype: `__int64 __fastcall(CProcessStateManager *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e750`
- `0x1800410a0`
- `0x18005d488`
- `0x18006c000`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180041128`
- `KERNEL32!CompareStringOrdinal` at `0x180041128`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800411a0`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800411a0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180041170`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180041170`
- `KERNEL32!AcquireSRWLockShared` at `0x1800410cf`
- `KERNEL32!AcquireSRWLockShared` at `0x1800410cf`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18004114d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18004114d`
- `USER32!OpenInputDesktop` at `0x1800410e1`
- `USER32!OpenInputDesktop` at `0x1800410e1`
- `USER32!GetUserObjectInformationW` at `0x180041108`
- `USER32!GetUserObjectInformationW` at `0x180041108`
- `USER32!CloseDesktop` at `0x180041138`
- `USER32!CloseDesktop` at `0x180041138`

## pseudocode

```c
__int64 __fastcall CProcessStateManager::OnDesktopSwitch(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rbp
  char v3; // si
  HDESK v4; // rax
  int v5; // r14d
  HDESK v6; // rbx
  unsigned int Ptr; // ebp
  int v9; // eax
  unsigned int v10; // ebx
  int lpnLengthNeeded; // [rsp+20h] [rbp-268h]
  WCHAR pvInfo[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  v1 = this + 47;
  AcquireSRWLockShared(this + 47);
  v3 = 1;
  v4 = OpenInputDesktop(0, 0, 1u);
  v5 = 0;
  v6 = v4;
  if ( v4 )
  {
    if ( GetUserObjectInformationW(v4, 2, pvInfo, 0x104u, 0) )
      LOBYTE(v5) = CompareStringOrdinal(pvInfo, -1, L"Screen-saver", -1, 1) == 2;
    CloseDesktop(v6);
  }
  if ( v1 )
    ReleaseSRWLockShared(v1);
  AcquireSRWLockExclusive(this + 58);
  if ( v5 == ((LODWORD(this[59].Ptr) >> 20) & 1) )
  {
    v3 = 0;
    Ptr = 0;
  }
  else
  {
    LODWORD(this[59].Ptr) ^= 0x100000u;
    Ptr = (unsigned int)this[59].Ptr;
  }
  if ( this != (RTL_SRWLOCK *)-464LL )
    ReleaseSRWLockExclusive(this + 58);
  if ( !v3 )
    return 0;
  v9 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider *,enum Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<CProcessStateManager *,enum Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags>(
         &this[55],
         &this[-5],
         Ptr);
  v10 = v9;
  if ( v9 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x488,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
    (const char *)(unsigned int)v9,
    lpnLengthNeeded);
  return v10;
}

```

## disassembly

```asm
0x1800410a0  push    rbx
0x1800410a2  push    rbp
0x1800410a3  push    rsi
0x1800410a4  push    rdi
0x1800410a5  push    r14
0x1800410a7  push    r15
0x1800410a9  sub     rsp, 258h
0x1800410b0  mov     rax, cs:__security_cookie
0x1800410b7  xor     rax, rsp
0x1800410ba  mov     [rsp+288h+var_48], rax
0x1800410c2  lea     rbp, [rcx+178h]
0x1800410c9  mov     rdi, rcx
0x1800410cc  mov     rcx, rbp; SRWLock
0x1800410cf  call    cs:__imp_AcquireSRWLockShared
0x1800410d5  mov     esi, 1
0x1800410da  xor     edx, edx; fInherit
0x1800410dc  mov     r8d, esi; dwDesiredAccess
0x1800410df  xor     ecx, ecx; dwFlags
0x1800410e1  call    cs:__imp_OpenInputDesktop
0x1800410e7  xor     r14d, r14d
0x1800410ea  mov     rbx, rax
0x1800410ed  test    rax, rax
0x1800410f0  jz      short loc_18004113E
0x1800410f2  mov     r9d, 104h; nLength
0x1800410f8  mov     qword ptr [rsp+288h+lpnLengthNeeded], r14; lpnLengthNeeded
0x1800410fd  lea     r8, [rsp+288h+pvInfo]; pvInfo
0x180041102  mov     rcx, rax; hObj
0x180041105  lea     edx, [rsi+1]; nIndex
0x180041108  call    cs:__imp_GetUserObjectInformationW
0x18004110e  test    eax, eax
0x180041110  jz      short loc_180041135
0x180041112  or      edx, 0FFFFFFFFh; cchCount1
0x180041115  mov     [rsp+288h+lpnLengthNeeded], esi; int
0x180041119  mov     r9d, edx; cchCount2
0x18004111c  lea     r8, aScreenSaver; "Screen-saver"
0x180041123  lea     rcx, [rsp+288h+pvInfo]; lpString1
0x180041128  call    cs:__imp_CompareStringOrdinal
0x18004112e  cmp     eax, 2
0x180041131  setz    r14b
0x180041135  mov     rcx, rbx; hDesktop
0x180041138  call    cs:__imp_CloseDesktop
0x18004113e  test    rbp, rbp
0x180041141  jnz     short loc_18004119D
0x180041143  lea     rbx, [rdi+1D0h]
0x18004114a  mov     rcx, rbx; SRWLock
0x18004114d  call    cs:__imp_AcquireSRWLockExclusive
0x180041153  mov     eax, [rdi+1D8h]
0x180041159  shr     eax, 14h
0x18004115c  and     eax, esi
0x18004115e  cmp     r14d, eax
0x180041161  jnz     short loc_1800411A8
0x180041163  xor     sil, sil
0x180041166  xor     ebp, ebp
0x180041168  test    rbx, rbx
0x18004116b  jz      short loc_180041176
0x18004116d  mov     rcx, rbx; SRWLock
0x180041170  call    cs:__imp_ReleaseSRWLockExclusive
0x180041176  test    sil, sil
0x180041179  jnz     short loc_1800411B8
0x18004117b  xor     eax, eax
0x18004117d  mov     rcx, [rsp+288h+var_48]
0x180041185  xor     rcx, rsp; StackCookie
0x180041188  call    __security_check_cookie
0x18004118d  add     rsp, 258h
0x180041194  pop     r15
0x180041196  pop     r14
0x180041198  pop     rdi
0x180041199  pop     rsi
0x18004119a  pop     rbp
0x18004119b  pop     rbx
0x18004119c  retn
0x18004119d  mov     rcx, rbp; SRWLock
0x1800411a0  call    cs:__imp_ReleaseSRWLockShared
0x1800411a6  jmp     short loc_180041143
0x1800411a8  btc     dword ptr [rdi+1D8h], 14h
0x1800411b0  mov     ebp, [rdi+1D8h]
0x1800411b6  jmp     short loc_180041168
0x1800411b8  lea     rcx, [rdi+1B8h]
0x1800411bf  mov     r8d, ebp
0x1800411c2  lea     rdx, [rdi-28h]
0x1800411c6  call    ??$InvokeAll@PEAVCProcessStateManager@@W4DisplayStateFlags@CredProvData@Logon@UI@Internal@Windows@@@?$EventSource@U?$ITypedEventHandler@PEAUIDisplayStateProvider@CredProvData@Logon@UI@Internal@Windows@@W4DisplayStateFlags@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAVCProcessStateManager@@W4DisplayStateFlags@CredProvData@Logon@UI@Internal@Windows@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider *,Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<CProcessStateManager *,Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags>(CProcessStateManager *,Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags)
0x1800411cb  mov     ebx, eax
0x1800411cd  test    eax, eax
0x1800411cf  jns     short loc_18004117B
0x1800411d1  mov     rcx, [rsp+288h]; this
0x1800411d9  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800411e0  mov     r9d, eax; char *
0x1800411e3  mov     edx, 488h; void *
0x1800411e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800411ed  mov     eax, ebx
0x1800411ef  jmp     short loc_18004117D
```
