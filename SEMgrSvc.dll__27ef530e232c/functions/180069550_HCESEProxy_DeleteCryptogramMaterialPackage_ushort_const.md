# HCESEProxy::DeleteCryptogramMaterialPackage(ushort const *)

- ea: `0x180069550`
- end: `0x180069774`
- name: `?DeleteCryptogramMaterialPackage@HCESEProxy@@UEAAJPEBG@Z`
- size: `548`
- prototype: `__int64 __fastcall(HCESEProxy *__hidden this, const unsigned __int16 *)`
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
- `0x180069550`
- `0x18009d010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient2` at `0x1800695c1`
- `RPCRT4!RpcImpersonateClient2` at `0x1800695c1`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800695e6`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800695f1`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800695e6`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800695f1`

## string_xrefs

- `0x180069643`: `DeviceCastle::Library::DeviceCastleProvider::DeleteCryptogramMaterialPackage`
- `0x1800696c2`: `Device Castle failed to delete the Cryptogram Material Package '%2!s!' for user %1!s!.  The error code was %3!#08I32x!.`
- `0x180069576`: `HCESecureElement::DeleteCryptogramMaterialPackage`
- `0x1800696dd`: `HCESecureElement::DeleteCryptogramMaterialPackage`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HCESEProxy::DeleteCryptogramMaterialPackage(
        HCESEProxy *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  _QWORD *v4; // rcx
  RPC_STATUS v5; // ebx
  __int64 v6; // r8
  DeviceCastle::Library::DeviceCastleInternal *v7; // rdi
  _QWORD *v8; // rdx
  unsigned int v9; // esi
  const wchar_t *v10; // r14
  _QWORD *v11; // rax
  _QWORD v13[7]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v14; // [rsp+78h] [rbp-88h]
  _QWORD v15[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v16[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v17[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v18[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v19[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v20[32]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v21; // [rsp+140h] [rbp+40h] BYREF
  RPC_STATUS v22; // [rsp+148h] [rbp+48h]
  const wchar_t *v23; // [rsp+150h] [rbp+50h]
  __int64 v24; // [rsp+158h] [rbp+58h]

  if ( (byte_180132D81 & 0x10) != 0 )
  {
    v23 = L"HCESecureElement::DeleteCryptogramMaterialPackage";
    v24 = 100;
    McGenEventWrite_EventWriteTransfer(this, ")#", a3, 2, &v21);
  }
  DeviceCastle::Library::CallerIdentity::CallerIdentity((DeviceCastle::Library::CallerIdentity *)v15);
  v21 = 0;
  v5 = RpcImpersonateClient2(0);
  v22 = v5;
  if ( v5 >= 0 )
  {
    v5 = DeviceCastle::Library::CallerIdentity::DetermineCallerIdentity((DeviceCastle::Library::CallerIdentity *)v15);
    if ( v5 < 0 )
    {
      RpcRevertToSelfEx(0);
      goto LABEL_21;
    }
    RpcRevertToSelfEx(0);
    v7 = qword_18012F408;
    if ( qword_18012F408 )
    {
      v13[0] = off_1800A0140;
      v13[1] = &off_18012F400;
      v13[2] = v15;
      v13[3] = a2;
      v14 = v13;
      v5 = DeviceCastle::Library::Internal::Utilities::TranslateExceptions(
             L"DeviceCastle::Library::DeviceCastleProvider::DeleteCryptogramMaterialPackage",
             v15,
             v13);
      v4 = v14;
      if ( v14 )
      {
        v8 = v13;
        LOBYTE(v8) = v14 != v13;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v14 + 32LL))(v14, v8);
      }
      if ( v5 >= 0 )
      {
        v5 = 0;
        goto LABEL_21;
      }
      v7 = qword_18012F408;
    }
    else
    {
      v5 = -2147024882;
    }
    if ( v7 )
    {
      v9 = 2;
      if ( v5 == -2134834660 )
        v9 = 4;
      v10 = L"<null>";
      if ( a2 )
        v10 = a2;
      v11 = DeviceCastle::Library::CallerIdentity::Username(v15);
      if ( v11[3] > 7u )
        v11 = (_QWORD *)*v11;
      DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(
        v7,
        v9,
        (struct DeviceCastle::Library::CallerIdentity *)v15,
        L"Device Castle failed to delete the Cryptogram Material Package '%2!s!' for user %1!s!.  The error code was %3!#08I32x!.",
        v11,
        v10,
        v5);
    }
  }
LABEL_21:
  if ( (byte_180132D81 & 0x10) != 0 )
  {
    v23 = L"HCESecureElement::DeleteCryptogramMaterialPackage";
    v24 = 100;
    McGenEventWrite_EventWriteTransfer(v4, "*#", v6, 2, &v21);
  }
  std::wstring::~wstring(v20);
  std::wstring::~wstring(v19);
  std::wstring::~wstring(v18);
  std::wstring::~wstring(v17);
  std::wstring::~wstring(v16);
  v15[0] = &DeviceCastle::Library::Blob::`vftable';
  DeviceCastle::Library::Blob::Clear((DeviceCastle::Library::Blob *)v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180069550  push    rbp
0x180069552  push    rbx
0x180069553  push    rsi
0x180069554  push    rdi
0x180069555  push    r14
0x180069557  push    r15
0x180069559  lea     rbp, [rsp-78h]
0x18006955e  sub     rsp, 178h
0x180069565  mov     rax, cs:__security_cookie
0x18006956c  xor     rax, rsp
0x18006956f  mov     [rbp+0A0h+var_40], rax
0x180069573  mov     r15, rdx
0x180069576  lea     rdi, aHcesecureeleme_7; "HCESecureElement::DeleteCryptogramMater"...
0x18006957d  test    cs:byte_180132D81, 10h
0x180069584  jz      short loc_1800695AD
0x180069586  mov     [rbp+0A0h+var_50], rdi
0x18006958a  mov     [rbp+0A0h+var_48], 64h ; 'd'
0x180069592  lea     rax, [rbp+0A0h+var_60]
0x180069596  mov     [rsp+1A0h+var_180], rax
0x18006959b  mov     r9d, 2
0x1800695a1  lea     rdx, SEMgr_Event_COM_API_Start; ")#"
0x1800695a8  call    McGenEventWrite_EventWriteTransfer
0x1800695ad  lea     rcx, [rbp+0A0h+var_120]; this
0x1800695b1  call    ??0CallerIdentity@Library@DeviceCastle@@QEAA@XZ; DeviceCastle::Library::CallerIdentity::CallerIdentity(void)
0x1800695b6  nop
0x1800695b7  mov     [rbp+0A0h+var_60], 0
0x1800695bf  xor     ecx, ecx; BindingHandle
0x1800695c1  call    cs:__imp_RpcImpersonateClient2
0x1800695c7  mov     ebx, eax
0x1800695c9  mov     [rbp+0A0h+var_58], eax
0x1800695cc  test    eax, eax
0x1800695ce  jns     short loc_1800695D5
0x1800695d0  jmp     loc_1800696E4
0x1800695d5  lea     rcx, [rbp+0A0h+var_120]; this
0x1800695d9  call    ?DetermineCallerIdentity@CallerIdentity@Library@DeviceCastle@@QEAAJXZ; DeviceCastle::Library::CallerIdentity::DetermineCallerIdentity(void)
0x1800695de  mov     ebx, eax
0x1800695e0  xor     ecx, ecx; BindingHandle
0x1800695e2  test    eax, eax
0x1800695e4  jns     short loc_1800695F1
0x1800695e6  call    cs:__imp_RpcRevertToSelfEx
0x1800695ec  jmp     loc_1800696E4
0x1800695f1  call    cs:__imp_RpcRevertToSelfEx
0x1800695f7  mov     rdi, cs:qword_18012F408
0x1800695fe  test    rdi, rdi
0x180069601  jnz     short loc_18006960A
0x180069603  mov     ebx, 8007000Eh
0x180069608  jmp     short loc_18006967D
0x18006960a  lea     rax, off_1800A0140
0x180069611  mov     [rsp+1A0h+var_160], rax
0x180069616  lea     rax, off_18012F400
0x18006961d  mov     [rsp+1A0h+var_158], rax
0x180069622  lea     rax, [rbp+0A0h+var_120]
0x180069626  mov     [rsp+1A0h+var_150], rax
0x18006962b  mov     [rsp+1A0h+var_148], r15
0x180069630  lea     rax, [rsp+1A0h+var_160]
0x180069635  mov     [rsp+1A0h+var_128], rax
0x18006963a  lea     r8, [rsp+1A0h+var_160]
0x18006963f  lea     rdx, [rbp+0A0h+var_120]
0x180069643  lea     rcx, aDevicecastleLi_3; "DeviceCastle::Library::DeviceCastleProv"...
0x18006964a  call    ?TranslateExceptions@Utilities@Internal@Library@DeviceCastle@@SAJPEBGPEAVCallerIdentity@34@AEBV?$function@$$A6AJXZ@std@@@Z; DeviceCastle::Library::Internal::Utilities::TranslateExceptions(ushort const *,DeviceCastle::Library::CallerIdentity *,std::function<long (void)> const &)
0x18006964f  mov     ebx, eax
0x180069651  mov     rcx, [rsp+1A0h+var_128]
0x180069656  test    rcx, rcx
0x180069659  jz      short loc_180069672
0x18006965b  mov     rax, [rcx]
0x18006965e  lea     rdx, [rsp+1A0h+var_160]
0x180069663  cmp     rcx, rdx
0x180069666  setnz   dl
0x180069669  mov     rax, [rax+20h]
0x18006966d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069672  test    ebx, ebx
0x180069674  jns     short loc_1800696DB
0x180069676  mov     rdi, cs:qword_18012F408
0x18006967d  test    rdi, rdi
0x180069680  jz      short loc_1800696DD
0x180069682  mov     esi, 2
0x180069687  lea     eax, [rsi+2]
0x18006968a  cmp     ebx, 80C1021Ch
0x180069690  cmovz   esi, eax
0x180069693  lea     r14, aNull_0; "<null>"
0x18006969a  test    r15, r15
0x18006969d  cmovnz  r14, r15
0x1800696a1  lea     rcx, [rbp+0A0h+var_120]
0x1800696a5  call    ?Username@CallerIdentity@Library@DeviceCastle@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceCastle::Library::CallerIdentity::Username(void)
0x1800696aa  cmp     qword ptr [rax+18h], 7
0x1800696af  jbe     short loc_1800696B4
0x1800696b1  mov     rax, [rax]
0x1800696b4  mov     [rsp+1A0h+var_170], ebx
0x1800696b8  mov     [rsp+1A0h+var_178], r14
0x1800696bd  mov     [rsp+1A0h+var_180], rax
0x1800696c2  lea     r9, aDeviceCastleFa_5; "Device Castle failed to delete the Cryp"...
0x1800696c9  lea     r8, [rbp+0A0h+var_120]; struct DeviceCastle::Library::CallerIdentity *
0x1800696cd  mov     edx, esi; unsigned int
0x1800696cf  mov     rcx, rdi; this
0x1800696d2  call    ?LogFormattedMessage@DeviceCastleInternal@Library@DeviceCastle@@QEBAXKPEAVCallerIdentity@23@PEBGZZ; DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(ulong,DeviceCastle::Library::CallerIdentity *,ushort const *,...)
0x1800696d7  test    ebx, ebx
0x1800696d9  js      short loc_1800696DD
0x1800696db  xor     ebx, ebx
0x1800696dd  lea     rdi, aHcesecureeleme_7; "HCESecureElement::DeleteCryptogramMater"...
0x1800696e4  test    cs:byte_180132D81, 10h
0x1800696eb  jz      short loc_180069715
0x1800696ed  mov     [rbp+0A0h+var_50], rdi
0x1800696f1  mov     [rbp+0A0h+var_48], 64h ; 'd'
0x1800696f9  lea     rax, [rbp+0A0h+var_60]
0x1800696fd  mov     [rsp+1A0h+var_180], rax
0x180069702  mov     r9d, 2
0x180069708  lea     rdx, SEMgr_Event_COM_API_End; "*#"
0x18006970f  call    McGenEventWrite_EventWriteTransfer
0x180069714  nop
0x180069715  lea     rcx, [rbp+0A0h+var_80]
0x180069719  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006971e  lea     rcx, [rbp+0A0h+var_A0]
0x180069722  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069727  lea     rcx, [rbp+0A0h+var_C0]
0x18006972b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069730  lea     rcx, [rbp+0A0h+var_E0]
0x180069734  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069739  lea     rcx, [rbp+0A0h+var_100]
0x18006973d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069742  lea     rax, ??_7Blob@Library@DeviceCastle@@6B@; const DeviceCastle::Library::Blob::`vftable'
0x180069749  mov     [rbp+0A0h+var_120], rax
0x18006974d  lea     rcx, [rbp+0A0h+var_120]; this
0x180069751  call    ?Clear@Blob@Library@DeviceCastle@@UEAAXXZ; DeviceCastle::Library::Blob::Clear(void)
0x180069756  mov     eax, ebx
0x180069758  mov     rcx, [rbp+0A0h+var_40]
0x18006975c  xor     rcx, rsp; StackCookie
0x18006975f  call    __security_check_cookie
0x180069764  add     rsp, 178h
0x18006976b  pop     r15
0x18006976d  pop     r14
0x18006976f  pop     rdi
0x180069770  pop     rsi
0x180069771  pop     rbx
0x180069772  pop     rbp
0x180069773  retn
```
