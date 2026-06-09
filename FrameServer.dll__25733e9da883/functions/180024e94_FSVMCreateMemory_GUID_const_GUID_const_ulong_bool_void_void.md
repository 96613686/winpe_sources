# FSVMCreateMemory(_GUID const &,_GUID const &,ulong,bool,void * *,void * *)

- ea: `0x180024e94`
- end: `0x1800253a4`
- name: `?FSVMCreateMemory@@YAJAEBU_GUID@@0K_NPEAPEAX2@Z`
- size: `1296`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, unsigned int, unsigned __int8, void **, void **)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800e6c90`
- `0x1800e7240`

## callees

- `0x1800041f0`
- `0x180009608`
- `0x180009b5c`
- `0x180009cc0`
- `0x180015b40`
- `0x1800198f4`
- `0x18001c444`
- `0x18002432c`
- `0x18002435c`
- `0x180024394`
- `0x180024e94`
- `0x1800261ec`
- `0x180026c98`
- `0x18004d714`
- `0x18004da70`
- `0x1800542f4`
- `0x180054404`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025308`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025308`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180025279`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180025279`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800252fa`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800252fa`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800252b2`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800252b2`

## pseudocode

```c
__int64 __fastcall FSVMCreateMemory(
        const struct _GUID *a1,
        const struct _GUID *a2,
        unsigned int a3,
        unsigned __int8 a4,
        void **a5,
        void **a6)
{
  char v6; // bl
  int v7; // r15d
  unsigned __int64 dwMaximumSizeLow; // r13
  DWORD v11; // esi
  GuidTrace *v12; // rax
  const char *String; // rbx
  GuidTrace *v14; // rax
  const char *v15; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // r14
  unsigned int v18; // esi
  unsigned int v19; // r15d
  int v20; // eax
  int v21; // ebx
  int v22; // eax
  signed int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  int v26; // eax
  const struct std::nothrow_t *v27; // rdx
  WCHAR *v28; // rcx
  int v29; // eax
  const struct std::nothrow_t *v30; // rdx
  WCHAR *v31; // rcx
  const struct std::nothrow_t *v32; // rdx
  WCHAR *v33; // rcx
  void *v34; // rax
  signed int LastError; // eax
  HANDLE v36; // rcx
  __int64 v37; // rdx
  HANDLE hFileMappingObject; // [rsp+40h] [rbp-59h] BYREF
  LPCWSTR lpName; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int64 v41; // [rsp+50h] [rbp-49h] BYREF
  LPCWSTR *p_lpName; // [rsp+58h] [rbp-41h] BYREF
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v44[104]; // [rsp+78h] [rbp-21h] BYREF
  DWORD dwDesiredAccess; // [rsp+108h] [rbp+6Fh]

  v6 = 0;
  v7 = a4;
  dwMaximumSizeLow = a3;
  hFileMappingObject = 0;
  v11 = 2 * a4 + 2;
  dwDesiredAccess = v11;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v12 = GuidTrace::GuidTrace((GuidTrace *)v44, a2);
    String = GuidTrace::GetString(v12);
    v14 = GuidTrace::GuidTrace((GuidTrace *)&p_lpName, a1);
    GuidTrace::GetString(v14);
    v15 = "true";
    if ( !(_BYTE)v7 )
      v15 = "false";
    WPP_SF_ssDs(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)String, dwMaximumSizeLow, (__int64)v15);
    v6 = 3;
  }
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    FSString::~FSString((FSString *)&p_lpName);
  }
  if ( (v6 & 1) != 0 )
    FSString::~FSString((FSString *)v44);
  v16 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
    v16 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  v17 = (unsigned __int64)a2 & -(__int64)(v16 != 0);
  if ( byte_18010ED54 )
  {
    v41 = dwMaximumSizeLow;
    v18 = (_BYTE)v7 != 0 ? 0xFFFFFFFD : 0;
    v19 = 2 * (v7 ^ 1) + 2;
    if ( v17 )
    {
      p_lpName = (LPCWSTR *)&AutoSecurityAttributes::`vftable';
      memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
      v20 = FSVMSecurityAttributes::Set(
              (FSVMSecurityAttributes *)&p_lpName,
              L"O:LSD:AI(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;WD)");
      v21 = v20;
      if ( v20 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v20);
LABEL_16:
        p_lpName = (LPCWSTR *)&AutoSecurityAttributes::`vftable';
        AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&p_lpName);
        goto LABEL_53;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hFileMappingObject,
        0);
      v22 = CreateVmSharedMemorySection2(&hFileMappingObject, v18 + 7, v19, (__int64)a1, v17);
      v21 = v22 | 0x10000000;
      if ( v22 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v21);
        goto LABEL_16;
      }
      p_lpName = (LPCWSTR *)&AutoSecurityAttributes::`vftable';
      AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&p_lpName);
      goto LABEL_21;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFileMappingObject,
      0);
    v26 = OpenVmSharedMemorySection2(&hFileMappingObject, v18 + 7, v25, v19, a1);
    v21 = v26 | 0x10000000;
    if ( v26 >= 0 )
    {
LABEL_21:
      v11 = dwDesiredAccess;
      goto LABEL_22;
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids,
        0,
        v26 | 0x10000000);
LABEL_53:
    if ( byte_18010EC4D )
    {
      v37 = 52;
LABEL_57:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v37,
        &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids,
        (unsigned int)v21);
      goto LABEL_58;
    }
    goto LABEL_58;
  }
  lpName = 0;
  p_lpName = &lpName;
  *(_QWORD *)&FileMappingAttributes.nLength = 0;
  LOBYTE(FileMappingAttributes.lpSecurityDescriptor) = 1;
  v21 = BuildObjectName(a1, L"section", (unsigned __int16 **)&FileMappingAttributes);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>>(&p_lpName);
  if ( v21 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v21);
    v28 = (WCHAR *)lpName;
    lpName = 0;
    if ( v28 )
      operator delete(v28, v27);
    goto LABEL_52;
  }
  if ( v17 )
  {
    p_lpName = (LPCWSTR *)&AutoSecurityAttributes::`vftable';
    memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
    v29 = FSVMSecurityAttributes::Set(
            (FSVMSecurityAttributes *)&p_lpName,
            L"O:LSD:AI(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;WD)(A;;GA;;;S-1-15-3-3845273463-1331427702-1186551195-1148109977)");
    v21 = v29;
    if ( v29 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v29);
      p_lpName = (LPCWSTR *)&AutoSecurityAttributes::`vftable';
      AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&p_lpName);
      v31 = (WCHAR *)lpName;
      lpName = 0;
      if ( v31 )
        operator delete(v31, v30);
      goto LABEL_53;
    }
    v41 = (unsigned __int64)CreateFileMappingW(
                              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                              &FileMappingAttributes,
                              (2 * (v7 ^ 1) + 2) | 0x8000000u,
                              0,
                              dwMaximumSizeLow,
                              lpName);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &hFileMappingObject,
      &v41);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
    p_lpName = (LPCWSTR *)&AutoSecurityAttributes::`vftable';
    AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&p_lpName);
  }
  else
  {
    v41 = (unsigned __int64)OpenFileMappingW(v11, 0, lpName);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &hFileMappingObject,
      &v41);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
  }
  v33 = (WCHAR *)lpName;
  lpName = 0;
  if ( v33 )
    operator delete(v33, v32);
