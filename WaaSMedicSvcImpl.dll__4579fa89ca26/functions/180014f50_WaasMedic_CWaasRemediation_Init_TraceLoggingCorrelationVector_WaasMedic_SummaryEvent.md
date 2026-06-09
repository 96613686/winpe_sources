# WaasMedic::CWaasRemediation::Init(TraceLoggingCorrelationVector *,WaasMedic::SummaryEvent *)

- ea: `0x180014f50`
- end: `0x180015134`
- name: `?Init@CWaasRemediation@WaasMedic@@UEAAJPEAVTraceLoggingCorrelationVector@@PEAVSummaryEvent@2@@Z`
- size: `484`
- prototype: `__int64 __fastcall(WaasMedic::CWaasRemediation *__hidden this, struct TraceLoggingCorrelationVector *, struct WaasMedic::SummaryEvent *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x18000bbd4`
- `0x1800124c4`
- `0x180014f50`
- `0x18001a834`
- `0x18001c554`
- `0x180022e64`
- `0x18002e81c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015079`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015090`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015090`

## string_xrefs

- `0x180014fb1`: `Failed to CreateInstance for State provider! hr = 0x%08x.`
- `0x1800150be`: `Failed to create canceled event for WaasRemediation. hr = 0x%08x`
- `0x1800150ca`: `Failed to create canceled event for WaasRemediation.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::CWaasRemediation::Init(
        WaasMedic::CWaasRemediation *this,
        struct TraceLoggingCorrelationVector *a2,
        struct WaasMedic::SummaryEvent *a3)
{
  int Instance; // eax
  unsigned int v7; // ebx
  int SettingsProvider; // eax
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rcx
  HANDLE EventW; // rbx
  char *v13; // rcx
  signed int LastError; // eax
  int v15; // eax
  struct WaasMedic::SettingsProvider *v17[2]; // [rsp+20h] [rbp-D8h] BYREF
  _BYTE v18[16]; // [rsp+30h] [rbp-C8h] BYREF
  char v19[144]; // [rsp+40h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  memset_0(v19, 0, 0x81u);
  if ( *((_BYTE *)this + 32) )
    goto LABEL_22;
  v17[1] = 0;
  Instance = WaasMedic::StateProvider::CreateInstance((char *)this + 8);
  v7 = Instance;
  if ( Instance < 0 )
  {
    LogLevelW(2u, L"Failed to CreateInstance for State provider! hr = 0x%08x.", (unsigned int)Instance);
LABEL_24:
    *((_BYTE *)this + 32) = (v7 & 0x80000000) == 0;
    return v7;
  }
  if ( a2 )
  {
    if ( !TraceLoggingCorrelationVector::ToStringImpl(
            a2,
            _InterlockedExchangeAdd64((volatile signed __int64 *)a2 + 17, 0),
            v19) )
    {
      v7 = -2147418113;
      v9 = 2147549183LL;
      v10 = 241;
      goto LABEL_9;
    }
  }
  else
  {
    v19[0] = 0;
  }
  v17[0] = 0;
  SettingsProvider = WaasMedic::SettingsProviderFactory::CreateSettingsProvider(
                       (WaasMedic::SettingsProviderFactory *)v18,
                       v17);
  v7 = SettingsProvider;
  if ( SettingsProvider >= 0 )
  {
    v11 = *((_QWORD *)this + 2);
    *((struct WaasMedic::SettingsProvider **)this + 2) = v17[0];
    if ( v11 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 32LL))(v11, 1);
    if ( ((*((_QWORD *)this + 5) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      LogLevelW(2u, L"Failed to create canceled event for WaasRemediation.");
    }
    else
    {
      EventW = CreateEventW(0, 0, 0, 0);
      v13 = (char *)*((_QWORD *)this + 5);
      if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v13);
      *((_QWORD *)this + 5) = EventW;
      if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        LogLevelW(2u, L"Failed to create canceled event for WaasRemediation. hr = 0x%08x", v7);
        goto LABEL_24;
      }
    }
LABEL_22:
    *((_QWORD *)this + 3) = a3;
    v15 = WaasMedic::CWaasRemediation::SetAndExtendCV(this, a2);
    v7 = v15;
    if ( v15 < 0 )
      LogLevelW(2u, L"Failed to set and extend cV in Waas remediation engine. hr = 0x%08x", (unsigned int)v15);
    goto LABEL_24;
  }
  v9 = (unsigned int)SettingsProvider;
  v10 = 245;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\engine\\waasremediation.cpp",
    (const char *)v9,
    (int)v17[0]);
  return v7;
}

```

