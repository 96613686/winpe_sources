# CLocationWnfQuery::CreateEventForInternalUse(ulong,LOC_WNF_STATE_NAME &)

- ea: `0x1800567ac`
- end: `0x18005699b`
- name: `?CreateEventForInternalUse@CLocationWnfQuery@@SAJKAEAULOC_WNF_STATE_NAME@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(unsigned int, struct LOC_WNF_STATE_NAME *)`
- caller_count: `4`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800565f4`
- `0x1800566c0`
- `0x1800a6ec0`
- `0x1800dbd2c`

## callees

- `0x180018228`
- `0x18001e170`
- `0x18001ecbc`
- `0x18001efe0`
- `0x18001f09c`
- `0x18001f334`
- `0x1800208b0`
- `0x1800208d4`
- `0x180020994`
- `0x180020c64`
- `0x1800567ac`
- `0x18009cc78`
- `0x1800a98c0`
- `0x1800aa5ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800568f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800568f6`
- `ntdll!NtCreateWnfStateName` at `0x18005693c`
- `ntdll!NtCreateWnfStateName` at `0x18005693c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800568ec`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800568ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLocationWnfQuery::CreateEventForInternalUse(__int64 a1, struct LOC_WNF_STATE_NAME *a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  const unsigned __int16 *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  const WCHAR *v12; // rax
  signed int LastError; // eax
  int v14; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  void **v18; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v19; // [rsp+58h] [rbp-A8h]
  __int64 v20; // [rsp+68h] [rbp-98h]
  _OWORD v21[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[128]; // [rsp+90h] [rbp-70h] BYREF

  v17 = 0;
  SecurityDescriptor = 0;
  memset(v21, 0, sizeof(v21));
  v3 = std::_WChar_traits<unsigned short>::length(L"D:(A;;3;;;");
  std::wstring::_Construct<1,unsigned short const *>(v21, v4, v3);
  v18 = &ATL::CAccessToken::`vftable';
  v19 = 0;
  v20 = 0;
  if ( ATL::CAccessToken::GetEffectiveToken((ATL::CAccessToken *)&v18, 8u) )
  {
    memset_0(v22, 0, 0x78u);
    ATL::CSid::CSid((ATL::CSid *)v22);
    if ( ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>((__int64)&v18, (__int64)v22) )
    {
      v6 = ATL::CSid::Sid((ATL::CSid *)v22);
      v7 = std::_WChar_traits<unsigned short>::length(v6);
      std::wstring::_Append<unsigned short>(v21, v8, v7);
      v9 = std::_WChar_traits<unsigned short>::length(L")");
      std::wstring::_Append<unsigned short>(v21, v10, v9);
      v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21, v11);
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v12, 1u, &SecurityDescriptor, 0) )
      {
        v14 = NtCreateWnfStateName(&v17, 3, 0);
        v5 = v14 | 0x10000000;
        if ( v14 >= 0 )
        {
          *(_QWORD *)a2 = v17;
          ATL::CSid::~CSid((ATL::CSid *)v22);
          v5 = 0;
          goto LABEL_11;
        }
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
      ATL::CSid::~CSid((ATL::CSid *)v22);
    }
    else
    {
      ATL::CSid::~CSid((ATL::CSid *)v22);
      v5 = -2147418113;
    }
  }
  else
  {
    v5 = -2147024891;
  }
LABEL_11:
  v18 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v18);
  std::wstring::_Tidy_deallocate(v21);
  return v5;
}

