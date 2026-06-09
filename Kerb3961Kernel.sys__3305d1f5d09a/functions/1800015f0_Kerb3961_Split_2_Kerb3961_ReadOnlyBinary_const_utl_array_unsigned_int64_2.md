# Kerb3961::Split<2>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,2>)

- ea: `0x1800015f0`
- end: `0x18000167c`
- name: `??$Split@$01@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$01@utl@@AEBUReadOnlyBinary@0@U?$array@_K$01@2@@Z`
- size: `140`
- prototype: `__int64 __fastcall(Kerb3961::ReadOnlyBinary *this)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800028d4`
- `0x180003b10`
- `0x180003dc0`
- `0x180007338`
- `0x180007ad0`
- `0x18000f2c0`

## callees

- `0x1800015f0`
- `0x1800018cc`
- `0x180003a38`

## pseudocode

```c
Kerb3961::ReadOnlyBinary *__fastcall Kerb3961::Split<2>(
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
  v7 = 2;
  do
  {
    Kerb3961::ReadOnlyBinary::ReadOnlyBinary(v6);
    v6 = (Kerb3961::ReadOnlyBinary *)((char *)v6 + 16);
    --v7;
  }
  while ( v7 );
  v8 = 0;
  for ( i = 0; i < 2; ++i )
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
0x1800015f0  mov     [rsp+arg_8], rbx
0x1800015f5  mov     [rsp+arg_10], rbp
0x1800015fa  push    rsi
0x1800015fb  push    rdi
0x1800015fc  push    r14
0x1800015fe  sub     rsp, 20h
0x180001602  mov     r14, r8
0x180001605  mov     rbp, rdx
0x180001608  mov     rbx, rcx
0x18000160b  mov     rdi, rcx
0x18000160e  mov     esi, 2
0x180001613  mov     rcx, rdi; this
0x180001616  call    ??0ReadOnlyBinary@Kerb3961@@QEAA@XZ; Kerb3961::ReadOnlyBinary::ReadOnlyBinary(void)
0x18000161b  add     rdi, 10h
0x18000161f  sub     rsi, 1
0x180001623  jnz     short loc_180001613
0x180001625  xor     r8d, r8d
0x180001628  xor     r9d, r9d
0x18000162b  mov     rdx, [rbp+8]
0x18000162f  mov     rcx, r9
0x180001632  mov     rax, [r14+r9*8]
0x180001636  add     rcx, rcx
0x180001639  add     rdx, r8; unsigned __int16 *
0x18000163c  mov     [rbx+rcx*8], rax
0x180001640  mov     [rbx+rcx*8+8], rdx
0x180001645  add     r8, [r14+r9*8]
0x180001649  inc     r9
0x18000164c  cmp     r9, 2
0x180001650  jb      short loc_18000162B
0x180001652  cmp     r8, [rbp+0]
0x180001656  ja      short loc_18000166F
0x180001658  mov     rbp, [rsp+38h+arg_10]
0x18000165d  mov     rax, rbx
0x180001660  mov     rbx, [rsp+38h+arg_8]
0x180001665  add     rsp, 20h
0x180001669  pop     r14
0x18000166b  pop     rdi
0x18000166c  pop     rsi
0x18000166d  retn
0x18000166f  lea     rcx, aSplittingBuffe; "Splitting buffer into parts that exceed"...
0x180001676  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
