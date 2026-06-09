# Kerb3961::SSPICipherSuite<1,1,2>::InterleaveDecryptionAndIntegrity(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800059e4`
- end: `0x180005b14`
- name: `?InterleaveDecryptionAndIntegrity@?$SSPICipherSuite@$00$00$01@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006b30`

## callees

- `0x1800059e4`
- `0x180005b1c`
- `0x180011760`
- `0x180012300`

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
  *(_DWORD *)(a1 + 16) = v21;
  *(_QWORD *)a1 = v19;
  *(_QWORD *)(a1 + 8) = v12;
  return a1;
}

```

## disassembly

```asm
0x1800059e4  push    rbx
0x1800059e6  push    rbp
0x1800059e7  push    rsi
0x1800059e8  push    rdi
0x1800059e9  push    r12
0x1800059eb  push    r14
0x1800059ed  push    r15
0x1800059ef  sub     rsp, 40h
0x1800059f3  mov     rax, [rdx]
0x1800059f6  xor     r12d, r12d
0x1800059f9  mov     rbp, r8
0x1800059fc  mov     r14, rdx
0x1800059ff  mov     rbx, rcx
0x180005a02  test    rax, rax
0x180005a05  jnz     short loc_180005A17
0x180005a07  mov     [rcx], r12
0x180005a0a  mov     [rcx+8], r12
0x180005a0e  mov     [rcx+10h], r12d
0x180005a12  jmp     loc_180005B01
0x180005a17  mov     rcx, [rdx+8]
0x180005a1b  lea     rax, [rax+rax*2]
0x180005a1f  mov     r8, [r8]
0x180005a22  mov     r9b, r12b
0x180005a25  lea     r10, [rcx+rax*8]
0x180005a29  cmp     rcx, r10
0x180005a2c  jz      loc_180005AF6
0x180005a32  cmp     [rcx+10h], r12b
0x180005a36  jnz     short loc_180005A52
0x180005a38  mov     rdx, [rcx]
0x180005a3b  add     rdx, r8; char *
0x180005a3e  cmp     rdx, r8
0x180005a41  jb      short loc_180005AAA
0x180005a43  cmp     rdx, 0FFFFFFFFFFFF0000h
0x180005a4a  ja      short loc_180005A8E
0x180005a4c  mov     r9b, 1
0x180005a4f  mov     r8, rdx
0x180005a52  add     rcx, 18h
0x180005a56  cmp     rcx, r10
0x180005a59  jnz     short loc_180005A32
0x180005a5b  test    r9b, r9b
0x180005a5e  jz      loc_180005AF6
0x180005a64  mov     rdx, r8
0x180005a67  lea     rcx, [rsp+78h+var_58]
0x180005a6c  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180005a71  mov     rax, [r14]
0x180005a74  mov     rdi, [r14+8]
0x180005a78  mov     r15, [rsp+78h+var_50]
0x180005a7d  mov     rbp, [rbp+8]
0x180005a81  mov     rsi, r15
0x180005a84  lea     rcx, [rax+rax*2]
0x180005a88  lea     r14, [rdi+rcx*8]
0x180005a8c  jmp     short loc_180005ADC
0x180005a8e  lea     rcx, aNewtotallength_0; "newTotalLength <= MessageLimit"
0x180005a95  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180005a9a  mov     [rbx], r12
0x180005a9d  mov     [rbx+8], r12
0x180005aa1  mov     dword ptr [rbx+10h], 0C0000095h
0x180005aa8  jmp     short loc_180005B01
0x180005aaa  lea     rcx, aNewtotallength; "newTotalLength >= totalLength"
0x180005ab1  jmp     short loc_180005A95
0x180005ab3  mov     rcx, rsi; void *
0x180005ab6  mov     r8, [rdi]; Size
0x180005ab9  cmp     [rdi+10h], r12b
0x180005abd  jz      short loc_180005ACC
0x180005abf  mov     rdx, rbp; Src
0x180005ac2  call    memmove
0x180005ac7  add     rbp, [rdi]
0x180005aca  jmp     short loc_180005AD5
0x180005acc  mov     rdx, [rdi+8]; Src
0x180005ad0  call    memmove
0x180005ad5  add     rsi, [rdi]
0x180005ad8  add     rdi, 18h
0x180005adc  cmp     rdi, r14
0x180005adf  jnz     short loc_180005AB3
0x180005ae1  mov     eax, [rsp+78h+var_48]
0x180005ae5  mov     [rbx+10h], eax
0x180005ae8  mov     rax, [rsp+78h+var_58]
0x180005aed  mov     [rbx], rax
0x180005af0  mov     [rbx+8], r15
0x180005af4  jmp     short loc_180005B01
0x180005af6  mov     [rbx], r12
0x180005af9  mov     [rbx+8], r12
0x180005afd  mov     [rbx+10h], r12d
0x180005b01  mov     rax, rbx
0x180005b04  add     rsp, 40h
0x180005b08  pop     r15
0x180005b0a  pop     r14
0x180005b0c  pop     r12
0x180005b0e  pop     rdi
0x180005b0f  pop     rsi
0x180005b10  pop     rbp
0x180005b11  pop     rbx
0x180005b12  retn
```
