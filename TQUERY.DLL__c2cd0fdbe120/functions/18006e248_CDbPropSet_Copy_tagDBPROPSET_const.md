# CDbPropSet::Copy(tagDBPROPSET const &)

- ea: `0x18006e248`
- end: `0x18006e398`
- name: `?Copy@CDbPropSet@@QEAAHAEBUtagDBPROPSET@@@Z`
- size: `336`
- prototype: `__int64 __fastcall(CDbPropSet *__hidden this, const struct tagDBPROPSET *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18006c020`
- `0x18006d3a0`
- `0x180182364`

## callees

- `0x18006e248`
- `0x18006e44c`
- `0x18006e4c0`
- `0x180189cce`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e339`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b95f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b9634`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e339`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b95f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802b9634`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006e2c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006e2c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDbPropSet::Copy(CDbPropSet *this, const struct tagDBPROPSET *a2)
{
  ULONG *v4; // rdi
  ULONG cProperties; // ebp
  char *v6; // rax
  char *v7; // rsi
  char *v8; // r14
  unsigned int v9; // edi
  unsigned int v10; // r15d
  __int64 v11; // rbp
  unsigned int v12; // eax
  __int64 v13; // rbp
  __int64 v15; // rsi
  CDbProp *v16; // rcx

  v4 = (ULONG *)((char *)this + 8);
  if ( *(_QWORD *)this )
  {
    if ( *v4 )
    {
      v15 = 0;
      if ( !*v4 )
      {
        v16 = 0;
        goto LABEL_19;
      }
      do
      {
        v16 = (CDbProp *)(*(_QWORD *)this + 72 * v15);
LABEL_19:
        CDbProp::Cleanup(v16);
        v15 = (unsigned int)(v15 + 1);
      }
      while ( (unsigned int)v15 < *v4 );
    }
    CoTaskMemFree(*(LPVOID *)this);
    *(_QWORD *)this = 0;
  }
  *(GUID *)((char *)this + 12) = a2->guidPropertySet;
  cProperties = a2->cProperties;
  *v4 = cProperties;
  if ( !cProperties )
    return 1;
  if ( is_mul_ok(0x48u, cProperties) && (v6 = (char *)CoTaskMemAlloc(72LL * cProperties), (v7 = v6) != 0) )
  {
    memset_0(v6, 0, 72LL * cProperties);
    v8 = v7;
    v9 = 1;
    v10 = 0;
    v11 = 0;
    do
    {
      if ( (unsigned int)v11 >= *((_DWORD *)this + 2) )
      {
        v7 = 0;
        goto LABEL_25;
      }
      v9 = CDbProp::Copy((CDbProp *)&v7[72 * v11], &a2->rgProperties[v11]);
      v11 = (unsigned int)(v11 + 1);
      v12 = v10 + 1;
      if ( !v9 )
        v12 = v10;
      v10 = v12;
    }
    while ( v9 );
    v13 = 0;
    if ( v12 )
    {
      do
      {
        CDbProp::Cleanup((CDbProp *)&v7[72 * v13]);
        v13 = (unsigned int)(v13 + 1);
      }
      while ( (unsigned int)v13 < v10 );
    }
    *((_DWORD *)this + 2) = 0;
    v8 = 0;
LABEL_25:
    *(_QWORD *)this = v8;
    CoTaskMemFree(v7);
    return v9;
  }
  else
  {
    CoTaskMemFree(0);
    return 0;
  }
}

