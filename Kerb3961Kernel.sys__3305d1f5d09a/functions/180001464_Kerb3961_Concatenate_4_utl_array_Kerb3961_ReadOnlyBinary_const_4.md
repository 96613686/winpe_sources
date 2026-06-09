# Kerb3961::Concatenate<4>(utl::array<Kerb3961::ReadOnlyBinary const,4>)

- ea: `0x180001464`
- end: `0x180001579`
- name: `??$Concatenate@$03@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@0@U?$array@$$CBUReadOnlyBinary@Kerb3961@@$03@utl@@@Z`
- size: `277`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180003240`
- `0x180004a00`
- `0x180007710`
- `0x18000d900`
- `0x18000eec0`

## callees

- `0x180001464`
- `0x180001818`
- `0x180011760`
- `0x180012300`

## pseudocode

```c
__int64 __fastcall Kerb3961::Concatenate<4>(__int64 a1, size_t *a2)
{
  size_t *v2; // rdi
  size_t *v3; // rsi
  size_t *v4; // rax
  const struct std::nothrow_t *v6; // r15
  char *v7; // rcx
  const char *v8; // rdx
  void *v9; // rbx
  char *v10; // r12
  size_t v11; // rbp
  void *v13; // [rsp+20h] [rbp-38h] BYREF

  v2 = a2;
  v3 = a2 + 8;
  v4 = a2;
  v6 = 0;
  while ( v4 != v3 )
  {
    if ( *v4 > 0xFFFFFFFF )
    {
      v7 = "entry.length <= utl::numeric_limits<uint32_t>::max()";
      goto LABEL_17;
    }
    v6 = (const struct std::nothrow_t *)((char *)v6 + *v4);
    v4 += 2;
  }
  if ( (unsigned __int64)v6 > 0xFFFFFFFF )
  {
    v7 = "length <= utl::numeric_limits<uint32_t>::max()";
LABEL_17:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v7, (const char *)0xFFFFFFFFLL);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = -1073741675;
  }
  else
  {
    if ( !v6 )
    {
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
LABEL_9:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
    }
    utl::make_unique<unsigned char [0],0>(&v13, v6);
    v9 = v13;
    if ( v13 )
    {
      v10 = (char *)v13;
      while ( v2 != v3 )
      {
        v11 = *v2;
        memmove(v10, (const void *)v2[1], *v2);
        v10 += v11;
        v2 += 2;
      }
      *(_QWORD *)a1 = v6;
      *(_QWORD *)(a1 + 8) = v9;
      goto LABEL_9;
    }
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"result", v8);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = -1073741801;
  }
  return a1;
}

```

## disassembly

```asm
0x180001464  mov     [rsp+arg_8], rbx
0x180001469  mov     [rsp+arg_10], rbp
0x18000146e  push    rsi
0x18000146f  push    rdi
0x180001470  push    r12
0x180001472  push    r14
0x180001474  push    r15
0x180001476  sub     rsp, 30h
0x18000147a  mov     rdi, rdx
0x18000147d  lea     rsi, [rdx+40h]
0x180001481  mov     rax, rdx
0x180001484  mov     r14, rcx
0x180001487  mov     edx, 0FFFFFFFFh; char *
0x18000148c  xor     r15d, r15d
0x18000148f  cmp     rax, rsi
0x180001492  jz      short loc_1800014B1
0x180001494  mov     rcx, [rax]
0x180001497  cmp     rcx, rdx
0x18000149a  ja      short loc_1800014A5
0x18000149c  add     r15, rcx
0x18000149f  add     rax, 10h
0x1800014a3  jmp     short loc_18000148F
0x1800014a5  lea     rcx, aEntryLengthUtl; "entry.length <= utl::numeric_limits<uin"...
0x1800014ac  jmp     loc_180001542
0x1800014b1  cmp     r15, rdx
0x1800014b4  ja      loc_18000153B
0x1800014ba  test    r15, r15
0x1800014bd  jnz     short loc_1800014D3
0x1800014bf  mov     [r14], r15
0x1800014c2  mov     [r14+8], r15
0x1800014c6  mov     dword ptr [r14+10h], 0
0x1800014ce  jmp     loc_18000155E
0x1800014d3  mov     rdx, r15
0x1800014d6  lea     rcx, [rsp+58h+var_38]
0x1800014db  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x1800014e0  mov     rbx, [rsp+58h+var_38]
0x1800014e5  test    rbx, rbx
0x1800014e8  jz      short loc_180001516
0x1800014ea  mov     r12, rbx
0x1800014ed  cmp     rdi, rsi
0x1800014f0  jz      short loc_18000150D
0x1800014f2  mov     rbp, [rdi]
0x1800014f5  mov     rcx, r12; void *
0x1800014f8  mov     rdx, [rdi+8]; Src
0x1800014fc  mov     r8, rbp; Size
0x1800014ff  call    memmove
0x180001504  add     r12, rbp
0x180001507  add     rdi, 10h
0x18000150b  jmp     short loc_1800014ED
0x18000150d  mov     [r14], r15
0x180001510  mov     [r14+8], rbx
0x180001514  jmp     short loc_1800014C6
0x180001516  lea     rcx, aResult; "result"
0x18000151d  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180001522  mov     qword ptr [r14], 0
0x180001529  mov     qword ptr [r14+8], 0
0x180001531  mov     dword ptr [r14+10h], 0C0000017h
0x180001539  jmp     short loc_18000155E
0x18000153b  lea     rcx, aLengthUtlNumer; "length <= utl::numeric_limits<uint32_t>"...
0x180001542  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180001547  mov     qword ptr [r14], 0
0x18000154e  mov     qword ptr [r14+8], 0
0x180001556  mov     dword ptr [r14+10h], 0C0000095h
0x18000155e  mov     rbx, [rsp+58h+arg_8]
0x180001563  mov     rax, r14
0x180001566  mov     rbp, [rsp+58h+arg_10]
0x18000156b  add     rsp, 30h
0x18000156f  pop     r15
0x180001571  pop     r14
0x180001573  pop     r12
0x180001575  pop     rdi
0x180001576  pop     rsi
0x180001577  retn
```