LABEL_22:
  if ( hFileMappingObject )
  {
    v34 = MapViewOfFile(hFileMappingObject, v11, 0, 0, 0);
    if ( v34 )
    {
      *a5 = v34;
      v36 = hFileMappingObject;
      hFileMappingObject = 0;
      *a6 = v36;
    }
    else
    {
      LastError = GetLastError();
      v21 = LastError;
      if ( LastError > 0 )
        v21 = (unsigned __int16)LastError | 0x80070000;
      if ( g_wppLevels )
      {
        v24 = 51;
        goto LABEL_27;
      }
    }
  }
  else
  {
    v23 = GetLastError();
    v21 = v23;
    if ( v23 > 0 )
      v21 = (unsigned __int16)v23 | 0x80070000;
    if ( g_wppLevels )
    {
      v24 = 50;
LABEL_27:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v21);
    }
  }
LABEL_52:
  if ( v21 < 0 )
    goto LABEL_53;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v37 = 53;
    goto LABEL_57;
  }
LABEL_58:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFileMappingObject);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180024e94  push    rbp
0x180024e96  push    rbx
0x180024e97  push    rsi
0x180024e98  push    rdi
0x180024e99  push    r12
0x180024e9b  push    r13
0x180024e9d  push    r14
0x180024e9f  push    r15
0x180024ea1  lea     rbp, [rsp-0Fh]
0x180024ea6  sub     rsp, 0A8h
0x180024ead  xor     ebx, ebx
0x180024eaf  movzx   r15d, r9b
0x180024eb3  mov     [rbp+47h+dwDesiredAccess], ebx
0x180024eb6  mov     rdi, rdx
0x180024eb9  mov     r13d, r8d
0x180024ebc  mov     r12, rcx
0x180024ebf  mov     [rbp+47h+hFileMappingObject], rbx
0x180024ec3  lea     esi, ds:2[r15*2]
0x180024ecb  mov     [rbp+47h+dwDesiredAccess], esi
0x180024ece  cmp     cs:byte_18010EC4D, 8
0x180024ed5  jb      short loc_180024F3E
0x180024ed7  lea     rcx, [rbp+47h+var_68]; this
0x180024edb  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180024ee0  mov     rcx, rax; this
0x180024ee3  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180024ee8  lea     rcx, [rbp+47h+var_88]; this
0x180024eec  mov     rdx, r12; struct _GUID *
0x180024eef  mov     rbx, rax
0x180024ef2  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180024ef7  mov     rcx, rax; this
0x180024efa  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180024eff  test    r15b, r15b
0x180024f02  lea     rdx, aFalse; "false"
0x180024f09  lea     rcx, aTrue_0; "true"
0x180024f10  mov     r9, rax
0x180024f13  cmovz   rcx, rdx
0x180024f17  mov     [rsp+0E0h+var_B0], rcx; __int64
0x180024f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f23  mov     dword ptr [rsp+0E0h+lpName], r13d; char
0x180024f28  mov     qword ptr [rsp+0E0h+dwMaximumSizeLow], rbx; __int64
0x180024f2d  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180024f34  call    WPP_SF_ssDs
0x180024f39  mov     ebx, 3
0x180024f3e  test    bl, 2
0x180024f41  jz      short loc_180024F4F
0x180024f43  and     ebx, 0FFFFFFFDh
0x180024f46  lea     rcx, [rbp+47h+var_88]; this
0x180024f4a  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180024f4f  test    bl, 1
0x180024f52  jz      short loc_180024F5D
0x180024f54  lea     rcx, [rbp+47h+var_68]; this
0x180024f58  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180024f5d  mov     rax, [rdi]
0x180024f60  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180024f67  jnz     short loc_180024F74
0x180024f69  mov     rax, [rdi+8]
0x180024f6d  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180024f74  test    rax, rax
0x180024f77  setnz   al
0x180024f7a  neg     al
0x180024f7c  sbb     r14, r14
0x180024f7f  and     r14, rdi
0x180024f82  xor     edi, edi
0x180024f84  cmp     cs:byte_18010ED54, dil
0x180024f8b  jz      loc_18002513C
0x180024f91  mov     al, r15b
0x180024f94  mov     [rbp+47h+var_90], r13
0x180024f98  neg     al
0x180024f9a  mov     eax, r15d
0x180024f9d  sbb     esi, esi
0x180024f9f  xor     eax, 1
0x180024fa2  and     esi, 0FFFFFFFDh
0x180024fa5  lea     r15d, ds:2[rax*2]
0x180024fad  test    r14, r14
0x180024fb0  jz      loc_1800250DA
0x180024fb6  xorps   xmm0, xmm0
0x180024fb9  lea     rdi, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x180024fc0  xor     eax, eax
0x180024fc2  mov     [rbp+47h+var_88], rdi
0x180024fc6  lea     rdx, aOLsdAiAGaSyAGa_0; "O:LSD:AI(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;"...
0x180024fcd  mov     qword ptr [rbp+47h+FileMappingAttributes.bInheritHandle], rax
0x180024fd1  lea     rcx, [rbp+47h+var_88]; this
0x180024fd5  movups  xmmword ptr [rbp+47h+FileMappingAttributes.nLength], xmm0
0x180024fd9  call    ?Set@FSVMSecurityAttributes@@QEAAJPEBG@Z; FSVMSecurityAttributes::Set(ushort const *)
0x180024fde  mov     ebx, eax
0x180024fe0  test    eax, eax
0x180024fe2  jns     short loc_180025022
0x180024fe4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024feb  jb      short loc_180025010
0x180024fed  mov     edx, 2Dh ; '-'
0x180024ff2  mov     [rsp+0E0h+dwMaximumSizeLow], eax
0x180024ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ffd  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x180025004  xor     r9d, r9d
0x180025007  mov     rcx, [rcx+10h]
0x18002500b  call    WPP_SF_qD
0x180025010  lea     rcx, [rbp+47h+var_88]; this
0x180025014  mov     [rbp+47h+var_88], rdi
0x180025018  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18002501d  jmp     loc_18002534A
0x180025022  mov     rbx, [rbp+47h+FileMappingAttributes.lpSecurityDescriptor]
0x180025026  lea     rcx, [rbp+47h+hFileMappingObject]
0x18002502a  xor     edx, edx
0x18002502c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180025031  mov     [rsp+0E0h+var_B0], r14; __int64
0x180025036  lea     r9, [rbp+47h+var_90]
0x18002503a  mov     [rsp+0E0h+lpName], r12; __int64
0x18002503f  lea     edx, [rsi+7]; DesiredAccess
0x180025042  mov     r8, rbx
0x180025045  mov     [rsp+0E0h+dwMaximumSizeLow], r15d; int
0x18002504a  lea     rcx, [rbp+47h+hFileMappingObject]; SectionHandle
0x18002504e  call    CreateVmSharedMemorySection2
0x180025053  mov     ebx, eax
0x180025055  or      ebx, 10000000h
0x18002505b  jge     short loc_180025071
0x18002505d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025064  jb      short loc_180025010
0x180025066  mov     edx, 2Eh ; '.'
0x18002506b  mov     [rsp+0E0h+dwMaximumSizeLow], ebx
0x18002506f  jmp     short loc_180024FF6
0x180025071  lea     rcx, [rbp+47h+var_88]; this
0x180025075  mov     [rbp+47h+var_88], rdi
0x180025079  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18002507e  xor     edi, edi
0x180025080  mov     esi, [rbp+47h+dwDesiredAccess]
0x180025083  mov     rcx, [rbp+47h+hFileMappingObject]; hFileMappingObject
0x180025087  test    rcx, rcx
0x18002508a  jnz     loc_1800252ED
0x180025090  call    cs:__imp_GetLastError
0x180025096  mov     ebx, eax
0x180025098  test    eax, eax
0x18002509a  jle     short loc_1800250A5
0x18002509c  movzx   ebx, ax
0x18002509f  or      ebx, 80070000h
0x1800250a5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800250ac  jb      loc_180025346
0x1800250b2  mov     edx, 32h ; '2'
0x1800250b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800250be  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x1800250c5  xor     r9d, r9d
0x1800250c8  mov     [rsp+0E0h+dwMaximumSizeLow], ebx
0x1800250cc  mov     rcx, [rcx+10h]
0x1800250d0  call    WPP_SF_qD
0x1800250d5  jmp     loc_180025346
0x1800250da  xor     edx, edx
0x1800250dc  lea     rcx, [rbp+47h+hFileMappingObject]
0x1800250e0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800250e5  mov     r9d, r15d
0x1800250e8  mov     qword ptr [rsp+0E0h+dwMaximumSizeLow], r12
0x1800250ed  lea     edx, [rsi+7]
0x1800250f0  lea     rcx, [rbp+47h+hFileMappingObject]
0x1800250f4  call    OpenVmSharedMemorySection2
0x1800250f9  mov     ebx, eax
0x1800250fb  or      ebx, 10000000h
0x180025101  jge     loc_180025080
0x180025107  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002510e  jb      loc_18002534A
0x180025114  mov     rcx, cs:WPP_GLOBAL_Control
0x18002511b  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x180025122  mov     edx, 2Fh ; '/'
0x180025127  mov     [rsp+0E0h+dwMaximumSizeLow], ebx
0x18002512b  xor     r9d, r9d
0x18002512e  mov     rcx, [rcx+10h]
0x180025132  call    WPP_SF_qD
0x180025137  jmp     loc_18002534A
0x18002513c  lea     rax, [rbp+47h+var_98]
0x180025140  mov     [rbp+47h+var_98], rdi
0x180025144  lea     r8, [rbp+47h+FileMappingAttributes]; unsigned __int16 **
0x180025148  mov     [rbp+47h+var_88], rax
0x18002514c  lea     rdx, aSection; "section"
0x180025153  mov     qword ptr [rbp+47h+FileMappingAttributes.nLength], rdi
0x180025157  mov     rcx, r12; struct _GUID *
0x18002515a  mov     byte ptr [rbp+47h+FileMappingAttributes.lpSecurityDescriptor], 1
0x18002515e  call    ?BuildObjectName@@YAJAEBU_GUID@@PEBGPEAPEAG@Z; BuildObjectName(_GUID const &,ushort const *,ushort * *)
0x180025163  lea     rcx, [rbp+47h+var_88]
0x180025167  mov     ebx, eax
0x180025169  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>>::~out_param_t<wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>>(void)
0x18002516e  mov     eax, ebx
0x180025170  shr     eax, 1Fh
0x180025173  test    al, al
0x180025175  jz      short loc_1800251BE
0x180025177  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002517e  jb      short loc_1800251A3
0x180025180  mov     rcx, cs:WPP_GLOBAL_Control
0x180025187  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x18002518e  mov     edx, 30h ; '0'
0x180025193  mov     [rsp+0E0h+dwMaximumSizeLow], ebx
0x180025197  xor     r9d, r9d
0x18002519a  mov     rcx, [rcx+10h]
0x18002519e  call    WPP_SF_qD
0x1800251a3  mov     rcx, [rbp+47h+var_98]; void *
0x1800251a7  mov     [rbp+47h+var_98], rdi
0x1800251ab  test    rcx, rcx
0x1800251ae  jz      loc_180025346
0x1800251b4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800251b9  jmp     loc_180025346
0x1800251be  test    r14, r14
0x1800251c1  jz      loc_1800252AA
0x1800251c7  xorps   xmm0, xmm0
0x1800251ca  lea     rdi, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x1800251d1  xor     eax, eax
0x1800251d3  mov     [rbp+47h+var_88], rdi
0x1800251d7  lea     rdx, aOLsdAiAGaSyAGa; "O:LSD:AI(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;"...
0x1800251de  mov     qword ptr [rbp+47h+FileMappingAttributes.bInheritHandle], rax
0x1800251e2  lea     rcx, [rbp+47h+var_88]; this
0x1800251e6  movups  xmmword ptr [rbp+47h+FileMappingAttributes.nLength], xmm0
0x1800251ea  call    ?Set@FSVMSecurityAttributes@@QEAAJPEBG@Z; FSVMSecurityAttributes::Set(ushort const *)
0x1800251ef  mov     ebx, eax
0x1800251f1  test    eax, eax
0x1800251f3  jns     short loc_18002524D
0x1800251f5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800251fc  jb      short loc_180025221
0x1800251fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180025205  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x18002520c  mov     edx, 31h ; '1'
0x180025211  mov     [rsp+0E0h+dwMaximumSizeLow], eax
0x180025215  xor     r9d, r9d
0x180025218  mov     rcx, [rcx+10h]
0x18002521c  call    WPP_SF_qD
0x180025221  lea     rcx, [rbp+47h+var_88]; this
0x180025225  mov     [rbp+47h+var_88], rdi
0x180025229  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18002522e  mov     rcx, [rbp+47h+var_98]; void *
0x180025232  mov     [rbp+47h+var_98], 0
0x18002523a  test    rcx, rcx
0x18002523d  jz      loc_18002534A
0x180025243  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180025248  jmp     loc_18002534A
0x18002524d  mov     rcx, [rbp+47h+var_98]
0x180025251  lea     rdx, [rbp+47h+FileMappingAttributes]; lpFileMappingAttributes
0x180025255  mov     [rsp+0E0h+lpName], rcx; lpName
0x18002525a  mov     eax, r15d
0x18002525d  xor     eax, 1
0x180025260  mov     [rsp+0E0h+dwMaximumSizeLow], r13d; dwMaximumSizeLow
0x180025265  xor     r9d, r9d; dwMaximumSizeHigh
0x180025268  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18002526c  lea     r8d, ds:2[rax*2]
0x180025274  bts     r8d, 1Bh; flProtect
0x180025279  call    cs:__imp_CreateFileMappingW
0x18002527f  lea     rdx, [rbp+47h+var_90]
0x180025283  mov     [rbp+47h+var_90], rax
0x180025287  lea     rcx, [rbp+47h+hFileMappingObject]
0x18002528b  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180025290  lea     rcx, [rbp+47h+var_90]
0x180025294  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180025299  lea     rcx, [rbp+47h+var_88]; this
0x18002529d  mov     [rbp+47h+var_88], rdi
0x1800252a1  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x1800252a6  xor     edi, edi
0x1800252a8  jmp     short loc_1800252D2
0x1800252aa  mov     r8, [rbp+47h+var_98]; lpName
0x1800252ae  xor     edx, edx; bInheritHandle
0x1800252b0  mov     ecx, esi; dwDesiredAccess
0x1800252b2  call    cs:__imp_OpenFileMappingW
0x1800252b8  lea     rdx, [rbp+47h+var_90]
0x1800252bc  mov     [rbp+47h+var_90], rax
0x1800252c0  lea     rcx, [rbp+47h+hFileMappingObject]
0x1800252c4  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800252c9  lea     rcx, [rbp+47h+var_90]
0x1800252cd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800252d2  mov     rcx, [rbp+47h+var_98]; void *
0x1800252d6  mov     [rbp+47h+var_98], rdi
0x1800252da  test    rcx, rcx
0x1800252dd  jz      loc_180025083
0x1800252e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800252e8  jmp     loc_180025083
0x1800252ed  xor     r9d, r9d; dwFileOffsetLow
0x1800252f0  mov     qword ptr [rsp+0E0h+dwMaximumSizeLow], rdi; dwNumberOfBytesToMap
0x1800252f5  xor     r8d, r8d; dwFileOffsetHigh
0x1800252f8  mov     edx, esi; dwDesiredAccess
0x1800252fa  call    cs:__imp_MapViewOfFile
0x180025300  mov     rcx, rax
0x180025303  test    rax, rax
0x180025306  jnz     short loc_180025330
0x180025308  call    cs:__imp_GetLastError
0x18002530e  mov     ebx, eax
0x180025310  test    eax, eax
0x180025312  jle     short loc_18002531D
0x180025314  movzx   ebx, ax
0x180025317  or      ebx, 80070000h
0x18002531d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025324  jb      short loc_180025346
0x180025326  mov     edx, 33h ; '3'
0x18002532b  jmp     loc_1800250B7
0x180025330  mov     rax, [rbp+47h+arg_20]
0x180025334  mov     [rax], rcx
0x180025337  mov     rcx, [rbp+47h+hFileMappingObject]
0x18002533b  mov     rax, [rbp+47h+arg_28]
0x18002533f  mov     [rbp+47h+hFileMappingObject], rdi
0x180025343  mov     [rax], rcx
0x180025346  test    ebx, ebx
0x180025348  jns     short loc_18002535A
0x18002534a  cmp     cs:byte_18010EC4D, 1
0x180025351  jb      short loc_180025385
0x180025353  mov     edx, 34h ; '4'
0x180025358  jmp     short loc_180025368
0x18002535a  cmp     cs:byte_18010EC4D, 8
0x180025361  jb      short loc_180025385
0x180025363  mov     edx, 35h ; '5'
0x180025368  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
