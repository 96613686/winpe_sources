# NTUserCapabilityHandler::AccessChanged(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x1800103c0`
- end: `0x18001078a`
- name: `?AccessChanged@NTUserCapabilityHandler@@UEAAJPEBG0000K@Z`
- size: `970`
- prototype: `__int64 __fastcall(NTUserCapabilityHandler *this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *, char *)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004c70`
- `0x180005270`
- `0x1800056e0`
- `0x18000f9f0`
- `0x18000fd3c`
- `0x18000fe60`
- `0x18001008c`
- `0x1800101bc`
- `0x1800102b8`
- `0x1800103c0`
- `0x18001096c`
- `0x180010a5c`
- `0x180010be0`
- `0x180010c20`
- `0x180010d10`
- `0x180010d60`
- `0x180010dbc`
- `0x180011144`
- `0x180011360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010741`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800105be`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800105be`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001066e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001066e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001054e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001054e`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x18001043a`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x18001043a`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x18001058e`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x18001058e`

## pseudocode

```c
__int64 __fastcall NTUserCapabilityHandler::AccessChanged(
        NTUserCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        char *a6)
{
  int v8; // esi
  DWORD v9; // ebx
  char *v10; // rdi
  unsigned __int64 v11; // rbx
  DWORD *v12; // rax
  size_t v13; // rbx
  DWORD v14; // edi
  int v15; // r15d
  __int64 **v16; // rax
  DWORD v17; // esi
  unsigned __int16 *v18; // r15
  DWORD v19; // r14d
  unsigned __int16 *v20; // rbx
  NTUserCapabilityHandler *v21; // rcx
  const unsigned __int16 *v22; // r9
  WCHAR *v23; // rax
  int v24; // edx
  bool HasAccess; // al
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // xmm1_8
  __int64 **v30; // rdi
  __int64 **i; // rbx
  signed int LastError; // eax
  unsigned int v33; // ebx
  DWORD cbNeeded; // [rsp+20h] [rbp-E0h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v36; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+38h] [rbp-C8h] BYREF
  int v38; // [rsp+3Ch] [rbp-C4h]
  DWORD *lpidProcess; // [rsp+40h] [rbp-C0h] BYREF
  void *v40; // [rsp+48h] [rbp-B8h]
  __int64 v41; // [rsp+50h] [rbp-B0h]
  _BYTE v42[24]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  __int64 **v44; // [rsp+78h] [rbp-88h]
  __int64 v45; // [rsp+80h] [rbp-80h]
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  __int128 v47; // [rsp+90h] [rbp-70h]
  __int64 v48; // [rsp+A0h] [rbp-60h]
  __int64 v49; // [rsp+A8h] [rbp-58h]
  _BYTE v50[16]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+C0h] [rbp-40h] BYREF

  v36 = a4;
  if ( !NTUserCapabilityHandler::IsCapabilityRelevantToNTUser(this, a4) )
    return 0;
  gHandlingAccessChanged = 1;
  std::vector<unsigned long>::vector<unsigned long>(&lpidProcess);
  v8 = 0;
  while ( 1 )
  {
    cbNeeded = 0;
    v9 = ((_DWORD)v40 - (_DWORD)lpidProcess) & 0xFFFFFFFC;
    if ( !K32EnumProcesses(lpidProcess, v9, &cbNeeded) )
      break;
    if ( v9 != cbNeeded )
    {
      v14 = cbNeeded >> 2;
      goto LABEL_16;
    }
    v10 = (char *)v40;
    v11 = ((_BYTE *)v40 - (_BYTE *)lpidProcess) >> 2;
    if ( 2 * v11 < v11 )
    {
      v12 = &lpidProcess[2 * v11];
LABEL_12:
      v40 = v12;
      goto LABEL_13;
    }
    if ( 2 * v11 > v11 )
    {
      if ( 2 * v11 <= (v41 - (__int64)lpidProcess) >> 2 )
      {
        v13 = 4 * v11;
        memset_0(v40, 0, v13);
        v12 = (DWORD *)&v10[v13];
        goto LABEL_12;
      }
      std::vector<unsigned long>::_Resize_reallocate<std::_Value_init_tag>(&lpidProcess);
    }
LABEL_13:
    if ( (unsigned int)++v8 >= 5 )
    {
      v14 = 0;
LABEL_16:
      v38 = 0;
      v15 = 0;
      LODWORD(v43) = 0;
      v44 = 0;
      v45 = 0;
      v16 = (__int64 **)operator new(0x30u);
      *v16 = (__int64 *)v16;
      v16[1] = (__int64 *)v16;
      v44 = v16;
      v46 = 0;
      v47 = 0;
      v48 = 7;
      v49 = 8;
      LODWORD(v43) = 1065353216;
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>>>>>::_Assign_grow(
        &v46,
        16,
        v16);
      v17 = 0;
      if ( v14 )
      {
        v18 = v36;
        do
        {
          v19 = lpidProcess[v17];
          if ( v19 )
          {
            v20 = (unsigned __int16 *)OpenProcess(0x1208u, 0, v19);
            v36 = v20;
            if ( (unsigned __int64)v20 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              memset_0(packageFamilyName, 0, 0x82u);
              packageFamilyNameLength = 65;
              if ( !GetPackageFamilyName(v20, &packageFamilyNameLength, packageFamilyName) )
              {
                TokenHandle = 0;
                wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
                  &TokenHandle,
                  0);
                if ( OpenProcessToken(v20, 8u, &TokenHandle)
                  && NTUserCapabilityHandler::ShouldApplyNTuserCapabilitiesChecks(TokenHandle)
                  && (!a3 || NTUserCapabilityHandler::ProcessBelongsToUser(v21, TokenHandle, a3)) )
                {
                  if ( !a6 )
                    goto LABEL_30;
                  v23 = packageFamilyName;
                  do
                  {
                    v24 = *(WCHAR *)((char *)v23 + a6 - (char *)packageFamilyName);
                    v21 = (NTUserCapabilityHandler *)((unsigned int)*v23 - v24);
                    if ( (_DWORD)v21 )
                      break;
                    ++v23;
                  }
                  while ( v24 );
                  if ( !(_DWORD)v21 )
                  {
LABEL_30:
                    HasAccess = NTUserCapabilityHandler::HasAccess(v21, v19, a3, v22);
                    v36 = 0;
                    *(_QWORD *)v42 = v20;
                    *(_OWORD *)&v42[8] = 0;
                    SetNTUserCapabilityBitForString((struct tagPROCESS_WIN32_CAPABILITIES *)v42, v18, HasAccess);
                    cbNeeded = 0;
                    if ( ProcessIdToSessionId(v19, &cbNeeded) )
                    {
                      v26 = std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Try_emplace<unsigned long const &,>(
                              (float *)&v43,
                              (__int64)v50,
                              &cbNeeded);
                      v27 = *(_QWORD *)v26 + 24LL;
                      v28 = *(_QWORD *)(*(_QWORD *)v26 + 32LL);
                      if ( v28 == *(_QWORD *)(*(_QWORD *)v26 + 40LL) )
                      {
                        std::vector<tagPROCESS_WIN32_CAPABILITIES>::_Emplace_reallocate<tagPROCESS_WIN32_CAPABILITIES &>(
                          v27,
                          v28,
                          v42);
                      }
                      else
                      {
                        v29 = *(_QWORD *)&v42[16];
                        *(_OWORD *)v28 = *(_OWORD *)v42;
                        *(_QWORD *)(v28 + 16) = v29;
                        *(_QWORD *)(v27 + 8) += 24LL;
                      }
                    }
                  }
                }
                wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
              }
            }
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
          }
          ++v17;
        }
        while ( v17 < v14 );
        v15 = v38;
      }
      v30 = v44;
      for ( i = (__int64 **)*v44; i != v30; i = (__int64 **)*i )
      {
        v15 = CallSetProcessWin32Capabilities(
                (struct tagPROCESS_WIN32_CAPABILITIES *)i[3],
                -1431655765 * (unsigned int)(i[4] - i[3]));
        if ( v15 < 0 )
          break;
      }
      gHandlingAccessChanged = 0;
      std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::~_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>(&v43);
      std::vector<unsigned long>::_Tidy(&lpidProcess);
      return (unsigned int)v15;
    }
  }
  LastError = GetLastError();
  v33 = LastError;
  if ( LastError > 0 )
    v33 = (unsigned __int16)LastError | 0x80070000;
  std::vector<unsigned long>::_Tidy(&lpidProcess);
  return v33;
}

