# GetCapabilitySidFromName(void * *)

- ea: `0x14000c148`
- end: `0x14000c2b8`
- name: `?GetCapabilitySidFromName@@YAXPEAPEAX@Z`
- size: `368`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000b114`

## callees

- `0x140002210`
- `0x140002d50`
- `0x14000a19c`
- `0x14000c148`
- `0x14000fb94`
- `0x14000fbd0`
- `0x14000fbf0`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x14000c219`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x14000c219`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000c237`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000c237`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000c263`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14000c263`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000c243`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000c243`

## pseudocode

```c
void __fastcall GetCapabilitySidFromName(void **a1)
{
  __int64 v2; // rdx
  const wchar_t *v3; // rax
  int v4; // eax
  unsigned int v5; // r8d
  DWORD LengthSid; // edi
  HLOCAL v7; // rax
  void *v8; // rdx
  unsigned int v9; // r8d
  const char *v10; // r9
  void *v11; // rbx
  unsigned int v12; // r8d
  const char *v13; // r9
  HLOCAL v14; // [rsp+20h] [rbp-89h] BYREF
  __int128 v15; // [rsp+28h] [rbp-81h] BYREF
  _BYTE pSid[80]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v17[80]; // [rsp+90h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v15 = 0;
  v2 = 0x7FFF;
  v3 = L"Microsoft.delegatedWebFeatures_8wekyb3d8bbwe";
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v2;
  }
  while ( v2 );
  if ( !v2 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x9E, 2u, (const char *)0xC000000DLL, (int)v14);
  LOWORD(v15) = -2 - 2 * v2;
  WORD1(v15) = -2 * v2;
  *((_QWORD *)&v15 + 1) = L"Microsoft.delegatedWebFeatures_8wekyb3d8bbwe";
  memset_0(v17, 0, 0x44u);
  memset_0(pSid, 0, 0x44u);
  v4 = RtlDeriveCapabilitySidsFromName(&v15, v17, pSid);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0xA5, v5, (const char *)(unsigned int)v4, (int)v14);
  LengthSid = GetLengthSid(pSid);
  v7 = LocalAlloc(0, LengthSid);
  v11 = v7;
  v14 = v7;
  if ( !v7 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v8, v9, v10);
  if ( !CopySid(LengthSid, v7, pSid) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xAB, v12, v13);
  v14 = 0;
  *a1 = v11;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
}

```

## disassembly

```asm
0x14000c148  mov     [rsp-8+arg_8], rbx
0x14000c14d  mov     [rsp-8+arg_10], rsi
0x14000c152  push    rbp
0x14000c153  push    rdi
0x14000c154  push    r14
0x14000c156  lea     rbp, [rsp-47h]
0x14000c15b  sub     rsp, 0F0h
0x14000c162  mov     rax, cs:__security_cookie
0x14000c169  xor     rax, rsp
0x14000c16c  mov     [rbp+57h+var_20], rax
0x14000c170  mov     rsi, rcx
0x14000c173  xorps   xmm0, xmm0
0x14000c176  movups  [rsp+100h+var_D8], xmm0
0x14000c17b  mov     edx, 7FFFh
0x14000c180  lea     r10, aMicrosoftDeleg; "Microsoft.delegatedWebFeatures_8wekyb3d"...
0x14000c187  mov     rax, r10
0x14000c18a  xor     r14d, r14d
0x14000c18d  lea     r8d, [r14+2]; unsigned int
0x14000c191  cmp     [rax], r14w
0x14000c195  jz      short loc_14000C1A0
0x14000c197  add     rax, r8
0x14000c19a  sub     rdx, 1
0x14000c19e  jnz     short loc_14000C191
0x14000c1a0  mov     rax, rdx
0x14000c1a3  neg     rax
0x14000c1a6  sbb     r9d, r9d
0x14000c1a9  not     r9d
0x14000c1ac  and     r9d, 0C000000Dh; char *
0x14000c1b3  test    rdx, rdx
0x14000c1b6  jz      short loc_14000C1D7
0x14000c1b8  movzx   eax, dx
0x14000c1bb  add     ax, ax
0x14000c1be  mov     ecx, 0FFFEh
0x14000c1c3  sub     cx, ax
0x14000c1c6  mov     word ptr [rsp+100h+var_D8], cx
0x14000c1cb  add     cx, r8w
0x14000c1cf  mov     word ptr [rbp+57h+var_D8+2], cx
0x14000c1d3  mov     qword ptr [rbp+57h+var_D8+8], r10
0x14000c1d7  mov     rcx, [rbp+5Fh]; this
0x14000c1db  test    rdx, rdx
0x14000c1de  jnz     short loc_14000C1EB
0x14000c1e0  mov     edx, 9Eh; void *
0x14000c1e5  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x14000c1eb  mov     ebx, 44h ; 'D'
0x14000c1f0  mov     r8d, ebx; Size
0x14000c1f3  xor     edx, edx; Val
0x14000c1f5  lea     rcx, [rbp+57h+var_70]; void *
0x14000c1f9  call    memset_0
0x14000c1fe  mov     r8d, ebx; Size
0x14000c201  xor     edx, edx; Val
0x14000c203  lea     rcx, [rbp+57h+pSid]; void *
0x14000c207  call    memset_0
0x14000c20c  lea     r8, [rbp+57h+pSid]
0x14000c210  lea     rdx, [rbp+57h+var_70]
0x14000c214  lea     rcx, [rsp+100h+var_D8]
0x14000c219  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x14000c21f  mov     rcx, [rbp+5Fh]; this
0x14000c223  test    eax, eax
0x14000c225  jns     short loc_14000C233
0x14000c227  mov     r9d, eax; char *
0x14000c22a  lea     edx, [rbx+61h]; void *
0x14000c22d  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x14000c233  lea     rcx, [rbp+57h+pSid]; pSid
0x14000c237  call    cs:__imp_GetLengthSid
0x14000c23d  mov     edi, eax
0x14000c23f  mov     edx, eax; uBytes
0x14000c241  xor     ecx, ecx; uFlags
0x14000c243  call    cs:__imp_LocalAlloc
0x14000c249  mov     rbx, rax
0x14000c24c  mov     [rsp+100h+var_E0], rax
0x14000c251  mov     rcx, [rbp+5Fh]; this
0x14000c255  test    rax, rax
0x14000c258  jz      short loc_14000C2B2
0x14000c25a  lea     r8, [rbp+57h+pSid]; pSourceSid
0x14000c25e  mov     rdx, rax; pDestinationSid
0x14000c261  mov     ecx, edi; nDestinationSidLength
0x14000c263  call    cs:__imp_CopySid
0x14000c269  mov     rcx, [rbp+5Fh]; this
0x14000c26d  test    eax, eax
0x14000c26f  jnz     short loc_14000C27C
0x14000c271  mov     edx, 0ABh; void *
0x14000c276  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14000c27c  mov     [rsp+100h+var_E0], r14
0x14000c281  mov     [rsi], rbx
0x14000c284  lea     rcx, [rsp+100h+var_E0]
0x14000c289  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000c28e  mov     rcx, [rbp+57h+var_20]
0x14000c292  xor     rcx, rsp; StackCookie
0x14000c295  call    __security_check_cookie
0x14000c29a  lea     r11, [rsp+100h+var_10]
0x14000c2a2  mov     rbx, [r11+28h]
0x14000c2a6  mov     rsi, [r11+30h]
0x14000c2aa  mov     rsp, r11
0x14000c2ad  pop     r14
0x14000c2af  pop     rdi
0x14000c2b0  pop     rbp
0x14000c2b1  retn
0x14000c2b2  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
