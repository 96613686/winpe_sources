# ConvertIdentityToSid(ushort const *,_GUID const &,uchar *,ushort *)

- ea: `0x180017d88`
- end: `0x1800180b9`
- name: `?ConvertIdentityToSid@@YAKPEBGAEBU_GUID@@PEAEPEAG@Z`
- size: `817`
- prototype: `__int64 __fastcall(WCHAR *, const struct _GUID *, unsigned __int8 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800157d4`
- `0x18001640c`

## callees

- `0x180017d88`
- `0x1800181e8`
- `0x180018728`
- `0x1800187a8`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017e8c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017e8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017ebf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017ebf`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x180017f07`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x180017f07`
- `bcrypt!BCryptHashData` at `0x180017f45`
- `bcrypt!BCryptHashData` at `0x180017f45`
- `bcrypt!BCryptFinishHash` at `0x180017f63`
- `bcrypt!BCryptFinishHash` at `0x180017f63`
- `bcrypt!BCryptDestroyHash` at `0x180017f76`
- `bcrypt!BCryptDestroyHash` at `0x180017f76`
- `bcrypt!BCryptCreateHash` at `0x180017f27`
- `bcrypt!BCryptCreateHash` at `0x180017f27`
- `ntdll!RtlLengthRequiredSid` at `0x180017e39`
- `ntdll!RtlLengthRequiredSid` at `0x180017e39`
- `ntdll!RtlSubAuthoritySid` at `0x180017faa`
- `ntdll!RtlSubAuthoritySid` at `0x180017fbe`
- `ntdll!RtlSubAuthoritySid` at `0x180017fce`
- `ntdll!RtlSubAuthoritySid` at `0x180017fde`
- `ntdll!RtlSubAuthoritySid` at `0x180017ff1`
- `ntdll!RtlSubAuthoritySid` at `0x180018005`
- `ntdll!RtlSubAuthoritySid` at `0x180018019`
- `ntdll!RtlSubAuthoritySid` at `0x18001802e`
- `ntdll!RtlSubAuthoritySid` at `0x180018043`
- `ntdll!RtlSubAuthoritySid` at `0x180018058`
- `ntdll!RtlSubAuthoritySid` at `0x18001806d`
- `ntdll!RtlSubAuthoritySid` at `0x180017faa`
- `ntdll!RtlSubAuthoritySid` at `0x180017fbe`
- `ntdll!RtlSubAuthoritySid` at `0x180017fce`
- `ntdll!RtlSubAuthoritySid` at `0x180017fde`
- `ntdll!RtlSubAuthoritySid` at `0x180017ff1`
- `ntdll!RtlSubAuthoritySid` at `0x180018005`
- `ntdll!RtlSubAuthoritySid` at `0x180018019`
- `ntdll!RtlSubAuthoritySid` at `0x18001802e`
- `ntdll!RtlSubAuthoritySid` at `0x180018043`
- `ntdll!RtlSubAuthoritySid` at `0x180018058`
- `ntdll!RtlSubAuthoritySid` at `0x18001806d`
- `ntdll!RtlInitializeSid` at `0x180017f9f`
- `ntdll!RtlInitializeSid` at `0x180017f9f`

## string_xrefs

- `0x180017dc2`: `ConvertIdentityToSid`

## pseudocode

```c
__int64 __fastcall ConvertIdentityToSid(WCHAR *a1, const struct _GUID *a2, unsigned __int8 *a3, unsigned __int16 *a4)
{
  unsigned __int64 v8; // rdi
  unsigned __int16 v9; // ax
  unsigned __int64 v10; // rdx
  unsigned __int16 v11; // cx
  unsigned int v12; // ebx
  ULONG v13; // r14d
  unsigned __int64 v14; // rbx
  WCHAR *v15; // rax
  WCHAR *v16; // r12
  unsigned __int64 v17; // rbx
  __int64 v18; // rcx
  WCHAR *v19; // rcx
  ULONG Data1; // ebx
  ULONG Data2; // edi
  unsigned int v22; // r14d
  ULONG Data3; // esi
  unsigned int v24; // r15d
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-29h] BYREF
  ULONG cbInput[2]; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v28[2]; // [rsp+50h] [rbp-19h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+60h] [rbp-9h] BYREF
  UCHAR pbOutput[4]; // [rsp+68h] [rbp-1h] BYREF
  unsigned int v31; // [rsp+6Ch] [rbp+3h]
  unsigned int v32; // [rsp+70h] [rbp+7h]
  unsigned int v33; // [rsp+74h] [rbp+Bh]
  unsigned int v34; // [rsp+78h] [rbp+Fh]

  *(_WORD *)&IdentifierAuthority.Value[4] = 2816;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  phHash = 0;
  v28[1] = "ConvertIdentityToSid";
  *(_QWORD *)cbInput = 0;
  v28[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10);
  if ( !a1 )
    goto LABEL_36;
  v8 = -1;
  do
    ++v8;
  while ( a1[v8] );
  if ( !v8 || !a4 )
    goto LABEL_36;
  v9 = RtlLengthRequiredSid(0xBu);
  v11 = *a4;
  *a4 = v9;
  if ( v11 >= v9 )
  {
    if ( a3 )
    {
      if ( (int)ULongLongMult(v8, v10, (unsigned __int64 *)cbInput) < 0
        || (v13 = cbInput[0],
            v14 = *(_QWORD *)cbInput + 2LL,
            (unsigned __int64)(*(_QWORD *)cbInput + 2LL) < *(_QWORD *)cbInput) )
      {
        v12 = 111;
        goto LABEL_37;
      }
      v15 = (WCHAR *)LocalAlloc(0x40u, *(_QWORD *)cbInput + 2LL);
      v16 = v15;
      if ( !v15 )
      {
        v12 = 14;
        goto LABEL_37;
      }
      v17 = v14 >> 1;
      if ( v17 )
      {
        if ( v17 <= 0x7FFFFFFF )
        {
          v18 = 2147483646;
          do
          {
            if ( !v18 )
              break;
            if ( !*a1 )
              break;
            *v15++ = *a1++;
            --v18;
            --v17;
          }
          while ( v17 );
          v19 = v15 - 1;
          if ( v17 )
            v19 = v15;
          *v19 = 0;
          if ( v17 )
          {
            CharUpperBuffW(v16, v8);
            if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &phHash, 0, 0, 0, 0, 0) < 0 )
              __fastfail(7u);
            if ( BCryptHashData(phHash, (PUCHAR)v16, v13, 0) < 0 )
              __fastfail(7u);
            if ( BCryptFinishHash(phHash, pbOutput, 0x14u, 0) < 0 )
              __fastfail(7u);
            BCryptDestroyHash(phHash);
            Data1 = a2->Data1;
            Data2 = a2->Data2;
            v22 = *(_DWORD *)a2->Data4;
            phHash = 0;
            Data3 = a2->Data3;
            v24 = *(_DWORD *)&a2->Data4[4];
            RtlInitializeSid(a3, &IdentifierAuthority, 0xBu);
            *RtlSubAuthoritySid(a3, 0) = 96;
            *RtlSubAuthoritySid(a3, 1u) = Data1;
            *RtlSubAuthoritySid(a3, 2u) = Data2;
            *RtlSubAuthoritySid(a3, 3u) = Data3;
            *RtlSubAuthoritySid(a3, 4u) = _byteswap_ulong(v22);
            *RtlSubAuthoritySid(a3, 5u) = _byteswap_ulong(v24);
            *RtlSubAuthoritySid(a3, 6u) = _byteswap_ulong(*(unsigned int *)pbOutput);
            *RtlSubAuthoritySid(a3, 7u) = _byteswap_ulong(v31);
            *RtlSubAuthoritySid(a3, 8u) = _byteswap_ulong(v32);
            *RtlSubAuthoritySid(a3, 9u) = _byteswap_ulong(v33);
            *RtlSubAuthoritySid(a3, 0xAu) = _byteswap_ulong(v34);
            v12 = 0;
            goto LABEL_21;
          }
        }
        else
        {
          *v15 = 0;
        }
      }
      v12 = 111;
