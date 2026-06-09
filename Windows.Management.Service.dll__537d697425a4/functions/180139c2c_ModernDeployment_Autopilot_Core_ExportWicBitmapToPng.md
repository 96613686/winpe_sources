# ModernDeployment::Autopilot::Core::ExportWicBitmapToPng

- ea: `0x180139c2c`
- end: `0x18013a010`
- name: `ModernDeployment::Autopilot::Core::ExportWicBitmapToPng`
- size: `996`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18013a208`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x18006e43c`
- `0x1800942e8`
- `0x180135b04`
- `0x180139c2c`
- `0x180200010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180139c94`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180139c94`

## string_xrefs

- `0x180139eff`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180139f17`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180139f2c`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180139f41`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180139f56`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180139f6b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180139f80`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180139f95`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180139faa`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180139fbf`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180139fd4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180139fe9`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180139ffe`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ModernDeployment::Autopilot::Core::ExportWicBitmapToPng(__int64 a1, __int64 **a2, _QWORD *a3)
{
  IStream *v6; // rbx
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v23; // [rsp+20h] [rbp-99h]
  _BYTE v24[4]; // [rsp+30h] [rbp-89h] BYREF
  int v25; // [rsp+34h] [rbp-85h]
  _QWORD v26[5]; // [rsp+38h] [rbp-81h] BYREF
  _BYTE v27[16]; // [rsp+60h] [rbp-59h] BYREF
  __int64 v28; // [rsp+70h] [rbp-49h]
  __int64 v29; // [rsp+B0h] [rbp-9h] BYREF
  __int64 *v30; // [rsp+B8h] [rbp-1h] BYREF
  unsigned int v31; // [rsp+C0h] [rbp+7h] BYREF
  unsigned int v32; // [rsp+C4h] [rbp+Bh] BYREF
  int v33; // [rsp+C8h] [rbp+Fh] BYREF
  GUID v34; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v26[1] = a1;
  v26[2] = a2;
  v26[3] = a3;
  v25 = 0;
  v32 = 0;
  v31 = 0;
  (*(void (__fastcall **)(_QWORD, unsigned int *, unsigned int *))(*(_QWORD *)*a3 + 24LL))(*a3, &v32, &v31);
  v6 = SHCreateMemStream(0, 0);
  v26[0] = v6;
  if ( !v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\nayukiencoder.cpp",
      (const char *)0x8007000ELL,
      v23);
  v30 = 0;
  v7 = *a2;
  v8 = **a2;
  v30 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD, __int64 **))(v8 + 64))(
         v7,
         &GUID_ContainerFormatPng,
         0,
         &v30);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\nayukiencoder.cpp",
      (const char *)(unsigned int)v9,
      v23);
  v10 = (*(__int64 (__fastcall **)(__int64 *, IStream *, __int64))(*v30 + 24))(v30, v6, 2);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\nayukiencoder.cpp",
      (const char *)(unsigned int)v10,
      v23);
  v29 = 0;
  v11 = *v30;
  v29 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, _QWORD))(v11 + 80))(v30, &v29, 0);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\nayukiencoder.cpp",
      (const char *)(unsigned int)v12,
      v23);
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 24LL))(v29, 0);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\nayukiencoder.cpp",
      (const char *)(unsigned int)v13,
      v23);
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v29 + 32LL))(v29, v32, v31);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\nayukiencoder.cpp",
      (const char *)(unsigned int)v14,
      v23);
  v34 = GUID_WICPixelFormat32bppRGBA;
  v15 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v29 + 48LL))(v29, &v34);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\nayukiencoder.cpp",
      (const char *)(unsigned int)v15,
      v23);
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v29 + 88LL))(v29, *a3, 0);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\nayukiencoder.cpp",
      (const char *)(unsigned int)v16,
      v23);
  v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 96LL))(v29);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\nayukiencoder.cpp",
      (const char *)(unsigned int)v17,
      v23);
  v18 = (*(__int64 (__fastcall **)(__int64 *))(*v30 + 88))(v30);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\nayukiencoder.cpp",
      (const char *)(unsigned int)v18,
      v23);
  v19 = (*(__int64 (__fastcall **)(IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v6 + 40LL))(v6, 0, 0, 0);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\nayukiencoder.cpp",
      (const char *)(unsigned int)v19,
      v23);
  memset_0(v27, 0, 0x50u);
  v20 = (*(__int64 (__fastcall **)(IStream *, _BYTE *, __int64))(*(_QWORD *)v6 + 96LL))(v6, v27, 1);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\nayukiencoder.cpp",
      (const char *)(unsigned int)v20,
      v23);
  v24[0] = 0;
  std::vector<unsigned char>::vector<unsigned char>(a1, v28, v24);
  v25 = 1;
  v33 = 0;
  v21 = (*(__int64 (__fastcall **)(IStream *, _QWORD, _QWORD, int *))(*(_QWORD *)v6 + 24LL))(
          v6,
          *(_QWORD *)a1,
          (unsigned int)(*(_DWORD *)(a1 + 8) - *(_DWORD *)a1),
          &v33);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\nayukiencoder.cpp",
      (const char *)(unsigned int)v21,
      v23);
  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v29);
  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v30);
  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v26);
  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(a2);
  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(a3);
  return a1;
}

```

