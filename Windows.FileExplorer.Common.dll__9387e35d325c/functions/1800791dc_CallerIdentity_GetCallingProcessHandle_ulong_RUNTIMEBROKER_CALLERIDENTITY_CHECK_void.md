# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x1800791dc`
- end: `0x1800792b8`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `220`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800790fc`

## callees

- `0x1800077c8`
- `0x1800791dc`
- `0x1800794a4`
- `0x18007967c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180079255`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180079255`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180079244`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180079244`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079266`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079266`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18007920f`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18007920f`

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
0x1800791dc  mov     [rsp+arg_0], rbx
0x1800791e1  push    rdi; int
0x1800791e2  sub     rsp, 20h
0x1800791e6  lea     rcx, [rsp+28h+ppInterface]
0x1800791eb  mov     qword ptr [r8], 0
0x1800791f2  mov     rbx, r8
0x1800791f5  mov     [rsp+28h+ppInterface], 0
0x1800791fe  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x180079203  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x180079208  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x18007920f  call    cs:__imp_CoGetCallContext
0x180079215  mov     edi, eax
0x180079217  test    eax, eax
0x180079219  js      short loc_18007923C
0x18007921b  mov     rcx, [rsp+28h+ppInterface]
0x180079220  mov     r8, rbx
0x180079223  mov     edx, 1000h
0x180079228  mov     rax, [rcx]
0x18007922b  mov     rax, [rax+18h]
0x18007922f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079234  mov     edi, eax
0x180079236  test    eax, eax
0x180079238  jns     short loc_18007924D
0x18007923a  jmp     short loc_1800792A1
0x18007923c  cmp     edi, 80010117h
0x180079242  jnz     short loc_180079288
0x180079244  call    cs:__imp_GetCurrentProcess
0x18007924a  mov     [rbx], rax
0x18007924d  call    ?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ; CallerIdentity::_EnsureRuntimeBrokerPID(void)
0x180079252  mov     rcx, [rbx]; Process
0x180079255  call    cs:__imp_GetProcessId
0x18007925b  cmp     eax, cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x180079261  jnz     short loc_18007927A
0x180079263  mov     rcx, [rbx]; hObject
0x180079266  call    cs:__imp_CloseHandle
0x18007926c  mov     qword ptr [rbx], 0
0x180079273  mov     edi, 80004005h
0x180079278  jmp     short loc_1800792A1
0x18007927a  lea     rcx, [rsp+28h+ppInterface]
0x18007927f  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x180079284  xor     eax, eax
0x180079286  jmp     short loc_1800792AD
0x180079288  mov     rcx, [rsp+28h]; this
0x18007928d  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180079294  mov     r9d, edi; char *
0x180079297  mov     edx, 58h ; 'X'; void *
0x18007929c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800792a1  lea     rcx, [rsp+28h+ppInterface]
0x1800792a6  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x1800792ab  mov     eax, edi
0x1800792ad  mov     rbx, [rsp+28h+arg_0]
0x1800792b2  add     rsp, 20h
0x1800792b6  pop     rdi
0x1800792b7  retn
```
