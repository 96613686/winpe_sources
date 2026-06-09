# Kerb3961::SSPICipherSuite<1,1,2>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800190d0`
- end: `0x180019240`
- name: `?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$01@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z`
- size: `368`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001bec0`
- `0x18001c5d0`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x1800033f4`
- `0x18000901c`
- `0x1800190d0`
- `0x18001d360`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,2>::CoalesceAuthWrapBuffers(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rax
  const char *v7; // r9
  char v8; // r8
  __int64 v9; // r10
  const char *v10; // rdx
  const char *v11; // rdx
  int v12; // r15d
  __int64 v13; // rdi
  char *v14; // rbp
  char *v15; // rsi
  __int64 v16; // r14
  __int64 v17; // rcx
  void *v18; // rcx
  char *v19; // rcx
  __int64 v21; // [rsp+20h] [rbp-58h] BYREF
  void *v22; // [rsp+28h] [rbp-50h]
  __int64 v23; // [rsp+30h] [rbp-48h]

  if ( !*a3 )
  {
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = 0;
    return a2;
  }
  v5 = a3[1];
  v6 = 3LL * *a3;
  v7 = 0;
  v8 = 0;
  v9 = v5 + 8 * v6;
  if ( v5 == v9 )
  {
LABEL_23:
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = 0;
    return a2;
  }
  while ( 1 )
  {
    if ( !*(_BYTE *)(v5 + 16) )
      v8 = 1;
    v10 = &v7[*(_QWORD *)v5];
    if ( v10 < v7 )
    {
      v19 = "newTotalLength >= totalLength";
      goto LABEL_21;
    }
    if ( (unsigned __int64)v10 > 0xFFFFFFFFFFFF0000uLL )
    {
      v19 = "newTotalLength <= MessageLimit";
LABEL_21:
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v19, v10);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -1073741675;
      return a2;
    }
    v5 += 24;
    if ( v5 == v9 )
      break;
    v7 = v10;
  }
  if ( !v8 || !v10 )
    goto LABEL_23;
  Kerb3961::MakeBuffer(&v21);
  v12 = v23;
  if ( (int)v23 < 0 )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"result", v11);
    v18 = v22;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741801;
    if ( v18 )
      operator delete(v18, 0);
  }
  else
  {
    v13 = a3[1];
    v14 = (char *)v22;
    v15 = (char *)v22;
    v16 = v13 + 24LL * *a3;
    while ( v13 != v16 )
    {
      memcpy_0(v15, *(const void **)(v13 + 8), *(_QWORD *)v13);
      v15 += *(_QWORD *)v13;
      v13 += 24;
    }
    v17 = v21;
    if ( v15 != &v14[v21] )
      Kerb3961::ConsistencyFail(
        (Kerb3961 *)L"Incorrect total length for coalescing auth buffers",
        (const unsigned __int16 *)v11);
    *(_DWORD *)(a2 + 16) = v12;
    *(_QWORD *)a2 = v17;
    *(_QWORD *)(a2 + 8) = v14;
  }
  return a2;
}

