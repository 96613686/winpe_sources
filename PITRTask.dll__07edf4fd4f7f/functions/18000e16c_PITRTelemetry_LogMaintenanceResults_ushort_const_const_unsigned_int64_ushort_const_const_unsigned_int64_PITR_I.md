# PITRTelemetry_LogMaintenanceResults(ushort const * const *,unsigned __int64,ushort const * const *,unsigned __int64,PITR::IPITRSettings *,_GUID const *,__int64,__int64,__int64)

- ea: `0x18000e16c`
- end: `0x18000e669`
- name: `?PITRTelemetry_LogMaintenanceResults@@YAXPEBQEBG_K01PEAUIPITRSettings@PITR@@PEBU_GUID@@_J44@Z`
- size: `1277`
- prototype: `void __fastcall(const unsigned __int16 *const *, unsigned __int64, const unsigned __int16 *const *, unsigned __int64, struct PITR::IPITRSettings *, const struct _GUID *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e670`

## callees

- `0x180003150`
- `0x180004664`
- `0x18000bbd0`
- `0x18000d1a0`
- `0x18000d3d0`
- `0x18000d938`
- `0x18000dc90`
- `0x18000e16c`
- `0x18000e804`
- `0x18000ea00`
- `0x18000ece8`
- `0x1800107c0`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000e258`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e3e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e258`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e3e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e410`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e477`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e477`
- `WDSCORE!CurrentIP` at `0x18000e418`
- `WDSCORE!CurrentIP` at `0x18000e418`

## string_xrefs

- `0x18000e454`: `base\diagnosis\srt\pitr\task\dll\pitrtelemetry.cpp`
- `0x18000e424`: `PITRTelemetry_LogMaintenanceResults: Snapshot deleted during maintenance. ID: %s`

## pseudocode

```c
void __fastcall PITRTelemetry_LogMaintenanceResults(
        const unsigned __int16 *const *a1,
        unsigned __int64 a2,
        const unsigned __int16 *const *a3,
        unsigned __int64 a4,
        struct PITR::IPITRSettings *a5,
        const struct _GUID *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  unsigned __int64 v9; // rdi
  const struct _GUID *v12; // r12
  __int64 v13; // r15
  int v14; // esi
  unsigned __int64 i; // rbx
  unsigned __int16 *v16; // rdx
  int v17; // r8d
  const unsigned __int16 *v18; // r14
  __int64 *v19; // rcx
  _QWORD *v20; // r8
  unsigned __int64 v21; // rdi
  void *v22; // r12
  _WORD *v23; // r10
  _QWORD *v24; // rax
  unsigned __int64 v25; // rbx
  unsigned __int64 v26; // r9
  unsigned __int16 v27; // r13
  int v28; // eax
  _QWORD *v29; // rcx
  unsigned __int64 v30; // r10
  unsigned __int64 v31; // rax
  _WORD *v32; // r9
  int v33; // eax
  char v34; // bl
  __int64 v35; // r8
  const unsigned __int16 *v36; // r9
  DWORD LastError; // edi
  __int64 v38; // rbx
  struct tagLOG_PARTIAL_MSG *v39; // rax
  struct PITR::IPITRSettings *v40; // rbx
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  int v46; // eax
  _QWORD v47[2]; // [rsp+68h] [rbp-91h] BYREF
  unsigned __int64 v48; // [rsp+78h] [rbp-81h]
  unsigned __int64 v49; // [rsp+80h] [rbp-79h]
  const unsigned __int16 *const *v50; // [rsp+88h] [rbp-71h]
  unsigned __int64 v51; // [rsp+90h] [rbp-69h]
  unsigned int v52[2]; // [rsp+98h] [rbp-61h]
  struct PITR::IPITRSettings *v53; // [rsp+A0h] [rbp-59h]
  void *v54[4]; // [rsp+A8h] [rbp-51h] BYREF
  char v55; // [rsp+C8h] [rbp-31h] BYREF
  int v56; // [rsp+D8h] [rbp-21h] BYREF
  _QWORD v57[2]; // [rsp+E0h] [rbp-19h] BYREF

  v9 = a4;
  *(_QWORD *)v52 = a4;
  v51 = a2;
  v50 = a1;
  v53 = a5;
  v12 = a6;
  v13 = 0;
  v14 = 0;
  v56 = 0;
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)
    || (int)PITRTelemetryInitialize() >= 0 && dword_18001BFA0 && (unsigned int)dword_18001B000 > 4 )
  {
    v57[1] = 0;
    v57[0] = std::_Tree_alloc<0,std::_Tree_base_types<std::wstring>>::_Buyheadnode();
    for ( i = 0; i < v9; ++i )
    {
      v16 = (unsigned __int16 *)a3[i];
      if ( v16 )
      {
        if ( *v16 )
        {
          std::wstring::wstring(v54, v16);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring,std::_Nil>(
            (unsigned int)v57,
            (unsigned int)&v55,
            v17,
            (unsigned int)v54,
            byte_18001BFD9);
          if ( v54[3] >= (void *)8 )
            operator delete(v54[0]);
        }
      }
    }
    if ( a2 )
    {
      while ( 1 )
      {
        v18 = v50[v13];
        if ( v18 && *v18 )
        {
          std::wstring::wstring(v47, (void *)v50[v13]);
          v19 = *(__int64 **)(v57[0] + 8LL);
          v20 = (_QWORD *)v57[0];
          v21 = v49;
          v22 = (void *)v47[0];
          while ( !*((_BYTE *)v19 + 25) )
          {
            v23 = v47;
            if ( v21 >= 8 )
              v23 = (_WORD *)v47[0];
            v24 = v19 + 4;
            v25 = v19[6];
            v26 = v25;
            if ( v25 >= v48 )
              v26 = v48;
            if ( (unsigned __int64)v19[7] >= 8 )
              v24 = (_QWORD *)*v24;
            if ( v26 )
            {
              while ( 1 )
              {
                v27 = *(_WORD *)v24;
                LOWORD(v56) = *v23;
                v21 = v49;
                if ( v27 != (_WORD)v56 )
                  break;
                v24 = (_QWORD *)((char *)v24 + 2);
                ++v23;
                if ( !--v26 )
                  goto LABEL_24;
              }
              v28 = v27 < (unsigned __int16)v56 ? -1 : 1;
            }
            else
            {
LABEL_24:
              if ( v25 >= v48 )
                v28 = v25 != v48;
              else
                v28 = -1;
            }
            if ( v28 >= 0 )
            {
              v20 = v19;
              v19 = (__int64 *)*v19;
            }
            else
            {
              v19 = (__int64 *)v19[2];
            }
          }
          if ( v20 == (_QWORD *)v57[0] )
            goto LABEL_47;
          v29 = v20 + 4;
          if ( v20[7] >= 8u )
            v29 = (_QWORD *)*v29;
          v30 = v20[6];
          v31 = v48;
          if ( v48 >= v30 )
            v31 = v20[6];
          v32 = v47;
          if ( v21 >= 8 )
            v32 = (_WORD *)v47[0];
          if ( v31 )
          {
            while ( *v32 == *(_WORD *)v29 )
            {
              ++v32;
              v29 = (_QWORD *)((char *)v29 + 2);
              if ( !--v31 )
                goto LABEL_42;
            }
            v33 = *v32 < *(_WORD *)v29 ? -1 : 1;
          }
          else
          {
LABEL_42:
            v33 = v48 >= v30 ? v48 != v30 : -1;
          }
          if ( v33 < 0 )
LABEL_47:
            v20 = (_QWORD *)v57[0];
          v14 |= 1u;
          if ( v20 == (_QWORD *)v57[0] )
          {
            v34 = 1;
            goto LABEL_52;
          }
        }
        else
        {
          v21 = v49;
          v22 = (void *)v47[0];
        }
        v34 = 0;
LABEL_52:
        if ( (v14 & 1) != 0 )
        {
          v14 &= ~1u;
          if ( v21 >= 8 )
            operator delete(v22);
        }
        if ( v34 )
        {
          v12 = a6;
          if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
          {
            PITRTelemetry_DeleteSnapshot(v18, a6, v35, v36);
            LastError = GetLastError();
            v38 = CurrentIP();
            v39 = ConstructPartialMsgW(
                    0x4000000,
                    "PITRTelemetry_LogMaintenanceResults: Snapshot deleted during maintenance. ID: %s",
                    (const char *)v18);
            WdsSetupLogMessageW(
              v39,
              0,
              L"D",
              0,
              514,
              L"base\\diagnosis\\srt\\pitr\\task\\dll\\pitrtelemetry.cpp",
              L"PITRTelemetry_LogMaintenanceResults",
              v38,
              LastError,
              0,
              0);
          }
        }
        else
        {
          v12 = a6;
        }
        if ( ++v13 >= v51 )
        {
          LODWORD(v9) = v52[0];
          break;
        }
      }
    }
    PITRTelemetry_GetAllSnapshotsSizeWithVSS(a7, a8, a9, v9, v12);
    v40 = v53;
    if ( v53 )
    {
      v56 = 1;
      v41 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64, int *))(*(_QWORD *)v53 + 32LL))(
              v53,
              5,
              &v56);
      PITRTelemetry_SnapshotSettingValue(L"RebootDelay", v41, v56 == 1);
      v56 = 1;
      v42 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64, int *))(*(_QWORD *)v40 + 64LL))(
              v40,
              5,
              &v56);
      PITRTelemetry_SnapshotSettingValue(L"SnapshotInterval", v42, v56 == 1);
      v56 = 1;
      v43 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64, int *))(*(_QWORD *)v40 + 96LL))(
              v40,
              5,
              &v56);
      PITRTelemetry_SnapshotSettingValue(L"MaxCount", v43, v56 == 1);
      v56 = 1;
      v44 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64, int *))(*(_QWORD *)v40 + 128LL))(
              v40,
              5,
              &v56);
      PITRTelemetry_SnapshotSettingValue(L"MaxTimespan", v44, v56 == 1);
      v56 = 1;
      v45 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64, int *))(*(_QWORD *)v40 + 160LL))(
              v40,
              5,
              &v56);
      PITRTelemetry_SnapshotSettingValue(L"MaxGlobalSize", v45, v56 == 1);
      v56 = 1;
      v46 = (**(__int64 (__fastcall ***)(struct PITR::IPITRSettings *, __int64, int *))v40)(v40, 5, &v56);
      PITRTelemetry_SnapshotSettingValue(L"Active", v46 != 0, v56 == 1);
    }
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v57);
  }
}

