# HCESEProxy::CreateCryptogramMaterialStorageKey(unsigned __int64,UnlockPromptingBehavior,ushort const *,CryptogramStorageKeyAlgorithm,CryptogramStorageKeyCapabilities)

- ea: `0x1800692f0`
- end: `0x180069549`
- name: `?CreateCryptogramMaterialStorageKey@HCESEProxy@@UEAAJ_KW4UnlockPromptingBehavior@@PEBGW4CryptogramStorageKeyAlgorithm@@W4CryptogramStorageKeyCapabilities@@@Z`
- size: `601`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation`

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
- `0x1800692f0`
- `0x18009d010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient2` at `0x180069370`
- `RPCRT4!RpcImpersonateClient2` at `0x180069370`
- `RPCRT4!RpcRevertToSelfEx` at `0x180069395`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800693a0`
- `RPCRT4!RpcRevertToSelfEx` at `0x180069395`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800693a0`

## string_xrefs

- `0x180069419`: `DeviceCastle::Library::DeviceCastleProvider::CreateCryptogramMaterialStorageKey`
- `0x180069491`: `Device Castle failed to create the Cryptogram Material Storage Key '%2!s!' for user %1!s!.  The error code was %3!#08I32x!.`
- `0x180069325`: `HCESecureElement::CreateCryptogramMaterialStorageKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HCESEProxy::CreateCryptogramMaterialStorageKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        int a5,
        int a6)
{
  int v7; // esi
  _QWORD *v9; // rcx
  RPC_STATUS v10; // ebx
  __int64 v11; // r8
  DeviceCastle::Library::DeviceCastleInternal *v12; // rdi
  _QWORD *v13; // rdx
  const wchar_t *v14; // r14
  _QWORD *v15; // rax
  _QWORD v17[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+60h] [rbp-A0h]
  int v19; // [rsp+64h] [rbp-9Ch]
  const wchar_t *v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+74h] [rbp-8Ch]
  _QWORD *v23; // [rsp+78h] [rbp-88h]
  _QWORD v24[4]; // [rsp+80h] [rbp-80h] BYREF
  char v25[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v26[32]; // [rsp+C0h] [rbp-40h] BYREF
  char v27[32]; // [rsp+E0h] [rbp-20h] BYREF
  char v28[32]; // [rsp+100h] [rbp+0h] BYREF
  char v29[32]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v30; // [rsp+140h] [rbp+40h] BYREF
  RPC_STATUS v31; // [rsp+148h] [rbp+48h]
  const wchar_t *v32; // [rsp+150h] [rbp+50h]
  __int64 v33; // [rsp+158h] [rbp+58h]

  v7 = a3;
  if ( (byte_180132D81 & 0x10) != 0 )
  {
    v32 = L"HCESecureElement::CreateCryptogramMaterialStorageKey";
    v33 = 106;
    McGenEventWrite_EventWriteTransfer(a1, ")#", a3, 2, &v30);
  }
  DeviceCastle::Library::CallerIdentity::CallerIdentity((DeviceCastle::Library::CallerIdentity *)v24);
  v30 = 0;
  v10 = RpcImpersonateClient2(0);
  v31 = v10;
  if ( v10 >= 0 )
  {
    v10 = DeviceCastle::Library::CallerIdentity::DetermineCallerIdentity((DeviceCastle::Library::CallerIdentity *)v24);
    if ( v10 < 0 )
    {
      RpcRevertToSelfEx(0);
      goto LABEL_19;
    }
    RpcRevertToSelfEx(0);
    v12 = qword_18012F408;
    if ( qword_18012F408 )
    {
      v17[0] = off_1800A0110;
      v17[1] = &off_18012F400;
      v17[2] = v24;
      v17[3] = a2;
      v18 = v7;
      v19 = HIDWORD(v33);
      v20 = a4;
      v21 = a5;
      v22 = a6;
      v23 = v17;
      v10 = DeviceCastle::Library::Internal::Utilities::TranslateExceptions(
              L"DeviceCastle::Library::DeviceCastleProvider::CreateCryptogramMaterialStorageKey",
              v24,
              v17);
      v9 = v23;
      if ( v23 )
      {
        v13 = v17;
        LOBYTE(v13) = v23 != v17;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v23 + 32LL))(v23, v13);
      }
      if ( v10 >= 0 )
      {
        v10 = 0;
        goto LABEL_19;
      }
      v12 = qword_18012F408;
    }
    else
    {
      v10 = -2147024882;
    }
    if ( v12 )
    {
      v14 = L"<null>";
      if ( a4 )
        v14 = a4;
      v15 = DeviceCastle::Library::CallerIdentity::Username(v24);
      if ( v15[3] > 7u )
        v15 = (_QWORD *)*v15;
      DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(
        v12,
        4 - (v10 != -2134834654),
        (struct DeviceCastle::Library::CallerIdentity *)v24,
        L"Device Castle failed to create the Cryptogram Material Storage Key '%2!s!' for user %1!s!.  The error code was %3!#08I32x!.",
        v15,
        v14,
        v10);
    }
  }
LABEL_19:
  if ( (byte_180132D81 & 0x10) != 0 )
  {
    v32 = L"HCESecureElement::CreateCryptogramMaterialStorageKey";
    v33 = 106;
    McGenEventWrite_EventWriteTransfer(v9, "*#", v11, 2, &v30);
  }
  std::wstring::~wstring(v29);
  std::wstring::~wstring(v28);
  std::wstring::~wstring(v27);
  std::wstring::~wstring(v26);
  std::wstring::~wstring(v25);
  v24[0] = &DeviceCastle::Library::Blob::`vftable';
  DeviceCastle::Library::Blob::Clear((DeviceCastle::Library::Blob *)v24);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800692f0  mov     [rsp-8+arg_0], rbx
