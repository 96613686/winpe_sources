# Windows::Compat::Ids::IdsTlsModel::Notify(Windows::Compat::Ids::IdsEventData *)

- ea: `0x1800c1f20`
- end: `0x1800c23cf`
- name: `?Notify@IdsTlsModel@Ids@Compat@Windows@@UEAAKPEAVIdsEventData@234@@Z`
- size: `1199`
- prototype: `__int64 __fastcall(Windows::Compat::Ids::IdsTlsModel *this, __m128i *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008e14`
- `0x18000c73c`
- `0x180012920`
- `0x18009a410`
- `0x1800ab010`
- `0x1800b32f0`
- `0x1800ba918`
- `0x1800bb510`
- `0x1800c1908`
- `0x1800c1960`
- `0x1800c1f20`
- `0x1800c37f8`
- `0x1800c3834`
- `0x1800c38a0`
- `0x1800c38d0`
- `0x1800c392c`
- `0x1800c39c0`
- `0x1800dba94`
- `0x1800dbd4c`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800c2270`
- `msvcrt!wcsrchr` at `0x1800c2270`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c212a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c213e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c217d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c21bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c212a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c213e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c217d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c21bf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800c2290`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800c2290`

## string_xrefs

- `0x1800c1ff4`: `Process id [%d] path [%ws]`
- `0x1800c1f49`: `Windows::Compat::Ids::IdsTlsModel::Notify`
- `0x1800c1fe2`: `Windows::Compat::Ids::IdsTlsModel::Notify`
- `0x1800c1fff`: `Windows::Compat::Ids::IdsTlsModel::Notify`
- `0x1800c205f`: `Windows::Compat::Ids::IdsTlsModel::Notify`
- `0x1800c20be`: `Windows::Compat::Ids::IdsTlsModel::Notify`
- `0x1800c2113`: `Windows::Compat::Ids::IdsTlsModel::Notify`
- `0x1800c2154`: `Windows::Compat::Ids::IdsTlsModel::Notify`
- `0x1800c21f7`: `Windows::Compat::Ids::IdsTlsModel::Notify`
- `0x1800c2228`: `Windows::Compat::Ids::IdsTlsModel::Notify`
- `0x1800c22ba`: `Windows::Compat::Ids::IdsTlsModel::Notify`
- `0x1800c2310`: `Windows::Compat::Ids::IdsTlsModel::Notify`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Ids::IdsTlsModel::Notify(Windows::Compat::Ids::IdsTlsModel *this, __m128i *a2)
{
  _QWORD *v4; // rax
  char *v5; // rsi
  __int64 i; // rax
  const unsigned __int16 *v7; // r14
  unsigned int v8; // r12d
  unsigned int v9; // edx
  __int64 *v10; // rbx
  __int64 *v11; // rdi
  __int64 v12; // r13
  const unsigned __int16 *v13; // r8
  unsigned int v14; // eax
  Windows::Compat::Ids::IdsMatchingFile **v15; // rbx
  Windows::Compat::Ids::IdsMatchingFile **v16; // rdi
  int v17; // ebx
  int v18; // eax
  wchar_t *v19; // rbx
  struct Windows::Compat::Ids::IdsProc *v20; // rdx
  Windows::Compat::Ids::IdsActionMgr *v21; // rcx
  const unsigned __int16 ***v22; // rdi
  const unsigned __int16 ***v23; // rbx
  __m128i *v24; // r13
  __int64 v25; // r14
  const unsigned __int16 **v26; // r15
  unsigned __int16 *v28; // [rsp+20h] [rbp-30h]
  unsigned __int16 *v29; // [rsp+20h] [rbp-30h]
  unsigned __int16 *v30; // [rsp+20h] [rbp-30h]
  unsigned __int16 *v31; // [rsp+20h] [rbp-30h]
  __int64 v32; // [rsp+28h] [rbp-28h]
  _BYTE v33[16]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v34; // [rsp+90h] [rbp+40h] BYREF
  __m128i *v35; // [rsp+98h] [rbp+48h]

  v35 = a2;
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsTlsModel::Notify",
    567,
    (unsigned int)"TlsModel:Analyzing event ");
  v34 = 0;
  v4 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::ensure_data(&v34);
  tip2::details::shared_data<1,0,0>::start(*v4 + 8LL, v33);
  v5 = (char *)this + 128;
  wil::com_ptr_t<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>,wil::err_returncode_policy>::operator=(
    (char *)this + 128,
    &v34);
  wil::com_ptr_t<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>,wil::err_returncode_policy>(&v34);
  for ( i = *((_QWORD *)this + 6); ; i += 8 )
  {
    if ( i == *((_QWORD *)this + 7) )
    {
      tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::data(
        (char *)this + 128,
        &v34);
      *(_DWORD *)(v34 + 272) = 0;
      goto LABEL_46;
    }
    if ( **(_QWORD **)i == a2->m128i_i64[0] && *(_QWORD *)(*(_QWORD *)i + 8LL) == _mm_srli_si128(*a2, 8).m128i_u64[0] )
      break;
  }
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsTlsModel::Notify",
    592,
    (unsigned int)"Checking conditions");
  v7 = (const unsigned __int16 *)a2[2].m128i_i64[0];
  v8 = a2[1].m128i_u32[2];
  HIDWORD(v32) = HIDWORD(v7);
  LODWORD(v28) = v8;
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsTlsModel::Notify",
    597,
    (unsigned int)"Process id [%d] path [%ws]");
  v10 = (__int64 *)*((_QWORD *)this + 6);
  v11 = (__int64 *)*((_QWORD *)this + 7);
  while ( 1 )
  {
    if ( v10 == v11 )
    {
      v15 = (Windows::Compat::Ids::IdsMatchingFile **)*((_QWORD *)this + 12);
      v16 = (Windows::Compat::Ids::IdsMatchingFile **)*((_QWORD *)this + 13);
      while ( v15 != v16 )
      {
        if ( !Windows::Compat::Ids::IdsMatchingFile::Match(*v15, v7) )
        {
          AslLogCallPrintf(
            3,
            (unsigned int)"Windows::Compat::Ids::IdsTlsModel::Notify",
            635,
            (unsigned int)"One of the matching files didn't match");
          goto LABEL_12;
        }
        ++v15;
      }
      LODWORD(v34) = 0;
      if ( !(unsigned int)PcaStoreGetValueEx(&v34, 4, 0, v7, 13) )
      {
        v17 = v34;
        LODWORD(v29) = v34;
        AslLogCallPrintf(
          3,
          (unsigned int)"Windows::Compat::Ids::IdsTlsModel::Notify",
          655,
          (unsigned int)"lasttickcount [%d]",
          v29);
        if ( v17 )
        {
          if ( v17 + 60000 > GetTickCount() )
          {
            LODWORD(v32) = GetTickCount();
            LODWORD(v30) = v17;
            AslLogCallPrintf(
              3,
              (unsigned int)"Windows::Compat::Ids::IdsTlsModel::Notify",
              661,
              (unsigned int)"Less than 60s passed since last check last [%d] current [%d] [%ws]",
              v30,
              v32,
              v7);
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IdsBugFix1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IdsBugFix1>::GetImpl'::`2'::impl) )
            {
              LODWORD(v34) = GetTickCount();
              PcaStoreSetValueEx(0, v7, 13, &v34, 4);
            }
            tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::data(
              (char *)this + 128,
              &v34);
            *(_DWORD *)(v34 + 272) = 2;
            goto LABEL_46;
          }
        }
      }
      LODWORD(v34) = GetTickCount();
      v18 = PcaStoreSetValueEx(0, v7, 13, &v34, 4);
      if ( v18 )
      {
        LODWORD(v31) = v18;
        AslLogCallPrintf(
          1,
          (unsigned int)"Windows::Compat::Ids::IdsTlsModel::Notify",
          691,
          (unsigned int)"Failed to set the last tickcount for IDS [%d]",
          v31);
      }
      if ( *((_BYTE *)this + 44) && !(unsigned int)PcauiIsProcessErrorWindow(v8) )
      {
        AslLogCallPrintf(
          3,
          (unsigned int)"Windows::Compat::Ids::IdsTlsModel::Notify",
          698,
          (unsigned int)"No error window in the foreground");
        tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::data(
          (char *)this + 128,
          &v34);
        *(_DWORD *)(v34 + 272) = 3;
        goto LABEL_46;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IdsTlsProcessName>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IdsTlsProcessName>::GetImpl'::`2'::impl)
        && v7 )
      {
        v19 = wcsrchr(v7, 0x5Cu);
        if ( !v19 )
          v19 = (wchar_t *)v7;
        if ( !lstrcmpiW(L"\\svchost.exe", v19) )
          return 0;
        IdsLogInfo("[%ws] process", v19);
      }
      AslLogCallPrintf(
        3,
        (unsigned int)"Windows::Compat::Ids::IdsTlsModel::Notify",
        733,
        (unsigned int)"All conditions met");
      v22 = (const unsigned __int16 ***)*((_QWORD *)this + 10);
      v23 = (const unsigned __int16 ***)*((_QWORD *)this + 9);
      v24 = v35;
      v25 = v22 - v23;
      while ( v23 != v22 )
      {
        v26 = *v23;
        if ( (unsigned int)Windows::Compat::Ids::IdsActionMgr::Action(
                             v21,
                             v20,
                             (const unsigned __int16 *)v24[2].m128i_i64[0],
                             **v23,
                             (wchar_t *)(*v23)[1]) )
          AslLogCallPrintf(
            1,
            (unsigned int)"Windows::Compat::Ids::IdsTlsModel::Notify",
            747,
            (unsigned int)"Failed to apply action [%ws] [%ws]",
            *v26,
            v26[1]);
        else
          --v25;
        ++v23;
      }
      tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::data(
        v5,
        &v34);
      if ( v25 )
        *(_DWORD *)(v34 + 272) = 4;
      else
        *(_DWORD *)(v34 + 272) = 5;
      tip2::test_data_control<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::close(&v34);
      tip2::test_data_control<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::~test_data_control<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>(&v34);
      tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::complete(v5);
      return 0;
    }
    v12 = *v10;
    v13 = *(const unsigned __int16 **)(*v10 + 24);
    if ( v13 )
    {
      v14 = Windows::Compat::Ids::CountEtwEvent(
              (Windows::Compat::Ids *)v8,
              v9,
              v13,
              *(const unsigned __int16 **)(v12 + 32),
              v28);
      if ( v14 < *(_DWORD *)(v12 + 16) )
        break;
    }
    ++v10;
  }
  LODWORD(v28) = v14;
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsTlsModel::Notify",
    619,
    (unsigned int)"Count did not meet [%d]",
    v28);
