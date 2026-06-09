# _SendRpcRequest2

- ea: `0x18000dd48`
- end: `0x18000df8f`
- name: `_SendRpcRequest2`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004baa4`

## callees

- `0x18000dd48`
- `0x18000df98`
- `0x18000e09c`
- `0x180015bc0`
- `0x18002a2f0`
- `0x18002bbf4`
- `0x180031708`
- `0x180045354`
- `0x1800537a4`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ddc1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ddc1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000df60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000df60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df47`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000de87`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000de87`

## string_xrefs

- `0x18000dde7`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18000de2d`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18000def6`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`

## pseudocode

```c
__int64 __fastcall SendRpcRequest2(
        void *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        char a5,
        unsigned int *a6,
        _QWORD *a7)
{
  void *v10; // rdi
  HANDLE EventW; // rax
  void *v13; // rsi
  int NonzeroLastError; // eax
  unsigned int started; // ebx
  __int64 v16; // rdx
  DWORD v17; // eax
  int v18; // eax
  _QWORD *v19; // rcx
  HANDLE ProcessHeap; // rax
  unsigned int v22; // [rsp+20h] [rbp-C1h] BYREF
  void *v23; // [rsp+28h] [rbp-B9h] BYREF
  _QWORD *v24; // [rsp+30h] [rbp-B1h]
  HANDLE Handles[3]; // [rsp+38h] [rbp-A9h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+50h] [rbp-91h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v24 = a7;
  v10 = 0;
  v22 = 0;
  v23 = 0;
  pAsync.Size = 0;
  memset_0(&pAsync.Signature, 0, 0x84u);
  *a6 = 0;
  *a7 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v13 = EventW;
  if ( EventW )
  {
    if ( (*(_DWORD *)(a2 + 8) & 0x40000000) != 0 )
    {
      started = CtapTestCltStartSSCtapCommand(EventW, &pAsync, a4, a3);
      if ( started )
      {
        v16 = 475;
        goto LABEL_8;
      }
    }
    else
    {
      started = CtapCltStartSSCtapCommand(EventW, &pAsync, a4, a3);
      if ( started )
      {
        v16 = 483;
LABEL_8:
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)v16,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
          (const char *)started,
          v22);
        if ( (int)started > 0 )
          started = (unsigned __int16)started | 0x80070000;
        goto LABEL_34;
      }
    }
    Handles[1] = a1;
    started = 0;
    Handles[0] = v13;
    v17 = WaitForMultipleObjects((a1 != 0) + 1, Handles, 0, 0xFFFFFFFF);
    if ( v17 )
    {
      switch ( v17 )
      {
        case 1u:
          started = 1223;
          break;
        case 0x102u:
          started = 1460;
          break;
        case 0xFFFFFFFF:
          started = _GetNonzeroLastError();
          break;
        default:
          started = -2147418113;
          break;
      }
    }
    if ( (*(_DWORD *)(a2 + 8) & 0x40000000) != 0 )
      v18 = CtapTestCltCompleteSSCtapCommand(&pAsync, &v23, &v22);
    else
      v18 = CtapCltCompleteSSCtapCommand(&pAsync);
    if ( started )
    {
      if ( (int)started > 0 )
        started = (unsigned __int16)started | 0x80070000;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x21E,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
        (const char *)started,
        v22);
    }
    else
    {
      started = 0;
      if ( !v18 || (v18 > 0 ? (started = (unsigned __int16)v18 | 0x80070000) : (started = v18), (a5 & 1) != 0) )
      {
        v10 = 0;
        v19 = v24;
        *a6 = v22;
        *v19 = v23;
        goto LABEL_34;
      }
    }
    v10 = v23;
