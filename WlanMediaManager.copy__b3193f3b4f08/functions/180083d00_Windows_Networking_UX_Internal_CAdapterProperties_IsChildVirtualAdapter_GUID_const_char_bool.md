# Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(_GUID const &,char *,bool *)

- ea: `0x180083d00`
- end: `0x180083dd4`
- name: `?IsChildVirtualAdapter@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_GUID@@PEADPEA_N@Z`
- size: `212`
- prototype: `int(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, const struct _GUID *, char *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180082b60`

## callees

- `0x180003ed0`
- `0x1800097b4`
- `0x180083d00`
- `0x180083ddc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x180083d56`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x180083d56`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180083d6e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180083d6e`

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
0x180083d00  push    rbx
0x180083d02  push    rsi
0x180083d03  push    rdi
0x180083d04  sub     rsp, 0B0h
0x180083d0b  mov     rax, cs:__security_cookie
0x180083d12  xor     rax, rsp
0x180083d15  mov     [rsp+0C8h+var_28], rax
0x180083d1d  mov     rdi, r9
0x180083d20  mov     byte ptr [r9], 0
0x180083d24  mov     rsi, rdx
0x180083d27  mov     [rsp+0C8h+var_98], 0
0x180083d30  or      rax, 0FFFFFFFFFFFFFFFFh
0x180083d34  inc     rax
0x180083d37  cmp     byte ptr [r8+rax], 0
0x180083d3c  jnz     short loc_180083D34
0x180083d3e  mov     r9, r8
0x180083d41  mov     qword ptr [rsp+0C8h+var_A8], rax; int
0x180083d46  mov     r8d, 27h ; '''
0x180083d4c  lea     rdx, [rsp+0C8h+sz]
0x180083d51  lea     rcx, [rsp+0C8h+var_98]
0x180083d56  call    cs:__imp__o_mbstowcs_s
0x180083d5c  xorps   xmm0, xmm0
0x180083d5f  lea     rdx, [rsp+0C8h+pclsid]; pclsid
0x180083d64  lea     rcx, [rsp+0C8h+sz]; lpsz
0x180083d69  movups  xmmword ptr [rsp+0C8h+pclsid.Data1], xmm0
0x180083d6e  call    cs:__imp_CLSIDFromString
0x180083d74  mov     ebx, eax
0x180083d76  test    eax, eax
0x180083d78  jns     short loc_180083D9A
0x180083d7a  mov     edx, 378h; void *
0x180083d7f  mov     rcx, [rsp+0C8h]; this
0x180083d87  lea     r8, aOnecoreuapNetU_4; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180083d8e  mov     r9d, ebx; char *
0x180083d91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083d96  mov     eax, ebx
0x180083d98  jmp     short loc_180083DB9
0x180083d9a  mov     r8, rdi; bool *
0x180083d9d  lea     rdx, [rsp+0C8h+pclsid]; struct _GUID *
0x180083da2  mov     rcx, rsi; struct _GUID *
0x180083da5  call    ?IsChildVirtualAdapter@CAdapterProperties@Internal@UX@Networking@Windows@@SAJAEBU_GUID@@0PEA_N@Z; Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(_GUID const &,_GUID const &,bool *)
0x180083daa  mov     ebx, eax
0x180083dac  test    eax, eax
0x180083dae  jns     short loc_180083DB7
0x180083db0  mov     edx, 379h
0x180083db5  jmp     short loc_180083D7F
0x180083db7  xor     eax, eax
0x180083db9  mov     rcx, [rsp+0C8h+var_28]
0x180083dc1  xor     rcx, rsp; StackCookie
0x180083dc4  call    __security_check_cookie
0x180083dc9  add     rsp, 0B0h
0x180083dd0  pop     rdi
0x180083dd1  pop     rsi
0x180083dd2  pop     rbx
0x180083dd3  retn
```
