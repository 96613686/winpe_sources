# FSVMCreateEvent(_GUID const &,_GUID const &,void * *)

- ea: `0x180024ad8`
- end: `0x180024e8e`
- name: `?FSVMCreateEvent@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `950`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e67b0`

## callees

- `0x1800041f0`
- `0x180009608`
- `0x180009b5c`
- `0x180009cc0`
- `0x180015b40`
- `0x1800198f4`
- `0x18001c444`
- `0x18002432c`
- `0x180024394`
- `0x180024ad8`
- `0x1800261ec`
- `0x180026d90`
- `0x18004d714`
- `0x18004da70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180024d1a`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180024d1a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180024dbe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180024dbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024de3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024de3`
- `ntdll!NtCreateCrossVmEvent` at `0x180024c4a`
- `ntdll!NtCreateCrossVmEvent` at `0x180024c4a`

## pseudocode

```c
__int64 __fastcall FSVMCreateEvent(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  char v4; // bl
  GuidTrace *v7; // rax
  const char *String; // rbx
  GuidTrace *v9; // rax
  const char *v10; // rax
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rax
  unsigned __int64 v14; // rbx
  int v15; // eax
  const struct std::nothrow_t *v16; // rdx
  __int64 v17; // rdx
  WCHAR *v18; // rcx
  __int64 v19; // rax
  HANDLE v20; // rax
  const struct std::nothrow_t *v21; // rdx
  int v22; // eax
  const struct std::nothrow_t *v23; // rdx
  WCHAR *v24; // rcx
  HANDLE v25; // rax
  signed int LastError; // eax
  WCHAR *v27; // rcx
  __int64 v28; // rdx
  LPCWSTR *p_lpName; // [rsp+30h] [rbp-50h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v32[4]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v33; // [rsp+70h] [rbp-10h]
  LPCWSTR lpName; // [rsp+C0h] [rbp+40h] BYREF
  void *v35; // [rsp+C8h] [rbp+48h] BYREF

  v4 = 0;
  LODWORD(lpName) = 0;
  v35 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v7 = GuidTrace::GuidTrace((GuidTrace *)v32, a2);
    String = GuidTrace::GetString(v7);
    v9 = GuidTrace::GuidTrace((GuidTrace *)&p_lpName, a1);
    v10 = GuidTrace::GetString(v9);
    WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v10, (__int64)String);
    v4 = 3;
  }
  if ( (v4 & 2) != 0 )
  {
    v4 &= ~2u;
    FSString::~FSString((FSString *)&p_lpName);
  }
  if ( (v4 & 1) != 0 )
    FSString::~FSString((FSString *)v32);
  if ( !a3 )
  {
    v11 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_42;
    v12 = 21;
    goto LABEL_10;
  }
  *a3 = 0;
  v13 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
    v13 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  v14 = (unsigned __int64)a2 & -(__int64)(v13 != 0);
  if ( byte_18010ED54 )
  {
    v32[0] = 48;
    memset(&v32[1], 0, 24);
    v33 = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v35,
      0);
    v15 = NtCreateCrossVmEvent(&v35, 2031619, v32, 0, a1, v14);
    v11 = v15 | 0x10000000;
    if ( v15 < 0 )
    {
      if ( g_wppLevels )
      {
        v12 = 22;
LABEL_10:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v11);
      }
