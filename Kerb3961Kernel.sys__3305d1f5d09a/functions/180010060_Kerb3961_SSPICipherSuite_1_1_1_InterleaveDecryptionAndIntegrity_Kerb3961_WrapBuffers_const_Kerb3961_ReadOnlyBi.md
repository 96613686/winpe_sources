# Kerb3961::SSPICipherSuite<1,1,1>::InterleaveDecryptionAndIntegrity(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180010060`
- end: `0x1800101b5`
- name: `?InterleaveDecryptionAndIntegrity@?$SSPICipherSuite@$00$00$00@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010bd0`

## callees

- `0x180005b1c`
- `0x180010060`
- `0x180011760`
- `0x180012300`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,1>::InterleaveDecryptionAndIntegrity(
        __int64 a1,
        _QWORD *a2,
        unsigned __int64 *a3)
{
  __int64 v6; // rcx
  unsigned __int64 v7; // r8
  char v8; // r9
  __int64 v9; // r10
  const char *v10; // rdx
  __int64 v11; // rdi
  void *v12; // r12
  char *v13; // rsi
  char *v14; // rbp
  __int64 v15; // r15
  char *v16; // rcx
  size_t v17; // r8
  unsigned __int64 v18; // r8
  __int64 v20; // [rsp+20h] [rbp-68h] BYREF
  void *v21; // [rsp+28h] [rbp-60h]
  int v22; // [rsp+30h] [rbp-58h]

  if ( !*a2 )
  {
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = 0;
    return a1;
  }
  v6 = a2[1];
  v7 = *a3;
  v8 = 0;
  v9 = v6 + 24LL * *a2;
  if ( v6 == v9 )
  {
LABEL_22:
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = 0;
    return a1;
  }
  do
  {
    if ( *(_BYTE *)(v6 + 16) )
      goto LABEL_8;
    v10 = (const char *)(v7 + *(_QWORD *)v6);
    if ( (unsigned __int64)v10 < v7 )
    {
      v16 = "newTotalLength >= totalLength";
      goto LABEL_12;
    }
    if ( (unsigned __int64)v10 > 0xFFFFFFFFFFFF0000uLL )
    {
      v16 = "newTotalLength <= MessageLimit";
LABEL_12:
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v16, v10);
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = -1073741675;
      return a1;
    }
    v8 = 1;
    v7 += *(_QWORD *)v6;
LABEL_8:
    v6 += 24;
  }
  while ( v6 != v9 );
  if ( !v8 )
    goto LABEL_22;
  Kerb3961::MakeBuffer(&v20);
  v11 = a2[1];
  v12 = v21;
  v13 = (char *)a3[1];
  v14 = (char *)v21;
  v15 = v11 + 24LL * *a2;
  while ( v11 != v15 )
  {
    v17 = *(_QWORD *)v11;
    if ( *(_BYTE *)(v11 + 16) )
    {
      memmove(v14, v13, v17);
      v13 += *(_QWORD *)v11;
    }
    else
    {
      memmove(v14, *(const void **)(v11 + 8), v17);
    }
    v14 += *(_QWORD *)v11;
    v11 += 24;
  }
  v18 = a3[1];
  if ( (unsigned __int64)v13 < v18 + *a3 )
    memmove(v14, v13, *a3 + v18 - (_QWORD)v13);
  *(_DWORD *)(a1 + 16) = v22;
  *(_QWORD *)a1 = v20;
  *(_QWORD *)(a1 + 8) = v12;
  return a1;
}

