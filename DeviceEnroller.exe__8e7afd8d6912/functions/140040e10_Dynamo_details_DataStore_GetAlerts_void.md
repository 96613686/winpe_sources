# Dynamo::details::DataStore::GetAlerts(void)

- ea: `0x140040e10`
- end: `0x14004113c`
- name: `?GetAlerts@DataStore@details@Dynamo@@UEBA?AV?$vector@V?$unique_struct@UOMADMALERTINFO@@$$A6AJPEAU1@@Z$1?LocalFreeOmadmAlertInfo@dmstd@@YAJ0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@UOMADMALERTINFO@@$$A6AJPEAU1@@Z$1?LocalFreeOmadmAlertInfo@dmstd@@YAJ0@Z$$T$0A@@wil@@@std@@@std@@XZ`
- size: `812`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140004e28`
- `0x14000a6e4`
- `0x140037194`
- `0x14003e278`
- `0x14003e934`
- `0x14003fd64`
- `0x14004053c`
- `0x140040e10`
- `0x1400419a4`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140040fb7`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140040fb7`
- `DMCmnUtils!OmaDmRegistryGetAllSubKeys` at `0x140040e89`
- `DMCmnUtils!OmaDmRegistryGetAllSubKeys` at `0x140040e89`
- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x140040f7d`
- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x140040f7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140040eee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140040eee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041043`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400410ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041043`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400410ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Dynamo::details::DataStore::GetAlerts(__int64 a1, _QWORD *a2)
{
  unsigned int v3; // r14d
  int DynamicManagementRegistryKey; // eax
  int AllSubKeys; // eax
  __int64 v6; // rdx
  LPCWSTR *v7; // rdi
  unsigned __int16 **v8; // r15
  unsigned int v9; // eax
  HKEY v10; // r12
  int v11; // r14d
  unsigned int i; // esi
  unsigned int String; // eax
  const char *v14; // r9
  int DWORD; // eax
  _OWORD *v16; // rdx
  struct OMADMALERTINFO *v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  int phkResult; // [rsp+20h] [rbp-99h]
  unsigned int phkResulta; // [rsp+20h] [rbp-99h]
  HKEY *v23; // [rsp+28h] [rbp-91h]
  __int128 v24; // [rsp+30h] [rbp-89h] BYREF
  __int64 v25; // [rsp+40h] [rbp-79h]
  int v26; // [rsp+48h] [rbp-71h]
  unsigned __int16 **v27; // [rsp+50h] [rbp-69h] BYREF
  __int64 v28; // [rsp+58h] [rbp-61h]
  unsigned __int16 ***v29; // [rsp+60h] [rbp-59h]
  _QWORD v30[3]; // [rsp+68h] [rbp-51h] BYREF
  __int128 v31; // [rsp+80h] [rbp-39h] BYREF
  __int128 v32; // [rsp+90h] [rbp-29h] BYREF
  __int128 v33; // [rsp+A0h] [rbp-19h]
  __int128 v34; // [rsp+B0h] [rbp-9h] BYREF
  _QWORD v35[10]; // [rsp+C0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  unsigned int v37; // [rsp+120h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+130h] [rbp+77h] BYREF
  HKEY v39; // [rsp+138h] [rbp+7Fh] BYREF

  v3 = 0;
  v26 = 0;
  hKey = 0;
  DynamicManagementRegistryKey = dmstd::GetDynamicManagementRegistryKey(
                                   *(dmstd **)(a1 + 8),
                                   *(const unsigned __int16 **)(a1 + 16),
                                   L"Alerts",
                                   0,
                                   (bool)&hKey,
                                   v23);
  if ( DynamicManagementRegistryKey < 0 )
  {
    if ( DynamicManagementRegistryKey != -2147024894 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x138,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
        (const char *)(unsigned int)DynamicManagementRegistryKey,
        phkResult);
    *a2 = 0;
    a2[1] = 0;
    a2[2] = 0;
  }
  else
  {
    v27 = 0;
    v28 = 0;
    v29 = &v27;
    LODWORD(v30[0]) = 0;
    BYTE4(v30[0]) = 1;
    AllSubKeys = OmaDmRegistryGetAllSubKeys(hKey, (unsigned int *)v30, &v27);
    if ( AllSubKeys < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x127,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
        (const char *)(unsigned int)AllSubKeys,
        phkResult);
    if ( BYTE4(v30[0]) )
      v29[1] = (unsigned __int16 **)LODWORD(v30[0]);
    v24 = 0;
    v6 = 0;
    v25 = 0;
    v7 = (LPCWSTR *)v27;
    v8 = &v27[v28];
    if ( v27 != v8 )
    {
      do
      {
        v39 = 0;
        v9 = RegOpenKeyExW(hKey, *v7, 0, 0x20019u, &v39);
        if ( v9 )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            (void *)0x12D,
            (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
            (const char *)v9,
            phkResulta);
        v10 = v39;
        memset_0(&v31, 0, 0x40u);
        v11 = v3 | 2;
        v26 = v11;
        v35[0] = L"AlertData";
        v35[1] = L"Source";
        v35[2] = L"Target";
        v35[3] = L"AlertType";
        v29 = (unsigned __int16 ***)&v32 + 1;
        v30[0] = &v32;
        v30[1] = (char *)&v34 + 8;
        v30[2] = (char *)&v31 + 8;
        for ( i = 0; i < 4; ++i )
        {
          String = OmDmRegistryAllocAndGetString(v10, v35[i], 0, v30[(int)i - 1]);
          v14 = (const char *)String;
          if ( String == -2147024894 )
            v14 = 0;
          if ( (int)v14 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x113,
              (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
              v14,
              phkResulta);
        }
        v37 = 0;
        DWORD = OmaDmRegistryGetDWORD(v10, 0, L"EventType", &v37);
        if ( DWORD < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x117,
            (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
            (const char *)(unsigned int)DWORD,
            phkResulta);
        DWORD1(v31) = v37;
        LODWORD(v31) = 64;
        LODWORD(v33) = 1;
        v16 = (_OWORD *)*((_QWORD *)&v24 + 1);
        if ( *((_QWORD *)&v24 + 1) == v25 )
        {
          std::vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&long dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>::_Emplace_reallocate<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&long dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>(
            &v24,
            *((_QWORD *)&v24 + 1),
            &v31);
        }
        else
        {
          **((_OWORD **)&v24 + 1) = v31;
          v16[1] = v32;
          v16[2] = v33;
          v16[3] = v34;
          memset_0(&v31, 0, 0x40u);
          *((_QWORD *)&v24 + 1) += 64LL;
        }
        v3 = v11 & 0xFFFFFFFD;
        dmstd::LocalFreeOmadmAlertInfo((dmstd *)&v31, v17);
        if ( v39 )
          RegCloseKey(v39);
        ++v7;
      }
      while ( v7 != (LPCWSTR *)v8 );
      v6 = v25;
    }
    v25 = 0;
    v18 = *((_QWORD *)&v24 + 1);
    v19 = v24;
    v24 = 0u;
    *a2 = v19;
    a2[1] = v18;
    a2[2] = v6;
    std::vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&long dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>::~vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&long dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>(&v24);
    wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>((__int64)&v27);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return a2;
}

```

## disassembly

```asm
0x140040e10  mov     [rsp-8+arg_8], rbx
0x140040e15  push    rbp
0x140040e16  push    rsi
0x140040e17  push    rdi
0x140040e18  push    r12
0x140040e1a  push    r13
0x140040e1c  push    r14
0x140040e1e  push    r15
0x140040e20  lea     rbp, [rsp-27h]
0x140040e25  sub     rsp, 0E0h
0x140040e2c  mov     rbx, rdx
0x140040e2f  xor     r13d, r13d
0x140040e32  mov     r14d, r13d
0x140040e35  mov     [rbp+57h+var_C8], r13d
0x140040e39  mov     [rbp+57h+hKey], r13
0x140040e3d  lea     rax, [rbp+57h+hKey]
0x140040e41  mov     [rsp+110h+phkResult], rax; int
0x140040e46  xor     r9d, r9d; unsigned __int16 *
0x140040e49  lea     r8, aAlerts; "Alerts"
0x140040e50  mov     rdx, [rcx+10h]; unsigned __int16 *
0x140040e54  mov     rcx, [rcx+8]; this
0x140040e58  call    ?GetDynamicManagementRegistryKey@dmstd@@YAJPEBG00_NPEAPEAUHKEY__@@@Z; dmstd::GetDynamicManagementRegistryKey(ushort const *,ushort const *,ushort const *,bool,HKEY__ * *)
0x140040e5d  test    eax, eax
0x140040e5f  js      loc_140041093
0x140040e65  mov     [rbp+57h+var_C0], r13
0x140040e69  mov     [rbp+57h+var_B8], r13
0x140040e6d  lea     rax, [rbp+57h+var_C0]
0x140040e71  mov     [rbp+57h+var_B0], rax
0x140040e75  mov     dword ptr [rbp+57h+var_A8], r13d
0x140040e79  mov     byte ptr [rbp+57h+var_A8+4], 1
0x140040e7d  lea     r8, [rbp+57h+var_C0]
0x140040e81  lea     rdx, [rbp+57h+var_A8]
0x140040e85  mov     rcx, [rbp+57h+hKey]
0x140040e89  call    cs:__imp_?OmaDmRegistryGetAllSubKeys@@YAJPEAUHKEY__@@PEAKPEAPEAPEAG@Z; OmaDmRegistryGetAllSubKeys(HKEY__ *,ulong *,ushort * * *)
0x140040e8f  mov     rcx, [rbp+5Fh]; this
0x140040e93  test    eax, eax
0x140040e95  js      loc_140041100
0x140040e9b  cmp     byte ptr [rbp+57h+var_A8+4], r13b
0x140040e9f  jz      short loc_140040EAC
0x140040ea1  mov     ecx, dword ptr [rbp+57h+var_A8]
0x140040ea4  mov     rax, [rbp+57h+var_B0]
0x140040ea8  mov     [rax+8], rcx
0x140040eac  xorps   xmm0, xmm0
0x140040eaf  movdqu  [rsp+110h+var_E0], xmm0
0x140040eb5  mov     rdx, r13
0x140040eb8  mov     [rbp+57h+var_D0], rdx
0x140040ebc  mov     rdi, [rbp+57h+var_C0]
0x140040ec0  mov     rax, [rbp+57h+var_B8]
0x140040ec4  lea     r15, [rdi+rax*8]
0x140040ec8  cmp     rdi, r15
0x140040ecb  jz      loc_14004105A
0x140040ed1  mov     [rbp+57h+arg_18], r13
0x140040ed5  lea     rax, [rbp+57h+arg_18]
0x140040ed9  mov     [rsp+110h+phkResult], rax; int
0x140040ede  mov     r9d, 20019h; samDesired
0x140040ee4  xor     r8d, r8d; ulOptions
0x140040ee7  mov     rdx, [rdi]; lpSubKey
0x140040eea  mov     rcx, [rbp+57h+hKey]; hKey
0x140040eee  call    cs:__imp_RegOpenKeyExW
0x140040ef4  mov     rcx, [rbp+5Fh]; this
0x140040ef8  test    eax, eax
0x140040efa  jnz     loc_1400410D2
0x140040f00  mov     r12, [rbp+57h+arg_18]
0x140040f04  xor     edx, edx; Val
0x140040f06  lea     r8d, [rax+40h]; Size
0x140040f0a  lea     rcx, [rbp+57h+var_90]; void *
0x140040f0e  call    memset_0
0x140040f13  or      r14d, 2
0x140040f17  mov     [rbp+57h+var_C8], r14d
0x140040f1b  lea     rax, aAlertdata; "AlertData"
0x140040f22  mov     [rbp+57h+var_50], rax
0x140040f26  lea     rax, aSource; "Source"
0x140040f2d  mov     [rbp+57h+var_48], rax
0x140040f31  lea     rax, aTarget; "Target"
0x140040f38  mov     [rbp+57h+var_40], rax
0x140040f3c  lea     rax, aAlerttype; "AlertType"
0x140040f43  mov     [rbp+57h+var_38], rax
0x140040f47  lea     rax, [rbp+57h+var_80+8]
0x140040f4b  mov     [rbp+57h+var_B0], rax
0x140040f4f  lea     rax, [rbp+57h+var_80]
0x140040f53  mov     [rbp+57h+var_A8], rax
0x140040f57  lea     rax, [rbp+57h+var_58]
0x140040f5b  mov     [rbp+57h+var_A0], rax
0x140040f5f  lea     rax, [rbp+57h+var_90+8]
0x140040f63  mov     [rbp+57h+var_98], rax
0x140040f67  mov     esi, r13d
0x140040f6a  movsxd  rdx, esi
0x140040f6d  mov     r9, [rbp+rdx*8+57h+var_B0]
0x140040f72  xor     r8d, r8d
0x140040f75  mov     rdx, [rbp+rdx*8+57h+var_50]
0x140040f7a  mov     rcx, r12
0x140040f7d  call    cs:__imp_?OmDmRegistryAllocAndGetString@@YAJPEAUHKEY__@@PEBGW4AllocFunction@@PEAPEAG@Z; OmDmRegistryAllocAndGetString(HKEY__ *,ushort const *,AllocFunction,ushort * *)
0x140040f83  mov     r9d, eax
0x140040f86  cmp     eax, 80070002h
0x140040f8b  cmovz   r9d, r13d; char *
0x140040f8f  mov     rcx, [rbp+5Fh]; this
0x140040f93  test    r9d, r9d
0x140040f96  js      loc_14004112A
0x140040f9c  inc     esi
0x140040f9e  cmp     esi, 4
0x140040fa1  jb      short loc_140040F6A
0x140040fa3  mov     [rbp+57h+arg_0], r13d
0x140040fa7  lea     r9, [rbp+57h+arg_0]
0x140040fab  lea     r8, aEventtype; "EventType"
0x140040fb2  xor     edx, edx
0x140040fb4  mov     rcx, r12
0x140040fb7  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140040fbd  mov     rcx, [rbp+5Fh]; this
0x140040fc1  test    eax, eax
0x140040fc3  js      loc_140041115
0x140040fc9  mov     eax, [rbp+57h+arg_0]
0x140040fcc  mov     dword ptr [rbp+57h+var_90+4], eax
0x140040fcf  mov     dword ptr [rbp+57h+var_90], 40h ; '@'
0x140040fd6  mov     dword ptr [rbp+57h+var_70], 1
0x140040fdd  mov     rdx, qword ptr [rsp+110h+var_E0+8]
0x140040fe2  cmp     rdx, [rbp+57h+var_D0]
0x140040fe6  jz      short loc_14004101E
0x140040fe8  movups  xmm0, [rbp+57h+var_90]
0x140040fec  movups  xmmword ptr [rdx], xmm0
0x140040fef  movups  xmm1, [rbp+57h+var_80]
0x140040ff3  movups  xmmword ptr [rdx+10h], xmm1
0x140040ff7  movups  xmm0, [rbp+57h+var_70]
0x140040ffb  movups  xmmword ptr [rdx+20h], xmm0
0x140040fff  movups  xmm1, xmmword ptr [rbp-9]
0x140041003  movups  xmmword ptr [rdx+30h], xmm1
0x140041007  xor     edx, edx; Val
0x140041009  lea     r8d, [rdx+40h]; Size
0x14004100d  lea     rcx, [rbp+57h+var_90]; void *
0x140041011  call    memset_0
0x140041016  add     qword ptr [rsp+110h+var_E0+8], 40h ; '@'
0x14004101c  jmp     short loc_14004102C
0x14004101e  lea     r8, [rbp+57h+var_90]
0x140041022  lea     rcx, [rsp+110h+var_E0]
0x140041027  call    ??$_Emplace_reallocate@V?$unique_struct@UOMADMALERTINFO@@$$A6AJPEAU1@@Z$1?LocalFreeOmadmAlertInfo@dmstd@@YAJ0@Z$$T$0A@@wil@@@?$vector@V?$unique_struct@UOMADMALERTINFO@@$$A6AJPEAU1@@Z$1?LocalFreeOmadmAlertInfo@dmstd@@YAJ0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@UOMADMALERTINFO@@$$A6AJPEAU1@@Z$1?LocalFreeOmadmAlertInfo@dmstd@@YAJ0@Z$$T$0A@@wil@@@std@@@std@@AEAAPEAV?$unique_struct@UOMADMALERTINFO@@$$A6AJPEAU1@@Z$1?LocalFreeOmadmAlertInfo@dmstd@@YAJ0@Z$$T$0A@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>::_Emplace_reallocate<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>(wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0> * const,wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0> &&)
0x14004102c  and     r14d, 0FFFFFFFDh
0x140041030  lea     rcx, [rbp+57h+var_90]; this
0x140041034  call    ?LocalFreeOmadmAlertInfo@dmstd@@YAJPEAUOMADMALERTINFO@@@Z; dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *)
0x140041039  nop
0x14004103a  mov     rcx, [rbp+57h+arg_18]; hKey
0x14004103e  test    rcx, rcx
0x140041041  jz      short loc_140041049
0x140041043  call    cs:__imp_RegCloseKey
0x140041049  add     rdi, 8
0x14004104d  cmp     rdi, r15
0x140041050  jnz     loc_140040ED1
0x140041056  mov     rdx, [rbp+57h+var_D0]
0x14004105a  mov     [rbp+57h+var_D0], r13
0x14004105e  mov     rcx, qword ptr [rsp+110h+var_E0+8]
0x140041063  mov     qword ptr [rsp+110h+var_E0+8], r13
0x140041068  mov     rax, qword ptr [rsp+110h+var_E0]
0x14004106d  mov     qword ptr [rsp+110h+var_E0], r13
0x140041072  mov     [rbx], rax
0x140041075  mov     [rbx+8], rcx
0x140041079  mov     [rbx+10h], rdx
0x14004107d  lea     rcx, [rsp+110h+var_E0]
0x140041082  call    ??1?$vector@V?$unique_struct@UOMADMALERTINFO@@$$A6AJPEAU1@@Z$1?LocalFreeOmadmAlertInfo@dmstd@@YAJ0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@UOMADMALERTINFO@@$$A6AJPEAU1@@Z$1?LocalFreeOmadmAlertInfo@dmstd@@YAJ0@Z$$T$0A@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>::~vector<wil::unique_struct<OMADMALERTINFO,long (OMADMALERTINFO *),&dmstd::LocalFreeOmadmAlertInfo(OMADMALERTINFO *),std::nullptr_t,0>>(void)
0x140041087  nop
0x140041088  lea     rcx, [rbp+57h+var_C0]
0x14004108c  call    ??1?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x140041091  jmp     short loc_1400410A5
0x140041093  cmp     eax, 80070002h
0x140041098  jnz     short loc_1400410E7
0x14004109a  mov     [rbx], r13
0x14004109d  mov     [rbx+8], r13
0x1400410a1  mov     [rbx+10h], r13
0x1400410a5  mov     rcx, [rbp+57h+hKey]; hKey
0x1400410a9  test    rcx, rcx
0x1400410ac  jz      short loc_1400410B4
0x1400410ae  call    cs:__imp_RegCloseKey
0x1400410b4  mov     rax, rbx
0x1400410b7  mov     rbx, [rsp+110h+arg_8]
0x1400410bf  add     rsp, 0E0h
0x1400410c6  pop     r15
0x1400410c8  pop     r14
0x1400410ca  pop     r13
0x1400410cc  pop     r12
0x1400410ce  pop     rdi
0x1400410cf  pop     rsi
0x1400410d0  pop     rbp
0x1400410d1  retn
0x1400410d2  mov     r9d, eax; char *
0x1400410d5  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400410dc  mov     edx, 12Dh; void *
0x1400410e1  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1400410e7  mov     rcx, [rbp+5Fh]; this
0x1400410eb  mov     r9d, eax; char *
0x1400410ee  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400410f5  mov     edx, 138h; void *
0x1400410fa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140041100  mov     r9d, eax; char *
0x140041103  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14004110a  mov     edx, 127h; void *
0x14004110f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140041115  mov     r9d, eax; char *
0x140041118  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14004111f  mov     edx, 117h; void *
0x140041124  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14004112a  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140041131  mov     edx, 113h; void *
0x140041136  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