LABEL_21:
      LocalFree(v16);
      goto LABEL_37;
    }
LABEL_36:
    v12 = 87;
    goto LABEL_37;
  }
  v12 = 122;
LABEL_37:
  CLogBlock::~CLogBlock((CLogBlock *)v28);
  return v12;
}

```

## disassembly

```asm
0x180017d88  mov     [rsp-8+arg_8], rbx
0x180017d8d  push    rbp
0x180017d8e  push    rsi
0x180017d8f  push    rdi
0x180017d90  push    r12
0x180017d92  push    r13
0x180017d94  push    r14
0x180017d96  push    r15
0x180017d98  lea     rbp, [rsp-27h]
0x180017d9d  sub     rsp, 90h
0x180017da4  mov     rax, cs:__security_cookie
0x180017dab  xor     rax, rsp
0x180017dae  mov     [rbp+57h+var_40], rax
0x180017db2  xor     r14d, r14d
0x180017db5  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 0B00h
0x180017dbb  mov     rbx, r9
0x180017dbe  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r14d
0x180017dc2  lea     r9, aConvertidentit; "ConvertIdentityToSid"
0x180017dc9  mov     [rbp+57h+phHash], r14
0x180017dcd  mov     [rbp+57h+var_68], r9
0x180017dd1  mov     r13, r8
0x180017dd4  mov     r15, rdx
0x180017dd7  mov     qword ptr [rbp+57h+cbInput], r14
0x180017ddb  mov     rsi, rcx
0x180017dde  mov     [rbp+57h+var_70], r14
0x180017de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180017de9  lea     rax, WPP_GLOBAL_Control
0x180017df0  cmp     rcx, rax
0x180017df3  jz      short loc_180017E0B
0x180017df5  test    dword ptr [rcx+1Ch], 400h
0x180017dfc  jz      short loc_180017E0B
0x180017dfe  mov     rcx, [rcx+10h]
0x180017e02  lea     edx, [r14+0Ah]
0x180017e06  call    WPP_SF_s
0x180017e0b  test    rsi, rsi
0x180017e0e  jz      loc_180018082
0x180017e14  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017e18  inc     rdi
0x180017e1b  cmp     [rsi+rdi*2], r14w
0x180017e20  jnz     short loc_180017E18
0x180017e22  test    rdi, rdi
0x180017e25  jz      loc_180018082
0x180017e2b  test    rbx, rbx
0x180017e2e  jz      loc_180018082
0x180017e34  mov     ecx, 0Bh; SubAuthorityCount
0x180017e39  call    cs:__imp_RtlLengthRequiredSid
0x180017e3f  movzx   ecx, word ptr [rbx]
0x180017e42  mov     [rbx], ax
0x180017e45  cmp     cx, ax
0x180017e48  jnb     short loc_180017E54
0x180017e4a  mov     ebx, 7Ah ; 'z'
0x180017e4f  jmp     loc_180018087
0x180017e54  test    r13, r13
0x180017e57  jz      loc_180018082
0x180017e5d  lea     r8, [rbp+57h+cbInput]; unsigned __int64 *
0x180017e61  mov     rcx, rdi; unsigned __int64
0x180017e64  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180017e69  test    eax, eax
0x180017e6b  jns     short loc_180017E77
0x180017e6d  mov     ebx, 6Fh ; 'o'
0x180017e72  jmp     loc_180018087
0x180017e77  mov     r14, qword ptr [rbp+57h+cbInput]
0x180017e7b  lea     rbx, [r14+2]
0x180017e7f  cmp     rbx, r14
0x180017e82  jb      short loc_180017E6D
0x180017e84  mov     rdx, rbx; uBytes
0x180017e87  mov     ecx, 40h ; '@'; uFlags
0x180017e8c  call    cs:__imp_LocalAlloc
0x180017e92  xor     r8d, r8d
0x180017e95  mov     r12, rax
0x180017e98  test    rax, rax
0x180017e9b  jnz     short loc_180017EA5
0x180017e9d  lea     ebx, [rax+0Eh]
0x180017ea0  jmp     loc_180018087
0x180017ea5  shr     rbx, 1
0x180017ea8  jz      short loc_180017EB7
0x180017eaa  cmp     rbx, 7FFFFFFFh
0x180017eb1  jbe     short loc_180017ECA
0x180017eb3  mov     [rax], r8w
0x180017eb7  mov     ebx, 6Fh ; 'o'
0x180017ebc  mov     rcx, r12; hMem
0x180017ebf  call    cs:__imp_LocalFree
0x180017ec5  jmp     loc_180018087
0x180017eca  mov     ecx, 7FFFFFFEh
0x180017ecf  test    rcx, rcx
0x180017ed2  jz      short loc_180017EF0
0x180017ed4  movzx   edx, word ptr [rsi]
0x180017ed7  test    dx, dx
0x180017eda  jz      short loc_180017EF0
0x180017edc  mov     [rax], dx
0x180017edf  add     rsi, 2
0x180017ee3  add     rax, 2
0x180017ee7  dec     rcx
0x180017eea  sub     rbx, 1
0x180017eee  jnz     short loc_180017ECF
0x180017ef0  xor     esi, esi
0x180017ef2  lea     rcx, [rax-2]
0x180017ef6  test    rbx, rbx
0x180017ef9  cmovnz  rcx, rax
0x180017efd  mov     [rcx], si
0x180017f00  jz      short loc_180017EB7
0x180017f02  mov     edx, edi; cchLength
0x180017f04  mov     rcx, r12; lpsz
0x180017f07  call    cs:__imp_CharUpperBuffW
0x180017f0d  mov     [rsp+0C0h+dwFlags], esi; dwFlags
0x180017f11  lea     rdx, [rbp+57h+phHash]; phHash
0x180017f15  mov     [rsp+0C0h+cbSecret], esi; cbSecret
0x180017f19  lea     ecx, [rsi+31h]; hAlgorithm
0x180017f1c  xor     r9d, r9d; cbHashObject
0x180017f1f  mov     [rsp+0C0h+pbSecret], rsi; pbSecret
0x180017f24  xor     r8d, r8d; pbHashObject
0x180017f27  call    cs:__imp_BCryptCreateHash
0x180017f2d  lea     ebx, [rsi+7]
0x180017f30  test    eax, eax
0x180017f32  jns     short loc_180017F38
0x180017f34  mov     ecx, ebx
0x180017f36  int     29h; Win8: RtlFailFast(ecx)
0x180017f38  mov     rcx, [rbp+57h+phHash]; hHash
0x180017f3c  xor     r9d, r9d; dwFlags
0x180017f3f  mov     r8d, r14d; cbInput
0x180017f42  mov     rdx, r12; pbInput
0x180017f45  call    cs:__imp_BCryptHashData
0x180017f4b  test    eax, eax
0x180017f4d  jns     short loc_180017F54
0x180017f4f  mov     rcx, rbx
0x180017f52  int     29h; Win8: RtlFailFast(ecx)
0x180017f54  mov     rcx, [rbp+57h+phHash]; hHash
0x180017f58  lea     rdx, [rbp+57h+pbOutput]; pbOutput
0x180017f5c  xor     r9d, r9d; dwFlags
0x180017f5f  lea     r8d, [r9+14h]; cbOutput
0x180017f63  call    cs:__imp_BCryptFinishHash
0x180017f69  test    eax, eax
0x180017f6b  jns     short loc_180017F72
0x180017f6d  mov     rcx, rbx
0x180017f70  int     29h; Win8: RtlFailFast(ecx)
0x180017f72  mov     rcx, [rbp+57h+phHash]; hHash
0x180017f76  call    cs:__imp_BCryptDestroyHash
0x180017f7c  mov     ebx, [r15]
0x180017f7f  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180017f83  movzx   edi, word ptr [r15+4]
0x180017f88  mov     r8b, 0Bh; SubAuthorityCount
0x180017f8b  mov     r14d, [r15+8]
0x180017f8f  mov     rcx, r13; Sid
0x180017f92  mov     [rbp+57h+phHash], rsi
0x180017f96  movzx   esi, word ptr [r15+6]
0x180017f9b  mov     r15d, [r15+0Ch]
0x180017f9f  call    cs:__imp_RtlInitializeSid
0x180017fa5  xor     edx, edx; SubAuthority
0x180017fa7  mov     rcx, r13; Sid
0x180017faa  call    cs:__imp_RtlSubAuthoritySid
0x180017fb0  mov     edx, 1; SubAuthority
0x180017fb5  mov     rcx, r13; Sid
0x180017fb8  mov     dword ptr [rax], 60h ; '`'
0x180017fbe  call    cs:__imp_RtlSubAuthoritySid
0x180017fc4  mov     edx, 2; SubAuthority
0x180017fc9  mov     rcx, r13; Sid
0x180017fcc  mov     [rax], ebx
0x180017fce  call    cs:__imp_RtlSubAuthoritySid
0x180017fd4  mov     edx, 3; SubAuthority
0x180017fd9  mov     rcx, r13; Sid
0x180017fdc  mov     [rax], edi
0x180017fde  call    cs:__imp_RtlSubAuthoritySid
0x180017fe4  mov     edx, 4; SubAuthority
0x180017fe9  mov     rcx, r13; Sid
0x180017fec  bswap   r14d
0x180017fef  mov     [rax], esi
0x180017ff1  call    cs:__imp_RtlSubAuthoritySid
0x180017ff7  mov     edx, 5; SubAuthority
0x180017ffc  mov     rcx, r13; Sid
0x180017fff  bswap   r15d
0x180018002  mov     [rax], r14d
0x180018005  call    cs:__imp_RtlSubAuthoritySid
0x18001800b  mov     edx, 6; SubAuthority
0x180018010  mov     rcx, r13; Sid
0x180018013  mov     [rax], r15d
0x180018016  mov     ebx, dword ptr [rbp+57h+pbOutput]
0x180018019  call    cs:__imp_RtlSubAuthoritySid
0x18001801f  bswap   ebx
0x180018021  mov     edx, 7; SubAuthority
0x180018026  mov     rcx, r13; Sid
0x180018029  mov     [rax], ebx
0x18001802b  mov     ebx, [rbp+57h+var_54]
0x18001802e  call    cs:__imp_RtlSubAuthoritySid
0x180018034  bswap   ebx
0x180018036  mov     edx, 8; SubAuthority
0x18001803b  mov     rcx, r13; Sid
0x18001803e  mov     [rax], ebx
0x180018040  mov     ebx, [rbp+57h+var_50]
0x180018043  call    cs:__imp_RtlSubAuthoritySid
0x180018049  bswap   ebx
0x18001804b  mov     edx, 9; SubAuthority
0x180018050  mov     rcx, r13; Sid
0x180018053  mov     [rax], ebx
0x180018055  mov     ebx, [rbp+57h+var_4C]
0x180018058  call    cs:__imp_RtlSubAuthoritySid
0x18001805e  bswap   ebx
0x180018060  mov     edx, 0Ah; SubAuthority
0x180018065  mov     rcx, r13; Sid
0x180018068  mov     [rax], ebx
0x18001806a  mov     ebx, [rbp+57h+var_48]
0x18001806d  call    cs:__imp_RtlSubAuthoritySid
0x180018073  bswap   ebx
0x180018075  xor     r8d, r8d
0x180018078  mov     [rax], ebx
0x18001807a  mov     ebx, r8d
0x18001807d  jmp     loc_180017EBC
0x180018082  mov     ebx, 57h ; 'W'
0x180018087  lea     rcx, [rbp+57h+var_70]; this
0x18001808b  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x180018090  mov     eax, ebx
0x180018092  mov     rcx, [rbp+57h+var_40]
0x180018096  xor     rcx, rsp; StackCookie
0x180018099  call    __security_check_cookie
0x18001809e  mov     rbx, [rsp+0C0h+arg_8]
0x1800180a6  add     rsp, 90h
0x1800180ad  pop     r15
0x1800180af  pop     r14
0x1800180b1  pop     r13
0x1800180b3  pop     r12
0x1800180b5  pop     rdi
0x1800180b6  pop     rsi
0x1800180b7  pop     rbp
0x1800180b8  retn
```
