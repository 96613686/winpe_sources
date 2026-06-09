# FSBlobToPropVariant(ushort,uchar *,ulong,tagPROPVARIANT &)

- ea: `0x1800552b8`
- end: `0x180055670`
- name: `?FSBlobToPropVariant@@YAJGPEAEKAEAUtagPROPVARIANT@@@Z`
- size: `952`
- prototype: `__int64 __fastcall(VARTYPE, unsigned __int8 *, __int64, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180055d3c`

## callees

- `0x180007824`
- `0x180007b64`
- `0x180007bcc`
- `0x180016fb4`
- `0x18002da54`
- `0x18002dbc4`
- `0x180054880`
- `0x1800552b8`
- `0x1800611b4`
- `0x180061b34`
- `0x1800e924c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800554a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055628`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800554a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055628`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005550c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005550c`

## string_xrefs

- `0x180055329`: `avcore\mf\frameserver\common\fshelper.cpp`
- `0x180055551`: `avcore\mf\frameserver\common\fshelper.cpp`

## pseudocode

```c
__int64 __fastcall FSBlobToPropVariant(VARTYPE a1, unsigned __int8 *a2, __int64 a3, struct tagPROPVARIANT *a4)
{
  size_t v5; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int v10; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  unsigned int v24; // ebx
  unsigned int v25; // ebx
  LPVOID v26; // rdi
  unsigned __int16 **v27; // rax
  unsigned __int16 *v28; // rbx
  void *v29; // rcx
  int v30; // edi
  __int64 v31; // rdx
  unsigned __int64 v32; // rdi
  char *v33; // rax
  char *i; // rcx
  __int64 unique_cotaskmem; // rax
  void *v36; // rcx
  BYTE *v37; // rbx
  int v38; // [rsp+20h] [rbp-20h]
  LPVOID pv; // [rsp+30h] [rbp-10h] BYREF
  void *v40; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  v5 = (unsigned int)a3;
  v8 = a1;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v38 = (int)a2;
    WPP_SF_dqd(*((_QWORD *)WPP_GLOBAL_Control + 27), 117, a3, a1);
  }
  if ( a1 >= 2u && (!(_DWORD)v5 || !a2) )
  {
    v9 = 1622;
LABEL_7:
    v10 = -2147024809;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\mf\\frameserver\\common\\fshelper.cpp",
      (const char *)(unsigned int)v10,
      v38);
    return (unsigned int)v10;
  }
  if ( v8 > 0x40 )
  {
    if ( v8 != 65 )
      goto LABEL_71;
    v40 = 0;
    unique_cotaskmem = wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(&pv, v5);
    wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
      &v40,
      unique_cotaskmem);
    v36 = pv;
    pv = 0;
    if ( v36 )
      CoTaskMemFree(v36);
    v37 = (BYTE *)v40;
    if ( !v40 )
    {
      v10 = -2147024882;
      v9 = 1711;
      goto LABEL_8;
    }
    memcpy_0(v40, a2, v5);
    a4->lVal = v5;
    a4->bstrblobVal.pData = v37;
    goto LABEL_77;
  }
  if ( v8 == 64 )
  {
    if ( (unsigned int)v5 < 8 )
    {
      v9 = 1703;
      goto LABEL_7;
    }
    goto LABEL_30;
  }
  if ( v8 > 0x11 )
  {
    v19 = v8 - 18;
    if ( !v19 )
      goto LABEL_65;
    v20 = v19 - 1;
    if ( !v20 )
      goto LABEL_62;
    v21 = v20 - 1;
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( !v23 )
          goto LABEL_62;
        v24 = v23 - 1;
        if ( !v24 )
          goto LABEL_62;
        v25 = v24 - 7;
        if ( v25 )
        {
          if ( v25 != 1 )
            goto LABEL_71;
          pv = 0;
          v10 = StringCbLengthW((const unsigned __int16 *)a2, v5, (unsigned __int64 *)&pv);
          if ( v10 < 0 )
          {
            v9 = 1695;
            goto LABEL_8;
          }
          v26 = pv;
          v27 = (unsigned __int16 **)wil::make_unique_cotaskmem_nothrow<unsigned short [0]>(&pv, (char *)pv + 1);
          v28 = *v27;
          *v27 = 0;
          v29 = pv;
          pv = 0;
          if ( v29 )
            CoTaskMemFree(v29);
          if ( !v28 )
          {
            v10 = -2147024882;
            v9 = 1697;
            goto LABEL_8;
          }
          v30 = StringCchCopyW(v28, (unsigned __int64)v26 + 1, (const unsigned __int16 *)a2);
          if ( v30 < 0 )
          {
            v31 = 1698;
LABEL_57:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v31,
              (unsigned int)"avcore\\mf\\frameserver\\common\\fshelper.cpp",
              (const char *)(unsigned int)v30,
              v38);
            CoTaskMemFree(v28);
            return (unsigned int)v30;
          }
        }
        else
        {
          pv = 0;
          v10 = StringCbLengthA((const char *)a2, v5, (unsigned __int64 *)&pv);
          if ( v10 < 0 )
          {
            v9 = 1681;
            goto LABEL_8;
          }
          v32 = (unsigned __int64)pv + 1;
          v33 = (char *)CoTaskMemAlloc((SIZE_T)pv + 1);
          if ( !v33 )
          {
            v10 = -2147024882;
            v9 = 1683;
            goto LABEL_8;
          }
          for ( i = v33; i != &v33[v32]; ++i )
            *i = 0;
          v28 = (unsigned __int16 *)v33;
          v30 = StringCbCopyA(v33, v32, (const char *)a2);
          if ( v30 < 0 )
          {
            v31 = 1684;
            goto LABEL_57;
          }
        }
        a4->hVal.QuadPart = (LONGLONG)v28;
        goto LABEL_77;
      }
    }
    if ( (unsigned int)v5 < 8 )
    {
      v9 = 1661;
      goto LABEL_7;
    }
LABEL_30:
    a4->hVal.QuadPart = *(_QWORD *)a2;
    goto LABEL_77;
  }
  if ( v8 == 17 )
  {
LABEL_22:
    if ( !(_DWORD)v5 )
    {
      v9 = 1636;
      goto LABEL_7;
    }
    a4->cVal = *a2;
    goto LABEL_77;
  }
  if ( v8 )
  {
    v12 = v8 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          v15 = v14 - 1;
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( v16 )
            {
              v17 = v16 - 5;
              if ( v17 )
              {
                v18 = v17 - 1;
                if ( v18 )
                {
                  if ( v18 == 5 )
                    goto LABEL_22;
LABEL_71:
                  v10 = -1072875800;
                  v9 = 1719;
                  goto LABEL_8;
                }
                if ( (unsigned int)v5 < 2 )
                {
                  v9 = 1671;
                  goto LABEL_7;
                }
                goto LABEL_67;
              }
              if ( (unsigned int)v5 < 4 )
              {
                v9 = 1667;
                goto LABEL_7;
              }
              goto LABEL_64;
            }
            if ( (unsigned int)v5 < 8 )
            {
              v9 = 1656;
              goto LABEL_7;
            }
            goto LABEL_30;
          }
          if ( (unsigned int)v5 < 4 )
          {
            v9 = 1652;
            goto LABEL_7;
          }
LABEL_64:
          a4->lVal = *(_DWORD *)a2;
          goto LABEL_77;
        }
LABEL_62:
        if ( (unsigned int)v5 < 4 )
        {
          v9 = 1648;
          goto LABEL_7;
        }
        goto LABEL_64;
      }
LABEL_65:
      if ( (unsigned int)v5 < 2 )
      {
        v9 = 1641;
        goto LABEL_7;
      }
LABEL_67:
      a4->iVal = *(_WORD *)a2;
    }
  }
LABEL_77:
  a4->vt = a1;
  return 0;
}

```

