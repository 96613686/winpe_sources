# DeviceConfiguration::DeviceInstaller::_FillPrinterParameters(std::shared_ptr<DeviceConfiguration::Device>,unsigned __int64,ushort *)

- ea: `0x180015678`
- end: `0x180015964`
- name: `?_FillPrinterParameters@DeviceInstaller@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@_KPEAG@Z`
- size: `748`
- prototype: `__int64 __fastcall(__int64, IID **, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180015088`

## callees

- `0x1800020c0`
- `0x180008e7c`
- `0x180008f08`
- `0x18000af54`
- `0x18000dc94`
- `0x1800115a0`
- `0x18001440c`
- `0x180014658`
- `0x1800146c4`
- `0x180014fcc`
- `0x180015010`
- `0x180015678`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800156d4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800156d4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001592d`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001592d`

## string_xrefs

- `0x1800156e5`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x18001571a`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x180015746`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x18001576f`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x1800157b5`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x1800157f7`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x180015829`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x18001588e`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x1800158d0`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x180015902`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceInstaller::_FillPrinterParameters(
        __int64 a1,
        IID **a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  HRESULT v6; // eax
  int v7; // eax
  int v8; // eax
  unsigned __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  __int64 DeviceId; // rax
  int v13; // eax
  unsigned __int64 v14; // rdx
  int v15; // eax
  bool v16; // bl
  int v17; // eax
  __int64 UserSid; // rax
  int v19; // eax
  unsigned __int64 v20; // rdx
  int v21; // eax
  std::_Ref_count_base *v22; // rcx
  int v24; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int64 v25; // [rsp+28h] [rbp-48h] BYREF
  LPOLESTR lpsz[2]; // [rsp+30h] [rbp-40h] BYREF
  IID rclsid; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  lpsz[1] = (LPOLESTR)a2;
  wil::RoInitialize(&v24);
  v25 = 0;
  lpsz[0] = 0;
  rclsid = (*a2)[14];
  v6 = StringFromCLSID(&rclsid, lpsz);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)(unsigned int)v6,
      v24);
  v7 = StringCchCopyW(a4, 0x30Cu, L"{2a42f847-7a53-4230-9cc1-314021fc7c3b}");
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC2,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)(unsigned int)v7,
      v24);
  v8 = StringCchCatW(a4, 0x30Cu, lpsz[0]);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)(unsigned int)v8,
      v24);
  v10 = StringCchLengthW(a4, v9, &v25);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)(unsigned int)v10,
      v24);
  a4[v25] = 59;
  v25 = 0;
  v11 = StringCchCatW(a4, 0x30Cu, L"{069b2476-c6b4-4093-9815-ae387a8caa42}");
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)(unsigned int)v11,
      v24);
  DeviceId = DeviceConfiguration::Device::GetDeviceId(*a2, &rclsid);
  if ( *(_QWORD *)(DeviceId + 24) > 7u )
    DeviceId = *(_QWORD *)DeviceId;
  v13 = StringCchCatW(a4, 0x30Cu, (const unsigned __int16 *)DeviceId);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)(unsigned int)v13,
      v24);
  std::wstring::_Tidy_deallocate(&rclsid);
  v15 = StringCchLengthW(a4, v14, &v25);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)(unsigned int)v15,
      v24);
  a4[v25] = 59;
  v16 = *(_QWORD *)(DeviceConfiguration::Device::GetUserSid(*a2, &rclsid) + 16) != 0;
  std::wstring::_Tidy_deallocate(&rclsid);
  if ( v16 )
  {
    v25 = 0;
    v17 = StringCchCatW(a4, 0x30Cu, L"{CCF68DDA-0A57-4224-BF2E-94463CFA4E6D}");
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD2,
        (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
        (const char *)(unsigned int)v17,
        v24);
    UserSid = DeviceConfiguration::Device::GetUserSid(*a2, &rclsid);
    if ( *(_QWORD *)(UserSid + 24) > 7u )
      UserSid = *(_QWORD *)UserSid;
    v19 = StringCchCatW(a4, 0x30Cu, (const unsigned __int16 *)UserSid);
    if ( v19 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD3,
        (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
        (const char *)(unsigned int)v19,
        v24);
    std::wstring::_Tidy_deallocate(&rclsid);
    v21 = StringCchLengthW(a4, v20, &v25);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
        (const char *)(unsigned int)v21,
        v24);
    a4[v25] = 59;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpsz);
  if ( (_BYTE)v24 )
    RoUninitialize();
  v22 = (std::_Ref_count_base *)a2[1];
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  return 0;
}

```

## disassembly

