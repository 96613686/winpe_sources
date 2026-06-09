# CPrintCoreHelperPS::GetPrivateOptions(CPrintCoreConfig *)

- ea: `0x18002cca0`
- end: `0x18002d0d9`
- name: `?GetPrivateOptions@CPrintCoreHelperPS@@MEAAPEAUtagPrivateFeaturesAccessTable@@PEAVCPrintCoreConfig@@@Z`
- size: `1081`
- prototype: `struct tagPrivateFeaturesAccessTable *(CPrintCoreHelperPS *__hidden this, struct CPrintCoreConfig *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002c484`
- `0x18002cca0`
- `0x18002e6b0`
- `0x180032d10`
- `0x180032d54`
- `0x18005d010`

## string_xrefs

- `0x18002d05a`: `%OutputProtocol`

## pseudocode

```c
struct tagPrivateFeaturesAccessTable *__fastcall CPrintCoreHelperPS::GetPrivateOptions(
        CPrintCoreHelperPS *this,
        struct CPrintCoreConfig *a2)
{
  unsigned int v4; // r13d
  __int64 v6; // rbp
  __int64 v7; // r14
  __int64 v8; // r14
  int v9; // ebx
  int v10; // eax
  int v11; // r9d
  struct tagPrivateFeaturesAccessTable near *v12; // rax
  struct tagPrivateFeaturesAccessTable near **v13; // r14
  int v14; // r12d
  CPrintCoreHelperPS *v15; // rcx
  int v16; // r15d
  unsigned int v17; // r8d
  int v18; // ebx
  int v19; // eax
  int v20; // ebp
  int v21; // eax
  int v22; // ebp
  _QWORD *v23; // rax
  _QWORD *v24; // rdx
  int v25; // ebx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rcx
  unsigned int v31; // edx
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rcx
  struct PrivateOptionAccessTable near **v39; // rax
  int v40; // ebx
  char *v41; // r12
  __int64 i; // r15
  struct _UIINFO *UIInfo; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rax
  int v50; // [rsp+70h] [rbp+8h] BYREF
  int v51; // [rsp+78h] [rbp+10h]

  v4 = 0;
  if ( !(*(unsigned int (__fastcall **)(_QWORD))(*((_QWORD *)this + 134) + 16LL))(*(_QWORD *)a2) )
    return 0;
  if ( !*((_QWORD *)this + 146) )
  {
    v50 = 0;
    LODWORD(v6) = 0;
    if ( *((_DWORD *)CPrintCoreConfig::GetUIInfo(a2) + 54) )
    {
      v7 = *((unsigned int *)CPrintCoreConfig::GetUIInfo(a2) + 54);
      v8 = *((_QWORD *)CPrintCoreConfig::GetUIInfo(a2) + 41) + v7;
    }
    else
    {
      v8 = 0;
    }
    v9 = *((_DWORD *)CPrintCoreConfig::GetUIInfo(a2) + 75);
    v10 = (**((__int64 (__fastcall ***)(_QWORD))a2 + 1))(*(_QWORD *)a2);
    VGetEnabledEMFFeatures(v10, v9, v8 != 0, v11, (__int64)&v50);
    if ( *((_DWORD *)CPrintCoreConfig::GetUIInfo(a2) + 20) == 1 )
    {
      v12 = gpPScriptLevel1Features;
      v13 = &gpPScriptLevel1Features;
    }
    else if ( *((_DWORD *)CPrintCoreConfig::GetUIInfo(a2) + 20) == 2 )
    {
      v12 = gpPScriptLevel2Features;
      v13 = &gpPScriptLevel2Features;
    }
    else
    {
      v12 = gpPScriptLevel3Features;
      v13 = &gpPScriptLevel3Features;
    }
    if ( v12 )
    {
      do
        v6 = (unsigned int)(v6 + 1);
      while ( v13[3 * v6] );
    }
    v14 = *((_DWORD *)CPrintCoreConfig::GetUIInfo(a2) + 28);
    v16 = CPrintCoreHelperPS::BIsCustomPageSizeSupported(v15, a2);
    v17 = 0;
    v18 = v6 + (v16 != 0) + 1;
    if ( (_DWORD)gpPScriptEMFFeatures )
    {
      do
      {
        v19 = v18 + 1;
        if ( (v50 & *(_DWORD *)(&gpPScriptEMFFeatures + 4 * v17)) != *((_DWORD *)&gpPScriptEMFFeatures + 8 * v17) )
          v19 = v18;
        ++v17;
        v18 = v19;
      }
      while ( *((_DWORD *)&gpPScriptEMFFeatures + 8 * v17) );
    }
    v20 = *((_DWORD *)CPrintCoreConfig::GetUIInfo(a2) + 35);
    v21 = v18 + 1;
    v22 = v20 & 8;
    if ( v22 )
      v21 = v18;
    v23 = CPrintCoreConfig::PrivateAlloc(a2, 24LL * (unsigned int)(v21 + 2));
    *((_QWORD *)this + 146) = v23;
    v24 = v23;
    if ( v23 )
    {
      v25 = 0;
      if ( *v13 )
      {
        do
        {
          v26 = v25++;
          v27 = 3 * v26;
          v28 = *((_QWORD *)this + 146);
          *(_OWORD *)(v28 + 8 * v27) = *(_OWORD *)&v13[v27];
          *(_QWORD *)(v28 + 8 * v27 + 16) = v13[v27 + 2];
        }
        while ( v13[3 * v25] );
        v24 = (_QWORD *)*((_QWORD *)this + 146);
      }
      v51 = v25;
      if ( v16 )
      {
        v29 = v25++;
        v30 = 3 * v29;
        v24[v30] = &kstrPSCustomPageSize;
        *(_QWORD *)(*((_QWORD *)this + 146) + 8 * v30 + 16) = &gpPScriptEmptyOptionsTable;
      }
      v31 = 0;
      if ( (_DWORD)gpPScriptEMFFeatures )
      {
        do
        {
          v32 = 4LL * v31;
          if ( (v50 & *(_DWORD *)((_BYTE *)&gpPScriptEMFFeatures + v32 * 8)) == *(_DWORD *)((char *)&gpPScriptEMFFeatures
                                                                                          + v32 * 8) )
          {
            v33 = v25++;
            v34 = 3 * v33;
            v35 = *((_QWORD *)this + 146);
            *(_OWORD *)(v35 + 8 * v34) = *(_OWORD *)&(&off_180071E78)[v32];
            *(_QWORD *)(v35 + 8 * v34 + 16) = (&off_180071E88)[v32];
          }
          ++v31;
        }
        while ( *((_DWORD *)&gpPScriptEMFFeatures + 8 * v31) );
      }
      if ( !v22 )
      {
        v36 = v25++;
        v37 = 3 * v36;
        *(_QWORD *)(*((_QWORD *)this + 146) + 8 * v37) = &kstrPSNegative;
        *(_DWORD *)(*((_QWORD *)this + 146) + 8 * v37 + 8) = 0;
        *(_QWORD *)(*((_QWORD *)this + 146) + 8 * v37 + 16) = &gpPScriptNegImageOptionsTable;
      }
      v38 = 3LL * v25;
      *(_QWORD *)(*((_QWORD *)this + 146) + 8 * v38) = &kstrTrueTypeFormat;
      *(_DWORD *)(*((_QWORD *)this + 146) + 8 * v38 + 8) = 0;
      v39 = &gpPScriptTrueTypeOptionsTableNative;
      if ( v14 != 2 )
        v39 = &gpPScriptTrueTypeOptionsTable;
      *(_QWORD *)(*((_QWORD *)this + 146) + 24LL * v25 + 16) = v39;
      v40 = v25 + 1;
      v41 = (char *)CPrintCoreConfig::PrivateAlloc(a2, 0xA0u);
      if ( v41 )
      {
        for ( i = 0; i != 5; ++i )
        {
          if ( *(&gpPScriptOutputProtocolTable + 4 * i) )
          {
            v50 = dword_180072A4C[8 * i];
            if ( v50 )
            {
              UIInfo = CPrintCoreConfig::GetUIInfo(a2);
              if ( (v50 & *((_DWORD *)UIInfo + 25)) == 0 )
                continue;
            }
          }
          v44 = 32LL * v4++;
          *(_OWORD *)&v41[v44] = *((_OWORD *)&gpPScriptOutputProtocolTable + 2 * i);
          *(_OWORD *)&v41[v44 + 16] = xmmword_180072A50[2 * i];
        }
        v45 = v40++;
        v46 = 3 * v45;
        *(_QWORD *)(*((_QWORD *)this + 146) + 8 * v46) = &kstrPSOutputProtocol;
        *(_DWORD *)(*((_QWORD *)this + 146) + 8 * v46 + 8) = 1;
        *(_QWORD *)(*((_QWORD *)this + 146) + 8 * v46 + 16) = v41;
      }
      v47 = 3LL * v51;
      v48 = 3LL * v40;
      v49 = *((_QWORD *)this + 146);
      *(_OWORD *)(v49 + 8 * v48) = *(_OWORD *)&v13[3 * v51];
      *(_QWORD *)(v49 + 8 * v48 + 16) = v13[v47 + 2];
    }
  }
  return (struct tagPrivateFeaturesAccessTable *)*((_QWORD *)this + 146);
}

```

