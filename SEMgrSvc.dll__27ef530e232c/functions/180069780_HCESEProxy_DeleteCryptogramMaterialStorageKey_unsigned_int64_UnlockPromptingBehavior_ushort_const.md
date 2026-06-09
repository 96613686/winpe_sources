# HCESEProxy::DeleteCryptogramMaterialStorageKey(unsigned __int64,UnlockPromptingBehavior,ushort const *)

- ea: `0x180069780`
- end: `0x1800699bd`
- name: `?DeleteCryptogramMaterialStorageKey@HCESEProxy@@UEAAJ_KW4UnlockPromptingBehavior@@PEBG@Z`
- size: `573`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1800049a0`
- `0x1800127c0`
- `0x180013274`
- `0x1800436c0`
- `0x180047f88`
- `0x1800480dc`
- `0x18004830c`
- `0x180048aac`
- `0x18004bf9c`
- `0x180069780`
- `0x18009d010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient2` at `0x1800697f7`
- `RPCRT4!RpcImpersonateClient2` at `0x1800697f7`
- `RPCRT4!RpcRevertToSelfEx` at `0x18006981c`
- `RPCRT4!RpcRevertToSelfEx` at `0x180069827`
- `RPCRT4!RpcRevertToSelfEx` at `0x18006981c`
- `RPCRT4!RpcRevertToSelfEx` at `0x180069827`

## string_xrefs

- `0x18006990b`: `Device Castle failed to delete the Cryptogram Material Storage Key '%2!s!' for user %1!s!.  The error code was %3!#08I32x!.`
- `0x18006988c`: `DeviceCastle::Library::DeviceCastleProvider::DeleteCryptogramMaterialStorageKey`
- `0x1800697ac`: `HCESecureElement::DeleteCryptogramMaterialStorageKey`
- `0x180069926`: `HCESecureElement::DeleteCryptogramMaterialStorageKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HCESEProxy::DeleteCryptogramMaterialStorageKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4)
{
  int v5; // esi
  _QWORD *v7; // rcx
  RPC_STATUS v8; // ebx
  __int64 v9; // r8
  DeviceCastle::Library::DeviceCastleInternal *v10; // rdi
  _QWORD *v11; // rdx
  unsigned int v12; // esi
  const wchar_t *v13; // r14
  _QWORD *v14; // rax
  _QWORD v16[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+60h] [rbp-A0h]
  int v18; // [rsp+64h] [rbp-9Ch]
  const wchar_t *v19; // [rsp+68h] [rbp-98h]
  _QWORD *v20; // [rsp+78h] [rbp-88h]
  _QWORD v21[4]; // [rsp+80h] [rbp-80h] BYREF
  char v22[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v23[32]; // [rsp+C0h] [rbp-40h] BYREF
  char v24[32]; // [rsp+E0h] [rbp-20h] BYREF
  char v25[32]; // [rsp+100h] [rbp+0h] BYREF
  char v26[32]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v27; // [rsp+140h] [rbp+40h] BYREF
  RPC_STATUS v28; // [rsp+148h] [rbp+48h]
  const wchar_t *v29; // [rsp+150h] [rbp+50h]
  __int64 v30; // [rsp+158h] [rbp+58h]

  v5 = a3;
  if ( (byte_180132D81 & 0x10) != 0 )
  {
    v29 = L"HCESecureElement::DeleteCryptogramMaterialStorageKey";
    v30 = 106;
    McGenEventWrite_EventWriteTransfer(a1, ")#", a3, 2, &v27);
  }
  DeviceCastle::Library::CallerIdentity::CallerIdentity((DeviceCastle::Library::CallerIdentity *)v21);
  v27 = 0;
  v8 = RpcImpersonateClient2(0);
  v28 = v8;
  if ( v8 >= 0 )
  {
    v8 = DeviceCastle::Library::CallerIdentity::DetermineCallerIdentity((DeviceCastle::Library::CallerIdentity *)v21);
    if ( v8 < 0 )
    {
      RpcRevertToSelfEx(0);
      goto LABEL_21;
    }
    RpcRevertToSelfEx(0);
    v10 = qword_18012F408;
    if ( qword_18012F408 )
    {
      v16[0] = off_1800A0170;
      v16[1] = &off_18012F400;
      v16[2] = v21;
      v16[3] = a2;
      v17 = v5;
      v18 = HIDWORD(v30);
      v19 = a4;
      v20 = v16;
      v8 = DeviceCastle::Library::Internal::Utilities::TranslateExceptions(
             L"DeviceCastle::Library::DeviceCastleProvider::DeleteCryptogramMaterialStorageKey",
             v21,
             v16);
      v7 = v20;
      if ( v20 )
      {
        v11 = v16;
        LOBYTE(v11) = v20 != v16;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v20 + 32LL))(v20, v11);
      }
      if ( v8 >= 0 )
      {
        v8 = 0;
        goto LABEL_21;
      }
      v10 = qword_18012F408;
    }
    else
    {
      v8 = -2147024882;
    }
    if ( v10 )
    {
      v12 = 2;
      if ( v8 == -2134834658 )
        v12 = 4;
      v13 = L"<null>";
      if ( a4 )
        v13 = a4;
      v14 = DeviceCastle::Library::CallerIdentity::Username(v21);
      if ( v14[3] > 7u )
        v14 = (_QWORD *)*v14;
      DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(
        v10,
        v12,
        (struct DeviceCastle::Library::CallerIdentity *)v21,
        L"Device Castle failed to delete the Cryptogram Material Storage Key '%2!s!' for user %1!s!.  The error code was %3!#08I32x!.",
        v14,
        v13,
        v8);
    }
  }
LABEL_21:
  if ( (byte_180132D81 & 0x10) != 0 )
  {
    v29 = L"HCESecureElement::DeleteCryptogramMaterialStorageKey";
    v30 = 106;
    McGenEventWrite_EventWriteTransfer(v7, "*#", v9, 2, &v27);
  }
  std::wstring::~wstring(v26);
  std::wstring::~wstring(v25);
  std::wstring::~wstring(v24);
  std::wstring::~wstring(v23);
  std::wstring::~wstring(v22);
  v21[0] = &DeviceCastle::Library::Blob::`vftable';
  DeviceCastle::Library::Blob::Clear((DeviceCastle::Library::Blob *)v21);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180069780  push    rbp
