# CPrintCoreHelperPS::GetOptionInternal(char const *,CPrintCoreConfig *,char const * *)

- ea: `0x18002c8d0`
- end: `0x18002cc99`
- name: `?GetOptionInternal@CPrintCoreHelperPS@@MEAAJPEBDPEAVCPrintCoreConfig@@PEAPEBD@Z`
- size: `969`
- prototype: `__int64 __fastcall(CPrintCoreHelperPS *__hidden this, const char *, struct CPrintCoreConfig *, const char **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180002830`
- `0x18002bc60`
- `0x18002c484`
- `0x18002c8d0`
- `0x180031aa0`
- `0x180032cb0`
- `0x180032d54`
- `0x18005d010`

## pseudocode

```c
int __fastcall CPrintCoreHelperPS::GetOptionInternal(
        CPrintCoreHelperPS *this,
        const char *a2,
        struct CPrintCoreConfig *a3,
        const char **a4)
{
  __int64 v8; // rbx
  char near **v9; // rax
  char near **v11; // rax
  int v12; // r8d
  int v13; // edx
  __int64 v14; // rbx
  CPrintCoreHelperPS *v15; // rcx
  const char *v16; // rdi
  __int64 v17; // rax
  __int64 v18; // r10
  unsigned int v19; // ebx
  char near **v20; // rcx
  int v21; // r8d
  int v22; // edx
  char near **v23; // rax
  BOOL v24; // r9d
  int v25; // edx
  int v26; // ecx
  char near **v27; // rax
  int v28; // edx
  int v29; // ecx
  char near **v30; // rax
  int v31; // edx
  int v32; // ecx
  const char *v33; // rax
  char near **v34; // rcx
  int v35; // edx
  int v36; // eax
  char near **v37; // rax
  int v38; // edx
  int v39; // ecx
  char near **v40; // rax
  int v41; // edx
  int v42; // ecx
  char near **v43; // rax
  int v44; // edx
  int v45; // ecx
  char near **v46; // rax
  int v47; // edx
  int v48; // ecx
  unsigned int v49[18]; // [rsp+30h] [rbp-48h] BYREF

  if ( !strcmp((const char *)&kstrPSOrientation, a2) )
  {
    v8 = *((_QWORD *)a3 + 2);
    if ( !v8 )
      v8 = (*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a3 + 1) + 48LL))(*(_QWORD *)a3);
    if ( (CPrintCoreConfig::GetHelperSettingsFlags(a3) & 2) != 0 )
    {
      if ( (*(_BYTE *)(v8 + 72) & 1) != 0 && *(_WORD *)(v8 + 76) == 2 )
      {
        v9 = &kstrPSOrientRotatedLandscape;
        if ( (*(_DWORD *)(*(unsigned __int16 *)(v8 + 68) + v8 + 4) & 0x200) == 0 )
          v9 = &kstrPSOrientLandscape;
      }
      else
      {
        v9 = &kstrPSOrientPortrait;
      }
      *a4 = (const char *)v9;
      return 0;
    }
    return -2147467259;
  }
  v11 = &kstrPSCustomPageSize;
  do
  {
    v12 = *((unsigned __int8 *)v11 + a2 - (const char *)&kstrPSCustomPageSize);
    v13 = *(unsigned __int8 *)v11 - v12;
    if ( v13 )
      break;
    v11 = (char near **)((char *)v11 + 1);
  }
  while ( v12 );
  if ( v13 )
  {
    if ( (CPrintCoreConfig::GetHelperSettingsFlags(a3) & 8) != 0 )
    {
      if ( !*(_QWORD *)a3 )
        return -2147024882;
      v17 = (*(__int64 (**)(void))(*((_QWORD *)a3 + 1) + 40LL))();
      v18 = v17;
      if ( !v17 )
        return -2147024882;
      v19 = 0;
      v20 = &kstrPSJobTimeout;
      do
      {
        v21 = *((unsigned __int8 *)v20 + a2 - (const char *)&kstrPSJobTimeout);
        v22 = *(unsigned __int8 *)v20 - v21;
        if ( v22 )
          break;
        v20 = (char near **)((char *)v20 + 1);
      }
      while ( v21 );
      if ( !v22 )
        v19 = *(_DWORD *)(v17 + 12);
      v23 = &kstrPSMaxBMPFontSize;
      v24 = v22 == 0;
      do
      {
        v25 = *((unsigned __int8 *)v23 + a2 - (const char *)&kstrPSMaxBMPFontSize);
        v26 = *(unsigned __int8 *)v23 - v25;
        if ( v26 )
          break;
        v23 = (char near **)((char *)v23 + 1);
      }
      while ( v25 );
      if ( !v26 )
      {
        v19 = *(unsigned __int16 *)(v18 + 22);
        v24 = 1;
      }
      v27 = &kstrPSWaitTimeout;
      do
      {
        v28 = *((unsigned __int8 *)v27 + a2 - (const char *)&kstrPSWaitTimeout);
        v29 = *(unsigned __int8 *)v27 - v28;
        if ( v29 )
          break;
        v27 = (char near **)((char *)v27 + 1);
      }
      while ( v28 );
      if ( !v29 )
      {
        v19 = *(_DWORD *)(v18 + 16);
        v24 = 1;
      }
      v30 = &kstrPSMinOutlineFont;
      do
      {
        v31 = *((unsigned __int8 *)v30 + a2 - (const char *)&kstrPSMinOutlineFont);
        v32 = *(unsigned __int8 *)v30 - v31;
        if ( v32 )
          break;
        v30 = (char near **)((char *)v30 + 1);
      }
      while ( v31 );
      if ( !v32 )
      {
        v19 = *(unsigned __int16 *)(v18 + 20);
        v24 = 1;
      }
      if ( !strcmp((const char *)&kstrPSMemory, a2) )
      {
        v19 = *(_DWORD *)(v18 + 8) >> 10;
        goto LABEL_52;
      }
      if ( v24 )
      {
LABEL_52:
        v33 = (const char *)CPrintCoreConfig::PrivateAlloc(a3, 0x10u);
        *a4 = v33;
        if ( v33 )
        {
          o__ultoa_s_0(v19, v33, 16, 10);
          return 0;
        }
        return -2147024882;
      }
    }
    else
    {
      v34 = &kstrPSJobTimeout;
      do
      {
        v35 = *((unsigned __int8 *)v34 + a2 - (const char *)&kstrPSJobTimeout);
        v36 = *(unsigned __int8 *)v34 - v35;
        if ( v36 )
          break;
        v34 = (char near **)((char *)v34 + 1);
      }
      while ( v35 );
      if ( !v36 )
        return -2147467259;
      v37 = &kstrPSMaxBMPFontSize;
      do
      {
        v38 = *((unsigned __int8 *)v37 + a2 - (const char *)&kstrPSMaxBMPFontSize);
        v39 = *(unsigned __int8 *)v37 - v38;
        if ( v39 )
          break;
        v37 = (char near **)((char *)v37 + 1);
      }
      while ( v38 );
      if ( !v39 )
        return -2147467259;
      v40 = &kstrPSWaitTimeout;
      do
      {
        v41 = *((unsigned __int8 *)v40 + a2 - (const char *)&kstrPSWaitTimeout);
        v42 = *(unsigned __int8 *)v40 - v41;
        if ( v42 )
          break;
        v40 = (char near **)((char *)v40 + 1);
      }
      while ( v41 );
      if ( !v42 )
        return -2147467259;
      v43 = &kstrPSMinOutlineFont;
      do
      {
        v44 = *((unsigned __int8 *)v43 + a2 - (const char *)&kstrPSMinOutlineFont);
        v45 = *(unsigned __int8 *)v43 - v44;
        if ( v45 )
          break;
        v43 = (char near **)((char *)v43 + 1);
      }
      while ( v44 );
      if ( !v45 )
        return -2147467259;
      v46 = &kstrPSMemory;
      do
      {
        v47 = *((unsigned __int8 *)v46 + a2 - (const char *)&kstrPSMemory);
        v48 = *(unsigned __int8 *)v46 - v47;
        if ( v48 )
          break;
        v46 = (char near **)((char *)v46 + 1);
      }
      while ( v47 );
      if ( !v48 )
        return -2147467259;
    }
    return CPrintAbstractHelper::GetOptionInternal(this, a2, a3, a4);
  }
  v14 = *((_QWORD *)a3 + 2);
  if ( !v14 )
    v14 = (*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a3 + 1) + 48LL))(*(_QWORD *)a3);
  if ( (CPrintCoreConfig::GetHelperSettingsFlags(a3) & 2) == 0
    || !CPrintCoreHelperPS::BIsCustomPageSizeSupported(v15, a3)
    || (*(_BYTE *)(v14 + 72) & 2) == 0
    || *(_WORD *)(v14 + 78) != 0x7FFF )
  {
    return -2147467259;
  }
  v49[0] = 0;
  BPSReadCustomPageSize(v14, 0, 0, 0, v49);
  v16 = (const char *)CPrintCoreConfig::PrivateAlloc(a3, v49[0]);
  if ( !v16 )
    return -2147024882;
  if ( (unsigned int)BPSReadCustomPageSize(v14, 0, v16, v49[0], v49) )
  {
    *a4 = v16;
    return 0;
  }
  return -2147467259;
}

```