0x1800692f5  mov     [rsp-8+arg_8], rsi
0x1800692fa  push    rbp
0x1800692fb  push    rdi
0x1800692fc  push    r13
0x1800692fe  push    r14
0x180069300  push    r15
0x180069302  lea     rbp, [rsp-80h]
0x180069307  sub     rsp, 180h
0x18006930e  mov     rax, cs:__security_cookie
0x180069315  xor     rax, rsp
0x180069318  mov     [rbp+0A0h+var_30], rax
0x18006931c  mov     r15, r9
0x18006931f  mov     esi, r8d
0x180069322  mov     r14, rdx
0x180069325  lea     r13, aHcesecureeleme_6; "HCESecureElement::CreateCryptogramMater"...
0x18006932c  test    cs:byte_180132D81, 10h
0x180069333  jz      short loc_18006935C
0x180069335  mov     [rbp+0A0h+var_50], r13
0x180069339  mov     [rbp+0A0h+var_48], 6Ah ; 'j'
0x180069341  lea     rax, [rbp+0A0h+var_60]
0x180069345  mov     [rsp+1A0h+var_180], rax
0x18006934a  mov     r9d, 2
0x180069350  lea     rdx, SEMgr_Event_COM_API_Start; ")#"
0x180069357  call    McGenEventWrite_EventWriteTransfer
0x18006935c  lea     rcx, [rbp+0A0h+var_120]; this
0x180069360  call    ??0CallerIdentity@Library@DeviceCastle@@QEAA@XZ; DeviceCastle::Library::CallerIdentity::CallerIdentity(void)
0x180069365  nop
0x180069366  mov     [rbp+0A0h+var_60], 0
0x18006936e  xor     ecx, ecx; BindingHandle
0x180069370  call    cs:__imp_RpcImpersonateClient2
0x180069376  mov     ebx, eax
0x180069378  mov     [rbp+0A0h+var_58], eax
0x18006937b  test    eax, eax
0x18006937d  jns     short loc_180069384
0x18006937f  jmp     loc_1800694AD
0x180069384  lea     rcx, [rbp+0A0h+var_120]; this
0x180069388  call    ?DetermineCallerIdentity@CallerIdentity@Library@DeviceCastle@@QEAAJXZ; DeviceCastle::Library::CallerIdentity::DetermineCallerIdentity(void)
0x18006938d  mov     ebx, eax
0x18006938f  xor     ecx, ecx; BindingHandle
0x180069391  test    eax, eax
0x180069393  jns     short loc_1800693A0
0x180069395  call    cs:__imp_RpcRevertToSelfEx
0x18006939b  jmp     loc_1800694AD
0x1800693a0  call    cs:__imp_RpcRevertToSelfEx
0x1800693a6  mov     rdi, cs:qword_18012F408
0x1800693ad  test    rdi, rdi
0x1800693b0  jnz     short loc_1800693BC
0x1800693b2  mov     ebx, 8007000Eh
0x1800693b7  jmp     loc_180069453
0x1800693bc  lea     rax, off_1800A0110
0x1800693c3  mov     [rsp+1A0h+var_160], rax
0x1800693c8  lea     rax, off_18012F400
0x1800693cf  mov     [rsp+1A0h+var_158], rax
0x1800693d4  lea     rax, [rbp+0A0h+var_120]
0x1800693d8  mov     [rsp+1A0h+var_150], rax
0x1800693dd  mov     [rsp+1A0h+var_148], r14
0x1800693e2  mov     [rsp+1A0h+var_140], esi
0x1800693e6  mov     eax, dword ptr [rbp+0A0h+var_48+4]
0x1800693e9  mov     [rsp+1A0h+var_13C], eax
0x1800693ed  mov     [rsp+1A0h+var_138], r15
0x1800693f2  mov     eax, [rbp+0A0h+arg_20]
0x1800693f8  mov     [rsp+1A0h+var_130], eax
0x1800693fc  mov     eax, [rbp+0A0h+arg_28]
0x180069402  mov     [rsp+1A0h+var_12C], eax
0x180069406  lea     rax, [rsp+1A0h+var_160]
0x18006940b  mov     [rsp+1A0h+var_128], rax
0x180069410  lea     r8, [rsp+1A0h+var_160]
0x180069415  lea     rdx, [rbp+0A0h+var_120]
0x180069419  lea     rcx, aDevicecastleLi; "DeviceCastle::Library::DeviceCastleProv"...
0x180069420  call    ?TranslateExceptions@Utilities@Internal@Library@DeviceCastle@@SAJPEBGPEAVCallerIdentity@34@AEBV?$function@$$A6AJXZ@std@@@Z; DeviceCastle::Library::Internal::Utilities::TranslateExceptions(ushort const *,DeviceCastle::Library::CallerIdentity *,std::function<long (void)> const &)
0x180069425  mov     ebx, eax
0x180069427  mov     rcx, [rsp+1A0h+var_128]
0x18006942c  test    rcx, rcx
0x18006942f  jz      short loc_180069448
0x180069431  mov     rax, [rcx]
0x180069434  lea     rdx, [rsp+1A0h+var_160]
0x180069439  cmp     rcx, rdx
0x18006943c  setnz   dl
0x18006943f  mov     rax, [rax+20h]
0x180069443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069448  test    ebx, ebx
0x18006944a  jns     short loc_1800694AB
0x18006944c  mov     rdi, cs:qword_18012F408
0x180069453  test    rdi, rdi
0x180069456  jz      short loc_1800694AD
0x180069458  lea     eax, [rbx+7F3EFDDEh]
0x18006945e  neg     eax
0x180069460  sbb     esi, esi
0x180069462  lea     r14, aNull_0; "<null>"
0x180069469  test    r15, r15
0x18006946c  cmovnz  r14, r15
0x180069470  lea     rcx, [rbp+0A0h+var_120]
0x180069474  call    ?Username@CallerIdentity@Library@DeviceCastle@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceCastle::Library::CallerIdentity::Username(void)
0x180069479  cmp     qword ptr [rax+18h], 7
0x18006947e  jbe     short loc_180069483
0x180069480  mov     rax, [rax]
0x180069483  mov     [rsp+1A0h+var_170], ebx
0x180069487  mov     [rsp+1A0h+var_178], r14
0x18006948c  mov     [rsp+1A0h+var_180], rax
0x180069491  lea     r9, aDeviceCastleFa_13; "Device Castle failed to create the Cryp"...
0x180069498  lea     r8, [rbp+0A0h+var_120]; struct DeviceCastle::Library::CallerIdentity *
0x18006949c  lea     edx, [rsi+4]; unsigned int
0x18006949f  mov     rcx, rdi; this
0x1800694a2  call    ?LogFormattedMessage@DeviceCastleInternal@Library@DeviceCastle@@QEBAXKPEAVCallerIdentity@23@PEBGZZ; DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(ulong,DeviceCastle::Library::CallerIdentity *,ushort const *,...)
0x1800694a7  test    ebx, ebx
0x1800694a9  js      short loc_1800694AD
0x1800694ab  xor     ebx, ebx
0x1800694ad  test    cs:byte_180132D81, 10h
0x1800694b4  jz      short loc_1800694DE
0x1800694b6  mov     [rbp+0A0h+var_50], r13
0x1800694ba  mov     [rbp+0A0h+var_48], 6Ah ; 'j'
0x1800694c2  lea     rax, [rbp+0A0h+var_60]
0x1800694c6  mov     [rsp+1A0h+var_180], rax
0x1800694cb  mov     r9d, 2
0x1800694d1  lea     rdx, SEMgr_Event_COM_API_End; "*#"
0x1800694d8  call    McGenEventWrite_EventWriteTransfer
0x1800694dd  nop
0x1800694de  lea     rcx, [rbp+0A0h+var_80]
0x1800694e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800694e7  lea     rcx, [rbp+0A0h+var_A0]
0x1800694eb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800694f0  lea     rcx, [rbp+0A0h+var_C0]
0x1800694f4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800694f9  lea     rcx, [rbp+0A0h+var_E0]
0x1800694fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069502  lea     rcx, [rbp+0A0h+var_100]
0x180069506  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006950b  lea     rax, ??_7Blob@Library@DeviceCastle@@6B@; const DeviceCastle::Library::Blob::`vftable'
0x180069512  mov     [rbp+0A0h+var_120], rax
0x180069516  lea     rcx, [rbp+0A0h+var_120]; this
0x18006951a  call    ?Clear@Blob@Library@DeviceCastle@@UEAAXXZ; DeviceCastle::Library::Blob::Clear(void)
0x18006951f  mov     eax, ebx
0x180069521  mov     rcx, [rbp+0A0h+var_30]
0x180069525  xor     rcx, rsp; StackCookie
0x180069528  call    __security_check_cookie
0x18006952d  lea     r11, [rsp+1A0h+var_20]
0x180069535  mov     rbx, [r11+30h]
0x180069539  mov     rsi, [r11+38h]
0x18006953d  mov     rsp, r11
0x180069540  pop     r15
0x180069542  pop     r14
0x180069544  pop     r13
0x180069546  pop     rdi
0x180069547  pop     rbp
0x180069548  retn
```
