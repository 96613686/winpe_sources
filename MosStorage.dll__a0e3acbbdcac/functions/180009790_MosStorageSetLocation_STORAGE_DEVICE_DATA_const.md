# MosStorageSetLocation(_STORAGE_DEVICE_DATA const &)

- ea: `0x180009790`
- end: `0x180009acc`
- name: `?MosStorageSetLocation@@YAJAEBU_STORAGE_DEVICE_DATA@@@Z`
- size: `828`
- prototype: `__int64 __fastcall(const struct _STORAGE_DEVICE_DATA *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009be0`

## callees

- `0x180001c80`
- `0x1800020a0`
- `0x180002802`
- `0x180006c44`
- `0x180007000`
- `0x1800078d4`
- `0x1800094c0`
- `0x180009510`
- `0x180009790`
- `0x18000abd0`
- `0x18000abf8`
- `0x18000c9bc`
- `0x18000cc50`
- `0x18000e7e0`
- `0x18000e7ec`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180009877`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180009a31`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180009877`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180009a31`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800099ca`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009a8f`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800099ca`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009a8f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180009a0e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180009a0e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000985b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000985b`

## string_xrefs

- `0x180009a61`: `MapsRepairAttempts`

## pseudocode

```c
__int64 __fastcall MosStorageSetLocation(const struct _STORAGE_DEVICE_DATA *a1)
{
  int DefaultStorageLocation; // eax
  int v3; // r8d
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned __int64 v7; // rbx
  __int64 v8; // rsi
  size_t v9; // rbx
  size_t v10; // rcx
  void *v11; // rax
  _QWORD *v12; // rdi
  size_t v13; // rbx
  int PersistedRegistryLocation; // eax
  int v15; // r8d
  int v16; // ebx
  LPCVOID *lpData; // rcx
  int v18; // eax
  int v19; // ecx
  unsigned int v20; // ebx
  LPCVOID v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v24; // [rsp+48h] [rbp-B8h]
  GUID Buf1; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR sz[64]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[542]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE Buf2[564]; // [rsp+51Ch] [rbp+41Ch] BYREF

  memset_0(SubKey, 0, 0x670u);
  Buf1 = *(GUID *)((char *)a1 + 1084);
  DefaultStorageLocation = GetDefaultStorageLocation(SubKey);
  if ( DefaultStorageLocation < 0 )
  {
    v3 = 829;
LABEL_45:
    v19 = DefaultStorageLocation;
    return (unsigned int)ZTraceReportPropagationNoThis(v19, "MosStorageSetLocation", v3);
  }
  if ( memcmp_0(&Buf1, Buf2, 0x10u) )
  {
    DefaultStorageLocation = EnsureStorageIsAppContainerCompliant(a1);
    if ( DefaultStorageLocation < 0 )
    {
      v3 = 842;
      goto LABEL_45;
    }
    if ( !StringFromGUID2(&Buf1, sz, 64) )
      return (unsigned int)ZTraceReportOriginationNoThis(-2147024774, "MosStorageSetLocation", 844);
    *(_OWORD *)v22 = 0;
    v23 = 0;
    v24 = 0;
    v7 = -1;
    do
      ++v7;
    while ( sz[v7] );
    v8 = 0x7FFFFFFFFFFFFFFELL;
    if ( v7 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v7 <= 7 )
    {
      v23 = v7;
      v24 = 7;
      v9 = 2 * v7;
      memcpy_0(v22, sz, v9);
      *(_WORD *)((char *)v22 + v9) = 0;
      goto LABEL_29;
    }
    if ( (v7 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v8 = v7 | 7;
      if ( (v7 | 7) < 0xA )
        v8 = 10;
      if ( (unsigned __int64)(v8 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_50;
      v10 = 2 * (v8 + 1);
      if ( !v10 )
      {
        v12 = 0;
        goto LABEL_28;
      }
    }
    else
    {
      v10 = -2;
    }
    if ( v10 >= 0x1000 )
    {
      if ( v10 + 39 >= v10 )
      {
        v11 = operator new(v10 + 39);
        if ( !v11 )
          __fastfail(5u);
        v12 = (_QWORD *)(((unsigned __int64)v11 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v12 - 1) = v11;
        goto LABEL_28;
      }
LABEL_50:
      __scrt_throw_std_bad_array_new_length();
    }
    v12 = operator new(v10);
LABEL_28:
    v22[0] = v12;
    v23 = v7;
    v24 = v8;
    v13 = 2 * v7;
    memcpy_0(v12, sz, v13);
    *(_WORD *)((char *)v12 + v13) = 0;
LABEL_29:
    memset_0(SubKey, 0, 0x208u);
    PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(1, SubKey);
    if ( PersistedRegistryLocation >= 0 )
    {
      lpData = v22;
      if ( v24 > 7 )
        lpData = (LPCVOID *)v22[0];
      v18 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, SubKey, L"MapsPreferredDeviceGuid", 1u, lpData, 2 * v23 + 2);
      if ( !v18 )
        goto LABEL_39;
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
      PersistedRegistryLocation = ZTraceReportOriginationNoThis(v18, "RegUtils::SetRegString", 93);
      if ( PersistedRegistryLocation >= 0 )
      {
LABEL_39:
        v16 = 0;
LABEL_40:
        std::wstring::~wstring(v22);
        if ( v16 < 0 )
        {
          v3 = 845;
          v19 = v16;
          return (unsigned int)ZTraceReportPropagationNoThis(v19, "MosStorageSetLocation", v3);
        }
        goto LABEL_42;
      }
      v15 = 612;
    }
    else
    {
      v15 = 607;
    }
    v16 = ZTraceReportPropagationNoThis(PersistedRegistryLocation, "RegUtils::SetMapsPersistedRegString", v15);
    goto LABEL_40;
  }
  DefaultStorageLocation = RegUtils::DeleteMapsPersistedRegValue(v4, L"MapsPreferredDeviceGuid");
  if ( DefaultStorageLocation < 0 )
  {
    v3 = 834;
    goto LABEL_45;
  }
LABEL_42:
  DefaultStorageLocation = RegUtils::DeleteMapsPersistedRegValue(v5, L"MapsRepairAttempts");
  if ( DefaultStorageLocation < 0 )
  {
    v3 = 849;
    goto LABEL_45;
  }
  v20 = 0;
  MosStorageResetCacheValues();
  MosStorageResetMigrationStateCacheValues();
  return v20;
}

```