## disassembly

```asm
0x18002c8d0  push    rbx
0x18002c8d2  push    rbp
0x18002c8d3  push    rsi
0x18002c8d4  push    rdi
0x18002c8d5  push    r14
0x18002c8d7  push    r15
0x18002c8d9  sub     rsp, 48h
0x18002c8dd  lea     rax, ?kstrPSOrientation@@3PADA; "%Orientation"
0x18002c8e4  mov     rsi, rdx
0x18002c8e7  sub     rdx, rax
0x18002c8ea  mov     r14, r9
0x18002c8ed  mov     rdi, r8
0x18002c8f0  mov     rbp, rcx
0x18002c8f3  mov     r15d, 1
0x18002c8f9  movzx   r10d, byte ptr [rax]
0x18002c8fd  movzx   r8d, byte ptr [rax+rdx]
0x18002c902  sub     r10d, r8d
0x18002c905  jnz     short loc_18002C90F
0x18002c907  add     rax, r15
0x18002c90a  test    r8d, r8d
0x18002c90d  jnz     short loc_18002C8F9
0x18002c90f  test    r10d, r10d
0x18002c912  jnz     short loc_18002C97E
0x18002c914  mov     rbx, [rdi+10h]
0x18002c918  test    rbx, rbx
0x18002c91b  jnz     short loc_18002C930
0x18002c91d  mov     rax, [rdi+8]
0x18002c921  mov     rcx, [rdi]
0x18002c924  mov     rax, [rax+30h]
0x18002c928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c92d  mov     rbx, rax
0x18002c930  mov     rcx, rdi; this
0x18002c933  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x18002c938  test    al, 2
0x18002c93a  jz      loc_18002CC87
0x18002c940  test    [rbx+48h], r15b
0x18002c944  jz      short loc_18002C96D
0x18002c946  cmp     word ptr [rbx+4Ch], 2
0x18002c94b  jnz     short loc_18002C96D
0x18002c94d  movzx   eax, word ptr [rbx+44h]
0x18002c951  lea     rcx, ?kstrPSOrientLandscape@@3PADA; "Landscape"
0x18002c958  test    dword ptr [rax+rbx+4], 200h
0x18002c960  lea     rax, ?kstrPSOrientRotatedLandscape@@3PADA; "RotatedLandscape"
0x18002c967  cmovz   rax, rcx
0x18002c96b  jmp     short loc_18002C974
0x18002c96d  lea     rax, ?kstrPSOrientPortrait@@3PADA; "Portrait"
0x18002c974  mov     [r14], rax
0x18002c977  xor     eax, eax
0x18002c979  jmp     loc_18002CC8C
0x18002c97e  lea     rax, ?kstrPSCustomPageSize@@3PADA; "%CustomPageSize"
0x18002c985  mov     rcx, rsi
0x18002c988  sub     rcx, rax
0x18002c98b  movzx   edx, byte ptr [rax]
0x18002c98e  movzx   r8d, byte ptr [rax+rcx]
0x18002c993  sub     edx, r8d
0x18002c996  jnz     short loc_18002C9A0
0x18002c998  add     rax, r15
0x18002c99b  test    r8d, r8d
0x18002c99e  jnz     short loc_18002C98B
0x18002c9a0  test    edx, edx
0x18002c9a2  jnz     loc_18002CA63
0x18002c9a8  mov     rbx, [rdi+10h]
0x18002c9ac  test    rbx, rbx
0x18002c9af  jnz     short loc_18002C9C4
0x18002c9b1  mov     rax, [rdi+8]
0x18002c9b5  mov     rcx, [rdi]
0x18002c9b8  mov     rax, [rax+30h]
0x18002c9bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9c1  mov     rbx, rax
0x18002c9c4  mov     rcx, rdi; this
0x18002c9c7  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x18002c9cc  test    al, 2
0x18002c9ce  jz      loc_18002CC87
0x18002c9d4  mov     rdx, rdi; struct CPrintCoreConfig *
0x18002c9d7  call    ?BIsCustomPageSizeSupported@CPrintCoreHelperPS@@AEAAHPEAVCPrintCoreConfig@@@Z; CPrintCoreHelperPS::BIsCustomPageSizeSupported(CPrintCoreConfig *)
0x18002c9dc  test    eax, eax
0x18002c9de  jz      loc_18002CC87
0x18002c9e4  test    byte ptr [rbx+48h], 2
0x18002c9e8  jz      loc_18002CC87
0x18002c9ee  mov     eax, 7FFFh
0x18002c9f3  cmp     [rbx+4Eh], ax
0x18002c9f7  jnz     loc_18002CC87
0x18002c9fd  lea     rax, [rsp+78h+var_48]
0x18002ca02  mov     [rsp+78h+var_48], 0
0x18002ca0a  xor     r9d, r9d
0x18002ca0d  mov     [rsp+78h+var_58], rax
0x18002ca12  xor     r8d, r8d
0x18002ca15  xor     edx, edx
0x18002ca17  mov     rcx, rbx
0x18002ca1a  call    BPSReadCustomPageSize
0x18002ca1f  mov     edx, [rsp+78h+var_48]; unsigned __int64
0x18002ca23  mov     rcx, rdi; this
0x18002ca26  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x18002ca2b  mov     rdi, rax
0x18002ca2e  test    rax, rax
0x18002ca31  jz      loc_18002CBB2
0x18002ca37  mov     r9d, [rsp+78h+var_48]
0x18002ca3c  lea     rax, [rsp+78h+var_48]
0x18002ca41  mov     r8, rdi
0x18002ca44  mov     [rsp+78h+var_58], rax
0x18002ca49  xor     edx, edx
0x18002ca4b  mov     rcx, rbx
0x18002ca4e  call    BPSReadCustomPageSize
0x18002ca53  test    eax, eax
0x18002ca55  jz      loc_18002CC87
0x18002ca5b  mov     [r14], rdi
0x18002ca5e  jmp     loc_18002C977
0x18002ca63  mov     rcx, rdi; this
0x18002ca66  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x18002ca6b  test    al, 8
0x18002ca6d  jz      loc_18002CBBC
0x18002ca73  mov     rcx, [rdi]
0x18002ca76  test    rcx, rcx
0x18002ca79  jz      loc_18002CBB2
0x18002ca7f  mov     rax, [rdi+8]
0x18002ca83  mov     rax, [rax+28h]
0x18002ca87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca8c  mov     r10, rax
0x18002ca8f  test    rax, rax
0x18002ca92  jz      loc_18002CBB2
0x18002ca98  xor     ebx, ebx
0x18002ca9a  lea     rcx, ?kstrPSJobTimeout@@3PADA; "%JobTimeout"
0x18002caa1  mov     r9, rsi
0x18002caa4  sub     r9, rcx
0x18002caa7  movzx   edx, byte ptr [rcx]
0x18002caaa  movzx   r8d, byte ptr [rcx+r9]
0x18002caaf  sub     edx, r8d
0x18002cab2  jnz     short loc_18002CABC
0x18002cab4  add     rcx, r15
0x18002cab7  test    r8d, r8d
0x18002caba  jnz     short loc_18002CAA7
0x18002cabc  test    edx, edx
0x18002cabe  jnz     short loc_18002CAC3
0x18002cac0  mov     ebx, [rax+0Ch]
0x18002cac3  xor     r9d, r9d
0x18002cac6  lea     rax, ?kstrPSMaxBMPFontSize@@3PADA; "%MaxFontSizeAsBitmap"
0x18002cacd  test    edx, edx
0x18002cacf  mov     r8, rsi
0x18002cad2  setz    r9b
0x18002cad6  sub     r8, rax
0x18002cad9  movzx   ecx, byte ptr [rax]
0x18002cadc  movzx   edx, byte ptr [rax+r8]
0x18002cae1  sub     ecx, edx
0x18002cae3  jnz     short loc_18002CAEC
0x18002cae5  add     rax, r15
0x18002cae8  test    edx, edx
0x18002caea  jnz     short loc_18002CAD9
0x18002caec  test    ecx, ecx
0x18002caee  jnz     short loc_18002CAF8
0x18002caf0  movzx   ebx, word ptr [r10+16h]
0x18002caf5  mov     r9d, r15d
0x18002caf8  lea     rax, ?kstrPSWaitTimeout@@3PADA; "%WaitTimeout"
0x18002caff  mov     r8, rsi
0x18002cb02  sub     r8, rax
0x18002cb05  movzx   ecx, byte ptr [rax]
0x18002cb08  movzx   edx, byte ptr [rax+r8]
0x18002cb0d  sub     ecx, edx
0x18002cb0f  jnz     short loc_18002CB18
0x18002cb11  add     rax, r15
0x18002cb14  test    edx, edx
0x18002cb16  jnz     short loc_18002CB05
0x18002cb18  test    ecx, ecx
0x18002cb1a  jnz     short loc_18002CB23
0x18002cb1c  mov     ebx, [r10+10h]
0x18002cb20  mov     r9d, r15d
0x18002cb23  lea     rax, ?kstrPSMinOutlineFont@@3PADA; "%MinFontSizeAsOutline"
0x18002cb2a  mov     r8, rsi
0x18002cb2d  sub     r8, rax
0x18002cb30  movzx   ecx, byte ptr [rax]
0x18002cb33  movzx   edx, byte ptr [rax+r8]
0x18002cb38  sub     ecx, edx
0x18002cb3a  jnz     short loc_18002CB43
0x18002cb3c  add     rax, r15
0x18002cb3f  test    edx, edx
0x18002cb41  jnz     short loc_18002CB30
0x18002cb43  test    ecx, ecx
0x18002cb45  jnz     short loc_18002CB4F
0x18002cb47  movzx   ebx, word ptr [r10+14h]
0x18002cb4c  mov     r9d, r15d
0x18002cb4f  lea     rax, ?kstrPSMemory@@3PADA; "%PSMemory"
0x18002cb56  mov     r8, rsi
0x18002cb59  sub     r8, rax
0x18002cb5c  movzx   ecx, byte ptr [rax]
0x18002cb5f  movzx   edx, byte ptr [rax+r8]
0x18002cb64  sub     ecx, edx
0x18002cb66  jnz     short loc_18002CB6F
0x18002cb68  add     rax, r15
0x18002cb6b  test    edx, edx
0x18002cb6d  jnz     short loc_18002CB5C
0x18002cb6f  test    ecx, ecx
0x18002cb71  jnz     short loc_18002CB7C
0x18002cb73  mov     ebx, [r10+8]
0x18002cb77  shr     ebx, 0Ah
0x18002cb7a  jmp     short loc_18002CB85
0x18002cb7c  test    r9d, r9d
0x18002cb7f  jz      loc_18002CC74
0x18002cb85  mov     esi, 10h
0x18002cb8a  mov     rcx, rdi; this
0x18002cb8d  mov     edx, esi; unsigned __int64
0x18002cb8f  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x18002cb94  mov     [r14], rax
0x18002cb97  test    rax, rax
0x18002cb9a  jz      short loc_18002CBB2
0x18002cb9c  lea     r9d, [rsi-6]
0x18002cba0  mov     r8d, esi
0x18002cba3  mov     rdx, rax
0x18002cba6  mov     ecx, ebx
0x18002cba8  call    _o__ultoa_s_0
0x18002cbad  jmp     loc_18002C977
0x18002cbb2  mov     eax, 8007000Eh
0x18002cbb7  jmp     loc_18002CC8C
0x18002cbbc  lea     rcx, ?kstrPSJobTimeout@@3PADA; "%JobTimeout"
0x18002cbc3  mov     r8, rsi
0x18002cbc6  sub     r8, rcx
0x18002cbc9  movzx   eax, byte ptr [rcx]
0x18002cbcc  movzx   edx, byte ptr [rcx+r8]
0x18002cbd1  sub     eax, edx
0x18002cbd3  jnz     short loc_18002CBDC
0x18002cbd5  add     rcx, r15
0x18002cbd8  test    edx, edx
0x18002cbda  jnz     short loc_18002CBC9
0x18002cbdc  test    eax, eax
0x18002cbde  jz      loc_18002CC87
0x18002cbe4  lea     rax, ?kstrPSMaxBMPFontSize@@3PADA; "%MaxFontSizeAsBitmap"
0x18002cbeb  mov     r8, rsi
0x18002cbee  sub     r8, rax
0x18002cbf1  movzx   ecx, byte ptr [rax]
0x18002cbf4  movzx   edx, byte ptr [rax+r8]
0x18002cbf9  sub     ecx, edx
0x18002cbfb  jnz     short loc_18002CC04
0x18002cbfd  add     rax, r15
0x18002cc00  test    edx, edx
0x18002cc02  jnz     short loc_18002CBF1
0x18002cc04  test    ecx, ecx
0x18002cc06  jz      short loc_18002CC87
0x18002cc08  lea     rax, ?kstrPSWaitTimeout@@3PADA; "%WaitTimeout"
0x18002cc0f  mov     r8, rsi
0x18002cc12  sub     r8, rax
0x18002cc15  movzx   ecx, byte ptr [rax]
0x18002cc18  movzx   edx, byte ptr [rax+r8]
0x18002cc1d  sub     ecx, edx
0x18002cc1f  jnz     short loc_18002CC28
0x18002cc21  add     rax, r15
0x18002cc24  test    edx, edx
0x18002cc26  jnz     short loc_18002CC15
0x18002cc28  test    ecx, ecx
0x18002cc2a  jz      short loc_18002CC87
0x18002cc2c  lea     rax, ?kstrPSMinOutlineFont@@3PADA; "%MinFontSizeAsOutline"
0x18002cc33  mov     r8, rsi
0x18002cc36  sub     r8, rax
0x18002cc39  movzx   ecx, byte ptr [rax]
0x18002cc3c  movzx   edx, byte ptr [rax+r8]
0x18002cc41  sub     ecx, edx
0x18002cc43  jnz     short loc_18002CC4C
0x18002cc45  add     rax, r15
0x18002cc48  test    edx, edx
0x18002cc4a  jnz     short loc_18002CC39
0x18002cc4c  test    ecx, ecx
0x18002cc4e  jz      short loc_18002CC87
0x18002cc50  lea     rax, ?kstrPSMemory@@3PADA; "%PSMemory"
0x18002cc57  mov     r8, rsi
0x18002cc5a  sub     r8, rax
0x18002cc5d  movzx   ecx, byte ptr [rax]
0x18002cc60  movzx   edx, byte ptr [rax+r8]
0x18002cc65  sub     ecx, edx
0x18002cc67  jnz     short loc_18002CC70
0x18002cc69  add     rax, r15
0x18002cc6c  test    edx, edx
0x18002cc6e  jnz     short loc_18002CC5D
0x18002cc70  test    ecx, ecx
0x18002cc72  jz      short loc_18002CC87
0x18002cc74  mov     r9, r14; char **
0x18002cc77  mov     r8, rdi; struct CPrintCoreConfig *
0x18002cc7a  mov     rdx, rsi; char *
0x18002cc7d  mov     rcx, rbp; this
0x18002cc80  call    ?GetOptionInternal@CPrintAbstractHelper@@MEAAJPEBDPEAVCPrintCoreConfig@@PEAPEBD@Z; CPrintAbstractHelper::GetOptionInternal(char const *,CPrintCoreConfig *,char const * *)
0x18002cc85  jmp     short loc_18002CC8C
0x18002cc87  mov     eax, 80004005h
0x18002cc8c  add     rsp, 48h
0x18002cc90  pop     r15
0x18002cc92  pop     r14
0x18002cc94  pop     rdi
0x18002cc95  pop     rsi
0x18002cc96  pop     rbp
0x18002cc97  pop     rbx
0x18002cc98  retn
```
