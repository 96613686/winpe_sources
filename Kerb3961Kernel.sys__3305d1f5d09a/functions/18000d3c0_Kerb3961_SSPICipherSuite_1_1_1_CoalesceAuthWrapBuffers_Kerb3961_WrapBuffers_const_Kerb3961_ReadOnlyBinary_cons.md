# Kerb3961::SSPICipherSuite<1,1,1>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000d3c0`
- end: `0x18000d56b`
- name: `?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$00@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z`
- size: `427`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180010760`
- `0x180010bd0`

## callees

- `0x180003a38`
- `0x180005b1c`
- `0x18000d3c0`
- `0x180011760`
- `0x180011b40`
- `0x180012300`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,1>::CoalesceAuthWrapBuffers(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v7; // rcx
  const char *v8; // rdx
  char v9; // r9
  __int64 v10; // r10
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // rax
  const char *v13; // rdx
  int v14; // r15d
  __int64 v15; // rsi
  char *v16; // rbp
  char *v17; // rdi
  __int64 v18; // r12
  char *v19; // rcx
  __int64 v20; // rcx
  void *v21; // rcx
  __int64 v23; // [rsp+20h] [rbp-68h] BYREF
  void *v24; // [rsp+28h] [rbp-60h]
  __int64 v25; // [rsp+30h] [rbp-58h]

  if ( !*a3 )
  {
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = 0;
    return a2;
  }
  v7 = a3[1];
  v8 = 0;
  v9 = 0;
  v10 = v7 + 24LL * *a3;
  while ( v7 != v10 )
  {
    if ( !*(_BYTE *)(v7 + 16) )
      v9 = 1;
    v11 = (unsigned __int64)&v8[*(_QWORD *)v7];
    if ( v11 < (unsigned __int64)v8 )
      goto LABEL_20;
    if ( v11 > 0xFFFFFFFFFFFF0000uLL )
      goto LABEL_18;
    v8 += *(_QWORD *)v7;
    v7 += 24;
  }
  if ( *(_QWORD *)a4 )
  {
    v12 = (unsigned __int64)&v8[*(_QWORD *)a4];
    if ( v12 < (unsigned __int64)v8 )
    {
LABEL_20:
      v19 = "newTotalLength >= totalLength";
    }
    else
    {
      if ( v12 <= 0xFFFFFFFFFFFF0000uLL )
      {
        v8 += *(_QWORD *)a4;
        goto LABEL_14;
      }
LABEL_18:
      v19 = "newTotalLength <= MessageLimit";
    }
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v19, v8);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
    return a2;
  }
LABEL_14:
  if ( v9 && v8 )
  {
    Kerb3961::MakeBuffer(&v23);
    v14 = v25;
    if ( (int)v25 < 0 )
    {
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"result", v13);
      v21 = v24;
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -1073741801;
      if ( v21 )
        Kerb3961Free(v21);
    }
    else
    {
      v15 = a3[1];
      v16 = (char *)v24;
      v17 = (char *)v24;
      v18 = v15 + 24LL * *a3;
      while ( v15 != v18 )
      {
        memmove(v17, *(const void **)(v15 + 8), *(_QWORD *)v15);
        v17 += *(_QWORD *)v15;
        v15 += 24;
      }
      if ( *(_QWORD *)a4 )
      {
        memmove(v17, *(const void **)(a4 + 8), *(_QWORD *)a4);
        v17 += *(_QWORD *)a4;
      }
      v20 = v23;
      if ( v17 != &v16[v23] )
        Kerb3961::ConsistencyFail(
          (Kerb3961 *)L"Incorrect total length for coalescing auth buffers",
          (const unsigned __int16 *)v13);
      *(_DWORD *)(a2 + 16) = v14;
      *(_QWORD *)a2 = v20;
      *(_QWORD *)(a2 + 8) = v16;
    }
  }
  else
  {
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18000d3c0  push    rbx
0x18000d3c2  push    rbp
0x18000d3c3  push    rsi
0x18000d3c4  push    rdi
0x18000d3c5  push    r12
0x18000d3c7  push    r13
0x18000d3c9  push    r14
0x18000d3cb  push    r15
0x18000d3cd  sub     rsp, 48h
0x18000d3d1  mov     rax, [r8]
0x18000d3d4  xor     r13d, r13d
0x18000d3d7  mov     r14, r9
0x18000d3da  mov     r12, r8
0x18000d3dd  mov     rbx, rdx
0x18000d3e0  test    rax, rax
0x18000d3e3  jnz     short loc_18000D3F5
0x18000d3e5  mov     [rdx], r13
0x18000d3e8  mov     [rdx+8], r13
0x18000d3ec  mov     [rdx+10h], r13d
0x18000d3f0  jmp     loc_18000D549
0x18000d3f5  mov     rcx, [r8+8]
0x18000d3f9  lea     rax, [rax+rax*2]
0x18000d3fd  mov     rdx, r13
0x18000d400  mov     r9b, r13b
0x18000d403  mov     r11, 0FFFFFFFFFFFF0000h
0x18000d40a  lea     r10, [rcx+rax*8]
0x18000d40e  jmp     short loc_18000D43C
0x18000d410  cmp     [rcx+10h], r13b
0x18000d414  mov     eax, 1
0x18000d419  mov     r8, [rcx]
0x18000d41c  movzx   r9d, r9b
0x18000d420  cmovz   r9d, eax
0x18000d424  add     r8, rdx
0x18000d427  cmp     r8, rdx
0x18000d42a  jb      loc_18000D4BD
0x18000d430  cmp     r8, r11
0x18000d433  ja      short loc_18000D49E
0x18000d435  mov     rdx, r8; char *
0x18000d438  add     rcx, 18h
0x18000d43c  cmp     rcx, r10
0x18000d43f  jnz     short loc_18000D410
0x18000d441  mov     rax, [r14]
0x18000d444  test    rax, rax
0x18000d447  jz      short loc_18000D459
0x18000d449  add     rax, rdx
0x18000d44c  cmp     rax, rdx
0x18000d44f  jb      short loc_18000D4BD
0x18000d451  cmp     rax, r11
0x18000d454  ja      short loc_18000D49E
0x18000d456  mov     rdx, rax
0x18000d459  test    r9b, r9b
0x18000d45c  jz      loc_18000D53E
0x18000d462  test    rdx, rdx
0x18000d465  jz      loc_18000D53E
0x18000d46b  lea     rcx, [rsp+88h+var_68]
0x18000d470  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000d475  mov     r15, [rsp+88h+var_58]
0x18000d47a  test    r15d, r15d
0x18000d47d  js      loc_18000D513
0x18000d483  mov     rax, [r12]
0x18000d487  mov     rsi, [r12+8]
0x18000d48c  mov     rbp, [rsp+88h+var_60]
0x18000d491  mov     rdi, rbp
0x18000d494  lea     rcx, [rax+rax*2]
0x18000d498  lea     r12, [rsi+rcx*8]
0x18000d49c  jmp     short loc_18000D4DC
0x18000d49e  lea     rcx, aNewtotallength_0; "newTotalLength <= MessageLimit"
0x18000d4a5  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000d4aa  mov     [rbx], r13
0x18000d4ad  mov     [rbx+8], r13
0x18000d4b1  mov     dword ptr [rbx+10h], 0C0000095h
0x18000d4b8  jmp     loc_18000D549
0x18000d4bd  lea     rcx, aNewtotallength; "newTotalLength >= totalLength"
0x18000d4c4  jmp     short loc_18000D4A5
0x18000d4c6  mov     r8, [rsi]; Size
0x18000d4c9  mov     rcx, rdi; void *
0x18000d4cc  mov     rdx, [rsi+8]; Src
0x18000d4d0  call    memmove
0x18000d4d5  add     rdi, [rsi]
0x18000d4d8  add     rsi, 18h
0x18000d4dc  cmp     rsi, r12
0x18000d4df  jnz     short loc_18000D4C6
0x18000d4e1  mov     r8, [r14]; Size
0x18000d4e4  test    r8, r8
0x18000d4e7  jz      short loc_18000D4F8
0x18000d4e9  mov     rdx, [r14+8]; Src
0x18000d4ed  mov     rcx, rdi; void *
0x18000d4f0  call    memmove
0x18000d4f5  add     rdi, [r14]
0x18000d4f8  mov     rcx, [rsp+88h+var_68]
0x18000d4fd  lea     rax, [rcx+rbp]
0x18000d501  cmp     rdi, rax
0x18000d504  jnz     short loc_18000D55E
0x18000d506  mov     [rbx+10h], r15d
0x18000d50a  mov     [rbx], rcx
0x18000d50d  mov     [rbx+8], rbp
0x18000d511  jmp     short loc_18000D549
0x18000d513  lea     rcx, aResult; "result"
0x18000d51a  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000d51f  mov     rcx, [rsp+88h+var_60]
0x18000d524  mov     [rbx], r13
0x18000d527  mov     [rbx+8], r13
0x18000d52b  mov     dword ptr [rbx+10h], 0C0000017h
0x18000d532  test    rcx, rcx
0x18000d535  jz      short loc_18000D549
0x18000d537  call    Kerb3961Free
0x18000d53c  jmp     short loc_18000D549
0x18000d53e  mov     [rbx], r13
0x18000d541  mov     [rbx+8], r13
0x18000d545  mov     [rbx+10h], r13d
0x18000d549  mov     rax, rbx
0x18000d54c  add     rsp, 48h
0x18000d550  pop     r15
0x18000d552  pop     r14
0x18000d554  pop     r13
0x18000d556  pop     r12
0x18000d558  pop     rdi
0x18000d559  pop     rsi
0x18000d55a  pop     rbp
0x18000d55b  pop     rbx
0x18000d55c  retn
0x18000d55e  lea     rcx, aIncorrectTotal; "Incorrect total length for coalescing a"...
0x18000d565  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
