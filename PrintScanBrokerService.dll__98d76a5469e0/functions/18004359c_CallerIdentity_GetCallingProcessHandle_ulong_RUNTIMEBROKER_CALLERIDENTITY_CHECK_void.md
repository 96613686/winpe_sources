# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x18004359c`
- end: `0x180043688`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `236`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800434ac`
- `0x180043578`

## callees

- `0x18000ddac`
- `0x18004359c`
- `0x18004390c`
- `0x180043d2c`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800435d5`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800435d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004360a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004360a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180043620`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180043620`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043631`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043631`

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
0x18004359c  mov     rax, rsp
0x18004359f  mov     [rax+8], rbx
0x1800435a3  mov     [rax+10h], rsi
0x1800435a7  push    rdi; int
0x1800435a8  sub     rsp, 20h
0x1800435ac  lea     rcx, [rax+18h]
0x1800435b0  mov     qword ptr [r8], 0
0x1800435b7  mov     rbx, r8
0x1800435ba  mov     qword ptr [rax+18h], 0
0x1800435c2  mov     esi, edx
0x1800435c4  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x1800435c9  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x1800435ce  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x1800435d5  call    cs:__imp_CoGetCallContext
0x1800435db  mov     edi, eax
0x1800435dd  test    eax, eax
0x1800435df  js      short loc_180043602
0x1800435e1  mov     rcx, [rsp+28h+ppInterface]
0x1800435e6  mov     r8, rbx
0x1800435e9  mov     edx, 1000h
0x1800435ee  mov     rax, [rcx]
0x1800435f1  mov     rax, [rax+18h]
0x1800435f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435fa  mov     edi, eax
0x1800435fc  test    eax, eax
0x1800435fe  jns     short loc_180043613
0x180043600  jmp     short loc_18004366C
0x180043602  cmp     edi, 80010117h
0x180043608  jnz     short loc_180043653
0x18004360a  call    cs:__imp_GetCurrentProcess
0x180043610  mov     [rbx], rax
0x180043613  cmp     esi, 1
0x180043616  jnz     short loc_180043645
0x180043618  call    ?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ; CallerIdentity::_EnsureRuntimeBrokerPID(void)
0x18004361d  mov     rcx, [rbx]; Process
0x180043620  call    cs:__imp_GetProcessId
0x180043626  cmp     eax, cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x18004362c  jnz     short loc_180043645
0x18004362e  mov     rcx, [rbx]; hObject
0x180043631  call    cs:__imp_CloseHandle
0x180043637  mov     qword ptr [rbx], 0
0x18004363e  mov     edi, 80004005h
0x180043643  jmp     short loc_18004366C
0x180043645  lea     rcx, [rsp+28h+ppInterface]
0x18004364a  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x18004364f  xor     eax, eax
0x180043651  jmp     short loc_180043678
0x180043653  mov     rcx, [rsp+28h]; this
0x180043658  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18004365f  mov     r9d, edi; char *
0x180043662  mov     edx, 58h ; 'X'; void *
0x180043667  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004366c  lea     rcx, [rsp+28h+ppInterface]
0x180043671  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x180043676  mov     eax, edi
0x180043678  mov     rbx, [rsp+28h+arg_0]
0x18004367d  mov     rsi, [rsp+28h+arg_8]
0x180043682  add     rsp, 20h
0x180043686  pop     rdi
0x180043687  retn
```
