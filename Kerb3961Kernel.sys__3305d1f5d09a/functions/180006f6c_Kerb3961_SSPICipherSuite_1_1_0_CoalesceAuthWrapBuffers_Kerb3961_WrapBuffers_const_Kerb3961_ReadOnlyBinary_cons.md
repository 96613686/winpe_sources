# Kerb3961::SSPICipherSuite<1,1,0>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180006f6c`
- end: `0x1800070d6`
- name: `?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z`
- size: `362`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180009040`
- `0x180009300`

## callees

- `0x180003a38`
- `0x180005b1c`
- `0x180006f6c`
- `0x180011760`
- `0x180011b40`
- `0x180012300`

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
      Kerb3961Free(v18);
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
        memmove(v14, *(const void **)(v12 + 8), *(_QWORD *)v12);
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
0x180006f6c  push    rbx
0x180006f6e  push    rbp
0x180006f6f  push    rsi
0x180006f70  push    rdi
0x180006f71  push    r12
0x180006f73  push    r14
0x180006f75  push    r15
0x180006f77  sub     rsp, 40h
0x180006f7b  mov     rax, [r8]
0x180006f7e  xor     r12d, r12d
0x180006f81  mov     r15, r8
0x180006f84  mov     rbx, rdx
0x180006f87  test    rax, rax
0x180006f8a  jnz     short loc_180006F9C
0x180006f8c  mov     [rdx], r12
0x180006f8f  mov     [rdx+8], r12
0x180006f93  mov     [rdx+10h], r12d
0x180006f97  jmp     loc_1800070B6
0x180006f9c  mov     rcx, [r8+8]
0x180006fa0  lea     rax, [rax+rax*2]
0x180006fa4  mov     rdx, r12; char *
0x180006fa7  mov     r9b, r12b
0x180006faa  lea     r10, [rcx+rax*8]
0x180006fae  cmp     rcx, r10
0x180006fb1  jz      loc_1800070AB
0x180006fb7  cmp     [rcx+10h], r12b
0x180006fbb  jnz     short loc_180006FD7
0x180006fbd  mov     r8, [rcx]
0x180006fc0  add     r8, rdx
0x180006fc3  cmp     r8, rdx
0x180006fc6  jb      short loc_18000703B
0x180006fc8  cmp     r8, 0FFFFFFFFFFFF0000h
0x180006fcf  ja      short loc_18000701F
0x180006fd1  mov     r9b, 1
0x180006fd4  mov     rdx, r8
0x180006fd7  add     rcx, 18h
0x180006fdb  cmp     rcx, r10
0x180006fde  jnz     short loc_180006FB7
0x180006fe0  test    r9b, r9b
0x180006fe3  jz      loc_1800070AB
0x180006fe9  test    rdx, rdx
0x180006fec  jz      loc_1800070AB
0x180006ff2  lea     rcx, [rsp+78h+var_58]
0x180006ff7  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180006ffc  mov     r14, [rsp+78h+var_48]
0x180007001  test    r14d, r14d
0x180007004  js      short loc_180007080
0x180007006  mov     rax, [r15]
0x180007009  mov     rdi, [r15+8]
0x18000700d  mov     rbp, [rsp+78h+var_50]
0x180007012  mov     rsi, rbp
0x180007015  lea     rcx, [rax+rax*2]
0x180007019  lea     r15, [rdi+rcx*8]
0x18000701d  jmp     short loc_180007060
0x18000701f  lea     rcx, aNewtotallength_0; "newTotalLength <= MessageLimit"
0x180007026  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000702b  mov     [rbx], r12
0x18000702e  mov     [rbx+8], r12
0x180007032  mov     dword ptr [rbx+10h], 0C0000095h
0x180007039  jmp     short loc_1800070B6
0x18000703b  lea     rcx, aNewtotallength; "newTotalLength >= totalLength"
0x180007042  jmp     short loc_180007026
0x180007044  cmp     [rdi+10h], r12b
0x180007048  jnz     short loc_18000705C
0x18000704a  mov     r8, [rdi]; Size
0x18000704d  mov     rcx, rsi; void *
0x180007050  mov     rdx, [rdi+8]; Src
0x180007054  call    memmove
0x180007059  add     rsi, [rdi]
0x18000705c  add     rdi, 18h
0x180007060  cmp     rdi, r15
0x180007063  jnz     short loc_180007044
0x180007065  mov     rcx, [rsp+78h+var_58]
0x18000706a  lea     rax, [rcx+rbp]
0x18000706e  cmp     rsi, rax
0x180007071  jnz     short loc_1800070C9
0x180007073  mov     [rbx+10h], r14d
0x180007077  mov     [rbx], rcx
0x18000707a  mov     [rbx+8], rbp
0x18000707e  jmp     short loc_1800070B6
0x180007080  lea     rcx, aResult; "result"
0x180007087  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000708c  mov     rcx, [rsp+78h+var_50]
0x180007091  mov     [rbx], r12
0x180007094  mov     [rbx+8], r12
0x180007098  mov     dword ptr [rbx+10h], 0C0000017h
0x18000709f  test    rcx, rcx
0x1800070a2  jz      short loc_1800070B6
0x1800070a4  call    Kerb3961Free
0x1800070a9  jmp     short loc_1800070B6
0x1800070ab  mov     [rbx], r12
0x1800070ae  mov     [rbx+8], r12
0x1800070b2  mov     [rbx+10h], r12d
0x1800070b6  mov     rax, rbx
0x1800070b9  add     rsp, 40h
0x1800070bd  pop     r15
0x1800070bf  pop     r14
0x1800070c1  pop     r12
0x1800070c3  pop     rdi
0x1800070c4  pop     rsi
0x1800070c5  pop     rbp
0x1800070c6  pop     rbx
0x1800070c7  retn
0x1800070c9  lea     rcx, aIncorrectTotal; "Incorrect total length for coalescing a"...
0x1800070d0  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
