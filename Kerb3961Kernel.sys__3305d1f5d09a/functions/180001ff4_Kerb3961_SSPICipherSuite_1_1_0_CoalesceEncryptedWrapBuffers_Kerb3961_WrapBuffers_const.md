# Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(Kerb3961::WrapBuffers const &)

- ea: `0x180001ff4`
- end: `0x18000216b`
- name: `?CoalesceEncryptedWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z`
- size: `375`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x1800060f0`
- `0x1800064e0`
- `0x180009040`
- `0x180009300`
- `0x180010460`
- `0x180010760`

## callees

- `0x180001ff4`
- `0x180005b1c`
- `0x180011760`
- `0x180011b40`
- `0x180012300`

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
  _BYTE *v18; // rcx
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
    Kerb3961::MakeBuffer((__int64)&v20, (const struct std::nothrow_t *)v6);
    v13 = v22;
    if ( (int)v22 < 0 )
    {
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"result", v12);
      v18 = v21;
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = -1073741801;
      if ( v18 )
        Kerb3961Free(v18);
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
          memmove(v16, *(const void **)(v14 + 8), *(_QWORD *)v14);
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
0x180001ff4  push    rbx
0x180001ff6  push    rbp
0x180001ff7  push    rsi
0x180001ff8  push    rdi
0x180001ff9  push    r12
0x180001ffb  push    r14
0x180001ffd  push    r15
0x180001fff  sub     rsp, 40h
0x180002003  mov     rax, [rdx]
0x180002006  xor     r12d, r12d
0x180002009  mov     r14, rdx
0x18000200c  mov     rbx, rcx
0x18000200f  test    rax, rax
0x180002012  jnz     short loc_180002024
0x180002014  mov     [rcx], r12
0x180002017  mov     [rcx+8], r12
0x18000201b  mov     [rcx+10h], r12d
0x18000201f  jmp     loc_180002158
0x180002024  mov     r10, [r14+8]
0x180002028  lea     rax, [rax+rax*2]
0x18000202c  mov     rdx, r12; char *
0x18000202f  mov     r8, r12
0x180002032  mov     rcx, r10
0x180002035  lea     r11, [r10+rax*8]
0x180002039  cmp     r10, r11
0x18000203c  jz      loc_18000214D
0x180002042  cmp     [rcx+10h], r12b
0x180002046  jz      short loc_180002062
0x180002048  mov     r9, [rcx]
0x18000204b  add     r9, rdx
0x18000204e  cmp     r9, rdx
0x180002051  jb      short loc_1800020BB
0x180002053  cmp     r9, 0FFFFFFFFFFFF0000h
0x18000205a  ja      short loc_18000209C
0x18000205c  mov     rdx, r9
0x18000205f  inc     r8
0x180002062  add     rcx, 18h
0x180002066  cmp     rcx, r11
0x180002069  jnz     short loc_180002042
0x18000206b  test    r8, r8
0x18000206e  jz      loc_18000214D
0x180002074  test    rdx, rdx
0x180002077  jz      loc_18000214D
0x18000207d  cmp     r8, 1
0x180002081  jnz     short loc_1800020C4
0x180002083  cmp     [r10+10h], r12b
0x180002087  jz      short loc_1800020C4
0x180002089  mov     [rbx], r12
0x18000208c  mov     [rbx+8], r12
0x180002090  mov     dword ptr [rbx+10h], 0FFh
0x180002097  jmp     loc_180002158
0x18000209c  lea     rcx, aNewtotallength_0; "newTotalLength <= MessageLimit"
0x1800020a3  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800020a8  mov     [rbx], r12
0x1800020ab  mov     [rbx+8], r12
0x1800020af  mov     dword ptr [rbx+10h], 0C0000095h
0x1800020b6  jmp     loc_180002158
0x1800020bb  lea     rcx, aNewtotallength; "newTotalLength >= totalLength"
0x1800020c2  jmp     short loc_1800020A3
0x1800020c4  lea     rcx, [rsp+78h+var_58]
0x1800020c9  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x1800020ce  mov     rsi, [rsp+78h+var_48]
0x1800020d3  test    esi, esi
0x1800020d5  js      short loc_180002122
0x1800020d7  mov     rax, [r14]
0x1800020da  mov     rdi, [r14+8]
0x1800020de  mov     r15, [rsp+78h+var_50]
0x1800020e3  mov     rbp, r15
0x1800020e6  lea     rcx, [rax+rax*2]
0x1800020ea  lea     r14, [rdi+rcx*8]
0x1800020ee  jmp     short loc_18000210C
0x1800020f0  cmp     [rdi+10h], r12b
0x1800020f4  jz      short loc_180002108
0x1800020f6  mov     r8, [rdi]; Size
0x1800020f9  mov     rcx, rbp; void *
0x1800020fc  mov     rdx, [rdi+8]; Src
0x180002100  call    memmove
0x180002105  add     rbp, [rdi]
0x180002108  add     rdi, 18h
0x18000210c  cmp     rdi, r14
0x18000210f  jnz     short loc_1800020F0
0x180002111  mov     rax, [rsp+78h+var_58]
0x180002116  mov     [rbx], rax
0x180002119  mov     [rbx+10h], esi
0x18000211c  mov     [rbx+8], r15
0x180002120  jmp     short loc_180002158
0x180002122  lea     rcx, aResult; "result"
0x180002129  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000212e  mov     rcx, [rsp+78h+var_50]
0x180002133  mov     [rbx], r12
0x180002136  mov     [rbx+8], r12
0x18000213a  mov     dword ptr [rbx+10h], 0C0000017h
0x180002141  test    rcx, rcx
0x180002144  jz      short loc_180002158
0x180002146  call    Kerb3961Free
0x18000214b  jmp     short loc_180002158
0x18000214d  mov     [rbx], r12
0x180002150  mov     [rbx+8], r12
0x180002154  mov     [rbx+10h], r12d
0x180002158  mov     rax, rbx
0x18000215b  add     rsp, 40h
0x18000215f  pop     r15
0x180002161  pop     r14
0x180002163  pop     r12
0x180002165  pop     rdi
0x180002166  pop     rsi
0x180002167  pop     rbp
0x180002168  pop     rbx
0x180002169  retn
```
