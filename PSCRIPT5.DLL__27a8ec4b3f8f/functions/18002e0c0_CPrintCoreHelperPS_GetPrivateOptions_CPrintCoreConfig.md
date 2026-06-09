# CPrintCoreHelperPS::GetPrivateOptions(CPrintCoreConfig *)

- ea: `0x18002e0c0`
- end: `0x18002e4fa`
- name: `?GetPrivateOptions@CPrintCoreHelperPS@@MEAAPEAUtagPrivateFeaturesAccessTable@@PEAVCPrintCoreConfig@@@Z`
- size: `1082`
- prototype: `struct tagPrivateFeaturesAccessTable *__fastcall(CPrintCoreHelperPS *this, struct CPrintCoreConfig *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002d8a4`
- `0x18002e0c0`
- `0x18002fcc8`
- `0x180034384`
- `0x1800343c8`
- `0x18005f010`

## string_xrefs

- `0x18002e47a`: `%OutputProtocol`

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
  void *v10; // rax
  __int64 v11; // r9
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
    v10 = (void *)(**((__int64 (__fastcall ***)(_QWORD))a2 + 1))(*(_QWORD *)a2);
    VGetEnabledEMFFeatures(v10, v9, v8 != 0, v11, &v50);
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
            *(_OWORD *)(v35 + 8 * v34) = *(_OWORD *)&(&off_180073E78)[v32];
            *(_QWORD *)(v35 + 8 * v34 + 16) = (&off_180073E88)[v32];
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
            v50 = dword_180074A3C[8 * i];
            if ( v50 )
            {
              UIInfo = CPrintCoreConfig::GetUIInfo(a2);
              if ( (v50 & *((_DWORD *)UIInfo + 25)) == 0 )
                continue;
            }
          }
          v44 = 32LL * v4++;
          *(_OWORD *)&v41[v44] = *((_OWORD *)&gpPScriptOutputProtocolTable + 2 * i);
          *(_OWORD *)&v41[v44 + 16] = xmmword_180074A40[2 * i];
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
0x18002e0c0  mov     [rsp+arg_10], rbx
0x18002e0c5  push    rbp
0x18002e0c6  push    rsi
0x18002e0c7  push    rdi
0x18002e0c8  push    r12
0x18002e0ca  push    r13
0x18002e0cc  push    r14
0x18002e0ce  push    r15
0x18002e0d0  sub     rsp, 30h
0x18002e0d4  mov     rax, [rcx+430h]
0x18002e0db  mov     rdi, rcx
0x18002e0de  mov     rcx, [rdx]
0x18002e0e1  mov     rsi, rdx
0x18002e0e4  mov     rax, [rax+10h]
0x18002e0e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0ed  xor     r13d, r13d
0x18002e0f0  test    eax, eax
0x18002e0f2  jnz     short loc_18002E0FB
0x18002e0f4  xor     eax, eax
0x18002e0f6  jmp     loc_18002E4E1
0x18002e0fb  cmp     [rdi+490h], r13
0x18002e102  jnz     loc_18002E4DA
0x18002e108  mov     rcx, rsi; this
0x18002e10b  mov     [rsp+68h+arg_0], r13d
0x18002e110  mov     ebp, r13d
0x18002e113  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002e118  cmp     [rax+0D8h], r13d
0x18002e11f  jz      short loc_18002E141
0x18002e121  mov     rcx, rsi; this
0x18002e124  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002e129  mov     rcx, rsi; this
0x18002e12c  mov     r14d, [rax+0D8h]
0x18002e133  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002e138  add     r14, [rax+148h]
0x18002e13f  jmp     short loc_18002E144
0x18002e141  mov     r14, r13
0x18002e144  mov     rcx, rsi; this
0x18002e147  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002e14c  mov     rcx, [rsi]
0x18002e14f  mov     ebx, [rax+12Ch]
0x18002e155  mov     rax, [rsi+8]
0x18002e159  mov     rax, [rax]
0x18002e15c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e161  lea     rcx, [rsp+68h+arg_0]
0x18002e166  mov     r8d, r13d
0x18002e169  mov     [rsp+68h+var_48], rcx
0x18002e16e  test    r14, r14
0x18002e171  mov     rcx, rax
0x18002e174  mov     edx, ebx
0x18002e176  setnz   r8b
0x18002e17a  call    VGetEnabledEMFFeatures
0x18002e17f  mov     rcx, rsi; this
0x18002e182  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002e187  cmp     dword ptr [rax+50h], 1
0x18002e18b  jnz     short loc_18002E19D
0x18002e18d  mov     rax, cs:?gpPScriptLevel1Features@@3PAUtagPrivateFeaturesAccessTable@@A; tagPrivateFeaturesAccessTable near * gpPScriptLevel1Features
0x18002e194  lea     r14, ?gpPScriptLevel1Features@@3PAUtagPrivateFeaturesAccessTable@@A; tagPrivateFeaturesAccessTable near * gpPScriptLevel1Features
0x18002e19b  jmp     short loc_18002E1C9
0x18002e19d  mov     rcx, rsi; this
0x18002e1a0  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002e1a5  cmp     dword ptr [rax+50h], 2
0x18002e1a9  jnz     short loc_18002E1BB
0x18002e1ab  mov     rax, cs:?gpPScriptLevel2Features@@3PAUtagPrivateFeaturesAccessTable@@A; tagPrivateFeaturesAccessTable near * gpPScriptLevel2Features
0x18002e1b2  lea     r14, ?gpPScriptLevel2Features@@3PAUtagPrivateFeaturesAccessTable@@A; tagPrivateFeaturesAccessTable near * gpPScriptLevel2Features
0x18002e1b9  jmp     short loc_18002E1C9
0x18002e1bb  mov     rax, cs:?gpPScriptLevel3Features@@3PAUtagPrivateFeaturesAccessTable@@A; tagPrivateFeaturesAccessTable near * gpPScriptLevel3Features
0x18002e1c2  lea     r14, ?gpPScriptLevel3Features@@3PAUtagPrivateFeaturesAccessTable@@A; tagPrivateFeaturesAccessTable near * gpPScriptLevel3Features
0x18002e1c9  test    rax, rax
0x18002e1cc  jz      short loc_18002E1E1
0x18002e1ce  inc     ebp
0x18002e1d0  lea     rcx, ds:0[rbp*2]
0x18002e1d8  add     rcx, rbp
0x18002e1db  cmp     [r14+rcx*8], r13
0x18002e1df  jnz     short loc_18002E1CE
0x18002e1e1  mov     rcx, rsi; this
0x18002e1e4  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002e1e9  mov     rdx, rsi; struct CPrintCoreConfig *
0x18002e1ec  mov     r12d, [rax+70h]
0x18002e1f0  call    ?BIsCustomPageSizeSupported@CPrintCoreHelperPS@@AEAAHPEAVCPrintCoreConfig@@@Z; CPrintCoreHelperPS::BIsCustomPageSizeSupported(CPrintCoreConfig *)
0x18002e1f5  mov     ecx, eax
0x18002e1f7  lea     r9, cs:180000000h
0x18002e1fe  neg     ecx
0x18002e200  mov     r15d, eax
0x18002e203  mov     r8d, r13d
0x18002e206  sbb     edx, edx
0x18002e208  neg     edx
0x18002e20a  lea     ebx, [rdx+1]
0x18002e20d  add     ebx, ebp
0x18002e20f  cmp     cs:?gpPScriptEMFFeatures@@3PAU_unnamed_type_gpPScriptEMFFeatures_@@A, r13d; _unnamed_type_gpPScriptEMFFeatures_ near * gpPScriptEMFFeatures
0x18002e216  jz      short loc_18002E24B
0x18002e218  mov     eax, r8d
0x18002e21b  shl     rax, 5
0x18002e21f  mov     edx, [rax+r9+73E70h]
0x18002e227  lea     eax, [rbx+1]
0x18002e22a  mov     ecx, edx
0x18002e22c  and     ecx, [rsp+68h+arg_0]
0x18002e230  cmp     ecx, edx
0x18002e232  cmovnz  eax, ebx
0x18002e235  inc     r8d
0x18002e238  mov     ebx, eax
0x18002e23a  mov     eax, r8d
0x18002e23d  shl     rax, 5
0x18002e241  cmp     [rax+r9+73E70h], r13d
0x18002e249  jnz     short loc_18002E218
0x18002e24b  mov     rcx, rsi; this
0x18002e24e  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002e253  mov     rcx, rsi; this
0x18002e256  mov     ebp, [rax+8Ch]
0x18002e25c  lea     eax, [rbx+1]
0x18002e25f  and     ebp, 8
0x18002e262  cmovnz  eax, ebx
0x18002e265  add     eax, 2
0x18002e268  lea     rdx, [rax+rax*2]
0x18002e26c  shl     rdx, 3; unsigned __int64
0x18002e270  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x18002e275  mov     [rdi+490h], rax
0x18002e27c  mov     rdx, rax
0x18002e27f  test    rax, rax
0x18002e282  jz      loc_18002E4DA
0x18002e288  mov     ebx, r13d
0x18002e28b  cmp     [r14], r13
0x18002e28e  jz      short loc_18002E2CA
0x18002e290  movsxd  rax, ebx
0x18002e293  inc     ebx
0x18002e295  lea     rcx, [rax+rax*2]
0x18002e299  mov     rax, [rdi+490h]
0x18002e2a0  movups  xmm0, xmmword ptr [r14+rcx*8]
0x18002e2a5  movups  xmmword ptr [rax+rcx*8], xmm0
0x18002e2a9  movsd   xmm1, qword ptr [r14+rcx*8+10h]
0x18002e2b0  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x18002e2b6  movsxd  rax, ebx
0x18002e2b9  lea     rcx, [rax+rax*2]
0x18002e2bd  cmp     [r14+rcx*8], r13
0x18002e2c1  jnz     short loc_18002E290
0x18002e2c3  mov     rdx, [rdi+490h]
0x18002e2ca  mov     [rsp+68h+arg_8], ebx
0x18002e2ce  test    r15d, r15d
0x18002e2d1  jz      short loc_18002E2FA
0x18002e2d3  movsxd  rax, ebx
0x18002e2d6  inc     ebx
0x18002e2d8  lea     rcx, [rax+rax*2]
0x18002e2dc  lea     rax, ?kstrPSCustomPageSize@@3PADA; "%CustomPageSize"
0x18002e2e3  mov     [rdx+rcx*8], rax
0x18002e2e7  lea     rdx, ?gpPScriptEmptyOptionsTable@@3PAUPrivateOptionAccessTable@@A; PrivateOptionAccessTable near * gpPScriptEmptyOptionsTable
0x18002e2ee  mov     rax, [rdi+490h]
0x18002e2f5  mov     [rax+rcx*8+10h], rdx
0x18002e2fa  cmp     cs:?gpPScriptEMFFeatures@@3PAU_unnamed_type_gpPScriptEMFFeatures_@@A, r13d; _unnamed_type_gpPScriptEMFFeatures_ near * gpPScriptEMFFeatures
0x18002e301  mov     edx, r13d
0x18002e304  jz      short loc_18002E365
0x18002e306  lea     r9, cs:180000000h
0x18002e30d  mov     r8d, edx
0x18002e310  shl     r8, 5
0x18002e314  mov     ecx, [r8+r9+73E70h]
0x18002e31c  mov     eax, ecx
0x18002e31e  and     eax, [rsp+68h+arg_0]
0x18002e322  cmp     eax, ecx
0x18002e324  jnz     short loc_18002E353
0x18002e326  movups  xmm0, xmmword ptr [r8+r9+73E78h]
0x18002e32f  movsxd  rax, ebx
0x18002e332  inc     ebx
0x18002e334  lea     rcx, [rax+rax*2]
0x18002e338  mov     rax, [rdi+490h]
0x18002e33f  movups  xmmword ptr [rax+rcx*8], xmm0
0x18002e343  movsd   xmm1, qword ptr [r8+r9+73E88h]
0x18002e34d  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x18002e353  inc     edx
0x18002e355  mov     eax, edx
0x18002e357  shl     rax, 5
0x18002e35b  cmp     [rax+r9+73E70h], r13d
0x18002e363  jnz     short loc_18002E30D
0x18002e365  test    ebp, ebp
0x18002e367  jnz     short loc_18002E3A3
0x18002e369  movsxd  rax, ebx
0x18002e36c  lea     rdx, ?kstrPSNegative@@3PADA; "%Negative"
0x18002e373  inc     ebx
0x18002e375  lea     rcx, [rax+rax*2]
0x18002e379  mov     rax, [rdi+490h]
0x18002e380  mov     [rax+rcx*8], rdx
0x18002e384  lea     rdx, ?gpPScriptNegImageOptionsTable@@3PAUPrivateOptionAccessTable@@A; PrivateOptionAccessTable near * gpPScriptNegImageOptionsTable
0x18002e38b  mov     rax, [rdi+490h]
0x18002e392  mov     [rax+rcx*8+8], r13d
0x18002e397  mov     rax, [rdi+490h]
0x18002e39e  mov     [rax+rcx*8+10h], rdx
0x18002e3a3  movsxd  rax, ebx
0x18002e3a6  lea     rdx, ?kstrTrueTypeFormat@@3PADA; "%TTDownloadFormat"
0x18002e3ad  lea     rcx, [rax+rax*2]
0x18002e3b1  mov     rax, [rdi+490h]
0x18002e3b8  mov     [rax+rcx*8], rdx
0x18002e3bc  mov     rax, [rdi+490h]
0x18002e3c3  mov     [rax+rcx*8+8], r13d
0x18002e3c8  mov     rax, [rdi+490h]
0x18002e3cf  lea     rdx, [rax+rcx*8]
0x18002e3d3  lea     rax, ?gpPScriptTrueTypeOptionsTableNative@@3PAUPrivateOptionAccessTable@@A; PrivateOptionAccessTable near * gpPScriptTrueTypeOptionsTableNative
0x18002e3da  cmp     r12d, 2
0x18002e3de  jz      short loc_18002E3E7
0x18002e3e0  lea     rax, ?gpPScriptTrueTypeOptionsTable@@3PAUPrivateOptionAccessTable@@A; PrivateOptionAccessTable near * gpPScriptTrueTypeOptionsTable
0x18002e3e7  mov     [rdx+10h], rax
0x18002e3eb  mov     rcx, rsi; this
0x18002e3ee  mov     edx, 0A0h; unsigned __int64
0x18002e3f3  inc     ebx
0x18002e3f5  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x18002e3fa  mov     r12, rax
0x18002e3fd  test    rax, rax
0x18002e400  jz      loc_18002E4AD
0x18002e406  xor     r15d, r15d
0x18002e409  lea     rcx, cs:180000000h
0x18002e410  mov     rbp, r15
0x18002e413  shl     rbp, 5
0x18002e417  cmp     rva ?gpPScriptOutputProtocolTable@@3PAUPrivateOptionAccessTable@@A[rcx+rbp], 0; PrivateOptionAccessTable near * gpPScriptOutputProtocolTable ...
0x18002e420  jz      short loc_18002E449
0x18002e422  mov     eax, rva dword_180074A3C[rcx+rbp]
0x18002e429  mov     [rsp+68h+arg_0], eax
0x18002e42d  test    eax, eax
0x18002e42f  jz      short loc_18002E449
0x18002e431  mov     rcx, rsi; this
0x18002e434  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18002e439  mov     ecx, [rsp+68h+arg_0]
0x18002e43d  test    [rax+64h], ecx
0x18002e440  lea     rcx, cs:180000000h
0x18002e447  jz      short loc_18002E46E
0x18002e449  movups  xmm0, xmmword ptr rva ?gpPScriptOutputProtocolTable@@3PAUPrivateOptionAccessTable@@A[rcx+rbp]; PrivateOptionAccessTable near * gpPScriptOutputProtocolTable ...
0x18002e451  mov     eax, r13d
0x18002e454  shl     rax, 5
0x18002e458  inc     r13d
0x18002e45b  movups  xmmword ptr [rax+r12], xmm0
0x18002e460  movups  xmm1, rva xmmword_180074A40[rcx+rbp]
0x18002e468  movups  xmmword ptr [rax+r12+10h], xmm1
0x18002e46e  inc     r15
0x18002e471  cmp     r15, 5
0x18002e475  jnz     short loc_18002E410
0x18002e477  movsxd  rax, ebx
0x18002e47a  lea     rdx, ?kstrPSOutputProtocol@@3PADA; "%OutputProtocol"
0x18002e481  inc     ebx
0x18002e483  lea     rcx, [rax+rax*2]
0x18002e487  mov     rax, [rdi+490h]
0x18002e48e  mov     [rax+rcx*8], rdx
0x18002e492  mov     rax, [rdi+490h]
0x18002e499  mov     dword ptr [rax+rcx*8+8], 1
0x18002e4a1  mov     rax, [rdi+490h]
0x18002e4a8  mov     [rax+rcx*8+10h], r12
0x18002e4ad  movsxd  rax, [rsp+68h+arg_8]
0x18002e4b2  lea     rdx, [rax+rax*2]
0x18002e4b6  movsxd  rax, ebx
0x18002e4b9  movups  xmm0, xmmword ptr [r14+rdx*8]
0x18002e4be  lea     rcx, [rax+rax*2]
0x18002e4c2  mov     rax, [rdi+490h]
0x18002e4c9  movups  xmmword ptr [rax+rcx*8], xmm0
0x18002e4cd  movsd   xmm1, qword ptr [r14+rdx*8+10h]
0x18002e4d4  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x18002e4da  mov     rax, [rdi+490h]
0x18002e4e1  mov     rbx, [rsp+68h+arg_10]
0x18002e4e9  add     rsp, 30h
0x18002e4ed  pop     r15
0x18002e4ef  pop     r14
0x18002e4f1  pop     r13
0x18002e4f3  pop     r12
0x18002e4f5  pop     rdi
0x18002e4f6  pop     rsi
0x18002e4f7  pop     rbp
0x18002e4f8  retn
```
