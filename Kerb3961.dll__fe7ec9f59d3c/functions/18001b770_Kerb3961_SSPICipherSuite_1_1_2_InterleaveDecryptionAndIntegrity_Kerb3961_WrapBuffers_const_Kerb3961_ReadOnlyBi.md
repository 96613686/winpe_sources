# Kerb3961::SSPICipherSuite<1,1,2>::InterleaveDecryptionAndIntegrity(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18001b770`
- end: `0x18001b89f`
- name: `?InterleaveDecryptionAndIntegrity@?$SSPICipherSuite@$00$00$01@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001c5d0`

## callees

- `0x180002c64`
- `0x18000901c`
- `0x18001b770`
- `0x18001d360`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,2>::InterleaveDecryptionAndIntegrity(
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
  void *v12; // r15
  char *v13; // rbp
  char *v14; // rsi
  __int64 v15; // r14
  char *v16; // rcx
  size_t v17; // r8
  __int64 v19; // [rsp+20h] [rbp-58h] BYREF
  void *v20; // [rsp+28h] [rbp-50h]
  int v21; // [rsp+30h] [rbp-48h]

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
LABEL_20:
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
    goto LABEL_20;
  Kerb3961::MakeBuffer(&v19);
  v11 = a2[1];
  v12 = v20;
  v13 = (char *)a3[1];
  v14 = (char *)v20;
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
  *(_DWORD *)(a1 + 16) = v21;
  *(_QWORD *)a1 = v19;
  *(_QWORD *)(a1 + 8) = v12;
  return a1;
}

```

## disassembly

```asm
0x18001b770  push    rbx
0x18001b772  push    rbp
0x18001b773  push    rsi
0x18001b774  push    rdi
0x18001b775  push    r12
0x18001b777  push    r14
0x18001b779  push    r15
0x18001b77b  sub     rsp, 40h
0x18001b77f  mov     rax, [rdx]
0x18001b782  xor     r12d, r12d
0x18001b785  mov     rbp, r8
0x18001b788  mov     r14, rdx
0x18001b78b  mov     rbx, rcx
0x18001b78e  test    rax, rax
0x18001b791  jnz     short loc_18001B7A3
0x18001b793  mov     [rcx], r12
0x18001b796  mov     [rcx+8], r12
0x18001b79a  mov     [rcx+10h], r12d
0x18001b79e  jmp     loc_18001B88D
0x18001b7a3  mov     rcx, [rdx+8]
0x18001b7a7  lea     rax, [rax+rax*2]
0x18001b7ab  mov     r8, [r8]
0x18001b7ae  mov     r9b, r12b
0x18001b7b1  lea     r10, [rcx+rax*8]
0x18001b7b5  cmp     rcx, r10
0x18001b7b8  jz      loc_18001B882
0x18001b7be  cmp     [rcx+10h], r12b
0x18001b7c2  jnz     short loc_18001B7DE
0x18001b7c4  mov     rdx, [rcx]
0x18001b7c7  add     rdx, r8; char *
0x18001b7ca  cmp     rdx, r8
0x18001b7cd  jb      short loc_18001B836
0x18001b7cf  cmp     rdx, 0FFFFFFFFFFFF0000h
0x18001b7d6  ja      short loc_18001B81A
0x18001b7d8  mov     r9b, 1
0x18001b7db  mov     r8, rdx
0x18001b7de  add     rcx, 18h
0x18001b7e2  cmp     rcx, r10
0x18001b7e5  jnz     short loc_18001B7BE
0x18001b7e7  test    r9b, r9b
0x18001b7ea  jz      loc_18001B882
0x18001b7f0  mov     rdx, r8
0x18001b7f3  lea     rcx, [rsp+78h+var_58]
0x18001b7f8  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18001b7fd  mov     rax, [r14]
0x18001b800  mov     rdi, [r14+8]
0x18001b804  mov     r15, [rsp+78h+var_50]
0x18001b809  mov     rbp, [rbp+8]
0x18001b80d  mov     rsi, r15
0x18001b810  lea     rcx, [rax+rax*2]
0x18001b814  lea     r14, [rdi+rcx*8]
0x18001b818  jmp     short loc_18001B868
0x18001b81a  lea     rcx, aNewtotallength_0; "newTotalLength <= MessageLimit"
0x18001b821  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001b826  mov     [rbx], r12
0x18001b829  mov     [rbx+8], r12
0x18001b82d  mov     dword ptr [rbx+10h], 0C0000095h
0x18001b834  jmp     short loc_18001B88D
0x18001b836  lea     rcx, aNewtotallength; "newTotalLength >= totalLength"
0x18001b83d  jmp     short loc_18001B821
0x18001b83f  mov     rcx, rsi; void *
0x18001b842  mov     r8, [rdi]; Size
0x18001b845  cmp     [rdi+10h], r12b
0x18001b849  jz      short loc_18001B858
0x18001b84b  mov     rdx, rbp; Src
0x18001b84e  call    memcpy_0
0x18001b853  add     rbp, [rdi]
0x18001b856  jmp     short loc_18001B861
0x18001b858  mov     rdx, [rdi+8]; Src
0x18001b85c  call    memcpy_0
0x18001b861  add     rsi, [rdi]
0x18001b864  add     rdi, 18h
0x18001b868  cmp     rdi, r14
0x18001b86b  jnz     short loc_18001B83F
0x18001b86d  mov     eax, [rsp+78h+var_48]
0x18001b871  mov     [rbx+10h], eax
0x18001b874  mov     rax, [rsp+78h+var_58]
0x18001b879  mov     [rbx], rax
0x18001b87c  mov     [rbx+8], r15
0x18001b880  jmp     short loc_18001B88D
0x18001b882  mov     [rbx], r12
0x18001b885  mov     [rbx+8], r12
0x18001b889  mov     [rbx+10h], r12d
0x18001b88d  mov     rax, rbx
0x18001b890  add     rsp, 40h
0x18001b894  pop     r15
0x18001b896  pop     r14
0x18001b898  pop     r12
0x18001b89a  pop     rdi
0x18001b89b  pop     rsi
0x18001b89c  pop     rbp
0x18001b89d  pop     rbx
0x18001b89e  retn
```
