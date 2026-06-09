# Kerb3961::SSPICipherSuite<1,1,1>::InterleaveDecryptionAndIntegrity(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180008a5c`
- end: `0x180008bb0`
- name: `?InterleaveDecryptionAndIntegrity@?$SSPICipherSuite@$00$00$00@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a090`

## callees

- `0x180002c64`
- `0x180008a5c`
- `0x18000901c`
- `0x18001d360`

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
      memcpy_0(v14, v13, v17);
      v13 += *(_QWORD *)v11;
    }
    else
    {
      memcpy_0(v14, *(const void **)(v11 + 8), v17);
    }
    v14 += *(_QWORD *)v11;
    v11 += 24;
  }
  v18 = a3[1];
  if ( (unsigned __int64)v13 < v18 + *a3 )
    memcpy_0(v14, v13, *a3 + v18 - (_QWORD)v13);
  *(_DWORD *)(a1 + 16) = v22;
  *(_QWORD *)a1 = v20;
  *(_QWORD *)(a1 + 8) = v12;
  return a1;
}

```

## disassembly

```asm
0x180008a5c  push    rbx
0x180008a5e  push    rbp
0x180008a5f  push    rsi
0x180008a60  push    rdi
0x180008a61  push    r12
0x180008a63  push    r13
0x180008a65  push    r14
0x180008a67  push    r15
0x180008a69  sub     rsp, 48h
0x180008a6d  mov     rax, [rdx]
0x180008a70  xor     r13d, r13d
0x180008a73  mov     r14, r8
0x180008a76  mov     r15, rdx
0x180008a79  mov     rbx, rcx
0x180008a7c  test    rax, rax
0x180008a7f  jnz     short loc_180008A91
0x180008a81  mov     [rcx], r13
0x180008a84  mov     [rcx+8], r13
0x180008a88  mov     [rcx+10h], r13d
0x180008a8c  jmp     loc_180008B9C
0x180008a91  mov     rcx, [rdx+8]
0x180008a95  lea     rax, [rax+rax*2]
0x180008a99  mov     r8, [r8]
0x180008a9c  mov     r9b, r13b
0x180008a9f  lea     r10, [rcx+rax*8]
0x180008aa3  cmp     rcx, r10
0x180008aa6  jz      loc_180008B91
0x180008aac  cmp     [rcx+10h], r13b
0x180008ab0  jnz     short loc_180008ACC
0x180008ab2  mov     rdx, [rcx]
0x180008ab5  add     rdx, r8; char *
0x180008ab8  cmp     rdx, r8
0x180008abb  jb      short loc_180008B24
0x180008abd  cmp     rdx, 0FFFFFFFFFFFF0000h
0x180008ac4  ja      short loc_180008B08
0x180008ac6  mov     r9b, 1
0x180008ac9  mov     r8, rdx
0x180008acc  add     rcx, 18h
0x180008ad0  cmp     rcx, r10
0x180008ad3  jnz     short loc_180008AAC
0x180008ad5  test    r9b, r9b
0x180008ad8  jz      loc_180008B91
0x180008ade  mov     rdx, r8
0x180008ae1  lea     rcx, [rsp+88h+var_68]
0x180008ae6  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180008aeb  mov     rax, [r15]
0x180008aee  mov     rdi, [r15+8]
0x180008af2  mov     r12, [rsp+88h+var_60]
0x180008af7  mov     rsi, [r14+8]
0x180008afb  mov     rbp, r12
0x180008afe  lea     rcx, [rax+rax*2]
0x180008b02  lea     r15, [rdi+rcx*8]
0x180008b06  jmp     short loc_180008B56
0x180008b08  lea     rcx, aNewtotallength_0; "newTotalLength <= MessageLimit"
0x180008b0f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180008b14  mov     [rbx], r13
0x180008b17  mov     [rbx+8], r13
0x180008b1b  mov     dword ptr [rbx+10h], 0C0000095h
0x180008b22  jmp     short loc_180008B9C
0x180008b24  lea     rcx, aNewtotallength; "newTotalLength >= totalLength"
0x180008b2b  jmp     short loc_180008B0F
0x180008b2d  mov     rcx, rbp; void *
0x180008b30  mov     r8, [rdi]; Size
0x180008b33  cmp     [rdi+10h], r13b
0x180008b37  jz      short loc_180008B46
0x180008b39  mov     rdx, rsi; Src
0x180008b3c  call    memcpy_0
0x180008b41  add     rsi, [rdi]
0x180008b44  jmp     short loc_180008B4F
0x180008b46  mov     rdx, [rdi+8]; Src
0x180008b4a  call    memcpy_0
0x180008b4f  add     rbp, [rdi]
0x180008b52  add     rdi, 18h
0x180008b56  cmp     rdi, r15
0x180008b59  jnz     short loc_180008B2D
0x180008b5b  mov     rcx, [r14]
0x180008b5e  mov     r8, [r14+8]
0x180008b62  lea     rax, [r8+rcx]
0x180008b66  cmp     rsi, rax
0x180008b69  jnb     short loc_180008B7C
0x180008b6b  sub     r8, rsi
0x180008b6e  mov     rdx, rsi; Src
0x180008b71  add     r8, rcx; Size
0x180008b74  mov     rcx, rbp; void *
0x180008b77  call    memcpy_0
0x180008b7c  mov     eax, [rsp+88h+var_58]
0x180008b80  mov     [rbx+10h], eax
0x180008b83  mov     rax, [rsp+88h+var_68]
0x180008b88  mov     [rbx], rax
0x180008b8b  mov     [rbx+8], r12
0x180008b8f  jmp     short loc_180008B9C
0x180008b91  mov     [rbx], r13
0x180008b94  mov     [rbx+8], r13
0x180008b98  mov     [rbx+10h], r13d
0x180008b9c  mov     rax, rbx
0x180008b9f  add     rsp, 48h
0x180008ba3  pop     r15
0x180008ba5  pop     r14
0x180008ba7  pop     r13
0x180008ba9  pop     r12
0x180008bab  pop     rdi
0x180008bac  pop     rsi
0x180008bad  pop     rbp
0x180008bae  pop     rbx
0x180008baf  retn
```
