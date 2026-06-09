# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x14001d20c`
- end: `0x14001d2c3`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(unsigned int, __int64, HANDLE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009cfc`
- `0x14001d1ec`

## callees

- `0x14000e920`
- `0x1400136fc`
- `0x14001d20c`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x14001d245`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x14001d245`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001d277`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001d277`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCallingProcessHandle(unsigned int a1, __int64 a2, HANDLE *a3)
{
  HRESULT v5; // eax
  int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *ppInterface; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  ppInterface = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInterface);
  v5 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(void *, _QWORD, HANDLE *))(*(_QWORD *)ppInterface + 24LL))(ppInterface, a1, a3);
    if ( v6 < 0 )
      goto LABEL_8;
LABEL_6:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInterface);
    return 0;
  }
  if ( v5 == -2147417833 )
  {
    *a3 = GetCurrentProcess();
    goto LABEL_6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x58,
    (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
    (const char *)(unsigned int)v5,
    v8);
LABEL_8:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInterface);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001d20c  mov     rax, rsp
0x14001d20f  mov     [rax+8], rbx
0x14001d213  mov     [rax+10h], rsi
0x14001d217  push    rdi; int
0x14001d218  sub     rsp, 20h
0x14001d21c  mov     esi, ecx
0x14001d21e  mov     qword ptr [r8], 0
0x14001d225  lea     rcx, [rax+18h]
0x14001d229  mov     qword ptr [rax+18h], 0
0x14001d231  mov     rdi, r8
0x14001d234  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001d239  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x14001d23e  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x14001d245  call    cs:__imp_CoGetCallContext
0x14001d24b  mov     ebx, eax
0x14001d24d  test    eax, eax
0x14001d24f  js      short loc_14001D26F
0x14001d251  mov     rcx, [rsp+28h+ppInterface]
0x14001d256  mov     r8, rdi
0x14001d259  mov     edx, esi
0x14001d25b  mov     rax, [rcx]
0x14001d25e  mov     rax, [rax+18h]
0x14001d262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d267  mov     ebx, eax
0x14001d269  test    eax, eax
0x14001d26b  jns     short loc_14001D280
0x14001d26d  jmp     short loc_14001D2A7
0x14001d26f  cmp     ebx, 80010117h
0x14001d275  jnz     short loc_14001D28E
0x14001d277  call    cs:__imp_GetCurrentProcess
0x14001d27d  mov     [rdi], rax
0x14001d280  lea     rcx, [rsp+28h+ppInterface]
0x14001d285  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001d28a  xor     eax, eax
0x14001d28c  jmp     short loc_14001D2B3
0x14001d28e  mov     rcx, [rsp+28h]; this
0x14001d293  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x14001d29a  mov     r9d, ebx; char *
0x14001d29d  mov     edx, 58h ; 'X'; void *
0x14001d2a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d2a7  lea     rcx, [rsp+28h+ppInterface]
0x14001d2ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001d2b1  mov     eax, ebx
0x14001d2b3  mov     rbx, [rsp+28h+arg_0]
0x14001d2b8  mov     rsi, [rsp+28h+arg_8]
0x14001d2bd  add     rsp, 20h
0x14001d2c1  pop     rdi
0x14001d2c2  retn
```
