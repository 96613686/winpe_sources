# CSyncSharePartnershipManagerInternal::SetConfiguredByPolicy(ushort *,short)

- ea: `0x18001bef0`
- end: `0x18001c05a`
- name: `?SetConfiguredByPolicy@CSyncSharePartnershipManagerInternal@@UEAAJPEAGF@Z`
- size: `362`
- prototype: `int(CSyncSharePartnershipManagerInternal *__hidden this, unsigned __int16 *, __int16)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007e10`
- `0x180008b60`
- `0x180009384`
- `0x180011314`
- `0x18001bef0`
- `0x180023e64`
- `0x180027384`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c014`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c014`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001bf8e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001bf8e`

## string_xrefs

- `0x18001bf7d`: `CSyncSharePartnershipManagerInternal::SetConfiguredByPolicy`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSyncSharePartnershipManagerInternal::SetConfiguredByPolicy(
        CSyncSharePartnershipManagerInternal *this,
        unsigned __int16 *a2,
        __int16 a3)
{
  _BYTE *v6; // rax
  char v7; // al
  HRESULT v8; // eax
  unsigned int v9; // ebx
  int v11; // [rsp+20h] [rbp-88h] BYREF
  int v12; // [rsp+24h] [rbp-84h]
  char v13; // [rsp+28h] [rbp-80h]
  const char *v14; // [rsp+30h] [rbp-78h]
  __int64 v15; // [rsp+38h] [rbp-70h]
  HRESULT pExceptionObject; // [rsp+40h] [rbp-68h] BYREF
  int v17; // [rsp+44h] [rbp-64h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-60h] BYREF
  char v19; // [rsp+50h] [rbp-58h]
  const ATL::CAtlException *v20; // [rsp+58h] [rbp-50h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-48h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_8:
      v7 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 73, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( (v6[68] & 8) == 0 || v6[65] < 6u )
    goto LABEL_8;
  v7 = 1;
LABEL_9:
  v11 = 0;
  v12 = 1056;
  v13 = v7;
  v14 = "CSyncSharePartnershipManagerInternal::SetConfiguredByPolicy";
  v15 = 0;
  try
  {
    v8 = CoImpersonateClient();
    v11 = v8;
    if ( v8 < 0 )
    {
      HIWORD(v12) = 1060;
      pExceptionObject = v8;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v12) = 1060;
    CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(
      (__int64)&lpCriticalSection,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 216));
    CSyncStateManager::AddImpersonatingUser(*((CSyncStateManager **)this + 18), (__int64)v21);
    std::wstring::~wstring((__int64)v21);
    CSyncStateManager::SetConfiguredByPolicy(*((CSyncStateManager **)this + 18), a2, a3 == -1);
    if ( v19 )
    {
      LeaveCriticalSection(lpCriticalSection);
      v19 = 0;
    }
  }
  catch ( long v17 )
  {
    v11 = v17;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v12) = 1068;
    v11 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v12) = 1068;
    v11 = -2147418113;
  }
  catch ( const ATL::CAtlException *v20 )
  {
    HIWORD(v12) = 1068;
    v11 = *(_DWORD *)v20;
  }
  v9 = v11;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v11);
  return v9;
}

```

## disassembly

