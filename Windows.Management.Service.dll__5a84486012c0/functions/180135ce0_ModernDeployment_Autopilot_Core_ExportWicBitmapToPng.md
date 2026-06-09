# ModernDeployment::Autopilot::Core::ExportWicBitmapToPng

- ea: `0x180135ce0`
- end: `0x1801360bd`
- name: `ModernDeployment::Autopilot::Core::ExportWicBitmapToPng`
- size: `989`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801362b4`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x18006defc`
- `0x180093060`
- `0x180131d50`
- `0x180135ce0`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180135d48`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180135d48`

## string_xrefs

- `0x180135fac`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180135fc4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180135fd9`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180135fee`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180136003`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180136018`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x18013602d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180136042`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180136057`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x18013606c`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180136081`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x180136096`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`
- `0x1801360ab`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\nayukiencoder.cpp`

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
0x180135ce0  push    rbp
0x180135ce2  push    rbx
0x180135ce3  push    rsi
0x180135ce4  push    rdi
0x180135ce5  push    r14
0x180135ce7  lea     rbp, [rsp-37h]
0x180135cec  sub     rsp, 0F0h
0x180135cf3  mov     rax, cs:__security_cookie
0x180135cfa  xor     rax, rsp
0x180135cfd  mov     [rbp+57h+var_30], rax
0x180135d01  mov     rsi, r8
0x180135d04  mov     r14, rdx
0x180135d07  mov     rdi, rcx
0x180135d0a  mov     [rbp+57h+var_D0], rcx
0x180135d0e  mov     [rbp+57h+var_C8], rdx
0x180135d12  mov     [rbp+57h+var_C0], r8
0x180135d16  mov     [rsp+110h+var_DC], 0
0x180135d1e  mov     [rbp+57h+var_4C], 0
0x180135d25  mov     [rbp+57h+var_50], 0
0x180135d2c  mov     rcx, [r8]
0x180135d2f  mov     rax, [rcx]
0x180135d32  lea     r8, [rbp+57h+var_50]
0x180135d36  lea     rdx, [rbp+57h+var_4C]
0x180135d3a  mov     rax, [rax+18h]
0x180135d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135d43  nop
0x180135d44  xor     edx, edx; cbInit
0x180135d46  xor     ecx, ecx; pInit
0x180135d48  call    cs:__imp_SHCreateMemStream
0x180135d4e  mov     rbx, rax
0x180135d51  mov     [rsp+110h+var_D8], rax
0x180135d56  mov     rcx, [rbp+5Fh]; this
0x180135d5a  test    rax, rax
0x180135d5d  jz      loc_180135FBE
0x180135d63  mov     [rbp+57h+var_58], 0
0x180135d6b  mov     rcx, [r14]
0x180135d6e  mov     rax, [rcx]
0x180135d71  mov     [rbp+57h+var_58], 0
0x180135d79  lea     r9, [rbp+57h+var_58]
0x180135d7d  xor     r8d, r8d
0x180135d80  lea     rdx, GUID_ContainerFormatPng
0x180135d87  mov     rax, [rax+40h]
0x180135d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135d90  mov     rcx, [rbp+5Fh]; this
0x180135d94  test    eax, eax
0x180135d96  js      loc_180135FD6
0x180135d9c  mov     rcx, [rbp+57h+var_58]
0x180135da0  mov     rax, [rcx]
0x180135da3  mov     r8d, 2
0x180135da9  mov     rdx, rbx
0x180135dac  mov     rax, [rax+18h]
0x180135db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135db5  mov     rcx, [rbp+5Fh]; this
0x180135db9  test    eax, eax
0x180135dbb  js      loc_180135FEB
0x180135dc1  mov     [rbp+57h+var_60], 0
0x180135dc9  mov     rcx, [rbp+57h+var_58]
0x180135dcd  mov     rax, [rcx]
0x180135dd0  mov     [rbp+57h+var_60], 0
0x180135dd8  xor     r8d, r8d
0x180135ddb  lea     rdx, [rbp+57h+var_60]
0x180135ddf  mov     rax, [rax+50h]
0x180135de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135de8  mov     rcx, [rbp+5Fh]; this
0x180135dec  test    eax, eax
0x180135dee  js      loc_180136000
0x180135df4  mov     rcx, [rbp+57h+var_60]
0x180135df8  mov     rax, [rcx]
0x180135dfb  xor     edx, edx
0x180135dfd  mov     rax, [rax+18h]
0x180135e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135e06  mov     rcx, [rbp+5Fh]; this
0x180135e0a  test    eax, eax
0x180135e0c  js      loc_180136015
0x180135e12  mov     rcx, [rbp+57h+var_60]
0x180135e16  mov     rax, [rcx]
0x180135e19  mov     r8d, [rbp+57h+var_50]
0x180135e1d  mov     edx, [rbp+57h+var_4C]
0x180135e20  mov     rax, [rax+20h]
0x180135e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135e29  mov     rcx, [rbp+5Fh]; this
0x180135e2d  test    eax, eax
0x180135e2f  js      loc_18013602A
0x180135e35  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppRGBA.Data1
0x180135e3c  movdqu  [rbp+57h+var_40], xmm0
0x180135e41  mov     rcx, [rbp+57h+var_60]
0x180135e45  mov     rax, [rcx]
0x180135e48  lea     rdx, [rbp+57h+var_40]
0x180135e4c  mov     rax, [rax+30h]
0x180135e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135e55  mov     rcx, [rbp+5Fh]; this
0x180135e59  test    eax, eax
0x180135e5b  js      loc_18013603F
0x180135e61  mov     rcx, [rbp+57h+var_60]
0x180135e65  mov     rax, [rcx]
0x180135e68  xor     r8d, r8d
0x180135e6b  mov     rdx, [rsi]
0x180135e6e  mov     rax, [rax+58h]
0x180135e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135e77  mov     rcx, [rbp+5Fh]; this
0x180135e7b  test    eax, eax
0x180135e7d  js      loc_180136054
0x180135e83  mov     rcx, [rbp+57h+var_60]
0x180135e87  mov     rax, [rcx]
0x180135e8a  mov     rax, [rax+60h]
0x180135e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135e93  mov     rcx, [rbp+5Fh]; this
0x180135e97  test    eax, eax
0x180135e99  js      loc_180136069
0x180135e9f  mov     rcx, [rbp+57h+var_58]
0x180135ea3  mov     rax, [rcx]
0x180135ea6  mov     rax, [rax+58h]
0x180135eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135eaf  mov     rcx, [rbp+5Fh]; this
0x180135eb3  test    eax, eax
0x180135eb5  js      loc_18013607E
0x180135ebb  xor     edx, edx
0x180135ebd  mov     rax, [rbx]
0x180135ec0  xor     r9d, r9d
0x180135ec3  xor     r8d, r8d
0x180135ec6  mov     rcx, rbx
0x180135ec9  mov     rax, [rax+28h]
0x180135ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135ed2  mov     rcx, [rbp+5Fh]; this
0x180135ed6  test    eax, eax
0x180135ed8  js      loc_180136093
0x180135ede  xor     edx, edx; Val
0x180135ee0  lea     r8d, [rdx+50h]; Size
0x180135ee4  lea     rcx, [rbp+57h+var_B0]; void *
0x180135ee8  call    memset_0
0x180135eed  mov     rax, [rbx]
0x180135ef0  mov     r8d, 1
0x180135ef6  lea     rdx, [rbp+57h+var_B0]
0x180135efa  mov     rcx, rbx
0x180135efd  mov     rax, [rax+60h]
0x180135f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135f06  mov     rcx, [rbp+5Fh]; this
0x180135f0a  test    eax, eax
0x180135f0c  js      loc_1801360A8
0x180135f12  mov     [rsp+110h+var_E0], 0
0x180135f17  lea     r8, [rsp+110h+var_E0]
0x180135f1c  mov     rdx, [rbp+57h+var_A0]
0x180135f20  mov     rcx, rdi
0x180135f23  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x180135f28  mov     [rsp+110h+var_DC], 1
0x180135f30  mov     [rbp+57h+var_48], 0
0x180135f37  mov     rax, [rbx]
0x180135f3a  mov     r8d, [rdi+8]
0x180135f3e  sub     r8d, [rdi]
0x180135f41  lea     r9, [rbp+57h+var_48]
0x180135f45  mov     rdx, [rdi]
0x180135f48  mov     rcx, rbx
0x180135f4b  mov     rax, [rax+18h]
0x180135f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135f54  mov     rcx, [rbp+5Fh]; this
0x180135f58  test    eax, eax
0x180135f5a  js      short loc_180135FA9
0x180135f5c  lea     rcx, [rbp+57h+var_60]
0x180135f60  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180135f65  nop
0x180135f66  lea     rcx, [rbp+57h+var_58]
0x180135f6a  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180135f6f  nop
0x180135f70  lea     rcx, [rsp+110h+var_D8]
0x180135f75  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180135f7a  nop
0x180135f7b  mov     rcx, r14
0x180135f7e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180135f83  nop
0x180135f84  mov     rcx, rsi
0x180135f87  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x180135f8c  mov     rax, rdi
0x180135f8f  mov     rcx, [rbp+57h+var_30]
0x180135f93  xor     rcx, rsp; StackCookie
0x180135f96  call    __security_check_cookie
0x180135f9b  add     rsp, 0F0h
0x180135fa2  pop     r14
0x180135fa4  pop     rdi
0x180135fa5  pop     rsi
0x180135fa6  pop     rbx
0x180135fa7  pop     rbp
0x180135fa8  retn
0x180135fa9  mov     r9d, eax; char *
0x180135fac  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180135fb3  mov     edx, 9Dh; void *
0x180135fb8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180135fbe  mov     r9d, 8007000Eh; char *
0x180135fc4  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180135fcb  mov     edx, 85h; void *
0x180135fd0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180135fd6  mov     r9d, eax; char *
0x180135fd9  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180135fe0  mov     edx, 88h; void *
0x180135fe5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180135feb  mov     r9d, eax; char *
0x180135fee  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180135ff5  mov     edx, 89h; void *
0x180135ffa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180136000  mov     r9d, eax; char *
0x180136003  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013600a  mov     edx, 8Bh; void *
0x18013600f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180136015  mov     r9d, eax; char *
0x180136018  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013601f  mov     edx, 8Ch; void *
0x180136024  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18013602a  mov     r9d, eax; char *
0x18013602d  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180136034  mov     edx, 8Dh; void *
0x180136039  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18013603f  mov     r9d, eax; char *
0x180136042  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180136049  mov     edx, 8Fh; void *
0x18013604e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180136054  mov     r9d, eax; char *
0x180136057  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013605e  mov     edx, 90h; void *
0x180136063  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180136069  mov     r9d, eax; char *
0x18013606c  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180136073  mov     edx, 91h; void *
0x180136078  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18013607e  mov     r9d, eax; char *
0x180136081  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180136088  mov     edx, 92h; void *
0x18013608d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180136093  mov     r9d, eax; char *
0x180136096  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013609d  mov     edx, 96h; void *
0x1801360a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801360a8  mov     r9d, eax; char *
0x1801360ab  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801360b2  mov     edx, 99h; void *
0x1801360b7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
