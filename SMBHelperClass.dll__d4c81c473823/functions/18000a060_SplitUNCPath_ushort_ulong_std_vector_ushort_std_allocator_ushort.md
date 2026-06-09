# SplitUNCPath(ushort *,ulong,std::vector<ushort *,std::allocator<ushort *>> &)

- ea: `0x18000a060`
- end: `0x18000a256`
- name: `?SplitUNCPath@@YA?AW4SMBHC_ResultCode@@PEAGKAEAV?$vector@PEAGV?$allocator@PEAG@std@@@std@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(_WORD *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005a20`

## callees

- `0x18000a060`
- `0x18000a450`
- `0x18000eddc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a1cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a1cc`

## pseudocode

```c
__int64 __fastcall SplitUNCPath(_WORD *a1, unsigned int a2, __int64 a3)
{
  _WORD *v4; // rbx
  __int64 v5; // rax
  _WORD *v6; // rdx
  __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdi
  unsigned int v10; // esi
  __int64 v11; // rbp
  __int64 v12; // r15
  __int64 v13; // r14
  _WORD *v14; // rax
  _WORD *v15; // rdx
  _WORD *v16; // rcx
  _WORD *v17; // rcx
  _WORD *TestMemory; // rax
  _WORD *v19; // r8
  void *v21; // rcx
  unsigned __int64 v22; // rdx
  _WORD *v23; // rcx
  _WORD *v24; // [rsp+70h] [rbp+8h] BYREF

  v4 = a1;
  if ( !a1 || a2 < 3 || *a1 != 92 || a1[1] != 92 || a2 > 0x7FFFFFFF )
    return 3;
  v5 = a2;
  v6 = a1;
  v7 = (unsigned int)v5;
  while ( *v6 )
  {
    ++v6;
    if ( !--v5 )
    {
      v8 = 0;
      goto LABEL_10;
    }
  }
  v8 = v7 - v5;
LABEL_10:
  if ( !v5 )
    return 3;
  v9 = v8 - 1;
  v10 = 2;
  if ( v4[v8 - 1] != 92 )
    v9 = v8;
  if ( v9 <= 2 )
  {
LABEL_28:
    TestMemory = AllocateTestMemory(2 * v9 + 2);
    v24 = TestMemory;
    v19 = TestMemory;
    if ( !TestMemory )
      return 5;
    v22 = v9 + 1;
    if ( v9 != -1 )
    {
      if ( v22 <= 0x7FFFFFFF && v9 <= 0x7FFFFFFE )
      {
        do
        {
          if ( !v9 )
            break;
          if ( !*v4 )
            break;
          *TestMemory++ = *v4++;
          --v9;
          --v22;
        }
        while ( v22 );
        v23 = TestMemory - 1;
        if ( v22 )
          v23 = TestMemory;
        *v23 = 0;
        if ( v22 )
        {
          std::vector<unsigned short *>::push_back(a3, &v24);
          return 0;
        }
      }
      else
      {
        *TestMemory = 0;
      }
    }
    v21 = v19;
    goto LABEL_33;
  }
  while ( 1 )
  {
    v11 = v10;
    v12 = v10 + 1;
    if ( v4[v10] != 92 )
      goto LABEL_27;
    v13 = (unsigned int)v12;
    v14 = AllocateTestMemory(2 * v12);
    v24 = v14;
    v15 = v14;
    if ( !v14 )
      return 5;
    if ( v10 == -1 )
      goto LABEL_32;
    if ( (unsigned int)v12 > 0x7FFFFFFFuLL || v10 > 0x7FFFFFFE )
      break;
    v16 = v4;
    do
    {
      if ( !v11 )
        break;
      if ( !*v16 )
        break;
      *v14++ = *v16++;
      --v11;
      --v13;
    }
    while ( v13 );
    v17 = v14 - 1;
    if ( v13 )
      v17 = v14;
    *v17 = 0;
    if ( !v13 )
      goto LABEL_32;
    std::vector<unsigned short *>::push_back(a3, &v24);
LABEL_27:
    ++v10;
    if ( (unsigned int)v12 >= v9 )
      goto LABEL_28;
  }
  *v14 = 0;
LABEL_32:
  v21 = v15;
LABEL_33:
  CoTaskMemFree(v21);
  return 1;
}

```