LABEL_12:
  tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::data(
    (char *)this + 128,
    &v34);
  *(_DWORD *)(v34 + 272) = 1;
LABEL_46:
  tip2::test_data_control<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::close(&v34);
  tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::complete((char *)this + 128);
  tip2::test_data_control<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::~test_data_control<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>(&v34);
  return 0;
}

```

## disassembly

```asm
0x1800c1f20  mov     [rsp-38h+arg_10], rbx
0x1800c1f25  mov     [rsp-38h+arg_8], rdx
0x1800c1f2a  push    rbp
0x1800c1f2b  push    rsi
0x1800c1f2c  push    rdi
0x1800c1f2d  push    r12
0x1800c1f2f  push    r13
0x1800c1f31  push    r14
0x1800c1f33  push    r15
0x1800c1f35  mov     rbp, rsp
0x1800c1f38  sub     rsp, 50h
0x1800c1f3c  mov     r13, rdx
0x1800c1f3f  lea     r9, aTlsmodelAnalyz; "TlsModel:Analyzing event "
0x1800c1f46  mov     r15, rcx
0x1800c1f49  lea     rdx, aWindowsCompatI_78; "Windows::Compat::Ids::IdsTlsModel::Noti"...
0x1800c1f50  mov     ebx, 3
0x1800c1f55  mov     r8d, 237h
0x1800c1f5b  mov     ecx, ebx
0x1800c1f5d  call    AslLogCallPrintf
0x1800c1f62  lea     rcx, [rbp+arg_0]
0x1800c1f66  mov     [rbp+arg_0], 0
0x1800c1f6e  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::ensure_data(void)
0x1800c1f73  lea     rdx, [rbp+var_10]
0x1800c1f77  mov     rcx, [rax]
0x1800c1f7a  add     rcx, 8
0x1800c1f7e  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x1800c1f83  lea     rsi, [r15+80h]
0x1800c1f8a  mov     rcx, rsi
0x1800c1f8d  lea     rdx, [rbp+arg_0]
0x1800c1f91  call    ??4?$com_ptr_t@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>,wil::err_returncode_policy> &&)
0x1800c1f96  lea     rcx, [rbp+arg_0]
0x1800c1f9a  call    ??1?$com_ptr_t@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>,wil::err_returncode_policy>(void)
0x1800c1f9f  mov     rax, [r15+30h]
0x1800c1fa3  cmp     rax, [r15+38h]
0x1800c1fa7  jz      loc_1800C2381
0x1800c1fad  movups  xmm0, xmmword ptr [r13+0]
0x1800c1fb2  mov     rdx, [rax]
0x1800c1fb5  movq    rcx, xmm0
0x1800c1fba  cmp     [rdx], rcx
0x1800c1fbd  jnz     short loc_1800C1FCF
0x1800c1fbf  psrldq  xmm0, 8
0x1800c1fc4  movq    rcx, xmm0
0x1800c1fc9  cmp     [rdx+8], rcx
0x1800c1fcd  jz      short loc_1800C1FD5
0x1800c1fcf  add     rax, 8
0x1800c1fd3  jmp     short loc_1800C1FA3
0x1800c1fd5  lea     r9, aCheckingCondit; "Checking conditions"
0x1800c1fdc  mov     r8d, 250h
0x1800c1fe2  lea     rdx, aWindowsCompatI_78; "Windows::Compat::Ids::IdsTlsModel::Noti"...
0x1800c1fe9  mov     ecx, ebx
0x1800c1feb  call    AslLogCallPrintf
0x1800c1ff0  mov     r14, [r13+20h]
0x1800c1ff4  lea     r9, aProcessIdDPath; "Process id [%d] path [%ws]"
0x1800c1ffb  mov     r12d, [r13+18h]
0x1800c1fff  lea     rdx, aWindowsCompatI_78; "Windows::Compat::Ids::IdsTlsModel::Noti"...
0x1800c2006  mov     [rsp+50h+var_28], r14
0x1800c200b  mov     r8d, 255h
0x1800c2011  mov     ecx, ebx
0x1800c2013  mov     dword ptr [rsp+50h+var_30], r12d; unsigned __int16 *
0x1800c2018  call    AslLogCallPrintf
0x1800c201d  mov     rbx, [r15+30h]
0x1800c2021  mov     rdi, [r15+38h]
0x1800c2025  cmp     rbx, rdi
0x1800c2028  jz      short loc_1800C208F
0x1800c202a  mov     r13, [rbx]
0x1800c202d  mov     r8, [r13+18h]; unsigned __int16 *
0x1800c2031  test    r8, r8
0x1800c2034  jz      short loc_1800C2048
0x1800c2036  mov     r9, [r13+20h]; unsigned __int16 *
0x1800c203a  mov     ecx, r12d; this
0x1800c203d  call    ?CountEtwEvent@Ids@Compat@Windows@@YAKKPEBG00@Z; Windows::Compat::Ids::CountEtwEvent(ulong,ushort const *,ushort const *,ushort const *)
0x1800c2042  cmp     eax, [r13+10h]
0x1800c2046  jb      short loc_1800C204E
0x1800c2048  add     rbx, 8
0x1800c204c  jmp     short loc_1800C2025
0x1800c204e  lea     r9, aCountDidNotMee; "Count did not meet [%d]"
0x1800c2055  mov     dword ptr [rsp+50h+var_30], eax
0x1800c2059  mov     r8d, 26Bh
0x1800c205f  lea     rdx, aWindowsCompatI_78; "Windows::Compat::Ids::IdsTlsModel::Noti"...
0x1800c2066  mov     ecx, 3
0x1800c206b  call    AslLogCallPrintf
0x1800c2070  lea     rdx, [rbp+arg_0]
0x1800c2074  mov     rcx, rsi
0x1800c2077  call    ?data@?$tip_test@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::data(void)
0x1800c207c  mov     rax, [rbp+arg_0]
0x1800c2080  mov     dword ptr [rax+110h], 1
0x1800c208a  jmp     loc_1800C239B
0x1800c208f  mov     rbx, [r15+60h]
0x1800c2093  mov     rdi, [r15+68h]
0x1800c2097  cmp     rbx, rdi
0x1800c209a  jz      short loc_1800C20D1
0x1800c209c  mov     rcx, [rbx]; this
0x1800c209f  mov     rdx, r14; unsigned __int16 *
0x1800c20a2  call    ?Match@IdsMatchingFile@Ids@Compat@Windows@@QEAAHPEBG@Z; Windows::Compat::Ids::IdsMatchingFile::Match(ushort const *)
0x1800c20a7  test    eax, eax
0x1800c20a9  jz      short loc_1800C20B1
0x1800c20ab  add     rbx, 8
0x1800c20af  jmp     short loc_1800C2097
0x1800c20b1  lea     r9, aOneOfTheMatchi; "One of the matching files didn't match"
0x1800c20b8  mov     r8d, 27Bh
0x1800c20be  lea     rdx, aWindowsCompatI_78; "Windows::Compat::Ids::IdsTlsModel::Noti"...
0x1800c20c5  mov     ecx, 3
0x1800c20ca  call    AslLogCallPrintf
0x1800c20cf  jmp     short loc_1800C2070
0x1800c20d1  mov     edi, 0Dh
0x1800c20d6  mov     dword ptr [rbp+arg_0], 0
0x1800c20dd  mov     r9, r14
0x1800c20e0  mov     dword ptr [rsp+50h+var_30], edi
0x1800c20e4  xor     r8d, r8d
0x1800c20e7  lea     rcx, [rbp+arg_0]
0x1800c20eb  lea     edx, [rdi-9]
0x1800c20ee  call    ?PcaStoreGetValueEx@@YAKPEAX_KPEBG2W4_PCA_SLOT_ID@@@Z; PcaStoreGetValueEx(void *,unsigned __int64,ushort const *,ushort const *,_PCA_SLOT_ID)
0x1800c20f3  lea     r13d, [rdi-0Ah]
0x1800c20f7  test    eax, eax
0x1800c20f9  jnz     loc_1800C21BF
0x1800c20ff  mov     ebx, dword ptr [rbp+arg_0]
0x1800c2102  lea     r9, aLasttickcountD; "lasttickcount [%d]"
0x1800c2109  mov     r8d, 28Fh
0x1800c210f  mov     dword ptr [rsp+50h+var_30], ebx
0x1800c2113  lea     rdx, aWindowsCompatI_78; "Windows::Compat::Ids::IdsTlsModel::Noti"...
0x1800c211a  mov     ecx, r13d
0x1800c211d  call    AslLogCallPrintf
0x1800c2122  test    ebx, ebx
0x1800c2124  jz      loc_1800C21BF
0x1800c212a  call    cs:__imp_GetTickCount
0x1800c2130  lea     ecx, [rbx+0EA60h]
0x1800c2136  cmp     ecx, eax
0x1800c2138  jbe     loc_1800C21BF
0x1800c213e  call    cs:__imp_GetTickCount
0x1800c2144  mov     [rsp+50h+var_20], r14
0x1800c2149  lea     r9, aLessThan60sPas; "Less than 60s passed since last check l"...
0x1800c2150  mov     dword ptr [rsp+50h+var_28], eax
0x1800c2154  lea     rdx, aWindowsCompatI_78; "Windows::Compat::Ids::IdsTlsModel::Noti"...
0x1800c215b  mov     r8d, 295h
0x1800c2161  mov     dword ptr [rsp+50h+var_30], ebx
0x1800c2165  mov     ecx, r13d
0x1800c2168  call    AslLogCallPrintf
0x1800c216d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IdsBugFix1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IdsBugFix1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IdsBugFix1> `wil::Feature<__WilFeatureTraits_Feature_IdsBugFix1>::GetImpl(void)'::`2'::impl
0x1800c2174  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IdsBugFix1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IdsBugFix1>::__private_IsEnabled(void)
0x1800c2179  test    al, al
0x1800c217b  jz      short loc_1800C21A0
0x1800c217d  call    cs:__imp_GetTickCount
0x1800c2183  lea     r9, [rbp+arg_0]
0x1800c2187  mov     [rsp+50h+var_30], 4
0x1800c2190  mov     r8d, edi
0x1800c2193  mov     dword ptr [rbp+arg_0], eax
0x1800c2196  mov     rdx, r14
0x1800c2199  xor     ecx, ecx
0x1800c219b  call    ?PcaStoreSetValueEx@@YAKPEBG0W4_PCA_SLOT_ID@@PEAX_K@Z; PcaStoreSetValueEx(ushort const *,ushort const *,_PCA_SLOT_ID,void *,unsigned __int64)
0x1800c21a0  lea     rdx, [rbp+arg_0]
0x1800c21a4  mov     rcx, rsi
0x1800c21a7  call    ?data@?$tip_test@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::data(void)
0x1800c21ac  mov     rax, [rbp+arg_0]
0x1800c21b0  mov     dword ptr [rax+110h], 2
0x1800c21ba  jmp     loc_1800C239B
0x1800c21bf  call    cs:__imp_GetTickCount
0x1800c21c5  lea     r9, [rbp+arg_0]
0x1800c21c9  mov     [rsp+50h+var_30], 4
0x1800c21d2  mov     r8d, edi
0x1800c21d5  mov     dword ptr [rbp+arg_0], eax
0x1800c21d8  mov     rdx, r14
0x1800c21db  xor     ecx, ecx
0x1800c21dd  call    ?PcaStoreSetValueEx@@YAKPEBG0W4_PCA_SLOT_ID@@PEAX_K@Z; PcaStoreSetValueEx(ushort const *,ushort const *,_PCA_SLOT_ID,void *,unsigned __int64)
0x1800c21e2  test    eax, eax
0x1800c21e4  jz      short loc_1800C2208
0x1800c21e6  lea     r9, aFailedToSetThe_0; "Failed to set the last tickcount for ID"...
0x1800c21ed  mov     dword ptr [rsp+50h+var_30], eax
0x1800c21f1  mov     r8d, 2B3h
0x1800c21f7  lea     rdx, aWindowsCompatI_78; "Windows::Compat::Ids::IdsTlsModel::Noti"...
0x1800c21fe  mov     ecx, 1
0x1800c2203  call    AslLogCallPrintf
0x1800c2208  cmp     byte ptr [r15+2Ch], 0
0x1800c220d  jz      short loc_1800C2253
0x1800c220f  mov     ecx, r12d; unsigned int
0x1800c2212  call    ?PcauiIsProcessErrorWindow@@YAHK@Z; PcauiIsProcessErrorWindow(ulong)
0x1800c2217  test    eax, eax
0x1800c2219  jnz     short loc_1800C2253
0x1800c221b  lea     r9, aNoErrorWindowI; "No error window in the foreground"
0x1800c2222  mov     r8d, 2BAh
0x1800c2228  lea     rdx, aWindowsCompatI_78; "Windows::Compat::Ids::IdsTlsModel::Noti"...
0x1800c222f  mov     ecx, r13d
0x1800c2232  call    AslLogCallPrintf
0x1800c2237  lea     rdx, [rbp+arg_0]
0x1800c223b  mov     rcx, rsi
0x1800c223e  call    ?data@?$tip_test@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::data(void)
0x1800c2243  mov     rax, [rbp+arg_0]
0x1800c2247  mov     [rax+110h], r13d
0x1800c224e  jmp     loc_1800C239B
0x1800c2253  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IdsTlsProcessName@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IdsTlsProcessName@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IdsTlsProcessName> `wil::Feature<__WilFeatureTraits_Feature_IdsTlsProcessName>::GetImpl(void)'::`2'::impl
0x1800c225a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IdsTlsProcessName@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IdsTlsProcessName>::__private_IsEnabled(void)
0x1800c225f  test    al, al
0x1800c2261  jz      short loc_1800C22AD
0x1800c2263  test    r14, r14
0x1800c2266  jz      short loc_1800C22AD
0x1800c2268  mov     edx, 5Ch ; '\'; Ch
0x1800c226d  mov     rcx, r14; Str
0x1800c2270  call    cs:__imp_wcsrchr
0x1800c2276  mov     rbx, rax
0x1800c2279  test    rax, rax
0x1800c227c  jnz     short loc_1800C2286
0x1800c227e  test    r14, r14
0x1800c2281  jz      short loc_1800C22AD
0x1800c2283  mov     rbx, r14
0x1800c2286  mov     rdx, rbx; lpString2
0x1800c2289  lea     rcx, aSvchostExe; "\\svchost.exe"
0x1800c2290  call    cs:__imp_lstrcmpiW
0x1800c2296  test    eax, eax
0x1800c2298  jz      loc_1800C23B5
0x1800c229e  mov     rdx, rbx
0x1800c22a1  lea     rcx, aWsProcess; "[%ws] process"
0x1800c22a8  call    ?IdsLogInfo@@YAXPEBDZZ; IdsLogInfo(char const *,...)
0x1800c22ad  lea     r9, aAllConditionsM; "All conditions met"
0x1800c22b4  mov     r8d, 2DDh
0x1800c22ba  lea     rdx, aWindowsCompatI_78; "Windows::Compat::Ids::IdsTlsModel::Noti"...
0x1800c22c1  mov     ecx, r13d
0x1800c22c4  call    AslLogCallPrintf
0x1800c22c9  mov     rdi, [r15+50h]
0x1800c22cd  mov     rbx, [r15+48h]
0x1800c22d1  mov     r14, rdi
0x1800c22d4  mov     r13, [rbp+arg_8]
0x1800c22d8  sub     r14, rbx
0x1800c22db  sar     r14, 3
0x1800c22df  cmp     rbx, rdi
0x1800c22e2  jz      short loc_1800C233A
0x1800c22e4  mov     r15, [rbx]
0x1800c22e7  mov     r8, [r13+20h]; unsigned __int16 *
0x1800c22eb  mov     rax, [r15+8]
0x1800c22ef  mov     r9, [r15]; unsigned __int16 *
0x1800c22f2  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x1800c22f7  call    ?Action@IdsActionMgr@Ids@Compat@Windows@@QEAAKPEAVIdsProc@234@PEBG11@Z; Windows::Compat::Ids::IdsActionMgr::Action(Windows::Compat::Ids::IdsProc *,ushort const *,ushort const *,ushort const *)
0x1800c22fc  test    eax, eax
0x1800c22fe  jz      short loc_1800C2331
0x1800c2300  mov     rax, [r15+8]
0x1800c2304  lea     r9, aFailedToApplyA; "Failed to apply action [%ws] [%ws]"
0x1800c230b  mov     [rsp+50h+var_28], rax
0x1800c2310  lea     rdx, aWindowsCompatI_78; "Windows::Compat::Ids::IdsTlsModel::Noti"...
0x1800c2317  mov     rax, [r15]
0x1800c231a  mov     r8d, 2EBh
0x1800c2320  mov     ecx, 1
0x1800c2325  mov     [rsp+50h+var_30], rax
0x1800c232a  call    AslLogCallPrintf
0x1800c232f  jmp     short loc_1800C2334
0x1800c2331  dec     r14
0x1800c2334  add     rbx, 8
0x1800c2338  jmp     short loc_1800C22DF
0x1800c233a  lea     rdx, [rbp+arg_0]
0x1800c233e  mov     rcx, rsi
0x1800c2341  call    ?data@?$tip_test@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::data(void)
0x1800c2346  mov     rax, [rbp+arg_0]
0x1800c234a  lea     rcx, [rbp+arg_0]
0x1800c234e  test    r14, r14
0x1800c2351  jnz     short loc_1800C235F
0x1800c2353  mov     dword ptr [rax+110h], 5
0x1800c235d  jmp     short loc_1800C2369
0x1800c235f  mov     dword ptr [rax+110h], 4
0x1800c2369  call    ?close@?$test_data_control@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::close(void)
0x1800c236e  lea     rcx, [rbp+arg_0]
0x1800c2372  call    ??1?$test_data_control@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::~test_data_control<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>(void)
0x1800c2377  mov     rcx, rsi
0x1800c237a  call    ?complete@?$tip_test@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::complete(void)
0x1800c237f  jmp     short loc_1800C23B5
0x1800c2381  lea     rdx, [rbp+arg_0]
0x1800c2385  mov     rcx, rsi
0x1800c2388  call    ?data@?$tip_test@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::data(void)
0x1800c238d  mov     rax, [rbp+arg_0]
0x1800c2391  mov     dword ptr [rax+110h], 0
0x1800c239b  lea     rcx, [rbp+arg_0]
0x1800c239f  call    ?close@?$test_data_control@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::close(void)
0x1800c23a4  mov     rcx, rsi
0x1800c23a7  call    ?complete@?$tip_test@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::complete(void)
0x1800c23ac  lea     rcx, [rbp+arg_0]
0x1800c23b0  call    ??1?$test_data_control@V?$merged_data@U_tip_IdsTLSModelNotifySuccess@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>::~test_data_control<tip2::details::merged_data<_tip_IdsTLSModelNotifySuccess,_tip_IdsTLSModelNotifySuccess>>(void)
0x1800c23b5  mov     rbx, [rsp+50h+arg_10]
0x1800c23bd  xor     eax, eax
0x1800c23bf  add     rsp, 50h
0x1800c23c3  pop     r15
0x1800c23c5  pop     r14
0x1800c23c7  pop     r13
0x1800c23c9  pop     r12
0x1800c23cb  pop     rdi
0x1800c23cc  pop     rsi
0x1800c23cd  pop     rbp
0x1800c23ce  retn
```