```

## disassembly

```asm
0x18000e16c  mov     [rsp-8+arg_8], rbx
0x18000e171  push    rbp
0x18000e172  push    rsi
0x18000e173  push    rdi
0x18000e174  push    r12
0x18000e176  push    r13
0x18000e178  push    r14
0x18000e17a  push    r15
0x18000e17c  lea     rbp, [rsp-7]
0x18000e181  sub     rsp, 100h
0x18000e188  mov     rax, cs:__security_cookie
0x18000e18f  xor     rax, rsp
0x18000e192  mov     [rbp+37h+var_40], rax
0x18000e196  mov     rdi, r9
0x18000e199  mov     qword ptr [rbp+37h+var_98], r9
0x18000e19d  mov     r14, r8
0x18000e1a0  mov     r13, rdx
0x18000e1a3  mov     [rbp+37h+var_A0], rdx
0x18000e1a7  mov     [rbp+37h+var_A8], rcx
0x18000e1ab  mov     rax, [rbp+37h+arg_20]
0x18000e1af  mov     [rbp+37h+var_90], rax
0x18000e1b3  mov     r12, [rbp+37h+arg_28]
0x18000e1b7  mov     [rsp+130h+var_D0], r12
0x18000e1bc  xor     r15d, r15d
0x18000e1bf  mov     esi, r15d
0x18000e1c2  mov     [rbp+37h+var_58], r15d
0x18000e1c6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18000e1cd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18000e1d2  test    al, al
0x18000e1d4  jz      short loc_18000E1FF
0x18000e1d6  call    ?PITRTelemetryInitialize@@YAJXZ; PITRTelemetryInitialize(void)
0x18000e1db  test    eax, eax
0x18000e1dd  js      loc_18000E642
0x18000e1e3  cmp     cs:dword_18001BFA0, r15d
0x18000e1ea  jz      loc_18000E642
0x18000e1f0  mov     eax, cs:dword_18001B000
0x18000e1f6  cmp     eax, 4
0x18000e1f9  jbe     loc_18000E642
0x18000e1ff  mov     [rbp+37h+var_50], r15
0x18000e203  mov     [rbp+37h+var_48], r15
0x18000e207  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::wstring>>::_Buyheadnode(void)
0x18000e20c  mov     [rbp+37h+var_50], rax
0x18000e210  mov     rbx, r15
0x18000e213  test    rdi, rdi
0x18000e216  jz      short loc_18000E266
0x18000e218  mov     rdx, [r14+rbx*8]; Src
0x18000e21c  test    rdx, rdx
0x18000e21f  jz      short loc_18000E25E
0x18000e221  cmp     [rdx], r15w
0x18000e225  jz      short loc_18000E25E
0x18000e227  lea     rcx, [rbp+37h+var_88]; void *
0x18000e22b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000e230  nop
0x18000e231  mov     al, cs:byte_18001BFD9
0x18000e237  mov     byte ptr [rsp+130h+var_110], al
0x18000e23b  lea     r9, [rbp+37h+var_88]
0x18000e23f  lea     rdx, [rbp+37h+var_68]
0x18000e243  lea     rcx, [rbp+37h+var_50]
0x18000e247  call    ??$_Insert_nohint@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Nil@2@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@_N$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring,std::_Nil>(bool,std::wstring &&,std::_Nil)
0x18000e24c  nop
0x18000e24d  cmp     [rbp+37h+var_70], 8
0x18000e252  jb      short loc_18000E25E
0x18000e254  mov     rcx, [rbp+37h+var_88]
0x18000e258  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000e25e  inc     rbx
0x18000e261  cmp     rbx, rdi
0x18000e264  jb      short loc_18000E218
0x18000e266  test    r13, r13
0x18000e269  jz      loc_18000E49D
0x18000e26f  xor     r13d, r13d
0x18000e272  mov     rax, [rbp+37h+var_A8]
0x18000e276  mov     r14, [rax+r15*8]
0x18000e27a  test    r14, r14
0x18000e27d  jz      loc_18000E3C4
0x18000e283  cmp     [r14], r13w
0x18000e287  jz      loc_18000E3C4
0x18000e28d  mov     rdx, r14; Src
0x18000e290  lea     rcx, [rsp+130h+var_C8]; void *
0x18000e295  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000e29a  mov     r11, [rbp+37h+var_50]
0x18000e29e  mov     rcx, [r11+8]
0x18000e2a2  mov     r8, r11
0x18000e2a5  mov     rdi, [rbp+37h+var_B0]
0x18000e2a9  mov     rdx, [rsp+130h+var_B8]
0x18000e2ae  mov     r12, [rsp+130h+var_C8]
0x18000e2b3  jmp     loc_18000E33E
0x18000e2b8  lea     r10, [rsp+130h+var_C8]
0x18000e2bd  cmp     rdi, 8
0x18000e2c1  cmovnb  r10, r12
0x18000e2c5  lea     rax, [rcx+20h]
0x18000e2c9  mov     rbx, [rax+10h]
0x18000e2cd  mov     r9, rbx
0x18000e2d0  cmp     rbx, rdx
0x18000e2d3  cmovnb  r9, rdx
0x18000e2d7  cmp     qword ptr [rax+18h], 8
0x18000e2dc  jb      short loc_18000E2E1
0x18000e2de  mov     rax, [rax]
0x18000e2e1  test    r9, r9
0x18000e2e4  jz      short loc_18000E30D
0x18000e2e6  movzx   r13d, word ptr [rax]
0x18000e2ea  movzx   edi, word ptr [r10]
0x18000e2ee  mov     word ptr [rbp+37h+var_58], di
0x18000e2f2  cmp     r13w, di
0x18000e2f6  mov     rdi, [rbp+37h+var_B0]
0x18000e2fa  jnz     short loc_18000E317
0x18000e2fc  add     rax, 2
0x18000e300  add     r10, 2
0x18000e304  sub     r9, 1
0x18000e308  jnz     short loc_18000E2E6
0x18000e30a  xor     r13d, r13d
0x18000e30d  cmp     rbx, rdx
0x18000e310  jnb     short loc_18000E328
0x18000e312  or      eax, 0FFFFFFFFh
0x18000e315  jmp     short loc_18000E32E
0x18000e317  cmp     r13w, word ptr [rbp+37h+var_58]
0x18000e31c  sbb     eax, eax
0x18000e31e  and     eax, 0FFFFFFFEh
0x18000e321  inc     eax
0x18000e323  xor     r13d, r13d
0x18000e326  jmp     short loc_18000E32E
0x18000e328  mov     eax, r13d
0x18000e32b  setnz   al
0x18000e32e  test    eax, eax
0x18000e330  jns     short loc_18000E338
0x18000e332  mov     rcx, [rcx+10h]
0x18000e336  jmp     short loc_18000E33E
0x18000e338  mov     r8, rcx
0x18000e33b  mov     rcx, [rcx]
0x18000e33e  cmp     [rcx+19h], r13b
0x18000e342  jz      loc_18000E2B8
0x18000e348  cmp     r8, r11
0x18000e34b  jz      short loc_18000E3B5
0x18000e34d  lea     rcx, [r8+20h]
0x18000e351  cmp     qword ptr [r8+38h], 8
0x18000e356  jb      short loc_18000E35B
0x18000e358  mov     rcx, [rcx]
0x18000e35b  mov     r10, [r8+30h]
0x18000e35f  mov     rax, rdx
0x18000e362  cmp     rdx, r10
0x18000e365  cmovnb  rax, r10
0x18000e369  lea     r9, [rsp+130h+var_C8]
0x18000e36e  cmp     rdi, 8
0x18000e372  cmovnb  r9, r12
0x18000e376  test    rax, rax
0x18000e379  jz      short loc_18000E395
0x18000e37b  movzx   ebx, word ptr [r9]
0x18000e37f  cmp     bx, [rcx]
0x18000e382  jnz     short loc_18000E39F
0x18000e384  add     r9, 2
0x18000e388  add     rcx, 2
0x18000e38c  sub     rax, 1
0x18000e390  jnz     short loc_18000E37B
0x18000e392  xor     r13d, r13d
0x18000e395  cmp     rdx, r10
0x18000e398  jnb     short loc_18000E3AB
0x18000e39a  or      eax, 0FFFFFFFFh
0x18000e39d  jmp     short loc_18000E3B1
0x18000e39f  sbb     eax, eax
0x18000e3a1  and     eax, 0FFFFFFFEh
0x18000e3a4  inc     eax
0x18000e3a6  xor     r13d, r13d
0x18000e3a9  jmp     short loc_18000E3B1
0x18000e3ab  mov     eax, r13d
0x18000e3ae  setnz   al
0x18000e3b1  test    eax, eax
0x18000e3b3  jns     short loc_18000E3B8
0x18000e3b5  mov     r8, r11
0x18000e3b8  or      esi, 1
0x18000e3bb  cmp     r8, r11
0x18000e3be  jnz     short loc_18000E3CD
0x18000e3c0  mov     bl, 1
0x18000e3c2  jmp     short loc_18000E3D0
0x18000e3c4  mov     rdi, [rbp+37h+var_B0]
0x18000e3c8  mov     r12, [rsp+130h+var_C8]
0x18000e3cd  mov     bl, r13b
0x18000e3d0  test    sil, 1
0x18000e3d4  jz      short loc_18000E3E8
0x18000e3d6  and     esi, 0FFFFFFFEh
0x18000e3d9  cmp     rdi, 8
0x18000e3dd  jb      short loc_18000E3E8
0x18000e3df  mov     rcx, r12
0x18000e3e2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000e3e8  test    bl, bl
0x18000e3ea  jz      loc_18000E47F
0x18000e3f0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18000e3f7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18000e3fc  mov     r12, [rsp+130h+var_D0]
0x18000e401  test    al, al
0x18000e403  jnz     short loc_18000E484
0x18000e405  mov     rdx, r12; struct _GUID *
0x18000e408  mov     rcx, r14; unsigned __int16 *
0x18000e40b  call    ?PITRTelemetry_DeleteSnapshot@@YAXPEBGPEBU_GUID@@J0@Z; PITRTelemetry_DeleteSnapshot(ushort const *,_GUID const *,long,ushort const *)
0x18000e410  call    cs:__imp_GetLastError
0x18000e416  mov     edi, eax
0x18000e418  call    cs:__imp_CurrentIP
0x18000e41e  mov     rbx, rax
0x18000e421  mov     r8, r14
0x18000e424  lea     rdx, aPitrtelemetryL_3; "PITRTelemetry_LogMaintenanceResults: Sn"...
0x18000e42b  mov     ecx, 4000000h; unsigned int
0x18000e430  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000e435  mov     [rsp+130h+var_E0], r13d
0x18000e43a  mov     [rsp+130h+var_E8], r13
0x18000e43f  mov     [rsp+130h+var_F0], edi
0x18000e443  mov     [rsp+130h+var_F8], rbx
0x18000e448  lea     rcx, aPitrtelemetryL_2; "PITRTelemetry_LogMaintenanceResults"
0x18000e44f  mov     [rsp+130h+var_100], rcx
0x18000e454  lea     rcx, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\pitr\\task\\dll\\"...
0x18000e45b  mov     [rsp+130h+var_108], rcx
0x18000e460  mov     dword ptr [rsp+130h+var_110], 202h
0x18000e468  xor     r9d, r9d
0x18000e46b  lea     r8, aD; "D"
0x18000e472  xor     edx, edx
0x18000e474  mov     rcx, rax
0x18000e477  call    cs:__imp_WdsSetupLogMessageW
0x18000e47d  jmp     short loc_18000E484
0x18000e47f  mov     r12, [rsp+130h+var_D0]
0x18000e484  mov     r14d, 1
0x18000e48a  add     r15, r14
0x18000e48d  cmp     r15, [rbp+37h+var_A0]
0x18000e491  jb      loc_18000E272
0x18000e497  mov     rdi, qword ptr [rbp+37h+var_98]
0x18000e49b  jmp     short loc_18000E4A3
0x18000e49d  mov     r14d, 1
0x18000e4a3  mov     r9d, edi; unsigned int
0x18000e4a6  mov     [rsp+130h+var_110], r12; struct _GUID *
0x18000e4ab  mov     r8, [rbp+37h+arg_40]; __int64
0x18000e4b2  mov     rdx, [rbp+37h+arg_38]; __int64
0x18000e4b6  mov     rcx, [rbp+37h+arg_30]; __int64
0x18000e4ba  call    ?PITRTelemetry_GetAllSnapshotsSizeWithVSS@@YAX_J00KPEBU_GUID@@@Z; PITRTelemetry_GetAllSnapshotsSizeWithVSS(__int64,__int64,__int64,ulong,_GUID const *)
0x18000e4bf  mov     rbx, [rbp+37h+var_90]
0x18000e4c3  test    rbx, rbx
0x18000e4c6  jz      loc_18000E639
0x18000e4cc  mov     [rbp+37h+var_58], r14d
0x18000e4d0  mov     rax, [rbx]
0x18000e4d3  lea     r8, [rbp+37h+var_58]
0x18000e4d7  mov     edi, 5
0x18000e4dc  mov     edx, edi
0x18000e4de  mov     rcx, rbx
0x18000e4e1  mov     rax, [rax+20h]
0x18000e4e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4ea  mov     r9d, [rbp+37h+var_58]
0x18000e4ee  mov     r8d, r13d
0x18000e4f1  cmp     r9d, r14d
0x18000e4f4  setz    r8b
0x18000e4f8  mov     [rsp+130h+var_110], r12
0x18000e4fd  mov     edx, eax
0x18000e4ff  lea     rcx, aRebootdelay; "RebootDelay"
0x18000e506  call    ?PITRTelemetry_SnapshotSettingValue@@YAXPEBGKHW4PITR_SETTINGS_LEVEL@PITR@@PEBU_GUID@@@Z; PITRTelemetry_SnapshotSettingValue(ushort const *,ulong,int,PITR::PITR_SETTINGS_LEVEL,_GUID const *)
0x18000e50b  mov     [rbp+37h+var_58], r14d
0x18000e50f  mov     rax, [rbx]
0x18000e512  lea     r8, [rbp+37h+var_58]
0x18000e516  mov     edx, edi
0x18000e518  mov     rcx, rbx
0x18000e51b  mov     rax, [rax+40h]
0x18000e51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e524  mov     r9d, [rbp+37h+var_58]
0x18000e528  mov     r8d, r13d
0x18000e52b  cmp     r9d, r14d
0x18000e52e  setz    r8b
0x18000e532  mov     [rsp+130h+var_110], r12
0x18000e537  mov     edx, eax
0x18000e539  lea     rcx, aSnapshotinterv; "SnapshotInterval"
0x18000e540  call    ?PITRTelemetry_SnapshotSettingValue@@YAXPEBGKHW4PITR_SETTINGS_LEVEL@PITR@@PEBU_GUID@@@Z; PITRTelemetry_SnapshotSettingValue(ushort const *,ulong,int,PITR::PITR_SETTINGS_LEVEL,_GUID const *)
0x18000e545  mov     [rbp+37h+var_58], r14d
0x18000e549  mov     rax, [rbx]
0x18000e54c  lea     r8, [rbp+37h+var_58]
0x18000e550  mov     edx, edi
0x18000e552  mov     rcx, rbx
0x18000e555  mov     rax, [rax+60h]
0x18000e559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e55e  mov     r9d, [rbp+37h+var_58]
0x18000e562  mov     r8d, r13d
0x18000e565  cmp     r9d, r14d
0x18000e568  setz    r8b
0x18000e56c  mov     [rsp+130h+var_110], r12
0x18000e571  mov     edx, eax
0x18000e573  lea     rcx, aMaxcount; "MaxCount"
0x18000e57a  call    ?PITRTelemetry_SnapshotSettingValue@@YAXPEBGKHW4PITR_SETTINGS_LEVEL@PITR@@PEBU_GUID@@@Z; PITRTelemetry_SnapshotSettingValue(ushort const *,ulong,int,PITR::PITR_SETTINGS_LEVEL,_GUID const *)
0x18000e57f  mov     [rbp+37h+var_58], r14d
0x18000e583  mov     rax, [rbx]
0x18000e586  lea     r8, [rbp+37h+var_58]
0x18000e58a  mov     edx, edi
0x18000e58c  mov     rcx, rbx
0x18000e58f  mov     rax, [rax+80h]
0x18000e596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e59b  mov     r9d, [rbp+37h+var_58]
0x18000e59f  mov     r8d, r13d
0x18000e5a2  cmp     r9d, r14d
0x18000e5a5  setz    r8b
0x18000e5a9  mov     [rsp+130h+var_110], r12
0x18000e5ae  mov     edx, eax
0x18000e5b0  lea     rcx, aMaxtimespan; "MaxTimespan"
0x18000e5b7  call    ?PITRTelemetry_SnapshotSettingValue@@YAXPEBGKHW4PITR_SETTINGS_LEVEL@PITR@@PEBU_GUID@@@Z; PITRTelemetry_SnapshotSettingValue(ushort const *,ulong,int,PITR::PITR_SETTINGS_LEVEL,_GUID const *)
0x18000e5bc  mov     [rbp+37h+var_58], r14d
0x18000e5c0  mov     rax, [rbx]
0x18000e5c3  lea     r8, [rbp+37h+var_58]
0x18000e5c7  mov     edx, edi
0x18000e5c9  mov     rcx, rbx
0x18000e5cc  mov     rax, [rax+0A0h]
0x18000e5d3  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