```

## disassembly

```asm
0x180010060  push    rbx
0x180010062  push    rbp
0x180010063  push    rsi
0x180010064  push    rdi
0x180010065  push    r12
0x180010067  push    r13
0x180010069  push    r14
0x18001006b  push    r15
0x18001006d  sub     rsp, 48h
0x180010071  mov     rax, [rdx]
0x180010074  xor     r13d, r13d
0x180010077  mov     r14, r8
0x18001007a  mov     r15, rdx
0x18001007d  mov     rbx, rcx
0x180010080  test    rax, rax
0x180010083  jnz     short loc_180010095
0x180010085  mov     [rcx], r13
0x180010088  mov     [rcx+8], r13
0x18001008c  mov     [rcx+10h], r13d
0x180010090  jmp     loc_1800101A0
0x180010095  mov     rcx, [rdx+8]
0x180010099  lea     rax, [rax+rax*2]
0x18001009d  mov     r8, [r8]
0x1800100a0  mov     r9b, r13b
0x1800100a3  lea     r10, [rcx+rax*8]
0x1800100a7  cmp     rcx, r10
0x1800100aa  jz      loc_180010195
0x1800100b0  cmp     [rcx+10h], r13b
0x1800100b4  jnz     short loc_1800100D0
0x1800100b6  mov     rdx, [rcx]
0x1800100b9  add     rdx, r8; char *
0x1800100bc  cmp     rdx, r8
0x1800100bf  jb      short loc_180010128
0x1800100c1  cmp     rdx, 0FFFFFFFFFFFF0000h
0x1800100c8  ja      short loc_18001010C
0x1800100ca  mov     r9b, 1
0x1800100cd  mov     r8, rdx
0x1800100d0  add     rcx, 18h
0x1800100d4  cmp     rcx, r10
0x1800100d7  jnz     short loc_1800100B0
0x1800100d9  test    r9b, r9b
0x1800100dc  jz      loc_180010195
0x1800100e2  mov     rdx, r8
0x1800100e5  lea     rcx, [rsp+88h+var_68]
0x1800100ea  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x1800100ef  mov     rax, [r15]
0x1800100f2  mov     rdi, [r15+8]
0x1800100f6  mov     r12, [rsp+88h+var_60]
0x1800100fb  mov     rsi, [r14+8]
0x1800100ff  mov     rbp, r12
0x180010102  lea     rcx, [rax+rax*2]
0x180010106  lea     r15, [rdi+rcx*8]
0x18001010a  jmp     short loc_18001015A
0x18001010c  lea     rcx, aNewtotallength_0; "newTotalLength <= MessageLimit"
0x180010113  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180010118  mov     [rbx], r13
0x18001011b  mov     [rbx+8], r13
0x18001011f  mov     dword ptr [rbx+10h], 0C0000095h
0x180010126  jmp     short loc_1800101A0
0x180010128  lea     rcx, aNewtotallength; "newTotalLength >= totalLength"
0x18001012f  jmp     short loc_180010113
0x180010131  mov     rcx, rbp; void *
0x180010134  mov     r8, [rdi]; Size
0x180010137  cmp     [rdi+10h], r13b
0x18001013b  jz      short loc_18001014A
0x18001013d  mov     rdx, rsi; Src
0x180010140  call    memmove
0x180010145  add     rsi, [rdi]
0x180010148  jmp     short loc_180010153
0x18001014a  mov     rdx, [rdi+8]; Src
0x18001014e  call    memmove
0x180010153  add     rbp, [rdi]
0x180010156  add     rdi, 18h
0x18001015a  cmp     rdi, r15
0x18001015d  jnz     short loc_180010131
0x18001015f  mov     rcx, [r14]
0x180010162  mov     r8, [r14+8]
0x180010166  lea     rax, [r8+rcx]
0x18001016a  cmp     rsi, rax
0x18001016d  jnb     short loc_180010180
0x18001016f  sub     r8, rsi
0x180010172  mov     rdx, rsi; Src
0x180010175  add     r8, rcx; Size
0x180010178  mov     rcx, rbp; void *
0x18001017b  call    memmove
0x180010180  mov     eax, [rsp+88h+var_58]
0x180010184  mov     [rbx+10h], eax
0x180010187  mov     rax, [rsp+88h+var_68]
0x18001018c  mov     [rbx], rax
0x18001018f  mov     [rbx+8], r12
0x180010193  jmp     short loc_1800101A0
0x180010195  mov     [rbx], r13
0x180010198  mov     [rbx+8], r13
0x18001019c  mov     [rbx+10h], r13d
0x1800101a0  mov     rax, rbx
0x1800101a3  add     rsp, 48h
0x1800101a7  pop     r15
0x1800101a9  pop     r14
0x1800101ab  pop     r13
0x1800101ad  pop     r12
0x1800101af  pop     rdi
0x1800101b0  pop     rsi
0x1800101b1  pop     rbp
0x1800101b2  pop     rbx
0x1800101b3  retn
```
