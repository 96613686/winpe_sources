# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x1800164d4`
- end: `0x1800165bd`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `233`
- prototype: `__int64 __fastcall(__int64, __int64, HANDLE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015dc0`

## callees

- `0x18000ed10`
- `0x1800164d4`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800164fd`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800164fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001654c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001654c`

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
0x1800164d4  mov     [rsp+arg_0], rbx
0x1800164d9  push    rdi; int
0x1800164da  sub     rsp, 20h
0x1800164de  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x1800164e3  mov     qword ptr [r8], 0
0x1800164ea  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x1800164f1  mov     [rsp+28h+ppInterface], 0
0x1800164fa  mov     rdi, r8
0x1800164fd  call    cs:__imp_CoGetCallContext
0x180016503  mov     ebx, eax
0x180016505  test    eax, eax
0x180016507  js      short loc_180016544
0x180016509  mov     rcx, [rsp+28h+ppInterface]
0x18001650e  mov     r8, rdi
0x180016511  mov     edx, 1000h
0x180016516  mov     rax, [rcx]
0x180016519  mov     rax, [rax+18h]
0x18001651d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016522  mov     ebx, eax
0x180016524  test    eax, eax
0x180016526  jns     short loc_180016555
0x180016528  mov     rcx, [rsp+28h+ppInterface]
0x18001652d  test    rcx, rcx
0x180016530  jz      short loc_1800165B0
0x180016532  mov     [rsp+28h+ppInterface], 0
0x18001653b  mov     rdx, [rcx]
0x18001653e  mov     rax, [rdx+10h]
0x180016542  jmp     short loc_1800165AB
0x180016544  cmp     ebx, 80010117h
0x18001654a  jnz     short loc_180016578
0x18001654c  call    cs:__imp_GetCurrentProcess
0x180016552  mov     [rdi], rax
0x180016555  mov     rcx, [rsp+28h+ppInterface]
0x18001655a  test    rcx, rcx
0x18001655d  jz      short loc_180016574
0x18001655f  mov     [rsp+28h+ppInterface], 0
0x180016568  mov     rax, [rcx]
0x18001656b  mov     rax, [rax+10h]
0x18001656f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016574  xor     eax, eax
0x180016576  jmp     short loc_1800165B2
0x180016578  mov     rcx, [rsp+28h]; this
0x18001657d  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180016584  mov     r9d, ebx; char *
0x180016587  mov     edx, 58h ; 'X'; void *
0x18001658c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016591  mov     rcx, [rsp+28h+ppInterface]
0x180016596  test    rcx, rcx
0x180016599  jz      short loc_1800165B0
0x18001659b  mov     [rsp+28h+ppInterface], 0
0x1800165a4  mov     rax, [rcx]
0x1800165a7  mov     rax, [rax+10h]
0x1800165ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165b0  mov     eax, ebx
0x1800165b2  mov     rbx, [rsp+28h+arg_0]
0x1800165b7  add     rsp, 20h
0x1800165bb  pop     rdi
0x1800165bc  retn
```
