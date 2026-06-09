# SerializePropVariant(tagPROPVARIANT const *,ulong *,uchar * *,unsigned __int64 *)

- ea: `0x1800633a4`
- end: `0x1800638dc`
- name: `?SerializePropVariant@@YAJPEBUtagPROPVARIANT@@PEAKPEAPEAEPEA_K@Z`
- size: `1336`
- prototype: `__int64 __fastcall(struct tagPROPVARIANT *, unsigned int *, LARGE_INTEGER **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180032d9c`

## callees

- `0x180010da8`
- `0x18001b950`
- `0x18001ba30`
- `0x18001f2b0`
- `0x18003f78c`
- `0x1800633a4`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800636fc`
- `OLEAUT32!__imp_SysStringLen` at `0x1800636fc`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18006351a`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18006351a`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18006354c`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18006354c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180063575`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180063575`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180063600`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180063600`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006384b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006384b`

## string_xrefs

- `0x18006346b`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x1800634e2`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180063533`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SerializePropVariant(
        struct tagPROPVARIANT *a1,
        unsigned int *a2,
        LARGE_INTEGER **a3,
        unsigned __int64 *a4)
{
  unsigned __int16 *v4; // r11
  SAFEARRAY **p_parray; // r14
  LARGE_INTEGER *p_hVal; // r15
  VARTYPE vt; // di
  unsigned int v9; // r10d
  BYTE **v10; // r12
  unsigned __int64 v11; // rdi
  BYTE *v12; // rcx
  int v13; // esi
  int v14; // r10d
  __int64 v15; // rdx
  unsigned int v17; // r15d
  LARGE_INTEGER *v18; // rsi
  unsigned __int16 *v19; // rcx
  int v20; // eax
  unsigned int v21; // r14d
  unsigned int v22; // r14d
  __int64 v23; // rdx
  HRESULT UBound; // ebx
  SAFEARRAY *v25; // rcx
  void *v26; // rcx
  LONG v27; // eax
  __int128 v28; // xmm0
  BYTE *pData; // xmm1_8
  LARGE_INTEGER *v30; // rsi
  __int64 v31; // rbx
  BYTE **p_pData; // rdx
  __int16 v33; // r8
  OLECHAR *bstrVal; // rcx
  UINT v35; // eax
  __int64 v36; // rbx
  __int64 v37; // rbx
  LARGE_INTEGER *v38; // rcx
  __int64 v39; // rax
  size_t v40; // r8
  int v41; // [rsp+20h] [rbp-38h]
  int v42; // [rsp+20h] [rbp-38h]
  unsigned int v43; // [rsp+28h] [rbp-30h]
  VARTYPE v44; // [rsp+30h] [rbp-28h]
  LONG plUbound; // [rsp+34h] [rbp-24h] BYREF
  LONG rgIndices[2]; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int64 v47; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int16 *v48[2]; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]

  v4 = 0;
  p_parray = &a1->parray;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  p_hVal = &a1->hVal;
  vt = a1->vt;
  v44 = vt;
  *(_QWORD *)rgIndices = &a1->hVal;
  if ( vt != 4127 )
  {
    LODWORD(v47) = 1;
    LODWORD(v48[0]) = 3;
    if ( vt == 8196 )
    {
      if ( SafeArrayGetDim(*p_parray) != 1 )
      {
        v23 = 586;
        goto LABEL_17;
      }
      if ( SafeArrayGetElemsize(*p_parray) != 4 )
      {
        v23 = 587;
        goto LABEL_17;
      }
      v25 = *p_parray;
      plUbound = 0;
      UBound = SafeArrayGetUBound(v25, 1u, &plUbound);
      if ( UBound < 0 )
      {
        v23 = 589;
        goto LABEL_18;
      }
      v27 = plUbound;
      if ( plUbound < 0 )
      {
        UBound = -2147024882;
        v23 = 590;
        goto LABEL_18;
      }
      ++plUbound;
      v11 = 4LL * (v27 + 1) + 24;
      UBound = CTCoAllocPolicy::Alloc(v26, 1u, v11, (void **)rgIndices);
      if ( UBound < 0 )
      {
        v23 = 599;
        goto LABEL_18;
      }
      p_hVal = *(LARGE_INTEGER **)rgIndices;
      v28 = *(_OWORD *)&a1->vt;
      rgIndices[0] = 0;
      *(_OWORD *)&p_hVal->LowPart = v28;
      pData = a1->bstrblobVal.pData;
      v30 = p_hVal + 3;
      p_hVal[2].QuadPart = (LONGLONG)pData;
      if ( plUbound > 0 )
      {
        while ( 1 )
        {
          UBound = SafeArrayGetElement(a1->parray, rgIndices, v30);
          if ( UBound < 0 )
            break;
          v30 = (LARGE_INTEGER *)((char *)v30 + 4);
          if ( ++rgIndices[0] >= plUbound )
            goto LABEL_30;
        }
        v23 = 608;
        goto LABEL_18;
      }
LABEL_30:
      v31 = v11;
LABEL_84:
      v22 = (unsigned int)v48[0];
      goto LABEL_86;
    }
    p_pData = &a1->bstrblobVal.pData;
    v33 = vt & 0x1000;
    if ( (vt & 0x1000) != 0 )
    {
      p_hVal = (LARGE_INTEGER *)*p_pData;
      vt &= ~0x1000u;
      v44 = vt;
      if ( vt == 30 || vt == 65 || (LODWORD(v47) = *(_DWORD *)p_parray, vt == 8) )
      {
        v23 = 624;
        goto LABEL_17;
      }
      p_parray = &a1->parray;
    }
    if ( vt <= 0x40u )
    {
      if ( vt != 64 )
      {
        if ( vt > 0xBu )
        {
          switch ( vt )
          {
            case 0xDu:
              goto LABEL_80;
            case 0x11u:
              v31 = 1;
              goto LABEL_82;
            case 0x12u:
              v31 = 2;
              goto LABEL_82;
            case 0x13u:
              v22 = 4;
              v31 = 4;
              v11 = 4;
LABEL_86:
              if ( p_hVal )
              {
                v18 = (LARGE_INTEGER *)CoTaskMemAlloc(v11);
                if ( v18 )
                {
                  if ( v22 == 1 || v22 == 4 || v22 == 3 && v44 == 8196 )
                  {
                    v40 = v31;
                    v38 = v18;
                  }
                  else
                  {
                    v38 = v18 + 1;
                    v18->QuadPart = 0;
                    LOWORD(v18->LowPart) = a1->vt;
                    v39 = (int)v47;
                    v18->HighPart = v47;
                    v40 = v31 * v39;
                  }
                  memcpy_0(v38, p_hVal, v40);
                  goto LABEL_97;
                }
                UBound = -2147024882;
                v23 = 756;
LABEL_18:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v23,
                  (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
                  (const char *)(unsigned int)UBound,
                  v41);
                return (unsigned int)UBound;
              }
              v23 = 751;
LABEL_17:
              UBound = -2147024809;
              goto LABEL_18;
          }
          if ( vt != 20 && vt != 21 )
          {
            if ( vt == 30 )
            {
              p_hVal = (LARGE_INTEGER *)a1->hVal.QuadPart;
              if ( !p_hVal )
              {
                v23 = 689;
                goto LABEL_17;
              }
              v37 = -1;
              do
                ++v37;
              while ( *((_BYTE *)&p_hVal->LowPart + v37) );
              v31 = v37 + 1;
              goto LABEL_82;
            }
            if ( vt == 31 )
            {
              p_hVal = (LARGE_INTEGER *)a1->hVal.QuadPart;
              if ( !p_hVal )
              {
                v23 = 699;
                goto LABEL_17;
              }
              v22 = 1;
              v36 = -1;
              do
                ++v36;
              while ( *((_WORD *)&p_hVal->LowPart + v36) );
              v11 = 2 * v36 + 2;
              v31 = v11;
              goto LABEL_86;
            }
            goto LABEL_80;
          }
        }
        else
        {
          if ( vt == 11 )
            goto LABEL_49;
          v31 = 2;
          if ( vt == 2 )
          {
LABEL_82:
            if ( vt == 8196 )
            {
              v11 = v31;
              v22 = 3;
              goto LABEL_86;
            }
            v11 = v31 * (int)v47 + 8;
            goto LABEL_84;
          }
          if ( vt == 3 || vt == 4 )
          {
LABEL_49:
            v31 = 4;
            goto LABEL_82;
          }
          if ( vt != 5 && vt != 6 && vt != 7 )
          {
            if ( vt == 8 )
            {
              bstrVal = a1->bstrVal;
              if ( !bstrVal )
              {
                v23 = 668;
                goto LABEL_17;
              }
              v35 = SysStringLen(bstrVal);
              p_hVal = (LARGE_INTEGER *)a1->hVal.QuadPart;
              v31 = 2LL * (v35 + 1);
              goto LABEL_82;
            }
            if ( vt == 10 )
              goto LABEL_49;
LABEL_80:
            UBound = -2147023266;
            v23 = 728;
            goto LABEL_18;
          }
        }
      }
      v31 = 8;
      goto LABEL_82;
    }
    if ( vt == 65 )
    {
      v31 = *(unsigned int *)p_parray;
      p_hVal = (LARGE_INTEGER *)*p_pData;
      goto LABEL_82;
    }
    if ( vt == 72 )
    {
      v31 = 16;
      if ( !v33 )
        p_hVal = (LARGE_INTEGER *)*p_parray;
      goto LABEL_82;
    }
    goto LABEL_80;
  }
  v9 = 0;
  v10 = &a1->bstrblobVal.pData;
  v11 = 2;
  if ( *(_DWORD *)p_parray )
  {
    while ( 1 )
    {
      v12 = *v10;
      v48[0] = v4;
      v13 = StringCbLengthW(*(const unsigned __int16 **)&v12[8 * v9], 0x7FFFFFFFu, (unsigned __int64 *)v48);
      if ( v13 < 0 )
        break;
      v9 = v14 + 1;
      v11 += (unsigned __int64)(v48[0] + 1);
      if ( v9 >= *(_DWORD *)p_parray )
        goto LABEL_5;
    }
    v15 = 567;
    goto LABEL_8;
  }
LABEL_5:
  v13 = CTCoAllocPolicy::Alloc(a1, 1u, v11, (void **)rgIndices);
  if ( v13 < 0 )
  {
    v15 = 572;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
      (const char *)(unsigned int)v13,
      v41);
    return (unsigned int)v13;
  }
  v17 = 0;
  v18 = *(LARGE_INTEGER **)rgIndices;
  v19 = *(unsigned __int16 **)rgIndices;
  v48[0] = *(unsigned __int16 **)rgIndices;
  if ( !*(_DWORD *)p_parray )
  {
LABEL_12:
    v22 = 7;
LABEL_97:
    *a2 = v22;
    *a3 = v18;
    *a4 = v11;
    return 0;
  }
  while ( 1 )
  {
    v20 = StringCbCopyExW(v19, v11, *(const unsigned __int16 **)&(*v10)[8 * v17], v48, &v47, v43);
    v21 = v20;
    if ( v20 < 0 )
      break;
    ++v17;
    v19 = ++v48[0];
    if ( v17 >= a1->lVal )
      goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x242,
    (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
    (const char *)(unsigned int)v20,
    v42);
  return v21;
}

```

