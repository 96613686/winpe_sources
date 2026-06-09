# wil::cloud_store::unmarshal<Windows::Data::Accessibility::EyeControl::SyncedSettings>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)

- ea: `0x180018d24`
- end: `0x180018f91`
- name: `??$unmarshal@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z`
- size: `621`
- prototype: `__int64 __fastcall(__int64, __int64 *, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001325c`

## callees

- `0x18000bd64`
- `0x180018d24`
- `0x180019ae8`
- `0x180019da0`
- `0x18001a4a4`
- `0x18001b128`
- `0x18001b1b8`
- `0x18001b8d8`
- `0x18001ba2c`
- `0x180020a58`
- `0x180022594`
- `0x180022b80`
- `0x180022e18`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::unmarshal<Windows::Data::Accessibility::EyeControl::SyncedSettings>(
        __int64 a1,
        __int64 *a2,
        char a3)
{
  __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  const struct bond::blob *v10; // rax
  bond *v11; // rcx
  __int64 v12; // r8
  const char *v13; // r9
  _BYTE v15[8]; // [rsp+28h] [rbp-B0h] BYREF
  __int64 *v16; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+38h] [rbp-A0h] BYREF
  char v18; // [rsp+40h] [rbp-98h]
  int v19; // [rsp+50h] [rbp-88h]
  __int16 v20; // [rsp+58h] [rbp-80h]
  _BYTE v21[32]; // [rsp+60h] [rbp-78h] BYREF
  int v22; // [rsp+80h] [rbp-58h]
  __int16 v23; // [rsp+88h] [rbp-50h]
  _BYTE v24[8]; // [rsp+90h] [rbp-48h] BYREF
  _BYTE v25[24]; // [rsp+98h] [rbp-40h] BYREF
  int v26; // [rsp+B0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  int v30; // [rsp+E8h] [rbp+10h] BYREF
  __int64 v31; // [rsp+F8h] [rbp+20h] BYREF

  v5 = a1;
  *(_DWORD *)a1 = 0;
  *(_DWORD *)(a1 + 4) = 400000;
  *(_DWORD *)(a1 + 8) = 800000;
  *(_DWORD *)(a1 + 12) = 1084227584;
  *(_DWORD *)(a1 + 16) = 1036831949;
  *(_WORD *)(a1 + 20) = 1;
  *(_BYTE *)(a1 + 22) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_WORD *)(a1 + 40) = 1;
  *(_BYTE *)(a1 + 48) = 1;
  v30 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, int *))(*a2 + 72))(a2, &v30);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x685,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v6,
      1);
  *(_DWORD *)(v5 + 44) = v30 == 1;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 64))(a2, v5 + 24);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x691,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v7,
      1);
  if ( (a3 & 3) != 0 )
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(v5 + 32, a2);
  else
    *(_BYTE *)(v5 + 48) = 0;
  v31 = 0;
  v8 = *a2;
  v16 = &v31;
  v17 = 0;
  v18 = 1;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v8 + 56))(a2, &v17);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x69F,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v9,
      1);
  wil::details::out_param_t<wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>>(&v16);
  if ( v31 )
  {
    wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>(
      v15,
      v31);
    v10 = (const struct bond::blob *)wil::cloud_store::buffer_to_blob(&v16, v15);
    bond::blob::blob((bond::blob *)v24, v10);
    v26 = 0;
    boost::detail::shared_count::~shared_count((boost::detail::shared_count *)&v17);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>((__int64 *)v15);
    bond::CompactBinaryReader<bond::InputBuffer>::CompactBinaryReader<bond::InputBuffer>(
      (bond::blob *)&v16,
      (const struct bond::blob *)v24);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( !(unsigned __int8)bond::CompactBinaryReader<bond::InputBuffer>::ReadVersion(&v16) )
        bond::UnknownProtocolException(v11);
      bond::blob::blob((bond::blob *)v21, (const struct bond::blob *)&v16);
      v22 = v19;
      v23 = v20;
      bond::Deserialize<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::CompactBinaryReader<bond::InputBuffer>>(
        (__int64)v21,
        v5,
        v12);
      *(_BYTE *)(v5 + 40) = 0;
      boost::detail::shared_count::~shared_count((boost::detail::shared_count *)&v17);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &bond::Exception `RTTI Type Descriptor', 0) )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x6B2,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
          v13);
        *(_BYTE *)(a1 + 41) = 1;
        v5 = a1;
        __eh34_try_continuation(0, &bond::Exception `RTTI Type Descriptor', &loc_180018F11);
      }
    }
    boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v25);
  }
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v31);
  return v5;
}

