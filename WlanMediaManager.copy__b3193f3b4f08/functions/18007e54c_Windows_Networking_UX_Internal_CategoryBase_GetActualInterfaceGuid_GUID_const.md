# Windows::Networking::UX::Internal::CategoryBase::_GetActualInterfaceGuid(_GUID const &)

- ea: `0x18007e54c`
- end: `0x18007e7cc`
- name: `?_GetActualInterfaceGuid@CategoryBase@Internal@UX@Networking@Windows@@CA?AU_GUID@@AEBU6@@Z`
- size: `640`
- prototype: `static struct _GUID *(struct _GUID *__return_ptr __struct_ptr retstr, const struct _GUID *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18007d734`
- `0x18007e004`

## callees

- `0x180003ed0`
- `0x1800078ac`
- `0x18001b230`
- `0x18001be60`
- `0x18001be80`
- `0x18004ca20`
- `0x18007e270`
- `0x18007e54c`
- `0x180083ddc`
- `0x180089410`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x18007e694`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x18007e694`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs_s` at `0x18007e5b6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs_s` at `0x18007e5b6`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18007e5e1`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18007e623`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18007e5e1`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18007e623`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18007e585`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18007e585`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007e6ab`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007e6ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007e5f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007e5f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e711`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e711`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _GUID *__fastcall Windows::Networking::UX::Internal::CategoryBase::_GetActualInterfaceGuid(
        struct _GUID *__return_ptr retstr,
        const struct _GUID *a2)
{
  ULONG AdaptersAddresses; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  IP_ADAPTER_ADDRESSES_LH *v7; // rbx
  const char *v8; // r9
  ULONG v9; // eax
  IP_ADAPTER_ADDRESSES_LH *v10; // rsi
  IP_ADAPTER_ADDRESSES_LH *v11; // rsi
  __int64 v12; // rax
  HRESULT v13; // eax
  int IsChildVirtualAdapter; // eax
  GUID v15; // xmm0
  unsigned int v17; // eax
  unsigned int v18; // eax
  int SizePointer; // [rsp+20h] [rbp-E0h]
  unsigned int SizePointera; // [rsp+20h] [rbp-E0h]
  unsigned int SizePointerb; // [rsp+20h] [rbp-E0h]
  int SizePointerc; // [rsp+20h] [rbp-E0h]
  bool v23; // [rsp+30h] [rbp-D0h] BYREF
  ULONG v24; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD v25[2]; // [rsp+38h] [rbp-C8h] BYREF
  GUID pclsid; // [rsp+48h] [rbp-B8h] BYREF
  char Str1[40]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR v29[40]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  if ( !StringFromGUID2(a2, sz, 39) )
  {
    v17 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x339,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)v17,
      SizePointer);
  }
  v25[0] = 0;
  if ( (unsigned int)_o_wcstombs_s(v25, Str1, 39, sz) )
  {
    v18 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x334,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)v18,
      38);
  }
  v24 = 0;
  AdaptersAddresses = GetAdaptersAddresses(0, 0xA6u, 0, 0, &v24);
  if ( AdaptersAddresses != 111 )
    wil::details::in1diag3::Throw_Win32(retaddr, v5, v6, (const char *)AdaptersAddresses, SizePointera);
  v7 = (IP_ADAPTER_ADDRESSES_LH *)CoTaskMemAlloc(v24);
  v25[1] = v7;
  if ( !v7 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x34C,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      v8);
  v9 = GetAdaptersAddresses(0, 0xA6u, 0, v7, &v24);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x352,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)v9,
      SizePointerb);
  v10 = v7;
  while ( strncmp_0(Str1, v10->AdapterName, 0x27u) )
  {
    v10 = v10->Next;
    if ( !v10 )
    {
      v11 = v7;
      while ( 1 )
      {
        if ( v11->FirstUnicastAddress )
        {
          v25[0] = 0;
          v12 = -1;
          do
            ++v12;
          while ( v11->AdapterName[v12] );
          SizePointerc = v12;
          _o_mbstowcs_s(v25, v29, 39);
          pclsid = 0;
          v13 = CLSIDFromString(v29, &pclsid);
          if ( v13 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x36E,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
              (const char *)(unsigned int)v13,
              SizePointerc);
          v23 = 0;
          IsChildVirtualAdapter = Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(
                                    a2,
                                    &pclsid,
                                    &v23);
          if ( IsChildVirtualAdapter >= 0 )
          {
            if ( v23 )
            {
              v15 = pclsid;
              goto LABEL_19;
            }
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x371,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
              (const char *)(unsigned int)IsChildVirtualAdapter,
              SizePointerc);
          }
        }
        v11 = v11->Next;
        if ( !v11 )
          goto LABEL_18;
      }
    }
  }
