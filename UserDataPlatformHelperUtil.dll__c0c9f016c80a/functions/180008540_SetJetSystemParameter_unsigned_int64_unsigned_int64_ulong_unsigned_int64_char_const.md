# SetJetSystemParameter(unsigned __int64 *,unsigned __int64,ulong,unsigned __int64,char const *)

- ea: `0x180008540`
- end: `0x1800085cd`
- name: `?SetJetSystemParameter@@YAJPEA_K_KK1PEBD@Z`
- size: `141`
- prototype: `__int64 __fastcall(unsigned __int64 *, __int64, unsigned int, JET_API_PTR)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800085e0`

## callees

- `0x180008540`
- `0x18000a190`

## import_xrefs

- `ESENT!JetGetSystemParameterA` at `0x18000859f`
- `ESENT!JetGetSystemParameterA` at `0x18000859f`
- `ESENT!JetSetSystemParameterA` at `0x18000856b`
- `ESENT!JetSetSystemParameterA` at `0x18000856b`

## pseudocode

```c
__int64 __fastcall SetJetSystemParameter(unsigned __int64 *a1, __int64 a2, unsigned int a3, JET_API_PTR a4)
{
  JET_ERR v5; // eax
  JET_API_PTR plParam[2]; // [rsp+30h] [rbp-138h] BYREF
  char szParam[272]; // [rsp+40h] [rbp-128h] BYREF

  v5 = JetSetSystemParameterA(0, 0, a3, a4, 0);
  if ( v5 == -1030 )
  {
    plParam[0] = 0;
    JetGetSystemParameterA(0, 0, a3, plParam, szParam, 0x104u);
    return 0;
  }
  if ( v5 >= 0 )
    return 0;
  return -v5 | 0x80C80000;
}

```

## disassembly

```asm
0x180008540  push    rbx
0x180008542  sub     rsp, 160h
0x180008549  mov     rax, cs:__security_cookie
0x180008550  xor     rax, rsp
0x180008553  mov     [rsp+168h+var_18], rax
0x18000855b  xor     edx, edx; sesid
0x18000855d  mov     [rsp+168h+szParam], 0; szParam
0x180008566  xor     ecx, ecx; pinstance
0x180008568  mov     ebx, r8d
0x18000856b  call    cs:__imp_JetSetSystemParameterA
0x180008571  cmp     eax, 0FFFFFBFAh
0x180008576  jnz     short loc_1800085C0
0x180008578  lea     rax, [rsp+168h+var_128]
0x18000857d  mov     [rsp+168h+cbMax], 104h; cbMax
0x180008585  lea     r9, [rsp+168h+plParam]; plParam
0x18000858a  mov     [rsp+168h+szParam], rax; szParam
0x18000858f  mov     r8d, ebx; paramid
0x180008592  mov     [rsp+168h+plParam], 0
0x18000859b  xor     edx, edx; sesid
0x18000859d  xor     ecx, ecx; instance
0x18000859f  call    cs:__imp_JetGetSystemParameterA
0x1800085a5  xor     eax, eax
0x1800085a7  mov     rcx, [rsp+168h+var_18]
0x1800085af  xor     rcx, rsp; StackCookie
0x1800085b2  call    __security_check_cookie
0x1800085b7  add     rsp, 160h
0x1800085be  pop     rbx
0x1800085bf  retn
0x1800085c0  test    eax, eax
0x1800085c2  jns     short loc_1800085A5
0x1800085c4  neg     eax
0x1800085c6  or      eax, 80C80000h
0x1800085cb  jmp     short loc_1800085A7
```
