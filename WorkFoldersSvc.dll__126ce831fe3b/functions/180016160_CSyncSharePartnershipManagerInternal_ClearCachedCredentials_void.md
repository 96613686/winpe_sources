# CSyncSharePartnershipManagerInternal::ClearCachedCredentials(void)

- ea: `0x180016160`
- end: `0x1800162b2`
- name: `?ClearCachedCredentials@CSyncSharePartnershipManagerInternal@@UEAAJXZ`
- size: `338`
- prototype: `__int64 __fastcall(CSyncSharePartnershipManagerInternal *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007e10`
- `0x180008b60`
- `0x180009384`
- `0x180011314`
- `0x180016160`
- `0x180023e64`
- `0x180024884`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001626f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001626f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800161f4`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800161f4`

## string_xrefs

- `0x1800161e3`: `CSyncSharePartnershipManagerInternal::ClearCachedCredentials`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSyncSharePartnershipManagerInternal::ClearCachedCredentials(
        CSyncSharePartnershipManagerInternal *this)
{
  _BYTE *v2; // rax
  char v3; // al
  HRESULT v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-78h] BYREF
  int v8; // [rsp+24h] [rbp-74h]
  char v9; // [rsp+28h] [rbp-70h]
  const char *v10; // [rsp+30h] [rbp-68h]
  __int64 v11; // [rsp+38h] [rbp-60h]
  HRESULT pExceptionObject; // [rsp+40h] [rbp-58h] BYREF
  int v13; // [rsp+44h] [rbp-54h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-50h] BYREF
  char v15; // [rsp+50h] [rbp-48h]
  const ATL::CAtlException *v16; // [rsp+58h] [rbp-40h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp-38h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_8:
      v3 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 72, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
  }
  if ( (v2[68] & 8) == 0 || v2[65] < 6u )
    goto LABEL_8;
  v3 = 1;
LABEL_9:
  v7 = 0;
  v8 = 1017;
  v9 = v3;
  v10 = "CSyncSharePartnershipManagerInternal::ClearCachedCredentials";
  v11 = 0;
  try
  {
    v4 = CoImpersonateClient();
    v7 = v4;
    if ( v4 < 0 )
    {
      HIWORD(v8) = 1021;
      pExceptionObject = v4;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v8) = 1021;
    CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(
      (__int64)&lpCriticalSection,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 216));
    CSyncStateManager::AddImpersonatingUser(*((CSyncStateManager **)this + 18), (__int64)v17);
    std::wstring::~wstring((__int64)v17);
    CSyncStateManager::ClearCachedCredentials(*((CSyncStateManager **)this + 18));
    if ( v15 )
    {
      LeaveCriticalSection(lpCriticalSection);
      v15 = 0;
    }
  }
  catch ( long v13 )
  {
    v7 = v13;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v8) = 1029;
    v7 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v8) = 1029;
    v7 = -2147418113;
  }
  catch ( const ATL::CAtlException *v16 )
  {
    HIWORD(v8) = 1029;
    v7 = *(_DWORD *)v16;
  }
  v5 = v7;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v7);
  return v5;
}

```

## disassembly

```asm
0x180016160  mov     [rsp+arg_8], rbx
0x180016165  push    rdi
0x180016166  sub     rsp, 90h
0x18001616d  mov     rax, cs:__security_cookie
0x180016174  xor     rax, rsp
0x180016177  mov     [rsp+98h+var_18], rax
0x18001617f  mov     rdi, rcx
0x180016182  lea     rcx, WPP_GLOBAL_Control
0x180016189  mov     rax, cs:WPP_GLOBAL_Control
0x180016190  cmp     rax, rcx
0x180016193  jz      short loc_1800161BD
0x180016195  test    byte ptr [rax+44h], 8
0x180016199  jz      short loc_1800161CF
0x18001619b  cmp     byte ptr [rax+41h], 6
0x18001619f  jb      short loc_1800161BD
0x1800161a1  mov     edx, 48h ; 'H'
0x1800161a6  lea     r8, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids
0x1800161ad  mov     rcx, [rax+38h]
0x1800161b1  call    WPP_SF_
0x1800161b6  mov     rax, cs:WPP_GLOBAL_Control
0x1800161bd  test    byte ptr [rax+44h], 8
0x1800161c1  jz      short loc_1800161CF
0x1800161c3  cmp     byte ptr [rax+41h], 6
0x1800161c7  jb      short loc_1800161CF
0x1800161c9  mov     al, 1
0x1800161cb  xor     ebx, ebx
0x1800161cd  jmp     short loc_1800161D3
0x1800161cf  xor     ebx, ebx
0x1800161d1  mov     al, bl
0x1800161d3  mov     [rsp+98h+var_78], ebx
0x1800161d7  mov     [rsp+98h+var_74], 3F9h
0x1800161df  mov     [rsp+98h+var_70], al
0x1800161e3  lea     rax, aCsyncsharepart_30; "CSyncSharePartnershipManagerInternal::C"...
0x1800161ea  mov     [rsp+98h+var_68], rax
0x1800161ef  mov     [rsp+98h+var_60], rbx
0x1800161f4  call    cs:__imp_CoImpersonateClient
0x1800161fa  mov     [rsp+98h+var_78], eax
0x1800161fe  mov     [rsp+98h+var_78], eax
0x180016202  mov     ecx, 3FDh
0x180016207  test    eax, eax
0x180016209  jns     short loc_180016225
0x18001620b  mov     word ptr [rsp+98h+var_74+2], cx
0x180016210  mov     [rsp+98h+pExceptionObject], eax
0x180016214  lea     rdx, _TI1J; pThrowInfo
0x18001621b  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180016220  call    _CxxThrowException_0
0x180016225  mov     word ptr [rsp+98h+var_74], cx
0x18001622a  lea     rdx, [rdi+0D8h]
0x180016231  lea     rcx, [rsp+98h+lpCriticalSection]
0x180016236  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x18001623b  nop
0x18001623c  lea     rdx, [rsp+98h+var_38]
0x180016241  mov     rcx, [rdi+90h]; this
0x180016248  call    ?AddImpersonatingUser@CSyncStateManager@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CSyncStateManager::AddImpersonatingUser(void)
0x18001624d  lea     rcx, [rsp+98h+var_38]
0x180016252  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016257  mov     rcx, [rdi+90h]; this
0x18001625e  call    ?ClearCachedCredentials@CSyncStateManager@@QEAAXXZ; CSyncStateManager::ClearCachedCredentials(void)
0x180016263  nop
0x180016264  cmp     [rsp+98h+var_48], bl
0x180016268  jz      short loc_180016279
0x18001626a  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x18001626f  call    cs:__imp_LeaveCriticalSection
0x180016275  mov     [rsp+98h+var_48], bl
0x180016279  jmp     short loc_180016281
0x18001627b  jmp     short loc_180016281
0x18001627d  jmp     short loc_180016281
0x18001627f  jmp     short $+2
0x180016281  mov     ebx, [rsp+98h+var_78]
0x180016285  lea     rcx, [rsp+98h+var_78]; this
0x18001628a  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18001628f  mov     eax, ebx
0x180016291  mov     rcx, [rsp+98h+var_18]
0x180016299  xor     rcx, rsp; StackCookie
0x18001629c  call    __security_check_cookie
0x1800162a1  mov     rbx, [rsp+98h+arg_8]
0x1800162a9  add     rsp, 90h
0x1800162b0  pop     rdi
0x1800162b1  retn
```
