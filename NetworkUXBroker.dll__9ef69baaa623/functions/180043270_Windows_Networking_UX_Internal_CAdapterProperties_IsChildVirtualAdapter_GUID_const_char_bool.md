# Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(_GUID const &,char *,bool *)

- ea: `0x180043270`
- end: `0x180043344`
- name: `?IsChildVirtualAdapter@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_GUID@@PEADPEA_N@Z`
- size: `212`
- prototype: `int(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, const struct _GUID *, char *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180041e58`

## callees

- `0x180002520`
- `0x18000e768`
- `0x180043270`
- `0x18004334c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x1800432c6`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x1800432c6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800432de`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800432de`

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
0x180043270  push    rbx
0x180043272  push    rsi
0x180043273  push    rdi
0x180043274  sub     rsp, 0B0h
0x18004327b  mov     rax, cs:__security_cookie
0x180043282  xor     rax, rsp
0x180043285  mov     [rsp+0C8h+var_28], rax
0x18004328d  mov     rdi, r9
0x180043290  mov     byte ptr [r9], 0
0x180043294  mov     rsi, rdx
0x180043297  mov     [rsp+0C8h+var_98], 0
0x1800432a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800432a4  inc     rax
0x1800432a7  cmp     byte ptr [r8+rax], 0
0x1800432ac  jnz     short loc_1800432A4
0x1800432ae  mov     r9, r8
0x1800432b1  mov     qword ptr [rsp+0C8h+var_A8], rax; int
0x1800432b6  mov     r8d, 27h ; '''
0x1800432bc  lea     rdx, [rsp+0C8h+sz]
0x1800432c1  lea     rcx, [rsp+0C8h+var_98]
0x1800432c6  call    cs:__imp__o_mbstowcs_s
0x1800432cc  xorps   xmm0, xmm0
0x1800432cf  lea     rdx, [rsp+0C8h+pclsid]; pclsid
0x1800432d4  lea     rcx, [rsp+0C8h+sz]; lpsz
0x1800432d9  movups  xmmword ptr [rsp+0C8h+pclsid.Data1], xmm0
0x1800432de  call    cs:__imp_CLSIDFromString
0x1800432e4  mov     ebx, eax
0x1800432e6  test    eax, eax
0x1800432e8  jns     short loc_18004330A
0x1800432ea  mov     edx, 378h; void *
0x1800432ef  mov     rcx, [rsp+0C8h]; this
0x1800432f7  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x1800432fe  mov     r9d, ebx; char *
0x180043301  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043306  mov     eax, ebx
0x180043308  jmp     short loc_180043329
0x18004330a  mov     r8, rdi; bool *
0x18004330d  lea     rdx, [rsp+0C8h+pclsid]; struct _GUID *
0x180043312  mov     rcx, rsi; struct _GUID *
0x180043315  call    ?IsChildVirtualAdapter@CAdapterProperties@Internal@UX@Networking@Windows@@SAJAEBU_GUID@@0PEA_N@Z; Windows::Networking::UX::Internal::CAdapterProperties::IsChildVirtualAdapter(_GUID const &,_GUID const &,bool *)
0x18004331a  mov     ebx, eax
0x18004331c  test    eax, eax
0x18004331e  jns     short loc_180043327
0x180043320  mov     edx, 379h
0x180043325  jmp     short loc_1800432EF
0x180043327  xor     eax, eax
0x180043329  mov     rcx, [rsp+0C8h+var_28]
0x180043331  xor     rcx, rsp; StackCookie
0x180043334  call    __security_check_cookie
0x180043339  add     rsp, 0B0h
0x180043340  pop     rdi
0x180043341  pop     rsi
0x180043342  pop     rbx
0x180043343  retn
```