```

## disassembly

```asm
0x18006e248  mov     [rsp+arg_8], rbx
0x18006e24d  mov     [rsp+arg_10], rbp
0x18006e252  push    rsi
0x18006e253  push    rdi
0x18006e254  push    r12
0x18006e256  push    r14
0x18006e258  push    r15
0x18006e25a  sub     rsp, 30h
0x18006e25e  mov     r12, rdx
0x18006e261  mov     rbx, rcx
0x18006e264  lea     rdi, [rcx+8]
0x18006e268  mov     r15d, 1
0x18006e26e  cmp     qword ptr [rcx], 0
0x18006e272  jnz     loc_18006E370
0x18006e278  movups  xmm0, xmmword ptr [r12+0Ch]
0x18006e27e  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x18006e283  mov     ebp, [r12+8]
0x18006e288  mov     [rdi], ebp
0x18006e28a  test    ebp, ebp
0x18006e28c  jz      loc_18006E358
0x18006e292  mov     [rsp+58h+var_38], 0
0x18006e29b  mov     [rsp+58h+var_30], 0
0x18006e2a3  mov     [rsp+58h+arg_0], 0
0x18006e2ac  mov     eax, ebp
0x18006e2ae  mov     ecx, 48h ; 'H'
0x18006e2b3  mul     rcx
0x18006e2b6  mov     rdi, rax
0x18006e2b9  test    rdx, rdx
0x18006e2bc  jnz     short loc_18006E337
0x18006e2be  mov     rcx, rax; cb
0x18006e2c1  call    cs:__imp_CoTaskMemAlloc
0x18006e2c7  mov     rsi, rax
0x18006e2ca  mov     [rsp+58h+var_38], rax
0x18006e2cf  test    rax, rax
0x18006e2d2  jz      short loc_18006E337
0x18006e2d4  mov     r8, rdi; Size
0x18006e2d7  xor     edx, edx; Val
0x18006e2d9  mov     rcx, rax; void *
0x18006e2dc  call    memset_0
0x18006e2e1  mov     [rsp+58h+var_30], ebp
0x18006e2e5  mov     r14, rsi
0x18006e2e8  mov     edi, r15d
0x18006e2eb  xor     r15d, r15d
0x18006e2ee  xor     ebp, ebp
0x18006e2f0  cmp     ebp, [rbx+8]
0x18006e2f3  jnb     loc_18006E391
0x18006e2f9  lea     rcx, ds:0[rbp*8]
0x18006e301  add     rcx, rbp
0x18006e304  mov     rax, [r12]
0x18006e308  lea     rdx, [rax+rcx*8]; struct tagDBPROP *
0x18006e30c  lea     rcx, [rsi+rcx*8]; this
0x18006e310  call    ?Copy@CDbProp@@QEAAHAEBUtagDBPROP@@@Z; CDbProp::Copy(tagDBPROP const &)
0x18006e315  mov     edi, eax
0x18006e317  inc     ebp
0x18006e319  lea     eax, [r15+1]
0x18006e31d  test    edi, edi
0x18006e31f  cmovz   eax, r15d
0x18006e323  mov     r15d, eax
0x18006e326  jnz     short loc_18006E2F0
0x18006e328  xor     ebp, ebp
0x18006e32a  test    eax, eax
0x18006e32c  jnz     loc_1802B9609
0x18006e332  jmp     loc_1802B9624
0x18006e337  xor     ecx, ecx; pv
0x18006e339  call    cs:__imp_CoTaskMemFree
0x18006e33f  xor     eax, eax
0x18006e341  mov     rbx, [rsp+58h+arg_8]
0x18006e346  mov     rbp, [rsp+58h+arg_10]
0x18006e34b  add     rsp, 30h
0x18006e34f  pop     r15
0x18006e351  pop     r14
0x18006e353  pop     r12
0x18006e355  pop     rdi
0x18006e356  pop     rsi
0x18006e357  retn
0x18006e358  mov     eax, r15d
0x18006e35b  jmp     short loc_18006E341
0x18006e35d  xor     esi, esi
0x18006e35f  cmp     esi, eax
0x18006e361  jnb     short loc_18006E37C
0x18006e363  lea     rcx, [rsi+rsi*8]
0x18006e367  mov     rax, [rbx]
0x18006e36a  lea     rcx, [rax+rcx*8]
0x18006e36e  jmp     short loc_18006E37E
0x18006e370  mov     eax, [rdi]
0x18006e372  test    eax, eax
0x18006e374  jz      loc_1802B95F4
0x18006e37a  jmp     short loc_18006E35D
0x18006e37c  xor     ecx, ecx; this
0x18006e37e  call    ?Cleanup@CDbProp@@QEAAXXZ; CDbProp::Cleanup(void)
0x18006e383  add     esi, r15d
0x18006e386  mov     eax, [rdi]
0x18006e388  cmp     esi, eax
0x18006e38a  jb      short loc_18006E363
0x18006e38c  jmp     loc_1802B95F4
0x18006e391  xor     esi, esi
0x18006e393  jmp     loc_1802B962E
0x1802b95f4  mov     rcx, [rbx]; pv
0x1802b95f7  call    cs:__imp_CoTaskMemFree
0x1802b95fd  mov     qword ptr [rbx], 0
0x1802b9604  jmp     loc_18006E278
0x1802b9609  lea     rcx, ds:0[rbp*8]
0x1802b9611  add     rcx, rbp
0x1802b9614  lea     rcx, [rsi+rcx*8]; this
0x1802b9618  call    ?Cleanup@CDbProp@@QEAAXXZ; CDbProp::Cleanup(void)
0x1802b961d  inc     ebp
0x1802b961f  cmp     ebp, r15d
0x1802b9622  jb      short loc_1802B9609
0x1802b9624  mov     dword ptr [rbx+8], 0
0x1802b962b  xor     r14d, r14d
0x1802b962e  mov     [rbx], r14
0x1802b9631  mov     rcx, rsi; pv
0x1802b9634  call    cs:__imp_CoTaskMemFree
0x1802b963a  mov     eax, edi
0x1802b963c  jmp     loc_18006E341
```