```

## disassembly

```asm
0x180018d24  mov     r11, rsp
0x180018d27  mov     [r11+18h], rbx
0x180018d2b  mov     [r11+8], rcx
0x180018d2f  push    rsi
0x180018d30  push    rdi
0x180018d31  push    r14
0x180018d33  sub     rsp, 0C0h
0x180018d3a  mov     esi, r8d
0x180018d3d  mov     rdi, rdx
0x180018d40  mov     rbx, rcx
0x180018d43  xor     r14d, r14d
0x180018d46  mov     [rsp+0D8h+var_B8], r14d
0x180018d4b  mov     [rcx], r14d
0x180018d4e  mov     dword ptr [rcx+4], 61A80h
0x180018d55  mov     dword ptr [rcx+8], 0C3500h
0x180018d5c  mov     dword ptr [rcx+0Ch], 40A00000h
0x180018d63  mov     dword ptr [rcx+10h], 3DCCCCCDh
0x180018d6a  mov     word ptr [rcx+14h], 1
0x180018d70  mov     [rcx+16h], r14b
0x180018d74  mov     [rcx+20h], r14
0x180018d78  mov     word ptr [rcx+28h], 1
0x180018d7e  mov     byte ptr [rcx+30h], 1
0x180018d82  mov     [rsp+0D8h+var_B8], 1; int
0x180018d8a  mov     [r11+10h], r14d
0x180018d8e  mov     rax, [rdx]
0x180018d91  lea     rdx, [r11+10h]
0x180018d95  mov     rcx, rdi
0x180018d98  mov     rax, [rax+48h]
0x180018d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018da1  mov     rcx, [rsp+0D8h]; this
0x180018da9  test    eax, eax
0x180018dab  js      loc_180018F4B
0x180018db1  cmp     [rsp+0D8h+arg_8], 1
0x180018db9  mov     eax, 1
0x180018dbe  jz      short loc_180018DC3
0x180018dc0  mov     eax, r14d
0x180018dc3  mov     [rbx+2Ch], eax
0x180018dc6  mov     rax, [rdi]
0x180018dc9  lea     rdx, [rbx+18h]
0x180018dcd  mov     rcx, rdi
0x180018dd0  mov     rax, [rax+40h]
0x180018dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dd9  mov     rcx, [rsp+0D8h]; this
0x180018de1  test    eax, eax
0x180018de3  js      loc_180018F60
0x180018de9  test    sil, 3
0x180018ded  jz      short loc_180018DFD
0x180018def  lea     rcx, [rbx+20h]
0x180018df3  mov     rdx, rdi
0x180018df6  call    ??4?$com_ptr_t@UICloudStoreData@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(Windows::Internal::Storage::Cloud::ICloudStoreData *)
0x180018dfb  jmp     short loc_180018E01
0x180018dfd  mov     [rbx+30h], r14b
0x180018e01  mov     [rsp+0D8h+arg_18], r14
0x180018e09  mov     rax, [rdi]
0x180018e0c  lea     rcx, [rsp+0D8h+arg_18]
0x180018e14  mov     [rsp+0D8h+var_A8], rcx
0x180018e19  mov     [rsp+0D8h+var_A0], r14
0x180018e1e  mov     [rsp+0D8h+var_98], 1
0x180018e23  lea     rdx, [rsp+0D8h+var_A0]
0x180018e28  mov     rcx, rdi
0x180018e2b  mov     rax, [rax+38h]
0x180018e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e34  mov     rcx, [rsp+0D8h]; this
0x180018e3c  test    eax, eax
0x180018e3e  js      loc_180018F75
0x180018e44  lea     rcx, [rsp+0D8h+var_A8]
0x180018e49  call    ??1?$out_param_t@V?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>>(void)
0x180018e4e  mov     rdx, [rsp+0D8h+arg_18]
0x180018e56  test    rdx, rdx
0x180018e59  jz      loc_180018F27
0x180018e5f  lea     rcx, [rsp+0D8h+var_B0]
0x180018e64  call    ??0?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIBuffer@Streams@Storage@Windows@@@Z; wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>(Windows::Storage::Streams::IBuffer *)
0x180018e69  nop
0x180018e6a  lea     rdx, [rsp+0D8h+var_B0]
0x180018e6f  lea     rcx, [rsp+0D8h+var_A8]
0x180018e74  call    ?buffer_to_blob@cloud_store@wil@@CA?AVblob@bond@@AEBV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@@Z; wil::cloud_store::buffer_to_blob(wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy> const &)
0x180018e79  mov     rdx, rax; struct bond::blob *
0x180018e7c  lea     rcx, [rsp+0D8h+var_48]; this
0x180018e84  call    ??0blob@bond@@QEAA@AEBV01@@Z; bond::blob::blob(bond::blob const &)
0x180018e89  mov     [rsp+0D8h+var_28], r14d
0x180018e91  lea     rcx, [rsp+0D8h+var_A0]; this
0x180018e96  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180018e9b  nop
0x180018e9c  lea     rcx, [rsp+0D8h+var_B0]
0x180018ea1  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180018ea6  nop
0x180018ea7  lea     rdx, [rsp+0D8h+var_48]
0x180018eaf  lea     rcx, [rsp+0D8h+var_A8]
0x180018eb4  call    ??0?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAA@AEBVInputBuffer@1@G@Z; bond::CompactBinaryReader<bond::InputBuffer>::CompactBinaryReader<bond::InputBuffer>(bond::InputBuffer const &,ushort)
0x180018eb9  nop
0x180018eba  lea     rcx, [rsp+0D8h+var_A8]
0x180018ebf  call    ?ReadVersion@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAA_NXZ; bond::CompactBinaryReader<bond::InputBuffer>::ReadVersion(void)
0x180018ec4  test    al, al
0x180018ec6  jz      loc_180018F8A
0x180018ecc  lea     rdx, [rsp+0D8h+var_A8]; struct bond::blob *
0x180018ed1  lea     rcx, [rsp+0D8h+var_78]; this
0x180018ed6  call    ??0blob@bond@@QEAA@AEBV01@@Z; bond::blob::blob(bond::blob const &)
0x180018edb  mov     ecx, [rsp+0D8h+var_88]
0x180018edf  mov     [rsp+0D8h+var_58], ecx
0x180018ee6  movzx   eax, [rsp+0D8h+var_80]
0x180018eeb  mov     [rsp+0D8h+var_50], ax
0x180018ef3  mov     rdx, rbx
0x180018ef6  lea     rcx, [rsp+0D8h+var_78]
0x180018efb  call    ??$Deserialize@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@YAXV?$CompactBinaryReader@VInputBuffer@bond@@@0@AEAV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@Z; bond::Deserialize<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::CompactBinaryReader<bond::InputBuffer>>(bond::CompactBinaryReader<bond::InputBuffer>,wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings> &)
0x180018f00  mov     [rbx+28h], r14b
0x180018f04  lea     rcx, [rsp+0D8h+var_A0]; this
0x180018f09  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180018f0e  nop
0x180018f0f  jmp     short loc_180018F19
0x180018f11  mov     rbx, [rsp+0D8h+arg_0]
0x180018f19  lea     rcx, [rsp+0D8h+var_40]; this
0x180018f21  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180018f26  nop
0x180018f27  lea     rcx, [rsp+0D8h+arg_18]
0x180018f2f  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180018f34  mov     rax, rbx
0x180018f37  mov     rbx, [rsp+0D8h+arg_10]
0x180018f3f  add     rsp, 0C0h
0x180018f46  pop     r14
0x180018f48  pop     rdi
0x180018f49  pop     rsi
0x180018f4a  retn
0x180018f4b  mov     r9d, eax; char *
0x180018f4e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180018f55  mov     edx, 685h; void *
0x180018f5a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180018f60  mov     r9d, eax; char *
0x180018f63  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180018f6a  mov     edx, 691h; void *
0x180018f6f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180018f75  mov     r9d, eax; char *
0x180018f78  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180018f7f  mov     edx, 69Fh; void *
0x180018f84  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180018f8a  call    ?UnknownProtocolException@bond@@YAXXZ; bond::UnknownProtocolException(void)
```