```

## disassembly

```asm
0x1800103c0  mov     [rsp-8+arg_0], rbx
0x1800103c5  mov     [rsp-8+arg_8], rsi
0x1800103ca  push    rbp
0x1800103cb  push    rdi
0x1800103cc  push    r13
0x1800103ce  push    r14
0x1800103d0  push    r15
0x1800103d2  lea     rbp, [rsp-60h]
0x1800103d7  sub     rsp, 160h
0x1800103de  mov     rax, cs:__security_cookie
0x1800103e5  xor     rax, rsp
0x1800103e8  mov     [rbp+80h+var_30], rax
0x1800103ec  mov     rdx, r9; unsigned __int16 *
0x1800103ef  mov     [rsp+180h+var_150], r9
0x1800103f4  mov     r13, r8
0x1800103f7  call    ?IsCapabilityRelevantToNTUser@NTUserCapabilityHandler@@AEBA_NPEBG@Z; NTUserCapabilityHandler::IsCapabilityRelevantToNTUser(ushort const *)
0x1800103fc  xor     r14d, r14d
0x1800103ff  test    al, al
0x180010401  jnz     short loc_18001040A
0x180010403  xor     eax, eax
0x180010405  jmp     loc_180010762
0x18001040a  lea     rcx, [rsp+180h+lpidProcess]
0x18001040f  mov     cs:?gHandlingAccessChanged@@3_NA, 1; bool gHandlingAccessChanged
0x180010416  call    ??0?$vector@KV?$allocator@K@std@@@std@@QEAA@_KAEBV?$allocator@K@1@@Z; std::vector<ulong>::vector<ulong>(unsigned __int64,std::allocator<ulong> const &)
0x18001041b  mov     esi, r14d
0x18001041e  mov     rbx, [rsp+180h+var_138]
0x180010423  lea     r8, [rsp+180h+cbNeeded]; lpcbNeeded
0x180010428  mov     rcx, [rsp+180h+lpidProcess]; lpidProcess
0x18001042d  sub     rbx, rcx
0x180010430  mov     [rsp+180h+cbNeeded], r14d
0x180010435  and     ebx, 0FFFFFFFCh
0x180010438  mov     edx, ebx; cb
0x18001043a  call    cs:__imp_K32EnumProcesses
0x180010440  test    eax, eax
0x180010442  jz      loc_180010741
0x180010448  mov     edi, [rsp+180h+cbNeeded]
0x18001044c  cmp     ebx, edi
0x18001044e  jnz     short loc_1800104BC
0x180010450  mov     rdi, [rsp+180h+var_138]
0x180010455  mov     rcx, [rsp+180h+lpidProcess]
0x18001045a  mov     rbx, rdi
0x18001045d  sub     rbx, rcx
0x180010460  sar     rbx, 2
0x180010464  lea     rdx, [rbx+rbx]
0x180010468  cmp     rdx, rbx
0x18001046b  jnb     short loc_180010473
0x18001046d  lea     rax, [rcx+rdx*4]
0x180010471  jmp     short loc_1800104A7
0x180010473  jbe     short loc_1800104AC
0x180010475  mov     rax, [rsp+180h+var_130]
0x18001047a  sub     rax, rcx
0x18001047d  sar     rax, 2
0x180010481  cmp     rdx, rax
0x180010484  jbe     short loc_180010492
0x180010486  lea     rcx, [rsp+180h+lpidProcess]
0x18001048b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@KV?$allocator@K@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ulong>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180010490  jmp     short loc_1800104AC
0x180010492  shl     rbx, 2
0x180010496  xor     edx, edx; Val
0x180010498  mov     r8, rbx; Size
0x18001049b  mov     rcx, rdi; void *
0x18001049e  call    memset_0
0x1800104a3  lea     rax, [rbx+rdi]
0x1800104a7  mov     [rsp+180h+var_138], rax
0x1800104ac  inc     esi
0x1800104ae  cmp     esi, 5
0x1800104b1  jb      loc_18001041E
0x1800104b7  mov     edi, r14d
0x1800104ba  jmp     short loc_1800104BF
0x1800104bc  shr     edi, 2
0x1800104bf  mov     ecx, 30h ; '0'; Size
0x1800104c4  mov     [rsp+180h+var_144], r14d
0x1800104c9  mov     r15d, r14d
0x1800104cc  mov     dword ptr [rsp+180h+var_110], r14d
0x1800104d1  mov     [rsp+180h+var_108], r14
0x1800104d6  mov     [rbp+80h+var_100], r14
0x1800104da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800104df  xorps   xmm0, xmm0
0x1800104e2  lea     rcx, [rbp+80h+var_F8]
0x1800104e6  mov     r8, rax
0x1800104e9  mov     edx, 10h
0x1800104ee  mov     [rax], rax
0x1800104f1  mov     [rax+8], rax
0x1800104f5  mov     [rsp+180h+var_108], rax
0x1800104fa  mov     [rbp+80h+var_F8], r14
0x1800104fe  movdqa  [rbp+80h+var_F0], xmm0
0x180010503  mov     [rbp+80h+var_E0], 7
0x18001050b  mov     [rbp+80h+var_D8], 8
0x180010513  mov     dword ptr [rsp+180h+var_110], 3F800000h
0x18001051b  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>>>)
0x180010520  mov     esi, r14d
0x180010523  test    edi, edi
0x180010525  jz      loc_1800106E6
0x18001052b  mov     r15, [rsp+180h+var_150]
0x180010530  mov     rax, [rsp+180h+lpidProcess]
0x180010535  mov     ecx, esi
0x180010537  mov     r14d, [rax+rcx*4]
0x18001053b  test    r14d, r14d
0x18001053e  jz      loc_1800106D4
0x180010544  mov     r8d, r14d; dwProcessId
0x180010547  xor     edx, edx; bInheritHandle
0x180010549  mov     ecx, 1208h; dwDesiredAccess
0x18001054e  call    cs:__imp_OpenProcess
0x180010554  mov     rbx, rax
0x180010557  mov     [rsp+180h+var_150], rax
0x18001055c  dec     rax
0x18001055f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010563  ja      loc_1800106CA
0x180010569  xor     edx, edx; Val
0x18001056b  lea     rcx, [rbp+80h+packageFamilyName]; void *
0x18001056f  mov     r8d, 82h; Size
0x180010575  call    memset_0
0x18001057a  lea     r8, [rbp+80h+packageFamilyName]; packageFamilyName
0x18001057e  mov     [rsp+180h+packageFamilyNameLength], 41h ; 'A'
0x180010586  lea     rdx, [rsp+180h+packageFamilyNameLength]; packageFamilyNameLength
0x18001058b  mov     rcx, rbx; hProcess
0x18001058e  call    cs:__imp_GetPackageFamilyName
0x180010594  test    eax, eax
0x180010596  jnz     loc_1800106CA
0x18001059c  xor     edx, edx
0x18001059e  mov     [rsp+180h+TokenHandle], 0
0x1800105a7  lea     rcx, [rsp+180h+TokenHandle]
0x1800105ac  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800105b1  lea     r8, [rsp+180h+TokenHandle]; TokenHandle
0x1800105b6  mov     edx, 8; DesiredAccess
0x1800105bb  mov     rcx, rbx; ProcessHandle
0x1800105be  call    cs:__imp_OpenProcessToken
0x1800105c4  test    eax, eax
0x1800105c6  jz      loc_1800106C0
0x1800105cc  mov     rcx, [rsp+180h+TokenHandle]; void *
0x1800105d1  call    ?ShouldApplyNTuserCapabilitiesChecks@NTUserCapabilityHandler@@CA_NPEAX@Z; NTUserCapabilityHandler::ShouldApplyNTuserCapabilitiesChecks(void *)
0x1800105d6  test    al, al
0x1800105d8  jz      loc_1800106C0
0x1800105de  test    r13, r13
0x1800105e1  jz      short loc_1800105F8
0x1800105e3  mov     rdx, [rsp+180h+TokenHandle]; void *
0x1800105e8  mov     r8, r13; unsigned __int16 *
0x1800105eb  call    ?ProcessBelongsToUser@NTUserCapabilityHandler@@AEBA_NPEAXPEBG@Z; NTUserCapabilityHandler::ProcessBelongsToUser(void *,ushort const *)
0x1800105f0  test    al, al
0x1800105f2  jz      loc_1800106C0
0x1800105f8  cmp     [rbp+80h+arg_28], 0
0x180010600  jz      short loc_18001062C
0x180010602  mov     r8, [rbp+80h+arg_28]
0x180010609  lea     rax, [rbp+80h+packageFamilyName]
0x18001060d  sub     r8, rax
0x180010610  movzx   ecx, word ptr [rax]
0x180010613  movzx   edx, word ptr [rax+r8]
0x180010618  sub     ecx, edx; this
0x18001061a  jnz     short loc_180010624
0x18001061c  add     rax, 2
0x180010620  test    edx, edx
0x180010622  jnz     short loc_180010610
0x180010624  test    ecx, ecx
0x180010626  jnz     loc_1800106C0
0x18001062c  mov     r8, r13; unsigned __int16 *
0x18001062f  mov     edx, r14d; unsigned int
0x180010632  call    ?HasAccess@NTUserCapabilityHandler@@AEBA_NKPEBG0@Z; NTUserCapabilityHandler::HasAccess(ulong,ushort const *,ushort const *)
0x180010637  xorps   xmm0, xmm0
0x18001063a  mov     [rsp+180h+var_150], 0
0x180010643  mov     r8b, al; bool
0x180010646  mov     qword ptr [rsp+180h+var_128], rbx
0x18001064b  mov     rdx, r15; unsigned __int16 *
0x18001064e  lea     rcx, [rsp+180h+var_128]; struct tagPROCESS_WIN32_CAPABILITIES *
0x180010653  movdqu  [rsp+180h+var_128+8], xmm0
0x180010659  call    ?SetNTUserCapabilityBitForString@@YAXPEAUtagPROCESS_WIN32_CAPABILITIES@@PEBG_N@Z; SetNTUserCapabilityBitForString(tagPROCESS_WIN32_CAPABILITIES *,ushort const *,bool)
0x18001065e  lea     rdx, [rsp+180h+cbNeeded]; pSessionId
0x180010663  mov     [rsp+180h+cbNeeded], 0
0x18001066b  mov     ecx, r14d; dwProcessId
0x18001066e  call    cs:__imp_ProcessIdToSessionId
0x180010674  test    eax, eax
0x180010676  jz      short loc_1800106C0
0x180010678  lea     r8, [rsp+180h+cbNeeded]
0x18001067d  lea     rdx, [rbp+80h+var_D0]
0x180010681  lea     rcx, [rsp+180h+var_110]
0x180010686  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x18001068b  mov     rcx, [rax]
0x18001068e  add     rcx, 18h
0x180010692  mov     rdx, [rcx+8]
0x180010696  cmp     rdx, [rcx+10h]
0x18001069a  jz      short loc_1800106B6
0x18001069c  movups  xmm0, [rsp+180h+var_128]
0x1800106a1  movsd   xmm1, [rsp+180h+var_118]
0x1800106a7  movups  xmmword ptr [rdx], xmm0
0x1800106aa  movsd   qword ptr [rdx+10h], xmm1
0x1800106af  add     qword ptr [rcx+8], 18h
0x1800106b4  jmp     short loc_1800106C0
0x1800106b6  lea     r8, [rsp+180h+var_128]
0x1800106bb  call    ??$_Emplace_reallocate@AEAUtagPROCESS_WIN32_CAPABILITIES@@@?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@AEAAPEAUtagPROCESS_WIN32_CAPABILITIES@@QEAU2@AEAU2@@Z; std::vector<tagPROCESS_WIN32_CAPABILITIES>::_Emplace_reallocate<tagPROCESS_WIN32_CAPABILITIES &>(tagPROCESS_WIN32_CAPABILITIES * const,tagPROCESS_WIN32_CAPABILITIES &)
0x1800106c0  lea     rcx, [rsp+180h+TokenHandle]
0x1800106c5  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800106ca  lea     rcx, [rsp+180h+var_150]
0x1800106cf  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800106d4  inc     esi
0x1800106d6  cmp     esi, edi
0x1800106d8  jb      loc_180010530
0x1800106de  mov     r15d, [rsp+180h+var_144]
0x1800106e3  xor     r14d, r14d
0x1800106e6  mov     rdi, [rsp+180h+var_108]
0x1800106eb  mov     rbx, [rdi]
0x1800106ee  cmp     rbx, rdi
0x1800106f1  jz      short loc_180010721
0x1800106f3  mov     rcx, [rbx+18h]; struct tagPROCESS_WIN32_CAPABILITIES *
0x1800106f7  mov     rax, 0AAAAAAAAAAAAAAABh
0x180010701  mov     rdx, [rbx+20h]
0x180010705  sub     rdx, rcx
0x180010708  sar     rdx, 3
0x18001070c  imul    rdx, rax; unsigned int
0x180010710  call    ?CallSetProcessWin32Capabilities@@YAJPEAUtagPROCESS_WIN32_CAPABILITIES@@K@Z; CallSetProcessWin32Capabilities(tagPROCESS_WIN32_CAPABILITIES *,ulong)
0x180010715  mov     r15d, eax
0x180010718  test    eax, eax
0x18001071a  js      short loc_180010721
0x18001071c  mov     rbx, [rbx]
0x18001071f  jmp     short loc_1800106EE
0x180010721  lea     rcx, [rsp+180h+var_110]
0x180010726  mov     cs:?gHandlingAccessChanged@@3_NA, r14b; bool gHandlingAccessChanged
0x18001072d  call    ??1?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::~_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>(void)
0x180010732  lea     rcx, [rsp+180h+lpidProcess]
0x180010737  call    ?_Tidy@?$vector@KV?$allocator@K@std@@@std@@AEAAXXZ; std::vector<ulong>::_Tidy(void)
0x18001073c  mov     eax, r15d
0x18001073f  jmp     short loc_180010762
0x180010741  call    cs:__imp_GetLastError
0x180010747  mov     ebx, eax
0x180010749  test    eax, eax
0x18001074b  jle     short loc_180010756
0x18001074d  movzx   ebx, ax
0x180010750  or      ebx, 80070000h
0x180010756  lea     rcx, [rsp+180h+lpidProcess]
0x18001075b  call    ?_Tidy@?$vector@KV?$allocator@K@std@@@std@@AEAAXXZ; std::vector<ulong>::_Tidy(void)
0x180010760  mov     eax, ebx
0x180010762  mov     rcx, [rbp+80h+var_30]
0x180010766  xor     rcx, rsp; StackCookie
0x180010769  call    __security_check_cookie
0x18001076e  lea     r11, [rsp+180h+var_20]
0x180010776  mov     rbx, [r11+30h]
0x18001077a  mov     rsi, [r11+38h]
0x18001077e  mov     rsp, r11
0x180010781  pop     r15
0x180010783  pop     r14
0x180010785  pop     r13
0x180010787  pop     rdi
0x180010788  pop     rbp
0x180010789  retn
```
