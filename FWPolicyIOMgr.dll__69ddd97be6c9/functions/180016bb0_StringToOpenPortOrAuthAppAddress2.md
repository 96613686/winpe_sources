# StringToOpenPortOrAuthAppAddress2

- ea: `0x180016bb0`
- end: `0x180016d5c`
- name: `StringToOpenPortOrAuthAppAddress2`
- size: `428`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180016b90`
- `0x180023f80`
- `0x180035900`

## callees

- `0x1800042c4`
- `0x180005de4`
- `0x180008a40`
- `0x180016bb0`
- `0x18001f650`
- `0x18001ffd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016c6b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016c6b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180016c88`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180016c88`
- `fwbase!FwFree` at `0x180016d23`
- `fwbase!FwFree` at `0x180016d23`
- `fwbase!FwStringCopy` at `0x180016c03`
- `fwbase!FwStringCopy` at `0x180016c03`
- `fwbase!FwIcfIpV4SubNetsCanonize` at `0x180016ce0`
- `fwbase!FwIcfIpV4SubNetsCanonize` at `0x180016ce0`
- `fwbase!FwIcfIpV6SubNetsCanonize` at `0x180016d06`
- `fwbase!FwIcfIpV6SubNetsCanonize` at `0x180016d06`

## pseudocode