## disassembly

```asm
0x180009790  mov     [rsp-8+arg_8], rbx
0x180009795  mov     [rsp-8+arg_10], rsi
0x18000979a  push    rbp
0x18000979b  push    rdi
0x18000979c  push    r14
0x18000979e  lea     rbp, [rsp-660h]
0x1800097a6  sub     rsp, 760h
0x1800097ad  mov     rax, cs:__security_cookie
0x1800097b4  xor     rax, rsp
0x1800097b7  mov     [rbp+670h+var_20], rax
0x1800097be  mov     rbx, rcx
0x1800097c1  xor     edx, edx; Val
0x1800097c3  mov     r8d, 670h; Size
0x1800097c9  lea     rcx, [rbp+670h+SubKey]; void *
0x1800097cd  call    memset_0
0x1800097d2  movups  xmm0, xmmword ptr [rbx+43Ch]
0x1800097d9  movdqu  [rsp+770h+Buf1], xmm0
0x1800097df  lea     rcx, [rbp+670h+SubKey]; void *
0x1800097e3  call    GetDefaultStorageLocation
0x1800097e8  xor     r14d, r14d
0x1800097eb  test    eax, eax
0x1800097ed  jns     short loc_1800097FA
0x1800097ef  mov     r8d, 33Dh
0x1800097f5  jmp     loc_180009A86
0x1800097fa  mov     r8d, 10h; Size
0x180009800  lea     rdx, [rbp+670h+Buf2]; Buf2
0x180009807  lea     rcx, [rsp+770h+Buf1]; Buf1
0x18000980c  call    memcmp_0
0x180009811  test    eax, eax
0x180009813  jnz     short loc_180009834
0x180009815  lea     rdx, ValueName; "MapsPreferredDeviceGuid"
0x18000981c  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x180009821  test    eax, eax
0x180009823  jns     loc_180009A61
0x180009829  mov     r8d, 342h
0x18000982f  jmp     loc_180009A86
0x180009834  mov     rcx, rbx
0x180009837  call    EnsureStorageIsAppContainerCompliant
0x18000983c  test    eax, eax
0x18000983e  jns     short loc_18000984B
0x180009840  mov     r8d, 34Ah
0x180009846  jmp     loc_180009A86
0x18000984b  mov     r8d, 40h ; '@'; cchMax
0x180009851  lea     rdx, [rsp+770h+sz]; lpsz
0x180009856  lea     rcx, [rsp+770h+Buf1]; rguid
0x18000985b  call    cs:__imp_StringFromGUID2
0x180009861  test    eax, eax
0x180009863  jnz     short loc_180009882
0x180009865  mov     r8d, 34Ch
0x18000986b  lea     rdx, aMosstoragesetl_0; "MosStorageSetLocation"
0x180009872  mov     ecx, 8007007Ah
0x180009877  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000987d  jmp     loc_180009A95
0x180009882  xorps   xmm0, xmm0
0x180009885  movups  xmmword ptr [rsp+770h+var_740], xmm0
0x18000988a  mov     [rsp+770h+var_730], r14
0x18000988f  mov     [rsp+770h+var_728], r14
0x180009894  lea     rax, [rsp+770h+sz]
0x180009899  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000989d  inc     rbx
0x1800098a0  cmp     [rax+rbx*2], r14w
0x1800098a5  jnz     short loc_18000989D
0x1800098a7  mov     rsi, 7FFFFFFFFFFFFFFEh
0x1800098b1  cmp     rbx, rsi
0x1800098b4  ja      loc_180009AC0
0x1800098ba  cmp     rbx, 7
0x1800098be  ja      short loc_1800098EE
0x1800098c0  mov     [rsp+770h+var_730], rbx
0x1800098c5  mov     [rsp+770h+var_728], 7
0x1800098ce  add     rbx, rbx
0x1800098d1  mov     r8, rbx; Size
0x1800098d4  lea     rdx, [rsp+770h+sz]; Src
0x1800098d9  lea     rcx, [rsp+770h+var_740]; void *
0x1800098de  call    memcpy_0
0x1800098e3  mov     word ptr [rsp+rbx+770h+var_740], r14w
0x1800098e9  jmp     loc_180009996
0x1800098ee  mov     rax, rbx
0x1800098f1  or      rax, 7
0x1800098f5  cmp     rax, rsi
0x1800098f8  jbe     short loc_180009929
0x1800098fa  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x180009901  cmp     rcx, 1000h
0x180009908  jb      short loc_180009967
0x18000990a  lea     rax, [rcx+27h]
0x18000990e  cmp     rax, rcx
0x180009911  jbe     loc_180009AC6
0x180009917  mov     rcx, rax; Size
0x18000991a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000991f  test    rax, rax
0x180009922  jnz     short loc_180009959
0x180009924  lea     ecx, [rax+5]
0x180009927  int     29h; Win8: RtlFailFast(ecx)
0x180009929  mov     rsi, rax
0x18000992c  mov     ecx, 0Ah
0x180009931  cmp     rax, rcx
0x180009934  cmovb   rsi, rcx
0x180009938  lea     rcx, [rsi+1]
0x18000993c  mov     rax, 7FFFFFFFFFFFFFFFh
0x180009946  cmp     rcx, rax
0x180009949  ja      loc_180009AC6
0x18000994f  add     rcx, rcx
0x180009952  jnz     short loc_180009901
0x180009954  mov     rdi, r14
0x180009957  jmp     short loc_18000996F
0x180009959  lea     rdi, [rax+27h]
0x18000995d  and     rdi, 0FFFFFFFFFFFFFFE0h
0x180009961  mov     [rdi-8], rax
0x180009965  jmp     short loc_18000996F
0x180009967  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000996c  mov     rdi, rax
0x18000996f  mov     [rsp+770h+var_740], rdi
0x180009974  mov     [rsp+770h+var_730], rbx
0x180009979  mov     [rsp+770h+var_728], rsi
0x18000997e  add     rbx, rbx
0x180009981  mov     r8, rbx; Size
0x180009984  lea     rdx, [rsp+770h+sz]; Src
0x180009989  mov     rcx, rdi; void *
0x18000998c  call    memcpy_0
0x180009991  mov     [rbx+rdi], r14w
0x180009996  xor     edx, edx; Val
0x180009998  mov     r8d, 208h; Size
0x18000999e  lea     rcx, [rbp+670h+SubKey]; void *
0x1800099a2  call    memset_0
0x1800099a7  lea     rdx, [rbp+670h+SubKey]
0x1800099ab  mov     ebx, 1
0x1800099b0  mov     ecx, ebx
0x1800099b2  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x1800099b7  test    eax, eax
0x1800099b9  jns     short loc_1800099D4
0x1800099bb  mov     r8d, 25Fh
0x1800099c1  lea     rdx, aRegutilsSetmap; "RegUtils::SetMapsPersistedRegString"
0x1800099c8  mov     ecx, eax
0x1800099ca  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800099d0  mov     ebx, eax
0x1800099d2  jmp     short loc_180009A49
0x1800099d4  mov     eax, dword ptr [rsp+770h+var_730]
0x1800099d8  lea     eax, ds:2[rax*2]
0x1800099df  lea     rcx, [rsp+770h+var_740]
0x1800099e4  cmp     [rsp+770h+var_728], 7
0x1800099ea  cmova   rcx, [rsp+770h+var_740]
0x1800099f0  mov     [rsp+770h+cbData], eax; cbData
0x1800099f4  mov     [rsp+770h+lpData], rcx; lpData
0x1800099f9  mov     r9d, ebx; dwType
0x1800099fc  lea     r8, ValueName; "MapsPreferredDeviceGuid"
0x180009a03  lea     rdx, [rbp+670h+SubKey]; lpSubKey
0x180009a07  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009a0e  call    cs:__imp_RegSetKeyValueW
0x180009a14  test    eax, eax
0x180009a16  jz      short loc_180009A46
0x180009a18  jle     short loc_180009A22
0x180009a1a  movzx   eax, ax
0x180009a1d  or      eax, 80070000h
0x180009a22  mov     r8d, 5Dh ; ']'
0x180009a28  lea     rdx, aRegutilsSetreg; "RegUtils::SetRegString"
0x180009a2f  mov     ecx, eax
0x180009a31  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180009a37  test    eax, eax
0x180009a39  jns     short loc_180009A46
0x180009a3b  mov     r8d, 264h
0x180009a41  jmp     loc_1800099C1
0x180009a46  mov     ebx, r14d
0x180009a49  lea     rcx, [rsp+770h+var_740]
0x180009a4e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009a53  test    ebx, ebx
0x180009a55  jns     short loc_180009A61
0x180009a57  mov     r8d, 34Dh
0x180009a5d  mov     ecx, ebx
0x180009a5f  jmp     short loc_180009A88
0x180009a61  lea     rdx, aMapsrepairatte; "MapsRepairAttempts"
0x180009a68  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x180009a6d  test    eax, eax
0x180009a6f  js      short loc_180009A80
0x180009a71  mov     ebx, r14d
0x180009a74  call    ?MosStorageResetCacheValues@@YAXXZ; MosStorageResetCacheValues(void)
0x180009a79  call    ?MosStorageResetMigrationStateCacheValues@@YAXXZ; MosStorageResetMigrationStateCacheValues(void)
0x180009a7e  jmp     short loc_180009A97
0x180009a80  mov     r8d, 351h
0x180009a86  mov     ecx, eax
0x180009a88  lea     rdx, aMosstoragesetl_0; "MosStorageSetLocation"
0x180009a8f  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180009a95  mov     ebx, eax
0x180009a97  mov     eax, ebx
0x180009a99  mov     rcx, [rbp+670h+var_20]
0x180009aa0  xor     rcx, rsp; StackCookie
0x180009aa3  call    __security_check_cookie
0x180009aa8  lea     r11, [rsp+770h+var_10]
0x180009ab0  mov     rbx, [r11+28h]
0x180009ab4  mov     rsi, [r11+30h]
0x180009ab8  mov     rsp, r11
0x180009abb  pop     r14
0x180009abd  pop     rdi
0x180009abe  pop     rbp
0x180009abf  retn
0x180009ac0  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180009ac6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
