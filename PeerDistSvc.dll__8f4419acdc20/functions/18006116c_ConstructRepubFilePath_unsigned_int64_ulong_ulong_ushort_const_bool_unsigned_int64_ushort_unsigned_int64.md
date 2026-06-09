# ConstructRepubFilePath(unsigned __int64,ulong,ulong,ushort const *,bool,unsigned __int64,ushort * *,unsigned __int64 *)

- ea: `0x18006116c`
- end: `0x18006156f`
- name: `?ConstructRepubFilePath@@YAK_KKKPEBG_N0PEAPEAGPEA_K@Z`
- size: `1027`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, unsigned int, const unsigned __int16 *, bool, unsigned __int64, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180073c54`
- `0x18007c658`
- `0x1800801f0`

## callees

- `0x1800024f0`
- `0x1800024fc`
- `0x180008290`
- `0x1800094d4`
- `0x18000cf48`
- `0x1800180e4`
- `0x180051e10`
- `0x180060fa0`
- `0x18006116c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061442`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180061438`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180061438`

## pseudocode

```c
__int64 __fastcall ConstructRepubFilePath(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        bool a5,
        unsigned __int64 a6,
        unsigned __int16 **a7,
        unsigned __int64 *a8)
{
  unsigned __int16 *v8; // r15
  unsigned __int64 v11; // r13
  unsigned __int64 v12; // rax
  int v13; // r12d
  void *v14; // rbx
  unsigned __int16 *v15; // rdi
  DWORD LastError; // eax
  DWORD v17; // esi
  CHostedCacheMsgEncoding *v18; // rcx
  int v19; // edx
  unsigned int v20; // edx
  unsigned int v21; // ebp
  int v22; // eax
  CHostedCacheMsgEncoding *v23; // rcx
  __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  unsigned int v26; // ecx
  int v27; // eax
  int v28; // eax
  void *Block; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int64 v31; // [rsp+38h] [rbp-60h] BYREF
  unsigned __int64 v32; // [rsp+40h] [rbp-58h]
  unsigned __int64 v33; // [rsp+48h] [rbp-50h]
  unsigned __int64 v34; // [rsp+50h] [rbp-48h]
  __int64 v35; // [rsp+58h] [rbp-40h]
  unsigned int v38; // [rsp+B0h] [rbp+18h]

  LODWORD(v8) = (_DWORD)a4;
  if ( (a3 & 1) != 0 )
    return 87;
  if ( a2 > 0x10 )
    return 87;
  if ( a3 > 0x400 )
    return 87;
  v11 = 0;
  if ( !a7 || !a8 )
    return 87;
  *a8 = 0;
  *a7 = 0;
  v12 = a3 - 1;
  v32 = v12;
  v13 = 0;
  while ( v12 )
  {
    v12 >>= 1;
    if ( (unsigned int)++v13 >= 0xA )
    {
      if ( v12 )
        return 87;
      break;
    }
  }
  v14 = 0;
  v34 = 0;
  v15 = 0;
  v35 = 0;
  Block = 0;
  v31 = 0;
  LastError = ConstructRepubBlockFolderRoot(a4, (unsigned __int16 **)&Block, &v31);
  v17 = LastError;
  if ( LastError )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v19 = 45;
LABEL_15:
      WPP_SF_Sd(
        *((_QWORD *)v18 + 12),
        v19,
        (unsigned int)WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids,
        (_DWORD)v8,
        LastError);
    }
