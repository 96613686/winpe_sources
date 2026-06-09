# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x18000fd74`
- end: `0x18000fe5d`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `233`
- prototype: `__int64 __fastcall(__int64, __int64, HANDLE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fba0`

## callees

- `0x180005524`
- `0x18000fd74`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fdec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fdec`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18000fd9d`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18000fd9d`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCallingProcessHandle(__int64 a1, __int64 a2, HANDLE *a3)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  void *v6; // rcx
  void (*v7)(void); // rax
  void *v8; // rcx
  void *v10; // rcx
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *ppInterface; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  ppInterface = 0;
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
        v11);
      v10 = ppInterface;
      if ( ppInterface )
      {
        ppInterface = 0;
        v7 = *(void (**)(void))(*(_QWORD *)v10 + 16LL);
        goto LABEL_12;
      }
      return v5;
    }
    *a3 = GetCurrentProcess();
  }
  else
  {
    v5 = (*(__int64 (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)ppInterface + 24LL))(ppInterface, 4096, a3);
    if ( (v5 & 0x80000000) != 0 )
    {
      v6 = ppInterface;
      if ( ppInterface )
      {
        ppInterface = 0;
        v7 = *(void (**)(void))(*(_QWORD *)v6 + 16LL);
LABEL_12:
        v7();
        return v5;
      }
      return v5;
    }
  }
  v8 = ppInterface;
  if ( ppInterface )
  {
    ppInterface = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18000fd74  mov     [rsp+arg_0], rbx
0x18000fd79  push    rdi; int
0x18000fd7a  sub     rsp, 20h
0x18000fd7e  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x18000fd83  mov     qword ptr [r8], 0
0x18000fd8a  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x18000fd91  mov     [rsp+28h+ppInterface], 0
0x18000fd9a  mov     rdi, r8
0x18000fd9d  call    cs:__imp_CoGetCallContext
0x18000fda3  mov     ebx, eax
0x18000fda5  test    eax, eax
0x18000fda7  js      short loc_18000FDE4
0x18000fda9  mov     rcx, [rsp+28h+ppInterface]
0x18000fdae  mov     r8, rdi
0x18000fdb1  mov     edx, 1000h
0x18000fdb6  mov     rax, [rcx]
0x18000fdb9  mov     rax, [rax+18h]
0x18000fdbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdc2  mov     ebx, eax
0x18000fdc4  test    eax, eax
0x18000fdc6  jns     short loc_18000FDF5
0x18000fdc8  mov     rcx, [rsp+28h+ppInterface]
0x18000fdcd  test    rcx, rcx
0x18000fdd0  jz      short loc_18000FE50
0x18000fdd2  mov     [rsp+28h+ppInterface], 0
0x18000fddb  mov     rdx, [rcx]
0x18000fdde  mov     rax, [rdx+10h]
0x18000fde2  jmp     short loc_18000FE4B
0x18000fde4  cmp     ebx, 80010117h
0x18000fdea  jnz     short loc_18000FE18
0x18000fdec  call    cs:__imp_GetCurrentProcess
0x18000fdf2  mov     [rdi], rax
0x18000fdf5  mov     rcx, [rsp+28h+ppInterface]
0x18000fdfa  test    rcx, rcx
0x18000fdfd  jz      short loc_18000FE14
0x18000fdff  mov     [rsp+28h+ppInterface], 0
0x18000fe08  mov     rax, [rcx]
0x18000fe0b  mov     rax, [rax+10h]
0x18000fe0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe14  xor     eax, eax
0x18000fe16  jmp     short loc_18000FE52
0x18000fe18  mov     rcx, [rsp+28h]; this
0x18000fe1d  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18000fe24  mov     r9d, ebx; char *
0x18000fe27  mov     edx, 58h ; 'X'; void *
0x18000fe2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fe31  mov     rcx, [rsp+28h+ppInterface]
0x18000fe36  test    rcx, rcx
0x18000fe39  jz      short loc_18000FE50
0x18000fe3b  mov     [rsp+28h+ppInterface], 0
0x18000fe44  mov     rax, [rcx]
0x18000fe47  mov     rax, [rax+10h]
0x18000fe4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe50  mov     eax, ebx
0x18000fe52  mov     rbx, [rsp+28h+arg_0]
0x18000fe57  add     rsp, 20h
0x18000fe5b  pop     rdi
0x18000fe5c  retn
```
