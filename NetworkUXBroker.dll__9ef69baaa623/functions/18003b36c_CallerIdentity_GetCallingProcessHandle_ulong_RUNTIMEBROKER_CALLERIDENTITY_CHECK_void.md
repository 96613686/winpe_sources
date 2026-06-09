# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x18003b36c`
- end: `0x18003b458`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `236`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b27c`
- `0x18003b348`

## callees

- `0x18000e768`
- `0x18003b36c`
- `0x18003b71c`
- `0x18003ba0c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003b3da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003b3da`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003b3f0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003b3f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b401`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b401`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18003b3a5`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18003b3a5`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCallingProcessHandle(__int64 a1, int a2, HANDLE *a3)
{
  HRESULT v5; // eax
  int v6; // edi
  CallerIdentity *v7; // rcx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *ppInterface; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  ppInterface = 0;
  Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(&ppInterface);
  v5 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( v5 != -2147417833 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
        (const char *)(unsigned int)v5,
        v9);
      goto LABEL_11;
    }
    *a3 = GetCurrentProcess();
  }
  else
  {
    v6 = (*(__int64 (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)ppInterface + 24LL))(ppInterface, 4096, a3);
    if ( v6 < 0 )
      goto LABEL_11;
  }
  if ( a2 != 1
    || (CallerIdentity::_EnsureRuntimeBrokerPID(v7), GetProcessId(*a3) != CallerIdentity::g_dwRuntimeBrokerProcessId) )
  {
    Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(&ppInterface);
    return 0;
  }
  CloseHandle(*a3);
  *a3 = 0;
  v6 = -2147467259;
LABEL_11:
  Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(&ppInterface);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003b36c  mov     rax, rsp
0x18003b36f  mov     [rax+8], rbx
0x18003b373  mov     [rax+10h], rsi
0x18003b377  push    rdi; int
0x18003b378  sub     rsp, 20h
0x18003b37c  lea     rcx, [rax+18h]
0x18003b380  mov     qword ptr [r8], 0
0x18003b387  mov     rbx, r8
0x18003b38a  mov     qword ptr [rax+18h], 0
0x18003b392  mov     esi, edx
0x18003b394  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x18003b399  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x18003b39e  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x18003b3a5  call    cs:__imp_CoGetCallContext
0x18003b3ab  mov     edi, eax
0x18003b3ad  test    eax, eax
0x18003b3af  js      short loc_18003B3D2
0x18003b3b1  mov     rcx, [rsp+28h+ppInterface]
0x18003b3b6  mov     r8, rbx
0x18003b3b9  mov     edx, 1000h
0x18003b3be  mov     rax, [rcx]
0x18003b3c1  mov     rax, [rax+18h]
0x18003b3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3ca  mov     edi, eax
0x18003b3cc  test    eax, eax
0x18003b3ce  jns     short loc_18003B3E3
0x18003b3d0  jmp     short loc_18003B43C
0x18003b3d2  cmp     edi, 80010117h
0x18003b3d8  jnz     short loc_18003B423
0x18003b3da  call    cs:__imp_GetCurrentProcess
0x18003b3e0  mov     [rbx], rax
0x18003b3e3  cmp     esi, 1
0x18003b3e6  jnz     short loc_18003B415
0x18003b3e8  call    ?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ; CallerIdentity::_EnsureRuntimeBrokerPID(void)
0x18003b3ed  mov     rcx, [rbx]; Process
0x18003b3f0  call    cs:__imp_GetProcessId
0x18003b3f6  cmp     eax, cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x18003b3fc  jnz     short loc_18003B415
0x18003b3fe  mov     rcx, [rbx]; hObject
0x18003b401  call    cs:__imp_CloseHandle
0x18003b407  mov     qword ptr [rbx], 0
0x18003b40e  mov     edi, 80004005h
0x18003b413  jmp     short loc_18003B43C
0x18003b415  lea     rcx, [rsp+28h+ppInterface]
0x18003b41a  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x18003b41f  xor     eax, eax
0x18003b421  jmp     short loc_18003B448
0x18003b423  mov     rcx, [rsp+28h]; this
0x18003b428  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18003b42f  mov     r9d, edi; char *
0x18003b432  mov     edx, 58h ; 'X'; void *
0x18003b437  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b43c  lea     rcx, [rsp+28h+ppInterface]
0x18003b441  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x18003b446  mov     eax, edi
0x18003b448  mov     rbx, [rsp+28h+arg_0]
0x18003b44d  mov     rsi, [rsp+28h+arg_8]
0x18003b452  add     rsp, 20h
0x18003b456  pop     rdi
0x18003b457  retn
```