```c
__int64 __fastcall StringToOpenPortOrAuthAppAddress2(__int64 a1, __int64 a2, unsigned int a3)
{
  int v6; // ebx
  LPCOLESTR v7; // rcx
  __int64 v8; // rdx
  wchar_t *i; // rcx
  wchar_t *v10; // rax
  wchar_t *String; // [rsp+20h] [rbp-40h] BYREF
  wchar_t *Context; // [rsp+28h] [rbp-38h] BYREF
  __int128 v14; // [rsp+30h] [rbp-30h] BYREF
  __int128 v15; // [rsp+40h] [rbp-20h] BYREF

  Context = 0;
  String = 0;
  v14 = 0;
  v15 = 0;
  memset_0((void *)a2, 0, 0x48u);
  v6 = FwStringCopy(a1, &String);
  if ( v6 >= 0 )
  {
    if ( String && *String && (unsigned int)_o__wcsicmp(String, L"*") )
    {
      for ( i = String; ; i = 0 )
      {
        v10 = wcstok_s(i, &WF_ADDR_TOKEN_DELIMITER_STR, &Context);
        if ( !v10 )
        {
          LODWORD(v14) = *(_DWORD *)(a2 + 8);
          *((_QWORD *)&v14 + 1) = *(_QWORD *)(a2 + 16);
          FwIcfIpV4SubNetsCanonize(&v14);
          *(_DWORD *)(a2 + 8) = v14;
          *(_QWORD *)(a2 + 16) = *((_QWORD *)&v14 + 1);
          LODWORD(v15) = *(_DWORD *)(a2 + 40);
          *((_QWORD *)&v15 + 1) = *(_QWORD *)(a2 + 48);
          FwIcfIpV6SubNetsCanonize(&v15);
          *(_DWORD *)(a2 + 40) = v15;
          *(_QWORD *)(a2 + 48) = *((_QWORD *)&v15 + 1);
          goto LABEL_18;
        }
        v6 = FwParseAddressToken2(v10, (struct _tag_FW_ADDRESSES *)a2, a3);
        if ( v6 < 0 )
          break;
      }
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v8 = 172;
        goto LABEL_5;
      }
    }
    else
    {
      v6 = 0;
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v8 = 171;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v6);
    }
  }
LABEL_18:
  FwFree(String);
  if ( v6 < 0 )
  {
    FwEmptyWFAddresses(a2);
    memset_0((void *)a2, 0, 0x48u);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016bb0  push    rbp
0x180016bb2  push    rbx
0x180016bb3  push    rsi
0x180016bb4  push    rdi
0x180016bb5  push    r14
0x180016bb7  mov     rbp, rsp
0x180016bba  sub     rsp, 60h
0x180016bbe  mov     rax, cs:__security_cookie
0x180016bc5  xor     rax, rsp
0x180016bc8  mov     [rbp+var_10], rax
0x180016bcc  xor     r14d, r14d
0x180016bcf  mov     rdi, rdx
0x180016bd2  mov     esi, r8d
0x180016bd5  mov     [rbp+Context], r14
0x180016bd9  mov     rbx, rcx
0x180016bdc  mov     [rbp+String], r14
0x180016be0  xorps   xmm0, xmm0
0x180016be3  xorps   xmm1, xmm1
0x180016be6  lea     r8d, [r14+48h]; Size
0x180016bea  xor     edx, edx; Val
0x180016bec  mov     rcx, rdi; void *
0x180016bef  movups  [rbp+var_30], xmm0
0x180016bf3  movups  [rbp+var_20], xmm1
0x180016bf7  call    memset_0
0x180016bfc  lea     rdx, [rbp+String]
0x180016c00  mov     rcx, rbx
0x180016c03  call    cs:__imp_FwStringCopy
0x180016c09  mov     ebx, eax
0x180016c0b  test    eax, eax
0x180016c0d  jns     short loc_180016C4D
0x180016c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c16  lea     rax, WPP_GLOBAL_Control
0x180016c1d  cmp     rcx, rax
0x180016c20  jz      loc_180016D1F
0x180016c26  test    byte ptr [rcx+1Ch], 1
0x180016c2a  jz      loc_180016D1F
0x180016c30  mov     edx, 0ABh
0x180016c35  mov     rcx, [rcx+10h]
0x180016c39  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180016c40  mov     r9d, ebx
0x180016c43  call    WPP_SF_d
0x180016c48  jmp     loc_180016D1F
0x180016c4d  mov     rcx, [rbp+String]
0x180016c51  test    rcx, rcx
0x180016c54  jz      loc_180016D1C
0x180016c5a  cmp     [rcx], r14w
0x180016c5e  jz      loc_180016D1C
0x180016c64  lea     rdx, asc_18003D504; "*"
0x180016c6b  call    cs:__imp__o__wcsicmp
0x180016c71  test    eax, eax
0x180016c73  jz      loc_180016D1C
0x180016c79  mov     rcx, [rbp+String]; String
0x180016c7d  lea     r8, [rbp+Context]; Context
0x180016c81  lea     rdx, ?WF_ADDR_TOKEN_DELIMITER_STR@@3QBGB; Delimiter
0x180016c88  call    cs:__imp_wcstok_s
0x180016c8e  test    rax, rax
0x180016c91  jz      short loc_180016CCE
0x180016c93  mov     r8d, esi; unsigned int
0x180016c96  mov     rdx, rdi; struct _tag_FW_ADDRESSES *
0x180016c99  mov     rcx, rax; lpString1
0x180016c9c  call    FwParseAddressToken2
0x180016ca1  mov     ebx, eax
0x180016ca3  test    eax, eax
0x180016ca5  js      short loc_180016CAB
0x180016ca7  xor     ecx, ecx
0x180016ca9  jmp     short loc_180016C7D
0x180016cab  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cb2  lea     rax, WPP_GLOBAL_Control
0x180016cb9  cmp     rcx, rax
0x180016cbc  jz      short loc_180016D1F
0x180016cbe  test    byte ptr [rcx+1Ch], 1
0x180016cc2  jz      short loc_180016D1F
0x180016cc4  mov     edx, 0ACh
0x180016cc9  jmp     loc_180016C35
0x180016cce  mov     eax, [rdi+8]
0x180016cd1  lea     rcx, [rbp+var_30]
0x180016cd5  mov     dword ptr [rbp+var_30], eax
0x180016cd8  mov     rax, [rdi+10h]
0x180016cdc  mov     qword ptr [rbp+var_30+8], rax
0x180016ce0  call    cs:__imp_FwIcfIpV4SubNetsCanonize
0x180016ce6  mov     eax, dword ptr [rbp+var_30]
0x180016ce9  lea     rcx, [rbp+var_20]
0x180016ced  mov     [rdi+8], eax
0x180016cf0  mov     rax, qword ptr [rbp+var_30+8]
0x180016cf4  mov     [rdi+10h], rax
0x180016cf8  mov     eax, [rdi+28h]
0x180016cfb  mov     dword ptr [rbp+var_20], eax
0x180016cfe  mov     rax, [rdi+30h]
0x180016d02  mov     qword ptr [rbp+var_20+8], rax
0x180016d06  call    cs:__imp_FwIcfIpV6SubNetsCanonize
0x180016d0c  mov     eax, dword ptr [rbp+var_20]
0x180016d0f  mov     [rdi+28h], eax
0x180016d12  mov     rax, qword ptr [rbp+var_20+8]
0x180016d16  mov     [rdi+30h], rax
0x180016d1a  jmp     short loc_180016D1F
0x180016d1c  mov     ebx, r14d
0x180016d1f  mov     rcx, [rbp+String]
0x180016d23  call    cs:__imp_FwFree
0x180016d29  test    ebx, ebx
0x180016d2b  jns     short loc_180016D43
0x180016d2d  mov     rcx, rdi
0x180016d30  call    FwEmptyWFAddresses
0x180016d35  xor     edx, edx; Val
0x180016d37  mov     rcx, rdi; void *
0x180016d3a  lea     r8d, [rdx+48h]; Size
0x180016d3e  call    memset_0
0x180016d43  mov     eax, ebx
0x180016d45  mov     rcx, [rbp+var_10]
0x180016d49  xor     rcx, rsp; StackCookie
0x180016d4c  call    __security_check_cookie
0x180016d51  add     rsp, 60h
0x180016d55  pop     r14
0x180016d57  pop     rdi
0x180016d58  pop     rsi
0x180016d59  pop     rbx
0x180016d5a  pop     rbp
0x180016d5b  retn
```