LABEL_42:
      if ( byte_18010EC4D )
      {
        v28 = 26;
LABEL_46:
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v28,
          &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids,
          (unsigned int)v11);
        goto LABEL_47;
      }
      goto LABEL_47;
    }
    goto LABEL_40;
  }
  lpName = 0;
  p_lpName = &lpName;
  *(_QWORD *)&EventAttributes.nLength = 0;
  LOBYTE(EventAttributes.lpSecurityDescriptor) = 1;
  v11 = BuildObjectName(a1, L"event", (unsigned __int16 **)&EventAttributes);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>>(&p_lpName);
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_21;
    v17 = 23;
    goto LABEL_20;
  }
  v19 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
    v19 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( v19 )
  {
    p_lpName = (LPCWSTR *)&AutoSecurityAttributes::`vftable';
    memset(&EventAttributes, 0, sizeof(EventAttributes));
    v22 = FSVMSecurityAttributes::Set(
            (FSVMSecurityAttributes *)&p_lpName,
            L"O:LSD:AI(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;WD)(A;;GA;;;S-1-15-3-3845273463-1331427702-1186551195-1148109977)");
    v11 = v22;
    if ( v22 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v22);
      p_lpName = (LPCWSTR *)&AutoSecurityAttributes::`vftable';
      AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&p_lpName);
      v24 = (WCHAR *)lpName;
      lpName = 0;
      if ( v24 )
        operator delete(v24, v23);
      goto LABEL_42;
    }
    v25 = CreateEventW(&EventAttributes, 1, 0, lpName);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v35,
      v25);
    p_lpName = (LPCWSTR *)&AutoSecurityAttributes::`vftable';
    AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&p_lpName);
  }
  else
  {
    v20 = OpenEventW(0x1F0003u, 0, lpName);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v35,
      v20);
  }
  if ( v35 )
  {
    v27 = (WCHAR *)lpName;
    lpName = 0;
    if ( v27 )
      operator delete(v27, v21);
LABEL_40:
    *a3 = v35;
    v35 = 0;
    goto LABEL_41;
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( g_wppLevels )
  {
    v17 = 25;
LABEL_20:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v11);
  }
LABEL_21:
  v18 = (WCHAR *)lpName;
  lpName = 0;
  if ( v18 )
    operator delete(v18, v16);
LABEL_41:
  if ( v11 < 0 )
    goto LABEL_42;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v28 = 27;
    goto LABEL_46;
  }
LABEL_47:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180024ad8  mov     [rsp-28h+arg_0], rbx
0x180024add  mov     [rsp-28h+arg_8], rsi
0x180024ae2  push    rbp
0x180024ae3  push    rdi
0x180024ae4  push    r13
0x180024ae6  push    r14
0x180024ae8  push    r15
0x180024aea  mov     rbp, rsp
0x180024aed  sub     rsp, 80h
0x180024af4  xor     r15d, r15d
0x180024af7  mov     rsi, r8
0x180024afa  mov     ebx, r15d
0x180024afd  mov     rdi, rdx
0x180024b00  mov     dword ptr [rbp+lpName], ebx
0x180024b03  mov     r14, rcx
0x180024b06  mov     [rbp+arg_18], r15
0x180024b0a  cmp     cs:byte_18010EC4D, 8
0x180024b11  jb      short loc_180024B79
0x180024b13  lea     rcx, [rbp+var_30]; this
0x180024b17  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180024b1c  mov     rcx, rax; this
0x180024b1f  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180024b24  lea     rcx, [rbp+var_50]; this
0x180024b28  mov     rdx, r14; struct _GUID *
0x180024b2b  mov     rbx, rax
0x180024b2e  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180024b33  mov     rcx, rax; this
0x180024b36  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180024b3b  cmp     cs:byte_18010ED54, r15b
0x180024b42  lea     rcx, aNovail; "novail"
0x180024b49  lea     r9, aVail; "vail"
0x180024b50  mov     [rsp+80h+var_58], rbx; __int64
0x180024b55  cmovz   r9, rcx
0x180024b59  mov     [rsp+80h+var_60], rax; __int64
0x180024b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b65  lea     edx, [r15+14h]
0x180024b69  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180024b70  call    WPP_SF_sss
0x180024b75  lea     ebx, [r15+3]
0x180024b79  test    bl, 2
0x180024b7c  jz      short loc_180024B8A
0x180024b7e  and     ebx, 0FFFFFFFDh
0x180024b81  lea     rcx, [rbp+var_50]; this
0x180024b85  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180024b8a  test    bl, 1
0x180024b8d  jz      short loc_180024B98
0x180024b8f  lea     rcx, [rbp+var_30]; this
0x180024b93  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180024b98  lea     r13, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x180024b9f  test    rsi, rsi
0x180024ba2  jnz     short loc_180024BD8
0x180024ba4  mov     ebx, 80004003h
0x180024ba9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024bb0  jb      loc_180024E30
0x180024bb6  lea     edx, [rsi+15h]
0x180024bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180024bc0  xor     r9d, r9d
0x180024bc3  mov     r8, r13
0x180024bc6  mov     dword ptr [rsp+80h+var_60], ebx
0x180024bca  mov     rcx, [rcx+10h]
0x180024bce  call    WPP_SF_qD
0x180024bd3  jmp     loc_180024E30
0x180024bd8  mov     [rsi], r15
0x180024bdb  mov     rax, [rdi]
0x180024bde  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180024be5  jnz     short loc_180024BF2
0x180024be7  mov     rax, [rdi+8]
0x180024beb  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180024bf2  test    rax, rax
0x180024bf5  setnz   al
0x180024bf8  neg     al
0x180024bfa  sbb     rbx, rbx
0x180024bfd  and     rbx, rdi
0x180024c00  cmp     cs:byte_18010ED54, r15b
0x180024c07  jz      short loc_180024C75
0x180024c09  xorps   xmm0, xmm0
0x180024c0c  mov     [rbp+var_30], 30h ; '0'
0x180024c14  xor     edx, edx
0x180024c16  mov     [rbp+var_18], r15
0x180024c1a  lea     rcx, [rbp+arg_18]
0x180024c1e  mov     [rbp+var_28], r15
0x180024c22  movdqu  [rbp+var_10], xmm0
0x180024c27  mov     [rbp+var_20], r15
0x180024c2b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180024c30  xor     r9d, r9d
0x180024c33  mov     [rsp+80h+var_58], rbx
0x180024c38  lea     r8, [rbp+var_30]
0x180024c3c  mov     [rsp+80h+var_60], r14
0x180024c41  mov     edx, 1F0003h
0x180024c46  lea     rcx, [rbp+arg_18]
0x180024c4a  call    cs:__imp_NtCreateCrossVmEvent
0x180024c50  mov     ebx, eax
0x180024c52  or      ebx, 10000000h
0x180024c58  jge     loc_180024E21
0x180024c5e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024c65  jb      loc_180024E30
0x180024c6b  mov     edx, 16h
0x180024c70  jmp     loc_180024BB9
0x180024c75  lea     rax, [rbp+lpName]
0x180024c79  mov     [rbp+lpName], r15
0x180024c7d  lea     r8, [rbp+EventAttributes]; unsigned __int16 **
0x180024c81  mov     [rbp+var_50], rax
0x180024c85  lea     rdx, aEvent; "event"
0x180024c8c  mov     qword ptr [rbp+EventAttributes.nLength], r15
0x180024c90  mov     rcx, r14; struct _GUID *
0x180024c93  mov     byte ptr [rbp+EventAttributes.lpSecurityDescriptor], 1
0x180024c97  call    ?BuildObjectName@@YAJAEBU_GUID@@PEBGPEAPEAG@Z; BuildObjectName(_GUID const &,ushort const *,ushort * *)
0x180024c9c  lea     rcx, [rbp+var_50]
0x180024ca0  mov     ebx, eax
0x180024ca2  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>>::~out_param_t<wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>>(void)
0x180024ca7  mov     eax, ebx
0x180024ca9  shr     eax, 1Fh
0x180024cac  test    al, al
0x180024cae  jz      short loc_180024CF3
0x180024cb0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024cb7  jb      short loc_180024CD8
0x180024cb9  mov     edx, 17h
0x180024cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180024cc5  xor     r9d, r9d
0x180024cc8  mov     r8, r13
0x180024ccb  mov     dword ptr [rsp+80h+var_60], ebx
0x180024ccf  mov     rcx, [rcx+10h]
0x180024cd3  call    WPP_SF_qD
0x180024cd8  mov     rcx, [rbp+lpName]; void *
0x180024cdc  mov     [rbp+lpName], r15
0x180024ce0  test    rcx, rcx
0x180024ce3  jz      loc_180024E2C
0x180024ce9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024cee  jmp     loc_180024E2C
0x180024cf3  mov     rax, [rdi]
0x180024cf6  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180024cfd  jnz     short loc_180024D0A
0x180024cff  mov     rax, [rdi+8]
0x180024d03  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180024d0a  test    rax, rax
0x180024d0d  jnz     short loc_180024D31
0x180024d0f  mov     r8, [rbp+lpName]; lpName
0x180024d13  xor     edx, edx; bInheritHandle
0x180024d15  mov     ecx, 1F0003h; dwDesiredAccess
0x180024d1a  call    cs:__imp_OpenEventW
0x180024d20  mov     rdx, rax
0x180024d23  lea     rcx, [rbp+arg_18]
0x180024d27  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180024d2c  jmp     loc_180024DDD
0x180024d31  xorps   xmm0, xmm0
0x180024d34  lea     rdi, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x180024d3b  xor     eax, eax
0x180024d3d  mov     [rbp+var_50], rdi
0x180024d41  lea     rdx, aOLsdAiAGaSyAGa; "O:LSD:AI(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;"...
0x180024d48  mov     qword ptr [rbp+EventAttributes.bInheritHandle], rax
0x180024d4c  lea     rcx, [rbp+var_50]; this
0x180024d50  movups  xmmword ptr [rbp+EventAttributes.nLength], xmm0
0x180024d54  call    ?Set@FSVMSecurityAttributes@@QEAAJPEBG@Z; FSVMSecurityAttributes::Set(ushort const *)
0x180024d59  mov     ebx, eax
0x180024d5b  test    eax, eax
0x180024d5d  jns     short loc_180024DAF
0x180024d5f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024d66  jb      short loc_180024D87
0x180024d68  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d6f  mov     edx, 18h
0x180024d74  xor     r9d, r9d
0x180024d77  mov     dword ptr [rsp+80h+var_60], eax
0x180024d7b  mov     r8, r13
0x180024d7e  mov     rcx, [rcx+10h]
0x180024d82  call    WPP_SF_qD
0x180024d87  lea     rcx, [rbp+var_50]; this
0x180024d8b  mov     [rbp+var_50], rdi
0x180024d8f  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x180024d94  mov     rcx, [rbp+lpName]; void *
0x180024d98  mov     [rbp+lpName], r15
0x180024d9c  test    rcx, rcx
0x180024d9f  jz      loc_180024E30
0x180024da5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024daa  jmp     loc_180024E30
0x180024daf  mov     r9, [rbp+lpName]; lpName
0x180024db3  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x180024db7  xor     r8d, r8d; bInitialState
0x180024dba  lea     edx, [r8+1]; bManualReset
0x180024dbe  call    cs:__imp_CreateEventW
0x180024dc4  mov     rdx, rax
0x180024dc7  lea     rcx, [rbp+arg_18]
0x180024dcb  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180024dd0  lea     rcx, [rbp+var_50]; this
0x180024dd4  mov     [rbp+var_50], rdi
0x180024dd8  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x180024ddd  cmp     [rbp+arg_18], r15
0x180024de1  jnz     short loc_180024E0F
0x180024de3  call    cs:__imp_GetLastError
0x180024de9  mov     ebx, eax
0x180024deb  test    eax, eax
0x180024ded  jle     short loc_180024DF8
0x180024def  movzx   ebx, ax
0x180024df2  or      ebx, 80070000h
0x180024df8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024dff  jb      loc_180024CD8
0x180024e05  mov     edx, 19h
0x180024e0a  jmp     loc_180024CBE
0x180024e0f  mov     rcx, [rbp+lpName]; void *
0x180024e13  mov     [rbp+lpName], r15
0x180024e17  test    rcx, rcx
0x180024e1a  jz      short loc_180024E21
0x180024e1c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024e21  mov     rax, [rbp+arg_18]
0x180024e25  mov     [rsi], rax
0x180024e28  mov     [rbp+arg_18], r15
0x180024e2c  test    ebx, ebx
0x180024e2e  jns     short loc_180024E40
0x180024e30  cmp     cs:byte_18010EC4D, 1
0x180024e37  jb      short loc_180024E67
0x180024e39  mov     edx, 1Ah
0x180024e3e  jmp     short loc_180024E4E
0x180024e40  cmp     cs:byte_18010EC4D, 8
0x180024e47  jb      short loc_180024E67
0x180024e49  mov     edx, 1Bh
0x180024e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e55  mov     r9d, ebx
0x180024e58  mov     r8, r13
0x180024e5b  mov     rcx, [rcx+0D8h]
0x180024e62  call    WPP_SF_d
0x180024e67  lea     rcx, [rbp+arg_18]
0x180024e6b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180024e70  lea     r11, [rsp+80h+var_s0]
0x180024e78  mov     eax, ebx
0x180024e7a  mov     rbx, [r11+30h]
0x180024e7e  mov     rsi, [r11+38h]
0x180024e82  mov     rsp, r11
0x180024e85  pop     r15
0x180024e87  pop     r14
0x180024e89  pop     r13
0x180024e8b  pop     rdi
0x180024e8c  pop     rbp
0x180024e8d  retn
```