## disassembly

```asm
0x1800552b8  push    rbp
0x1800552ba  push    rbx
0x1800552bb  push    rsi
0x1800552bc  push    rdi
0x1800552bd  push    r12
0x1800552bf  push    r14
0x1800552c1  push    r15
0x1800552c3  mov     rbp, rsp
0x1800552c6  sub     rsp, 40h
0x1800552ca  mov     rsi, r9
0x1800552cd  mov     edi, r8d
0x1800552d0  mov     r14, rdx
0x1800552d3  movzx   r12d, cx
0x1800552d7  cmp     cs:byte_18010EC4D, 8
0x1800552de  mov     ebx, r12d
0x1800552e1  jb      short loc_180055307
0x1800552e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800552ea  mov     edx, 75h ; 'u'
0x1800552ef  mov     [rsp+40h+var_18], edi
0x1800552f3  mov     r9d, ebx
0x1800552f6  mov     qword ptr [rsp+40h+var_20], r14; int
0x1800552fb  mov     rcx, [rcx+0D8h]
0x180055302  call    WPP_SF_dqd
0x180055307  mov     ecx, 2
0x18005530c  cmp     r12w, cx
0x180055310  jb      short loc_18005533F
0x180055312  test    edi, edi
0x180055314  jz      short loc_18005531B
0x180055316  test    r14, r14
0x180055319  jnz     short loc_18005533F
0x18005531b  mov     edx, 656h; void *
0x180055320  mov     ebx, 80070057h
0x180055325  mov     rcx, [rbp+38h]; this
0x180055329  lea     r8, aAvcoreMfFrames_2; "avcore\\mf\\frameserver\\common\\fshelp"...
0x180055330  mov     r9d, ebx; char *
0x180055333  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055338  mov     eax, ebx
0x18005533a  jmp     loc_180055661
0x18005533f  cmp     ebx, 40h ; '@'
0x180055342  ja      loc_1800555E3
0x180055348  jz      loc_1800555D0
0x18005534e  cmp     ebx, 11h
0x180055351  ja      loc_180055406
0x180055357  jz      short loc_180055399
0x180055359  test    ebx, ebx
0x18005535b  jz      loc_18005565B
0x180055361  sub     ebx, 1
0x180055364  jz      loc_18005565B
0x18005536a  sub     ebx, 1
0x18005536d  jz      loc_1800555B5
0x180055373  sub     ebx, 1
0x180055376  jz      loc_18005559B
0x18005537c  sub     ebx, 1
0x18005537f  jz      short loc_1800553E8
0x180055381  sub     ebx, 1
0x180055384  jz      short loc_1800553CD
0x180055386  sub     ebx, 5
0x180055389  jz      short loc_1800553BA
0x18005538b  sub     ebx, 1
0x18005538e  jz      short loc_1800553A8
0x180055390  cmp     ebx, 5
0x180055393  jnz     loc_1800555E8
0x180055399  cmp     edi, 1
0x18005539c  jnb     short loc_1800553FB
0x18005539e  mov     edx, 664h
0x1800553a3  jmp     loc_180055320
0x1800553a8  cmp     edi, ecx
0x1800553aa  jnb     loc_1800555C3
0x1800553b0  mov     edx, 687h
0x1800553b5  jmp     loc_180055320
0x1800553ba  cmp     edi, 4
0x1800553bd  jnb     loc_1800555AA
0x1800553c3  mov     edx, 683h
0x1800553c8  jmp     loc_180055320
0x1800553cd  cmp     edi, 8
0x1800553d0  jnb     short loc_1800553DC
0x1800553d2  mov     edx, 678h
0x1800553d7  jmp     loc_180055320
0x1800553dc  mov     rax, [r14]
0x1800553df  mov     [rsi+8], rax
0x1800553e3  jmp     loc_18005565B
0x1800553e8  cmp     edi, 4
0x1800553eb  jnb     loc_1800555AA
0x1800553f1  mov     edx, 674h
0x1800553f6  jmp     loc_180055320
0x1800553fb  mov     al, [r14]
0x1800553fe  mov     [rsi+8], al
0x180055401  jmp     loc_18005565B
0x180055406  sub     ebx, 12h
0x180055409  jz      loc_1800555B5
0x18005540f  sub     ebx, 1
0x180055412  jz      loc_18005559B
0x180055418  sub     ebx, 1
0x18005541b  jz      loc_180055588
0x180055421  sub     ebx, 1
0x180055424  jz      loc_180055588
0x18005542a  sub     ebx, 1
0x18005542d  jz      loc_18005559B
0x180055433  sub     ebx, 1
0x180055436  jz      loc_18005559B
0x18005543c  sub     ebx, 7
0x18005543f  jz      loc_1800554DB
0x180055445  cmp     ebx, 1
0x180055448  jnz     loc_1800555E8
0x18005544e  mov     rdx, rdi; unsigned __int64
0x180055451  mov     [rbp+pv], 0
0x180055459  lea     r8, [rbp+pv]; unsigned __int64 *
0x18005545d  mov     rcx, r14; unsigned __int16 *
0x180055460  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180055465  mov     ebx, eax
0x180055467  test    eax, eax
0x180055469  jns     short loc_180055475
0x18005546b  mov     edx, 69Fh
0x180055470  jmp     loc_180055325
0x180055475  mov     rdi, [rbp+pv]
0x180055479  lea     rcx, [rbp+pv]
0x18005547d  lea     rdx, [rdi+1]
0x180055481  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<ushort [0]>(unsigned __int64)
0x180055486  mov     rbx, [rax]
0x180055489  mov     qword ptr [rax], 0
0x180055490  mov     rcx, [rbp+pv]; pv
0x180055494  mov     [rbp+pv], 0
0x18005549c  test    rcx, rcx
0x18005549f  jz      short loc_1800554A7
0x1800554a1  call    cs:__imp_CoTaskMemFree
0x1800554a7  test    rbx, rbx
0x1800554aa  jnz     short loc_1800554BB
0x1800554ac  mov     ebx, 8007000Eh
0x1800554b1  mov     edx, 6A1h
0x1800554b6  jmp     loc_180055325
0x1800554bb  mov     r8, r14; unsigned __int16 *
0x1800554be  lea     rdx, [rdi+1]; unsigned __int64
0x1800554c2  mov     rcx, rbx; unsigned __int16 *
0x1800554c5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800554ca  mov     edi, eax
0x1800554cc  test    eax, eax
0x1800554ce  jns     loc_180055570
0x1800554d4  mov     edx, 6A2h
0x1800554d9  jmp     short loc_18005554D
0x1800554db  mov     rdx, rdi; unsigned __int64
0x1800554de  mov     [rbp+pv], 0
0x1800554e6  lea     r8, [rbp+pv]; unsigned __int64 *
0x1800554ea  mov     rcx, r14; char *
0x1800554ed  call    ?StringCbLengthA@@YAJPEBD_KPEA_K@Z; StringCbLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800554f2  mov     ebx, eax
0x1800554f4  test    eax, eax
0x1800554f6  jns     short loc_180055502
0x1800554f8  mov     edx, 691h
0x1800554fd  jmp     loc_180055325
0x180055502  mov     rdi, [rbp+pv]
0x180055506  inc     rdi
0x180055509  mov     rcx, rdi; cb
0x18005550c  call    cs:__imp_CoTaskMemAlloc
0x180055512  test    rax, rax
0x180055515  jz      short loc_180055579
0x180055517  lea     rdx, [rdi+rax]
0x18005551b  mov     rcx, rax
0x18005551e  cmp     rax, rdx
0x180055521  jz      short loc_180055531
0x180055523  xor     r8d, r8d
0x180055526  mov     [rcx], r8b
0x180055529  inc     rcx
0x18005552c  cmp     rcx, rdx
0x18005552f  jnz     short loc_180055523
0x180055531  mov     r8, r14; char *
0x180055534  mov     rdx, rdi; unsigned __int64
0x180055537  mov     rcx, rax; char *
0x18005553a  mov     rbx, rax
0x18005553d  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180055542  mov     edi, eax
0x180055544  test    eax, eax
0x180055546  jns     short loc_180055570
0x180055548  mov     edx, 694h; void *
0x18005554d  mov     rcx, [rbp+38h]; this
0x180055551  lea     r8, aAvcoreMfFrames_2; "avcore\\mf\\frameserver\\common\\fshelp"...
0x180055558  mov     r9d, edi; char *
0x18005555b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055560  mov     rcx, rbx; pv
0x180055563  call    cs:__imp_CoTaskMemFree
0x180055569  mov     eax, edi
0x18005556b  jmp     loc_180055661
0x180055570  mov     [rsi+8], rbx
0x180055574  jmp     loc_18005565B
0x180055579  mov     ebx, 8007000Eh
0x18005557e  mov     edx, 693h
0x180055583  jmp     loc_180055325
0x180055588  cmp     edi, 8
0x18005558b  jnb     loc_1800553DC
0x180055591  mov     edx, 67Dh
0x180055596  jmp     loc_180055320
0x18005559b  cmp     edi, 4
0x18005559e  jnb     short loc_1800555AA
0x1800555a0  mov     edx, 670h
0x1800555a5  jmp     loc_180055320
0x1800555aa  mov     eax, [r14]
0x1800555ad  mov     [rsi+8], eax
0x1800555b0  jmp     loc_18005565B
0x1800555b5  cmp     edi, ecx
0x1800555b7  jnb     short loc_1800555C3
0x1800555b9  mov     edx, 669h
0x1800555be  jmp     loc_180055320
0x1800555c3  movzx   eax, word ptr [r14]
0x1800555c7  mov     [rsi+8], ax
0x1800555cb  jmp     loc_18005565B
0x1800555d0  cmp     edi, 8
0x1800555d3  jnb     loc_1800553DC
0x1800555d9  mov     edx, 6A7h
0x1800555de  jmp     loc_180055320
0x1800555e3  cmp     ebx, 41h ; 'A'
0x1800555e6  jz      short loc_1800555F7
0x1800555e8  mov     ebx, 0C00D36E8h
0x1800555ed  mov     edx, 6B7h
0x1800555f2  jmp     loc_180055325
0x1800555f7  mov     rdx, rdi
0x1800555fa  mov     [rbp+var_8], 0
0x180055602  lea     rcx, [rbp+pv]
0x180055606  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)
0x18005560b  mov     rdx, rax
0x18005560e  lea     rcx, [rbp+var_8]
0x180055612  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180055617  mov     rcx, [rbp+pv]; pv
0x18005561b  mov     [rbp+pv], 0
0x180055623  test    rcx, rcx
0x180055626  jz      short loc_18005562E
0x180055628  call    cs:__imp_CoTaskMemFree
0x18005562e  mov     rbx, [rbp+var_8]
0x180055632  test    rbx, rbx
0x180055635  jnz     short loc_180055646
0x180055637  mov     ebx, 8007000Eh
0x18005563c  mov     edx, 6AFh
0x180055641  jmp     loc_180055325
0x180055646  mov     r8, rdi; Size
0x180055649  mov     rdx, r14; Src
0x18005564c  mov     rcx, rbx; void *
0x18005564f  call    memcpy_0
0x180055654  mov     [rsi+8], edi
0x180055657  mov     [rsi+10h], rbx
0x18005565b  mov     [rsi], r12w
0x18005565f  xor     eax, eax
0x180055661  add     rsp, 40h
0x180055665  pop     r15
0x180055667  pop     r14
0x180055669  pop     r12
0x18005566b  pop     rdi
0x18005566c  pop     rsi
0x18005566d  pop     rbx
0x18005566e  pop     rbp
0x18005566f  retn
```
