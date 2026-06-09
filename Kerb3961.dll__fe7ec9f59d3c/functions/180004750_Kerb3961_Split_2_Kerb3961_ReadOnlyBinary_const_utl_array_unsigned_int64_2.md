# Kerb3961::Split<2>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,2>)

- ea: `0x180004750`
- end: `0x1800047db`
- name: `??$Split@$01@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$01@utl@@AEBUReadOnlyBinary@0@U?$array@_K$01@2@@Z`
- size: `139`
- prototype: `__int64 __fastcall(Kerb3961::ReadOnlyBinary *this)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800071e0`
- `0x180011530`
- `0x1800126e0`
- `0x180019550`
- `0x180019cc0`
- `0x180019f70`

## callees

- `0x1800033f4`
- `0x180004750`
- `0x18000490c`

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
0x180004750  mov     [rsp+arg_8], rbx
0x180004755  mov     [rsp+arg_10], rbp
0x18000475a  push    rsi
0x18000475b  push    rdi
0x18000475c  push    r14
0x18000475e  sub     rsp, 20h
0x180004762  mov     r14, r8
0x180004765  mov     rbp, rdx
0x180004768  mov     rbx, rcx
0x18000476b  mov     rdi, rcx
0x18000476e  mov     esi, 2
0x180004773  mov     rcx, rdi; this
0x180004776  call    ??0ReadOnlyBinary@Kerb3961@@QEAA@XZ; Kerb3961::ReadOnlyBinary::ReadOnlyBinary(void)
0x18000477b  add     rdi, 10h
0x18000477f  sub     rsi, 1
0x180004783  jnz     short loc_180004773
0x180004785  xor     r8d, r8d
0x180004788  xor     r9d, r9d
0x18000478b  mov     rdx, [rbp+8]
0x18000478f  mov     rcx, r9
0x180004792  mov     rax, [r14+r9*8]
0x180004796  add     rcx, rcx
0x180004799  add     rdx, r8; unsigned __int16 *
0x18000479c  mov     [rbx+rcx*8], rax
0x1800047a0  mov     [rbx+rcx*8+8], rdx
0x1800047a5  add     r8, [r14+r9*8]
0x1800047a9  inc     r9
0x1800047ac  cmp     r9, 2
0x1800047b0  jb      short loc_18000478B
0x1800047b2  cmp     r8, [rbp+0]
0x1800047b6  ja      short loc_1800047CE
0x1800047b8  mov     rbp, [rsp+38h+arg_10]
0x1800047bd  mov     rax, rbx
0x1800047c0  mov     rbx, [rsp+38h+arg_8]
0x1800047c5  add     rsp, 20h
0x1800047c9  pop     r14
0x1800047cb  pop     rdi
0x1800047cc  pop     rsi
0x1800047cd  retn
0x1800047ce  lea     rcx, aSplittingBuffe; "Splitting buffer into parts that exceed"...
0x1800047d5  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
