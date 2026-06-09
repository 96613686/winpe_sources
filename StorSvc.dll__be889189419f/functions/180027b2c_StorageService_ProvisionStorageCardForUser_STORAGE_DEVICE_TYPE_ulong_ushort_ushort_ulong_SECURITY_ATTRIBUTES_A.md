# StorageService::ProvisionStorageCardForUser(_STORAGE_DEVICE_TYPE,ulong,ushort *,ushort *,ulong,_SECURITY_ATTRIBUTES *,_ACL *)

- ea: `0x180027b2c`
- end: `0x180027e52`
- name: `?ProvisionStorageCardForUser@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAG1KPEAU_SECURITY_ATTRIBUTES@@PEAU_ACL@@@Z`
- size: `806`
- prototype: `__int64 __fastcall(StorageService *, int, unsigned int, __int64, __int64, int, struct _SECURITY_ATTRIBUTES *, struct _ACL *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002a3f8`

## callees

- `0x18000231c`
- `0x18000d030`
- `0x180019d4c`
- `0x18001c130`
- `0x18001c208`
- `0x18001dcf4`
- `0x18001ee68`
- `0x1800203c0`
- `0x180020450`
- `0x180027b2c`
- `0x18002ce80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027d0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027d0f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180027d25`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180027d25`
- `RPCRT4!RpcRevertToSelf` at `0x180027d62`
- `RPCRT4!RpcRevertToSelf` at `0x180027d62`
- `RPCRT4!RpcImpersonateClient` at `0x180027d35`
- `RPCRT4!RpcImpersonateClient` at `0x180027d35`

## pseudocode

```c
__int64 __fastcall StorageService::ProvisionStorageCardForUser(
        StorageService *a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        struct _SECURITY_ATTRIBUTES *a7,
        struct _ACL *a8)
{
  __int64 v9; // r12
  __int64 v10; // r15
  int StorageCardDirectory; // ebx
  unsigned int v12; // esi
  int v13; // eax
  wchar_t *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // rax
  wchar_t *v21; // rdx
  __int64 v22; // r8
  HANDLE CurrentThread; // rax
  const unsigned __int16 *v24; // rax
  StorageService *v25; // rcx
  const unsigned __int16 *v26; // r8
  const WCHAR *v27; // rax
  signed int LastError; // eax
  StorageService *v30; // [rsp+50h] [rbp-A1h] BYREF
  struct _SECURITY_ATTRIBUTES *v31; // [rsp+58h] [rbp-99h] BYREF
  struct _ACL *v32; // [rsp+60h] [rbp-91h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-89h] BYREF
  const WCHAR *v34; // [rsp+70h] [rbp-81h] BYREF
  __int64 v35; // [rsp+78h] [rbp-79h] BYREF
  __int128 v36; // [rsp+80h] [rbp-71h] BYREF
  __int64 v37; // [rsp+90h] [rbp-61h]
  __int64 v38; // [rsp+98h] [rbp-59h]
  _OWORD v39[2]; // [rsp+A0h] [rbp-51h] BYREF
  __int128 v40; // [rsp+C0h] [rbp-31h] BYREF
  __m128i si128; // [rsp+D0h] [rbp-21h]

  v9 = a3;
  v10 = a2;
  v30 = a1;
  v31 = a7;
  v32 = a8;
  StorageCardDirectory = 0;
  v36 = 0;
  v37 = 0;
  v38 = 7;
  LOWORD(v36) = 0;
  v40 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v40) = 0;
  v39[0] = 0;
  v39[1] = si128;
  LOWORD(v39[0]) = 0;
  TokenHandle = 0;
  v12 = 0;
  v13 = a6;
  while ( 1 )
  {
    if ( (v13 & *((_DWORD *)&off_18008E4B0 + 4 * v12 + 3)) == 0 )
      goto LABEL_11;
    std::wstring::assign(&v36, a5);
    std::wstring::_Append<unsigned short>(&v36, L"\\", 1);
    v14 = (&off_18008E4B0)[2 * v12];
    v15 = -1;
    do
      ++v15;
    while ( v14[v15] );
    std::wstring::_Append<unsigned short>(&v36, v14, v15);
    v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v36);
    StorageCardDirectory = StorageService::CreateStorageCardDirectory(
                             v30,
                             v10,
                             v9,
                             v16,
                             *((_DWORD *)&off_18008E4B0 + 4 * v12 + 2),
                             v31,
                             v32,
                             1);
    if ( StorageCardDirectory < 0 )
      break;
    std::wstring::assign(&v40, *((_QWORD *)v30 + v10 + 5) + 4LL + 1112 * v9);
    v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v36);
    std::wstring::_Append<unsigned short>(&v40, v20, v37);
    std::wstring::assign(v39, a4);
    std::wstring::_Append<unsigned short>(v39, L"\\", 1);
    v21 = (&off_18008E4B0)[2 * v12];
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    std::wstring::_Append<unsigned short>(v39, v21, v22);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      StorageCardDirectory = LastError;
      goto LABEL_17;
    }
    StorageCardDirectory = RpcImpersonateClient(0);
    if ( StorageCardDirectory < 0 )
      goto LABEL_17;
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v40);
    v24 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39);
    StorageService::CreateDesktopIni(v25, v24, v26);
    RpcRevertToSelf();
    v13 = a6;
