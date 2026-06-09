# GetSecurityDescriptor(void *,void *,void *,tagPACKAGEDISPINFO *,int *)

- ea: `0x180027cc4`
- end: `0x180027e15`
- name: `?GetSecurityDescriptor@@YAJPEAX00PEAUtagPACKAGEDISPINFO@@PEAH@Z`
- size: `337`
- prototype: `__int64 __fastcall(void *, void *, void *, struct tagPACKAGEDISPINFO *, int *pbAccessStatus)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027a58`

## callees

- `0x1800016d0`
- `0x1800234b0`
- `0x180027cc4`
- `0x18002ada8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027d39`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027d39`
- `USERENV!RsopAccessCheckByType` at `0x180027de2`
- `USERENV!RsopAccessCheckByType` at `0x180027de2`
- `adsldpc!ADSIFreeColumn` at `0x180027df1`
- `adsldpc!ADSIFreeColumn` at `0x180027df1`

## string_xrefs

- `0x180027d03`: `nTSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall GetSecurityDescriptor(
        void *a1,
        void *a2,
        void *a3,
        struct tagPACKAGEDISPINFO *a4,
        int *pbAccessStatus)
{
  HRESULT v8; // ebx
  PADSVALUE pADsValues; // rbx
  HLOCAL v10; // rax
  void *v11; // rcx
  DWORD pdwGrantedAccessMask; // [rsp+60h] [rbp-31h] BYREF
  struct ads_search_column v14; // [rsp+68h] [rbp-29h] BYREF
  struct _GENERIC_MAPPING pGenericMapping; // [rsp+90h] [rbp-1h] BYREF

  memset(&v14, 0, sizeof(v14));
  v8 = DSGetAndValidateColumn(a1, a2, ADSTYPE_NT_SECURITY_DESCRIPTOR, L"nTSecurityDescriptor", &v14);
  if ( v8 >= 0 )
  {
    if ( v14.dwNumValues )
    {
      pADsValues = v14.pADsValues;
      v10 = LocalAlloc(0, v14.pADsValues->Boolean);
      *((_QWORD *)a4 + 17) = v10;
      if ( !v10 )
      {
        v8 = -2147024882;
LABEL_10:
        ADSIFreeColumn(a1, &v14);
        return (unsigned int)v8;
      }
      *((_DWORD *)a4 + 36) = pADsValues->Boolean;
      memcpy_0(v10, pADsValues->OctetString.lpValue, pADsValues->Boolean);
    }
    else
    {
      *((_QWORD *)a4 + 17) = 0;
    }
    v8 = 0;
    if ( pbAccessStatus && a3 )
    {
      v11 = (void *)*((_QWORD *)a4 + 17);
      pGenericMapping.GenericRead = 131220;
      pGenericMapping.GenericWrite = 131112;
      pGenericMapping.GenericExecute = 131076;
      pGenericMapping.GenericAll = 983551;
      pdwGrantedAccessMask = 0;
      v8 = RsopAccessCheckByType(
             v11,
             0,
             a3,
             0x80000000,
             0,
             0,
             &pGenericMapping,
             0,
             0,
             &pdwGrantedAccessMask,
             pbAccessStatus);
    }
    goto LABEL_10;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180027cc4  push    rbp
0x180027cc6  push    rbx
0x180027cc7  push    rsi
0x180027cc8  push    rdi
0x180027cc9  push    r14
0x180027ccb  push    r15
0x180027ccd  lea     rbp, [rsp-27h]
0x180027cd2  sub     rsp, 0B8h
0x180027cd9  mov     rax, cs:__security_cookie
0x180027ce0  xor     rax, rsp
0x180027ce3  mov     [rbp+4Fh+var_40], rax
0x180027ce7  mov     r14, [rbp+4Fh+arg_20]
0x180027ceb  xor     eax, eax
0x180027ced  xorps   xmm0, xmm0
0x180027cf0  mov     [rbp+4Fh+var_78.hReserved], rax
0x180027cf4  lea     rax, [rbp+4Fh+var_78]
0x180027cf8  mov     rdi, r9
0x180027cfb  mov     rsi, r8
0x180027cfe  mov     [rsp+0E0h+pObjectTypeList], rax; struct ads_search_column *
0x180027d03  lea     r9, aNtsecuritydesc; "nTSecurityDescriptor"
0x180027d0a  mov     r8d, 19h; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x180027d10  mov     r15, rcx
0x180027d13  movups  xmmword ptr [rbp+4Fh+var_78.pszAttrName], xmm0
0x180027d17  movups  xmmword ptr [rbp+4Fh+var_78.pADsValues], xmm0
0x180027d1b  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180027d20  mov     ebx, eax
0x180027d22  test    eax, eax
0x180027d24  js      loc_180027DF7
0x180027d2a  cmp     [rbp+4Fh+var_78.dwNumValues], 0
0x180027d2e  jz      short loc_180027D70
0x180027d30  mov     rbx, [rbp+4Fh+var_78.pADsValues]
0x180027d34  xor     ecx, ecx; uFlags
0x180027d36  mov     edx, [rbx+8]; uBytes
0x180027d39  call    cs:__imp_LocalAlloc
0x180027d3f  mov     [rdi+88h], rax
0x180027d46  mov     rcx, rax; void *
0x180027d49  test    rax, rax
0x180027d4c  jnz     short loc_180027D58
0x180027d4e  mov     ebx, 8007000Eh
0x180027d53  jmp     loc_180027DEA
0x180027d58  mov     eax, [rbx+8]
0x180027d5b  mov     [rdi+90h], eax
0x180027d61  mov     r8d, [rbx+8]; Size
0x180027d65  mov     rdx, [rbx+10h]; Src
0x180027d69  call    memcpy_0
0x180027d6e  jmp     short loc_180027D7B
0x180027d70  mov     qword ptr [rdi+88h], 0
0x180027d7b  xor     ebx, ebx
0x180027d7d  test    r14, r14
0x180027d80  jz      short loc_180027DEA
0x180027d82  test    rsi, rsi
0x180027d85  jz      short loc_180027DEA
0x180027d87  mov     rcx, [rdi+88h]; pSecurityDescriptor
0x180027d8e  lea     rax, [rbp+4Fh+var_80]
0x180027d92  mov     [rsp+0E0h+pbAccessStatus], r14; pbAccessStatus
0x180027d97  mov     r9d, 80000000h; dwDesiredAccessMask
0x180027d9d  mov     [rsp+0E0h+pdwGrantedAccessMask], rax; pdwGrantedAccessMask
0x180027da2  mov     r8, rsi; pRsopToken
0x180027da5  mov     [rsp+0E0h+pdwPrivilegeSetLength], rbx; pdwPrivilegeSetLength
0x180027daa  lea     rax, [rbp+4Fh+var_50]
0x180027dae  mov     [rsp+0E0h+pPrivilegeSet], rbx; pPrivilegeSet
0x180027db3  xor     edx, edx; pPrincipalSelfSid
0x180027db5  mov     [rsp+0E0h+pGenericMapping], rax; pGenericMapping
0x180027dba  mov     [rsp+0E0h+ObjectTypeListLength], ebx; ObjectTypeListLength
0x180027dbe  mov     [rsp+0E0h+pObjectTypeList], rbx; pObjectTypeList
0x180027dc3  mov     [rbp+4Fh+var_50.GenericRead], 20094h
0x180027dca  mov     [rbp+4Fh+var_50.GenericWrite], 20028h
0x180027dd1  mov     [rbp+4Fh+var_50.GenericExecute], 20004h
0x180027dd8  mov     [rbp+4Fh+var_50.GenericAll], 0F01FFh
0x180027ddf  mov     [rbp+4Fh+var_80], ebx
0x180027de2  call    cs:__imp_RsopAccessCheckByType
0x180027de8  mov     ebx, eax
0x180027dea  lea     rdx, [rbp+4Fh+var_78]
0x180027dee  mov     rcx, r15
0x180027df1  call    cs:__imp_ADSIFreeColumn
0x180027df7  mov     eax, ebx
0x180027df9  mov     rcx, [rbp+4Fh+var_40]
0x180027dfd  xor     rcx, rsp; StackCookie
0x180027e00  call    __security_check_cookie
0x180027e05  add     rsp, 0B8h
0x180027e0c  pop     r15
0x180027e0e  pop     r14
0x180027e10  pop     rdi
0x180027e11  pop     rsi
0x180027e12  pop     rbx
0x180027e13  pop     rbp
0x180027e14  retn
```
