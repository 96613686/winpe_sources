# CSyncSharePartnershipManagerInternal::Advise(IUnknown *,ulong *)

- ea: `0x180015e50`
- end: `0x180016151`
- name: `?Advise@CSyncSharePartnershipManagerInternal@@UEAAJPEAUIUnknown@@PEAK@Z`
- size: `769`
- prototype: `int(CSyncSharePartnershipManagerInternal *__hidden this, struct IUnknown *, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007e10`
- `0x180008b60`
- `0x180009384`
- `0x180011314`
- `0x1800158d4`
- `0x180015a1c`
- `0x180015d30`
- `0x180015e50`
- `0x180019b74`
- `0x18001d120`
- `0x180023e64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800160dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016108`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800160dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016108`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180016011`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180016011`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180015f76`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180015f76`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSyncSharePartnershipManagerInternal::Advise(
        CSyncSharePartnershipManagerInternal *this,
        struct IUnknown *a2,
        unsigned int *a3)
{
  unsigned int *v3; // rdi
  _BYTE *v6; // rax
  char v7; // al
  HRESULT v8; // eax
  HRESULT v9; // eax
  __int64 v10; // rax
  unsigned int v11; // ebx
  int v13; // [rsp+40h] [rbp-C8h] BYREF
  int v14; // [rsp+44h] [rbp-C4h]
  char v15; // [rsp+48h] [rbp-C0h]
  const char *v16; // [rsp+50h] [rbp-B8h]
  __int64 v17; // [rsp+58h] [rbp-B0h]
  unsigned int *v18; // [rsp+60h] [rbp-A8h]
  int pExceptionObject; // [rsp+68h] [rbp-A0h] BYREF
  int v20; // [rsp+6Ch] [rbp-9Ch] BYREF
  HRESULT v21; // [rsp+70h] [rbp-98h] BYREF
  HRESULT v22; // [rsp+74h] [rbp-94h] BYREF
  CSyncSharePartnershipManagerInternal *v23; // [rsp+78h] [rbp-90h]
  int v24; // [rsp+80h] [rbp-88h] BYREF
  int v25; // [rsp+84h] [rbp-84h] BYREF
  struct IUnknown *Unknown; // [rsp+88h] [rbp-80h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+90h] [rbp-78h] BYREF
  char v28; // [rsp+98h] [rbp-70h]
  LPCRITICAL_SECTION v29; // [rsp+A0h] [rbp-68h] BYREF
  char v30; // [rsp+A8h] [rbp-60h]
  const ATL::CAtlException *v31; // [rsp+B0h] [rbp-58h] BYREF
  const ATL::CAtlException *v32; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v33[32]; // [rsp+C0h] [rbp-48h] BYREF

  v3 = a3;
  v23 = this;
  v18 = a3;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 64, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( (v6[68] & 8) != 0 && v6[65] >= 6u )
  {
    v7 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v7 = 0;
LABEL_9:
  v13 = 0;
  v14 = 738;
  v15 = v7;
  v16 = "CSyncSharePartnershipManagerInternal::Advise";
  v17 = 0;
  if ( v3 )
    *v3 = 0;
  try
  {
    if ( !a2 )
    {
      v13 = -2147024809;
      HIWORD(v14) = 744;
      pExceptionObject = -2147024809;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v14) = 744;
    v13 = 0;
    if ( !v3 )
    {
      v13 = -2147024809;
      HIWORD(v14) = 745;
      v20 = -2147024809;
      throw (long *)&v20;
    }
    LOWORD(v14) = 745;
    v8 = CoImpersonateClient();
    v13 = v8;
    if ( v8 < 0 )
    {
      HIWORD(v14) = 746;
      v21 = v8;
      throw (long *)&v21;
    }
    LOWORD(v14) = 746;
    CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(
      (__int64)&v29,
      (struct _RTL_CRITICAL_SECTION *)this + 5);
    CSyncStateManager::AddImpersonatingUser(*((CSyncStateManager **)this + 16), (__int64)v33);
    CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(
      (__int64)&lpCriticalSection,
      (struct _RTL_CRITICAL_SECTION *)this + 4);
    v9 = CoSetProxyBlanket(a2, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
    v13 = v9;
    if ( v9 >= 0 )
    {
      v9 = ATL::IConnectionPointImpl<CSyncSharePartnershipManagerInternal,&__s_GUID const _GUID_7272b32b_b31c_43c6_8e6d_dd62c94608c3,ATL::CComDynamicUnkArray>::Advise(
             v23,
             a2,
             v3);
      v13 = v9;
      if ( v9 >= 0 )
      {
        Unknown = ATL::CComDynamicUnkArray::GetUnknown((CSyncSharePartnershipManagerInternal *)((char *)v23 + 8), *v3);
        try
        {
          v10 = std::map<IUnknown *,std::wstring>::operator[]((char *)this + 144, &Unknown);
          std::wstring::operator=(v10, v33);
        }
        catch ( long v24 )
        {
          v13 = v24;
          v3 = v18;
        }
        catch ( std::bad_alloc )
        {
          HIWORD(v14) = 782;
          v13 = -2147024882;
          v3 = v18;
        }
        catch ( std::exception )
        {
          HIWORD(v14) = 782;
          v13 = -2147418113;
          v3 = v18;
        }
        catch ( const ATL::CAtlException *v31 )
        {
          HIWORD(v14) = 782;
          v13 = *(_DWORD *)v31;
          v3 = v18;
        }
        v9 = v13;
        if ( v13 < 0 )
        {
          ATL::IConnectionPointImpl<CSyncSharePartnershipManagerInternal,&__s_GUID const _GUID_7272b32b_b31c_43c6_8e6d_dd62c94608c3,ATL::CComDynamicUnkArray>::Unadvise(
            v23,
            *v3);
          *v3 = 0;
          v9 = v13;
        }
      }
    }
    v13 = v9;
    if ( v9 < 0 )
    {
      HIWORD(v14) = 792;
      v22 = v9;
      throw (long *)&v22;
    }
    LOWORD(v14) = 792;
    if ( v28 )
    {
      LeaveCriticalSection(lpCriticalSection);
      v28 = 0;
    }
    std::wstring::~wstring((__int64)v33);
    if ( v30 )
    {
      LeaveCriticalSection(v29);
      v30 = 0;
    }
  }
  catch ( long v25 )
  {
    v13 = v25;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v14) = 794;
    v13 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v14) = 794;
    v13 = -2147418113;
  }
  catch ( const ATL::CAtlException *v32 )
  {
    HIWORD(v14) = 794;
    v13 = *(_DWORD *)v32;
  }
  v11 = v13;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v13);
  return v11;
}

```

