# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x18003de0c`
- end: `0x18003def8`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `236`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003dd34`
- `0x18003dde8`
- `0x1800402e0`

## callees

- `0x180009d6c`
- `0x18003de0c`
- `0x18003e0d4`
- `0x18003e2d0`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003de90`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003de90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003de7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003de7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dea1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dea1`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18003de45`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18003de45`

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
  Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&ppInterface);
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
    Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&ppInterface);
    return 0;
  }
  CloseHandle(*a3);
  *a3 = 0;
  v6 = -2147467259;
LABEL_11:
  Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&ppInterface);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003de0c  mov     rax, rsp
0x18003de0f  mov     [rax+8], rbx
0x18003de13  mov     [rax+10h], rsi
0x18003de17  push    rdi; int
0x18003de18  sub     rsp, 20h
0x18003de1c  lea     rcx, [rax+18h]
0x18003de20  mov     qword ptr [r8], 0
0x18003de27  mov     rbx, r8
0x18003de2a  mov     qword ptr [rax+18h], 0
0x18003de32  mov     esi, edx
0x18003de34  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18003de39  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x18003de3e  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x18003de45  call    cs:__imp_CoGetCallContext
0x18003de4b  mov     edi, eax
0x18003de4d  test    eax, eax
0x18003de4f  js      short loc_18003DE72
0x18003de51  mov     rcx, [rsp+28h+ppInterface]
0x18003de56  mov     r8, rbx
0x18003de59  mov     edx, 1000h
0x18003de5e  mov     rax, [rcx]
0x18003de61  mov     rax, [rax+18h]
0x18003de65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de6a  mov     edi, eax
0x18003de6c  test    eax, eax
0x18003de6e  jns     short loc_18003DE83
0x18003de70  jmp     short loc_18003DEDC
0x18003de72  cmp     edi, 80010117h
0x18003de78  jnz     short loc_18003DEC3
0x18003de7a  call    cs:__imp_GetCurrentProcess
0x18003de80  mov     [rbx], rax
0x18003de83  cmp     esi, 1
0x18003de86  jnz     short loc_18003DEB5
0x18003de88  call    ?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ; CallerIdentity::_EnsureRuntimeBrokerPID(void)
0x18003de8d  mov     rcx, [rbx]; Process
0x18003de90  call    cs:__imp_GetProcessId
0x18003de96  cmp     eax, cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x18003de9c  jnz     short loc_18003DEB5
0x18003de9e  mov     rcx, [rbx]; hObject
0x18003dea1  call    cs:__imp_CloseHandle
0x18003dea7  mov     qword ptr [rbx], 0
0x18003deae  mov     edi, 80004005h
0x18003deb3  jmp     short loc_18003DEDC
0x18003deb5  lea     rcx, [rsp+28h+ppInterface]
0x18003deba  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18003debf  xor     eax, eax
0x18003dec1  jmp     short loc_18003DEE8
0x18003dec3  mov     rcx, [rsp+28h]; this
0x18003dec8  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18003decf  mov     r9d, edi; char *
0x18003ded2  mov     edx, 58h ; 'X'; void *
0x18003ded7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dedc  lea     rcx, [rsp+28h+ppInterface]
0x18003dee1  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18003dee6  mov     eax, edi
0x18003dee8  mov     rbx, [rsp+28h+arg_0]
0x18003deed  mov     rsi, [rsp+28h+arg_8]
0x18003def2  add     rsp, 20h
0x18003def6  pop     rdi
0x18003def7  retn
```
