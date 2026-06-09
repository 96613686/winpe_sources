# Kerb3961::SSPICipherSuite<1,1,1>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180004b40`
- end: `0x180004cec`
- name: `?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$00@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z`
- size: `428`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800099c0`
- `0x18000a090`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x1800033f4`
- `0x180004b40`
- `0x18000901c`
- `0x18001d360`

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
        operator delete(v21, 0);
    }
    else
    {
      v15 = a3[1];
      v16 = (char *)v24;
      v17 = (char *)v24;
      v18 = v15 + 24LL * *a3;
      while ( v15 != v18 )
      {
        memcpy_0(v17, *(const void **)(v15 + 8), *(_QWORD *)v15);
        v17 += *(_QWORD *)v15;
        v15 += 24;
      }
      if ( *(_QWORD *)a4 )
      {
        memcpy_0(v17, *(const void **)(a4 + 8), *(_QWORD *)a4);
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
0x180004b40  push    rbx
0x180004b42  push    rbp
0x180004b43  push    rsi
0x180004b44  push    rdi
0x180004b45  push    r12
0x180004b47  push    r13
0x180004b49  push    r14
0x180004b4b  push    r15
0x180004b4d  sub     rsp, 48h
0x180004b51  mov     rax, [r8]
0x180004b54  xor     r13d, r13d
0x180004b57  mov     r14, r9
0x180004b5a  mov     r12, r8
0x180004b5d  mov     rbx, rdx
0x180004b60  test    rax, rax
0x180004b63  jnz     short loc_180004B75
0x180004b65  mov     [rdx], r13
0x180004b68  mov     [rdx+8], r13
0x180004b6c  mov     [rdx+10h], r13d
0x180004b70  jmp     loc_180004CCB
0x180004b75  mov     rcx, [r8+8]
0x180004b79  lea     rax, [rax+rax*2]
0x180004b7d  mov     rdx, r13
0x180004b80  mov     r9b, r13b
0x180004b83  mov     r11, 0FFFFFFFFFFFF0000h
0x180004b8a  lea     r10, [rcx+rax*8]
0x180004b8e  jmp     short loc_180004BBC
0x180004b90  cmp     [rcx+10h], r13b
0x180004b94  mov     eax, 1
0x180004b99  mov     r8, [rcx]
0x180004b9c  movzx   r9d, r9b
0x180004ba0  cmovz   r9d, eax
0x180004ba4  add     r8, rdx
0x180004ba7  cmp     r8, rdx
0x180004baa  jb      loc_180004C3D
0x180004bb0  cmp     r8, r11
0x180004bb3  ja      short loc_180004C1E
0x180004bb5  mov     rdx, r8; char *
0x180004bb8  add     rcx, 18h
0x180004bbc  cmp     rcx, r10
0x180004bbf  jnz     short loc_180004B90
0x180004bc1  mov     rax, [r14]
0x180004bc4  test    rax, rax
0x180004bc7  jz      short loc_180004BD9
0x180004bc9  add     rax, rdx
0x180004bcc  cmp     rax, rdx
0x180004bcf  jb      short loc_180004C3D
0x180004bd1  cmp     rax, r11
0x180004bd4  ja      short loc_180004C1E
0x180004bd6  mov     rdx, rax
0x180004bd9  test    r9b, r9b
0x180004bdc  jz      loc_180004CC0
0x180004be2  test    rdx, rdx
0x180004be5  jz      loc_180004CC0
0x180004beb  lea     rcx, [rsp+88h+var_68]
0x180004bf0  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180004bf5  mov     r15, [rsp+88h+var_58]
0x180004bfa  test    r15d, r15d
0x180004bfd  js      loc_180004C93
0x180004c03  mov     rax, [r12]
0x180004c07  mov     rsi, [r12+8]
0x180004c0c  mov     rbp, [rsp+88h+var_60]
0x180004c11  mov     rdi, rbp
0x180004c14  lea     rcx, [rax+rax*2]
0x180004c18  lea     r12, [rsi+rcx*8]
0x180004c1c  jmp     short loc_180004C5C
0x180004c1e  lea     rcx, aNewtotallength_0; "newTotalLength <= MessageLimit"
0x180004c25  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180004c2a  mov     [rbx], r13
0x180004c2d  mov     [rbx+8], r13
0x180004c31  mov     dword ptr [rbx+10h], 0C0000095h
0x180004c38  jmp     loc_180004CCB
0x180004c3d  lea     rcx, aNewtotallength; "newTotalLength >= totalLength"
0x180004c44  jmp     short loc_180004C25
0x180004c46  mov     r8, [rsi]; Size
0x180004c49  mov     rcx, rdi; void *
0x180004c4c  mov     rdx, [rsi+8]; Src
0x180004c50  call    memcpy_0
0x180004c55  add     rdi, [rsi]
0x180004c58  add     rsi, 18h
0x180004c5c  cmp     rsi, r12
0x180004c5f  jnz     short loc_180004C46
0x180004c61  mov     r8, [r14]; Size
0x180004c64  test    r8, r8
0x180004c67  jz      short loc_180004C78
0x180004c69  mov     rdx, [r14+8]; Src
0x180004c6d  mov     rcx, rdi; void *
0x180004c70  call    memcpy_0
0x180004c75  add     rdi, [r14]
0x180004c78  mov     rcx, [rsp+88h+var_68]
0x180004c7d  lea     rax, [rcx+rbp]
0x180004c81  cmp     rdi, rax
0x180004c84  jnz     short loc_180004CDF
0x180004c86  mov     [rbx+10h], r15d
0x180004c8a  mov     [rbx], rcx
0x180004c8d  mov     [rbx+8], rbp
0x180004c91  jmp     short loc_180004CCB
0x180004c93  lea     rcx, aResult; "result"
0x180004c9a  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180004c9f  mov     rcx, [rsp+88h+var_60]; void *
0x180004ca4  mov     [rbx], r13
0x180004ca7  mov     [rbx+8], r13
0x180004cab  mov     dword ptr [rbx+10h], 0C0000017h
0x180004cb2  test    rcx, rcx
0x180004cb5  jz      short loc_180004CCB
0x180004cb7  xor     edx, edx; struct std::nothrow_t *
0x180004cb9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004cbe  jmp     short loc_180004CCB
0x180004cc0  mov     [rbx], r13
0x180004cc3  mov     [rbx+8], r13
0x180004cc7  mov     [rbx+10h], r13d
0x180004ccb  mov     rax, rbx
0x180004cce  add     rsp, 48h
0x180004cd2  pop     r15
0x180004cd4  pop     r14
0x180004cd6  pop     r13
0x180004cd8  pop     r12
0x180004cda  pop     rdi
0x180004cdb  pop     rsi
0x180004cdc  pop     rbp
0x180004cdd  pop     rbx
0x180004cde  retn
0x180004cdf  lea     rcx, aIncorrectTotal; "Incorrect total length for coalescing a"...
0x180004ce6  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
