# FSSourceWatchdog::GenerateKernelDump(ushort const *,ulong,ulong)

- ea: `0x1800b3d0c`
- end: `0x1800b424d`
- name: `?GenerateKernelDump@FSSourceWatchdog@@IEAAJPEBGKK@Z`
- size: `1345`
- prototype: `__int64 __fastcall(FSSourceWatchdog *__hidden this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800b4b30`

## callees

- `0x180003e20`
- `0x180008cf0`
- `0x1800095c8`
- `0x180009608`
- `0x18000a648`
- `0x180017574`
- `0x180017fe0`
- `0x180024308`
- `0x1800b3d0c`
- `0x1800b5080`
- `0x1800b50a8`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3db3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b40f6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b40f6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b3f98`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b3f98`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800b3deb`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800b3deb`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800b3e27`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800b3e27`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800b3da9`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800b3da9`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x1800b415f`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x1800b415f`

## pseudocode

```c
__int64 __fastcall FSSourceWatchdog::GenerateKernelDump(
        FSSourceWatchdog *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4)
{
  signed int LastError; // eax
  int v8; // ebx
  HRESULT v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rax
  int v13; // ebx
  __int64 v14; // rdx
  BOOL pvData; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR pwzFile[2]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v23[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v24; // [rsp+90h] [rbp-70h] BYREF
  LPOLESTR lpsz; // [rsp+98h] [rbp-68h] BYREF
  char v26; // [rsp+A0h] [rbp-60h]
  GUID pguid; // [rsp+A8h] [rbp-58h] BYREF
  _WORD v28[264]; // [rsp+C0h] [rbp-40h] BYREF

  pwzFile[0] = v23;
  ppv = 0;
  pwzFile[1] = v23;
  v17 = 0;
  v23[0] = 0;
  pguid = 0;
  v21 = 0;
  v18 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 23, &WPP_26f50317b41939831fb096d13f0bfc88_Traceguids, this);
  if ( !(unsigned int)GetTempPath2W(260, v28) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_26f50317b41939831fb096d13f0bfc88_Traceguids, this, v8);
      goto LABEL_51;
    }
  }
  v9 = CoCreateGuid(&pguid);
  v8 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 25;
LABEL_50:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_26f50317b41939831fb096d13f0bfc88_Traceguids, this, v9);
    goto LABEL_51;
  }
  lpsz = 0;
  v24 = &v21;
  v26 = 1;
  v8 = StringFromCLSID(&pguid, &lpsz);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v24);
  if ( v8 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_26f50317b41939831fb096d13f0bfc88_Traceguids, this, v8);
LABEL_51:
    if ( byte_18010EC4D )
    {
      v14 = 38;
LABEL_57:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v14, &WPP_26f50317b41939831fb096d13f0bfc88_Traceguids, this, v8);
      goto LABEL_58;
    }
    goto LABEL_58;
  }
  v11 = -1;
  do
    ++v11;
  while ( v28[v11] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           pwzFile,
                           v28) )
  {
    v9 = -2147024882;
    v8 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 27;
    goto LABEL_50;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           pwzFile,
                           L"live_kernel_") )
  {
    v9 = -2147024882;
    v8 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 28;
    goto LABEL_50;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           pwzFile,
                           v21) )
  {
    v9 = -2147024882;
    v8 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 29;
    goto LABEL_50;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           pwzFile,
                           L".dmp") )
  {
    v9 = -2147024882;
    v8 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 30;
    goto LABEL_50;
  }
  ppv = 0;
  v9 = CoCreateInstance(&CLSID_FrameServerMonitorObjectFactory, 0, 1u, &GUID_473ae402_5e85_4176_ba86_285b5ce2cb94, &ppv);
  v8 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 31;
    goto LABEL_50;
  }
  v12 = *(_QWORD *)ppv;
  v17 = 0;
  v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(v12 + 24))(
         ppv,
         0,
         &GUID_746ea290_a034_4497_8afd_952a87bdd3d5,
         &v17);
  v8 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 32;
    goto LABEL_50;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v17 + 24LL))(
         v17,
         2,
         L"FSMSessionName_FSClientDumpGenerator");
  v8 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 33;
    goto LABEL_50;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, PCWSTR, int *))(*(_QWORD *)v17 + 112LL))(
         v17,
         L"watchdog_timer",
         a3,
         a4,
         pwzFile[0],
         &v18);
  v8 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 34;
    goto LABEL_50;
  }
  if ( v18 )
  {
    if ( byte_18010EC4D )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 37, &WPP_26f50317b41939831fb096d13f0bfc88_Traceguids, this);
  }
  else
  {
    pvData = 0;
    pcbData = 4;
    v13 = 3;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows Media Foundation\\FrameServer\\FSLiveKernelDump",
            L"PersistDumpOnFilesystem",
            0x10018u,
            0,
            &pvData,
            &pcbData) )
    {
      pvData = pvData;
      v13 = pvData ^ 3;
    }
    *((_DWORD *)this + 249) = 1;
    if ( byte_18010EC4D )
      WPP_SF_qSD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        35,
        (unsigned int)&WPP_26f50317b41939831fb096d13f0bfc88_Traceguids,
        (_DWORD)this,
        (__int64)pwzFile[0],
        v13);
    v9 = WerRegisterFile(pwzFile[0], WerRegFileTypeOther, v13);
    v8 = v9;
    if ( v9 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_51;
      v10 = 36;
      goto LABEL_50;
    }
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v14 = 39;
    goto LABEL_57;
  }
LABEL_58:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v21);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pwzFile);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v17);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800b3d0c  push    rbp
0x1800b3d0e  push    rbx
0x1800b3d0f  push    rsi
0x1800b3d10  push    r12
0x1800b3d12  push    r13
0x1800b3d14  push    r14
0x1800b3d16  push    r15
0x1800b3d18  lea     rbp, [rsp-1E0h]
0x1800b3d20  sub     rsp, 2E0h
0x1800b3d27  mov     rax, cs:__security_cookie
0x1800b3d2e  xor     rax, rsp
0x1800b3d31  mov     [rbp+210h+var_40], rax
0x1800b3d38  xor     r13d, r13d
0x1800b3d3b  lea     rax, [rbp+210h+var_290]
0x1800b3d3f  mov     [rsp+310h+pwzFile], rax
0x1800b3d44  xorps   xmm0, xmm0
0x1800b3d47  lea     rax, [rbp+210h+var_290]
0x1800b3d4b  mov     [rsp+310h+var_2B8], r13
0x1800b3d50  mov     [rsp+310h+var_298], rax
0x1800b3d55  mov     r12d, r9d
0x1800b3d58  mov     r15d, r8d
0x1800b3d5b  mov     [rsp+310h+var_2C8], r13
0x1800b3d60  mov     rsi, rcx
0x1800b3d63  mov     [rbp+210h+var_290], r13w
0x1800b3d68  movups  xmmword ptr [rbp+210h+pguid.Data1], xmm0
0x1800b3d6c  mov     [rsp+310h+var_2A8], r13
0x1800b3d71  mov     [rsp+310h+var_2C0], r13d
0x1800b3d76  cmp     cs:byte_18010EC4D, 8
0x1800b3d7d  jb      short loc_1800B3DA0
0x1800b3d7f  mov     r9, rcx
0x1800b3d82  lea     edx, [r13+17h]
0x1800b3d86  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3d8d  lea     r8, WPP_26f50317b41939831fb096d13f0bfc88_Traceguids
0x1800b3d94  mov     rcx, [rcx+0D8h]
0x1800b3d9b  call    WPP_SF_q
0x1800b3da0  lea     rdx, [rbp+210h+var_250]
0x1800b3da4  mov     ecx, 104h
0x1800b3da9  call    cs:__imp_GetTempPath2W
0x1800b3daf  test    eax, eax
0x1800b3db1  jnz     short loc_1800B3DE7
0x1800b3db3  call    cs:__imp_GetLastError
0x1800b3db9  mov     ebx, eax
0x1800b3dbb  test    eax, eax
0x1800b3dbd  jle     short loc_1800B3DC8
0x1800b3dbf  movzx   ebx, ax
0x1800b3dc2  or      ebx, 80070000h
0x1800b3dc8  test    ebx, ebx
0x1800b3dca  jns     short loc_1800B3DE7
0x1800b3dcc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3dd3  jb      loc_1800B4197
0x1800b3dd9  mov     edx, 18h
0x1800b3dde  mov     dword ptr [rsp+310h+ppv], ebx
0x1800b3de2  jmp     loc_1800B417D
0x1800b3de7  lea     rcx, [rbp+210h+pguid]; pguid
0x1800b3deb  call    cs:__imp_CoCreateGuid
0x1800b3df1  mov     ebx, eax
0x1800b3df3  test    eax, eax
0x1800b3df5  jns     short loc_1800B3E0E
0x1800b3df7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3dfe  jb      loc_1800B4197
0x1800b3e04  mov     edx, 19h
0x1800b3e09  jmp     loc_1800B4179
0x1800b3e0e  lea     rax, [rsp+310h+var_2A8]
0x1800b3e13  mov     [rbp+210h+lpsz], r13
0x1800b3e17  lea     rdx, [rbp+210h+lpsz]; lplpsz
0x1800b3e1b  mov     [rbp+210h+var_280], rax
0x1800b3e1f  lea     rcx, [rbp+210h+pguid]; rclsid
0x1800b3e23  mov     [rbp+210h+var_270], 1
0x1800b3e27  call    cs:__imp_StringFromCLSID
0x1800b3e2d  lea     rcx, [rbp+210h+var_280]
0x1800b3e31  mov     ebx, eax
0x1800b3e33  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800b3e38  mov     eax, ebx
0x1800b3e3a  shr     eax, 1Fh
0x1800b3e3d  test    al, al
0x1800b3e3f  jz      short loc_1800B3E7A
0x1800b3e41  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3e48  jb      short loc_1800B3E6D
0x1800b3e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3e51  lea     r8, WPP_26f50317b41939831fb096d13f0bfc88_Traceguids
0x1800b3e58  mov     edx, 1Ah
0x1800b3e5d  mov     dword ptr [rsp+310h+ppv], ebx
0x1800b3e61  mov     r9, rsi
0x1800b3e64  mov     rcx, [rcx+10h]
0x1800b3e68  call    WPP_SF_qD
0x1800b3e6d  test    ebx, ebx
0x1800b3e6f  jns     loc_1800B41D2
0x1800b3e75  jmp     loc_1800B4197
0x1800b3e7a  lea     rax, [rbp+210h+var_250]
0x1800b3e7e  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b3e82  inc     r8
0x1800b3e85  cmp     [rax+r8*2], r13w
0x1800b3e8a  jnz     short loc_1800B3E82
0x1800b3e8c  lea     rdx, [rbp+210h+var_250]
0x1800b3e90  lea     rcx, [rsp+310h+pwzFile]
0x1800b3e95  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800b3e9a  test    al, al
0x1800b3e9c  jnz     short loc_1800B3EBC
0x1800b3e9e  mov     eax, 8007000Eh
0x1800b3ea3  mov     ebx, eax
0x1800b3ea5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3eac  jb      loc_1800B4197
0x1800b3eb2  mov     edx, 1Bh
0x1800b3eb7  jmp     loc_1800B4179
0x1800b3ebc  mov     r8d, 0Ch
0x1800b3ec2  lea     rdx, aLiveKernel; "live_kernel_"
0x1800b3ec9  lea     rcx, [rsp+310h+pwzFile]
0x1800b3ece  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800b3ed3  test    al, al
0x1800b3ed5  jnz     short loc_1800B3EF5
0x1800b3ed7  mov     eax, 8007000Eh
0x1800b3edc  mov     ebx, eax
0x1800b3ede  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3ee5  jb      loc_1800B4197
0x1800b3eeb  mov     edx, 1Ch
0x1800b3ef0  jmp     loc_1800B4179
0x1800b3ef5  mov     rdx, [rsp+310h+var_2A8]
0x1800b3efa  lea     rcx, [rsp+310h+pwzFile]
0x1800b3eff  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800b3f04  test    al, al
0x1800b3f06  jnz     short loc_1800B3F26
0x1800b3f08  mov     eax, 8007000Eh
0x1800b3f0d  mov     ebx, eax
0x1800b3f0f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3f16  jb      loc_1800B4197
0x1800b3f1c  mov     edx, 1Dh
0x1800b3f21  jmp     loc_1800B4179
0x1800b3f26  mov     r8d, 4
0x1800b3f2c  lea     rdx, aDmp; ".dmp"
0x1800b3f33  lea     rcx, [rsp+310h+pwzFile]
0x1800b3f38  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800b3f3d  test    al, al
0x1800b3f3f  jnz     short loc_1800B3F5F
0x1800b3f41  mov     eax, 8007000Eh
0x1800b3f46  mov     ebx, eax
0x1800b3f48  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3f4f  jb      loc_1800B4197
0x1800b3f55  mov     edx, 1Eh
0x1800b3f5a  jmp     loc_1800B4179
0x1800b3f5f  mov     rcx, [rsp+310h+var_2B8]
0x1800b3f64  mov     [rsp+310h+var_2B8], r13
0x1800b3f69  test    rcx, rcx
0x1800b3f6c  jz      short loc_1800B3F7A
0x1800b3f6e  mov     rax, [rcx]
0x1800b3f71  mov     rax, [rax+10h]
0x1800b3f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3f7a  xor     edx, edx; pUnkOuter
0x1800b3f7c  lea     rax, [rsp+310h+var_2B8]
0x1800b3f81  lea     r9, _GUID_473ae402_5e85_4176_ba86_285b5ce2cb94; riid
0x1800b3f88  mov     [rsp+310h+ppv], rax; ppv
0x1800b3f8d  lea     rcx, CLSID_FrameServerMonitorObjectFactory; rclsid
0x1800b3f94  lea     r8d, [rdx+1]; dwClsContext
0x1800b3f98  call    cs:__imp_CoCreateInstance
0x1800b3f9e  mov     ebx, eax
0x1800b3fa0  test    eax, eax
0x1800b3fa2  jns     short loc_1800B3FBB
0x1800b3fa4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b3fab  jb      loc_1800B4197
0x1800b3fb1  mov     edx, 1Fh
0x1800b3fb6  jmp     loc_1800B4179
0x1800b3fbb  mov     rcx, [rsp+310h+var_2C8]
0x1800b3fc0  mov     rbx, [rsp+310h+var_2B8]
0x1800b3fc5  mov     rax, [rbx]
0x1800b3fc8  mov     [rsp+310h+var_2C8], r13
0x1800b3fcd  mov     r14, [rax+18h]
0x1800b3fd1  test    rcx, rcx
0x1800b3fd4  jz      short loc_1800B3FE2
0x1800b3fd6  mov     rdx, [rcx]
0x1800b3fd9  mov     rax, [rdx+10h]
0x1800b3fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3fe2  lea     r9, [rsp+310h+var_2C8]
0x1800b3fe7  xor     edx, edx
0x1800b3fe9  lea     r8, _GUID_746ea290_a034_4497_8afd_952a87bdd3d5
0x1800b3ff0  mov     rcx, rbx
0x1800b3ff3  mov     rax, r14
0x1800b3ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3ffb  mov     ebx, eax
0x1800b3ffd  test    eax, eax
0x1800b3fff  jns     short loc_1800B4018
0x1800b4001  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4008  jb      loc_1800B4197
0x1800b400e  mov     edx, 20h ; ' '
0x1800b4013  jmp     loc_1800B4179
0x1800b4018  mov     rcx, [rsp+310h+var_2C8]
0x1800b401d  lea     r8, aFsmsessionname; "FSMSessionName_FSClientDumpGenerator"
0x1800b4024  xor     r9d, r9d
0x1800b4027  mov     rax, [rcx]
0x1800b402a  lea     r14d, [r9+2]
0x1800b402e  mov     edx, r14d
0x1800b4031  mov     rax, [rax+18h]
0x1800b4035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b403a  mov     ebx, eax
0x1800b403c  test    eax, eax
0x1800b403e  jns     short loc_1800B4056
0x1800b4040  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4047  jb      loc_1800B4197
0x1800b404d  lea     edx, [r14+1Fh]
0x1800b4051  jmp     loc_1800B4179
0x1800b4056  mov     rdx, [rsp+310h+pwzFile]
0x1800b405b  lea     r8, [rsp+310h+var_2C0]
0x1800b4060  mov     rcx, [rsp+310h+var_2C8]
0x1800b4065  mov     r9d, r12d
0x1800b4068  mov     [rsp+310h+pvData], r8
0x1800b406d  mov     r8d, r15d
0x1800b4070  mov     [rsp+310h+ppv], rdx
0x1800b4075  lea     rdx, aWatchdogTimer; "watchdog_timer"
0x1800b407c  mov     rax, [rcx]
0x1800b407f  mov     rax, [rax+70h]
0x1800b4083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4088  mov     ebx, eax
0x1800b408a  test    eax, eax
0x1800b408c  jns     short loc_1800B40A5
0x1800b408e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4095  jb      loc_1800B4197
0x1800b409b  mov     edx, 22h ; '"'
0x1800b40a0  jmp     loc_1800B4179
0x1800b40a5  cmp     [rsp+310h+var_2C0], r13d
0x1800b40aa  jnz     loc_1800B41A7
0x1800b40b0  lea     rax, [rsp+310h+var_2B0]
0x1800b40b5  mov     [rsp+310h+var_2D0], r13d
0x1800b40ba  mov     [rsp+310h+pcbData], rax; pcbData
0x1800b40bf  lea     r8, aPersistdumponf; "PersistDumpOnFilesystem"
0x1800b40c6  lea     rax, [rsp+310h+var_2D0]
0x1800b40cb  mov     [rsp+310h+var_2B0], 4
0x1800b40d3  mov     [rsp+310h+pvData], rax; pvData
0x1800b40d8  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows Media Foun"...
0x1800b40df  mov     r9d, 10018h; dwFlags
0x1800b40e5  mov     [rsp+310h+ppv], r13; pdwType
0x1800b40ea  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800b40f1  mov     ebx, 3
0x1800b40f6  call    cs:__imp_RegGetValueW
0x1800b40fc  test    eax, eax
0x1800b40fe  jnz     short loc_1800B4111
0x1800b4100  cmp     [rsp+310h+var_2D0], r13d
0x1800b4105  mov     eax, r13d
0x1800b4108  setnbe  al
0x1800b410b  mov     [rsp+310h+var_2D0], eax
0x1800b410f  xor     ebx, eax
0x1800b4111  mov     dword ptr [rsi+3E4h], 1
0x1800b411b  cmp     cs:byte_18010EC4D, 1
0x1800b4122  jb      short loc_1800B4154
0x1800b4124  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b412b  lea     r8, WPP_26f50317b41939831fb096d13f0bfc88_Traceguids
0x1800b4132  mov     rax, [rsp+310h+pwzFile]
0x1800b4137  mov     edx, 23h ; '#'
0x1800b413c  mov     dword ptr [rsp+310h+pvData], ebx
0x1800b4140  mov     r9, rsi
0x1800b4143  mov     [rsp+310h+ppv], rax
0x1800b4148  mov     rcx, [rcx+0D8h]
0x1800b414f  call    WPP_SF_qSD
0x1800b4154  mov     rcx, [rsp+310h+pwzFile]; pwzFile
0x1800b4159  mov     r8d, ebx; dwFlags
0x1800b415c  mov     edx, r14d; regFileType
0x1800b415f  call    cs:__imp_WerRegisterFile
0x1800b4165  mov     ebx, eax
0x1800b4167  test    eax, eax
0x1800b4169  jns     short loc_1800B41D2
0x1800b416b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4172  jb      short loc_1800B4197
0x1800b4174  mov     edx, 24h ; '$'
0x1800b4179  mov     dword ptr [rsp+310h+ppv], eax
0x1800b417d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4184  lea     r8, WPP_26f50317b41939831fb096d13f0bfc88_Traceguids
0x1800b418b  mov     r9, rsi
0x1800b418e  mov     rcx, [rcx+10h]
0x1800b4192  call    WPP_SF_qD
0x1800b4197  cmp     cs:byte_18010EC4D, 1
0x1800b419e  jb      short loc_1800B4201
0x1800b41a0  mov     edx, 26h ; '&'
0x1800b41a5  jmp     short loc_1800B41E0
0x1800b41a7  cmp     cs:byte_18010EC4D, 1
0x1800b41ae  jb      short loc_1800B41D2
0x1800b41b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b41b7  lea     r8, WPP_26f50317b41939831fb096d13f0bfc88_Traceguids
0x1800b41be  mov     edx, 25h ; '%'
0x1800b41c3  mov     r9, rsi
0x1800b41c6  mov     rcx, [rcx+0D8h]
0x1800b41cd  call    WPP_SF_q
0x1800b41d2  cmp     cs:byte_18010EC4D, 8
0x1800b41d9  jb      short loc_1800B4201
0x1800b41db  mov     edx, 27h ; '''
0x1800b41e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b41e7  lea     r8, WPP_26f50317b41939831fb096d13f0bfc88_Traceguids
0x1800b41ee  mov     r9, rsi
0x1800b41f1  mov     dword ptr [rsp+310h+ppv], ebx
0x1800b41f5  mov     rcx, [rcx+0D8h]
0x1800b41fc  call    WPP_SF_qD
0x1800b4201  lea     rcx, [rsp+310h+var_2A8]
0x1800b4206  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800b420b  lea     rcx, [rsp+310h+pwzFile]
0x1800b4210  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800b4215  lea     rcx, [rsp+310h+var_2C8]; void *
0x1800b421a  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b421f  lea     rcx, [rsp+310h+var_2B8]; void *
0x1800b4224  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b4229  mov     eax, ebx
0x1800b422b  mov     rcx, [rbp+210h+var_40]
0x1800b4232  xor     rcx, rsp; StackCookie
0x1800b4235  call    __security_check_cookie
0x1800b423a  add     rsp, 2E0h
  ... truncated ...
```
