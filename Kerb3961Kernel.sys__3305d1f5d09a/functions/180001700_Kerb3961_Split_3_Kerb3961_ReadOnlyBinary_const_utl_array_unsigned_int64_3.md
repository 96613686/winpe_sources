# Kerb3961::Split<3>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,3>)

- ea: `0x180001700`
- end: `0x18000178c`
- name: `??$Split@$02@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$02@utl@@AEBUReadOnlyBinary@0@U?$array@_K$02@2@@Z`
- size: `140`
- prototype: `__int64 __fastcall(Kerb3961::ReadOnlyBinary *this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800028d4`
- `0x180002cc4`
- `0x180007338`

## callees

- `0x180001700`
- `0x1800018cc`
- `0x180003a38`

## pseudocode

```c
Kerb3961::ReadOnlyBinary *__fastcall Kerb3961::Split<3>(
        Kerb3961::ReadOnlyBinary *this,
        unsigned __int64 *a2,
        __int64 a3)
{
  Kerb3961::ReadOnlyBinary *v6; // rdi
  __int64 v7; // rsi
  unsigned __int64 v8; // r8
  unsigned __int64 i; // r9
  __int64 v10; // rcx
  const unsigned __int16 *v11; // rdx

  v6 = this;
  v7 = 3;
  do
  {
    Kerb3961::ReadOnlyBinary::ReadOnlyBinary(v6);
    v6 = (Kerb3961::ReadOnlyBinary *)((char *)v6 + 16);
    --v7;
  }
  while ( v7 );
  v8 = 0;
  for ( i = 0; i < 3; ++i )
  {
    v10 = 2 * i;
    v11 = (const unsigned __int16 *)(v8 + a2[1]);
    *((_QWORD *)this + v10) = *(_QWORD *)(a3 + 8 * i);
    *((_QWORD *)this + v10 + 1) = v11;
    v8 += *(_QWORD *)(a3 + 8 * i);
  }
  if ( v8 > *a2 )
    Kerb3961::ConsistencyFail((Kerb3961 *)L"Splitting buffer into parts that exceed the whole", v11);
  return this;
}

```

## disassembly

```asm
0x180001700  mov     [rsp+arg_8], rbx
0x180001705  mov     [rsp+arg_10], rbp
0x18000170a  push    rsi
0x18000170b  push    rdi
0x18000170c  push    r14
0x18000170e  sub     rsp, 20h
0x180001712  mov     r14, r8
0x180001715  mov     rbp, rdx
0x180001718  mov     rbx, rcx
0x18000171b  mov     rdi, rcx
0x18000171e  mov     esi, 3
0x180001723  mov     rcx, rdi; this
0x180001726  call    ??0ReadOnlyBinary@Kerb3961@@QEAA@XZ; Kerb3961::ReadOnlyBinary::ReadOnlyBinary(void)
0x18000172b  add     rdi, 10h
0x18000172f  sub     rsi, 1
0x180001733  jnz     short loc_180001723
0x180001735  xor     r8d, r8d
0x180001738  xor     r9d, r9d
0x18000173b  mov     rdx, [rbp+8]
0x18000173f  mov     rcx, r9
0x180001742  mov     rax, [r14+r9*8]
0x180001746  add     rcx, rcx
0x180001749  add     rdx, r8; unsigned __int16 *
0x18000174c  mov     [rbx+rcx*8], rax
0x180001750  mov     [rbx+rcx*8+8], rdx
0x180001755  add     r8, [r14+r9*8]
0x180001759  inc     r9
0x18000175c  cmp     r9, 3
0x180001760  jb      short loc_18000173B
0x180001762  cmp     r8, [rbp+0]
0x180001766  ja      short loc_18000177F
0x180001768  mov     rbp, [rsp+38h+arg_10]
0x18000176d  mov     rax, rbx
0x180001770  mov     rbx, [rsp+38h+arg_8]
0x180001775  add     rsp, 20h
0x180001779  pop     r14
0x18000177b  pop     rdi
0x18000177c  pop     rsi
0x18000177d  retn
0x18000177f  lea     rcx, aSplittingBuffe; "Splitting buffer into parts that exceed"...
0x180001786  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