## disassembly

```asm
0x180015e50  mov     [rsp+arg_18], rbx
0x180015e55  push    rsi
0x180015e56  push    rdi
0x180015e57  push    r14
0x180015e59  sub     rsp, 0F0h
0x180015e60  mov     rax, cs:__security_cookie
0x180015e67  xor     rax, rsp
0x180015e6a  mov     [rsp+108h+var_28], rax
0x180015e72  mov     rdi, r8
0x180015e75  mov     rsi, rdx
0x180015e78  mov     r14, rcx
0x180015e7b  mov     [rsp+108h+var_90], rcx
0x180015e80  mov     [rsp+108h+var_A8], r8
0x180015e85  lea     rcx, WPP_GLOBAL_Control
0x180015e8c  mov     rax, cs:WPP_GLOBAL_Control
0x180015e93  cmp     rax, rcx
0x180015e96  jz      short loc_180015EC0
0x180015e98  test    byte ptr [rax+44h], 8
0x180015e9c  jz      short loc_180015ED2
0x180015e9e  cmp     byte ptr [rax+41h], 6
0x180015ea2  jb      short loc_180015EC0
0x180015ea4  mov     edx, 40h ; '@'
0x180015ea9  lea     r8, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids
0x180015eb0  mov     rcx, [rax+38h]
0x180015eb4  call    WPP_SF_
0x180015eb9  mov     rax, cs:WPP_GLOBAL_Control
0x180015ec0  test    byte ptr [rax+44h], 8
0x180015ec4  jz      short loc_180015ED2
0x180015ec6  cmp     byte ptr [rax+41h], 6
0x180015eca  jb      short loc_180015ED2
0x180015ecc  mov     al, 1
0x180015ece  xor     ebx, ebx
0x180015ed0  jmp     short loc_180015ED6
0x180015ed2  xor     ebx, ebx
0x180015ed4  mov     al, bl
0x180015ed6  mov     [rsp+108h+var_C8], ebx
0x180015eda  mov     [rsp+108h+var_C4], 2E2h
0x180015ee2  mov     [rsp+108h+var_C0], al
0x180015ee6  lea     rax, aCsyncsharepart_49; "CSyncSharePartnershipManagerInternal::A"...
0x180015eed  mov     [rsp+108h+var_B8], rax
0x180015ef2  mov     [rsp+108h+var_B0], rbx
0x180015ef7  test    rdi, rdi
0x180015efa  jz      short loc_180015EFE
0x180015efc  mov     [rdi], ebx
0x180015efe  mov     eax, [rsp+108h+var_C8]
0x180015f02  mov     [rsp+108h+var_C8], eax
0x180015f06  mov     ecx, 2E8h
0x180015f0b  test    rsi, rsi
0x180015f0e  jnz     short loc_180015F33
0x180015f10  mov     eax, 80070057h
0x180015f15  mov     [rsp+108h+var_C8], eax
0x180015f19  mov     word ptr [rsp+108h+var_C4+2], cx
0x180015f1e  mov     [rsp+108h+pExceptionObject], eax
0x180015f22  lea     rdx, _TI1J; pThrowInfo
0x180015f29  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180015f2e  call    _CxxThrowException_0
0x180015f33  mov     [rsp+108h+var_C8], ebx
0x180015f37  mov     word ptr [rsp+108h+var_C4], cx
0x180015f3c  mov     [rsp+108h+var_C8], ebx
0x180015f40  mov     ecx, 2E9h
0x180015f45  test    rdi, rdi
0x180015f48  jnz     short loc_180015F6D
0x180015f4a  mov     eax, 80070057h
0x180015f4f  mov     [rsp+108h+var_C8], eax
0x180015f53  mov     word ptr [rsp+108h+var_C4+2], cx
0x180015f58  mov     [rsp+108h+var_9C], eax
0x180015f5c  lea     rdx, _TI1J; pThrowInfo
0x180015f63  lea     rcx, [rsp+108h+var_9C]; pExceptionObject
0x180015f68  call    _CxxThrowException_0
0x180015f6d  mov     [rsp+108h+var_C8], ebx
0x180015f71  mov     word ptr [rsp+108h+var_C4], cx
0x180015f76  call    cs:__imp_CoImpersonateClient
0x180015f7c  mov     [rsp+108h+var_C8], eax
0x180015f80  mov     [rsp+108h+var_C8], eax
0x180015f84  mov     ecx, 2EAh
0x180015f89  test    eax, eax
0x180015f8b  jns     short loc_180015FA7
0x180015f8d  mov     word ptr [rsp+108h+var_C4+2], cx
0x180015f92  mov     [rsp+108h+var_98], eax
0x180015f96  lea     rdx, _TI1J; pThrowInfo
0x180015f9d  lea     rcx, [rsp+108h+var_98]; pExceptionObject
0x180015fa2  call    _CxxThrowException_0
0x180015fa7  mov     word ptr [rsp+108h+var_C4], cx
0x180015fac  lea     rdx, [r14+0C8h]
0x180015fb3  lea     rcx, [rsp+108h+var_68]
0x180015fbb  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x180015fc0  nop
0x180015fc1  lea     rdx, [rsp+108h+var_48]
0x180015fc9  mov     rcx, [r14+80h]; this
0x180015fd0  call    ?AddImpersonatingUser@CSyncStateManager@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CSyncStateManager::AddImpersonatingUser(void)
0x180015fd5  nop
0x180015fd6  lea     rdx, [r14+0A0h]
0x180015fdd  lea     rcx, [rsp+108h+lpCriticalSection]
0x180015fe5  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x180015fea  nop
0x180015feb  mov     [rsp+108h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180015ff3  mov     [rsp+108h+pAuthInfo], rbx; pAuthInfo
0x180015ff8  mov     [rsp+108h+dwImpLevel], 3; dwImpLevel
0x180016000  mov     [rsp+108h+dwAuthnLevel], ebx; dwAuthnLevel
0x180016004  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180016008  xor     r8d, r8d; dwAuthzSvc
0x18001600b  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001600e  mov     rcx, rsi; pProxy
0x180016011  call    cs:__imp_CoSetProxyBlanket
0x180016017  mov     [rsp+108h+var_C8], eax
0x18001601b  test    eax, eax
0x18001601d  js      short loc_18001609B
0x18001601f  mov     r8, rdi
0x180016022  mov     rdx, rsi
0x180016025  mov     rsi, [rsp+108h+var_90]
0x18001602a  mov     rcx, rsi
0x18001602d  call    ?Advise@?$IConnectionPointImpl@VCSyncSharePartnershipManagerInternal@@$1?_GUID_7272b32b_b31c_43c6_8e6d_dd62c94608c3@@3U__s_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAUIUnknown@@PEAK@Z; ATL::IConnectionPointImpl<CSyncSharePartnershipManagerInternal,&__s_GUID const _GUID_7272b32b_b31c_43c6_8e6d_dd62c94608c3,ATL::CComDynamicUnkArray>::Advise(IUnknown *,ulong *)
0x180016032  mov     [rsp+108h+var_C8], eax
0x180016036  test    eax, eax
0x180016038  js      short loc_18001609B
0x18001603a  lea     rcx, [rsi+8]; this
0x18001603e  mov     edx, [rdi]; unsigned int
0x180016040  call    ?GetUnknown@CComDynamicUnkArray@ATL@@QEAAPEAUIUnknown@@K@Z; ATL::CComDynamicUnkArray::GetUnknown(ulong)
0x180016045  mov     [rsp+108h+var_80], rax
0x18001604d  lea     rcx, [r14+90h]
0x180016054  lea     rdx, [rsp+108h+var_80]
0x18001605c  call    ??A?$map@PEAUIUnknown@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@PEAUIUnknown@@@3@V?$allocator@U?$pair@QEAUIUnknown@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBQEAUIUnknown@@@Z; std::map<IUnknown *,std::wstring>::operator[](IUnknown * const &)
0x180016061  mov     rcx, rax
0x180016064  lea     rdx, [rsp+108h+var_48]
0x18001606c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180016071  nop
0x180016072  jmp     short loc_180016081
0x180016074  jmp     short loc_18001607A
0x180016076  jmp     short loc_18001607A
0x180016078  jmp     short $+2
0x18001607a  mov     rdi, [rsp+108h+var_A8]
0x18001607f  xor     ebx, ebx
0x180016081  mov     eax, [rsp+108h+var_C8]
0x180016085  test    eax, eax
0x180016087  jns     short loc_18001609B
0x180016089  mov     edx, [rdi]
0x18001608b  mov     rcx, [rsp+108h+var_90]
0x180016090  call    ?Unadvise@?$IConnectionPointImpl@VCSyncSharePartnershipManagerInternal@@$1?_GUID_7272b32b_b31c_43c6_8e6d_dd62c94608c3@@3U__s_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJK@Z; ATL::IConnectionPointImpl<CSyncSharePartnershipManagerInternal,&__s_GUID const _GUID_7272b32b_b31c_43c6_8e6d_dd62c94608c3,ATL::CComDynamicUnkArray>::Unadvise(ulong)
0x180016095  mov     [rdi], ebx
0x180016097  mov     eax, [rsp+108h+var_C8]
0x18001609b  mov     [rsp+108h+var_C8], eax
0x18001609f  mov     [rsp+108h+var_C8], eax
0x1800160a3  mov     ecx, 318h
0x1800160a8  test    eax, eax
0x1800160aa  jns     short loc_1800160C6
0x1800160ac  mov     word ptr [rsp+108h+var_C4+2], cx
0x1800160b1  mov     [rsp+108h+var_94], eax
0x1800160b5  lea     rdx, _TI1J; pThrowInfo
0x1800160bc  lea     rcx, [rsp+108h+var_94]; pExceptionObject
0x1800160c1  call    _CxxThrowException_0
0x1800160c6  mov     word ptr [rsp+108h+var_C4], cx
0x1800160cb  cmp     [rsp+108h+var_70], bl
0x1800160d2  jz      short loc_1800160E9
0x1800160d4  mov     rcx, [rsp+108h+lpCriticalSection]; lpCriticalSection
0x1800160dc  call    cs:__imp_LeaveCriticalSection
0x1800160e2  mov     [rsp+108h+var_70], bl
0x1800160e9  lea     rcx, [rsp+108h+var_48]
0x1800160f1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800160f6  nop
0x1800160f7  cmp     [rsp+108h+var_60], bl
0x1800160fe  jz      short loc_180016115
0x180016100  mov     rcx, [rsp+108h+var_68]; lpCriticalSection
0x180016108  call    cs:__imp_LeaveCriticalSection
0x18001610e  mov     [rsp+108h+var_60], bl
0x180016115  jmp     short loc_18001611D
0x180016117  jmp     short loc_18001611D
0x180016119  jmp     short loc_18001611D
0x18001611b  jmp     short $+2
0x18001611d  mov     ebx, [rsp+108h+var_C8]
0x180016121  lea     rcx, [rsp+108h+var_C8]; this
0x180016126  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18001612b  mov     eax, ebx
0x18001612d  mov     rcx, [rsp+108h+var_28]
0x180016135  xor     rcx, rsp; StackCookie
0x180016138  call    __security_check_cookie
0x18001613d  mov     rbx, [rsp+108h+arg_18]
0x180016145  add     rsp, 0F0h
0x18001614c  pop     r14
0x18001614e  pop     rdi
0x18001614f  pop     rsi
0x180016150  retn
```