```asm
0x18001bef0  mov     [rsp+arg_10], rbx
0x18001bef5  push    rsi
0x18001bef6  push    rdi
0x18001bef7  push    r14
0x18001bef9  sub     rsp, 90h
0x18001bf00  mov     rax, cs:__security_cookie
0x18001bf07  xor     rax, rsp
0x18001bf0a  mov     [rsp+0A8h+var_28], rax
0x18001bf12  movzx   esi, r8w
0x18001bf16  mov     r14, rdx
0x18001bf19  mov     rdi, rcx
0x18001bf1c  lea     rcx, WPP_GLOBAL_Control
0x18001bf23  mov     rax, cs:WPP_GLOBAL_Control
0x18001bf2a  cmp     rax, rcx
0x18001bf2d  jz      short loc_18001BF57
0x18001bf2f  test    byte ptr [rax+44h], 8
0x18001bf33  jz      short loc_18001BF69
0x18001bf35  cmp     byte ptr [rax+41h], 6
0x18001bf39  jb      short loc_18001BF57
0x18001bf3b  mov     edx, 49h ; 'I'
0x18001bf40  lea     r8, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids
0x18001bf47  mov     rcx, [rax+38h]
0x18001bf4b  call    WPP_SF_
0x18001bf50  mov     rax, cs:WPP_GLOBAL_Control
0x18001bf57  test    byte ptr [rax+44h], 8
0x18001bf5b  jz      short loc_18001BF69
0x18001bf5d  cmp     byte ptr [rax+41h], 6
0x18001bf61  jb      short loc_18001BF69
0x18001bf63  mov     al, 1
0x18001bf65  xor     ebx, ebx
0x18001bf67  jmp     short loc_18001BF6D
0x18001bf69  xor     ebx, ebx
0x18001bf6b  mov     al, bl
0x18001bf6d  mov     [rsp+0A8h+var_88], ebx
0x18001bf71  mov     [rsp+0A8h+var_84], 420h
0x18001bf79  mov     [rsp+0A8h+var_80], al
0x18001bf7d  lea     rax, aCsyncsharepart_10; "CSyncSharePartnershipManagerInternal::S"...
0x18001bf84  mov     [rsp+0A8h+var_78], rax
0x18001bf89  mov     [rsp+0A8h+var_70], rbx
0x18001bf8e  call    cs:__imp_CoImpersonateClient
0x18001bf94  mov     [rsp+0A8h+var_88], eax
0x18001bf98  mov     [rsp+0A8h+var_88], eax
0x18001bf9c  mov     ecx, 424h
0x18001bfa1  test    eax, eax
0x18001bfa3  jns     short loc_18001BFBF
0x18001bfa5  mov     word ptr [rsp+0A8h+var_84+2], cx
0x18001bfaa  mov     [rsp+0A8h+pExceptionObject], eax
0x18001bfae  lea     rdx, _TI1J; pThrowInfo
0x18001bfb5  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18001bfba  call    _CxxThrowException_0
0x18001bfbf  mov     word ptr [rsp+0A8h+var_84], cx
0x18001bfc4  lea     rdx, [rdi+0D8h]
0x18001bfcb  lea     rcx, [rsp+0A8h+lpCriticalSection]
0x18001bfd0  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x18001bfd5  nop
0x18001bfd6  lea     rdx, [rsp+0A8h+var_48]
0x18001bfdb  mov     rcx, [rdi+90h]; this
0x18001bfe2  call    ?AddImpersonatingUser@CSyncStateManager@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CSyncStateManager::AddImpersonatingUser(void)
0x18001bfe7  lea     rcx, [rsp+0A8h+var_48]
0x18001bfec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bff1  cmp     si, 0FFFFh
0x18001bff5  setz    r8b; bool
0x18001bff9  mov     rdx, r14; unsigned __int16 *
0x18001bffc  mov     rcx, [rdi+90h]; this
0x18001c003  call    ?SetConfiguredByPolicy@CSyncStateManager@@QEAAXPEBG_N@Z; CSyncStateManager::SetConfiguredByPolicy(ushort const *,bool)
0x18001c008  nop
0x18001c009  cmp     [rsp+0A8h+var_58], bl
0x18001c00d  jz      short loc_18001C01E
0x18001c00f  mov     rcx, [rsp+0A8h+lpCriticalSection]; lpCriticalSection
0x18001c014  call    cs:__imp_LeaveCriticalSection
0x18001c01a  mov     [rsp+0A8h+var_58], bl
0x18001c01e  jmp     short loc_18001C026
0x18001c020  jmp     short loc_18001C026
0x18001c022  jmp     short loc_18001C026
0x18001c024  jmp     short $+2
0x18001c026  mov     ebx, [rsp+0A8h+var_88]
0x18001c02a  lea     rcx, [rsp+0A8h+var_88]; this
0x18001c02f  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18001c034  mov     eax, ebx
0x18001c036  mov     rcx, [rsp+0A8h+var_28]
0x18001c03e  xor     rcx, rsp; StackCookie
0x18001c041  call    __security_check_cookie
0x18001c046  mov     rbx, [rsp+0A8h+arg_10]
0x18001c04e  add     rsp, 90h
0x18001c055  pop     r14
0x18001c057  pop     rdi
0x18001c058  pop     rsi
0x18001c059  retn
```