LABEL_52:
    operator delete(v15);
    operator delete(v14);
    return v17;
  }
  operator delete(0);
  v14 = Block;
  v34 = (unsigned __int64)Block;
  if ( v31 < 0xFFFFFFFF )
  {
    v20 = 65 * a2 + 66;
    if ( v31 + v20 >= v31 )
    {
      v21 = v20 + v31;
      v33 = v20 + (unsigned int)v31;
      v8 = (unsigned __int16 *)operator new[](saturated_mul(v33, 2u));
      operator delete(0);
      v15 = v8;
      v22 = StringCchCopyW(v8, v21, (const unsigned __int16 *)v14);
      if ( v22 >= 0 )
      {
        v25 = a1 >> 10;
        v34 = a1 >> 10;
        v26 = 0;
        while ( 1 )
        {
          v38 = v26;
          if ( v26 >= a2 )
            break;
          LODWORD(Block) = v13 * (a2 - v26 - 1);
          v31 = v32 & (v25 >> (char)Block);
          v27 = StringCchPrintfW(v8, v33, L"%s\\%I64u", v8, v31);
          if ( v27 < 0 )
          {
            v17 = (unsigned __int16)v27;
            v23 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              v24 = 47;
              goto LABEL_23;
            }
            goto LABEL_52;
          }
          if ( a5 && (a6 == -1 || (v32 & (a6 >> (char)Block)) != v31) )
          {
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
            {
              WPP_SF_SDI(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                48,
                (unsigned int)WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids,
                (_DWORD)v8,
                v38,
                a1);
            }
            if ( !CreateDirectoryW(v8, 0) )
            {
              LastError = GetLastError();
              v17 = LastError;
              if ( LastError != 183 )
              {
                v18 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  v19 = 49;
                  goto LABEL_15;
                }
                goto LABEL_52;
              }
              v17 = 0;
            }
          }
          v11 = v31 | (v11 << v13);
          v26 = v38 + 1;
          v25 = v34;
        }
        v28 = StringCchPrintfW(v8, v33, L"%s\\%I64u.dat", v8, a1);
        if ( v28 >= 0 )
        {
          v15 = 0;
          *a7 = v8;
          *a8 = v11;
        }
        else
        {
          v17 = (unsigned __int16)v28;
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v24 = 50;
            goto LABEL_23;
          }
        }
      }
      else
      {
        v17 = (unsigned __int16)v22;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v24 = 46;
LABEL_23:
          WPP_SF_d(*((_QWORD *)v23 + 12), v24, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids, v17);
        }
      }
      goto LABEL_52;
    }
  }
  operator delete(0);
  operator delete(v14);
  return 534;
}

