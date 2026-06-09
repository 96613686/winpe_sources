# ConvertIdentityToSid(ushort const *,_GUID const &,uchar *,ushort *)

- ea: `0x18000e660`
- end: `0x18000e950`
- name: `?ConvertIdentityToSid@@YAKPEBGAEBU_GUID@@PEAEPEAG@Z`
- size: `752`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int8 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800130e0`

## callees

- `0x180003560`
- `0x18000e660`
- `0x18000e988`
- `0x1800191ac`
- `0x180019750`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x18000e792`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x18000e792`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e75b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e75b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e90a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e90a`
- `ntdll!RtlSubAuthoritySid` at `0x18000e838`
- `ntdll!RtlSubAuthoritySid` at `0x18000e84c`
- `ntdll!RtlSubAuthoritySid` at `0x18000e85c`
- `ntdll!RtlSubAuthoritySid` at `0x18000e86c`
- `ntdll!RtlSubAuthoritySid` at `0x18000e87f`
- `ntdll!RtlSubAuthoritySid` at `0x18000e893`
- `ntdll!RtlSubAuthoritySid` at `0x18000e8a7`
- `ntdll!RtlSubAuthoritySid` at `0x18000e8bc`
- `ntdll!RtlSubAuthoritySid` at `0x18000e8d1`
- `ntdll!RtlSubAuthoritySid` at `0x18000e8e6`
- `ntdll!RtlSubAuthoritySid` at `0x18000e8fb`
- `ntdll!RtlSubAuthoritySid` at `0x18000e838`
- `ntdll!RtlSubAuthoritySid` at `0x18000e84c`
- `ntdll!RtlSubAuthoritySid` at `0x18000e85c`
- `ntdll!RtlSubAuthoritySid` at `0x18000e86c`
- `ntdll!RtlSubAuthoritySid` at `0x18000e87f`
- `ntdll!RtlSubAuthoritySid` at `0x18000e893`
- `ntdll!RtlSubAuthoritySid` at `0x18000e8a7`
- `ntdll!RtlSubAuthoritySid` at `0x18000e8bc`
- `ntdll!RtlSubAuthoritySid` at `0x18000e8d1`
- `ntdll!RtlSubAuthoritySid` at `0x18000e8e6`
- `ntdll!RtlSubAuthoritySid` at `0x18000e8fb`
- `ntdll!RtlLengthRequiredSid` at `0x18000e70e`
- `ntdll!RtlLengthRequiredSid` at `0x18000e70e`
- `ntdll!RtlInitializeSid` at `0x18000e82d`
- `ntdll!RtlInitializeSid` at `0x18000e82d`
- `bcrypt!BCryptDestroyHash` at `0x18000e804`
- `bcrypt!BCryptDestroyHash` at `0x18000e804`
- `bcrypt!BCryptCreateHash` at `0x18000e7b3`
- `bcrypt!BCryptCreateHash` at `0x18000e7b3`
- `bcrypt!BCryptHashData` at `0x18000e7d3`
- `bcrypt!BCryptHashData` at `0x18000e7d3`
- `bcrypt!BCryptFinishHash` at `0x18000e7f1`
- `bcrypt!BCryptFinishHash` at `0x18000e7f1`

## string_xrefs

- `0x18000e69a`: `ConvertIdentityToSid`

## pseudocode

