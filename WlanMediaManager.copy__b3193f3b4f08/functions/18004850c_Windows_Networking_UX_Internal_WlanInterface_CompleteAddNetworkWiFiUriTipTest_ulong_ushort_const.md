# Windows::Networking::UX::Internal::WlanInterface::_CompleteAddNetworkWiFiUriTipTest(ulong,ushort const *)

- ea: `0x18004850c`
- end: `0x1800486bf`
- name: `?_CompleteAddNetworkWiFiUriTipTest@WlanInterface@Internal@UX@Networking@Windows@@IEAAJKPEBG@Z`
- size: `435`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanInterface *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041c70`

## callees

- `0x18000a394`
- `0x18000de4c`
- `0x180010c6c`
- `0x18001d4d4`
- `0x180039314`
- `0x18003a000`
- `0x18003a108`
- `0x18003ad00`
- `0x18003ae0c`
- `0x18004850c`
- `0x18004dd08`
- `0x18004f768`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048662`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800485b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800485b5`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::_CompleteAddNetworkWiFiUriTipTest(
        HSTRING *this,
        int a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rsi
  PCWSTR StringRawBuffer; // rax
  __int128 v9; // xmm0
  LPVOID v10; // rax
  wil::details::in1diag3 *v11; // rcx
  __int128 v13; // [rsp+20h] [rbp-10h] BYREF
  __int64 v14; // [rsp+70h] [rbp+40h] BYREF
  __int64 v15; // [rsp+80h] [rbp+50h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  StringRawBuffer = WindowsGetStringRawBuffer(this[174], 0);
  do
    ++v6;
  while ( StringRawBuffer[v6] );
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(a3, v7, StringRawBuffer) )
  {
    v9 = *((_OWORD *)this + 86);
    v14 = 0;
    v13 = v9;
    v10 = CoTaskMemAlloc(0x128u);
    if ( !v10 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v11);
    v15 = tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>(
            v10,
            &v13);
    wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::operator=(
      &v14,
      &v15);
    wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>(&v15);
    if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v14 + 8) )
    {
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::operator->(
                               &v14,
                               &v15)
                + 280LL) = a2;
      tip2::test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(&v15);
      if ( !a2 )
      {
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::operator->(
                                 &v14,
                                 &v15)
                  + 276LL) = 3;
        tip2::test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(&v15);
      }
      tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::complete(&v14);
    }
    *((GUID *)this + 86) = GUID_NULL;
    WindowsDeleteString(this[174]);
    this[174] = 0;
    wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>(&v14);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18004850c  mov     [rsp-38h+arg_8], rbx
0x180048511  push    rbp
0x180048512  push    rsi
0x180048513  push    rdi
0x180048514  push    r12
0x180048516  push    r13
0x180048518  push    r14
0x18004851a  push    r15
0x18004851c  mov     rbp, rsp
0x18004851f  sub     rsp, 30h
0x180048523  mov     r14, r8
0x180048526  mov     r15d, edx
0x180048529  mov     rdi, rcx
0x18004852c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048533  lea     r13, WPP_GLOBAL_Control
0x18004853a  cmp     rcx, r13
0x18004853d  jz      short loc_18004855A
0x18004853f  test    byte ptr [rcx+1Ch], 8
0x180048543  jz      short loc_18004855A
0x180048545  mov     rcx, [rcx+10h]
0x180048549  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180048550  mov     edx, 8Bh
0x180048555  call    WPP_SF_
0x18004855a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004855e  mov     rsi, rbx
0x180048561  xor     r12d, r12d
0x180048564  inc     rsi
0x180048567  cmp     [r14+rsi*2], r12w
0x18004856c  jnz     short loc_180048564
0x18004856e  mov     rcx, [rdi+570h]; string
0x180048575  xor     edx, edx; length
0x180048577  call    cs:__imp_WindowsGetStringRawBuffer
0x18004857d  inc     rbx
0x180048580  cmp     [rax+rbx*2], r12w
0x180048585  jnz     short loc_18004857D
0x180048587  mov     r9, rbx
0x18004858a  mov     r8, rax
0x18004858d  mov     rdx, rsi
0x180048590  mov     rcx, r14
0x180048593  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180048598  test    al, al
0x18004859a  jz      loc_180048678
0x1800485a0  movups  xmm0, xmmword ptr [rdi+560h]
0x1800485a7  mov     ecx, 128h; cb
0x1800485ac  mov     [rbp+arg_0], r12
0x1800485b0  movdqu  [rbp+var_10], xmm0
0x1800485b5  call    cs:__imp_CoTaskMemAlloc
0x1800485bb  test    rax, rax
0x1800485be  jz      loc_1800486B9
0x1800485c4  lea     rdx, [rbp+var_10]
0x1800485c8  mov     rcx, rax
0x1800485cb  call    ??0?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>(_GUID *)
0x1800485d0  lea     rdx, [rbp+arg_10]
0x1800485d4  mov     [rbp+arg_10], rax
0x1800485d8  lea     rcx, [rbp+arg_0]
0x1800485dc  call    ??4?$com_ptr_t@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy> &&)
0x1800485e1  lea     rcx, [rbp+arg_10]
0x1800485e5  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>(void)
0x1800485ea  mov     rcx, [rbp+arg_0]
0x1800485ee  add     rcx, 8
0x1800485f2  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x1800485f7  test    al, al
0x1800485f9  jz      short loc_18004864C
0x1800485fb  lea     rdx, [rbp+arg_10]
0x1800485ff  lea     rcx, [rbp+arg_0]
0x180048603  call    ??C?$tip_test@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::operator->(void)
0x180048608  mov     rcx, [rax]
0x18004860b  mov     [rcx+118h], r15d
0x180048612  lea     rcx, [rbp+arg_10]
0x180048616  call    ??1?$test_data_control@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(void)
0x18004861b  test    r15d, r15d
0x18004861e  jnz     short loc_180048643
0x180048620  lea     rdx, [rbp+arg_10]
0x180048624  lea     rcx, [rbp+arg_0]
0x180048628  call    ??C?$tip_test@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::operator->(void)
0x18004862d  mov     rcx, [rax]
0x180048630  mov     dword ptr [rcx+114h], 3
0x18004863a  lea     rcx, [rbp+arg_10]
0x18004863e  call    ??1?$test_data_control@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(void)
0x180048643  lea     rcx, [rbp+arg_0]
0x180048647  call    ?complete@?$tip_test@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::complete(void)
0x18004864c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180048653  movdqu  xmmword ptr [rdi+560h], xmm0
0x18004865b  mov     rcx, [rdi+570h]; string
0x180048662  call    cs:__imp_WindowsDeleteString
0x180048668  lea     rcx, [rbp+arg_0]
0x18004866c  mov     [rdi+570h], r12
0x180048673  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>(void)
0x180048678  mov     rcx, cs:WPP_GLOBAL_Control
0x18004867f  cmp     rcx, r13
0x180048682  jz      short loc_1800486A2
0x180048684  test    byte ptr [rcx+1Ch], 8
0x180048688  jz      short loc_1800486A2
0x18004868a  mov     rcx, [rcx+10h]
0x18004868e  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180048695  mov     edx, 8Ch
0x18004869a  xor     r9d, r9d
0x18004869d  call    WPP_SF_d
0x1800486a2  mov     rbx, [rsp+30h+arg_8]
0x1800486a7  xor     eax, eax
0x1800486a9  add     rsp, 30h
0x1800486ad  pop     r15
0x1800486af  pop     r14
0x1800486b1  pop     r13
0x1800486b3  pop     r12
0x1800486b5  pop     rdi
0x1800486b6  pop     rsi
0x1800486b7  pop     rbp
0x1800486b8  retn
0x1800486b9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