```

## disassembly

```asm
0x1800567ac  mov     [rsp-8+arg_10], rbx
0x1800567b1  push    rbp
0x1800567b2  push    rdi
0x1800567b3  push    r14
0x1800567b5  lea     rbp, [rsp-20h]
0x1800567ba  sub     rsp, 120h
0x1800567c1  mov     rax, cs:__security_cookie
0x1800567c8  xor     rax, rsp
0x1800567cb  mov     [rbp+30h+var_20], rax
0x1800567cf  mov     rdi, rdx
0x1800567d2  mov     ebx, ecx
0x1800567d4  mov     [rsp+130h+var_E8], 0
0x1800567dd  mov     [rsp+130h+SecurityDescriptor], 0
0x1800567e6  xorps   xmm0, xmm0
0x1800567e9  movups  [rsp+130h+var_C0], xmm0
0x1800567ee  xorps   xmm1, xmm1
0x1800567f1  movdqu  [rbp+30h+var_B0], xmm1
0x1800567f6  lea     rcx, aDA3; "D:(A;;3;;;"
0x1800567fd  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180056802  mov     r8, rax
0x180056805  mov     rdx, rcx
0x180056808  lea     rcx, [rsp+130h+var_C0]
0x18005680d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180056812  nop
0x180056813  xorps   xmm0, xmm0
0x180056816  movups  [rsp+130h+var_E0], xmm0
0x18005681b  movups  [rsp+130h+var_D0], xmm0
0x180056820  lea     r14, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x180056827  mov     qword ptr [rsp+130h+var_E0], r14
0x18005682c  movdqu  [rsp+130h+var_E0+8], xmm0
0x180056832  mov     qword ptr [rsp+130h+var_D0+8], 0
0x18005683b  mov     edx, 8; unsigned int
0x180056840  lea     rcx, [rsp+130h+var_E0]; this
0x180056845  call    ?GetEffectiveToken@CAccessToken@ATL@@QEAA_NK@Z; ATL::CAccessToken::GetEffectiveToken(ulong)
0x18005684a  test    al, al
0x18005684c  jnz     short loc_180056858
0x18005684e  mov     ebx, 80070005h
0x180056853  jmp     loc_18005695F
0x180056858  xor     edx, edx; Val
0x18005685a  lea     r8d, [rdx+78h]; Size
0x18005685e  lea     rcx, [rbp+30h+var_A0]; void *
0x180056862  call    memset_0
0x180056867  lea     rcx, [rbp+30h+var_A0]; this
0x18005686b  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x180056870  nop
0x180056871  lea     rdx, [rbp+30h+var_A0]
0x180056875  lea     rcx, [rsp+130h+var_E0]
0x18005687a  call    ??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z; ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)
0x18005687f  test    al, al
0x180056881  jnz     short loc_180056896
0x180056883  lea     rcx, [rbp+30h+var_A0]; this
0x180056887  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18005688c  mov     ebx, 8000FFFFh
0x180056891  jmp     loc_18005695F
0x180056896  lea     rcx, [rbp+30h+var_A0]; this
0x18005689a  call    ?Sid@CSid@ATL@@QEBAPEBGXZ; ATL::CSid::Sid(void)
0x18005689f  mov     rcx, rax
0x1800568a2  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800568a7  mov     r8, rax
0x1800568aa  mov     rdx, rcx
0x1800568ad  lea     rcx, [rsp+130h+var_C0]
0x1800568b2  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800568b7  lea     rcx, asc_1801732C0; ")"
0x1800568be  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800568c3  mov     r8, rax
0x1800568c6  mov     rdx, rcx
0x1800568c9  lea     rcx, [rsp+130h+var_C0]
0x1800568ce  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800568d3  lea     rcx, [rsp+130h+var_C0]
0x1800568d8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800568dd  mov     rcx, rax; StringSecurityDescriptor
0x1800568e0  xor     r9d, r9d; SecurityDescriptorSize
0x1800568e3  lea     r8, [rsp+130h+SecurityDescriptor]; SecurityDescriptor
0x1800568e8  lea     edx, [r9+1]; StringSDRevision
0x1800568ec  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800568f2  test    eax, eax
0x1800568f4  jnz     short loc_180056916
0x1800568f6  call    cs:__imp_GetLastError
0x1800568fc  mov     ebx, eax
0x1800568fe  test    eax, eax
0x180056900  jle     short loc_18005690B
0x180056902  movzx   ebx, ax
0x180056905  or      ebx, 80070000h
0x18005690b  lea     rcx, [rbp+30h+var_A0]; this
0x18005690f  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180056914  jmp     short loc_18005695F
0x180056916  mov     rax, [rsp+130h+SecurityDescriptor]
0x18005691b  mov     [rsp+130h+var_100], rax
0x180056920  mov     [rsp+130h+var_108], ebx
0x180056924  mov     [rsp+130h+var_110], 0
0x18005692d  xor     r9d, r9d
0x180056930  xor     r8d, r8d
0x180056933  lea     edx, [r9+3]
0x180056937  lea     rcx, [rsp+130h+var_E8]
0x18005693c  call    cs:__imp_NtCreateWnfStateName
0x180056942  mov     ebx, eax
0x180056944  or      ebx, 10000000h
0x18005694a  jl      short loc_18005690B
0x18005694c  mov     rax, [rsp+130h+var_E8]
0x180056951  mov     [rdi], rax
0x180056954  lea     rcx, [rbp+30h+var_A0]; this
0x180056958  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18005695d  xor     ebx, ebx
0x18005695f  mov     qword ptr [rsp+130h+var_E0], r14
0x180056964  lea     rcx, [rsp+130h+var_E0]; this
0x180056969  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x18005696e  nop
0x18005696f  lea     rcx, [rsp+130h+var_C0]
0x180056974  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180056979  mov     eax, ebx
0x18005697b  mov     rcx, [rbp+30h+var_20]
0x18005697f  xor     rcx, rsp; StackCookie
0x180056982  call    __security_check_cookie
0x180056987  mov     rbx, [rsp+130h+arg_10]
0x18005698f  add     rsp, 120h
0x180056996  pop     r14
0x180056998  pop     rdi
0x180056999  pop     rbp
0x18005699a  retn
```