```

## disassembly

```asm
0x1800190d0  push    rbx
0x1800190d2  push    rbp
0x1800190d3  push    rsi
0x1800190d4  push    rdi
0x1800190d5  push    r14
0x1800190d7  push    r15
0x1800190d9  sub     rsp, 48h
0x1800190dd  mov     rax, [r8]
0x1800190e0  xor     edi, edi
0x1800190e2  mov     r14, r8
0x1800190e5  mov     rbx, rdx
0x1800190e8  test    rax, rax
0x1800190eb  jnz     short loc_1800190FC
0x1800190ed  mov     [rdx], rdi
0x1800190f0  mov     [rdx+8], rdi
0x1800190f4  mov     [rdx+10h], edi
0x1800190f7  jmp     loc_180019223
0x1800190fc  mov     rcx, [r14+8]
0x180019100  lea     rax, [rax+rax*2]
0x180019104  mov     r9, rdi
0x180019107  mov     r8b, dil
0x18001910a  lea     r10, [rcx+rax*8]
0x18001910e  cmp     rcx, r10
0x180019111  jz      loc_180019219
0x180019117  cmp     [rcx+10h], dil
0x18001911b  mov     eax, 1
0x180019120  mov     rdx, [rcx]
0x180019123  movzx   r8d, r8b
0x180019127  cmovz   r8d, eax
0x18001912b  add     rdx, r9; char *
0x18001912e  cmp     rdx, r9
0x180019131  jb      loc_180019210
0x180019137  cmp     rdx, 0FFFFFFFFFFFF0000h
0x18001913e  ja      loc_1800191F4
0x180019144  add     rcx, 18h
0x180019148  cmp     rcx, r10
0x18001914b  jz      short loc_180019152
0x18001914d  mov     r9, rdx
0x180019150  jmp     short loc_180019117
0x180019152  test    r8b, r8b
0x180019155  jz      loc_180019219
0x18001915b  test    rdx, rdx
0x18001915e  jz      loc_180019219
0x180019164  lea     rcx, [rsp+78h+var_58]
0x180019169  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18001916e  mov     r15, [rsp+78h+var_48]
0x180019173  test    r15d, r15d
0x180019176  js      short loc_1800191C7
0x180019178  mov     rax, [r14]
0x18001917b  mov     rdi, [r14+8]
0x18001917f  mov     rbp, [rsp+78h+var_50]
0x180019184  mov     rsi, rbp
0x180019187  lea     rcx, [rax+rax*2]
0x18001918b  lea     r14, [rdi+rcx*8]
0x18001918f  jmp     short loc_1800191A7
0x180019191  mov     r8, [rdi]; Size
0x180019194  mov     rcx, rsi; void *
0x180019197  mov     rdx, [rdi+8]; Src
0x18001919b  call    memcpy_0
0x1800191a0  add     rsi, [rdi]
0x1800191a3  add     rdi, 18h
0x1800191a7  cmp     rdi, r14
0x1800191aa  jnz     short loc_180019191
0x1800191ac  mov     rcx, [rsp+78h+var_58]
0x1800191b1  lea     rax, [rcx+rbp]
0x1800191b5  cmp     rsi, rax
0x1800191b8  jnz     short loc_180019233
0x1800191ba  mov     [rbx+10h], r15d
0x1800191be  mov     [rbx], rcx
0x1800191c1  mov     [rbx+8], rbp
0x1800191c5  jmp     short loc_180019223
0x1800191c7  lea     rcx, aResult; "result"
0x1800191ce  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800191d3  mov     rcx, [rsp+78h+var_50]; void *
0x1800191d8  mov     [rbx], rdi
0x1800191db  mov     [rbx+8], rdi
0x1800191df  mov     dword ptr [rbx+10h], 0C0000017h
0x1800191e6  test    rcx, rcx
0x1800191e9  jz      short loc_180019223
0x1800191eb  xor     edx, edx; struct std::nothrow_t *
0x1800191ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800191f2  jmp     short loc_180019223
0x1800191f4  lea     rcx, aNewtotallength_0; "newTotalLength <= MessageLimit"
0x1800191fb  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180019200  mov     [rbx], rdi
0x180019203  mov     [rbx+8], rdi
0x180019207  mov     dword ptr [rbx+10h], 0C0000095h
0x18001920e  jmp     short loc_180019223
0x180019210  lea     rcx, aNewtotallength; "newTotalLength >= totalLength"
0x180019217  jmp     short loc_1800191FB
0x180019219  mov     [rbx], rdi
0x18001921c  mov     [rbx+8], rdi
0x180019220  mov     [rbx+10h], edi
0x180019223  mov     rax, rbx
0x180019226  add     rsp, 48h
0x18001922a  pop     r15
0x18001922c  pop     r14
0x18001922e  pop     rdi
0x18001922f  pop     rsi
0x180019230  pop     rbp
0x180019231  pop     rbx
0x180019232  retn
0x180019233  lea     rcx, aIncorrectTotal; "Incorrect total length for coalescing a"...
0x18001923a  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
