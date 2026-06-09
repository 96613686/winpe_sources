# Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(Kerb3961::WrapBuffers const &)

- ea: `0x180004cf4`
- end: `0x180004e6c`
- name: `?CoalesceEncryptedWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z`
- size: `376`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800095b0`
- `0x1800099c0`
- `0x1800166e0`
- `0x1800169b0`
- `0x18001bbb0`
- `0x18001bec0`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180004cf4`
- `0x18000901c`
- `0x18001d360`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(__int64 a1, _QWORD *a2)
{
  __int64 v4; // r10
  __int64 v5; // rax
  const char *v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // r11
  unsigned __int64 v10; // r9
  char *v11; // rcx
  const char *v12; // rdx
  int v13; // esi
  __int64 v14; // rdi
  void *v15; // r15
  char *v16; // rbp
  __int64 v17; // r14
  void *v18; // rcx
  __int64 v20; // [rsp+20h] [rbp-58h] BYREF
  void *v21; // [rsp+28h] [rbp-50h]
  __int64 v22; // [rsp+30h] [rbp-48h]

  if ( !*a2 )
  {
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = 0;
    return a1;
  }
  v4 = a2[1];
  v5 = 3LL * *a2;
  v6 = 0;
  v7 = 0;
  v8 = v4;
  v9 = v4 + 8 * v5;
  if ( v4 == v9 )
  {
LABEL_26:
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = 0;
    return a1;
  }
  do
  {
    if ( !*(_BYTE *)(v8 + 16) )
      goto LABEL_8;
    v10 = (unsigned __int64)&v6[*(_QWORD *)v8];
    if ( v10 < (unsigned __int64)v6 )
    {
      v11 = "newTotalLength >= totalLength";
      goto LABEL_15;
    }
    if ( v10 > 0xFFFFFFFFFFFF0000uLL )
    {
      v11 = "newTotalLength <= MessageLimit";
LABEL_15:
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v11, v6);
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = -1073741675;
      return a1;
    }
    v6 += *(_QWORD *)v8;
    ++v7;
LABEL_8:
    v8 += 24;
  }
  while ( v8 != v9 );
  if ( !v7 || !v6 )
    goto LABEL_26;
  if ( v7 == 1 && *(_BYTE *)(v4 + 16) )
  {
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = 255;
  }
  else
  {
    Kerb3961::MakeBuffer(&v20);
    v13 = v22;
    if ( (int)v22 < 0 )
    {
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"result", v12);
      v18 = v21;
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = -1073741801;
      if ( v18 )
        operator delete(v18, 0);
    }
    else
    {
      v14 = a2[1];
      v15 = v21;
      v16 = (char *)v21;
      v17 = v14 + 24LL * *a2;
      while ( v14 != v17 )
      {
        if ( *(_BYTE *)(v14 + 16) )
        {
          memcpy_0(v16, *(const void **)(v14 + 8), *(_QWORD *)v14);
          v16 += *(_QWORD *)v14;
        }
        v14 += 24;
      }
      *(_QWORD *)a1 = v20;
      *(_DWORD *)(a1 + 16) = v13;
      *(_QWORD *)(a1 + 8) = v15;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180004cf4  push    rbx
0x180004cf6  push    rbp
0x180004cf7  push    rsi
0x180004cf8  push    rdi
0x180004cf9  push    r12
0x180004cfb  push    r14
0x180004cfd  push    r15
0x180004cff  sub     rsp, 40h
0x180004d03  mov     rax, [rdx]
0x180004d06  xor     r12d, r12d
0x180004d09  mov     r14, rdx
0x180004d0c  mov     rbx, rcx
0x180004d0f  test    rax, rax
0x180004d12  jnz     short loc_180004D24
0x180004d14  mov     [rcx], r12
0x180004d17  mov     [rcx+8], r12
0x180004d1b  mov     [rcx+10h], r12d
0x180004d1f  jmp     loc_180004E5A
0x180004d24  mov     r10, [r14+8]
0x180004d28  lea     rax, [rax+rax*2]
0x180004d2c  mov     rdx, r12; char *
0x180004d2f  mov     r8, r12
0x180004d32  mov     rcx, r10
0x180004d35  lea     r11, [r10+rax*8]
0x180004d39  cmp     r10, r11
0x180004d3c  jz      loc_180004E4F
0x180004d42  cmp     [rcx+10h], r12b
0x180004d46  jz      short loc_180004D62
0x180004d48  mov     r9, [rcx]
0x180004d4b  add     r9, rdx
0x180004d4e  cmp     r9, rdx
0x180004d51  jb      short loc_180004DBB
0x180004d53  cmp     r9, 0FFFFFFFFFFFF0000h
0x180004d5a  ja      short loc_180004D9C
0x180004d5c  mov     rdx, r9
0x180004d5f  inc     r8
0x180004d62  add     rcx, 18h
0x180004d66  cmp     rcx, r11
0x180004d69  jnz     short loc_180004D42
0x180004d6b  test    r8, r8
0x180004d6e  jz      loc_180004E4F
0x180004d74  test    rdx, rdx
0x180004d77  jz      loc_180004E4F
0x180004d7d  cmp     r8, 1
0x180004d81  jnz     short loc_180004DC4
0x180004d83  cmp     [r10+10h], r12b
0x180004d87  jz      short loc_180004DC4
0x180004d89  mov     [rbx], r12
0x180004d8c  mov     [rbx+8], r12
0x180004d90  mov     dword ptr [rbx+10h], 0FFh
0x180004d97  jmp     loc_180004E5A
0x180004d9c  lea     rcx, aNewtotallength_0; "newTotalLength <= MessageLimit"
0x180004da3  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180004da8  mov     [rbx], r12
0x180004dab  mov     [rbx+8], r12
0x180004daf  mov     dword ptr [rbx+10h], 0C0000095h
0x180004db6  jmp     loc_180004E5A
0x180004dbb  lea     rcx, aNewtotallength; "newTotalLength >= totalLength"
0x180004dc2  jmp     short loc_180004DA3
0x180004dc4  lea     rcx, [rsp+78h+var_58]
0x180004dc9  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180004dce  mov     rsi, [rsp+78h+var_48]
0x180004dd3  test    esi, esi
0x180004dd5  js      short loc_180004E22
0x180004dd7  mov     rax, [r14]
0x180004dda  mov     rdi, [r14+8]
0x180004dde  mov     r15, [rsp+78h+var_50]
0x180004de3  mov     rbp, r15
0x180004de6  lea     rcx, [rax+rax*2]
0x180004dea  lea     r14, [rdi+rcx*8]
0x180004dee  jmp     short loc_180004E0C
0x180004df0  cmp     [rdi+10h], r12b
0x180004df4  jz      short loc_180004E08
0x180004df6  mov     r8, [rdi]; Size
0x180004df9  mov     rcx, rbp; void *
0x180004dfc  mov     rdx, [rdi+8]; Src
0x180004e00  call    memcpy_0
0x180004e05  add     rbp, [rdi]
0x180004e08  add     rdi, 18h
0x180004e0c  cmp     rdi, r14
0x180004e0f  jnz     short loc_180004DF0
0x180004e11  mov     rax, [rsp+78h+var_58]
0x180004e16  mov     [rbx], rax
0x180004e19  mov     [rbx+10h], esi
0x180004e1c  mov     [rbx+8], r15
0x180004e20  jmp     short loc_180004E5A
0x180004e22  lea     rcx, aResult; "result"
0x180004e29  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180004e2e  mov     rcx, [rsp+78h+var_50]; void *
0x180004e33  mov     [rbx], r12
0x180004e36  mov     [rbx+8], r12
0x180004e3a  mov     dword ptr [rbx+10h], 0C0000017h
0x180004e41  test    rcx, rcx
0x180004e44  jz      short loc_180004E5A
0x180004e46  xor     edx, edx; struct std::nothrow_t *
0x180004e48  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004e4d  jmp     short loc_180004E5A
0x180004e4f  mov     [rbx], r12
0x180004e52  mov     [rbx+8], r12
0x180004e56  mov     [rbx+10h], r12d
0x180004e5a  mov     rax, rbx
0x180004e5d  add     rsp, 40h
0x180004e61  pop     r15
0x180004e63  pop     r14
0x180004e65  pop     r12
0x180004e67  pop     rdi
0x180004e68  pop     rsi
0x180004e69  pop     rbp
0x180004e6a  pop     rbx
0x180004e6b  retn
```