## disassembly

```asm
0x18002cca0  mov     [rsp+arg_10], rbx
0x18002cca5  push    rbp
0x18002cca6  push    rsi
0x18002cca7  push    rdi
0x18002cca8  push    r12
0x18002ccaa  push    r13
0x18002ccac  push    r14
0x18002ccae  push    r15
0x18002ccb0  sub     rsp, 30h
0x18002ccb4  mov     rax, [rcx+430h]
0x18002ccbb  mov     rdi, rcx
0x18002ccbe  mov     rcx, [rdx]
0x18002ccc1  mov     rsi, rdx
0x18002ccc4  mov     rax, [rax+10h]
0x18002ccc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cccd  xor     r13d, r13d
0x18002ccd0  test    eax, eax
0x18002ccd2  jnz     short loc_18002CCDB
0x18002ccd4  xor     eax, eax
0x18002ccd6  jmp     loc_18002D0C1
0x18002ccdb  cmp     [rdi+490h], r13
0x18002cce2  jnz     loc_18002D0BA
0x18002cce8  mov     rcx, rsi; this
0x18002cceb  mov     [rsp+68h+arg_0], r13d
0x18002ccf0  mov     ebp, r13d
0x18002ccf3  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002ccf8  cmp     [rax+0D8h], r13d
0x18002ccff  jz      short loc_18002CD21
0x18002cd01  mov     rcx, rsi; this
0x18002cd04  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002cd09  mov     rcx, rsi; this
0x18002cd0c  mov     r14d, [rax+0D8h]
0x18002cd13  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002cd18  add     r14, [rax+148h]
0x18002cd1f  jmp     short loc_18002CD24
0x18002cd21  mov     r14, r13
0x18002cd24  mov     rcx, rsi; this
0x18002cd27  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002cd2c  mov     rcx, [rsi]
0x18002cd2f  mov     ebx, [rax+12Ch]
0x18002cd35  mov     rax, [rsi+8]
0x18002cd39  mov     rax, [rax]
0x18002cd3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd41  lea     rcx, [rsp+68h+arg_0]
0x18002cd46  mov     r8d, r13d
0x18002cd49  mov     [rsp+68h+var_48], rcx
0x18002cd4e  test    r14, r14
0x18002cd51  mov     rcx, rax
0x18002cd54  mov     edx, ebx
0x18002cd56  setnz   r8b
0x18002cd5a  call    VGetEnabledEMFFeatures
0x18002cd5f  mov     rcx, rsi; this
0x18002cd62  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002cd67  cmp     dword ptr [rax+50h], 1
0x18002cd6b  jnz     short loc_18002CD7D
0x18002cd6d  mov     rax, cs:?gpPScriptLevel1Features@@3PAUtagPrivateFeaturesAccessTable@@A; tagPrivateFeaturesAccessTable near * gpPScriptLevel1Features
0x18002cd74  lea     r14, ?gpPScriptLevel1Features@@3PAUtagPrivateFeaturesAccessTable@@A; tagPrivateFeaturesAccessTable near * gpPScriptLevel1Features
0x18002cd7b  jmp     short loc_18002CDA9
0x18002cd7d  mov     rcx, rsi; this
0x18002cd80  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002cd85  cmp     dword ptr [rax+50h], 2
0x18002cd89  jnz     short loc_18002CD9B
0x18002cd8b  mov     rax, cs:?gpPScriptLevel2Features@@3PAUtagPrivateFeaturesAccessTable@@A; tagPrivateFeaturesAccessTable near * gpPScriptLevel2Features
0x18002cd92  lea     r14, ?gpPScriptLevel2Features@@3PAUtagPrivateFeaturesAccessTable@@A; tagPrivateFeaturesAccessTable near * gpPScriptLevel2Features
0x18002cd99  jmp     short loc_18002CDA9
0x18002cd9b  mov     rax, cs:?gpPScriptLevel3Features@@3PAUtagPrivateFeaturesAccessTable@@A; tagPrivateFeaturesAccessTable near * gpPScriptLevel3Features
0x18002cda2  lea     r14, ?gpPScriptLevel3Features@@3PAUtagPrivateFeaturesAccessTable@@A; tagPrivateFeaturesAccessTable near * gpPScriptLevel3Features
0x18002cda9  test    rax, rax
0x18002cdac  jz      short loc_18002CDC1
0x18002cdae  inc     ebp
0x18002cdb0  lea     rcx, ds:0[rbp*2]
0x18002cdb8  add     rcx, rbp
0x18002cdbb  cmp     [r14+rcx*8], r13
0x18002cdbf  jnz     short loc_18002CDAE
0x18002cdc1  mov     rcx, rsi; this
0x18002cdc4  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002cdc9  mov     rdx, rsi; struct CPrintCoreConfig *
0x18002cdcc  mov     r12d, [rax+70h]
0x18002cdd0  call    ?BIsCustomPageSizeSupported@CPrintCoreHelperPS@@AEAAHPEAVCPrintCoreConfig@@@Z; CPrintCoreHelperPS::BIsCustomPageSizeSupported(CPrintCoreConfig *)
0x18002cdd5  mov     ecx, eax
0x18002cdd7  lea     r9, cs:180000000h
0x18002cdde  neg     ecx
0x18002cde0  mov     r15d, eax
0x18002cde3  mov     r8d, r13d
0x18002cde6  sbb     edx, edx
0x18002cde8  neg     edx
0x18002cdea  lea     ebx, [rdx+1]
0x18002cded  add     ebx, ebp
0x18002cdef  cmp     cs:?gpPScriptEMFFeatures@@3PAU_unnamed_type_gpPScriptEMFFeatures_@@A, r13d; _unnamed_type_gpPScriptEMFFeatures_ near * gpPScriptEMFFeatures
0x18002cdf6  jz      short loc_18002CE2B
0x18002cdf8  mov     eax, r8d
0x18002cdfb  shl     rax, 5
0x18002cdff  mov     edx, [rax+r9+71E70h]
0x18002ce07  lea     eax, [rbx+1]
0x18002ce0a  mov     ecx, edx
0x18002ce0c  and     ecx, [rsp+68h+arg_0]
0x18002ce10  cmp     ecx, edx
0x18002ce12  cmovnz  eax, ebx
0x18002ce15  inc     r8d
0x18002ce18  mov     ebx, eax
0x18002ce1a  mov     eax, r8d
0x18002ce1d  shl     rax, 5
0x18002ce21  cmp     [rax+r9+71E70h], r13d
0x18002ce29  jnz     short loc_18002CDF8
0x18002ce2b  mov     rcx, rsi; this
0x18002ce2e  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002ce33  mov     rcx, rsi; this
0x18002ce36  mov     ebp, [rax+8Ch]
0x18002ce3c  lea     eax, [rbx+1]
0x18002ce3f  and     ebp, 8
0x18002ce42  cmovnz  eax, ebx
0x18002ce45  add     eax, 2
0x18002ce48  lea     rdx, [rax+rax*2]
0x18002ce4c  shl     rdx, 3; unsigned __int64
0x18002ce50  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x18002ce55  mov     [rdi+490h], rax
0x18002ce5c  mov     rdx, rax
0x18002ce5f  test    rax, rax
0x18002ce62  jz      loc_18002D0BA
0x18002ce68  mov     ebx, r13d
0x18002ce6b  cmp     [r14], r13
0x18002ce6e  jz      short loc_18002CEAA
0x18002ce70  movsxd  rax, ebx
0x18002ce73  inc     ebx
0x18002ce75  lea     rcx, [rax+rax*2]
0x18002ce79  mov     rax, [rdi+490h]
0x18002ce80  movups  xmm0, xmmword ptr [r14+rcx*8]
0x18002ce85  movups  xmmword ptr [rax+rcx*8], xmm0
0x18002ce89  movsd   xmm1, qword ptr [r14+rcx*8+10h]
0x18002ce90  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x18002ce96  movsxd  rax, ebx
0x18002ce99  lea     rcx, [rax+rax*2]
0x18002ce9d  cmp     [r14+rcx*8], r13
0x18002cea1  jnz     short loc_18002CE70
0x18002cea3  mov     rdx, [rdi+490h]
0x18002ceaa  mov     [rsp+68h+arg_8], ebx
0x18002ceae  test    r15d, r15d
0x18002ceb1  jz      short loc_18002CEDA
0x18002ceb3  movsxd  rax, ebx
0x18002ceb6  inc     ebx
0x18002ceb8  lea     rcx, [rax+rax*2]
0x18002cebc  lea     rax, ?kstrPSCustomPageSize@@3PADA; "%CustomPageSize"
0x18002cec3  mov     [rdx+rcx*8], rax
0x18002cec7  lea     rdx, ?gpPScriptEmptyOptionsTable@@3PAUPrivateOptionAccessTable@@A; PrivateOptionAccessTable near * gpPScriptEmptyOptionsTable
0x18002cece  mov     rax, [rdi+490h]
0x18002ced5  mov     [rax+rcx*8+10h], rdx
0x18002ceda  cmp     cs:?gpPScriptEMFFeatures@@3PAU_unnamed_type_gpPScriptEMFFeatures_@@A, r13d; _unnamed_type_gpPScriptEMFFeatures_ near * gpPScriptEMFFeatures
0x18002cee1  mov     edx, r13d
0x18002cee4  jz      short loc_18002CF45
0x18002cee6  lea     r9, cs:180000000h
0x18002ceed  mov     r8d, edx
0x18002cef0  shl     r8, 5
0x18002cef4  mov     ecx, [r8+r9+71E70h]
0x18002cefc  mov     eax, ecx
0x18002cefe  and     eax, [rsp+68h+arg_0]
0x18002cf02  cmp     eax, ecx
0x18002cf04  jnz     short loc_18002CF33
0x18002cf06  movups  xmm0, xmmword ptr [r8+r9+71E78h]
0x18002cf0f  movsxd  rax, ebx
0x18002cf12  inc     ebx
0x18002cf14  lea     rcx, [rax+rax*2]
0x18002cf18  mov     rax, [rdi+490h]
0x18002cf1f  movups  xmmword ptr [rax+rcx*8], xmm0
0x18002cf23  movsd   xmm1, qword ptr [r8+r9+71E88h]
0x18002cf2d  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x18002cf33  inc     edx
0x18002cf35  mov     eax, edx
0x18002cf37  shl     rax, 5
0x18002cf3b  cmp     [rax+r9+71E70h], r13d
0x18002cf43  jnz     short loc_18002CEED
0x18002cf45  test    ebp, ebp
0x18002cf47  jnz     short loc_18002CF83
0x18002cf49  movsxd  rax, ebx
0x18002cf4c  lea     rdx, ?kstrPSNegative@@3PADA; "%Negative"
0x18002cf53  inc     ebx
0x18002cf55  lea     rcx, [rax+rax*2]
0x18002cf59  mov     rax, [rdi+490h]
0x18002cf60  mov     [rax+rcx*8], rdx
0x18002cf64  lea     rdx, ?gpPScriptNegImageOptionsTable@@3PAUPrivateOptionAccessTable@@A; PrivateOptionAccessTable near * gpPScriptNegImageOptionsTable
0x18002cf6b  mov     rax, [rdi+490h]
0x18002cf72  mov     [rax+rcx*8+8], r13d
0x18002cf77  mov     rax, [rdi+490h]
0x18002cf7e  mov     [rax+rcx*8+10h], rdx
0x18002cf83  movsxd  rax, ebx
0x18002cf86  lea     rdx, ?kstrTrueTypeFormat@@3PADA; "%TTDownloadFormat"
0x18002cf8d  lea     rcx, [rax+rax*2]
0x18002cf91  mov     rax, [rdi+490h]
0x18002cf98  mov     [rax+rcx*8], rdx
0x18002cf9c  mov     rax, [rdi+490h]
0x18002cfa3  mov     [rax+rcx*8+8], r13d
0x18002cfa8  mov     rax, [rdi+490h]
0x18002cfaf  lea     rdx, [rax+rcx*8]
0x18002cfb3  lea     rax, ?gpPScriptTrueTypeOptionsTableNative@@3PAUPrivateOptionAccessTable@@A; PrivateOptionAccessTable near * gpPScriptTrueTypeOptionsTableNative
0x18002cfba  cmp     r12d, 2
0x18002cfbe  jz      short loc_18002CFC7
0x18002cfc0  lea     rax, ?gpPScriptTrueTypeOptionsTable@@3PAUPrivateOptionAccessTable@@A; PrivateOptionAccessTable near * gpPScriptTrueTypeOptionsTable
0x18002cfc7  mov     [rdx+10h], rax
0x18002cfcb  mov     rcx, rsi; this
0x18002cfce  mov     edx, 0A0h; unsigned __int64
0x18002cfd3  inc     ebx
0x18002cfd5  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x18002cfda  mov     r12, rax
0x18002cfdd  test    rax, rax
0x18002cfe0  jz      loc_18002D08D
0x18002cfe6  xor     r15d, r15d
0x18002cfe9  lea     rcx, cs:180000000h
0x18002cff0  mov     rbp, r15
0x18002cff3  shl     rbp, 5
0x18002cff7  cmp     rva ?gpPScriptOutputProtocolTable@@3PAUPrivateOptionAccessTable@@A[rcx+rbp], 0; PrivateOptionAccessTable near * gpPScriptOutputProtocolTable ...
0x18002d000  jz      short loc_18002D029
0x18002d002  mov     eax, rva dword_180072A4C[rcx+rbp]
0x18002d009  mov     [rsp+68h+arg_0], eax
0x18002d00d  test    eax, eax
0x18002d00f  jz      short loc_18002D029
0x18002d011  mov     rcx, rsi; this
0x18002d014  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002d019  mov     ecx, [rsp+68h+arg_0]
0x18002d01d  test    [rax+64h], ecx
0x18002d020  lea     rcx, cs:180000000h
0x18002d027  jz      short loc_18002D04E
0x18002d029  movups  xmm0, xmmword ptr rva ?gpPScriptOutputProtocolTable@@3PAUPrivateOptionAccessTable@@A[rcx+rbp]; PrivateOptionAccessTable near * gpPScriptOutputProtocolTable ...
0x18002d031  mov     eax, r13d
0x18002d034  shl     rax, 5
0x18002d038  inc     r13d
0x18002d03b  movups  xmmword ptr [rax+r12], xmm0
0x18002d040  movups  xmm1, rva xmmword_180072A50[rcx+rbp]
0x18002d048  movups  xmmword ptr [rax+r12+10h], xmm1
0x18002d04e  inc     r15
0x18002d051  cmp     r15, 5
0x18002d055  jnz     short loc_18002CFF0
0x18002d057  movsxd  rax, ebx
0x18002d05a  lea     rdx, ?kstrPSOutputProtocol@@3PADA; "%OutputProtocol"
0x18002d061  inc     ebx
0x18002d063  lea     rcx, [rax+rax*2]
0x18002d067  mov     rax, [rdi+490h]
0x18002d06e  mov     [rax+rcx*8], rdx
0x18002d072  mov     rax, [rdi+490h]
0x18002d079  mov     dword ptr [rax+rcx*8+8], 1
0x18002d081  mov     rax, [rdi+490h]
0x18002d088  mov     [rax+rcx*8+10h], r12
0x18002d08d  movsxd  rax, [rsp+68h+arg_8]
0x18002d092  lea     rdx, [rax+rax*2]
0x18002d096  movsxd  rax, ebx
0x18002d099  movups  xmm0, xmmword ptr [r14+rdx*8]
0x18002d09e  lea     rcx, [rax+rax*2]
0x18002d0a2  mov     rax, [rdi+490h]
0x18002d0a9  movups  xmmword ptr [rax+rcx*8], xmm0
0x18002d0ad  movsd   xmm1, qword ptr [r14+rdx*8+10h]
0x18002d0b4  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x18002d0ba  mov     rax, [rdi+490h]
0x18002d0c1  mov     rbx, [rsp+68h+arg_10]
0x18002d0c9  add     rsp, 30h
0x18002d0cd  pop     r15
0x18002d0cf  pop     r14
0x18002d0d1  pop     r13
0x18002d0d3  pop     r12
0x18002d0d5  pop     rdi
0x18002d0d6  pop     rsi
0x18002d0d7  pop     rbp
0x18002d0d8  retn
```
