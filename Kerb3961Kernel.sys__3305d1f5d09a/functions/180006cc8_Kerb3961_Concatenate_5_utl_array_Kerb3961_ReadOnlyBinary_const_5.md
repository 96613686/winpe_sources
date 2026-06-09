# Kerb3961::Concatenate<5>(utl::array<Kerb3961::ReadOnlyBinary const,5>)

- ea: `0x180006cc8`
- end: `0x180006ddd`
- name: `??$Concatenate@$04@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@0@U?$array@$$CBUReadOnlyBinary@Kerb3961@@$04@utl@@@Z`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007e9c`

## callees

- `0x180001818`
- `0x180006cc8`
- `0x180011760`
- `0x180012300`

## pseudocode

```c
__int64 __fastcall Kerb3961::Concatenate<5>(__int64 a1, size_t *a2)
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
  v3 = a2 + 10;
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
0x180006cc8  mov     [rsp+arg_8], rbx
0x180006ccd  mov     [rsp+arg_10], rbp
0x180006cd2  push    rsi
0x180006cd3  push    rdi
0x180006cd4  push    r12
0x180006cd6  push    r14
0x180006cd8  push    r15
0x180006cda  sub     rsp, 30h
0x180006cde  mov     rdi, rdx
0x180006ce1  lea     rsi, [rdx+50h]
0x180006ce5  mov     rax, rdx
0x180006ce8  mov     r14, rcx
0x180006ceb  mov     edx, 0FFFFFFFFh; char *
0x180006cf0  xor     r15d, r15d
0x180006cf3  cmp     rax, rsi
0x180006cf6  jz      short loc_180006D15
0x180006cf8  mov     rcx, [rax]
0x180006cfb  cmp     rcx, rdx
0x180006cfe  ja      short loc_180006D09
0x180006d00  add     r15, rcx
0x180006d03  add     rax, 10h
0x180006d07  jmp     short loc_180006CF3
0x180006d09  lea     rcx, aEntryLengthUtl; "entry.length <= utl::numeric_limits<uin"...
0x180006d10  jmp     loc_180006DA6
0x180006d15  cmp     r15, rdx
0x180006d18  ja      loc_180006D9F
0x180006d1e  test    r15, r15
0x180006d21  jnz     short loc_180006D37
0x180006d23  mov     [r14], r15
0x180006d26  mov     [r14+8], r15
0x180006d2a  mov     dword ptr [r14+10h], 0
0x180006d32  jmp     loc_180006DC2
0x180006d37  mov     rdx, r15
0x180006d3a  lea     rcx, [rsp+58h+var_38]
0x180006d3f  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x180006d44  mov     rbx, [rsp+58h+var_38]
0x180006d49  test    rbx, rbx
0x180006d4c  jz      short loc_180006D7A
0x180006d4e  mov     r12, rbx
0x180006d51  cmp     rdi, rsi
0x180006d54  jz      short loc_180006D71
0x180006d56  mov     rbp, [rdi]
0x180006d59  mov     rcx, r12; void *
0x180006d5c  mov     rdx, [rdi+8]; Src
0x180006d60  mov     r8, rbp; Size
0x180006d63  call    memmove
0x180006d68  add     r12, rbp
0x180006d6b  add     rdi, 10h
0x180006d6f  jmp     short loc_180006D51
0x180006d71  mov     [r14], r15
0x180006d74  mov     [r14+8], rbx
0x180006d78  jmp     short loc_180006D2A
0x180006d7a  lea     rcx, aResult; "result"
0x180006d81  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180006d86  mov     qword ptr [r14], 0
0x180006d8d  mov     qword ptr [r14+8], 0
0x180006d95  mov     dword ptr [r14+10h], 0C0000017h
0x180006d9d  jmp     short loc_180006DC2
0x180006d9f  lea     rcx, aLengthUtlNumer; "length <= utl::numeric_limits<uint32_t>"...
0x180006da6  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180006dab  mov     qword ptr [r14], 0
0x180006db2  mov     qword ptr [r14+8], 0
0x180006dba  mov     dword ptr [r14+10h], 0C0000095h
0x180006dc2  mov     rbx, [rsp+58h+arg_8]
0x180006dc7  mov     rax, r14
0x180006dca  mov     rbp, [rsp+58h+arg_10]
0x180006dcf  add     rsp, 30h
0x180006dd3  pop     r15
0x180006dd5  pop     r14
0x180006dd7  pop     r12
0x180006dd9  pop     rdi
0x180006dda  pop     rsi
0x180006ddb  retn
```
