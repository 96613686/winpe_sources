# W32SCard::GetStatusChangeWrapper(tagRDPDR_IOREQUEST_PACKET *,ulong)

- ea: `0x18007328c`
- end: `0x180073419`
- name: `?GetStatusChangeWrapper@W32SCard@@IEAAXPEAUtagRDPDR_IOREQUEST_PACKET@@K@Z`
- size: `397`
- prototype: `void __fastcall(W32SCard *__hidden this, struct tagRDPDR_IOREQUEST_PACKET *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18054d3b0`

## callees

- `0x18002a334`
- `0x180039ce4`
- `0x18007328c`
- `0x180073420`
- `0x18007344c`
- `0x180073de0`
- `0x1800ebb60`
- `0x1800ee8f8`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800733bf`
- `KERNEL32!WaitForSingleObject` at `0x1800733bf`
- `KERNEL32!CloseHandle` at `0x1800733c8`
- `KERNEL32!CloseHandle` at `0x1800733c8`
- `KERNEL32!FreeLibrary` at `0x1800733d1`
- `KERNEL32!FreeLibrary` at `0x1800733d1`
- `KERNEL32!LeaveCriticalSection` at `0x18007335b`
- `KERNEL32!LeaveCriticalSection` at `0x1800733aa`
- `KERNEL32!LeaveCriticalSection` at `0x1800733ef`
- `KERNEL32!LeaveCriticalSection` at `0x18007335b`
- `KERNEL32!LeaveCriticalSection` at `0x1800733aa`
- `KERNEL32!LeaveCriticalSection` at `0x1800733ef`
- `KERNEL32!EnterCriticalSection` at `0x180073349`
- `KERNEL32!EnterCriticalSection` at `0x180073349`
- `KERNEL32!CreateThread` at `0x180073383`
- `KERNEL32!CreateThread` at `0x180073383`
- `KERNEL32!ResumeThread` at `0x1800733b3`
- `KERNEL32!ResumeThread` at `0x1800733fc`
- `KERNEL32!ResumeThread` at `0x1800733b3`
- `KERNEL32!ResumeThread` at `0x1800733fc`

## pseudocode

```c
void __fastcall W32SCard::GetStatusChangeWrapper(
        struct _RTL_CRITICAL_SECTION *this,
        struct tagRDPDR_IOREQUEST_PACKET *a2,
        int a3)
{
  HMODULE v6; // r15
  _QWORD *v7; // rbx
  int v8; // edi
  _QWORD *v9; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HANDLE v11; // rax
  void *v12; // rsi
  int v13; // eax
  struct _RTL_CRITICAL_SECTION *v14; // rcx
  DWORD ThreadId; // [rsp+78h] [rbp+20h] BYREF

  ThreadId = 0;
  v6 = W32SCard::AddRefCurrentModule((W32SCard *)this);
  if ( !v6 )
  {
    v7 = 0;
    v8 = -2146435041;
LABEL_16:
    MIDL_user_free(v7);
    W32SCard::EncodeAndChannelWriteLongReturn((W32SCard *)this, a2, v8);
    return;
  }
  v9 = MIDL_user_allocate(0x28u);
  v7 = v9;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        137,
        WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    v8 = -2146435066;
    goto LABEL_15;
  }
  *v9 = this;
  v8 = 0;
  v9[1] = a2;
  *((_DWORD *)v9 + 4) = a3;
  v9[3] = v6;
  v9[4] = 0;
  EnterCriticalSection(this + 18);
  if ( LODWORD(this[20].DebugInfo) )
    goto LABEL_10;
  v11 = CreateThread(0, 0, W32SCard::GetStatusChangeThreadProc, v7, 4u, &ThreadId);
  v12 = v11;
  if ( !v11 )
  {
    v8 = -2146435041;
LABEL_10:
    LeaveCriticalSection(this + 18);
LABEL_15:
    FreeLibrary(v6);
    goto LABEL_16;
  }
  v13 = W32SCard::AddThreadToList((W32SCard *)this, v11);
  v14 = this + 18;
  if ( !v13 )
  {
    LeaveCriticalSection(v14);
    ResumeThread(v12);
    WaitForSingleObject(v12, 0xFFFFFFFF);
    CloseHandle(v12);
    goto LABEL_15;
  }
  LeaveCriticalSection(v14);
  v7[4] = v12;
  ResumeThread(v12);
}

