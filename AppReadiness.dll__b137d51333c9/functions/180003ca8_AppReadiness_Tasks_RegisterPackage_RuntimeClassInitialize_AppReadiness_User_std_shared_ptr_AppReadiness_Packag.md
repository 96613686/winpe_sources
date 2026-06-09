# AppReadiness::Tasks::RegisterPackage::RuntimeClassInitialize(AppReadiness::User *,std::shared_ptr<AppReadiness::PackageInfo> const &)

- ea: `0x180003ca8`
- end: `0x180003e9c`
- name: `?RuntimeClassInitialize@RegisterPackage@Tasks@AppReadiness@@QEAAJPEAVUser@3@AEBV?$shared_ptr@VPackageInfo@AppReadiness@@@std@@@Z`
- size: `500`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002dec`

## callees

- `0x180002958`
- `0x180003ca8`
- `0x180005270`
- `0x180005580`
- `0x18000a470`
- `0x18002ecec`
- `0x18003235c`
- `0x18003e210`
- `0x18003ecb4`
- `0x180044a38`
- `0x180049310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003e32`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003e32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003e1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003e1c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180003e59`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180003e59`

## string_xrefs

- `0x180003d6c`: `onecoreuap\shell\appreadiness\src\core\basetask.cpp`
- `0x180003d82`: `AppReadiness::Impl::BaseTask::RuntimeClassInitialize`
- `0x180003d77`: `BaseTask::RuntimeClassInitialize(user, taskId, priority)`
- `0x180003e6a`: `onecoreuap\shell\appreadiness\src\tasks\registerpackage.cpp`

## pseudocode

```c
__int64 __fastcall AppReadiness::Tasks::RegisterPackage::RuntimeClassInitialize(__int64 a1, __int64 a2, __int64 *a3)
{
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // r14
  __int64 v8; // rdx
  volatile signed __int32 *v9; // r8
  signed __int32 v10; // eax
  signed __int32 v11; // ett
  std::_Ref_count_base *v12; // rcx
  int v13; // eax
  HRESULT StringReference; // eax
  __int64 v15; // rdi
  int ActivationFactory; // eax
  int v18; // [rsp+20h] [rbp-59h]
  int pExceptionObject; // [rsp+50h] [rbp-29h] BYREF
  const char *v20; // [rsp+58h] [rbp-21h]
  const char *v21; // [rsp+60h] [rbp-19h]
  const char *v22; // [rsp+68h] [rbp-11h]
  int v23; // [rsp+70h] [rbp-9h]
  _QWORD hstringHeader[2]; // [rsp+78h] [rbp-1h] BYREF
  __m128i hstringHeader_16; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v5 = (volatile signed __int32 *)a3[1];
  if ( v5 )
  {
    v6 = *a3;
    _InterlockedIncrement(v5 + 3);
  }
  else
  {
    v5 = 0;
    v6 = 0;
  }
  v7 = AppReadiness::Tasks::BuildTaskIdWithPackageFamilyName<16>(hstringHeader, a2, *a3 + 72);
  v8 = 0;
  v9 = 0;
  if ( v5 )
  {
    v10 = *((_DWORD *)v5 + 2);
    while ( v10 )
    {
      v11 = v10;
      v10 = _InterlockedCompareExchange(v5 + 2, v10 + 1, v10);
      if ( v11 == v10 )
      {
        v8 = v6;
        v9 = v5;
        break;
      }
    }
  }
  *(_QWORD *)(a1 + 176) = v8;
  v12 = *(std::_Ref_count_base **)(a1 + 184);
  *(_QWORD *)(a1 + 184) = v9;
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  v13 = AppReadiness::Impl::BaseTask::RuntimeClassInitialize(a1 + 32, a2, v7, 3);
  if ( v13 < 0 )
  {
    pExceptionObject = v13;
    v20 = "onecoreuap\\shell\\appreadiness\\src\\core\\basetask.cpp";
    v21 = "BaseTask::RuntimeClassInitialize(user, taskId, priority)";
    v22 = "AppReadiness::Impl::BaseTask::RuntimeClassInitialize";
    v23 = 52;
    if ( (Microsoft_Windows_AppReadinessEnableBits & 2) != 0 )
      McTemplateU0dsssd_EventWriteTransfer(
        52,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\basetask.cpp",
        v13,
        (unsigned int)"BaseTask::RuntimeClassInitialize(user, taskId, priority)",
        (__int64)"AppReadiness::Impl::BaseTask::RuntimeClassInitialize",
        (__int64)"onecoreuap\\shell\\appreadiness\\src\\core\\basetask.cpp",
        52);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  if ( hstringHeader_16.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(hstringHeader[0], 2 * hstringHeader_16.m128i_i64[1] + 2);
  hstringHeader_16 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(hstringHeader[0]) = 0;
  if ( v5 )
    std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v5);
  hstringHeader_16.m128i_i64[1] = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.Internal.StateRepository.Package",
                      0x28u,
                      (HSTRING_HEADER *)hstringHeader,
                      (HSTRING *)&hstringHeader_16.m128i_i64[1]);
  if ( StringReference < 0 )
    RaiseException(StringReference, 1u, 0, 0);
  v15 = hstringHeader_16.m128i_i64[1];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 304);
  ActivationFactory = RoGetActivationFactory(v15, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, a1 + 304);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v18);
  return 0;
}