LABEL_11:
    if ( ++v12 >= 7 )
      goto LABEL_17;
  }
  if ( (unsigned int)dword_1800BF000 > 5 )
  {
    LODWORD(v31) = StorageCardDirectory;
    v27 = &word_180092AF0;
    if ( !a4 )
      v27 = 0;
    v34 = v27;
    v35 = a5;
    LODWORD(v32) = v9;
    LODWORD(v30) = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)byte_1800A6B69,
      v18,
      v19,
      (__int64)&v30,
      (__int64)&v32,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v31);
  }
LABEL_17:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  std::wstring::_Tidy_deallocate(v39);
  std::wstring::_Tidy_deallocate(&v40);
  std::wstring::_Tidy_deallocate(&v36);
  return (unsigned int)StorageCardDirectory;
}

```

## disassembly

```asm
0x180027b2c  push    rbp
0x180027b2e  push    rbx
0x180027b2f  push    rsi
0x180027b30  push    rdi
0x180027b31  push    r12
0x180027b33  push    r13
0x180027b35  push    r14
0x180027b37  push    r15
0x180027b39  lea     rbp, [rsp-7]
0x180027b3e  sub     rsp, 0F8h
0x180027b45  mov     rax, cs:__security_cookie
0x180027b4c  xor     rax, rsp
0x180027b4f  mov     [rbp+3Fh+var_50], rax
0x180027b53  mov     r14, r9
0x180027b56  mov     r12d, r8d
0x180027b59  movsxd  r15, edx
0x180027b5c  mov     [rsp+130h+var_E0], rcx
0x180027b61  mov     r13, [rbp+3Fh+arg_20]
0x180027b65  mov     rax, [rbp+3Fh+arg_30]
0x180027b69  mov     [rsp+130h+var_D8], rax
0x180027b6e  mov     rax, [rbp+3Fh+arg_38]
0x180027b75  mov     [rsp+130h+var_D0], rax
0x180027b7a  xor     ecx, ecx
0x180027b7c  mov     ebx, ecx
0x180027b7e  xorps   xmm0, xmm0
0x180027b81  movups  [rbp+3Fh+var_B0], xmm0
0x180027b85  mov     [rbp+3Fh+var_A0], rcx
0x180027b89  mov     [rbp+3Fh+var_98], rcx
0x180027b8d  mov     [rbp+3Fh+var_A0], rcx
0x180027b91  mov     [rbp+3Fh+var_98], 7
0x180027b99  mov     word ptr [rbp+3Fh+var_B0], cx
0x180027b9d  movups  [rbp+3Fh+var_70], xmm0
0x180027ba1  xorps   xmm1, xmm1
0x180027ba4  movdqu  [rbp+3Fh+var_60], xmm1
0x180027ba9  movdqa  xmm2, cs:__xmm@00000000000000070000000000000000
0x180027bb1  movdqu  [rbp+3Fh+var_60], xmm2
0x180027bb6  mov     word ptr [rbp+3Fh+var_70], cx
0x180027bba  movups  [rbp+3Fh+var_90], xmm0
0x180027bbe  movdqu  [rbp+3Fh+var_80], xmm1
0x180027bc3  movdqu  [rbp+3Fh+var_80], xmm2
0x180027bc8  mov     word ptr [rbp+3Fh+var_90], cx
0x180027bcc  mov     [rsp+130h+TokenHandle], rcx
0x180027bd1  mov     esi, ecx
0x180027bd3  lea     rcx, off_18008E4B0; "Music"
0x180027bda  mov     eax, [rbp+3Fh+arg_28]
0x180027bdd  mov     edi, esi
0x180027bdf  add     rdi, rdi
0x180027be2  test    [rcx+rdi*8+0Ch], eax
0x180027be6  jz      loc_180027D72
0x180027bec  mov     rdx, r13
0x180027bef  lea     rcx, [rbp+3Fh+var_B0]
0x180027bf3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180027bf8  mov     ebx, 1
0x180027bfd  mov     r8d, ebx
0x180027c00  lea     rdx, asc_180092790; "\\"
0x180027c07  lea     rcx, [rbp+3Fh+var_B0]
0x180027c0b  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180027c10  lea     rdx, off_18008E4B0; "Music"
0x180027c17  mov     rdx, [rdx+rdi*8]
0x180027c1b  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027c1f  xor     eax, eax
0x180027c21  inc     r8
0x180027c24  cmp     [rdx+r8*2], ax
0x180027c29  jnz     short loc_180027C21
0x180027c2b  lea     rcx, [rbp+3Fh+var_B0]
0x180027c2f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180027c34  lea     rcx, [rbp+3Fh+var_B0]
0x180027c38  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180027c3d  mov     r9, rax
0x180027c40  mov     dword ptr [rsp+130h+var_F8], ebx
0x180027c44  mov     rax, [rsp+130h+var_D0]
0x180027c49  mov     [rsp+130h+var_100], rax
0x180027c4e  mov     rax, [rsp+130h+var_D8]
0x180027c53  mov     [rsp+130h+var_108], rax
0x180027c58  lea     rax, off_18008E4B0; "Music"
0x180027c5f  mov     eax, [rax+rdi*8+8]
0x180027c63  mov     dword ptr [rsp+130h+var_110], eax
0x180027c67  mov     r8d, r12d
0x180027c6a  mov     edx, r15d
0x180027c6d  mov     rcx, [rsp+130h+var_E0]
0x180027c72  call    ?CreateStorageCardDirectory@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEBGKPEAU_SECURITY_ATTRIBUTES@@PEAU_ACL@@H@Z; StorageService::CreateStorageCardDirectory(_STORAGE_DEVICE_TYPE,ulong,ushort const *,ulong,_SECURITY_ATTRIBUTES *,_ACL *,int)
0x180027c77  mov     ebx, eax
0x180027c79  test    eax, eax
0x180027c7b  js      loc_180027D81
0x180027c81  imul    rdx, r12, 458h
0x180027c88  mov     rax, [rsp+130h+var_E0]
0x180027c8d  mov     rax, [rax+r15*8+28h]
0x180027c92  add     rax, 4
0x180027c96  add     rdx, rax
0x180027c99  lea     rcx, [rbp+3Fh+var_70]
0x180027c9d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180027ca2  lea     rcx, [rbp+3Fh+var_B0]
0x180027ca6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180027cab  mov     rdx, rax
0x180027cae  mov     r8, [rbp+3Fh+var_A0]
0x180027cb2  lea     rcx, [rbp+3Fh+var_70]
0x180027cb6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180027cbb  mov     rdx, r14
0x180027cbe  lea     rcx, [rbp+3Fh+var_90]
0x180027cc2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180027cc7  mov     ebx, 1
0x180027ccc  mov     r8d, ebx
0x180027ccf  lea     rdx, asc_180092790; "\\"
0x180027cd6  lea     rcx, [rbp+3Fh+var_90]
0x180027cda  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180027cdf  lea     rax, off_18008E4B0; "Music"
0x180027ce6  mov     rdx, [rax+rdi*8]
0x180027cea  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027cee  xor     edi, edi
0x180027cf0  inc     r8
0x180027cf3  cmp     [rdx+r8*2], di
0x180027cf8  jnz     short loc_180027CF0
0x180027cfa  lea     rcx, [rbp+3Fh+var_90]
0x180027cfe  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180027d03  xor     edx, edx
0x180027d05  lea     rcx, [rsp+130h+TokenHandle]
0x180027d0a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180027d0f  call    cs:__imp_GetCurrentThread
0x180027d15  lea     r9, [rsp+130h+TokenHandle]; TokenHandle
0x180027d1a  mov     r8d, ebx; OpenAsSelf
0x180027d1d  mov     edx, 0Ch; DesiredAccess
0x180027d22  mov     rcx, rax; ThreadHandle
0x180027d25  call    cs:__imp_OpenThreadToken
0x180027d2b  test    eax, eax
0x180027d2d  jnz     loc_180027E3B
0x180027d33  xor     ecx, ecx; BindingHandle
0x180027d35  call    cs:__imp_RpcImpersonateClient
0x180027d3b  mov     ebx, eax
0x180027d3d  test    eax, eax
0x180027d3f  js      loc_180027E39
0x180027d45  lea     rcx, [rbp+3Fh+var_70]
0x180027d49  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180027d4e  mov     r8, rax
0x180027d51  lea     rcx, [rbp+3Fh+var_90]
0x180027d55  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180027d5a  mov     rdx, rax; unsigned __int16 *
0x180027d5d  call    ?CreateDesktopIni@StorageService@@IEAAXPEBG0@Z; StorageService::CreateDesktopIni(ushort const *,ushort const *)
0x180027d62  call    cs:__imp_RpcRevertToSelf
0x180027d68  mov     eax, [rbp+3Fh+arg_28]
0x180027d6b  lea     rcx, off_18008E4B0; "Music"
0x180027d72  inc     esi
0x180027d74  cmp     esi, 7
0x180027d77  jb      loc_180027BDD
0x180027d7d  test    ebx, ebx
0x180027d7f  jns     short loc_180027DEF
0x180027d81  mov     eax, cs:dword_1800BF000
0x180027d87  cmp     eax, 5
0x180027d8a  jbe     short loc_180027DEF
0x180027d8c  mov     dword ptr [rsp+130h+var_D8], ebx
0x180027d90  lea     rax, word_180092AF0
0x180027d97  test    r14, r14
0x180027d9a  cmovz   rax, r14
0x180027d9e  mov     [rsp+130h+var_C0], rax
0x180027da3  mov     [rbp+3Fh+var_B8], r13
0x180027da7  mov     dword ptr [rsp+130h+var_D0], r12d
0x180027dac  mov     dword ptr [rsp+130h+var_E0], r15d
0x180027db1  lea     rax, [rsp+130h+var_D8]
0x180027db6  mov     [rsp+130h+var_F0], rax
0x180027dbb  lea     rax, [rsp+130h+var_C0]
0x180027dc0  mov     [rsp+130h+var_F8], rax
0x180027dc5  lea     rax, [rbp+3Fh+var_B8]
0x180027dc9  mov     [rsp+130h+var_100], rax
0x180027dce  lea     rax, [rsp+130h+var_D0]
0x180027dd3  mov     [rsp+130h+var_108], rax
0x180027dd8  lea     rax, [rsp+130h+var_E0]
0x180027ddd  mov     [rsp+130h+var_110], rax
0x180027de2  lea     rdx, byte_1800A6B69
0x180027de9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180027dee  nop
0x180027def  lea     rcx, [rsp+130h+TokenHandle]
0x180027df4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180027df9  nop
0x180027dfa  lea     rcx, [rbp+3Fh+var_90]
0x180027dfe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027e03  nop
0x180027e04  lea     rcx, [rbp+3Fh+var_70]
0x180027e08  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027e0d  nop
0x180027e0e  lea     rcx, [rbp+3Fh+var_B0]
0x180027e12  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027e17  mov     eax, ebx
0x180027e19  mov     rcx, [rbp+3Fh+var_50]
0x180027e1d  xor     rcx, rsp; StackCookie
0x180027e20  call    __security_check_cookie
0x180027e25  add     rsp, 0F8h
0x180027e2c  pop     r15
0x180027e2e  pop     r14
0x180027e30  pop     r13
0x180027e32  pop     r12
0x180027e34  pop     rdi
0x180027e35  pop     rsi
0x180027e36  pop     rbx
0x180027e37  pop     rbp
0x180027e38  retn
0x180027e39  jmp     short loc_180027DEF
0x180027e3b  call    cs:__imp_GetLastError
0x180027e41  test    eax, eax
0x180027e43  jle     short loc_180027E4D
0x180027e45  movzx   eax, ax
0x180027e48  or      eax, 80070000h
0x180027e4d  mov     ebx, eax
0x180027e4f  jmp     short loc_180027DEF
```