LABEL_34:
    CloseHandle(v13);
    goto LABEL_35;
  }
  NonzeroLastError = _GetNonzeroLastError();
  started = NonzeroLastError;
  if ( NonzeroLastError > 0 )
    started = (unsigned __int16)NonzeroLastError | 0x80070000;
  wil::details::in1diag3::Log_Hr(
    retaddr,
    (void *)0x1D2,
    (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
    (const char *)started,
    v22);
LABEL_35:
  if ( v10 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  return started;
}

```

## disassembly

```asm
0x18000dd48  mov     [rsp-8+arg_8], rbx
0x18000dd4d  push    rbp
0x18000dd4e  push    rsi
0x18000dd4f  push    rdi
0x18000dd50  push    r12
0x18000dd52  push    r13
0x18000dd54  push    r14
0x18000dd56  push    r15
0x18000dd58  lea     rbp, [rsp-0Fh]
0x18000dd5d  sub     rsp, 0F0h
0x18000dd64  mov     rax, cs:__security_cookie
0x18000dd6b  xor     rax, rsp
0x18000dd6e  mov     [rbp+3Fh+var_40], rax
0x18000dd72  mov     rsi, [rbp+3Fh+arg_30]
0x18000dd76  mov     ebx, r8d
0x18000dd79  mov     r13, [rbp+3Fh+arg_28]
0x18000dd7d  mov     r12, rdx
0x18000dd80  mov     r14, rcx
0x18000dd83  mov     [rsp+120h+var_F0], rsi
0x18000dd88  xor     edi, edi
0x18000dd8a  mov     [rsp+120h+var_100], 0; int
0x18000dd92  xor     edx, edx; Val
0x18000dd94  mov     [rsp+120h+var_F8], rdi
0x18000dd99  mov     r8d, 84h; Size
0x18000dd9f  mov     [rsp+120h+pAsync.Size], edi
0x18000dda3  lea     rcx, [rsp+120h+pAsync.Signature]; void *
0x18000dda8  mov     r15, r9
0x18000ddab  call    memset_0
0x18000ddb0  mov     [r13+0], edi
0x18000ddb4  xor     r9d, r9d; lpName
0x18000ddb7  xor     r8d, r8d; bInitialState
0x18000ddba  mov     [rsi], rdi
0x18000ddbd  xor     edx, edx; bManualReset
0x18000ddbf  xor     ecx, ecx; lpEventAttributes
0x18000ddc1  call    cs:__imp_CreateEventW
0x18000ddc7  mov     rsi, rax
0x18000ddca  test    rax, rax
0x18000ddcd  jnz     short loc_18000DE00
0x18000ddcf  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x18000ddd4  mov     ebx, eax
0x18000ddd6  test    eax, eax
0x18000ddd8  jle     short loc_18000DDE3
0x18000ddda  movzx   ebx, ax
0x18000dddd  or      ebx, 80070000h
0x18000dde3  mov     rcx, [rbp+47h]; this
0x18000dde7  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18000ddee  mov     r9d, ebx; char *
0x18000ddf1  mov     edx, 1D2h; void *
0x18000ddf6  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000ddfb  jmp     loc_18000DF4D
0x18000de00  test    dword ptr [r12+8], 40000000h
0x18000de09  lea     rdx, [rsp+120h+pAsync]
0x18000de0e  mov     r9d, ebx
0x18000de11  mov     r8, r15
0x18000de14  mov     rcx, rsi
0x18000de17  jz      short loc_18000DE52
0x18000de19  call    CtapTestCltStartSSCtapCommand
0x18000de1e  mov     ebx, eax
0x18000de20  test    eax, eax
0x18000de22  jz      short loc_18000DE64
0x18000de24  mov     edx, 1DBh; void *
0x18000de29  mov     rcx, [rbp+47h]; this
0x18000de2d  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18000de34  mov     r9d, ebx; char *
0x18000de37  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18000de3c  test    ebx, ebx
0x18000de3e  jle     loc_18000DF44
0x18000de44  movzx   ebx, bx
0x18000de47  or      ebx, 80070000h
0x18000de4d  jmp     loc_18000DF44
0x18000de52  call    CtapCltStartSSCtapCommand
0x18000de57  mov     ebx, eax
0x18000de59  test    eax, eax
0x18000de5b  jz      short loc_18000DE64
0x18000de5d  mov     edx, 1E3h
0x18000de62  jmp     short loc_18000DE29
0x18000de64  mov     [rsp+120h+var_E0], r14
0x18000de69  lea     rdx, [rsp+120h+Handles]; lpHandles
0x18000de6e  xor     ebx, ebx
0x18000de70  mov     [rsp+120h+Handles], rsi
0x18000de75  neg     r14
0x18000de78  sbb     ecx, ecx
0x18000de7a  or      edi, 0FFFFFFFFh
0x18000de7d  neg     ecx
0x18000de7f  mov     r9d, edi; dwMilliseconds
0x18000de82  inc     ecx; nCount
0x18000de84  xor     r8d, r8d; bWaitAll
0x18000de87  call    cs:__imp_WaitForMultipleObjects
0x18000de8d  test    eax, eax
0x18000de8f  jz      short loc_18000DEBD
0x18000de91  cmp     eax, 1
0x18000de94  jz      short loc_18000DEB8
0x18000de96  cmp     eax, 102h
0x18000de9b  jz      short loc_18000DEB1
0x18000de9d  cmp     eax, edi
0x18000de9f  jz      short loc_18000DEA8
0x18000dea1  mov     ebx, 8000FFFFh
0x18000dea6  jmp     short loc_18000DEBD
0x18000dea8  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x18000dead  mov     ebx, eax
0x18000deaf  jmp     short loc_18000DEBD
0x18000deb1  mov     ebx, 5B4h
0x18000deb6  jmp     short loc_18000DEBD
0x18000deb8  mov     ebx, 4C7h
0x18000debd  test    dword ptr [r12+8], 40000000h
0x18000dec6  lea     r8, [rsp+120h+var_100]
0x18000decb  lea     rdx, [rsp+120h+var_F8]
0x18000ded0  lea     rcx, [rsp+120h+pAsync]; pAsync
0x18000ded5  jz      short loc_18000DEDE
0x18000ded7  call    CtapTestCltCompleteSSCtapCommand
0x18000dedc  jmp     short loc_18000DEE3
0x18000dede  call    CtapCltCompleteSSCtapCommand
0x18000dee3  test    ebx, ebx
0x18000dee5  jz      short loc_18000DF11
0x18000dee7  jle     short loc_18000DEF2
0x18000dee9  movzx   ebx, bx
0x18000deec  or      ebx, 80070000h
0x18000def2  mov     rcx, [rbp+47h]; this
0x18000def6  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18000defd  mov     r9d, ebx; char *
0x18000df00  mov     edx, 21Eh; void *
0x18000df05  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000df0a  mov     rdi, [rsp+120h+var_F8]
0x18000df0f  jmp     short loc_18000DF44
0x18000df11  xor     ebx, ebx
0x18000df13  test    eax, eax
0x18000df15  jz      short loc_18000DF2D
0x18000df17  jg      short loc_18000DF1D
0x18000df19  mov     ebx, eax
0x18000df1b  jmp     short loc_18000DF26
0x18000df1d  movzx   ebx, ax
0x18000df20  or      ebx, 80070000h
0x18000df26  mov     eax, dword ptr [rbp+3Fh+arg_20]
0x18000df29  test    al, 1
0x18000df2b  jz      short loc_18000DF0A
0x18000df2d  mov     eax, [rsp+120h+var_100]
0x18000df31  xor     edi, edi
0x18000df33  mov     rcx, [rsp+120h+var_F0]
0x18000df38  mov     [r13+0], eax
0x18000df3c  mov     rax, [rsp+120h+var_F8]
0x18000df41  mov     [rcx], rax
0x18000df44  mov     rcx, rsi; hObject
0x18000df47  call    cs:__imp_CloseHandle
0x18000df4d  test    rdi, rdi
0x18000df50  jz      short loc_18000DF66
0x18000df52  call    cs:__imp_GetProcessHeap
0x18000df58  mov     r8, rdi; lpMem
0x18000df5b  xor     edx, edx; dwFlags
0x18000df5d  mov     rcx, rax; hHeap
0x18000df60  call    cs:__imp_HeapFree
0x18000df66  mov     eax, ebx
0x18000df68  mov     rcx, [rbp+3Fh+var_40]
0x18000df6c  xor     rcx, rsp; StackCookie
0x18000df6f  call    __security_check_cookie
0x18000df74  mov     rbx, [rsp+120h+arg_8]
0x18000df7c  add     rsp, 0F0h
0x18000df83  pop     r15
0x18000df85  pop     r14
0x18000df87  pop     r13
0x18000df89  pop     r12
0x18000df8b  pop     rdi
0x18000df8c  pop     rsi
0x18000df8d  pop     rbp
0x18000df8e  retn
```