```

## disassembly

```asm
0x18007328c  mov     [rsp+arg_0], rbx
0x180073291  mov     [rsp+arg_8], rbp
0x180073296  push    rsi
0x180073297  push    rdi
0x180073298  push    r12
0x18007329a  push    r14
0x18007329c  push    r15
0x18007329e  sub     rsp, 30h
0x1800732a2  mov     esi, r8d
0x1800732a5  mov     [rsp+58h+ThreadId], 0
0x1800732ad  mov     r12, rdx
0x1800732b0  mov     r14, rcx
0x1800732b3  call    ?AddRefCurrentModule@W32SCard@@IEAAPEAUHINSTANCE__@@XZ; W32SCard::AddRefCurrentModule(void)
0x1800732b8  mov     r15, rax
0x1800732bb  test    rax, rax
0x1800732be  jnz     short loc_1800732CC
0x1800732c0  xor     ebx, ebx
0x1800732c2  mov     edi, 8010001Fh
0x1800732c7  jmp     loc_1800733D7
0x1800732cc  mov     ecx, 28h ; '('; size
0x1800732d1  call    MIDL_user_allocate
0x1800732d6  mov     rbx, rax
0x1800732d9  test    rax, rax
0x1800732dc  jnz     short loc_18007332B
0x1800732de  mov     rax, cs:WPP_GLOBAL_Control
0x1800732e5  lea     rcx, WPP_GLOBAL_Control
0x1800732ec  cmp     rax, rcx
0x1800732ef  jz      short loc_180073321
0x1800732f1  test    byte ptr [rax+1Ch], 1
0x1800732f5  jz      short loc_180073321
0x1800732f7  cmp     byte ptr [rax+19h], 2
0x1800732fb  jb      short loc_180073321
0x1800732fd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180073302  mov     rcx, cs:WPP_GLOBAL_Control
0x180073309  lea     r8, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids
0x180073310  mov     edx, 89h
0x180073315  mov     r9d, eax
0x180073318  mov     rcx, [rcx+10h]
0x18007331c  call    WPP_SF_d
0x180073321  mov     edi, 80100006h
0x180073326  jmp     loc_1800733CE
0x18007332b  lea     rbp, [r14+2D0h]
0x180073332  mov     [rax], r14
0x180073335  xor     edi, edi
0x180073337  mov     [rax+8], r12
0x18007333b  mov     rcx, rbp; lpCriticalSection
0x18007333e  mov     [rax+10h], esi
0x180073341  mov     [rax+18h], r15
0x180073345  mov     [rax+20h], rdi
0x180073349  call    cs:__imp_EnterCriticalSection
0x18007334f  cmp     [r14+320h], edi
0x180073356  jz      short loc_180073363
0x180073358  mov     rcx, rbp; lpCriticalSection
0x18007335b  call    cs:__imp_LeaveCriticalSection
0x180073361  jmp     short loc_1800733CE
0x180073363  lea     rax, [rsp+58h+ThreadId]
0x180073368  mov     r9, rbx; lpParameter
0x18007336b  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180073370  lea     r8, ?GetStatusChangeThreadProc@W32SCard@@KAKPEAX@Z; lpStartAddress
0x180073377  xor     edx, edx; dwStackSize
0x180073379  mov     [rsp+58h+dwCreationFlags], 4; dwCreationFlags
0x180073381  xor     ecx, ecx; lpThreadAttributes
0x180073383  call    cs:__imp_CreateThread
0x180073389  mov     rsi, rax
0x18007338c  test    rax, rax
0x18007338f  jnz     short loc_180073398
0x180073391  mov     edi, 8010001Fh
0x180073396  jmp     short loc_180073358
0x180073398  mov     rdx, rsi; void *
0x18007339b  mov     rcx, r14; this
0x18007339e  call    ?AddThreadToList@W32SCard@@IEAAHPEAX@Z; W32SCard::AddThreadToList(void *)
0x1800733a3  mov     rcx, rbp; lpCriticalSection
0x1800733a6  test    eax, eax
0x1800733a8  jnz     short loc_1800733EF
0x1800733aa  call    cs:__imp_LeaveCriticalSection
0x1800733b0  mov     rcx, rsi; hThread
0x1800733b3  call    cs:__imp_ResumeThread
0x1800733b9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800733bc  mov     rcx, rsi; hHandle
0x1800733bf  call    cs:__imp_WaitForSingleObject
0x1800733c5  mov     rcx, rsi; hObject
0x1800733c8  call    cs:__imp_CloseHandle
0x1800733ce  mov     rcx, r15; hLibModule
0x1800733d1  call    cs:__imp_FreeLibrary
0x1800733d7  mov     rcx, rbx; void *
0x1800733da  call    MIDL_user_free
0x1800733df  mov     r8d, edi; int
0x1800733e2  mov     rdx, r12; struct tagRDPDR_IOREQUEST_PACKET *
0x1800733e5  mov     rcx, r14; this
0x1800733e8  call    ?EncodeAndChannelWriteLongReturn@W32SCard@@IEAAXPEAUtagRDPDR_IOREQUEST_PACKET@@J@Z; W32SCard::EncodeAndChannelWriteLongReturn(tagRDPDR_IOREQUEST_PACKET *,long)
0x1800733ed  jmp     short loc_180073402
0x1800733ef  call    cs:__imp_LeaveCriticalSection
0x1800733f5  mov     rcx, rsi; hThread
0x1800733f8  mov     [rbx+20h], rsi
0x1800733fc  call    cs:__imp_ResumeThread
0x180073402  mov     rbx, [rsp+58h+arg_0]
0x180073407  mov     rbp, [rsp+58h+arg_8]
0x18007340c  add     rsp, 30h
0x180073410  pop     r15
0x180073412  pop     r14
0x180073414  pop     r12
0x180073416  pop     rdi
0x180073417  pop     rsi
0x180073418  retn
```
