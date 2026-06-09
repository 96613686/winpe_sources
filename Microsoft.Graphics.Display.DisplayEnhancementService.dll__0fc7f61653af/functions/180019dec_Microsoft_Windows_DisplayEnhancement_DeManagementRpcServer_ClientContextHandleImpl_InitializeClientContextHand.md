# Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandleImpl::InitializeClientContextHandle(_DEM_RPC_CLIENT_ID,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServerPolicy> const &)

- ea: `0x180019dec`
- end: `0x180019fec`
- name: `?InitializeClientContextHandle@ClientContextHandleImpl@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@QEAAXU_DEM_RPC_CLIENT_ID@@AEBV?$shared_ptr@VDeManagementRpcServerPolicy@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(__int64, DWORD, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a064`

## callees

- `0x18000f778`
- `0x180011fe8`
- `0x180013138`
- `0x18001912c`
- `0x18001956c`
- `0x180019dec`
- `0x18001c7f0`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019f02`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019f02`

## string_xrefs

- `0x180019ee8`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserverclient.cpp`
- `0x180019fac`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementrpcserverclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandleImpl::InitializeClientContextHandle(
        __int64 a1,
        DWORD a2,
        __int64 a3)
{
  __int64 *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r8
  int v8; // edx
  signed int v9; // edi
  int v10; // r8d
  int v11; // edx
  signed int v12; // ebx
  int v13; // r8d
  int v15; // [rsp+20h] [rbp-48h]
  _BYTE v16[8]; // [rsp+50h] [rbp-18h] BYREF
  std::_Ref_count_base *v17; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HANDLE v19; // [rsp+70h] [rbp+8h] BYREF

  v5 = (__int64 *)std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<unsigned char>>(
                    v16,
                    a3);
  v6 = *v5;
  *v5 = *(_QWORD *)(a1 + 432);
  *(_QWORD *)(a1 + 432) = v6;
  v7 = v5[1];
  v5[1] = *(_QWORD *)(a1 + 440);
  *(_QWORD *)(a1 + 440) = v7;
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 432) + 8LL))(*(_QWORD *)(a1 + 432), 0);
  if ( v9 )
  {
    LOBYTE(v8) = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        2,
        5,
        10,
        &WPP_718a33e7340d3f3cf19b4a88e91c583f_Traceguids);
    }
    if ( v9 >= 0 )
      v9 = (unsigned __int16)v9 | 0x80010000;
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementr"
                    "pcserverclient.cpp",
      (const char *)(unsigned int)v9,
      v15);
  }
  v19 = OpenProcess(0x40u, 0, a2);
  v12 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 432) + 16LL))(*(_QWORD *)(a1 + 432));
  if ( v12 )
  {
    LOBYTE(v11) = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        2,
        5,
        11,
        &WPP_718a33e7340d3f3cf19b4a88e91c583f_Traceguids);
    }
    if ( v12 >= 0 )
      v12 = (unsigned __int16)v12 | 0x80010000;
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagementr"
                    "pcserverclient.cpp",
      (const char *)(unsigned int)v12,
      v15);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    a1 + 424,
    &v19);
  return wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
}

```

## disassembly