```c
__int64 __fastcall ConvertIdentityToSid(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int8 *a3,
        unsigned __int16 *a4)
{
  unsigned __int128 v4; // rax
  __int64 v7; // r15
  unsigned __int64 v9; // rbx
  unsigned __int16 v10; // cx
  unsigned int v11; // ebx
  WCHAR *v12; // r12
  ULONG v13; // ebx
  ULONG v14; // esi
  unsigned int v15; // r14d
  ULONG v16; // edi
  unsigned int v17; // r15d
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v20[3]; // [rsp+48h] [rbp-21h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+60h] [rbp-9h] BYREF
  UCHAR pbOutput[4]; // [rsp+68h] [rbp-1h] BYREF
  unsigned int v23; // [rsp+6Ch] [rbp+3h]
  unsigned int v24; // [rsp+70h] [rbp+7h]
  unsigned int v25; // [rsp+74h] [rbp+Bh]
  unsigned int v26; // [rsp+78h] [rbp+Fh]

  *((_QWORD *)&v4 + 1) = a2;
  *(_WORD *)&IdentifierAuthority.Value[4] = 2816;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  phHash = 0;
  v20[1] = "ConvertIdentityToSid";
  v7 = *((_QWORD *)&v4 + 1);
  v20[0] = 0;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "ConvertIdentityToSid");
  }
  if ( !a1 )
    goto LABEL_27;
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  if ( !v9 || !a4 )
    goto LABEL_27;
  LOWORD(v4) = RtlLengthRequiredSid(0xBu);
  v10 = *a4;
  *a4 = v4;
  if ( v10 < (unsigned __int16)v4 )
  {
    v11 = 122;
    goto LABEL_28;
  }
  if ( !a3 )
  {
LABEL_27:
    v11 = 87;
    goto LABEL_28;
  }
  v4 = v9 * (unsigned __int128)2uLL;
  if ( is_mul_ok(v9, 2u) && 2 * v9 + 2 >= 2 * v9 )
  {
    *(_QWORD *)&v4 = LocalAlloc(0x40u, 2 * v9 + 2);
    v12 = (WCHAR *)v4;
    if ( (_QWORD)v4 )
    {
      if ( (int)StringCbCopyW((unsigned __int16 *)v4, 2 * v9 + 2, a1) >= 0 )
      {
        CharUpperBuffW(v12, v9);
        if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &phHash, 0, 0, 0, 0, 0) < 0 )
          __fastfail(7u);
        if ( BCryptHashData(phHash, (PUCHAR)v12, 2 * v9, 0) < 0 )
          __fastfail(7u);
        if ( BCryptFinishHash(phHash, pbOutput, 0x14u, 0) < 0 )
          __fastfail(7u);
        BCryptDestroyHash(phHash);
        v13 = *(_DWORD *)v7;
        v14 = *(unsigned __int16 *)(v7 + 6);
        v15 = *(_DWORD *)(v7 + 8);
        phHash = 0;
        v16 = *(unsigned __int16 *)(v7 + 4);
        v17 = *(_DWORD *)(v7 + 12);
        RtlInitializeSid(a3, &IdentifierAuthority, 0xBu);
        *RtlSubAuthoritySid(a3, 0) = 96;
        *RtlSubAuthoritySid(a3, 1u) = v13;
        *RtlSubAuthoritySid(a3, 2u) = v16;
        *RtlSubAuthoritySid(a3, 3u) = v14;
        *RtlSubAuthoritySid(a3, 4u) = _byteswap_ulong(v15);
        *RtlSubAuthoritySid(a3, 5u) = _byteswap_ulong(v17);
        *RtlSubAuthoritySid(a3, 6u) = _byteswap_ulong(*(unsigned int *)pbOutput);
        *RtlSubAuthoritySid(a3, 7u) = _byteswap_ulong(v23);
        *RtlSubAuthoritySid(a3, 8u) = _byteswap_ulong(v24);
        *RtlSubAuthoritySid(a3, 9u) = _byteswap_ulong(v25);
        *RtlSubAuthoritySid(a3, 0xAu) = _byteswap_ulong(v26);
        v11 = 0;
      }
      else
      {
        v11 = 111;
      }
      LocalFree(v12);
    }
    else
    {
      v11 = 14;
    }
  }
  else
  {
    v11 = 111;
  }
LABEL_28:
  CLogBlock::~CLogBlock((CLogBlock *)v20, *((__int64 *)&v4 + 1), (__int64)a3);
  return v11;
}

```

## disassembly