## disassembly

```asm
0x18000a060  push    rbx
0x18000a062  push    rbp
0x18000a063  push    rsi
0x18000a064  push    rdi
0x18000a065  push    r12
0x18000a067  push    r13
0x18000a069  push    r14
0x18000a06b  push    r15
0x18000a06d  sub     rsp, 28h
0x18000a071  xor     r13d, r13d
0x18000a074  mov     r12, r8
0x18000a077  mov     rbx, rcx
0x18000a07a  test    rcx, rcx
0x18000a07d  jz      loc_18000A240
0x18000a083  cmp     edx, 3
0x18000a086  jb      loc_18000A240
0x18000a08c  cmp     word ptr [rcx], 5Ch ; '\'
0x18000a090  jnz     loc_18000A240
0x18000a096  cmp     word ptr [rcx+2], 5Ch ; '\'
0x18000a09b  jnz     loc_18000A240
0x18000a0a1  cmp     edx, 7FFFFFFFh
0x18000a0a7  ja      loc_18000A240
0x18000a0ad  mov     eax, edx
0x18000a0af  mov     rdx, rcx
0x18000a0b2  mov     ecx, eax
0x18000a0b4  test    rax, rax
0x18000a0b7  jz      short loc_18000A0CD
0x18000a0b9  cmp     [rdx], r13w
0x18000a0bd  jz      loc_18000A1BD
0x18000a0c3  add     rdx, 2
0x18000a0c7  sub     rax, 1
0x18000a0cb  jnz     short loc_18000A0B9
0x18000a0cd  mov     rcx, r13
0x18000a0d0  test    rax, rax
0x18000a0d3  jz      loc_18000A240
0x18000a0d9  cmp     word ptr [rbx+rcx*2-2], 5Ch ; '\'
0x18000a0df  lea     rdi, [rcx-1]
0x18000a0e3  mov     esi, 2
0x18000a0e8  cmovnz  rdi, rcx
0x18000a0ec  cmp     rdi, rsi
0x18000a0ef  jbe     loc_18000A199
0x18000a0f5  mov     ebp, esi
0x18000a0f7  lea     r15d, [rsi+1]
0x18000a0fb  cmp     word ptr [rbx+rbp*2], 5Ch ; '\'
0x18000a100  jnz     loc_18000A18A
0x18000a106  lea     rcx, [r15+r15]; unsigned __int64
0x18000a10a  mov     r14d, r15d
0x18000a10d  call    ?AllocateTestMemory@@YAPEAX_K@Z; AllocateTestMemory(unsigned __int64)
0x18000a112  mov     [rsp+68h+arg_0], rax
0x18000a117  mov     rdx, rax
0x18000a11a  test    rax, rax
0x18000a11d  jz      loc_18000A1B3
0x18000a123  test    r15d, r15d
0x18000a126  jz      loc_18000A1C9
0x18000a12c  cmp     r14, 7FFFFFFFh
0x18000a133  ja      loc_18000A1C5
0x18000a139  cmp     esi, 7FFFFFFEh
0x18000a13f  ja      loc_18000A1C5
0x18000a145  mov     rcx, rbx
0x18000a148  test    rbp, rbp
0x18000a14b  jz      short loc_18000A16C
0x18000a14d  movzx   r8d, word ptr [rcx]
0x18000a151  test    r8w, r8w
0x18000a155  jz      short loc_18000A16C
0x18000a157  mov     [rax], r8w
0x18000a15b  add     rcx, 2
0x18000a15f  add     rax, 2
0x18000a163  dec     rbp
0x18000a166  sub     r14, 1
0x18000a16a  jnz     short loc_18000A148
0x18000a16c  test    r14, r14
0x18000a16f  lea     rcx, [rax-2]
0x18000a173  cmovnz  rcx, rax
0x18000a177  mov     [rcx], r13w
0x18000a17b  jz      short loc_18000A1C9
0x18000a17d  lea     rdx, [rsp+68h+arg_0]
0x18000a182  mov     rcx, r12
0x18000a185  call    ?push_back@?$vector@PEAGV?$allocator@PEAG@std@@@std@@QEAAXAEBQEAG@Z; std::vector<ushort *>::push_back(ushort * const &)
0x18000a18a  mov     eax, r15d
0x18000a18d  mov     esi, r15d
0x18000a190  cmp     rax, rdi
0x18000a193  jb      loc_18000A0F5
0x18000a199  lea     rcx, ds:2[rdi*2]; unsigned __int64
0x18000a1a1  call    ?AllocateTestMemory@@YAPEAX_K@Z; AllocateTestMemory(unsigned __int64)
0x18000a1a6  mov     [rsp+68h+arg_0], rax
0x18000a1ab  mov     r8, rax
0x18000a1ae  test    rax, rax
0x18000a1b1  jnz     short loc_18000A1D9
0x18000a1b3  mov     eax, 5
0x18000a1b8  jmp     loc_18000A245
0x18000a1bd  sub     rcx, rax
0x18000a1c0  jmp     loc_18000A0D0
0x18000a1c5  mov     [rax], r13w
0x18000a1c9  mov     rcx, rdx; pv
0x18000a1cc  call    cs:__imp_CoTaskMemFree
0x18000a1d2  mov     eax, 1
0x18000a1d7  jmp     short loc_18000A245
0x18000a1d9  lea     rdx, [rdi+1]
0x18000a1dd  test    rdx, rdx
0x18000a1e0  jz      short loc_18000A1F8
0x18000a1e2  cmp     rdx, 7FFFFFFFh
0x18000a1e9  ja      short loc_18000A1F4
0x18000a1eb  cmp     rdi, 7FFFFFFEh
0x18000a1f2  jbe     short loc_18000A1FD
0x18000a1f4  mov     [rax], r13w
0x18000a1f8  mov     rcx, r8
0x18000a1fb  jmp     short loc_18000A1CC
0x18000a1fd  test    rdi, rdi
0x18000a200  jz      short loc_18000A21E
0x18000a202  movzx   ecx, word ptr [rbx]
0x18000a205  test    cx, cx
0x18000a208  jz      short loc_18000A21E
0x18000a20a  mov     [rax], cx
0x18000a20d  add     rbx, 2
0x18000a211  add     rax, 2
0x18000a215  dec     rdi
0x18000a218  sub     rdx, 1
0x18000a21c  jnz     short loc_18000A1FD
0x18000a21e  test    rdx, rdx
0x18000a221  lea     rcx, [rax-2]
0x18000a225  cmovnz  rcx, rax
0x18000a229  mov     [rcx], r13w
0x18000a22d  jz      short loc_18000A1F8
0x18000a22f  lea     rdx, [rsp+68h+arg_0]
0x18000a234  mov     rcx, r12
0x18000a237  call    ?push_back@?$vector@PEAGV?$allocator@PEAG@std@@@std@@QEAAXAEBQEAG@Z; std::vector<ushort *>::push_back(ushort * const &)
0x18000a23c  xor     eax, eax
0x18000a23e  jmp     short loc_18000A245
0x18000a240  mov     eax, 3
0x18000a245  add     rsp, 28h
0x18000a249  pop     r15
0x18000a24b  pop     r14
0x18000a24d  pop     r13
0x18000a24f  pop     r12
0x18000a251  pop     rdi
0x18000a252  pop     rsi
0x18000a253  pop     rbp
0x18000a254  pop     rbx
0x18000a255  retn
```
