# Kerb3961::SSPICipherSuite<1,1,0>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180010f4c`
- end: `0x1800110b7`
- name: `?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z`
- size: `363`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800166e0`
- `0x1800169b0`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x1800033f4`
- `0x18000901c`
- `0x180010f4c`
- `0x18001d360`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,0>::CoalesceAuthWrapBuffers(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rcx
  const char *v6; // rdx
  char v7; // r9
  __int64 v8; // r10
  unsigned __int64 v9; // r8
  const char *v10; // rdx
  int v11; // r14d
  __int64 v12; // rdi
  char *v13; // rbp
  char *v14; // rsi
  __int64 v15; // r15
  char *v16; // rcx
  __int64 v17; // rcx
  void *v18; // rcx
  __int64 v20; // [rsp+20h] [rbp-58h] BYREF
  void *v21; // [rsp+28h] [rbp-50h]
  __int64 v22; // [rsp+30h] [rbp-48h]

  if ( !*a3 )
  {
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = 0;
    return a2;
  }
  v5 = a3[1];
  v6 = 0;
  v7 = 0;
  v8 = v5 + 24LL * *a3;
  if ( v5 == v8 )
  {
LABEL_24:
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = 0;
    return a2;
  }
  do
  {
    if ( *(_BYTE *)(v5 + 16) )
      goto LABEL_8;
    v9 = (unsigned __int64)&v6[*(_QWORD *)v5];
    if ( v9 < (unsigned __int64)v6 )
    {
      v16 = "newTotalLength >= totalLength";
      goto LABEL_14;
    }
    if ( v9 > 0xFFFFFFFFFFFF0000uLL )
    {
      v16 = "newTotalLength <= MessageLimit";
LABEL_14:
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v16, v6);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -1073741675;
      return a2;
    }
    v7 = 1;
    v6 += *(_QWORD *)v5;
LABEL_8:
    v5 += 24;
  }
  while ( v5 != v8 );
  if ( !v7 || !v6 )
    goto LABEL_24;
  Kerb3961::MakeBuffer(&v20);
  v11 = v22;
  if ( (int)v22 < 0 )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"result", v10);
    v18 = v21;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741801;
    if ( v18 )
      operator delete(v18, 0);
  }
  else
  {
    v12 = a3[1];
    v13 = (char *)v21;
    v14 = (char *)v21;
    v15 = v12 + 24LL * *a3;
    while ( v12 != v15 )
    {
      if ( !*(_BYTE *)(v12 + 16) )
      {
        memcpy_0(v14, *(const void **)(v12 + 8), *(_QWORD *)v12);
        v14 += *(_QWORD *)v12;
      }
      v12 += 24;
    }
    v17 = v20;
    if ( v14 != &v13[v20] )
      Kerb3961::ConsistencyFail(
        (Kerb3961 *)L"Incorrect total length for coalescing auth buffers",
        (const unsigned __int16 *)v10);
    *(_DWORD *)(a2 + 16) = v11;
    *(_QWORD *)a2 = v17;
    *(_QWORD *)(a2 + 8) = v13;
  }
  return a2;
}

