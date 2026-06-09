# AssessmentCore::SetCallerName(ushort const *)

- ea: `0x18000a070`
- end: `0x18000a181`
- name: `?SetCallerName@AssessmentCore@@UEAAJPEBG@Z`
- size: `273`
- prototype: `__int64 __fastcall(AssessmentCore *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a070`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a0f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a0f4`

## pseudocode

```c
__int64 __fastcall AssessmentCore::SetCallerName(AssessmentCore *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // r14
  const unsigned __int16 *v4; // rax
  __int64 v5; // r8
  unsigned int v6; // edi
  unsigned int v7; // edx
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // rsi
  _WORD *v10; // rax
  _WORD *v11; // rdx
  __int64 v12; // rax
  _WORD *v13; // rcx

  v2 = a2;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v4 = a2;
  v5 = 0x7FFFFFFF;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  v6 = -2147024809;
  v7 = v5 == 0 ? 0x80070057 : 0;
  v8 = (0x7FFFFFFF - v5) & -(__int64)(v5 != 0);
  if ( !v5 )
    return v7;
  v9 = -1;
  if ( v8 + 1 >= v8 )
    v9 = v8 + 1;
  v10 = CoTaskMemAlloc(2 * v9);
  *((_QWORD *)this + 24) = v10;
  v11 = v10;
  if ( v8 + 1 < v8 )
  {
    return v8 + 1 < v8 ? 0x80070216 : 0;
  }
  else if ( v9 )
  {
    if ( v9 > 0x7FFFFFFF )
    {
      *v10 = 0;
    }
    else
    {
      v12 = 2147483646;
      do
      {
        if ( !v12 )
          break;
        if ( !*v2 )
          break;
        *v11++ = *v2++;
        --v12;
        --v9;
      }
      while ( v9 );
      v13 = v11 - 1;
      if ( v9 )
        v13 = v11;
      v6 = v9 == 0 ? 0x8007007A : 0;
      *v13 = 0;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000a070  push    rbx
0x18000a072  push    rbp
0x18000a073  push    rsi
0x18000a074  push    rdi
0x18000a075  push    r12
0x18000a077  push    r13
0x18000a079  push    r14
0x18000a07b  push    r15
0x18000a07d  sub     rsp, 28h
0x18000a081  xor     r12d, r12d
0x18000a084  mov     r14, rdx
0x18000a087  mov     r13, rcx
0x18000a08a  test    rdx, rdx
0x18000a08d  jz      loc_18000A167
0x18000a093  mov     ecx, 7FFFFFFFh
0x18000a098  mov     rax, rdx
0x18000a09b  mov     r8d, ecx
0x18000a09e  cmp     [rax], r12w
0x18000a0a2  jz      short loc_18000A0AE
0x18000a0a4  add     rax, 2
0x18000a0a8  sub     r8, 1
0x18000a0ac  jnz     short loc_18000A09E
0x18000a0ae  mov     rax, r8
0x18000a0b1  mov     edi, 80070057h
0x18000a0b6  neg     rax
0x18000a0b9  mov     rax, r8
0x18000a0bc  sbb     edx, edx
0x18000a0be  sub     rcx, r8
0x18000a0c1  not     edx
0x18000a0c3  and     edx, edi
0x18000a0c5  neg     rax
0x18000a0c8  sbb     rbp, rbp
0x18000a0cb  and     rbp, rcx
0x18000a0ce  test    r8, r8
0x18000a0d1  jz      loc_18000A16C
0x18000a0d7  lea     rbx, [rbp+1]
0x18000a0db  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a0df  cmp     rbx, rbp
0x18000a0e2  cmovnb  rsi, rbx
0x18000a0e6  sbb     r15d, r15d
0x18000a0e9  and     r15d, 80070216h
0x18000a0f0  lea     rcx, [rsi+rsi]; cb
0x18000a0f4  call    cs:__imp_CoTaskMemAlloc
0x18000a0fa  mov     [r13+0C0h], rax
0x18000a101  mov     rdx, rax
0x18000a104  cmp     rbx, rbp
0x18000a107  jb      short loc_18000A162
0x18000a109  test    rsi, rsi
0x18000a10c  jz      short loc_18000A16E
0x18000a10e  cmp     rsi, 7FFFFFFFh
0x18000a115  ja      short loc_18000A15C
0x18000a117  mov     eax, 7FFFFFFEh
0x18000a11c  test    rax, rax
0x18000a11f  jz      short loc_18000A13E
0x18000a121  movzx   ecx, word ptr [r14]
0x18000a125  test    cx, cx
0x18000a128  jz      short loc_18000A13E
0x18000a12a  mov     [rdx], cx
0x18000a12d  add     r14, 2
0x18000a131  add     rdx, 2
0x18000a135  dec     rax
0x18000a138  sub     rsi, 1
0x18000a13c  jnz     short loc_18000A11C
0x18000a13e  test    rsi, rsi
0x18000a141  lea     rcx, [rdx-2]
0x18000a145  cmovnz  rcx, rdx
0x18000a149  neg     rsi
0x18000a14c  sbb     edi, edi
0x18000a14e  not     edi
0x18000a150  and     edi, 8007007Ah
0x18000a156  mov     [rcx], r12w
0x18000a15a  jmp     short loc_18000A16E
0x18000a15c  mov     [rax], r12w
0x18000a160  jmp     short loc_18000A16E
0x18000a162  mov     edi, r15d
0x18000a165  jmp     short loc_18000A16E
0x18000a167  mov     edx, 80070057h
0x18000a16c  mov     edi, edx
0x18000a16e  mov     eax, edi
0x18000a170  add     rsp, 28h
0x18000a174  pop     r15
0x18000a176  pop     r14
0x18000a178  pop     r13
0x18000a17a  pop     r12
0x18000a17c  pop     rdi
0x18000a17d  pop     rsi
0x18000a17e  pop     rbp
0x18000a17f  pop     rbx
0x18000a180  retn
```
