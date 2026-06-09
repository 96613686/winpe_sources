# IsFileObjectSupported(CFile const &)

- ea: `0x180002568`
- end: `0x1800027a5`
- name: `?IsFileObjectSupported@@YAHAEBVCFile@@@Z`
- size: `573`
- prototype: `__int64 __fastcall(const struct CFile *this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180002060`
- `0x180002150`

## callees

- `0x180002568`
- `0x180002dfc`
- `0x180003296`
- `0x1800032ae`
- `0x1800032e0`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x180002618`
- `KERNEL32!GetFileSizeEx` at `0x180002618`
- `KERNEL32!SetLastError` at `0x180002779`
- `KERNEL32!SetLastError` at `0x180002779`

## pseudocode

```c
__int64 __fastcall IsFileObjectSupported(const struct CFile *this)
{
  unsigned int v2; // esi
  DWORD v3; // ecx
  void *v4; // rcx
  BOOL v5; // eax
  char *v6; // rdx
  unsigned __int64 v7; // r9
  _BYTE *i; // rax
  unsigned __int64 v9; // rcx
  signed __int64 v10; // r8
  __int64 v11; // rdi
  unsigned __int64 v12; // r10
  char *v13; // rbx
  __int64 v14; // r11
  unsigned __int64 v15; // r8
  __int64 v16; // rax
  unsigned __int64 v17; // rdx
  _QWORD *v18; // rax
  union _LARGE_INTEGER FileSize; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v21[4]; // [rsp+28h] [rbp-D8h] BYREF
  char v22; // [rsp+48h] [rbp-B8h] BYREF
  char Buf1[8]; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v25; // [rsp+78h] [rbp-88h]
  unsigned __int16 v26; // [rsp+7Ah] [rbp-86h]
  unsigned int v27; // [rsp+7Ch] [rbp-84h]
  _BYTE v28[24]; // [rsp+80h] [rbp-80h] BYREF
  char v29; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v30[24]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v31; // [rsp+C8h] [rbp-38h]
  char v32; // [rsp+CCh] [rbp-34h] BYREF
  unsigned int v33; // [rsp+104h] [rbp+4h]
  signed __int64 v34; // [rsp+10Ch] [rbp+Ch]
  _OWORD v35[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v36; // [rsp+140h] [rbp+40h]
  __int64 v37; // [rsp+148h] [rbp+48h] BYREF

  v2 = 0;
  memset_0(Buf1, 0, 0xD0u);
  if ( *((_QWORD *)this + 1) == -1 )
  {
    v3 = 87;
  }
  else
  {
    if ( CFile::Read(this, 0, 0xD0u, Buf1) && !memcmp_0(Buf1, "MSWIM", 8u) && v24 == 208 && v25 <= v26 && v31 <= v27 )
    {
      v4 = (void *)*((_QWORD *)this + 1);
      FileSize.QuadPart = 0;
      v5 = GetFileSizeEx(v4, &FileSize);
      v6 = (char *)v21;
      v21[0] = v28;
      v7 = FileSize.QuadPart & -(__int64)v5;
      v21[1] = &v29;
      v21[2] = v30;
      v21[3] = &v32;
      for ( i = v28; ; i = *(_BYTE **)v6 )
      {
        if ( i != v30 )
        {
          v9 = *(_QWORD *)i & 0xFFFFFFFFFFFFFFLL;
          if ( v9 >= v7 )
            break;
          v10 = *((_QWORD *)i + 1);
          if ( v10 >= (__int64)v7 || *((_QWORD *)i + 2) >= (signed __int64)v7 || v10 + v9 < v10 || v10 + v9 > v7 )
            break;
        }
        v6 += 8;
        if ( v6 == &v22 )
        {
          v11 = v33;
          if ( v33 < v7 )
          {
            v12 = v34;
            if ( v34 < (__int64)v7 && (unsigned __int64)v33 + v34 >= v34 && (unsigned __int64)v33 + v34 <= v7 )
            {
              v13 = (char *)v21;
              memset(v35, 0, sizeof(v35));
              v36 = 0;
              v14 = 0;
              while ( 1 )
              {
                v15 = *(_QWORD *)(*(_QWORD *)v13 + 8LL);
                v16 = -1;
                v17 = v15 + (**(_QWORD **)v13 & 0xFFFFFFFFFFFFFFLL);
                if ( v17 >= v15 )
                  v16 = v15 + (**(_QWORD **)v13 & 0xFFFFFFFFFFFFFFLL);
                *((_QWORD *)v35 + v14) = v16;
                if ( v17 < v15 )
                  break;
                ++v14;
                v13 += 8;
                if ( v13 == &v22 )
                {
                  if ( v12 + v11 < v12 )
                  {
                    *((_QWORD *)v35 + v14) = -1;
                    goto LABEL_3;
                  }
                  *((_QWORD *)v35 + v14) = v12 + v11;
                  v18 = v35;
                  while ( *v18 != v7 )
                  {
                    if ( ++v18 == &v37 )
                      goto LABEL_3;
                  }
                  v3 = 0;
                  v2 = 1;
                  goto LABEL_34;
                }
              }
            }
          }
          break;
        }
      }
    }
LABEL_3:
    v3 = 13;
  }
LABEL_34:
  SetLastError(v3);
  return v2;
}

```

## disassembly

```asm
0x180002568  mov     [rsp-8+arg_8], rbx
0x18000256d  mov     [rsp-8+arg_10], rsi
0x180002572  push    rbp
0x180002573  push    rdi
0x180002574  push    r12
0x180002576  lea     rbp, [rsp-50h]
0x18000257b  sub     rsp, 150h
0x180002582  mov     rax, cs:__security_cookie
0x180002589  xor     rax, rsp
0x18000258c  mov     [rbp+60h+var_18], rax
0x180002590  mov     rbx, rcx
0x180002593  mov     edi, 0D0h
0x180002598  mov     r8d, edi; Size
0x18000259b  lea     rcx, [rsp+160h+Buf1]; void *
0x1800025a0  xor     edx, edx; Val
0x1800025a2  xor     esi, esi
0x1800025a4  call    memset_0
0x1800025a9  cmp     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800025ae  jz      loc_180002774
0x1800025b4  lea     r9, [rsp+160h+Buf1]; void *
0x1800025b9  mov     r8d, edi; unsigned int
0x1800025bc  xor     edx, edx; unsigned __int64
0x1800025be  mov     rcx, rbx; this
0x1800025c1  call    ?Read@CFile@@QEBA_N_KKPEAX@Z; CFile::Read(unsigned __int64,ulong,void *)
0x1800025c6  test    al, al
0x1800025c8  jnz     short loc_1800025D4
0x1800025ca  mov     ecx, 0Dh
0x1800025cf  jmp     loc_180002779
0x1800025d4  mov     r8d, 8; Size
0x1800025da  lea     rdx, aMswim; "MSWIM"
0x1800025e1  lea     rcx, [rsp+160h+Buf1]; Buf1
0x1800025e6  call    memcmp_0
0x1800025eb  test    eax, eax
0x1800025ed  jnz     short loc_1800025CA
0x1800025ef  cmp     [rsp+160h+var_108], edi
0x1800025f3  jnz     short loc_1800025CA
0x1800025f5  movzx   eax, [rsp+160h+var_E6]
0x1800025fa  cmp     [rsp+160h+var_E8], ax
0x1800025ff  ja      short loc_1800025CA
0x180002601  mov     eax, [rsp+160h+var_E4]
0x180002605  cmp     [rbp+60h+var_98], eax
0x180002608  ja      short loc_1800025CA
0x18000260a  mov     rcx, [rbx+8]; hFile
0x18000260e  lea     rdx, [rsp+160h+FileSize]; lpFileSize
0x180002613  mov     qword ptr [rsp+160h+FileSize], rsi
0x180002618  call    cs:__imp_GetFileSizeEx
0x18000261e  lea     rdx, [rsp+160h+var_138]
0x180002623  mov     r12, 0FFFFFFFFFFFFFFh
0x18000262d  neg     eax
0x18000262f  lea     rax, [rbp+60h+var_E0]
0x180002633  mov     [rsp+160h+var_138], rax
0x180002638  sbb     r9, r9
0x18000263b  and     r9, qword ptr [rsp+160h+FileSize]
0x180002640  lea     rax, [rbp+60h+var_C8]
0x180002644  mov     [rsp+160h+var_130], rax
0x180002649  lea     rax, [rbp+60h+var_B0]
0x18000264d  mov     [rsp+160h+var_128], rax
0x180002652  lea     rax, [rbp+60h+var_94]
0x180002656  mov     [rsp+160h+var_120], rax
0x18000265b  lea     rax, [rbp+60h+var_E0]
0x18000265f  lea     rcx, [rbp+60h+var_B0]
0x180002663  cmp     rax, rcx
0x180002666  jz      short loc_1800026A4
0x180002668  mov     rcx, [rax]
0x18000266b  and     rcx, r12
0x18000266e  cmp     rcx, r9
0x180002671  jnb     loc_1800025CA
0x180002677  mov     r8, [rax+8]
0x18000267b  cmp     r8, r9
0x18000267e  jge     loc_1800025CA
0x180002684  cmp     [rax+10h], r9
0x180002688  jge     loc_1800025CA
0x18000268e  lea     rax, [r8+rcx]
0x180002692  cmp     rax, r8
0x180002695  jb      loc_1800025CA
0x18000269b  cmp     rax, r9
0x18000269e  ja      loc_1800025CA
0x1800026a4  add     rdx, 8
0x1800026a8  lea     rax, [rsp+160h+var_118]
0x1800026ad  cmp     rdx, rax
0x1800026b0  jz      short loc_1800026B7
0x1800026b2  mov     rax, [rdx]
0x1800026b5  jmp     short loc_18000265F
0x1800026b7  mov     edi, [rbp+60h+var_5C]
0x1800026ba  cmp     rdi, r9
0x1800026bd  jnb     loc_1800025CA
0x1800026c3  mov     r10, [rbp+60h+var_54]
0x1800026c7  cmp     r10, r9
0x1800026ca  jge     loc_1800025CA
0x1800026d0  lea     rcx, [rdi+r10]
0x1800026d4  cmp     rcx, r10
0x1800026d7  jb      loc_1800025CA
0x1800026dd  cmp     rcx, r9
0x1800026e0  ja      loc_1800025CA
0x1800026e6  xorps   xmm0, xmm0
0x1800026e9  lea     rbx, [rsp+160h+var_138]
0x1800026ee  xor     eax, eax
0x1800026f0  movups  [rbp+60h+var_40], xmm0
0x1800026f4  mov     [rbp+60h+var_20], rax
0x1800026f8  xor     r11d, r11d
0x1800026fb  movups  [rbp+60h+var_30], xmm0
0x1800026ff  mov     rax, [rbx]
0x180002702  mov     r8, [rax+8]
0x180002706  mov     rdx, [rax]
0x180002709  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000270d  and     rdx, r12
0x180002710  add     rdx, r8
0x180002713  cmp     rdx, r8
0x180002716  cmovnb  rax, rdx
0x18000271a  mov     qword ptr [rbp+r11*8+60h+var_40], rax
0x18000271f  jb      loc_1800025CA
0x180002725  inc     r11
0x180002728  lea     rax, [rsp+160h+var_118]
0x18000272d  add     rbx, 8
0x180002731  cmp     rbx, rax
0x180002734  jnz     short loc_1800026FF
0x180002736  lea     rcx, [r10+rdi]
0x18000273a  cmp     rcx, r10
0x18000273d  jb      short loc_180002766
0x18000273f  mov     qword ptr [rbp+r11*8+60h+var_40], rcx
0x180002744  lea     rax, [rbp+60h+var_40]
0x180002748  cmp     [rax], r9
0x18000274b  jz      short loc_18000275F
0x18000274d  add     rax, 8
0x180002751  lea     rcx, [rbp+60h+var_18]
0x180002755  cmp     rax, rcx
0x180002758  jnz     short loc_180002748
0x18000275a  jmp     loc_1800025CA
0x18000275f  xor     ecx, ecx
0x180002761  lea     esi, [rcx+1]
0x180002764  jmp     short loc_180002779
0x180002766  mov     qword ptr [rbp+r11*8+60h+var_40], 0FFFFFFFFFFFFFFFFh
0x18000276f  jmp     loc_1800025CA
0x180002774  mov     ecx, 57h ; 'W'; dwErrCode
0x180002779  call    cs:__imp_SetLastError
0x18000277f  mov     eax, esi
0x180002781  mov     rcx, [rbp+60h+var_18]
0x180002785  xor     rcx, rsp; StackCookie
0x180002788  call    __security_check_cookie
0x18000278d  lea     r11, [rsp+160h+var_10]
0x180002795  mov     rbx, [r11+28h]
0x180002799  mov     rsi, [r11+30h]
0x18000279d  mov     rsp, r11
0x1800027a0  pop     r12
0x1800027a2  pop     rdi
0x1800027a3  pop     rbp
0x1800027a4  retn
```