```

## disassembly

```asm
0x180010f4c  push    rbx
0x180010f4e  push    rbp
0x180010f4f  push    rsi
0x180010f50  push    rdi
0x180010f51  push    r12
0x180010f53  push    r14
0x180010f55  push    r15
0x180010f57  sub     rsp, 40h
0x180010f5b  mov     rax, [r8]
0x180010f5e  xor     r12d, r12d
0x180010f61  mov     r15, r8
0x180010f64  mov     rbx, rdx
0x180010f67  test    rax, rax
0x180010f6a  jnz     short loc_180010F7C
0x180010f6c  mov     [rdx], r12
0x180010f6f  mov     [rdx+8], r12
0x180010f73  mov     [rdx+10h], r12d
0x180010f77  jmp     loc_180011098
0x180010f7c  mov     rcx, [r8+8]
0x180010f80  lea     rax, [rax+rax*2]
0x180010f84  mov     rdx, r12; char *
0x180010f87  mov     r9b, r12b
0x180010f8a  lea     r10, [rcx+rax*8]
0x180010f8e  cmp     rcx, r10
0x180010f91  jz      loc_18001108D
0x180010f97  cmp     [rcx+10h], r12b
0x180010f9b  jnz     short loc_180010FB7
0x180010f9d  mov     r8, [rcx]
0x180010fa0  add     r8, rdx
0x180010fa3  cmp     r8, rdx
0x180010fa6  jb      short loc_18001101B
0x180010fa8  cmp     r8, 0FFFFFFFFFFFF0000h
0x180010faf  ja      short loc_180010FFF
0x180010fb1  mov     r9b, 1
0x180010fb4  mov     rdx, r8
0x180010fb7  add     rcx, 18h
0x180010fbb  cmp     rcx, r10
0x180010fbe  jnz     short loc_180010F97
0x180010fc0  test    r9b, r9b
0x180010fc3  jz      loc_18001108D
0x180010fc9  test    rdx, rdx
0x180010fcc  jz      loc_18001108D
0x180010fd2  lea     rcx, [rsp+78h+var_58]
0x180010fd7  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180010fdc  mov     r14, [rsp+78h+var_48]
0x180010fe1  test    r14d, r14d
0x180010fe4  js      short loc_180011060
0x180010fe6  mov     rax, [r15]
0x180010fe9  mov     rdi, [r15+8]
0x180010fed  mov     rbp, [rsp+78h+var_50]
0x180010ff2  mov     rsi, rbp
0x180010ff5  lea     rcx, [rax+rax*2]
0x180010ff9  lea     r15, [rdi+rcx*8]
0x180010ffd  jmp     short loc_180011040
0x180010fff  lea     rcx, aNewtotallength_0; "newTotalLength <= MessageLimit"
0x180011006  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001100b  mov     [rbx], r12
0x18001100e  mov     [rbx+8], r12
0x180011012  mov     dword ptr [rbx+10h], 0C0000095h
0x180011019  jmp     short loc_180011098
0x18001101b  lea     rcx, aNewtotallength; "newTotalLength >= totalLength"
0x180011022  jmp     short loc_180011006
0x180011024  cmp     [rdi+10h], r12b
0x180011028  jnz     short loc_18001103C
0x18001102a  mov     r8, [rdi]; Size
0x18001102d  mov     rcx, rsi; void *
0x180011030  mov     rdx, [rdi+8]; Src
0x180011034  call    memcpy_0
0x180011039  add     rsi, [rdi]
0x18001103c  add     rdi, 18h
0x180011040  cmp     rdi, r15
0x180011043  jnz     short loc_180011024
0x180011045  mov     rcx, [rsp+78h+var_58]
0x18001104a  lea     rax, [rcx+rbp]
0x18001104e  cmp     rsi, rax
0x180011051  jnz     short loc_1800110AA
0x180011053  mov     [rbx+10h], r14d
0x180011057  mov     [rbx], rcx
0x18001105a  mov     [rbx+8], rbp
0x18001105e  jmp     short loc_180011098
0x180011060  lea     rcx, aResult; "result"
0x180011067  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001106c  mov     rcx, [rsp+78h+var_50]; void *
0x180011071  mov     [rbx], r12
0x180011074  mov     [rbx+8], r12
0x180011078  mov     dword ptr [rbx+10h], 0C0000017h
0x18001107f  test    rcx, rcx
0x180011082  jz      short loc_180011098
0x180011084  xor     edx, edx; struct std::nothrow_t *
0x180011086  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001108b  jmp     short loc_180011098
0x18001108d  mov     [rbx], r12
0x180011090  mov     [rbx+8], r12
0x180011094  mov     [rbx+10h], r12d
0x180011098  mov     rax, rbx
0x18001109b  add     rsp, 40h
0x18001109f  pop     r15
0x1800110a1  pop     r14
0x1800110a3  pop     r12
0x1800110a5  pop     rdi
0x1800110a6  pop     rsi
0x1800110a7  pop     rbp
0x1800110a8  pop     rbx
0x1800110a9  retn
0x1800110aa  lea     rcx, aIncorrectTotal; "Incorrect total length for coalescing a"...
0x1800110b1  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
