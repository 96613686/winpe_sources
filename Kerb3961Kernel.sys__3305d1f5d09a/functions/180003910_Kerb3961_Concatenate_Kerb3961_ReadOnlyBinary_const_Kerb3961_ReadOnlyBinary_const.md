# Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180003910`
- end: `0x180003a32`
- name: `?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z`
- size: `290`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x1800023e0`
- `0x180002cc4`
- `0x180003020`
- `0x180003590`
- `0x180003dc0`
- `0x1800051e0`
- `0x18000d900`
- `0x18000fb70`

## callees

- `0x180001818`
- `0x180003910`
- `0x180011760`
- `0x180012300`

## pseudocode

```c
__int64 __fastcall Kerb3961::Concatenate(__int64 a1, _OWORD *a2, __int128 *a3)
{
  unsigned __int64 v4; // rbp
  __int128 v5; // xmm1
  _BYTE *v6; // rax
  char *v7; // rcx
  const char *v8; // rdx
  void *v9; // rdi
  char *v10; // r15
  const void **i; // rbx
  size_t v12; // rsi
  _OWORD v14[2]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v15[56]; // [rsp+40h] [rbp-38h] BYREF
  void *v16; // [rsp+80h] [rbp+8h] BYREF

  v4 = 0;
  v5 = *a3;
  v6 = v14;
  v14[0] = *a2;
  v14[1] = v5;
  while ( v6 != v15 )
  {
    if ( *(_QWORD *)v6 > 0xFFFFFFFF )
    {
      v7 = "entry.length <= utl::numeric_limits<uint32_t>::max()";
      goto LABEL_17;
    }
    v4 += *(_QWORD *)v6;
    v6 += 16;
  }
  if ( v4 > 0xFFFFFFFF )
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
    if ( !v4 )
    {
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
LABEL_9:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
    }
    utl::make_unique<unsigned char [0],0>(&v16);
    v9 = v16;
    if ( v16 )
    {
      v10 = (char *)v16;
      for ( i = (const void **)v14; i != (const void **)v15; i += 2 )
      {
        v12 = (size_t)*i;
        memmove(v10, i[1], (size_t)*i);
        v10 += v12;
      }
      *(_QWORD *)a1 = v4;
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
0x180003910  push    rbx
0x180003912  push    rbp
0x180003913  push    rsi
0x180003914  push    rdi
0x180003915  push    r14
0x180003917  push    r15
0x180003919  sub     rsp, 48h
0x18000391d  movups  xmm0, xmmword ptr [rdx]
0x180003920  mov     r14, rcx
0x180003923  xor     ebp, ebp
0x180003925  movups  xmm1, xmmword ptr [r8]
0x180003929  lea     rax, [rsp+78h+var_58]
0x18000392e  mov     edx, 0FFFFFFFFh; char *
0x180003933  movaps  [rsp+78h+var_58], xmm0
0x180003938  movaps  [rsp+78h+var_48], xmm1
0x18000393d  lea     rcx, [rsp+78h+var_38]
0x180003942  cmp     rax, rcx
0x180003945  jz      short loc_180003964
0x180003947  mov     rcx, [rax]
0x18000394a  cmp     rcx, rdx
0x18000394d  ja      short loc_180003958
0x18000394f  add     rbp, rcx
0x180003952  add     rax, 10h
0x180003956  jmp     short loc_18000393D
0x180003958  lea     rcx, aEntryLengthUtl; "entry.length <= utl::numeric_limits<uin"...
0x18000395f  jmp     loc_180003A05
0x180003964  cmp     rbp, rdx
0x180003967  ja      loc_1800039FE
0x18000396d  test    rbp, rbp
0x180003970  jnz     short loc_180003986
0x180003972  mov     [r14], rbp
0x180003975  mov     [r14+8], rbp
0x180003979  mov     dword ptr [r14+10h], 0
0x180003981  jmp     loc_180003A21
0x180003986  mov     rdx, rbp
0x180003989  lea     rcx, [rsp+78h+arg_0]
0x180003991  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x180003996  mov     rdi, [rsp+78h+arg_0]
0x18000399e  test    rdi, rdi
0x1800039a1  jz      short loc_1800039D9
0x1800039a3  mov     r15, rdi
0x1800039a6  lea     rbx, [rsp+78h+var_58]
0x1800039ab  lea     rax, [rsp+78h+var_38]
0x1800039b0  cmp     rbx, rax
0x1800039b3  jz      short loc_1800039D0
0x1800039b5  mov     rsi, [rbx]
0x1800039b8  mov     rcx, r15; void *
0x1800039bb  mov     rdx, [rbx+8]; Src
0x1800039bf  mov     r8, rsi; Size
0x1800039c2  call    memmove
0x1800039c7  add     r15, rsi
0x1800039ca  add     rbx, 10h
0x1800039ce  jmp     short loc_1800039AB
0x1800039d0  mov     [r14], rbp
0x1800039d3  mov     [r14+8], rdi
0x1800039d7  jmp     short loc_180003979
0x1800039d9  lea     rcx, aResult; "result"
0x1800039e0  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800039e5  mov     qword ptr [r14], 0
0x1800039ec  mov     qword ptr [r14+8], 0
0x1800039f4  mov     dword ptr [r14+10h], 0C0000017h
0x1800039fc  jmp     short loc_180003A21
0x1800039fe  lea     rcx, aLengthUtlNumer; "length <= utl::numeric_limits<uint32_t>"...
0x180003a05  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180003a0a  mov     qword ptr [r14], 0
0x180003a11  mov     qword ptr [r14+8], 0
0x180003a19  mov     dword ptr [r14+10h], 0C0000095h
0x180003a21  mov     rax, r14
0x180003a24  add     rsp, 48h
0x180003a28  pop     r15
0x180003a2a  pop     r14
0x180003a2c  pop     rdi
0x180003a2d  pop     rsi
0x180003a2e  pop     rbp
0x180003a2f  pop     rbx
0x180003a30  retn
```
