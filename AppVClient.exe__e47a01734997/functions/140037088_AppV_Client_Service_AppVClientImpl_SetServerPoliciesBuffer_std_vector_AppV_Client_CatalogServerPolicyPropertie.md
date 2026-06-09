# AppV::Client::Service::AppVClientImpl::SetServerPoliciesBuffer(std::vector<AppV::Client::CatalogServerPolicyProperties,std::allocator<AppV::Client::CatalogServerPolicyProperties>> const &,tagSAFEARRAY * *)

- ea: `0x140037088`
- end: `0x14003735a`
- name: `?SetServerPoliciesBuffer@AppVClientImpl@Service@Client@AppV@@AEAA_KAEBV?$vector@UCatalogServerPolicyProperties@Client@AppV@@V?$allocator@UCatalogServerPolicyProperties@Client@AppV@@@std@@@std@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x140028330`

## callees

- `0x140018bec`
- `0x140037088`
- `0x1400390d0`
- `0x14006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003710f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400372b4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003710f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400372b4`
- `OLEAUT32!__imp_SysAllocString` at `0x1400371e5`
- `OLEAUT32!__imp_SysAllocString` at `0x140037206`
- `OLEAUT32!__imp_SysAllocString` at `0x1400371e5`
- `OLEAUT32!__imp_SysAllocString` at `0x140037206`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14003717b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140037293`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140037338`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14003717b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140037293`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140037338`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140037171`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140037242`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140037289`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14003732e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140037171`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140037242`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140037289`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14003732e`
- `OLEAUT32!__imp_GetRecordInfoFromGuids` at `0x1400370f3`
- `OLEAUT32!__imp_GetRecordInfoFromGuids` at `0x1400370f3`

## string_xrefs

- `0x140037108`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x14003711f`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x1400372ad`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x1400372c4`: `admin\appman\appv\client\host\service\publicapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppV::Client::Service::AppVClientImpl::SetServerPoliciesBuffer(
        __int64 a1,
        __int64 *a2,
        SAFEARRAY **a3)
{
  HRESULT RecordInfoFromGuids; // eax
  __int64 v6; // rdi
  char *v7; // rax
  const char *v8; // rax
  unsigned __int64 v9; // rbx
  SAFEARRAY *v10; // rcx
  __int64 v12; // rdi
  __int64 v13; // rdx
  unsigned int v14; // r14d
  __int64 v15; // r15
  unsigned __int64 v16; // rsi
  const OLECHAR *v17; // rcx
  unsigned __int64 v18; // rcx
  BSTR v19; // rax
  SAFEARRAY *v20; // rax
  char v21; // dl
  SAFEARRAY *v22; // rcx
  char *v23; // rax
  const char *v24; // rax
  SAFEARRAY *v25; // rcx
  _BYTE v26[8]; // [rsp+30h] [rbp-20h] BYREF
  SAFEARRAY *psa[2]; // [rsp+38h] [rbp-18h]
  int v28; // [rsp+48h] [rbp-8h]
  IRecordInfo *v29; // [rsp+80h] [rbp+30h] BYREF
  __int64 v30; // [rsp+98h] [rbp+48h] BYREF

  *(_OWORD *)psa = 0;
  v28 = 0;
  v26[0] = 0;
  v30 = 0;
  v29 = 0;
  RecordInfoFromGuids = GetRecordInfoFromGuids(
                          &LIBID_AppVClientLib,
                          1u,
                          0,
                          0,
                          &GUID_aac31486_121c_4420_8cb8_cc61495a9f9f,
                          &v29);
  v6 = (unsigned int)RecordInfoFromGuids;
  if ( RecordInfoFromGuids < 0 )
  {
    v7 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
    if ( v7 )
      v8 = v7 + 1;
    else
      v8 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
    v9 = v6
       | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v8) << 52)
       | 0xF12300000000LL;
    if ( v29 )
      ((void (__fastcall *)(IRecordInfo *))v29->lpVtbl->Release)(v29);
LABEL_7:
    v10 = psa[0];
    if ( psa[0] )
    {
      if ( v26[0] )
      {
        SafeArrayUnaccessData(psa[0]);
        v10 = psa[0];
      }
      SafeArrayDestroy(v10);
    }
    return v9;
  }
  v12 = appv::utility::safe_array_with_structs<ServerPolicyProperties>::create_safe_array(
          v26,
          &v29,
          (a2[1] - *a2) >> 6,
          &v30);
  if ( (v12 & 0x8000000000LL) != 0 )
  {
    v13 = *a2;
    if ( (a2[1] - *a2) >> 6 )
    {
      v14 = 0;
      v15 = v30;
      while ( 1 )
      {
        v16 = (unsigned __int64)v14 << 6;
        v17 = (const OLECHAR *)(v16 + v13);
        if ( *(_QWORD *)(v16 + v13 + 24) > 7u )
          v17 = *(const OLECHAR **)v17;
        *(_QWORD *)(v15 + 16LL * v14) = SysAllocString(v17);
        v18 = v16 + *a2 + 32;
        if ( *(_QWORD *)(v18 + 24) > 7u )
          v18 = *(_QWORD *)v18;
        v19 = SysAllocString((const OLECHAR *)v18);
        *(_QWORD *)(v15 + 16LL * v14 + 8) = v19;
        if ( !*(_QWORD *)(v15 + 16LL * v14) || !v19 )
          break;
        ++v14;
        v13 = *a2;
        if ( v14 >= (unsigned __int64)((a2[1] - *a2) >> 6) )
          goto LABEL_22;
      }
      v23 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
      if ( v23 )
        v24 = v23 + 1;
      else
        v24 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
      v9 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v24) << 52)
         | 0xF3230000000ELL;
      if ( v29 )
        ((void (__fastcall *)(IRecordInfo *))v29->lpVtbl->Release)(v29);
      goto LABEL_7;
    }
LABEL_22:
    SafeArrayUnaccessData(psa[0]);
    v20 = psa[0];
    *(_OWORD *)psa = 0;
    v28 = 0;
    v21 = 0;
    v26[0] = 0;
    *a3 = v20;
    if ( v29 )
    {
      ((void (__fastcall *)(IRecordInfo *))v29->lpVtbl->Release)(v29);
      v21 = v26[0];
    }
    v22 = psa[0];
    if ( psa[0] )
    {
      if ( v21 )
      {
        SafeArrayUnaccessData(psa[0]);
        v22 = psa[0];
      }
      SafeArrayDestroy(v22);
    }
    return 0x8000000000LL;
  }
  else
  {
    if ( v29 )
      ((void (__fastcall *)(IRecordInfo *))v29->lpVtbl->Release)(v29);
    v25 = psa[0];
    if ( psa[0] )
    {
      if ( v26[0] )
      {
        SafeArrayUnaccessData(psa[0]);
        v25 = psa[0];
      }
      SafeArrayDestroy(v25);
    }
    return v12;
  }
}

```

