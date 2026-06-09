# Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(_GUID const &,char *,bool *)

- ea: `0x1800546b4`
- end: `0x180054788`
- name: `?IsChildVirtualAdapter@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_GUID@@PEADPEA_N@Z`
- size: `212`
- prototype: `int(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, const struct _GUID *, char *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003108`

## callees

- `0x180014d40`
- `0x18001cb10`
- `0x18002cd20`
- `0x1800546b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x18005470a`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x18005470a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180054722`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180054722`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(
        Windows::Networking::UX::Internal::CAdapterProperties *this,
        const struct _GUID *a2,
        char *a3,
        bool *a4)
{
  __int64 v6; // rax
  HRESULT IsChildVirtualAdapter; // ebx
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-A8h]
  __int64 v11; // [rsp+30h] [rbp-98h] BYREF
  GUID pclsid; // [rsp+38h] [rbp-90h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *a4 = 0;
  v11 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  v10 = v6;
  _o_mbstowcs_s(&v11, sz, 39);
  pclsid = 0;
  IsChildVirtualAdapter = CLSIDFromString(sz, &pclsid);
  if ( IsChildVirtualAdapter < 0 )
  {
    v8 = 888;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
      (const char *)(unsigned int)IsChildVirtualAdapter,
      v10);
    return (unsigned int)IsChildVirtualAdapter;
  }
  IsChildVirtualAdapter = Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(a2, &pclsid, a4);
  if ( IsChildVirtualAdapter < 0 )
  {
    v8 = 889;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x1800546b4  push    rbx
0x1800546b6  push    rsi
0x1800546b7  push    rdi
0x1800546b8  sub     rsp, 0B0h
0x1800546bf  mov     rax, cs:__security_cookie
0x1800546c6  xor     rax, rsp
0x1800546c9  mov     [rsp+0C8h+var_28], rax
0x1800546d1  mov     rdi, r9
0x1800546d4  mov     byte ptr [r9], 0
0x1800546d8  mov     rsi, rdx
0x1800546db  mov     [rsp+0C8h+var_98], 0
0x1800546e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800546e8  inc     rax
0x1800546eb  cmp     byte ptr [r8+rax], 0
0x1800546f0  jnz     short loc_1800546E8
0x1800546f2  mov     r9, r8
0x1800546f5  mov     qword ptr [rsp+0C8h+var_A8], rax; int
0x1800546fa  mov     r8d, 27h ; '''
0x180054700  lea     rdx, [rsp+0C8h+sz]
0x180054705  lea     rcx, [rsp+0C8h+var_98]
0x18005470a  call    cs:__imp__o_mbstowcs_s
0x180054710  xorps   xmm0, xmm0
0x180054713  lea     rdx, [rsp+0C8h+pclsid]; pclsid
0x180054718  lea     rcx, [rsp+0C8h+sz]; lpsz
0x18005471d  movups  xmmword ptr [rsp+0C8h+pclsid.Data1], xmm0
0x180054722  call    cs:__imp_CLSIDFromString
0x180054728  mov     ebx, eax
0x18005472a  test    eax, eax
0x18005472c  jns     short loc_18005474E
0x18005472e  mov     edx, 378h; void *
0x180054733  mov     rcx, [rsp+0C8h]; this
0x18005473b  lea     r8, aOnecoreuapNetU_2; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180054742  mov     r9d, ebx; char *
0x180054745  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005474a  mov     eax, ebx
0x18005474c  jmp     short loc_18005476D
0x18005474e  mov     r8, rdi; bool *
0x180054751  lea     rdx, [rsp+0C8h+pclsid]; struct _GUID *
0x180054756  mov     rcx, rsi; struct _GUID *
0x180054759  call    ?IsChildVirtualAdapter@CAdapterProperties@Internal@UX@Networking@Windows@@SAJAEBU_GUID@@0PEA_N@Z; Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(_GUID const &,_GUID const &,bool *)
0x18005475e  mov     ebx, eax
0x180054760  test    eax, eax
0x180054762  jns     short loc_18005476B
0x180054764  mov     edx, 379h
0x180054769  jmp     short loc_180054733
0x18005476b  xor     eax, eax
0x18005476d  mov     rcx, [rsp+0C8h+var_28]
0x180054775  xor     rcx, rsp; StackCookie
0x180054778  call    __security_check_cookie
0x18005477d  add     rsp, 0B0h
0x180054784  pop     rdi
0x180054785  pop     rsi
0x180054786  pop     rbx
0x180054787  retn
```