```asm
0x180019dec  mov     [rsp+arg_8], rbx
0x180019df1  mov     [rsp+arg_10], rsi
0x180019df6  push    rdi
0x180019df7  sub     rsp, 60h
0x180019dfb  mov     rbx, rdx
0x180019dfe  mov     rsi, rcx
0x180019e01  mov     rdx, r8
0x180019e04  lea     rcx, [rsp+68h+var_18]
0x180019e09  call    ??0?$shared_ptr@V?$OEMSetting@E@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<uchar>> const &)
0x180019e0e  mov     r8, [rax]
0x180019e11  mov     rdx, [rsi+1B0h]
0x180019e18  mov     [rax], rdx
0x180019e1b  mov     [rsi+1B0h], r8
0x180019e22  mov     r8, [rax+8]
0x180019e26  mov     rdx, [rsi+1B8h]
0x180019e2d  mov     [rax+8], rdx
0x180019e31  mov     [rsi+1B8h], r8
0x180019e38  mov     rcx, [rsp+68h+var_10]; this
0x180019e3d  test    rcx, rcx
0x180019e40  jz      short loc_180019E47
0x180019e42  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019e47  mov     rcx, [rsi+1B0h]
0x180019e4e  mov     rax, [rcx]
0x180019e51  xor     edx, edx
0x180019e53  mov     rax, [rax+8]
0x180019e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e5c  mov     edi, eax
0x180019e5e  test    eax, eax
0x180019e60  jz      loc_180019EFA
0x180019e66  lea     rax, WPP_GLOBAL_Control
0x180019e6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e74  cmp     rcx, rax
0x180019e77  jz      short loc_180019E89
0x180019e79  test    byte ptr [rcx+1Ch], 10h
0x180019e7d  jz      short loc_180019E89
0x180019e7f  cmp     byte ptr [rcx+19h], 2
0x180019e83  jb      short loc_180019E89
0x180019e85  mov     dl, 1
0x180019e87  jmp     short loc_180019E8B
0x180019e89  xor     dl, dl; int
0x180019e8b  lea     rax, WPP_RECORDER_INITIALIZED
0x180019e92  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180019e99  setnz   r8b; int
0x180019e9d  test    dl, dl
0x180019e9f  jnz     short loc_180019EA6
0x180019ea1  test    r8b, r8b
0x180019ea4  jz      short loc_180019ED3
0x180019ea6  lea     rax, WPP_718a33e7340d3f3cf19b4a88e91c583f_Traceguids
0x180019ead  mov     [rsp+68h+MessageGuid], rax; MessageGuid
0x180019eb2  mov     [rsp+68h+var_38], 0Ah; __int16
0x180019eb9  mov     [rsp+68h+var_40], 5; int
0x180019ec1  mov     [rsp+68h+var_48], 2; int
0x180019ec6  mov     r9, [rcx+28h]; int
0x180019eca  mov     rcx, [rcx+10h]; int
0x180019ece  call    WPP_RECORDER_AND_TRACE_SF_s
0x180019ed3  test    edi, edi
0x180019ed5  js      short loc_180019EE0
0x180019ed7  movzx   edi, di
0x180019eda  or      edi, 80010000h
0x180019ee0  mov     rcx, [rsp+68h]; this
0x180019ee5  mov     r9d, edi; char *
0x180019ee8  lea     r8, aOnecoreuapDriv_11; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180019eef  mov     edx, 28h ; '('; void *
0x180019ef4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019efa  mov     r8d, ebx; dwProcessId
0x180019efd  xor     edx, edx; bInheritHandle
0x180019eff  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180019f02  call    cs:__imp_OpenProcess
0x180019f08  mov     [rsp+68h+arg_0], rax
0x180019f0d  mov     rcx, [rsi+1B0h]
0x180019f14  mov     rax, [rcx]
0x180019f17  mov     rax, [rax+10h]
0x180019f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f20  mov     ebx, eax
0x180019f22  test    eax, eax
0x180019f24  jz      loc_180019FBE
0x180019f2a  lea     rax, WPP_GLOBAL_Control
0x180019f31  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f38  cmp     rcx, rax
0x180019f3b  jz      short loc_180019F4D
0x180019f3d  test    byte ptr [rcx+1Ch], 10h
0x180019f41  jz      short loc_180019F4D
0x180019f43  cmp     byte ptr [rcx+19h], 2
0x180019f47  jb      short loc_180019F4D
0x180019f49  mov     dl, 1
0x180019f4b  jmp     short loc_180019F4F
0x180019f4d  xor     dl, dl; int
0x180019f4f  lea     rax, WPP_RECORDER_INITIALIZED
0x180019f56  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180019f5d  setnz   r8b; int
0x180019f61  test    dl, dl
0x180019f63  jnz     short loc_180019F6A
0x180019f65  test    r8b, r8b
0x180019f68  jz      short loc_180019F97
0x180019f6a  lea     rax, WPP_718a33e7340d3f3cf19b4a88e91c583f_Traceguids
0x180019f71  mov     [rsp+68h+MessageGuid], rax; MessageGuid
0x180019f76  mov     [rsp+68h+var_38], 0Bh; __int16
0x180019f7d  mov     [rsp+68h+var_40], 5; int
0x180019f85  mov     [rsp+68h+var_48], 2; int
0x180019f8a  mov     r9, [rcx+28h]; int
0x180019f8e  mov     rcx, [rcx+10h]; int
0x180019f92  call    WPP_RECORDER_AND_TRACE_SF_s
0x180019f97  test    ebx, ebx
0x180019f99  js      short loc_180019FA4
0x180019f9b  movzx   ebx, bx
0x180019f9e  or      ebx, 80010000h
0x180019fa4  mov     rcx, [rsp+68h]; this
0x180019fa9  mov     r9d, ebx; char *
0x180019fac  lea     r8, aOnecoreuapDriv_11; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180019fb3  mov     edx, 37h ; '7'; void *
0x180019fb8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019fbe  lea     rcx, [rsi+1A8h]
0x180019fc5  lea     rdx, [rsp+68h+arg_0]
0x180019fca  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180019fcf  nop
0x180019fd0  lea     rcx, [rsp+68h+arg_0]
0x180019fd5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180019fda  lea     r11, [rsp+68h+var_8]
0x180019fdf  mov     rbx, [r11+18h]
0x180019fe3  mov     rsi, [r11+20h]
0x180019fe7  mov     rsp, r11
0x180019fea  pop     rdi
0x180019feb  retn
```