0x180069782  push    rbx
0x180069783  push    rsi
0x180069784  push    rdi
0x180069785  push    r14
0x180069787  push    r15
0x180069789  lea     rbp, [rsp-78h]
0x18006978e  sub     rsp, 178h
0x180069795  mov     rax, cs:__security_cookie
0x18006979c  xor     rax, rsp
0x18006979f  mov     [rbp+0A0h+var_38], rax
0x1800697a3  mov     r15, r9
0x1800697a6  mov     esi, r8d
0x1800697a9  mov     r14, rdx
0x1800697ac  lea     rdi, aHcesecureeleme_0; "HCESecureElement::DeleteCryptogramMater"...
0x1800697b3  test    cs:byte_180132D81, 10h
0x1800697ba  jz      short loc_1800697E3
0x1800697bc  mov     [rbp+0A0h+var_50], rdi
0x1800697c0  mov     [rbp+0A0h+var_48], 6Ah ; 'j'
0x1800697c8  lea     rax, [rbp+0A0h+var_60]
0x1800697cc  mov     [rsp+1A0h+var_180], rax
0x1800697d1  mov     r9d, 2
0x1800697d7  lea     rdx, SEMgr_Event_COM_API_Start; ")#"
0x1800697de  call    McGenEventWrite_EventWriteTransfer
0x1800697e3  lea     rcx, [rbp+0A0h+var_120]; this
0x1800697e7  call    ??0CallerIdentity@Library@DeviceCastle@@QEAA@XZ; DeviceCastle::Library::CallerIdentity::CallerIdentity(void)
0x1800697ec  nop
0x1800697ed  mov     [rbp+0A0h+var_60], 0
0x1800697f5  xor     ecx, ecx; BindingHandle
0x1800697f7  call    cs:__imp_RpcImpersonateClient2
0x1800697fd  mov     ebx, eax
0x1800697ff  mov     [rbp+0A0h+var_58], eax
0x180069802  test    eax, eax
0x180069804  jns     short loc_18006980B
0x180069806  jmp     loc_18006992D
0x18006980b  lea     rcx, [rbp+0A0h+var_120]; this
0x18006980f  call    ?DetermineCallerIdentity@CallerIdentity@Library@DeviceCastle@@QEAAJXZ; DeviceCastle::Library::CallerIdentity::DetermineCallerIdentity(void)
0x180069814  mov     ebx, eax
0x180069816  xor     ecx, ecx; BindingHandle
0x180069818  test    eax, eax
0x18006981a  jns     short loc_180069827
0x18006981c  call    cs:__imp_RpcRevertToSelfEx
0x180069822  jmp     loc_18006992D
0x180069827  call    cs:__imp_RpcRevertToSelfEx
0x18006982d  mov     rdi, cs:qword_18012F408
0x180069834  test    rdi, rdi
0x180069837  jnz     short loc_180069843
0x180069839  mov     ebx, 8007000Eh
0x18006983e  jmp     loc_1800698C6
0x180069843  lea     rax, off_1800A0170
0x18006984a  mov     [rsp+1A0h+var_160], rax
0x18006984f  lea     rax, off_18012F400
0x180069856  mov     [rsp+1A0h+var_158], rax
0x18006985b  lea     rax, [rbp+0A0h+var_120]
0x18006985f  mov     [rsp+1A0h+var_150], rax
0x180069864  mov     [rsp+1A0h+var_148], r14
0x180069869  mov     [rsp+1A0h+var_140], esi
0x18006986d  mov     eax, dword ptr [rbp+0A0h+var_48+4]
0x180069870  mov     [rsp+1A0h+var_13C], eax
0x180069874  mov     [rsp+1A0h+var_138], r15
0x180069879  lea     rax, [rsp+1A0h+var_160]
0x18006987e  mov     [rsp+1A0h+var_128], rax
0x180069883  lea     r8, [rsp+1A0h+var_160]
0x180069888  lea     rdx, [rbp+0A0h+var_120]
0x18006988c  lea     rcx, aDevicecastleLi_13; "DeviceCastle::Library::DeviceCastleProv"...
0x180069893  call    ?TranslateExceptions@Utilities@Internal@Library@DeviceCastle@@SAJPEBGPEAVCallerIdentity@34@AEBV?$function@$$A6AJXZ@std@@@Z; DeviceCastle::Library::Internal::Utilities::TranslateExceptions(ushort const *,DeviceCastle::Library::CallerIdentity *,std::function<long (void)> const &)
0x180069898  mov     ebx, eax
0x18006989a  mov     rcx, [rsp+1A0h+var_128]
0x18006989f  test    rcx, rcx
0x1800698a2  jz      short loc_1800698BB
0x1800698a4  mov     rax, [rcx]
0x1800698a7  lea     rdx, [rsp+1A0h+var_160]
0x1800698ac  cmp     rcx, rdx
0x1800698af  setnz   dl
0x1800698b2  mov     rax, [rax+20h]
0x1800698b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698bb  test    ebx, ebx
0x1800698bd  jns     short loc_180069924
0x1800698bf  mov     rdi, cs:qword_18012F408
0x1800698c6  test    rdi, rdi
0x1800698c9  jz      short loc_180069926
0x1800698cb  mov     esi, 2
0x1800698d0  lea     eax, [rsi+2]
0x1800698d3  cmp     ebx, 80C1021Eh
0x1800698d9  cmovz   esi, eax
0x1800698dc  lea     r14, aNull_0; "<null>"
0x1800698e3  test    r15, r15
0x1800698e6  cmovnz  r14, r15
0x1800698ea  lea     rcx, [rbp+0A0h+var_120]
0x1800698ee  call    ?Username@CallerIdentity@Library@DeviceCastle@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceCastle::Library::CallerIdentity::Username(void)
0x1800698f3  cmp     qword ptr [rax+18h], 7
0x1800698f8  jbe     short loc_1800698FD
0x1800698fa  mov     rax, [rax]
0x1800698fd  mov     [rsp+1A0h+var_170], ebx
0x180069901  mov     [rsp+1A0h+var_178], r14
0x180069906  mov     [rsp+1A0h+var_180], rax
0x18006990b  lea     r9, aDeviceCastleFa_10; "Device Castle failed to delete the Cryp"...
0x180069912  lea     r8, [rbp+0A0h+var_120]; struct DeviceCastle::Library::CallerIdentity *
0x180069916  mov     edx, esi; unsigned int
0x180069918  mov     rcx, rdi; this
0x18006991b  call    ?LogFormattedMessage@DeviceCastleInternal@Library@DeviceCastle@@QEBAXKPEAVCallerIdentity@23@PEBGZZ; DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(ulong,DeviceCastle::Library::CallerIdentity *,ushort const *,...)
0x180069920  test    ebx, ebx
0x180069922  js      short loc_180069926
0x180069924  xor     ebx, ebx
0x180069926  lea     rdi, aHcesecureeleme_0; "HCESecureElement::DeleteCryptogramMater"...
0x18006992d  test    cs:byte_180132D81, 10h
0x180069934  jz      short loc_18006995E
0x180069936  mov     [rbp+0A0h+var_50], rdi
0x18006993a  mov     [rbp+0A0h+var_48], 6Ah ; 'j'
0x180069942  lea     rax, [rbp+0A0h+var_60]
0x180069946  mov     [rsp+1A0h+var_180], rax
0x18006994b  mov     r9d, 2
0x180069951  lea     rdx, SEMgr_Event_COM_API_End; "*#"
0x180069958  call    McGenEventWrite_EventWriteTransfer
0x18006995d  nop
0x18006995e  lea     rcx, [rbp+0A0h+var_80]
0x180069962  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069967  lea     rcx, [rbp+0A0h+var_A0]
0x18006996b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069970  lea     rcx, [rbp+0A0h+var_C0]
0x180069974  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069979  lea     rcx, [rbp+0A0h+var_E0]
0x18006997d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069982  lea     rcx, [rbp+0A0h+var_100]
0x180069986  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006998b  lea     rax, ??_7Blob@Library@DeviceCastle@@6B@; const DeviceCastle::Library::Blob::`vftable'
0x180069992  mov     [rbp+0A0h+var_120], rax
0x180069996  lea     rcx, [rbp+0A0h+var_120]; this
0x18006999a  call    ?Clear@Blob@Library@DeviceCastle@@UEAAXXZ; DeviceCastle::Library::Blob::Clear(void)
0x18006999f  mov     eax, ebx
0x1800699a1  mov     rcx, [rbp+0A0h+var_38]
0x1800699a5  xor     rcx, rsp; StackCookie
0x1800699a8  call    __security_check_cookie
0x1800699ad  add     rsp, 178h
0x1800699b4  pop     r15
0x1800699b6  pop     r14
0x1800699b8  pop     rdi
0x1800699b9  pop     rsi
0x1800699ba  pop     rbx
0x1800699bb  pop     rbp
0x1800699bc  retn
```
