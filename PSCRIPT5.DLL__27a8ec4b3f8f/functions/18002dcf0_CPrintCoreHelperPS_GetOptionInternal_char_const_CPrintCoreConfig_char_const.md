# CPrintCoreHelperPS::GetOptionInternal(char const *,CPrintCoreConfig *,char const * *)

- ea: `0x18002dcf0`
- end: `0x18002e0ba`
- name: `?GetOptionInternal@CPrintCoreHelperPS@@MEAAJPEBDPEAVCPrintCoreConfig@@PEAPEBD@Z`
- size: `970`
- prototype: `int __fastcall(CPrintCoreHelperPS *this, const char *, struct CPrintCoreConfig *, const char **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180002890`
- `0x18002d058`
- `0x18002d8a4`
- `0x18002dcf0`
- `0x180033100`
- `0x180034320`
- `0x1800343c8`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall CPrintCoreHelperPS::GetOptionInternal(
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
  char *v16; // rdi
  char near **v17; // rcx
  int v18; // r8d
  int v19; // edx
  char near **v20; // rax
  BOOL v21; // r9d
  int v22; // edx
  int v23; // ecx
  char near **v24; // rax
  int v25; // edx
  int v26; // ecx
  char near **v27; // rax
  int v28; // edx
  int v29; // ecx
  const char *v30; // rax
  char near **v31; // rcx
  int v32; // edx
  int v33; // eax
  char near **v34; // rax
  int v35; // edx
  int v36; // ecx
  char near **v37; // rax
  int v38; // edx
  int v39; // ecx
  char near **v40; // rax
  int v41; // edx
  int v42; // ecx
  char near **v43; // rax
  int v44; // edx
  int v45; // ecx
  unsigned int v46[18]; // [rsp+30h] [rbp-48h] BYREF

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
    return 2147500037LL;
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
      if ( !*(_QWORD *)a3 || !(*(__int64 (**)(void))(*((_QWORD *)a3 + 1) + 40LL))() )
        return 2147942414LL;
      v17 = &kstrPSJobTimeout;
      do
      {
        v18 = *((unsigned __int8 *)v17 + a2 - (const char *)&kstrPSJobTimeout);
        v19 = *(unsigned __int8 *)v17 - v18;
        if ( v19 )
          break;
        v17 = (char near **)((char *)v17 + 1);
      }
      while ( v18 );
      v20 = &kstrPSMaxBMPFontSize;
      v21 = v19 == 0;
      do
      {
        v22 = *((unsigned __int8 *)v20 + a2 - (const char *)&kstrPSMaxBMPFontSize);
        v23 = *(unsigned __int8 *)v20 - v22;
        if ( v23 )
          break;
        v20 = (char near **)((char *)v20 + 1);
      }
      while ( v22 );
      if ( !v23 )
        v21 = 1;
      v24 = &kstrPSWaitTimeout;
      do
      {
        v25 = *((unsigned __int8 *)v24 + a2 - (const char *)&kstrPSWaitTimeout);
        v26 = *(unsigned __int8 *)v24 - v25;
        if ( v26 )
          break;
        v24 = (char near **)((char *)v24 + 1);
      }
      while ( v25 );
      if ( !v26 )
        v21 = 1;
      v27 = &kstrPSMinOutlineFont;
      do
      {
        v28 = *((unsigned __int8 *)v27 + a2 - (const char *)&kstrPSMinOutlineFont);
        v29 = *(unsigned __int8 *)v27 - v28;
        if ( v29 )
          break;
        v27 = (char near **)((char *)v27 + 1);
      }
      while ( v28 );
      if ( !v29 )
        v21 = 1;
      if ( !strcmp((const char *)&kstrPSMemory, a2) || v21 )
      {
        v30 = (const char *)CPrintCoreConfig::PrivateAlloc(a3, 0x10u);
        *a4 = v30;
        if ( v30 )
        {
          o__ultoa_s_0();
          return 0;
        }
        return 2147942414LL;
      }
    }
    else
    {
      v31 = &kstrPSJobTimeout;
      do
      {
        v32 = *((unsigned __int8 *)v31 + a2 - (const char *)&kstrPSJobTimeout);
        v33 = *(unsigned __int8 *)v31 - v32;
        if ( v33 )
          break;
        v31 = (char near **)((char *)v31 + 1);
      }
      while ( v32 );
      if ( !v33 )
        return 2147500037LL;
      v34 = &kstrPSMaxBMPFontSize;
      do
      {
        v35 = *((unsigned __int8 *)v34 + a2 - (const char *)&kstrPSMaxBMPFontSize);
        v36 = *(unsigned __int8 *)v34 - v35;
        if ( v36 )
          break;
        v34 = (char near **)((char *)v34 + 1);
      }
      while ( v35 );
      if ( !v36 )
        return 2147500037LL;
      v37 = &kstrPSWaitTimeout;
      do
      {
        v38 = *((unsigned __int8 *)v37 + a2 - (const char *)&kstrPSWaitTimeout);
        v39 = *(unsigned __int8 *)v37 - v38;
        if ( v39 )
          break;
        v37 = (char near **)((char *)v37 + 1);
      }
      while ( v38 );
      if ( !v39 )
        return 2147500037LL;
      v40 = &kstrPSMinOutlineFont;
      do
      {
        v41 = *((unsigned __int8 *)v40 + a2 - (const char *)&kstrPSMinOutlineFont);
        v42 = *(unsigned __int8 *)v40 - v41;
        if ( v42 )
          break;
        v40 = (char near **)((char *)v40 + 1);
      }
      while ( v41 );
      if ( !v42 )
        return 2147500037LL;
      v43 = &kstrPSMemory;
      do
      {
        v44 = *((unsigned __int8 *)v43 + a2 - (const char *)&kstrPSMemory);
        v45 = *(unsigned __int8 *)v43 - v44;
        if ( v45 )
          break;
        v43 = (char near **)((char *)v43 + 1);
      }
      while ( v44 );
      if ( !v45 )
        return 2147500037LL;
    }
    return CPrintAbstractHelper::GetOptionInternal(this, a2, a3, a4);
  }
  v14 = *((_QWORD *)a3 + 2);
  if ( !v14 )
    v14 = (*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a3 + 1) + 48LL))(*(_QWORD *)a3);
  if ( (CPrintCoreConfig::GetHelperSettingsFlags(a3) & 2) == 0
    || !(unsigned int)CPrintCoreHelperPS::BIsCustomPageSizeSupported(v15, a3)
    || (*(_BYTE *)(v14 + 72) & 2) == 0
    || *(_WORD *)(v14 + 78) != 0x7FFF )
  {
    return 2147500037LL;
  }
  v46[0] = 0;
  BPSReadCustomPageSize(v14, 0, 0, 0, v46);
  v16 = (char *)CPrintCoreConfig::PrivateAlloc(a3, v46[0]);
  if ( !v16 )
    return 2147942414LL;
  if ( BPSReadCustomPageSize(v14, 0, v16, v46[0], v46) )
  {
    *a4 = v16;
    return 0;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18002dcf0  push    rbx
0x18002dcf2  push    rbp
0x18002dcf3  push    rsi
0x18002dcf4  push    rdi
0x18002dcf5  push    r14
0x18002dcf7  push    r15
0x18002dcf9  sub     rsp, 48h
0x18002dcfd  lea     rax, ?kstrPSOrientation@@3PADA; "%Orientation"
0x18002dd04  mov     rsi, rdx
0x18002dd07  sub     rdx, rax
0x18002dd0a  mov     r14, r9
0x18002dd0d  mov     rdi, r8
0x18002dd10  mov     rbp, rcx
0x18002dd13  mov     r15d, 1
0x18002dd19  movzx   r10d, byte ptr [rax]
0x18002dd1d  movzx   r8d, byte ptr [rax+rdx]
0x18002dd22  sub     r10d, r8d
0x18002dd25  jnz     short loc_18002DD2F
0x18002dd27  add     rax, r15
0x18002dd2a  test    r8d, r8d
0x18002dd2d  jnz     short loc_18002DD19
0x18002dd2f  test    r10d, r10d
0x18002dd32  jnz     short loc_18002DD9E
0x18002dd34  mov     rbx, [rdi+10h]
0x18002dd38  test    rbx, rbx
0x18002dd3b  jnz     short loc_18002DD50
0x18002dd3d  mov     rax, [rdi+8]
0x18002dd41  mov     rcx, [rdi]
0x18002dd44  mov     rax, [rax+30h]
0x18002dd48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd4d  mov     rbx, rax
0x18002dd50  mov     rcx, rdi; this
0x18002dd53  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x18002dd58  test    al, 2
0x18002dd5a  jz      loc_18002E0A7
0x18002dd60  test    [rbx+48h], r15b
0x18002dd64  jz      short loc_18002DD8D
0x18002dd66  cmp     word ptr [rbx+4Ch], 2
0x18002dd6b  jnz     short loc_18002DD8D
0x18002dd6d  movzx   eax, word ptr [rbx+44h]
0x18002dd71  lea     rcx, ?kstrPSOrientLandscape@@3PADA; "Landscape"
0x18002dd78  test    dword ptr [rax+rbx+4], 200h
0x18002dd80  lea     rax, ?kstrPSOrientRotatedLandscape@@3PADA; "RotatedLandscape"
0x18002dd87  cmovz   rax, rcx
0x18002dd8b  jmp     short loc_18002DD94
0x18002dd8d  lea     rax, ?kstrPSOrientPortrait@@3PADA; "Portrait"
0x18002dd94  mov     [r14], rax
0x18002dd97  xor     eax, eax
0x18002dd99  jmp     loc_18002E0AC
0x18002dd9e  lea     rax, ?kstrPSCustomPageSize@@3PADA; "%CustomPageSize"
0x18002dda5  mov     rcx, rsi
0x18002dda8  sub     rcx, rax
0x18002ddab  movzx   edx, byte ptr [rax]
0x18002ddae  movzx   r8d, byte ptr [rax+rcx]
0x18002ddb3  sub     edx, r8d
0x18002ddb6  jnz     short loc_18002DDC0
0x18002ddb8  add     rax, r15
0x18002ddbb  test    r8d, r8d
0x18002ddbe  jnz     short loc_18002DDAB
0x18002ddc0  test    edx, edx
0x18002ddc2  jnz     loc_18002DE83
0x18002ddc8  mov     rbx, [rdi+10h]
0x18002ddcc  test    rbx, rbx
0x18002ddcf  jnz     short loc_18002DDE4
0x18002ddd1  mov     rax, [rdi+8]
0x18002ddd5  mov     rcx, [rdi]
0x18002ddd8  mov     rax, [rax+30h]
0x18002dddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dde1  mov     rbx, rax
0x18002dde4  mov     rcx, rdi; this
0x18002dde7  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x18002ddec  test    al, 2
0x18002ddee  jz      loc_18002E0A7
0x18002ddf4  mov     rdx, rdi; struct CPrintCoreConfig *
0x18002ddf7  call    ?BIsCustomPageSizeSupported@CPrintCoreHelperPS@@AEAAHPEAVCPrintCoreConfig@@@Z; CPrintCoreHelperPS::BIsCustomPageSizeSupported(CPrintCoreConfig *)
0x18002ddfc  test    eax, eax
0x18002ddfe  jz      loc_18002E0A7
0x18002de04  test    byte ptr [rbx+48h], 2
0x18002de08  jz      loc_18002E0A7
0x18002de0e  mov     eax, 7FFFh
0x18002de13  cmp     [rbx+4Eh], ax
0x18002de17  jnz     loc_18002E0A7
0x18002de1d  lea     rax, [rsp+78h+var_48]
0x18002de22  mov     [rsp+78h+var_48], 0
0x18002de2a  xor     r9d, r9d
0x18002de2d  mov     [rsp+78h+var_58], rax
0x18002de32  xor     r8d, r8d
0x18002de35  xor     edx, edx
0x18002de37  mov     rcx, rbx
0x18002de3a  call    BPSReadCustomPageSize
0x18002de3f  mov     edx, [rsp+78h+var_48]; unsigned __int64
0x18002de43  mov     rcx, rdi; this
0x18002de46  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x18002de4b  mov     rdi, rax
0x18002de4e  test    rax, rax
0x18002de51  jz      loc_18002DFD2
0x18002de57  mov     r9d, [rsp+78h+var_48]
0x18002de5c  lea     rax, [rsp+78h+var_48]
0x18002de61  mov     r8, rdi
0x18002de64  mov     [rsp+78h+var_58], rax
0x18002de69  xor     edx, edx
0x18002de6b  mov     rcx, rbx
0x18002de6e  call    BPSReadCustomPageSize
0x18002de73  test    eax, eax
0x18002de75  jz      loc_18002E0A7
0x18002de7b  mov     [r14], rdi
0x18002de7e  jmp     loc_18002DD97
0x18002de83  mov     rcx, rdi; this
0x18002de86  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x18002de8b  test    al, 8
0x18002de8d  jz      loc_18002DFDC
0x18002de93  mov     rcx, [rdi]
0x18002de96  test    rcx, rcx
0x18002de99  jz      loc_18002DFD2
0x18002de9f  mov     rax, [rdi+8]
0x18002dea3  mov     rax, [rax+28h]
0x18002dea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002deac  mov     r10, rax
0x18002deaf  test    rax, rax
0x18002deb2  jz      loc_18002DFD2
0x18002deb8  xor     ebx, ebx
0x18002deba  lea     rcx, ?kstrPSJobTimeout@@3PADA; "%JobTimeout"
0x18002dec1  mov     r9, rsi
0x18002dec4  sub     r9, rcx
0x18002dec7  movzx   edx, byte ptr [rcx]
0x18002deca  movzx   r8d, byte ptr [rcx+r9]
0x18002decf  sub     edx, r8d
0x18002ded2  jnz     short loc_18002DEDC
0x18002ded4  add     rcx, r15
0x18002ded7  test    r8d, r8d
0x18002deda  jnz     short loc_18002DEC7
0x18002dedc  test    edx, edx
0x18002dede  jnz     short loc_18002DEE3
0x18002dee0  mov     ebx, [rax+0Ch]
0x18002dee3  xor     r9d, r9d
0x18002dee6  lea     rax, ?kstrPSMaxBMPFontSize@@3PADA; "%MaxFontSizeAsBitmap"
0x18002deed  test    edx, edx
0x18002deef  mov     r8, rsi
0x18002def2  setz    r9b
0x18002def6  sub     r8, rax
0x18002def9  movzx   ecx, byte ptr [rax]
0x18002defc  movzx   edx, byte ptr [rax+r8]
0x18002df01  sub     ecx, edx
0x18002df03  jnz     short loc_18002DF0C
0x18002df05  add     rax, r15
0x18002df08  test    edx, edx
0x18002df0a  jnz     short loc_18002DEF9
0x18002df0c  test    ecx, ecx
0x18002df0e  jnz     short loc_18002DF18
0x18002df10  movzx   ebx, word ptr [r10+16h]
0x18002df15  mov     r9d, r15d
0x18002df18  lea     rax, ?kstrPSWaitTimeout@@3PADA; "%WaitTimeout"
0x18002df1f  mov     r8, rsi
0x18002df22  sub     r8, rax
0x18002df25  movzx   ecx, byte ptr [rax]
0x18002df28  movzx   edx, byte ptr [rax+r8]
0x18002df2d  sub     ecx, edx
0x18002df2f  jnz     short loc_18002DF38
0x18002df31  add     rax, r15
0x18002df34  test    edx, edx
0x18002df36  jnz     short loc_18002DF25
0x18002df38  test    ecx, ecx
0x18002df3a  jnz     short loc_18002DF43
0x18002df3c  mov     ebx, [r10+10h]
0x18002df40  mov     r9d, r15d
0x18002df43  lea     rax, ?kstrPSMinOutlineFont@@3PADA; "%MinFontSizeAsOutline"
0x18002df4a  mov     r8, rsi
0x18002df4d  sub     r8, rax
0x18002df50  movzx   ecx, byte ptr [rax]
0x18002df53  movzx   edx, byte ptr [rax+r8]
0x18002df58  sub     ecx, edx
0x18002df5a  jnz     short loc_18002DF63
0x18002df5c  add     rax, r15
0x18002df5f  test    edx, edx
0x18002df61  jnz     short loc_18002DF50
0x18002df63  test    ecx, ecx
0x18002df65  jnz     short loc_18002DF6F
0x18002df67  movzx   ebx, word ptr [r10+14h]
0x18002df6c  mov     r9d, r15d
0x18002df6f  lea     rax, ?kstrPSMemory@@3PADA; "%PSMemory"
0x18002df76  mov     r8, rsi
0x18002df79  sub     r8, rax
0x18002df7c  movzx   ecx, byte ptr [rax]
0x18002df7f  movzx   edx, byte ptr [rax+r8]
0x18002df84  sub     ecx, edx
0x18002df86  jnz     short loc_18002DF8F
0x18002df88  add     rax, r15
0x18002df8b  test    edx, edx
0x18002df8d  jnz     short loc_18002DF7C
0x18002df8f  test    ecx, ecx
0x18002df91  jnz     short loc_18002DF9C
0x18002df93  mov     ebx, [r10+8]
0x18002df97  shr     ebx, 0Ah
0x18002df9a  jmp     short loc_18002DFA5
0x18002df9c  test    r9d, r9d
0x18002df9f  jz      loc_18002E094
0x18002dfa5  mov     esi, 10h
0x18002dfaa  mov     rcx, rdi; this
0x18002dfad  mov     edx, esi; unsigned __int64
0x18002dfaf  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x18002dfb4  mov     [r14], rax
0x18002dfb7  test    rax, rax
0x18002dfba  jz      short loc_18002DFD2
0x18002dfbc  lea     r9d, [rsi-6]
0x18002dfc0  mov     r8d, esi
0x18002dfc3  mov     rdx, rax
0x18002dfc6  mov     ecx, ebx
0x18002dfc8  call    _o__ultoa_s_0
0x18002dfcd  jmp     loc_18002DD97
0x18002dfd2  mov     eax, 8007000Eh
0x18002dfd7  jmp     loc_18002E0AC
0x18002dfdc  lea     rcx, ?kstrPSJobTimeout@@3PADA; "%JobTimeout"
0x18002dfe3  mov     r8, rsi
0x18002dfe6  sub     r8, rcx
0x18002dfe9  movzx   eax, byte ptr [rcx]
0x18002dfec  movzx   edx, byte ptr [rcx+r8]
0x18002dff1  sub     eax, edx
0x18002dff3  jnz     short loc_18002DFFC
0x18002dff5  add     rcx, r15
0x18002dff8  test    edx, edx
0x18002dffa  jnz     short loc_18002DFE9
0x18002dffc  test    eax, eax
0x18002dffe  jz      loc_18002E0A7
0x18002e004  lea     rax, ?kstrPSMaxBMPFontSize@@3PADA; "%MaxFontSizeAsBitmap"
0x18002e00b  mov     r8, rsi
0x18002e00e  sub     r8, rax
0x18002e011  movzx   ecx, byte ptr [rax]
0x18002e014  movzx   edx, byte ptr [rax+r8]
0x18002e019  sub     ecx, edx
0x18002e01b  jnz     short loc_18002E024
0x18002e01d  add     rax, r15
0x18002e020  test    edx, edx
0x18002e022  jnz     short loc_18002E011
0x18002e024  test    ecx, ecx
0x18002e026  jz      short loc_18002E0A7
0x18002e028  lea     rax, ?kstrPSWaitTimeout@@3PADA; "%WaitTimeout"
0x18002e02f  mov     r8, rsi
0x18002e032  sub     r8, rax
0x18002e035  movzx   ecx, byte ptr [rax]
0x18002e038  movzx   edx, byte ptr [rax+r8]
0x18002e03d  sub     ecx, edx
0x18002e03f  jnz     short loc_18002E048
0x18002e041  add     rax, r15
0x18002e044  test    edx, edx
0x18002e046  jnz     short loc_18002E035
0x18002e048  test    ecx, ecx
0x18002e04a  jz      short loc_18002E0A7
0x18002e04c  lea     rax, ?kstrPSMinOutlineFont@@3PADA; "%MinFontSizeAsOutline"
0x18002e053  mov     r8, rsi
0x18002e056  sub     r8, rax
0x18002e059  movzx   ecx, byte ptr [rax]
0x18002e05c  movzx   edx, byte ptr [rax+r8]
0x18002e061  sub     ecx, edx
0x18002e063  jnz     short loc_18002E06C
0x18002e065  add     rax, r15
0x18002e068  test    edx, edx
0x18002e06a  jnz     short loc_18002E059
0x18002e06c  test    ecx, ecx
0x18002e06e  jz      short loc_18002E0A7
0x18002e070  lea     rax, ?kstrPSMemory@@3PADA; "%PSMemory"
0x18002e077  mov     r8, rsi
0x18002e07a  sub     r8, rax
0x18002e07d  movzx   ecx, byte ptr [rax]
0x18002e080  movzx   edx, byte ptr [rax+r8]
0x18002e085  sub     ecx, edx
0x18002e087  jnz     short loc_18002E090
0x18002e089  add     rax, r15
0x18002e08c  test    edx, edx
0x18002e08e  jnz     short loc_18002E07D
0x18002e090  test    ecx, ecx
0x18002e092  jz      short loc_18002E0A7
0x18002e094  mov     r9, r14; char **
0x18002e097  mov     r8, rdi; struct CPrintCoreConfig *
0x18002e09a  mov     rdx, rsi; char *
0x18002e09d  mov     rcx, rbp; this
0x18002e0a0  call    ?GetOptionInternal@CPrintAbstractHelper@@MEAAJPEBDPEAVCPrintCoreConfig@@PEAPEBD@Z; CPrintAbstractHelper::GetOptionInternal(char const *,CPrintCoreConfig *,char const * *)
0x18002e0a5  jmp     short loc_18002E0AC
0x18002e0a7  mov     eax, 80004005h
0x18002e0ac  add     rsp, 48h
0x18002e0b0  pop     r15
0x18002e0b2  pop     r14
0x18002e0b4  pop     rdi
0x18002e0b5  pop     rsi
0x18002e0b6  pop     rbp
0x18002e0b7  pop     rbx
0x18002e0b8  retn
```