```

## disassembly

```asm
0x180003ca8  push    rbp
0x180003caa  push    rbx
0x180003cab  push    rsi
0x180003cac  push    rdi
0x180003cad  push    r12
0x180003caf  push    r14
0x180003cb1  push    r15
0x180003cb3  lea     rbp, [rsp-27h]
0x180003cb8  sub     rsp, 0A0h
0x180003cbf  mov     rax, cs:__security_cookie
0x180003cc6  xor     rax, rsp
0x180003cc9  mov     [rbp+57h+var_38], rax
0x180003ccd  mov     r12, rdx
0x180003cd0  mov     r15, rcx
0x180003cd3  xorps   xmm0, xmm0
0x180003cd6  movdqu  [rbp+57h+var_90], xmm0
0x180003cdb  mov     rbx, [r8+8]
0x180003cdf  test    rbx, rbx
0x180003ce2  jz      short loc_180003CF5
0x180003ce4  mov     rdi, [r8]
0x180003ce7  mov     qword ptr [rbp+57h+var_90], rdi
0x180003ceb  mov     qword ptr [rbp+57h+var_90+8], rbx
0x180003cef  lock inc dword ptr [rbx+0Ch]
0x180003cf3  jmp     short loc_180003CFD
0x180003cf5  mov     rbx, qword ptr [rbp+57h+var_90+8]
0x180003cf9  mov     rdi, qword ptr [rbp+57h+var_90]
0x180003cfd  mov     r8, [r8]
0x180003d00  add     r8, 48h ; 'H'
0x180003d04  lea     rcx, [rbp+57h+hstringHeader]
0x180003d08  call    ??$BuildTaskIdWithPackageFamilyName@$0BA@@Tasks@AppReadiness@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY0BA@$$CBGAEBV23@@Z; AppReadiness::Tasks::BuildTaskIdWithPackageFamilyName<16>(ushort const (&)[16],std::wstring const &)
0x180003d0d  mov     r14, rax
0x180003d10  xor     edx, edx
0x180003d12  xor     r8d, r8d
0x180003d15  test    rbx, rbx
0x180003d18  jz      short loc_180003D31
0x180003d1a  mov     eax, [rbx+8]
0x180003d1d  test    eax, eax
0x180003d1f  jz      short loc_180003D31
0x180003d21  lea     ecx, [rax+1]
0x180003d24  lock cmpxchg [rbx+8], ecx
0x180003d29  jnz     short loc_180003D1D
0x180003d2b  mov     rdx, rdi
0x180003d2e  mov     r8, rbx
0x180003d31  mov     [r15+0B0h], rdx
0x180003d38  mov     rcx, [r15+0B8h]; this
0x180003d3f  mov     [r15+0B8h], r8
0x180003d46  test    rcx, rcx
0x180003d49  jz      short loc_180003D50
0x180003d4b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180003d50  mov     r9d, 3
0x180003d56  mov     r8, r14
0x180003d59  mov     rdx, r12
0x180003d5c  lea     rcx, [r15+20h]
0x180003d60  call    ?RuntimeClassInitialize@BaseTask@Impl@AppReadiness@@IEAAJPEAVUser@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TaskPriority@3@@Z; AppReadiness::Impl::BaseTask::RuntimeClassInitialize(AppReadiness::User *,std::wstring const &,AppReadiness::TaskPriority)
0x180003d65  test    eax, eax
0x180003d67  jns     short loc_180003DC5
0x180003d69  mov     [rbp+57h+pExceptionObject], eax
0x180003d6c  lea     rdx, aOnecoreuapShel_29; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180003d73  mov     [rbp+57h+var_78], rdx
0x180003d77  lea     r9, aBasetaskRuntim; "BaseTask::RuntimeClassInitialize(user, "...
0x180003d7e  mov     [rbp+57h+var_70], r9
0x180003d82  lea     r8, aAppreadinessIm_5; "AppReadiness::Impl::BaseTask::RuntimeCl"...
0x180003d89  mov     [rbp+57h+var_68], r8
0x180003d8d  mov     ecx, 34h ; '4'
0x180003d92  mov     [rbp+57h+var_60], ecx
0x180003d95  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits, 2
0x180003d9c  jz      short loc_180003DB4
0x180003d9e  mov     [rsp+0D0h+var_A0], ecx
0x180003da2  mov     [rsp+0D0h+var_A8], rdx
0x180003da7  mov     [rsp+0D0h+var_B0], r8
0x180003dac  mov     r8d, eax
0x180003daf  call    McTemplateU0dsssd_EventWriteTransfer
0x180003db4  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180003dbb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180003dbf  call    _CxxThrowException_0
0x180003dc5  mov     rdx, [rbp+57h+string]
0x180003dc9  cmp     rdx, 7
0x180003dcd  jbe     short loc_180003DE0
0x180003dcf  lea     rdx, ds:2[rdx*2]
0x180003dd7  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180003ddb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180003de0  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180003de8  movdqu  xmmword ptr [rbp+0Fh], xmm0
0x180003ded  xor     eax, eax
0x180003def  mov     word ptr [rbp+57h+hstringHeader.Reserved], ax
0x180003df3  test    rbx, rbx
0x180003df6  jz      short loc_180003E00
0x180003df8  mov     rcx, rbx; this
0x180003dfb  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180003e00  mov     [rbp+57h+string], 0
0x180003e08  lea     r9, [rbp+57h+string]; string
0x180003e0c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180003e10  mov     edx, 28h ; '('; length
0x180003e15  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180003e1c  call    cs:__imp_WindowsCreateStringReference
0x180003e22  test    eax, eax
0x180003e24  jns     short loc_180003E39
0x180003e26  xor     r9d, r9d; lpArguments
0x180003e29  xor     r8d, r8d; nNumberOfArguments
0x180003e2c  lea     edx, [r9+1]; dwExceptionFlags
0x180003e30  mov     ecx, eax; dwExceptionCode
0x180003e32  call    cs:__imp_RaiseException
0x180003e38  nop
0x180003e39  lea     rbx, [r15+130h]
0x180003e40  mov     rdi, [rbp+57h+string]
0x180003e44  mov     rcx, rbx
0x180003e47  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003e4c  mov     r8, rbx
0x180003e4f  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x180003e56  mov     rcx, rdi
0x180003e59  call    cs:__imp_RoGetActivationFactory
0x180003e5f  mov     rcx, [rbp+5Fh]; this
0x180003e63  test    eax, eax
0x180003e65  jns     short loc_180003E7C
0x180003e67  mov     r9d, eax; char *
0x180003e6a  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x180003e71  mov     edx, 1Dh; void *
0x180003e76  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180003e7c  xor     eax, eax
0x180003e7e  mov     rcx, [rbp+57h+var_38]
0x180003e82  xor     rcx, rsp; StackCookie
0x180003e85  call    __security_check_cookie
0x180003e8a  add     rsp, 0A0h
0x180003e91  pop     r15
0x180003e93  pop     r14
0x180003e95  pop     r12
0x180003e97  pop     rdi
0x180003e98  pop     rsi
0x180003e99  pop     rbx
0x180003e9a  pop     rbp
0x180003e9b  retn
```