## disassembly

```asm
0x180014f50  mov     [rsp+arg_10], rbx
0x180014f55  push    rbp
0x180014f56  push    rsi
0x180014f57  push    rdi
0x180014f58  sub     rsp, 0E0h
0x180014f5f  mov     rax, cs:__security_cookie
0x180014f66  xor     rax, rsp
0x180014f69  mov     [rsp+0F8h+var_28], rax
0x180014f71  mov     rbp, r8
0x180014f74  mov     rsi, rdx
0x180014f77  mov     rdi, rcx
0x180014f7a  xor     edx, edx; Val
0x180014f7c  mov     r8d, 81h; Size
0x180014f82  lea     rcx, [rsp+0F8h+var_B8]; void *
0x180014f87  call    memset_0
0x180014f8c  cmp     byte ptr [rdi+20h], 0
0x180014f90  jnz     loc_1800150DC
0x180014f96  mov     [rsp+0F8h+var_D0], 0
0x180014f9f  lea     rcx, [rdi+8]
0x180014fa3  call    ?CreateInstance@StateProvider@WaasMedic@@SAJAEAV?$unique_ptr@VIStateProvider@WaasMedic@@U?$default_delete@VIStateProvider@WaasMedic@@@std@@@std@@@Z; WaasMedic::StateProvider::CreateInstance(std::unique_ptr<WaasMedic::IStateProvider> &)
0x180014fa8  mov     ebx, eax
0x180014faa  test    eax, eax
0x180014fac  jns     short loc_180014FC8
0x180014fae  mov     r8d, eax
0x180014fb1  lea     rdx, aFailedToCreate_16; "Failed to CreateInstance for State prov"...
0x180014fb8  mov     ecx, 2; unsigned __int8
0x180014fbd  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180014fc2  nop
0x180014fc3  jmp     loc_180015105
0x180014fc8  test    rsi, rsi
0x180014fcb  jnz     short loc_180015012
0x180014fcd  mov     [rsp+0F8h+var_B8], sil
0x180014fd2  mov     [rsp+0F8h+var_D8], 0; int
0x180014fdb  lea     rdx, [rsp+0F8h+var_D8]; struct WaasMedic::SettingsProvider **
0x180014fe0  lea     rcx, [rsp+0F8h+var_C8]; this
0x180014fe5  call    ?CreateSettingsProvider@SettingsProviderFactory@WaasMedic@@UEAAJPEAPEAVSettingsProvider@2@@Z; WaasMedic::SettingsProviderFactory::CreateSettingsProvider(WaasMedic::SettingsProvider * *)
0x180014fea  mov     ebx, eax
0x180014fec  test    eax, eax
0x180014fee  jns     short loc_18001503D
0x180014ff0  mov     r9d, eax; char *
0x180014ff3  mov     edx, 0F5h; void *
0x180014ff8  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\engin"...
0x180014fff  mov     rcx, [rsp+0F8h]; this
0x180015007  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001500c  nop
0x18001500d  jmp     loc_18001510F
0x180015012  xor     edx, edx
0x180015014  lock xadd [rsi+88h], rdx; unsigned __int64
0x18001501d  lea     r8, [rsp+0F8h+var_B8]; char *
0x180015022  mov     rcx, rsi; this
0x180015025  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18001502a  test    al, al
0x18001502c  jnz     short loc_180014FD2
0x18001502e  mov     ebx, 8000FFFFh
0x180015033  mov     r9d, ebx
0x180015036  mov     edx, 0F1h
0x18001503b  jmp     short loc_180014FF8
0x18001503d  mov     rcx, [rdi+10h]
0x180015041  mov     rax, [rsp+0F8h+var_D8]
0x180015046  mov     [rdi+10h], rax
0x18001504a  test    rcx, rcx
0x18001504d  jz      short loc_180015060
0x18001504f  mov     rax, [rcx]
0x180015052  mov     edx, 1
0x180015057  mov     rax, [rax+20h]
0x18001505b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015060  mov     rax, [rdi+28h]
0x180015064  inc     rax
0x180015067  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001506d  jnz     short loc_1800150CA
0x18001506f  xor     r9d, r9d; lpName
0x180015072  xor     r8d, r8d; bInitialState
0x180015075  xor     edx, edx; bManualReset
0x180015077  xor     ecx, ecx; lpEventAttributes
0x180015079  call    cs:__imp_CreateEventW
0x18001507f  mov     rbx, rax
0x180015082  mov     rcx, [rdi+28h]; hObject
0x180015086  lea     rdx, [rcx-1]
0x18001508a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001508e  ja      short loc_180015096
0x180015090  call    cs:__imp_CloseHandle
0x180015096  mov     [rdi+28h], rbx
0x18001509a  lea     rax, [rbx+1]
0x18001509e  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800150a4  jnz     short loc_1800150DC
0x1800150a6  call    cs:__imp_GetLastError
0x1800150ac  mov     ebx, eax
0x1800150ae  test    eax, eax
0x1800150b0  jle     short loc_1800150BB
0x1800150b2  movzx   ebx, ax
0x1800150b5  or      ebx, 80070000h
0x1800150bb  mov     r8d, ebx
0x1800150be  lea     rdx, aFailedToCreate_10; "Failed to create canceled event for Waa"...
0x1800150c5  jmp     loc_180014FB8
0x1800150ca  lea     rdx, aFailedToCreate_13; "Failed to create canceled event for Waa"...
0x1800150d1  mov     ecx, 2; unsigned __int8
0x1800150d6  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800150db  nop
0x1800150dc  mov     [rdi+18h], rbp
0x1800150e0  mov     rdx, rsi; struct TraceLoggingCorrelationVector *
0x1800150e3  mov     rcx, rdi; this
0x1800150e6  call    ?SetAndExtendCV@CWaasRemediation@WaasMedic@@AEAAJPEAVTraceLoggingCorrelationVector@@@Z; WaasMedic::CWaasRemediation::SetAndExtendCV(TraceLoggingCorrelationVector *)
0x1800150eb  mov     ebx, eax
0x1800150ed  test    eax, eax
0x1800150ef  jns     short loc_180015105
0x1800150f1  mov     r8d, eax
0x1800150f4  lea     rdx, aFailedToSetAnd_10; "Failed to set and extend cV in Waas rem"...
0x1800150fb  mov     ecx, 2; unsigned __int8
0x180015100  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180015105  mov     eax, ebx
0x180015107  shr     eax, 1Fh
0x18001510a  xor     al, 1
0x18001510c  mov     [rdi+20h], al
0x18001510f  mov     eax, ebx
0x180015111  mov     rcx, [rsp+0F8h+var_28]
0x180015119  xor     rcx, rsp; StackCookie
0x18001511c  call    __security_check_cookie
0x180015121  mov     rbx, [rsp+0F8h+arg_10]
0x180015129  add     rsp, 0E0h
0x180015130  pop     rdi
0x180015131  pop     rsi
0x180015132  pop     rbp
0x180015133  retn
```
