# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x18005cc80`
- end: `0x18005cd5c`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `220`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005cbbc`

## callees

- `0x18001e798`
- `0x18005cc80`
- `0x18005cf44`
- `0x18005cfc4`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18005ccb3`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18005ccb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cce8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cce8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18005ccf9`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18005ccf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd0a`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCallingProcessHandle(__int64 a1, __int64 a2, HANDLE *a3)
{
  HRESULT v4; // eax
  int v5; // edi
  CallerIdentity *v6; // rcx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *ppInterface; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  ppInterface = 0;
  Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(&ppInterface);
  v4 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( v4 != -2147417833 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
        (const char *)(unsigned int)v4,
        v8);
      goto LABEL_10;
    }
    *a3 = GetCurrentProcess();
  }
  else
  {
    v5 = (*(__int64 (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)ppInterface + 24LL))(ppInterface, 4096, a3);
    if ( v5 < 0 )
      goto LABEL_10;
  }
  CallerIdentity::_EnsureRuntimeBrokerPID(v6);
  if ( GetProcessId(*a3) != CallerIdentity::g_dwRuntimeBrokerProcessId )
  {
    Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(&ppInterface);
    return 0;
  }
  CloseHandle(*a3);
  *a3 = 0;
  v5 = -2147467259;
LABEL_10:
  Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(&ppInterface);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005cc80  mov     [rsp+arg_0], rbx
0x18005cc85  push    rdi; int
0x18005cc86  sub     rsp, 20h
0x18005cc8a  lea     rcx, [rsp+28h+ppInterface]
0x18005cc8f  mov     qword ptr [r8], 0
0x18005cc96  mov     rbx, r8
0x18005cc99  mov     [rsp+28h+ppInterface], 0
0x18005cca2  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x18005cca7  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x18005ccac  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x18005ccb3  call    cs:__imp_CoGetCallContext
0x18005ccb9  mov     edi, eax
0x18005ccbb  test    eax, eax
0x18005ccbd  js      short loc_18005CCE0
0x18005ccbf  mov     rcx, [rsp+28h+ppInterface]
0x18005ccc4  mov     r8, rbx
0x18005ccc7  mov     edx, 1000h
0x18005cccc  mov     rax, [rcx]
0x18005cccf  mov     rax, [rax+18h]
0x18005ccd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ccd8  mov     edi, eax
0x18005ccda  test    eax, eax
0x18005ccdc  jns     short loc_18005CCF1
0x18005ccde  jmp     short loc_18005CD45
0x18005cce0  cmp     edi, 80010117h
0x18005cce6  jnz     short loc_18005CD2C
0x18005cce8  call    cs:__imp_GetCurrentProcess
0x18005ccee  mov     [rbx], rax
0x18005ccf1  call    ?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ; CallerIdentity::_EnsureRuntimeBrokerPID(void)
0x18005ccf6  mov     rcx, [rbx]; Process
0x18005ccf9  call    cs:__imp_GetProcessId
0x18005ccff  cmp     eax, cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x18005cd05  jnz     short loc_18005CD1E
0x18005cd07  mov     rcx, [rbx]; hObject
0x18005cd0a  call    cs:__imp_CloseHandle
0x18005cd10  mov     qword ptr [rbx], 0
0x18005cd17  mov     edi, 80004005h
0x18005cd1c  jmp     short loc_18005CD45
0x18005cd1e  lea     rcx, [rsp+28h+ppInterface]
0x18005cd23  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x18005cd28  xor     eax, eax
0x18005cd2a  jmp     short loc_18005CD51
0x18005cd2c  mov     rcx, [rsp+28h]; this
0x18005cd31  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18005cd38  mov     r9d, edi; char *
0x18005cd3b  mov     edx, 58h ; 'X'; void *
0x18005cd40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cd45  lea     rcx, [rsp+28h+ppInterface]
0x18005cd4a  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x18005cd4f  mov     eax, edi
0x18005cd51  mov     rbx, [rsp+28h+arg_0]
0x18005cd56  add     rsp, 20h
0x18005cd5a  pop     rdi
0x18005cd5b  retn
```