```asm
0x180015678  mov     [rsp-28h+arg_0], rbx
0x18001567d  push    rbp
0x18001567e  push    rsi
0x18001567f  push    rdi
0x180015680  push    r12
0x180015682  push    r15
0x180015684  mov     rbp, rsp
0x180015687  sub     rsp, 70h
0x18001568b  mov     rax, cs:__security_cookie
0x180015692  xor     rax, rsp
0x180015695  mov     [rbp+var_10], rax
0x180015699  mov     rdi, r9
0x18001569c  mov     rsi, rdx
0x18001569f  mov     [rbp+var_38], rdx
0x1800156a3  lea     rcx, [rbp+var_50]
0x1800156a7  call    ?RoInitialize@wil@@YA?AV?$unique_call@P6AXXZ$1?RoUninitialize@@YAXXZ$00@1@W4RO_INIT_TYPE@@@Z; wil::RoInitialize(RO_INIT_TYPE)
0x1800156ac  nop
0x1800156ad  mov     [rbp+var_48], 0
0x1800156b5  mov     [rbp+lpsz], 0
0x1800156bd  mov     rax, [rsi]
0x1800156c0  movups  xmm0, xmmword ptr [rax+0E0h]
0x1800156c7  movdqu  xmmword ptr [rbp+rclsid.Data1], xmm0
0x1800156cc  lea     rdx, [rbp+lpsz]; lplpsz
0x1800156d0  lea     rcx, [rbp+rclsid]; rclsid
0x1800156d4  call    cs:__imp_StringFromCLSID
0x1800156da  mov     rcx, [rbp+28h]; this
0x1800156de  test    eax, eax
0x1800156e0  jns     short loc_1800156F7
0x1800156e2  mov     r9d, eax; char *
0x1800156e5  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x1800156ec  mov     edx, 0C1h; void *
0x1800156f1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800156f7  lea     r8, a2a42f8477a5342; "{2a42f847-7a53-4230-9cc1-314021fc7c3b}"
0x1800156fe  mov     r15d, 30Ch
0x180015704  mov     edx, r15d; unsigned __int64
0x180015707  mov     rcx, rdi; unsigned __int16 *
0x18001570a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001570f  mov     rcx, [rbp+28h]; this
0x180015713  test    eax, eax
0x180015715  jns     short loc_18001572C
0x180015717  mov     r9d, eax; char *
0x18001571a  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180015721  mov     edx, 0C2h; void *
0x180015726  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001572c  mov     r8, [rbp+lpsz]; unsigned __int16 *
0x180015730  mov     rdx, r15; unsigned __int64
0x180015733  mov     rcx, rdi; unsigned __int16 *
0x180015736  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001573b  mov     rcx, [rbp+28h]; this
0x18001573f  test    eax, eax
0x180015741  jns     short loc_180015758
0x180015743  mov     r9d, eax; char *
0x180015746  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x18001574d  mov     edx, 0C3h; void *
0x180015752  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180015758  lea     r8, [rbp+var_48]; unsigned __int64 *
0x18001575c  mov     rcx, rdi; unsigned __int16 *
0x18001575f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180015764  mov     rcx, [rbp+28h]; this
0x180015768  test    eax, eax
0x18001576a  jns     short loc_180015781
0x18001576c  mov     r9d, eax; char *
0x18001576f  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180015776  mov     edx, 0C4h; void *
0x18001577b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180015781  mov     r12d, 3Bh ; ';'
0x180015787  mov     rax, [rbp+var_48]
0x18001578b  mov     [rdi+rax*2], r12w
0x180015790  mov     [rbp+var_48], 0
0x180015798  lea     r8, a069b2476C6b440; "{069b2476-c6b4-4093-9815-ae387a8caa42}"
0x18001579f  mov     rdx, r15; unsigned __int64
0x1800157a2  mov     rcx, rdi; unsigned __int16 *
0x1800157a5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800157aa  mov     rcx, [rbp+28h]; this
0x1800157ae  test    eax, eax
0x1800157b0  jns     short loc_1800157C7
0x1800157b2  mov     r9d, eax; char *
0x1800157b5  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x1800157bc  mov     edx, 0C9h; void *
0x1800157c1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800157c7  lea     rdx, [rbp+rclsid]
0x1800157cb  mov     rcx, [rsi]
0x1800157ce  call    ?GetDeviceId@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetDeviceId(void)
0x1800157d3  nop
0x1800157d4  cmp     qword ptr [rax+18h], 7
0x1800157d9  jbe     short loc_1800157DE
0x1800157db  mov     rax, [rax]
0x1800157de  mov     r8, rax; unsigned __int16 *
0x1800157e1  mov     rdx, r15; unsigned __int64
0x1800157e4  mov     rcx, rdi; unsigned __int16 *
0x1800157e7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800157ec  mov     rcx, [rbp+28h]; this
0x1800157f0  test    eax, eax
0x1800157f2  jns     short loc_180015809
0x1800157f4  mov     r9d, eax; char *
0x1800157f7  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x1800157fe  mov     edx, 0CAh; void *
0x180015803  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180015809  lea     rcx, [rbp+rclsid]
0x18001580d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015812  lea     r8, [rbp+var_48]; unsigned __int64 *
0x180015816  mov     rcx, rdi; unsigned __int16 *
0x180015819  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001581e  mov     rcx, [rbp+28h]; this
0x180015822  test    eax, eax
0x180015824  jns     short loc_18001583B
0x180015826  mov     r9d, eax; char *
0x180015829  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180015830  mov     edx, 0CBh; void *
0x180015835  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001583b  mov     rax, [rbp+var_48]
0x18001583f  mov     [rdi+rax*2], r12w
0x180015844  lea     rdx, [rbp+rclsid]
0x180015848  mov     rcx, [rsi]
0x18001584b  call    ?GetUserSid@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetUserSid(void)
0x180015850  cmp     qword ptr [rax+10h], 0
0x180015855  setnz   bl
0x180015858  lea     rcx, [rbp+rclsid]
0x18001585c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015861  test    bl, bl
0x180015863  jz      loc_18001591D
0x180015869  mov     [rbp+var_48], 0
0x180015871  lea     r8, aCcf68dda0a5742; "{CCF68DDA-0A57-4224-BF2E-94463CFA4E6D}"
0x180015878  mov     rdx, r15; unsigned __int64
0x18001587b  mov     rcx, rdi; unsigned __int16 *
0x18001587e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015883  mov     rcx, [rbp+28h]; this
0x180015887  test    eax, eax
0x180015889  jns     short loc_1800158A0
0x18001588b  mov     r9d, eax; char *
0x18001588e  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180015895  mov     edx, 0D2h; void *
0x18001589a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800158a0  lea     rdx, [rbp+rclsid]
0x1800158a4  mov     rcx, [rsi]
0x1800158a7  call    ?GetUserSid@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetUserSid(void)
0x1800158ac  nop
0x1800158ad  cmp     qword ptr [rax+18h], 7
0x1800158b2  jbe     short loc_1800158B7
0x1800158b4  mov     rax, [rax]
0x1800158b7  mov     r8, rax; unsigned __int16 *
0x1800158ba  mov     rdx, r15; unsigned __int64
0x1800158bd  mov     rcx, rdi; unsigned __int16 *
0x1800158c0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800158c5  mov     rcx, [rbp+28h]; this
0x1800158c9  test    eax, eax
0x1800158cb  jns     short loc_1800158E2
0x1800158cd  mov     r9d, eax; char *
0x1800158d0  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x1800158d7  mov     edx, 0D3h; void *
0x1800158dc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800158e2  lea     rcx, [rbp+rclsid]
0x1800158e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800158eb  lea     r8, [rbp+var_48]; unsigned __int64 *
0x1800158ef  mov     rcx, rdi; unsigned __int16 *
0x1800158f2  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800158f7  mov     rcx, [rbp+28h]; this
0x1800158fb  test    eax, eax
0x1800158fd  jns     short loc_180015914
0x1800158ff  mov     r9d, eax; char *
0x180015902  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180015909  mov     edx, 0D4h; void *
0x18001590e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180015914  mov     rax, [rbp+var_48]
0x180015918  mov     [rdi+rax*2], r12w
0x18001591d  lea     rcx, [rbp+lpsz]
0x180015921  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015926  nop
0x180015927  cmp     byte ptr [rbp+var_50], 0
0x18001592b  jz      short loc_180015934
0x18001592d  call    cs:__imp_RoUninitialize
0x180015933  nop
0x180015934  mov     rcx, [rsi+8]; this
0x180015938  test    rcx, rcx
0x18001593b  jz      short loc_180015942
0x18001593d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015942  xor     eax, eax
0x180015944  mov     rcx, [rbp+var_10]
0x180015948  xor     rcx, rsp; StackCookie
0x18001594b  call    __security_check_cookie
0x180015950  mov     rbx, [rsp+70h+arg_0]
0x180015958  add     rsp, 70h
0x18001595c  pop     r15
0x18001595e  pop     r12
0x180015960  pop     rdi
0x180015961  pop     rsi
0x180015962  pop     rbp
0x180015963  retn
```