```

## disassembly

```asm
0x18006116c  mov     [rsp+arg_18], rbx
0x180061171  mov     [rsp+arg_8], edx
0x180061175  mov     [rsp+arg_0], rcx
0x18006117a  push    rbp
0x18006117b  push    rsi
0x18006117c  push    rdi
0x18006117d  push    r12
0x18006117f  push    r13
0x180061181  push    r14
0x180061183  push    r15
0x180061185  sub     rsp, 60h
0x180061189  mov     r15, r9
0x18006118c  mov     ebp, edx
0x18006118e  mov     r14, rcx
0x180061191  test    r8b, 1
0x180061195  jnz     loc_180061552
0x18006119b  cmp     edx, 10h
0x18006119e  ja      loc_180061552
0x1800611a4  cmp     r8d, 400h
0x1800611ab  ja      loc_180061552
0x1800611b1  xor     r13d, r13d
0x1800611b4  mov     rax, [rsp+98h+arg_30]
0x1800611bc  test    rax, rax
0x1800611bf  jz      loc_180061552
0x1800611c5  mov     rcx, [rsp+98h+arg_38]
0x1800611cd  test    rcx, rcx
0x1800611d0  jz      loc_180061552
0x1800611d6  mov     [rcx], r13
0x1800611d9  mov     [rax], r13
0x1800611dc  lea     eax, [r8-1]
0x1800611e0  mov     [rsp+98h+var_58], rax
0x1800611e5  mov     r12d, r13d
0x1800611e8  test    rax, rax
0x1800611eb  jz      short loc_180061202
0x1800611ed  shr     rax, 1
0x1800611f0  inc     r12d
0x1800611f3  cmp     r12d, 0Ah
0x1800611f7  jb      short loc_1800611E8
0x1800611f9  test    rax, rax
0x1800611fc  jnz     loc_180061552
0x180061202  mov     rbx, r13
0x180061205  mov     [rsp+98h+var_48], rbx
0x18006120a  mov     rdi, r13
0x18006120d  mov     [rsp+98h+var_40], r13
0x180061212  mov     [rsp+98h+Block], r13
0x180061217  mov     [rsp+98h+var_60], r13
0x18006121c  lea     r8, [rsp+98h+var_60]; unsigned __int64 *
0x180061221  lea     rdx, [rsp+98h+Block]; unsigned __int16 **
0x180061226  mov     rcx, r15; unsigned __int16 *
0x180061229  call    ?ConstructRepubBlockFolderRoot@@YAKPEBGPEAPEAGPEA_K@Z; ConstructRepubBlockFolderRoot(ushort const *,ushort * *,unsigned __int64 *)
0x18006122e  mov     esi, eax
0x180061230  test    eax, eax
0x180061232  jz      short loc_180061283
0x180061234  lea     r14, WPP_GLOBAL_Control
0x18006123b  mov     rcx, cs:WPP_GLOBAL_Control
0x180061242  cmp     rcx, r14
0x180061245  jz      loc_180061526
0x18006124b  mov     bpl, 4
0x18006124e  test    [rcx+6Ch], bpl
0x180061252  jz      loc_180061526
0x180061258  cmp     byte ptr [rcx+69h], 1
0x18006125c  jb      loc_180061526
0x180061262  mov     edx, 2Dh ; '-'
0x180061267  mov     dword ptr [rsp+98h+var_78], eax
0x18006126b  mov     r9, r15
0x18006126e  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180061275  mov     rcx, [rcx+60h]
0x180061279  call    WPP_SF_Sd
0x18006127e  jmp     loc_180061526
0x180061283  xor     ecx, ecx; Block
0x180061285  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006128a  mov     rbx, [rsp+98h+Block]
0x18006128f  mov     [rsp+98h+var_48], rbx
0x180061294  mov     eax, 0FFFFFFFFh
0x180061299  mov     rcx, [rsp+98h+var_60]
0x18006129e  cmp     rcx, rax
0x1800612a1  jnb     loc_18006153B
0x1800612a7  imul    edx, ebp, 41h ; 'A'
0x1800612aa  add     edx, 42h ; 'B'
0x1800612ad  mov     eax, edx
0x1800612af  add     rax, rcx
0x1800612b2  cmp     rax, rcx
0x1800612b5  jb      loc_18006153B
0x1800612bb  lea     ebp, [rdx+rcx]
0x1800612be  mov     [rsp+98h+var_50], rbp
0x1800612c3  mov     eax, 2
0x1800612c8  mul     rbp
0x1800612cb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800612d2  cmovb   rax, rcx
0x1800612d6  mov     rcx, rax; unsigned __int64
0x1800612d9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800612de  mov     r15, rax
0x1800612e1  xor     ecx, ecx; Block
0x1800612e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800612e8  mov     rdi, r15
0x1800612eb  mov     r8, rbx; unsigned __int16 *
0x1800612ee  mov     edx, ebp; unsigned __int64
0x1800612f0  mov     rcx, r15; unsigned __int16 *
0x1800612f3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800612f8  test    eax, eax
0x1800612fa  jns     short loc_18006134A
0x1800612fc  movzx   esi, ax
0x1800612ff  lea     r14, WPP_GLOBAL_Control
0x180061306  mov     rcx, cs:WPP_GLOBAL_Control
0x18006130d  cmp     rcx, r14
0x180061310  jz      loc_180061526
0x180061316  mov     bpl, 4
0x180061319  test    [rcx+6Ch], bpl
0x18006131d  jz      loc_180061526
0x180061323  cmp     byte ptr [rcx+69h], 1
0x180061327  jb      loc_180061526
0x18006132d  mov     edx, 2Eh ; '.'
0x180061332  mov     r9d, esi
0x180061335  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x18006133c  mov     rcx, [rcx+60h]
0x180061340  call    WPP_SF_d
0x180061345  jmp     loc_180061526
0x18006134a  mov     rdx, r14
0x18006134d  shr     rdx, 0Ah
0x180061351  mov     [rsp+98h+var_48], rdx
0x180061356  xor     ecx, ecx
0x180061358  lea     r14, WPP_GLOBAL_Control
0x18006135f  mov     bpl, 4
0x180061362  mov     [rsp+98h+arg_10], ecx
0x180061369  mov     eax, [rsp+98h+arg_8]
0x180061370  mov     r9, r15
0x180061373  cmp     ecx, eax
0x180061375  jnb     loc_1800614C4
0x18006137b  sub     eax, ecx
0x18006137d  dec     eax
0x18006137f  imul    eax, r12d
0x180061383  mov     dword ptr [rsp+98h+Block], eax
0x180061387  mov     ecx, eax
0x180061389  shr     rdx, cl
0x18006138c  and     rdx, [rsp+98h+var_58]
0x180061391  mov     [rsp+98h+var_60], rdx
0x180061396  mov     [rsp+98h+var_78], rdx
0x18006139b  lea     r8, aSI64u; "%s\\%I64u"
0x1800613a2  mov     rdx, [rsp+98h+var_50]; unsigned __int64
0x1800613a7  mov     rcx, r15; unsigned __int16 *
0x1800613aa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800613af  test    eax, eax
0x1800613b1  js      loc_18006149F
0x1800613b7  cmp     [rsp+98h+arg_20], 0
0x1800613bf  jz      loc_180061453
0x1800613c5  cmp     [rsp+98h+arg_28], 0FFFFFFFFFFFFFFFFh
0x1800613ce  jz      short loc_1800613EB
0x1800613d0  mov     rax, [rsp+98h+arg_28]
0x1800613d8  mov     ecx, dword ptr [rsp+98h+Block]
0x1800613dc  shr     rax, cl
0x1800613df  and     rax, [rsp+98h+var_58]
0x1800613e4  cmp     rax, [rsp+98h+var_60]
0x1800613e9  jz      short loc_180061453
0x1800613eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800613f2  cmp     rcx, r14
0x1800613f5  jz      short loc_180061433
0x1800613f7  test    [rcx+6Ch], bpl
0x1800613fb  jz      short loc_180061433
0x1800613fd  cmp     [rcx+69h], bpl
0x180061401  jb      short loc_180061433
0x180061403  mov     edx, 30h ; '0'
0x180061408  mov     rax, [rsp+98h+arg_0]
0x180061410  mov     [rsp+98h+var_70], rax
0x180061415  mov     eax, [rsp+98h+arg_10]
0x18006141c  mov     dword ptr [rsp+98h+var_78], eax
0x180061420  mov     r9, r15
0x180061423  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x18006142a  mov     rcx, [rcx+60h]
0x18006142e  call    WPP_SF_SDI
0x180061433  xor     edx, edx; lpSecurityAttributes
0x180061435  mov     rcx, r15; lpPathName
0x180061438  call    cs:__imp_CreateDirectoryW
0x18006143e  test    eax, eax
0x180061440  jnz     short loc_180061453
0x180061442  call    cs:__imp_GetLastError
0x180061448  mov     esi, eax
0x18006144a  cmp     eax, 0B7h
0x18006144f  jnz     short loc_180061471
0x180061451  xor     esi, esi
0x180061453  mov     ecx, r12d
0x180061456  shl     r13, cl
0x180061459  or      r13, [rsp+98h+var_60]
0x18006145e  mov     ecx, [rsp+98h+arg_10]
0x180061465  inc     ecx
0x180061467  mov     rdx, [rsp+98h+var_48]
0x18006146c  jmp     loc_180061362
0x180061471  mov     rcx, cs:WPP_GLOBAL_Control
0x180061478  cmp     rcx, r14
0x18006147b  jz      loc_180061526
0x180061481  test    [rcx+6Ch], bpl
0x180061485  jz      loc_180061526
0x18006148b  cmp     byte ptr [rcx+69h], 1
0x18006148f  jb      loc_180061526
0x180061495  mov     edx, 31h ; '1'
0x18006149a  jmp     loc_180061267
0x18006149f  movzx   esi, ax
0x1800614a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800614a9  cmp     rcx, r14
0x1800614ac  jz      short loc_180061526
0x1800614ae  test    [rcx+6Ch], bpl
0x1800614b2  jz      short loc_180061526
0x1800614b4  cmp     byte ptr [rcx+69h], 1
0x1800614b8  jb      short loc_180061526
0x1800614ba  mov     edx, 2Fh ; '/'
0x1800614bf  jmp     loc_180061332
0x1800614c4  mov     rax, [rsp+98h+arg_0]
0x1800614cc  mov     [rsp+98h+var_78], rax
0x1800614d1  lea     r8, aSI64uDat; "%s\\%I64u.dat"
0x1800614d8  mov     rdx, [rsp+98h+var_50]; unsigned __int64
0x1800614dd  mov     rcx, r15; unsigned __int16 *
0x1800614e0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800614e5  test    eax, eax
0x1800614e7  jns     short loc_18006150E
0x1800614e9  movzx   esi, ax
0x1800614ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800614f3  cmp     rcx, r14
0x1800614f6  jz      short loc_180061526
0x1800614f8  test    [rcx+6Ch], bpl
0x1800614fc  jz      short loc_180061526
0x1800614fe  cmp     byte ptr [rcx+69h], 1
0x180061502  jb      short loc_180061526
0x180061504  mov     edx, 32h ; '2'
0x180061509  jmp     loc_180061332
0x18006150e  xor     edi, edi
0x180061510  mov     rax, [rsp+98h+arg_30]
0x180061518  mov     [rax], r15
0x18006151b  mov     rax, [rsp+98h+arg_38]
0x180061523  mov     [rax], r13
0x180061526  mov     rcx, rdi; Block
0x180061529  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006152e  nop
0x18006152f  mov     rcx, rbx; Block
0x180061532  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180061537  mov     eax, esi
0x180061539  jmp     short loc_180061557
0x18006153b  xor     ecx, ecx; Block
0x18006153d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180061542  nop
0x180061543  mov     rcx, rbx; Block
0x180061546  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006154b  mov     eax, 216h
0x180061550  jmp     short loc_180061557
0x180061552  mov     eax, 57h ; 'W'
0x180061557  mov     rbx, [rsp+98h+arg_18]
0x18006155f  add     rsp, 60h
0x180061563  pop     r15
0x180061565  pop     r14
0x180061567  pop     r13
0x180061569  pop     r12
0x18006156b  pop     rdi
0x18006156c  pop     rsi
0x18006156d  pop     rbp
0x18006156e  retn
```