```asm
0x18000e660  mov     [rsp-8+arg_8], rbx
0x18000e665  push    rbp
0x18000e666  push    rsi
0x18000e667  push    rdi
0x18000e668  push    r12
0x18000e66a  push    r13
0x18000e66c  push    r14
0x18000e66e  push    r15
0x18000e670  lea     rbp, [rsp-27h]
0x18000e675  sub     rsp, 90h
0x18000e67c  mov     rax, cs:__security_cookie
0x18000e683  xor     rax, rsp
0x18000e686  mov     [rbp+57h+var_40], rax
0x18000e68a  xor     r12d, r12d
0x18000e68d  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 0B00h
0x18000e693  mov     rdi, r9
0x18000e696  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r12d
0x18000e69a  lea     r9, aConvertidentit; "ConvertIdentityToSid"
0x18000e6a1  mov     [rbp+57h+phHash], r12
0x18000e6a5  mov     [rbp+57h+var_70], r9
0x18000e6a9  mov     r13, r8
0x18000e6ac  mov     r15, rdx
0x18000e6af  mov     [rbp+57h+var_78], r12
0x18000e6b3  mov     r14, rcx
0x18000e6b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6bd  lea     rax, WPP_GLOBAL_Control
0x18000e6c4  cmp     rcx, rax
0x18000e6c7  jz      short loc_18000E6E0
0x18000e6c9  test    dword ptr [rcx+1Ch], 400h
0x18000e6d0  jz      short loc_18000E6E0
0x18000e6d2  mov     rcx, [rcx+10h]
0x18000e6d6  lea     edx, [r12+0Ah]
0x18000e6db  call    WPP_SF_s
0x18000e6e0  test    r14, r14
0x18000e6e3  jz      loc_18000E919
0x18000e6e9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e6ed  inc     rbx
0x18000e6f0  cmp     [r14+rbx*2], r12w
0x18000e6f5  jnz     short loc_18000E6ED
0x18000e6f7  test    rbx, rbx
0x18000e6fa  jz      loc_18000E919
0x18000e700  test    rdi, rdi
0x18000e703  jz      loc_18000E919
0x18000e709  mov     ecx, 0Bh; SubAuthorityCount
0x18000e70e  call    cs:__imp_RtlLengthRequiredSid
0x18000e714  movzx   ecx, word ptr [rdi]
0x18000e717  mov     [rdi], ax
0x18000e71a  cmp     cx, ax
0x18000e71d  jnb     short loc_18000E729
0x18000e71f  mov     ebx, 7Ah ; 'z'
0x18000e724  jmp     loc_18000E91E
0x18000e729  test    r13, r13
0x18000e72c  jz      loc_18000E919
0x18000e732  mov     eax, 2
0x18000e737  mul     rbx
0x18000e73a  mov     rsi, rax
0x18000e73d  test    rdx, rdx
0x18000e740  jnz     loc_18000E912
0x18000e746  lea     rdi, [rax+2]
0x18000e74a  cmp     rdi, rax
0x18000e74d  jb      loc_18000E912
0x18000e753  mov     rdx, rdi; uBytes
0x18000e756  mov     ecx, 40h ; '@'; uFlags
0x18000e75b  call    cs:__imp_LocalAlloc
0x18000e761  mov     r12, rax
0x18000e764  test    rax, rax
0x18000e767  jnz     short loc_18000E771
0x18000e769  lea     ebx, [rax+0Eh]
0x18000e76c  jmp     loc_18000E91E
0x18000e771  mov     r8, r14; unsigned __int16 *
0x18000e774  mov     rdx, rdi; unsigned __int64
0x18000e777  mov     rcx, r12; unsigned __int16 *
0x18000e77a  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e77f  xor     edi, edi
0x18000e781  test    eax, eax
0x18000e783  jns     short loc_18000E78D
0x18000e785  lea     ebx, [rdi+6Fh]
0x18000e788  jmp     loc_18000E907
0x18000e78d  mov     edx, ebx; cchLength
0x18000e78f  mov     rcx, r12; lpsz
0x18000e792  call    cs:__imp_CharUpperBuffW
0x18000e798  xor     r9d, r9d; cbHashObject
0x18000e79b  mov     [rsp+0C0h+dwFlags], edi; dwFlags
0x18000e79f  mov     [rsp+0C0h+cbSecret], edi; cbSecret
0x18000e7a3  lea     rdx, [rbp+57h+phHash]; phHash
0x18000e7a7  xor     r8d, r8d; pbHashObject
0x18000e7aa  mov     [rsp+0C0h+pbSecret], rdi; pbSecret
0x18000e7af  lea     ecx, [r9+31h]; hAlgorithm
0x18000e7b3  call    cs:__imp_BCryptCreateHash
0x18000e7b9  mov     ebx, 7
0x18000e7be  test    eax, eax
0x18000e7c0  jns     short loc_18000E7C6
0x18000e7c2  mov     ecx, ebx
0x18000e7c4  int     29h; Win8: RtlFailFast(ecx)
0x18000e7c6  mov     rcx, [rbp+57h+phHash]; hHash
0x18000e7ca  mov     r8d, esi; cbInput
0x18000e7cd  xor     r9d, r9d; dwFlags
0x18000e7d0  mov     rdx, r12; pbInput
0x18000e7d3  call    cs:__imp_BCryptHashData
0x18000e7d9  test    eax, eax
0x18000e7db  jns     short loc_18000E7E2
0x18000e7dd  mov     rcx, rbx
0x18000e7e0  int     29h; Win8: RtlFailFast(ecx)
0x18000e7e2  mov     rcx, [rbp+57h+phHash]; hHash
0x18000e7e6  lea     rdx, [rbp+57h+pbOutput]; pbOutput
0x18000e7ea  xor     r9d, r9d; dwFlags
0x18000e7ed  lea     r8d, [r9+14h]; cbOutput
0x18000e7f1  call    cs:__imp_BCryptFinishHash
0x18000e7f7  test    eax, eax
0x18000e7f9  jns     short loc_18000E800
0x18000e7fb  mov     rcx, rbx
0x18000e7fe  int     29h; Win8: RtlFailFast(ecx)
0x18000e800  mov     rcx, [rbp+57h+phHash]; hHash
0x18000e804  call    cs:__imp_BCryptDestroyHash
0x18000e80a  mov     ebx, [r15]
0x18000e80d  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18000e811  movzx   esi, word ptr [r15+6]
0x18000e816  mov     r8b, 0Bh; SubAuthorityCount
0x18000e819  mov     r14d, [r15+8]
0x18000e81d  mov     rcx, r13; Sid
0x18000e820  mov     [rbp+57h+phHash], rdi
0x18000e824  movzx   edi, word ptr [r15+4]
0x18000e829  mov     r15d, [r15+0Ch]
0x18000e82d  call    cs:__imp_RtlInitializeSid
0x18000e833  xor     edx, edx; SubAuthority
0x18000e835  mov     rcx, r13; Sid
0x18000e838  call    cs:__imp_RtlSubAuthoritySid
0x18000e83e  mov     edx, 1; SubAuthority
0x18000e843  mov     rcx, r13; Sid
0x18000e846  mov     dword ptr [rax], 60h ; '`'
0x18000e84c  call    cs:__imp_RtlSubAuthoritySid
0x18000e852  mov     edx, 2; SubAuthority
0x18000e857  mov     rcx, r13; Sid
0x18000e85a  mov     [rax], ebx
0x18000e85c  call    cs:__imp_RtlSubAuthoritySid
0x18000e862  mov     edx, 3; SubAuthority
0x18000e867  mov     rcx, r13; Sid
0x18000e86a  mov     [rax], edi
0x18000e86c  call    cs:__imp_RtlSubAuthoritySid
0x18000e872  mov     edx, 4; SubAuthority
0x18000e877  mov     rcx, r13; Sid
0x18000e87a  bswap   r14d
0x18000e87d  mov     [rax], esi
0x18000e87f  call    cs:__imp_RtlSubAuthoritySid
0x18000e885  mov     edx, 5; SubAuthority
0x18000e88a  mov     rcx, r13; Sid
0x18000e88d  bswap   r15d
0x18000e890  mov     [rax], r14d
0x18000e893  call    cs:__imp_RtlSubAuthoritySid
0x18000e899  mov     edx, 6; SubAuthority
0x18000e89e  mov     rcx, r13; Sid
0x18000e8a1  mov     [rax], r15d
0x18000e8a4  mov     ebx, dword ptr [rbp+57h+pbOutput]
0x18000e8a7  call    cs:__imp_RtlSubAuthoritySid
0x18000e8ad  bswap   ebx
0x18000e8af  mov     edx, 7; SubAuthority
0x18000e8b4  mov     rcx, r13; Sid
0x18000e8b7  mov     [rax], ebx
0x18000e8b9  mov     ebx, [rbp+57h+var_54]
0x18000e8bc  call    cs:__imp_RtlSubAuthoritySid
0x18000e8c2  bswap   ebx
0x18000e8c4  mov     edx, 8; SubAuthority
0x18000e8c9  mov     rcx, r13; Sid
0x18000e8cc  mov     [rax], ebx
0x18000e8ce  mov     ebx, [rbp+57h+var_50]
0x18000e8d1  call    cs:__imp_RtlSubAuthoritySid
0x18000e8d7  bswap   ebx
0x18000e8d9  mov     edx, 9; SubAuthority
0x18000e8de  mov     rcx, r13; Sid
0x18000e8e1  mov     [rax], ebx
0x18000e8e3  mov     ebx, [rbp+57h+var_4C]
0x18000e8e6  call    cs:__imp_RtlSubAuthoritySid
0x18000e8ec  bswap   ebx
0x18000e8ee  mov     edx, 0Ah; SubAuthority
0x18000e8f3  mov     rcx, r13; Sid
0x18000e8f6  mov     [rax], ebx
0x18000e8f8  mov     ebx, [rbp+57h+var_48]
0x18000e8fb  call    cs:__imp_RtlSubAuthoritySid
0x18000e901  bswap   ebx
0x18000e903  mov     [rax], ebx
0x18000e905  xor     ebx, ebx
0x18000e907  mov     rcx, r12; hMem
0x18000e90a  call    cs:__imp_LocalFree
0x18000e910  jmp     short loc_18000E91E
0x18000e912  mov     ebx, 6Fh ; 'o'
0x18000e917  jmp     short loc_18000E91E
0x18000e919  mov     ebx, 57h ; 'W'
0x18000e91e  lea     rcx, [rbp+57h+var_78]; this
0x18000e922  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x18000e927  mov     eax, ebx
0x18000e929  mov     rcx, [rbp+57h+var_40]
0x18000e92d  xor     rcx, rsp; StackCookie
0x18000e930  call    __security_check_cookie
0x18000e935  mov     rbx, [rsp+0C0h+arg_8]
0x18000e93d  add     rsp, 90h
0x18000e944  pop     r15
0x18000e946  pop     r14
0x18000e948  pop     r13
0x18000e94a  pop     r12
0x18000e94c  pop     rdi
0x18000e94d  pop     rsi
0x18000e94e  pop     rbp
0x18000e94f  retn
```
