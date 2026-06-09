# Windows::Networking::UX::Internal::CategoryBase::_GetActualInterfaceGuid(_GUID const &)

- ea: `0x18003f27c`
- end: `0x18003f4ee`
- name: `?_GetActualInterfaceGuid@CategoryBase@Internal@UX@Networking@Windows@@CA?AU_GUID@@AEBU6@@Z`
- size: `626`
- prototype: `struct _GUID *__fastcall(struct _GUID *__return_ptr retstr, const struct _GUID *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003e424`
- `0x18003ed20`

## callees

- `0x180002520`
- `0x18000c75c`
- `0x18001a2d0`
- `0x18001a300`
- `0x18001fcd0`
- `0x18003ae50`
- `0x18003ef88`
- `0x18003efb0`
- `0x18003f27c`
- `0x18004334c`
- `0x180044a64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x18003f3c4`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x18003f3c4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs_s` at `0x18003f2e6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs_s` at `0x18003f2e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f324`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003f3db`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003f3db`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003f2b5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003f2b5`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18003f311`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18003f353`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18003f311`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18003f353`

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
  unsigned int v18; // r8d
  unsigned int v19; // eax
  unsigned int v20; // r8d
  int SizePointer; // [rsp+20h] [rbp-E0h]
  unsigned int SizePointera; // [rsp+20h] [rbp-E0h]
  unsigned int SizePointerb; // [rsp+20h] [rbp-E0h]
  int SizePointerc; // [rsp+20h] [rbp-E0h]
  bool v25; // [rsp+30h] [rbp-D0h] BYREF
  ULONG v26; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD v27[2]; // [rsp+38h] [rbp-C8h] BYREF
  GUID pclsid; // [rsp+48h] [rbp-B8h] BYREF
  char Str1[40]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR v31[40]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  if ( !StringFromGUID2(a2, sz, 39) )
  {
    v17 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x339, v18, (const char *)v17, SizePointer);
  }
  v27[0] = 0;
  if ( (unsigned int)_o_wcstombs_s(v27, Str1, 39, sz) )
  {
    v19 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x334, v20, (const char *)v19, 38);
  }
  v26 = 0;
  AdaptersAddresses = GetAdaptersAddresses(0, 0xA6u, 0, 0, &v26);
  if ( AdaptersAddresses != 111 )
    wil::details::in1diag3::Throw_Win32(retaddr, v5, v6, (const char *)AdaptersAddresses, SizePointera);
  v7 = (IP_ADAPTER_ADDRESSES_LH *)CoTaskMemAlloc(v26);
  v27[1] = v7;
  if ( !v7 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x34C,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      v8);
  v9 = GetAdaptersAddresses(0, 0xA6u, 0, v7, &v26);
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
          v27[0] = 0;
          v12 = -1;
          do
            ++v12;
          while ( v11->AdapterName[v12] );
          SizePointerc = v12;
          _o_mbstowcs_s(v27, v31, 39);
          pclsid = 0;
          v13 = CLSIDFromString(v31, &pclsid);
          if ( v13 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x36E,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
              (const char *)(unsigned int)v13,
              SizePointerc);
          v25 = 0;
          IsChildVirtualAdapter = Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(
                                    a2,
                                    &pclsid,
                                    &v25);
          if ( IsChildVirtualAdapter >= 0 )
          {
            if ( v25 )
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
0x18003f27c  push    rbp
0x18003f27e  push    rbx
0x18003f27f  push    rsi
0x18003f280  push    rdi
0x18003f281  push    r12
0x18003f283  push    r14
0x18003f285  lea     rbp, [rsp-38h]
0x18003f28a  sub     rsp, 138h
0x18003f291  mov     rax, cs:__security_cookie
0x18003f298  xor     rax, rsp
0x18003f29b  mov     [rbp+60h+var_40], rax
0x18003f29f  mov     r14, rdx
0x18003f2a2  mov     rdi, rcx
0x18003f2a5  mov     r12d, 27h ; '''
0x18003f2ab  mov     r8d, r12d; cchMax
0x18003f2ae  lea     rdx, [rbp+60h+sz]; lpsz
0x18003f2b2  mov     rcx, r14; rguid
0x18003f2b5  call    cs:__imp_StringFromGUID2
0x18003f2bb  test    eax, eax
0x18003f2bd  jz      loc_18003F47F
0x18003f2c3  mov     [rsp+160h+var_128], 0
0x18003f2cc  mov     qword ptr [rsp+160h+SizePointer], 26h ; '&'; int
0x18003f2d5  lea     r9, [rbp+60h+sz]
0x18003f2d9  mov     r8d, r12d
0x18003f2dc  lea     rdx, [rsp+160h+Str1]
0x18003f2e1  lea     rcx, [rsp+160h+var_128]
0x18003f2e6  call    cs:__imp__o_wcstombs_s
0x18003f2ec  test    eax, eax
0x18003f2ee  jnz     loc_18003F49B
0x18003f2f4  mov     [rsp+160h+var_12C], eax
0x18003f2f8  lea     rax, [rsp+160h+var_12C]
0x18003f2fd  mov     qword ptr [rsp+160h+SizePointer], rax; unsigned int
0x18003f302  xor     r9d, r9d; AdapterAddresses
0x18003f305  xor     r8d, r8d; Reserved
0x18003f308  lea     esi, [r12+7Fh]
0x18003f30d  mov     edx, esi; Flags
0x18003f30f  xor     ecx, ecx; Family
0x18003f311  call    cs:__imp_GetAdaptersAddresses
0x18003f317  cmp     eax, 6Fh ; 'o'
0x18003f31a  jnz     loc_18003F4B7
0x18003f320  mov     ecx, [rsp+160h+var_12C]; cb
0x18003f324  call    cs:__imp_CoTaskMemAlloc
0x18003f32a  mov     rbx, rax
0x18003f32d  mov     [rsp+160h+var_120], rax
0x18003f332  mov     rcx, [rbp+68h]; this
0x18003f336  test    rax, rax
0x18003f339  jz      loc_18003F46D
0x18003f33f  lea     rax, [rsp+160h+var_12C]
0x18003f344  mov     qword ptr [rsp+160h+SizePointer], rax; unsigned int
0x18003f349  mov     r9, rbx; AdapterAddresses
0x18003f34c  xor     r8d, r8d; Reserved
0x18003f34f  mov     edx, esi; Flags
0x18003f351  xor     ecx, ecx; Family
0x18003f353  call    cs:__imp_GetAdaptersAddresses
0x18003f359  mov     rcx, [rbp+68h]; this
0x18003f35d  test    eax, eax
0x18003f35f  jnz     loc_18003F4C4
0x18003f365  mov     rsi, rbx
0x18003f368  mov     r8d, r12d; MaxCount
0x18003f36b  mov     rdx, [rsi+10h]; Str2
0x18003f36f  lea     rcx, [rsp+160h+Str1]; Str1
0x18003f374  call    strncmp_0
0x18003f379  test    eax, eax
0x18003f37b  jz      loc_18003F436
0x18003f381  mov     rsi, [rsi+8]
0x18003f385  test    rsi, rsi
0x18003f388  jnz     short loc_18003F368
0x18003f38a  mov     rsi, rbx
0x18003f38d  cmp     qword ptr [rsi+18h], 0
0x18003f392  jz      loc_18003F429
0x18003f398  mov     [rsp+160h+var_128], 0
0x18003f3a1  mov     r9, [rsi+10h]
0x18003f3a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f3a9  inc     rax
0x18003f3ac  cmp     byte ptr [r9+rax], 0
0x18003f3b1  jnz     short loc_18003F3A9
0x18003f3b3  mov     qword ptr [rsp+160h+SizePointer], rax; int
0x18003f3b8  mov     r8, r12
0x18003f3bb  lea     rdx, [rbp+60h+var_90]
0x18003f3bf  lea     rcx, [rsp+160h+var_128]
0x18003f3c4  call    cs:__imp__o_mbstowcs_s
0x18003f3ca  xorps   xmm0, xmm0
0x18003f3cd  movups  xmmword ptr [rsp+160h+pclsid.Data1], xmm0
0x18003f3d2  lea     rdx, [rsp+160h+pclsid]; pclsid
0x18003f3d7  lea     rcx, [rbp+60h+var_90]; lpsz
0x18003f3db  call    cs:__imp_CLSIDFromString
0x18003f3e1  mov     rcx, [rbp+68h]; this
0x18003f3e5  test    eax, eax
0x18003f3e7  js      loc_18003F4D9
0x18003f3ed  mov     [rsp+160h+var_130], 0
0x18003f3f2  lea     r8, [rsp+160h+var_130]; bool *
0x18003f3f7  lea     rdx, [rsp+160h+pclsid]; struct _GUID *
0x18003f3fc  mov     rcx, r14; struct _GUID *
0x18003f3ff  call    ?IsChildVirtualAdapter@CAdapterProperties@Internal@UX@Networking@Windows@@SAJAEBU_GUID@@0PEA_N@Z; Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(_GUID const &,_GUID const &,bool *)
0x18003f404  mov     rcx, [rbp+68h]; this
0x18003f408  test    eax, eax
0x18003f40a  jns     short loc_18003F422
0x18003f40c  mov     r9d, eax; char *
0x18003f40f  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18003f416  mov     edx, 371h; void *
0x18003f41b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f420  jmp     short loc_18003F429
0x18003f422  cmp     [rsp+160h+var_130], 0
0x18003f427  jnz     short loc_18003F466
0x18003f429  mov     rsi, [rsi+8]
0x18003f42d  test    rsi, rsi
0x18003f430  jnz     loc_18003F38D
0x18003f436  movups  xmm0, xmmword ptr [r14]
0x18003f43a  movdqu  xmmword ptr [rdi], xmm0
0x18003f43e  mov     rcx, rbx; pv
0x18003f441  call    cs:__imp_CoTaskMemFree
0x18003f447  mov     rax, rdi
0x18003f44a  mov     rcx, [rbp+60h+var_40]
0x18003f44e  xor     rcx, rsp; StackCookie
0x18003f451  call    __security_check_cookie
0x18003f456  add     rsp, 138h
0x18003f45d  pop     r14
0x18003f45f  pop     r12
0x18003f461  pop     rdi
0x18003f462  pop     rsi
0x18003f463  pop     rbx
0x18003f464  pop     rbp
0x18003f465  retn
0x18003f466  movups  xmm0, xmmword ptr [rsp+160h+pclsid.Data1]
0x18003f46b  jmp     short loc_18003F43A
0x18003f46d  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18003f474  mov     edx, 34Ch; void *
0x18003f479  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18003f47f  mov     ecx, 80070057h
0x18003f484  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003f489  mov     r9d, eax; char *
0x18003f48c  mov     rcx, [rbp+68h]; this
0x18003f490  mov     edx, 339h; void *
0x18003f495  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003f49b  mov     ecx, 80070057h
0x18003f4a0  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003f4a5  mov     r9d, eax; char *
0x18003f4a8  mov     rcx, [rbp+68h]; this
0x18003f4ac  mov     edx, 334h; void *
0x18003f4b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003f4b7  mov     rcx, [rbp+68h]; this
0x18003f4bb  mov     r9d, eax; char *
0x18003f4be  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003f4c4  mov     r9d, eax; char *
0x18003f4c7  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18003f4ce  mov     edx, 352h; void *
0x18003f4d3  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18003f4d9  mov     r9d, eax; char *
0x18003f4dc  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18003f4e3  mov     edx, 36Eh; void *
0x18003f4e8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