## disassembly

```asm
0x140037088  mov     r11, rsp
0x14003708b  mov     [r11+10h], rbx
0x14003708f  mov     [r11+18h], rsi
0x140037093  mov     [r11+8], rcx
0x140037097  push    rbp
0x140037098  push    rdi
0x140037099  push    r12
0x14003709b  push    r14
0x14003709d  push    r15
0x14003709f  mov     rbp, rsp
0x1400370a2  sub     rsp, 50h
0x1400370a6  mov     r12, r8
0x1400370a9  mov     rbx, rdx
0x1400370ac  xorps   xmm0, xmm0
0x1400370af  movdqu  xmmword ptr [rbp+psa], xmm0
0x1400370b4  mov     [rbp+var_8], 0
0x1400370bb  mov     [rbp+var_20], 0
0x1400370bf  mov     [rbp+arg_18], 0
0x1400370c7  mov     [rbp+arg_0], 0
0x1400370cf  lea     rax, [rbp+arg_0]
0x1400370d3  mov     [r11-50h], rax
0x1400370d7  lea     rax, _GUID_aac31486_121c_4420_8cb8_cc61495a9f9f
0x1400370de  mov     [r11-58h], rax
0x1400370e2  xor     r9d, r9d; lcid
0x1400370e5  xor     r8d, r8d; uVerMinor
0x1400370e8  lea     edx, [r9+1]; uVerMajor
0x1400370ec  lea     rcx, LIBID_AppVClientLib; rGuidTypeLib
0x1400370f3  call    cs:__imp_GetRecordInfoFromGuids
0x1400370f9  mov     edi, eax
0x1400370fb  test    eax, eax
0x1400370fd  jns     loc_140037189
0x140037103  mov     edx, 5Ch ; '\'; Ch
0x140037108  lea     rcx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x14003710f  call    cs:__imp_strrchr
0x140037115  test    rax, rax
0x140037118  jz      short loc_14003711F
0x14003711a  inc     rax
0x14003711d  jmp     short loc_140037126
0x14003711f  lea     rax, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140037126  mov     rdx, rax; char *
0x140037129  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140037130  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140037135  mov     rbx, rax
0x140037138  shl     rbx, 34h
0x14003713c  or      rbx, rdi
0x14003713f  mov     rax, 0F12300000000h
0x140037149  or      rbx, rax
0x14003714c  mov     rcx, [rbp+arg_0]
0x140037150  test    rcx, rcx
0x140037153  jz      short loc_140037162
0x140037155  mov     rax, [rcx]
0x140037158  mov     rax, [rax+10h]
0x14003715c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037161  nop
0x140037162  mov     rcx, [rbp+psa]; psa
0x140037166  test    rcx, rcx
0x140037169  jz      short loc_140037181
0x14003716b  cmp     [rbp+var_20], 0
0x14003716f  jz      short loc_14003717B
0x140037171  call    cs:__imp_SafeArrayUnaccessData
0x140037177  mov     rcx, [rbp+psa]; psa
0x14003717b  call    cs:__imp_SafeArrayDestroy
0x140037181  mov     rax, rbx
0x140037184  jmp     loc_140037341
0x140037189  mov     r8, [rbx+8]
0x14003718d  sub     r8, [rbx]
0x140037190  sar     r8, 6
0x140037194  lea     r9, [rbp+arg_18]
0x140037198  lea     rdx, [rbp+arg_0]
0x14003719c  lea     rcx, [rbp+var_20]
0x1400371a0  call    ?create_safe_array@?$safe_array_with_structs@UServerPolicyProperties@@@utility@appv@@QEAA_KAEBV?$CComPtr@UIRecordInfo@@@ATL@@IAEAPEAUServerPolicyProperties@@@Z; appv::utility::safe_array_with_structs<ServerPolicyProperties>::create_safe_array(ATL::CComPtr<IRecordInfo> const &,uint,ServerPolicyProperties * &)
0x1400371a5  mov     rdi, rax
0x1400371a8  bt      rax, 27h ; '''
0x1400371ad  jnb     loc_140037309
0x1400371b3  mov     rdx, [rbx]
0x1400371b6  mov     rax, [rbx+8]
0x1400371ba  sub     rax, rdx
0x1400371bd  sar     rax, 6
0x1400371c1  test    rax, rax
0x1400371c4  jz      short loc_14003723E
0x1400371c6  xor     r14d, r14d
0x1400371c9  mov     r15, [rbp+arg_18]
0x1400371cd  mov     edi, r14d
0x1400371d0  mov     esi, r14d
0x1400371d3  shl     rsi, 6
0x1400371d7  lea     rcx, [rsi+rdx]
0x1400371db  cmp     qword ptr [rcx+18h], 7
0x1400371e0  jbe     short loc_1400371E5
0x1400371e2  mov     rcx, [rcx]; psz
0x1400371e5  call    cs:__imp_SysAllocString
0x1400371eb  add     rdi, rdi
0x1400371ee  mov     [r15+rdi*8], rax
0x1400371f2  mov     rcx, [rbx]
0x1400371f5  add     rcx, 20h ; ' '
0x1400371f9  add     rcx, rsi
0x1400371fc  cmp     qword ptr [rcx+18h], 7
0x140037201  jbe     short loc_140037206
0x140037203  mov     rcx, [rcx]; psz
0x140037206  call    cs:__imp_SysAllocString
0x14003720c  mov     [r15+rdi*8+8], rax
0x140037211  cmp     qword ptr [r15+rdi*8], 0
0x140037216  jz      loc_1400372A8
0x14003721c  test    rax, rax
0x14003721f  jz      loc_1400372A8
0x140037225  inc     r14d
0x140037228  mov     rdx, [rbx]
0x14003722b  mov     rcx, [rbx+8]
0x14003722f  sub     rcx, rdx
0x140037232  sar     rcx, 6
0x140037236  mov     eax, r14d
0x140037239  cmp     rax, rcx
0x14003723c  jb      short loc_1400371CD
0x14003723e  mov     rcx, [rbp+psa]; psa
0x140037242  call    cs:__imp_SafeArrayUnaccessData
0x140037248  mov     rax, [rbp+psa]
0x14003724c  xorps   xmm0, xmm0
0x14003724f  movdqu  xmmword ptr [rbp+psa], xmm0
0x140037254  mov     [rbp+var_8], 0
0x14003725b  xor     dl, dl
0x14003725d  mov     [rbp+var_20], dl
0x140037260  mov     [r12], rax
0x140037264  mov     rcx, [rbp+arg_0]
0x140037268  test    rcx, rcx
0x14003726b  jz      short loc_14003727C
0x14003726d  mov     rax, [rcx]
0x140037270  mov     rax, [rax+10h]
0x140037274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037279  mov     dl, [rbp+var_20]
0x14003727c  mov     rcx, [rbp+psa]; psa
0x140037280  test    rcx, rcx
0x140037283  jz      short loc_140037299
0x140037285  test    dl, dl
0x140037287  jz      short loc_140037293
0x140037289  call    cs:__imp_SafeArrayUnaccessData
0x14003728f  mov     rcx, [rbp+psa]; psa
0x140037293  call    cs:__imp_SafeArrayDestroy
0x140037299  mov     rax, 8000000000h
0x1400372a3  jmp     loc_140037341
0x1400372a8  mov     edx, 5Ch ; '\'; Ch
0x1400372ad  lea     rcx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x1400372b4  call    cs:__imp_strrchr
0x1400372ba  test    rax, rax
0x1400372bd  jz      short loc_1400372C4
0x1400372bf  inc     rax
0x1400372c2  jmp     short loc_1400372CB
0x1400372c4  lea     rax, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x1400372cb  mov     rdx, rax; char *
0x1400372ce  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400372d5  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400372da  mov     rbx, rax
0x1400372dd  shl     rbx, 34h
0x1400372e1  mov     rax, 0F3230000000Eh
0x1400372eb  or      rbx, rax
0x1400372ee  mov     rcx, [rbp+arg_0]
0x1400372f2  test    rcx, rcx
0x1400372f5  jz      short loc_140037304
0x1400372f7  mov     rdx, [rcx]
0x1400372fa  mov     rax, [rdx+10h]
0x1400372fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037303  nop
0x140037304  jmp     loc_140037162
0x140037309  mov     rcx, [rbp+arg_0]
0x14003730d  test    rcx, rcx
0x140037310  jz      short loc_14003731F
0x140037312  mov     rax, [rcx]
0x140037315  mov     rax, [rax+10h]
0x140037319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003731e  nop
0x14003731f  mov     rcx, [rbp+psa]; psa
0x140037323  test    rcx, rcx
0x140037326  jz      short loc_14003733E
0x140037328  cmp     [rbp+var_20], 0
0x14003732c  jz      short loc_140037338
0x14003732e  call    cs:__imp_SafeArrayUnaccessData
0x140037334  mov     rcx, [rbp+psa]; psa
0x140037338  call    cs:__imp_SafeArrayDestroy
0x14003733e  mov     rax, rdi
0x140037341  lea     r11, [rsp+50h+var_s0]
0x140037346  mov     rbx, [r11+38h]
0x14003734a  mov     rsi, [r11+40h]
0x14003734e  mov     rsp, r11
0x140037351  pop     r15
0x140037353  pop     r14
0x140037355  pop     r12
0x140037357  pop     rdi
0x140037358  pop     rbp
0x140037359  retn
```