LABEL_18:
  v15 = *a2;
LABEL_19:
  *retstr = v15;
  CoTaskMemFree(v7);
  return retstr;
}

```

## disassembly

```asm
0x18007e54c  push    rbp
0x18007e54e  push    rbx
0x18007e54f  push    rsi
0x18007e550  push    rdi
0x18007e551  push    r12
0x18007e553  push    r14
0x18007e555  lea     rbp, [rsp-38h]
0x18007e55a  sub     rsp, 138h
0x18007e561  mov     rax, cs:__security_cookie
0x18007e568  xor     rax, rsp
0x18007e56b  mov     [rbp+60h+var_40], rax
0x18007e56f  mov     r14, rdx
0x18007e572  mov     rdi, rcx
0x18007e575  mov     r12d, 27h ; '''
0x18007e57b  mov     r8d, r12d; cchMax
0x18007e57e  lea     rdx, [rbp+60h+sz]; lpsz
0x18007e582  mov     rcx, r14; rguid
0x18007e585  call    cs:__imp_StringFromGUID2
0x18007e58b  test    eax, eax
0x18007e58d  jz      loc_18007E74F
0x18007e593  mov     [rsp+160h+var_128], 0
0x18007e59c  mov     qword ptr [rsp+160h+SizePointer], 26h ; '&'; int
0x18007e5a5  lea     r9, [rbp+60h+sz]
0x18007e5a9  mov     r8d, r12d
0x18007e5ac  lea     rdx, [rsp+160h+Str1]
0x18007e5b1  lea     rcx, [rsp+160h+var_128]
0x18007e5b6  call    cs:__imp__o_wcstombs_s
0x18007e5bc  test    eax, eax
0x18007e5be  jnz     loc_18007E772
0x18007e5c4  mov     [rsp+160h+var_12C], eax
0x18007e5c8  lea     rax, [rsp+160h+var_12C]
0x18007e5cd  mov     qword ptr [rsp+160h+SizePointer], rax; unsigned int
0x18007e5d2  xor     r9d, r9d; AdapterAddresses
0x18007e5d5  xor     r8d, r8d; Reserved
0x18007e5d8  lea     esi, [r12+7Fh]
0x18007e5dd  mov     edx, esi; Flags
0x18007e5df  xor     ecx, ecx; Family
0x18007e5e1  call    cs:__imp_GetAdaptersAddresses
0x18007e5e7  cmp     eax, 6Fh ; 'o'
0x18007e5ea  jnz     loc_18007E795
0x18007e5f0  mov     ecx, [rsp+160h+var_12C]; cb
0x18007e5f4  call    cs:__imp_CoTaskMemAlloc
0x18007e5fa  mov     rbx, rax
0x18007e5fd  mov     [rsp+160h+var_120], rax
0x18007e602  mov     rcx, [rbp+68h]; this
0x18007e606  test    rax, rax
0x18007e609  jz      loc_18007E73D
0x18007e60f  lea     rax, [rsp+160h+var_12C]
0x18007e614  mov     qword ptr [rsp+160h+SizePointer], rax; unsigned int
0x18007e619  mov     r9, rbx; AdapterAddresses
0x18007e61c  xor     r8d, r8d; Reserved
0x18007e61f  mov     edx, esi; Flags
0x18007e621  xor     ecx, ecx; Family
0x18007e623  call    cs:__imp_GetAdaptersAddresses
0x18007e629  mov     rcx, [rbp+68h]; this
0x18007e62d  test    eax, eax
0x18007e62f  jnz     loc_18007E7A2
0x18007e635  mov     rsi, rbx
0x18007e638  mov     r8d, r12d; MaxCount
0x18007e63b  mov     rdx, [rsi+10h]; Str2
0x18007e63f  lea     rcx, [rsp+160h+Str1]; Str1
0x18007e644  call    strncmp_0
0x18007e649  test    eax, eax
0x18007e64b  jz      loc_18007E706
0x18007e651  mov     rsi, [rsi+8]
0x18007e655  test    rsi, rsi
0x18007e658  jnz     short loc_18007E638
0x18007e65a  mov     rsi, rbx
0x18007e65d  cmp     qword ptr [rsi+18h], 0
0x18007e662  jz      loc_18007E6F9
0x18007e668  mov     [rsp+160h+var_128], 0
0x18007e671  mov     r9, [rsi+10h]
0x18007e675  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007e679  inc     rax
0x18007e67c  cmp     byte ptr [r9+rax], 0
0x18007e681  jnz     short loc_18007E679
0x18007e683  mov     qword ptr [rsp+160h+SizePointer], rax; int
0x18007e688  mov     r8, r12
0x18007e68b  lea     rdx, [rbp+60h+var_90]
0x18007e68f  lea     rcx, [rsp+160h+var_128]
0x18007e694  call    cs:__imp__o_mbstowcs_s
0x18007e69a  xorps   xmm0, xmm0
0x18007e69d  movups  xmmword ptr [rsp+160h+pclsid.Data1], xmm0
0x18007e6a2  lea     rdx, [rsp+160h+pclsid]; pclsid
0x18007e6a7  lea     rcx, [rbp+60h+var_90]; lpsz
0x18007e6ab  call    cs:__imp_CLSIDFromString
0x18007e6b1  mov     rcx, [rbp+68h]; this
0x18007e6b5  test    eax, eax
0x18007e6b7  js      loc_18007E7B7
0x18007e6bd  mov     [rsp+160h+var_130], 0
0x18007e6c2  lea     r8, [rsp+160h+var_130]; bool *
0x18007e6c7  lea     rdx, [rsp+160h+pclsid]; struct _GUID *
0x18007e6cc  mov     rcx, r14; struct _GUID *
0x18007e6cf  call    ?IsChildVirtualAdapter@CAdapterProperties@Internal@UX@Networking@Windows@@SAJAEBU_GUID@@0PEA_N@Z; Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(_GUID const &,_GUID const &,bool *)
0x18007e6d4  mov     rcx, [rbp+68h]; this
0x18007e6d8  test    eax, eax
0x18007e6da  jns     short loc_18007E6F2
0x18007e6dc  mov     r9d, eax; char *
0x18007e6df  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007e6e6  mov     edx, 371h; void *
0x18007e6eb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007e6f0  jmp     short loc_18007E6F9
0x18007e6f2  cmp     [rsp+160h+var_130], 0
0x18007e6f7  jnz     short loc_18007E736
0x18007e6f9  mov     rsi, [rsi+8]
0x18007e6fd  test    rsi, rsi
0x18007e700  jnz     loc_18007E65D
0x18007e706  movups  xmm0, xmmword ptr [r14]
0x18007e70a  movdqu  xmmword ptr [rdi], xmm0
0x18007e70e  mov     rcx, rbx; pv
0x18007e711  call    cs:__imp_CoTaskMemFree
0x18007e717  mov     rax, rdi
0x18007e71a  mov     rcx, [rbp+60h+var_40]
0x18007e71e  xor     rcx, rsp; StackCookie
0x18007e721  call    __security_check_cookie
0x18007e726  add     rsp, 138h
0x18007e72d  pop     r14
0x18007e72f  pop     r12
0x18007e731  pop     rdi
0x18007e732  pop     rsi
0x18007e733  pop     rbx
0x18007e734  pop     rbp
0x18007e735  retn
0x18007e736  movups  xmm0, xmmword ptr [rsp+160h+pclsid.Data1]
0x18007e73b  jmp     short loc_18007E70A
0x18007e73d  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007e744  mov     edx, 34Ch; void *
0x18007e749  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18007e74f  mov     ecx, 80070057h
0x18007e754  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18007e759  mov     r9d, eax; char *
0x18007e75c  mov     rcx, [rbp+68h]; this
0x18007e760  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007e767  mov     edx, 339h; void *
0x18007e76c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e772  mov     ecx, 80070057h
0x18007e777  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18007e77c  mov     r9d, eax; char *
0x18007e77f  mov     rcx, [rbp+68h]; this
0x18007e783  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007e78a  mov     edx, 334h; void *
0x18007e78f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e795  mov     rcx, [rbp+68h]; this
0x18007e799  mov     r9d, eax; char *
0x18007e79c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18007e7a2  mov     r9d, eax; char *
0x18007e7a5  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007e7ac  mov     edx, 352h; void *
0x18007e7b1  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18007e7b7  mov     r9d, eax; char *
0x18007e7ba  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007e7c1  mov     edx, 36Eh; void *
0x18007e7c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
