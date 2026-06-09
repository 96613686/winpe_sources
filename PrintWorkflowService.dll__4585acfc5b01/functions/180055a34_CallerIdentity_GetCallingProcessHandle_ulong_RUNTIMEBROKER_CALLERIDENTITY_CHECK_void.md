# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x180055a34`
- end: `0x180055b1f`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `235`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d414`
- `0x180054bc0`
- `0x180055968`

## callees

- `0x180005038`
- `0x180010b0c`
- `0x1800542a0`
- `0x180055a34`
- `0x180055f6c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180055aa1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180055aa1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180055ab7`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180055ab7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055ac8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055ac8`

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
  Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(&ppInterface);
  v5 = CoGetCallContext_0(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface);
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
    Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(&ppInterface);
    return 0;
  }
  CloseHandle(*a3);
  *a3 = 0;
  v6 = -2147467259;
LABEL_11:
  Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(&ppInterface);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180055a34  mov     rax, rsp
0x180055a37  mov     [rax+8], rbx
0x180055a3b  mov     [rax+10h], rsi
0x180055a3f  push    rdi; int
0x180055a40  sub     rsp, 20h
0x180055a44  lea     rcx, [rax+18h]
0x180055a48  mov     qword ptr [r8], 0
0x180055a4f  mov     rbx, r8
0x180055a52  mov     qword ptr [rax+18h], 0
0x180055a5a  mov     esi, edx
0x180055a5c  call    ?InternalRelease@?$ComPtr@UIApplicationViewCompatibilityManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(void)
0x180055a61  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x180055a66  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x180055a6d  call    CoGetCallContext_0
0x180055a72  mov     edi, eax
0x180055a74  test    eax, eax
0x180055a76  js      short loc_180055A99
0x180055a78  mov     rcx, [rsp+28h+ppInterface]
0x180055a7d  mov     r8, rbx
0x180055a80  mov     edx, 1000h
0x180055a85  mov     rax, [rcx]
0x180055a88  mov     rax, [rax+18h]
0x180055a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a91  mov     edi, eax
0x180055a93  test    eax, eax
0x180055a95  jns     short loc_180055AAA
0x180055a97  jmp     short loc_180055B03
0x180055a99  cmp     edi, 80010117h
0x180055a9f  jnz     short loc_180055AEA
0x180055aa1  call    cs:__imp_GetCurrentProcess
0x180055aa7  mov     [rbx], rax
0x180055aaa  cmp     esi, 1
0x180055aad  jnz     short loc_180055ADC
0x180055aaf  call    ?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ; CallerIdentity::_EnsureRuntimeBrokerPID(void)
0x180055ab4  mov     rcx, [rbx]; Process
0x180055ab7  call    cs:__imp_GetProcessId
0x180055abd  cmp     eax, cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x180055ac3  jnz     short loc_180055ADC
0x180055ac5  mov     rcx, [rbx]; hObject
0x180055ac8  call    cs:__imp_CloseHandle
0x180055ace  mov     qword ptr [rbx], 0
0x180055ad5  mov     edi, 80004005h
0x180055ada  jmp     short loc_180055B03
0x180055adc  lea     rcx, [rsp+28h+ppInterface]
0x180055ae1  call    ?InternalRelease@?$ComPtr@UIApplicationViewCompatibilityManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(void)
0x180055ae6  xor     eax, eax
0x180055ae8  jmp     short loc_180055B0F
0x180055aea  mov     rcx, [rsp+28h]; this
0x180055aef  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180055af6  mov     r9d, edi; char *
0x180055af9  mov     edx, 58h ; 'X'; void *
0x180055afe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055b03  lea     rcx, [rsp+28h+ppInterface]
0x180055b08  call    ?InternalRelease@?$ComPtr@UIApplicationViewCompatibilityManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IApplicationViewCompatibilityManager>::InternalRelease(void)
0x180055b0d  mov     eax, edi
0x180055b0f  mov     rbx, [rsp+28h+arg_0]
0x180055b14  mov     rsi, [rsp+28h+arg_8]
0x180055b19  add     rsp, 20h
0x180055b1d  pop     rdi
0x180055b1e  retn
```