## disassembly

```asm
0x180139c2c  push    rbp
0x180139c2e  push    rbx
0x180139c2f  push    rsi
0x180139c30  push    rdi
0x180139c31  push    r14
0x180139c33  lea     rbp, [rsp-37h]
0x180139c38  sub     rsp, 0F0h
0x180139c3f  mov     rax, cs:__security_cookie
0x180139c46  xor     rax, rsp
0x180139c49  mov     [rbp+57h+var_30], rax
0x180139c4d  mov     rsi, r8
0x180139c50  mov     r14, rdx
0x180139c53  mov     rdi, rcx
0x180139c56  mov     [rbp+57h+var_D0], rcx
0x180139c5a  mov     [rbp+57h+var_C8], rdx
0x180139c5e  mov     [rbp+57h+var_C0], r8
0x180139c62  mov     [rsp+110h+var_DC], 0
0x180139c6a  mov     [rbp+57h+var_4C], 0
0x180139c71  mov     [rbp+57h+var_50], 0
0x180139c78  mov     rcx, [r8]
0x180139c7b  mov     rax, [rcx]
0x180139c7e  lea     r8, [rbp+57h+var_50]
0x180139c82  lea     rdx, [rbp+57h+var_4C]
0x180139c86  mov     rax, [rax+18h]
0x180139c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139c8f  nop
0x180139c90  xor     edx, edx; cbInit
0x180139c92  xor     ecx, ecx; pInit
0x180139c94  call    cs:__imp_SHCreateMemStream
0x180139c9b  nop     dword ptr [rax+rax+00h]
0x180139ca0  mov     rbx, rax
0x180139ca3  mov     [rsp+110h+var_D8], rax
0x180139ca8  mov     rcx, [rbp+5Fh]; this
0x180139cac  test    rax, rax
0x180139caf  jz      loc_180139F11
0x180139cb5  mov     [rbp+57h+var_58], 0
0x180139cbd  mov     rcx, [r14]
0x180139cc0  mov     rax, [rcx]
0x180139cc3  mov     [rbp+57h+var_58], 0
0x180139ccb  lea     r9, [rbp+57h+var_58]
0x180139ccf  xor     r8d, r8d
0x180139cd2  lea     rdx, GUID_ContainerFormatPng
0x180139cd9  mov     rax, [rax+40h]
0x180139cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139ce2  mov     rcx, [rbp+5Fh]; this
0x180139ce6  test    eax, eax
0x180139ce8  js      loc_180139F29
0x180139cee  mov     rcx, [rbp+57h+var_58]
0x180139cf2  mov     rax, [rcx]
0x180139cf5  mov     r8d, 2
0x180139cfb  mov     rdx, rbx
0x180139cfe  mov     rax, [rax+18h]
0x180139d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139d07  mov     rcx, [rbp+5Fh]; this
0x180139d0b  test    eax, eax
0x180139d0d  js      loc_180139F3E
0x180139d13  mov     [rbp+57h+var_60], 0
0x180139d1b  mov     rcx, [rbp+57h+var_58]
0x180139d1f  mov     rax, [rcx]
0x180139d22  mov     [rbp+57h+var_60], 0
0x180139d2a  xor     r8d, r8d
0x180139d2d  lea     rdx, [rbp+57h+var_60]
0x180139d31  mov     rax, [rax+50h]
0x180139d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139d3a  mov     rcx, [rbp+5Fh]; this
0x180139d3e  test    eax, eax
0x180139d40  js      loc_180139F53
0x180139d46  mov     rcx, [rbp+57h+var_60]
0x180139d4a  mov     rax, [rcx]
0x180139d4d  xor     edx, edx
0x180139d4f  mov     rax, [rax+18h]
0x180139d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139d58  mov     rcx, [rbp+5Fh]; this
0x180139d5c  test    eax, eax
0x180139d5e  js      loc_180139F68
0x180139d64  mov     rcx, [rbp+57h+var_60]
0x180139d68  mov     rax, [rcx]
0x180139d6b  mov     r8d, [rbp+57h+var_50]
0x180139d6f  mov     edx, [rbp+57h+var_4C]
0x180139d72  mov     rax, [rax+20h]
0x180139d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139d7b  mov     rcx, [rbp+5Fh]; this
0x180139d7f  test    eax, eax
0x180139d81  js      loc_180139F7D
0x180139d87  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppRGBA.Data1
0x180139d8e  movdqu  [rbp+57h+var_40], xmm0
0x180139d93  mov     rcx, [rbp+57h+var_60]
0x180139d97  mov     rax, [rcx]
0x180139d9a  lea     rdx, [rbp+57h+var_40]
0x180139d9e  mov     rax, [rax+30h]
0x180139da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139da7  mov     rcx, [rbp+5Fh]; this
0x180139dab  test    eax, eax
0x180139dad  js      loc_180139F92
0x180139db3  mov     rcx, [rbp+57h+var_60]
0x180139db7  mov     rax, [rcx]
0x180139dba  xor     r8d, r8d
0x180139dbd  mov     rdx, [rsi]
0x180139dc0  mov     rax, [rax+58h]
0x180139dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139dc9  mov     rcx, [rbp+5Fh]; this
0x180139dcd  test    eax, eax
0x180139dcf  js      loc_180139FA7
0x180139dd5  mov     rcx, [rbp+57h+var_60]
0x180139dd9  mov     rax, [rcx]
0x180139ddc  mov     rax, [rax+60h]
0x180139de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139de5  mov     rcx, [rbp+5Fh]; this
0x180139de9  test    eax, eax
0x180139deb  js      loc_180139FBC
0x180139df1  mov     rcx, [rbp+57h+var_58]
0x180139df5  mov     rax, [rcx]
0x180139df8  mov     rax, [rax+58h]
0x180139dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139e01  mov     rcx, [rbp+5Fh]; this
0x180139e05  test    eax, eax
0x180139e07  js      loc_180139FD1
0x180139e0d  xor     edx, edx
0x180139e0f  mov     rax, [rbx]
0x180139e12  xor     r9d, r9d
0x180139e15  xor     r8d, r8d
0x180139e18  mov     rcx, rbx
0x180139e1b  mov     rax, [rax+28h]
0x180139e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139e24  mov     rcx, [rbp+5Fh]; this
0x180139e28  test    eax, eax
0x180139e2a  js      loc_180139FE6
0x180139e30  xor     edx, edx; Val
0x180139e32  lea     r8d, [rdx+50h]; Size
0x180139e36  lea     rcx, [rbp+57h+var_B0]; void *
0x180139e3a  call    memset_0
0x180139e3f  mov     rax, [rbx]
0x180139e42  mov     r8d, 1
0x180139e48  lea     rdx, [rbp+57h+var_B0]
0x180139e4c  mov     rcx, rbx
0x180139e4f  mov     rax, [rax+60h]
0x180139e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139e58  mov     rcx, [rbp+5Fh]; this
0x180139e5c  test    eax, eax
0x180139e5e  js      loc_180139FFB
0x180139e64  mov     [rsp+110h+var_E0], 0
0x180139e69  lea     r8, [rsp+110h+var_E0]
0x180139e6e  mov     rdx, [rbp+57h+var_A0]
0x180139e72  mov     rcx, rdi
0x180139e75  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x180139e7a  mov     [rsp+110h+var_DC], 1
0x180139e82  mov     [rbp+57h+var_48], 0
0x180139e89  mov     rax, [rbx]
0x180139e8c  mov     r8d, [rdi+8]
0x180139e90  sub     r8d, [rdi]
0x180139e93  lea     r9, [rbp+57h+var_48]
0x180139e97  mov     rdx, [rdi]
0x180139e9a  mov     rcx, rbx
0x180139e9d  mov     rax, [rax+18h]
0x180139ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139ea6  mov     rcx, [rbp+5Fh]; this
0x180139eaa  test    eax, eax
0x180139eac  js      short loc_180139EFC
0x180139eae  lea     rcx, [rbp+57h+var_60]
0x180139eb2  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180139eb7  nop
0x180139eb8  lea     rcx, [rbp+57h+var_58]
0x180139ebc  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180139ec1  nop
0x180139ec2  lea     rcx, [rsp+110h+var_D8]
0x180139ec7  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180139ecc  nop
0x180139ecd  mov     rcx, r14
0x180139ed0  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180139ed5  nop
0x180139ed6  mov     rcx, rsi
0x180139ed9  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180139ede  mov     rax, rdi
0x180139ee1  mov     rcx, [rbp+57h+var_30]
0x180139ee5  xor     rcx, rsp; StackCookie
0x180139ee8  call    __security_check_cookie
0x180139eed  add     rsp, 0F0h
0x180139ef4  pop     r14
0x180139ef6  pop     rdi
0x180139ef7  pop     rsi
0x180139ef8  pop     rbx
0x180139ef9  pop     rbp
0x180139efa  retn
0x180139efc  mov     r9d, eax; char *
0x180139eff  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139f06  mov     edx, 9Dh; void *
0x180139f0b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180139f11  mov     r9d, 8007000Eh; char *
0x180139f17  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139f1e  mov     edx, 85h; void *
0x180139f23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180139f29  mov     r9d, eax; char *
0x180139f2c  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139f33  mov     edx, 88h; void *
0x180139f38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180139f3e  mov     r9d, eax; char *
0x180139f41  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139f48  mov     edx, 89h; void *
0x180139f4d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180139f53  mov     r9d, eax; char *
0x180139f56  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139f5d  mov     edx, 8Bh; void *
0x180139f62  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180139f68  mov     r9d, eax; char *
0x180139f6b  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139f72  mov     edx, 8Ch; void *
0x180139f77  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180139f7d  mov     r9d, eax; char *
0x180139f80  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139f87  mov     edx, 8Dh; void *
0x180139f8c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180139f92  mov     r9d, eax; char *
0x180139f95  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139f9c  mov     edx, 8Fh; void *
0x180139fa1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180139fa7  mov     r9d, eax; char *
0x180139faa  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139fb1  mov     edx, 90h; void *
0x180139fb6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180139fbc  mov     r9d, eax; char *
0x180139fbf  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139fc6  mov     edx, 91h; void *
0x180139fcb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180139fd1  mov     r9d, eax; char *
0x180139fd4  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139fdb  mov     edx, 92h; void *
0x180139fe0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180139fe6  mov     r9d, eax; char *
0x180139fe9  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139ff0  mov     edx, 96h; void *
0x180139ff5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180139ffb  mov     r9d, eax; char *
0x180139ffe  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a005  mov     edx, 99h; void *
0x18013a00a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
