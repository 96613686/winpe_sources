# Windows::Networking::UX::Internal::CategoryBase::_GetActualInterfaceGuid(_GUID const &)

- ea: `0x1800520c0`
- end: `0x180052340`
- name: `?_GetActualInterfaceGuid@CategoryBase@Internal@UX@Networking@Windows@@CA?AU_GUID@@AEBU6@@Z`
- size: `640`
- prototype: `struct _GUID *__fastcall(struct _GUID *__return_ptr retstr, const struct _GUID *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180028840`
- `0x18002a068`

## callees

- `0x180014d40`
- `0x18001bdb8`
- `0x1800266f8`
- `0x18002c904`
- `0x18002cd20`
- `0x180036714`
- `0x180051ec8`
- `0x1800520c0`
- `0x180052638`
- `0x180055e24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x180052208`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x180052208`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs_s` at `0x18005212a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs_s` at `0x18005212a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005221f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005221f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800520f9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800520f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052285`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052285`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052168`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180052155`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180052197`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180052155`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180052197`

## pseudocode

```c
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
0x1800520c0  push    rbp
0x1800520c2  push    rbx
0x1800520c3  push    rsi
0x1800520c4  push    rdi
0x1800520c5  push    r12
0x1800520c7  push    r14
0x1800520c9  lea     rbp, [rsp-38h]
0x1800520ce  sub     rsp, 138h
0x1800520d5  mov     rax, cs:__security_cookie
0x1800520dc  xor     rax, rsp
0x1800520df  mov     [rbp+60h+var_40], rax
0x1800520e3  mov     r14, rdx
0x1800520e6  mov     rdi, rcx
0x1800520e9  mov     r12d, 27h ; '''
0x1800520ef  mov     r8d, r12d; cchMax
0x1800520f2  lea     rdx, [rbp+60h+sz]; lpsz
0x1800520f6  mov     rcx, r14; rguid
0x1800520f9  call    cs:__imp_StringFromGUID2
0x1800520ff  test    eax, eax
0x180052101  jz      loc_1800522C3
0x180052107  mov     [rsp+160h+var_128], 0
0x180052110  mov     qword ptr [rsp+160h+SizePointer], 26h ; '&'; int
0x180052119  lea     r9, [rbp+60h+sz]
0x18005211d  mov     r8d, r12d
0x180052120  lea     rdx, [rsp+160h+Str1]
0x180052125  lea     rcx, [rsp+160h+var_128]
0x18005212a  call    cs:__imp__o_wcstombs_s
0x180052130  test    eax, eax
0x180052132  jnz     loc_1800522E6
0x180052138  mov     [rsp+160h+var_12C], eax
0x18005213c  lea     rax, [rsp+160h+var_12C]
0x180052141  mov     qword ptr [rsp+160h+SizePointer], rax; unsigned int
0x180052146  xor     r9d, r9d; AdapterAddresses
0x180052149  xor     r8d, r8d; Reserved
0x18005214c  lea     esi, [r12+7Fh]
0x180052151  mov     edx, esi; Flags
0x180052153  xor     ecx, ecx; Family
0x180052155  call    cs:__imp_GetAdaptersAddresses
0x18005215b  cmp     eax, 6Fh ; 'o'
0x18005215e  jnz     loc_180052309
0x180052164  mov     ecx, [rsp+160h+var_12C]; cb
0x180052168  call    cs:__imp_CoTaskMemAlloc
0x18005216e  mov     rbx, rax
0x180052171  mov     [rsp+160h+var_120], rax
0x180052176  mov     rcx, [rbp+68h]; this
0x18005217a  test    rax, rax
0x18005217d  jz      loc_1800522B1
0x180052183  lea     rax, [rsp+160h+var_12C]
0x180052188  mov     qword ptr [rsp+160h+SizePointer], rax; unsigned int
0x18005218d  mov     r9, rbx; AdapterAddresses
0x180052190  xor     r8d, r8d; Reserved
0x180052193  mov     edx, esi; Flags
0x180052195  xor     ecx, ecx; Family
0x180052197  call    cs:__imp_GetAdaptersAddresses
0x18005219d  mov     rcx, [rbp+68h]; this
0x1800521a1  test    eax, eax
0x1800521a3  jnz     loc_180052316
0x1800521a9  mov     rsi, rbx
0x1800521ac  mov     r8d, r12d; MaxCount
0x1800521af  mov     rdx, [rsi+10h]; Str2
0x1800521b3  lea     rcx, [rsp+160h+Str1]; Str1
0x1800521b8  call    strncmp_0
0x1800521bd  test    eax, eax
0x1800521bf  jz      loc_18005227A
0x1800521c5  mov     rsi, [rsi+8]
0x1800521c9  test    rsi, rsi
0x1800521cc  jnz     short loc_1800521AC
0x1800521ce  mov     rsi, rbx
0x1800521d1  cmp     qword ptr [rsi+18h], 0
0x1800521d6  jz      loc_18005226D
0x1800521dc  mov     [rsp+160h+var_128], 0
0x1800521e5  mov     r9, [rsi+10h]
0x1800521e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800521ed  inc     rax
0x1800521f0  cmp     byte ptr [r9+rax], 0
0x1800521f5  jnz     short loc_1800521ED
0x1800521f7  mov     qword ptr [rsp+160h+SizePointer], rax; int
0x1800521fc  mov     r8, r12
0x1800521ff  lea     rdx, [rbp+60h+var_90]
0x180052203  lea     rcx, [rsp+160h+var_128]
0x180052208  call    cs:__imp__o_mbstowcs_s
0x18005220e  xorps   xmm0, xmm0
0x180052211  movups  xmmword ptr [rsp+160h+pclsid.Data1], xmm0
0x180052216  lea     rdx, [rsp+160h+pclsid]; pclsid
0x18005221b  lea     rcx, [rbp+60h+var_90]; lpsz
0x18005221f  call    cs:__imp_CLSIDFromString
0x180052225  mov     rcx, [rbp+68h]; this
0x180052229  test    eax, eax
0x18005222b  js      loc_18005232B
0x180052231  mov     [rsp+160h+var_130], 0
0x180052236  lea     r8, [rsp+160h+var_130]; bool *
0x18005223b  lea     rdx, [rsp+160h+pclsid]; struct _GUID *
0x180052240  mov     rcx, r14; struct _GUID *
0x180052243  call    ?IsChildVirtualAdapter@CAdapterProperties@Internal@UX@Networking@Windows@@SAJAEBU_GUID@@0PEA_N@Z; Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(_GUID const &,_GUID const &,bool *)
0x180052248  mov     rcx, [rbp+68h]; this
0x18005224c  test    eax, eax
0x18005224e  jns     short loc_180052266
0x180052250  mov     r9d, eax; char *
0x180052253  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18005225a  mov     edx, 371h; void *
0x18005225f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180052264  jmp     short loc_18005226D
0x180052266  cmp     [rsp+160h+var_130], 0
0x18005226b  jnz     short loc_1800522AA
0x18005226d  mov     rsi, [rsi+8]
0x180052271  test    rsi, rsi
0x180052274  jnz     loc_1800521D1
0x18005227a  movups  xmm0, xmmword ptr [r14]
0x18005227e  movdqu  xmmword ptr [rdi], xmm0
0x180052282  mov     rcx, rbx; pv
0x180052285  call    cs:__imp_CoTaskMemFree
0x18005228b  mov     rax, rdi
0x18005228e  mov     rcx, [rbp+60h+var_40]
0x180052292  xor     rcx, rsp; StackCookie
0x180052295  call    __security_check_cookie
0x18005229a  add     rsp, 138h
0x1800522a1  pop     r14
0x1800522a3  pop     r12
0x1800522a5  pop     rdi
0x1800522a6  pop     rsi
0x1800522a7  pop     rbx
0x1800522a8  pop     rbp
0x1800522a9  retn
0x1800522aa  movups  xmm0, xmmword ptr [rsp+160h+pclsid.Data1]
0x1800522af  jmp     short loc_18005227E
0x1800522b1  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x1800522b8  mov     edx, 34Ch; void *
0x1800522bd  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800522c3  mov     ecx, 80070057h
0x1800522c8  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800522cd  mov     r9d, eax; char *
0x1800522d0  mov     rcx, [rbp+68h]; this
0x1800522d4  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x1800522db  mov     edx, 339h; void *
0x1800522e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800522e6  mov     ecx, 80070057h
0x1800522eb  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800522f0  mov     r9d, eax; char *
0x1800522f3  mov     rcx, [rbp+68h]; this
0x1800522f7  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x1800522fe  mov     edx, 334h; void *
0x180052303  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052309  mov     rcx, [rbp+68h]; this
0x18005230d  mov     r9d, eax; char *
0x180052310  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180052316  mov     r9d, eax; char *
0x180052319  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180052320  mov     edx, 352h; void *
0x180052325  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005232b  mov     r9d, eax; char *
0x18005232e  lea     r8, aOnecoreuapNetU_14; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180052335  mov     edx, 36Eh; void *
0x18005233a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
