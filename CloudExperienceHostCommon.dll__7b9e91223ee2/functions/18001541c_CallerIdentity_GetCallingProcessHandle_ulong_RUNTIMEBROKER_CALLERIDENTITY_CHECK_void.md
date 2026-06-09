# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x18001541c`
- end: `0x180015535`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `281`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800153b0`
- `0x1800cbc78`

## callees

- `0x1800153f8`
- `0x18001541c`
- `0x18001553c`
- `0x1800cbd10`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800154c3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800154c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800154ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800154ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800154d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800154d4`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180015455`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180015455`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCallingProcessHandle(__int64 a1, int a2, HANDLE *a3)
{
  HRESULT v5; // eax
  int v6; // edi
  CallerIdentity *v7; // rcx
  void *v8; // rcx
  int v10; // [rsp+20h] [rbp-8h]
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
        v10);
      Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(&ppInterface);
      return (unsigned int)v6;
    }
    *a3 = GetCurrentProcess();
  }
  else
  {
    v6 = (*(__int64 (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)ppInterface + 24LL))(ppInterface, 4096, a3);
    if ( v6 < 0 )
    {
      v8 = ppInterface;
      if ( ppInterface )
      {
        ppInterface = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
      }
      return (unsigned int)v6;
    }
  }
  if ( a2 == 1
    && (CallerIdentity::_EnsureRuntimeBrokerPID(v7), GetProcessId(*a3) == CallerIdentity::g_dwRuntimeBrokerProcessId) )
  {
    CloseHandle(*a3);
    *a3 = 0;
    Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(&ppInterface);
    return 2147500037LL;
  }
  else
  {
    Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(&ppInterface);
    return 0;
  }
}

```

## disassembly

```asm
0x18001541c  mov     rax, rsp
0x18001541f  mov     [rax+8], rbx
0x180015423  mov     [rax+10h], rsi
0x180015427  push    rdi; int
0x180015428  sub     rsp, 20h
0x18001542c  lea     rcx, [rax+18h]
0x180015430  mov     qword ptr [r8], 0
0x180015437  mov     rbx, r8
0x18001543a  mov     qword ptr [rax+18h], 0
0x180015442  mov     esi, edx
0x180015444  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x180015449  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x18001544e  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x180015455  call    cs:__imp_CoGetCallContext
0x18001545b  mov     edi, eax
0x18001545d  test    eax, eax
0x18001545f  js      short loc_1800154A5
0x180015461  mov     rcx, [rsp+28h+ppInterface]
0x180015466  mov     r8, rbx
0x180015469  mov     edx, 1000h
0x18001546e  mov     rax, [rcx]
0x180015471  mov     rax, [rax+18h]
0x180015475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001547a  mov     edi, eax
0x18001547c  test    eax, eax
0x18001547e  jns     short loc_1800154B6
0x180015480  mov     rcx, [rsp+28h+ppInterface]
0x180015485  test    rcx, rcx
0x180015488  jz      loc_180015523
0x18001548e  mov     [rsp+28h+ppInterface], 0
0x180015497  mov     rdx, [rcx]
0x18001549a  mov     rax, [rdx+10h]
0x18001549e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154a3  jmp     short loc_180015523
0x1800154a5  cmp     edi, 80010117h
0x1800154ab  jnz     short loc_180015500
0x1800154ad  call    cs:__imp_GetCurrentProcess
0x1800154b3  mov     [rbx], rax
0x1800154b6  cmp     esi, 1
0x1800154b9  jnz     short loc_1800154F2
0x1800154bb  call    ?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ; CallerIdentity::_EnsureRuntimeBrokerPID(void)
0x1800154c0  mov     rcx, [rbx]; Process
0x1800154c3  call    cs:__imp_GetProcessId
0x1800154c9  cmp     eax, cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x1800154cf  jnz     short loc_1800154F2
0x1800154d1  mov     rcx, [rbx]; hObject
0x1800154d4  call    cs:__imp_CloseHandle
0x1800154da  lea     rcx, [rsp+28h+ppInterface]
0x1800154df  mov     qword ptr [rbx], 0
0x1800154e6  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x1800154eb  mov     eax, 80004005h
0x1800154f0  jmp     short loc_180015525
0x1800154f2  lea     rcx, [rsp+28h+ppInterface]
0x1800154f7  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x1800154fc  xor     eax, eax
0x1800154fe  jmp     short loc_180015525
0x180015500  mov     rcx, [rsp+28h]; this
0x180015505  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18001550c  mov     r9d, edi; char *
0x18001550f  mov     edx, 58h ; 'X'; void *
0x180015514  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015519  lea     rcx, [rsp+28h+ppInterface]
0x18001551e  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x180015523  mov     eax, edi
0x180015525  mov     rbx, [rsp+28h+arg_0]
0x18001552a  mov     rsi, [rsp+28h+arg_8]
0x18001552f  add     rsp, 20h
0x180015533  pop     rdi
0x180015534  retn
```
