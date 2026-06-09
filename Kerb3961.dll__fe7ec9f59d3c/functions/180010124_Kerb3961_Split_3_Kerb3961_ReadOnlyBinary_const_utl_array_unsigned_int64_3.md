# Kerb3961::Split<3>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,3>)

- ea: `0x180010124`
- end: `0x1800101af`
- name: `??$Split@$02@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$02@utl@@AEBUReadOnlyBinary@0@U?$array@_K$02@2@@Z`
- size: `139`
- prototype: `__int64 __fastcall(Kerb3961::ReadOnlyBinary *this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180011530`
- `0x18001190c`
- `0x180019550`

## callees

- `0x1800033f4`
- `0x18000490c`
- `0x180010124`

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
0x180010124  mov     [rsp+arg_8], rbx
0x180010129  mov     [rsp+arg_10], rbp
0x18001012e  push    rsi
0x18001012f  push    rdi
0x180010130  push    r14
0x180010132  sub     rsp, 20h
0x180010136  mov     r14, r8
0x180010139  mov     rbp, rdx
0x18001013c  mov     rbx, rcx
0x18001013f  mov     rdi, rcx
0x180010142  mov     esi, 3
0x180010147  mov     rcx, rdi; this
0x18001014a  call    ??0ReadOnlyBinary@Kerb3961@@QEAA@XZ; Kerb3961::ReadOnlyBinary::ReadOnlyBinary(void)
0x18001014f  add     rdi, 10h
0x180010153  sub     rsi, 1
0x180010157  jnz     short loc_180010147
0x180010159  xor     r8d, r8d
0x18001015c  xor     r9d, r9d
0x18001015f  mov     rdx, [rbp+8]
0x180010163  mov     rcx, r9
0x180010166  mov     rax, [r14+r9*8]
0x18001016a  add     rcx, rcx
0x18001016d  add     rdx, r8; unsigned __int16 *
0x180010170  mov     [rbx+rcx*8], rax
0x180010174  mov     [rbx+rcx*8+8], rdx
0x180010179  add     r8, [r14+r9*8]
0x18001017d  inc     r9
0x180010180  cmp     r9, 3
0x180010184  jb      short loc_18001015F
0x180010186  cmp     r8, [rbp+0]
0x18001018a  ja      short loc_1800101A2
0x18001018c  mov     rbp, [rsp+38h+arg_10]
0x180010191  mov     rax, rbx
0x180010194  mov     rbx, [rsp+38h+arg_8]
0x180010199  add     rsp, 20h
0x18001019d  pop     r14
0x18001019f  pop     rdi
0x1800101a0  pop     rsi
0x1800101a1  retn
0x1800101a2  lea     rcx, aSplittingBuffe; "Splitting buffer into parts that exceed"...
0x1800101a9  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