## disassembly

```asm
0x1800633a4  mov     rax, rsp
0x1800633a7  mov     [rax+20h], r9
0x1800633ab  mov     [rax+18h], r8
0x1800633af  mov     [rax+10h], rdx
0x1800633b3  mov     [rax+8], rcx
0x1800633b7  push    rbp
0x1800633b8  push    rbx
0x1800633b9  push    rsi
0x1800633ba  push    rdi
0x1800633bb  push    r12
0x1800633bd  push    r13
0x1800633bf  push    r14
0x1800633c1  push    r15
0x1800633c3  mov     rbp, rsp
0x1800633c6  sub     rsp, 58h
0x1800633ca  xor     r11d, r11d
0x1800633cd  lea     r14, [rcx+8]
0x1800633d1  mov     [rdx], r11d
0x1800633d4  mov     eax, 101Fh
0x1800633d9  mov     [r8], r11
0x1800633dc  mov     rsi, rcx
0x1800633df  mov     [r9], r11
0x1800633e2  mov     r15, r14
0x1800633e5  movzx   edi, word ptr [rcx]
0x1800633e8  lea     r13d, [r11+1]
0x1800633ec  mov     [rbp+var_28], di
0x1800633f0  mov     qword ptr [rbp+rgIndices], r14
0x1800633f4  cmp     di, ax
0x1800633f7  jnz     loc_1800634FE
0x1800633fd  lea     ebx, [r11+2]
0x180063401  mov     r10d, r11d
0x180063404  lea     r12, [rcx+10h]
0x180063408  mov     edi, ebx
0x18006340a  cmp     [r14], r11d
0x18006340d  jbe     short loc_180063444
0x18006340f  mov     rcx, [r12]
0x180063413  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180063417  mov     eax, r10d
0x18006341a  mov     edx, 7FFFFFFFh; unsigned __int64
0x18006341f  mov     [rbp+var_10], r11
0x180063423  mov     rcx, [rcx+rax*8]; unsigned __int16 *
0x180063427  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006342c  mov     esi, eax
0x18006342e  test    eax, eax
0x180063430  js      short loc_180063462
0x180063432  mov     rax, [rbp+var_10]
0x180063436  add     r10d, r13d
0x180063439  add     rax, rbx
0x18006343c  add     rdi, rax
0x18006343f  cmp     r10d, [r14]
0x180063442  jb      short loc_18006340F
0x180063444  lea     r9, [rbp+rgIndices]; void **
0x180063448  mov     r8, rdi; unsigned __int64
0x18006344b  mov     edx, r13d; unsigned int
0x18006344e  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180063453  mov     esi, eax
0x180063455  xor     eax, eax
0x180063457  test    esi, esi
0x180063459  jns     short loc_180063481
0x18006345b  mov     edx, 23Ch
0x180063460  jmp     short loc_180063467
0x180063462  mov     edx, 237h; void *
0x180063467  mov     rcx, [rbp+40h]; this
0x18006346b  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180063472  mov     r9d, esi; char *
0x180063475  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006347a  mov     eax, esi
0x18006347c  jmp     loc_1800638CB
0x180063481  mov     r15d, eax
0x180063484  mov     rsi, qword ptr [rbp+rgIndices]
0x180063488  mov     rcx, rsi; unsigned __int16 *
0x18006348b  mov     [rbp+var_10], rcx
0x18006348f  cmp     [r14], eax
0x180063492  jbe     short loc_1800634D3
0x180063494  mov     r8, [r12]
0x180063498  lea     rdx, [rbp+var_18]
0x18006349c  mov     eax, r15d
0x18006349f  lea     r9, [rbp+var_10]; unsigned __int16 **
0x1800634a3  mov     [rsp+58h+var_38], rdx; int
0x1800634a8  mov     rdx, rdi; unsigned __int64
0x1800634ab  mov     r8, [r8+rax*8]; unsigned __int16 *
0x1800634af  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800634b4  mov     r14d, eax
0x1800634b7  test    eax, eax
0x1800634b9  js      short loc_1800634DE
0x1800634bb  mov     rcx, [rbp+var_10]
0x1800634bf  add     r15d, r13d
0x1800634c2  mov     rax, [rbp+arg_0]
0x1800634c6  add     rcx, rbx
0x1800634c9  mov     [rbp+var_10], rcx
0x1800634cd  cmp     r15d, [rax+8]
0x1800634d1  jb      short loc_180063494
0x1800634d3  mov     r14d, 7
0x1800634d9  jmp     loc_1800638B4
0x1800634de  mov     rcx, [rbp+40h]; this
0x1800634e2  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x1800634e9  mov     r9d, r14d; char *
0x1800634ec  mov     edx, 242h; void *
0x1800634f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800634f6  mov     eax, r14d
0x1800634f9  jmp     loc_1800638CB
0x1800634fe  mov     eax, 2004h
0x180063503  mov     dword ptr [rbp+var_18], r13d
0x180063507  mov     dword ptr [rbp+var_10], 3
0x18006350e  cmp     di, ax
0x180063511  jnz     loc_18006362F
0x180063517  mov     rcx, [r14]; psa
0x18006351a  call    cs:__imp_SafeArrayGetDim
0x180063520  cmp     eax, r13d
0x180063523  jz      short loc_180063549
0x180063525  mov     edx, 24Ah; void *
0x18006352a  mov     ebx, 80070057h
0x18006352f  mov     rcx, [rbp+40h]; this
0x180063533  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x18006353a  mov     r9d, ebx; char *
0x18006353d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063542  mov     eax, ebx
0x180063544  jmp     loc_1800638CB
0x180063549  mov     rcx, [r14]; psa
0x18006354c  call    cs:__imp_SafeArrayGetElemsize
0x180063552  mov     r12d, 4
0x180063558  cmp     eax, r12d
0x18006355b  jz      short loc_180063564
0x18006355d  mov     edx, 24Bh
0x180063562  jmp     short loc_18006352A
0x180063564  mov     rcx, [r14]; psa
0x180063567  lea     r8, [rbp+plUbound]; plUbound
0x18006356b  mov     edx, r13d; nDim
0x18006356e  mov     [rbp+plUbound], 0
0x180063575  call    cs:__imp_SafeArrayGetUBound
0x18006357b  xor     r14d, r14d
0x18006357e  mov     ebx, eax
0x180063580  test    eax, eax
0x180063582  jns     short loc_18006358B
0x180063584  mov     edx, 24Dh
0x180063589  jmp     short loc_18006352F
0x18006358b  mov     eax, [rbp+plUbound]
0x18006358e  test    eax, eax
0x180063590  jns     short loc_18006359E
0x180063592  mov     ebx, 8007000Eh
0x180063597  mov     edx, 24Eh
0x18006359c  jmp     short loc_18006352F
0x18006359e  add     eax, r13d
0x1800635a1  lea     r9, [rbp+rgIndices]; void **
0x1800635a5  mov     [rbp+plUbound], eax
0x1800635a8  mov     edx, r13d; unsigned int
0x1800635ab  cdqe
0x1800635ad  lea     rdi, ds:18h[rax*4]
0x1800635b5  mov     r8, rdi; unsigned __int64
0x1800635b8  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800635bd  mov     ebx, eax
0x1800635bf  test    eax, eax
0x1800635c1  jns     short loc_1800635CD
0x1800635c3  mov     edx, 257h
0x1800635c8  jmp     loc_18006352F
0x1800635cd  mov     r15, qword ptr [rbp+rgIndices]
0x1800635d1  movups  xmm0, xmmword ptr [rsi]
0x1800635d4  mov     [rbp+rgIndices], r14d
0x1800635d8  movups  xmmword ptr [r15], xmm0
0x1800635dc  movsd   xmm1, qword ptr [rsi+10h]
0x1800635e1  lea     rsi, [r15+18h]
0x1800635e5  movsd   qword ptr [r15+10h], xmm1
0x1800635eb  cmp     [rbp+plUbound], r14d
0x1800635ef  jle     short loc_18006361D
0x1800635f1  mov     rax, [rbp+arg_0]
0x1800635f5  lea     rdx, [rbp+rgIndices]; rgIndices
0x1800635f9  mov     r8, rsi; pv
0x1800635fc  mov     rcx, [rax+8]; psa
0x180063600  call    cs:__imp_SafeArrayGetElement
0x180063606  mov     ebx, eax
0x180063608  test    eax, eax
0x18006360a  js      short loc_180063625
0x18006360c  mov     eax, [rbp+rgIndices]
0x18006360f  add     rsi, r12
0x180063612  add     eax, r13d
0x180063615  mov     [rbp+rgIndices], eax
0x180063618  cmp     eax, [rbp+plUbound]
0x18006361b  jl      short loc_1800635F1
0x18006361d  mov     rbx, rdi
0x180063620  jmp     loc_18006382A
0x180063625  mov     edx, 260h
0x18006362a  jmp     loc_18006352F
0x18006362f  mov     r9d, 41h ; 'A'
0x180063635  lea     rdx, [rsi+10h]
0x180063639  mov     ecx, 1000h
0x18006363e  movzx   r8d, di
0x180063642  lea     r10d, [r9-39h]
0x180063646  and     r8w, cx
0x18006364a  jz      short loc_180063677
0x18006364c  mov     r15, [rdx]
0x18006364f  mov     eax, 0EFFFh
0x180063654  and     di, ax
0x180063657  mov     [rbp+var_28], di
0x18006365b  cmp     di, 1Eh
0x18006365f  jz      short loc_1800636DF
0x180063661  cmp     di, r9w
0x180063665  jz      short loc_1800636DF
0x180063667  mov     eax, [r14]
0x18006366a  mov     dword ptr [rbp+var_18], eax
0x18006366d  cmp     di, r10w
0x180063671  jz      short loc_1800636DF
0x180063673  lea     r14, [rsi+8]
0x180063677  movzx   ecx, di
0x18006367a  mov     r12d, 4
0x180063680  cmp     ecx, 40h ; '@'
0x180063683  ja      loc_1800637C8
0x180063689  jz      loc_180063718
0x18006368f  cmp     ecx, 0Bh
0x180063692  ja      loc_180063720
0x180063698  jz      short loc_1800636D7
0x18006369a  lea     ebx, [r12-2]
0x18006369f  sub     ecx, ebx
0x1800636a1  jz      loc_180063815
0x1800636a7  sub     ecx, r13d
0x1800636aa  jz      short loc_1800636D7
0x1800636ac  sub     ecx, r13d
0x1800636af  jz      short loc_1800636D7
0x1800636b1  sub     ecx, r13d
0x1800636b4  jz      short loc_180063718
0x1800636b6  sub     ecx, r13d
0x1800636b9  jz      short loc_180063718
0x1800636bb  sub     ecx, r13d
0x1800636be  jz      short loc_180063718
0x1800636c0  sub     ecx, r13d
0x1800636c3  jz      short loc_1800636E9
0x1800636c5  sub     ecx, r13d
0x1800636c8  jz      loc_180063800
0x1800636ce  cmp     ecx, r13d
0x1800636d1  jnz     loc_180063800
0x1800636d7  mov     rbx, r12
0x1800636da  jmp     loc_180063815
0x1800636df  mov     edx, 270h
0x1800636e4  jmp     loc_18006352A
0x1800636e9  mov     rcx, [rsi+8]; pbstr
0x1800636ed  test    rcx, rcx
0x1800636f0  jnz     short loc_1800636FC
0x1800636f2  mov     edx, 29Ch
0x1800636f7  jmp     loc_18006352A
0x1800636fc  call    cs:__imp_SysStringLen
0x180063702  mov     r15, [rsi+8]
0x180063706  mov     r10d, 8
0x18006370c  lea     ebx, [rax+r13]
0x180063710  add     rbx, rbx
0x180063713  jmp     loc_180063815
0x180063718  mov     rbx, r10
0x18006371b  jmp     loc_180063815
0x180063720  sub     ecx, 0Dh
0x180063723  jz      loc_180063800
0x180063729  sub     ecx, r12d
0x18006372c  jz      loc_1800637C3
0x180063732  sub     ecx, r13d
0x180063735  jz      loc_1800637BC
0x18006373b  sub     ecx, r13d
0x18006373e  jz      short loc_1800637B1
0x180063740  sub     ecx, r13d
0x180063743  jz      short loc_180063718
0x180063745  sub     ecx, r13d
0x180063748  jz      short loc_180063718
0x18006374a  sub     ecx, 9
0x18006374d  jz      short loc_18006378C
0x18006374f  cmp     ecx, r13d
0x180063752  jnz     loc_180063800
0x180063758  mov     r15, [rsi+8]
0x18006375c  test    r15, r15
0x18006375f  jnz     short loc_18006376B
0x180063761  mov     edx, 2BBh
0x180063766  jmp     loc_18006352A
0x18006376b  mov     r14d, r13d
0x18006376e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180063772  inc     rbx
0x180063775  cmp     [r15+rbx*2], r11w
0x18006377a  jnz     short loc_180063772
0x18006377c  lea     rdi, ds:2[rbx*2]
0x180063784  mov     rbx, rdi
0x180063787  jmp     loc_180063839
0x18006378c  mov     r15, [rsi+8]
0x180063790  test    r15, r15
0x180063793  jnz     short loc_18006379F
0x180063795  mov     edx, 2B1h
0x18006379a  jmp     loc_18006352A
0x18006379f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800637a3  inc     rbx
0x1800637a6  cmp     [r15+rbx], r11b
0x1800637aa  jnz     short loc_1800637A3
0x1800637ac  inc     rbx
0x1800637af  jmp     short loc_180063815
0x1800637b1  mov     r14d, r12d
0x1800637b4  mov     rbx, r12
0x1800637b7  mov     rdi, r12
0x1800637ba  jmp     short loc_180063839
0x1800637bc  mov     ebx, 2
0x1800637c1  jmp     short loc_180063815
0x1800637c3  mov     rbx, r13
0x1800637c6  jmp     short loc_180063815
0x1800637c8  sub     ecx, r9d
0x1800637cb  jz      short loc_18006380F
0x1800637cd  sub     ecx, r13d
0x1800637d0  jz      short loc_180063800
0x1800637d2  sub     ecx, r13d
0x1800637d5  jz      short loc_180063800
  ... truncated ...
```
