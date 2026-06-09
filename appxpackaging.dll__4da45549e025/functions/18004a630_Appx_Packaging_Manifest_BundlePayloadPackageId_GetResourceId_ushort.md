# Appx::Packaging::Manifest::BundlePayloadPackageId::GetResourceId(ushort * *)

- ea: `0x18004a630`
- end: `0x18004a7a9`
- name: `?GetResourceId@BundlePayloadPackageId@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `377`
- prototype: `int(Appx::Packaging::Manifest::BundlePayloadPackageId *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e61a0`

## callees

- `0x1800133fc`
- `0x18004a630`
- `0x180071f50`
- `0x18009d729`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a64f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a6ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a724`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a64f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a6ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a724`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a73d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a73d`

## string_xrefs

- `0x18004a6ce`: `onecore\base\appmodel\common\autocotaskmemstring.cpp`
- `0x18004a70d`: `onecore\printscan\appxpackaging\manifest\src\bundlepayloadpackageid.cpp`
- `0x18004a789`: `onecore\printscan\appxpackaging\manifest\src\bundlepayloadpackageid.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::BundlePayloadPackageId::GetResourceId(
        Appx::Packaging::Manifest::BundlePayloadPackageId *this,
        unsigned __int16 **a2)
{
  _WORD *v3; // rsi
  unsigned __int16 *v4; // rbx
  _WORD *v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // edi
  __int64 v8; // rdx
  unsigned __int64 v9; // rdi
  __int64 v10; // rdx
  unsigned __int16 *v12; // rax
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a2 )
  {
    v3 = (_WORD *)*((_QWORD *)this + 13);
    CoTaskMemFree(0);
    v4 = 0;
    if ( !v3 )
    {
LABEL_13:
      *a2 = v4;
      CoTaskMemFree(0);
      return 0;
    }
    v5 = v3;
    v6 = 0x7FFFFFFF;
    do
    {
      if ( !*v5 )
        break;
      ++v5;
      --v6;
    }
    while ( v6 );
    v7 = v6 == 0 ? 0x80070057 : 0;
    v8 = (0x7FFFFFFF - v6) & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64);
    if ( !v6 )
      goto LABEL_14;
    if ( (unsigned int)v8 > 0x3FFFFFFF )
    {
      v7 = -2147024809;
    }
    else
    {
      v9 = 2LL * (unsigned int)v8;
      if ( v9 > 0xFFFFFFFF )
      {
        v10 = 27;
LABEL_10:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecore\\base\\appmodel\\common\\autocotaskmemstring.cpp",
          (const char *)0x80070216LL,
          v13);
LABEL_11:
        v7 = -2147024882;
        goto LABEL_12;
      }
      if ( (int)v9 + 2 < (unsigned int)v9 )
      {
        v10 = 29;
        goto LABEL_10;
      }
      v12 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)(v9 + 2));
      v4 = v12;
      if ( !v12 )
      {
        v4 = 0;
        goto LABEL_11;
      }
      memcpy_0(v12, v3, (unsigned int)v9);
      v4[v9 / 2] = 0;
      v7 = 0;
    }
LABEL_12:
    if ( (v7 & 0x80000000) == 0 )
      goto LABEL_13;
LABEL_14:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlepayloadpackageid.cpp",
      (const char *)v7,
      v13);
    CoTaskMemFree(v4);
    return v7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E,
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlepayloadpackageid.cpp",
    (const char *)0x80004003LL,
    v13);
  return 2147500035LL;
}

```

## disassembly

```asm
0x18004a630  push    rbx
0x18004a632  push    rbp
0x18004a633  push    rsi
0x18004a634  push    rdi
0x18004a635  push    r14; int
0x18004a637  sub     rsp, 20h
0x18004a63b  xor     ebp, ebp
0x18004a63d  mov     r14, rdx
0x18004a640  test    rdx, rdx
0x18004a643  jz      loc_18004A784
0x18004a649  mov     rsi, [rcx+68h]
0x18004a64d  xor     ecx, ecx; pv
0x18004a64f  call    cs:__imp_CoTaskMemFree
0x18004a656  nop     dword ptr [rax+rax+00h]
0x18004a65b  mov     ebx, ebp
0x18004a65d  test    rsi, rsi
0x18004a660  jz      loc_18004A6E9
0x18004a666  mov     r8d, 7FFFFFFFh
0x18004a66c  mov     rax, rsi
0x18004a66f  mov     ecx, r8d
0x18004a672  cmp     [rax], bp
0x18004a675  jz      short loc_18004A681
0x18004a677  add     rax, 2
0x18004a67b  sub     rcx, 1
0x18004a67f  jnz     short loc_18004A672
0x18004a681  mov     rax, rcx
0x18004a684  mov     r9d, 80070057h
0x18004a68a  neg     rax
0x18004a68d  mov     rax, rcx
0x18004a690  sbb     edi, edi
0x18004a692  sub     r8, rcx
0x18004a695  not     edi
0x18004a697  and     edi, r9d
0x18004a69a  neg     rax
0x18004a69d  sbb     rdx, rdx
0x18004a6a0  and     rdx, r8
0x18004a6a3  test    rcx, rcx
0x18004a6a6  jz      short loc_18004A708
0x18004a6a8  cmp     edx, 3FFFFFFFh
0x18004a6ae  ja      loc_18004A774
0x18004a6b4  mov     eax, edx
0x18004a6b6  lea     rdi, [rax+rax]
0x18004a6ba  mov     eax, 0FFFFFFFFh
0x18004a6bf  cmp     rdi, rax
0x18004a6c2  jbe     short loc_18004A734
0x18004a6c4  mov     edx, 1Bh; void *
0x18004a6c9  mov     rcx, [rsp+48h]; this
0x18004a6ce  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\common\\autoco"...
0x18004a6d5  mov     r9d, 80070216h; char *
0x18004a6db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a6e0  mov     edi, 8007000Eh
0x18004a6e5  test    edi, edi
0x18004a6e7  js      short loc_18004A708
0x18004a6e9  xor     ecx, ecx; pv
0x18004a6eb  mov     [r14], rbx
0x18004a6ee  call    cs:__imp_CoTaskMemFree
0x18004a6f5  nop     dword ptr [rax+rax+00h]
0x18004a6fa  xor     eax, eax
0x18004a6fc  add     rsp, 20h
0x18004a700  pop     r14
0x18004a702  pop     rdi
0x18004a703  pop     rsi
0x18004a704  pop     rbp
0x18004a705  pop     rbx
0x18004a706  retn
0x18004a708  mov     rcx, [rsp+48h]; this
0x18004a70d  lea     r8, aOnecorePrintsc_79; "onecore\\printscan\\appxpackaging\\mani"...
0x18004a714  mov     r9d, edi; char *
0x18004a717  mov     edx, 62h ; 'b'; void *
0x18004a71c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a721  mov     rcx, rbx; pv
0x18004a724  call    cs:__imp_CoTaskMemFree
0x18004a72b  nop     dword ptr [rax+rax+00h]
0x18004a730  mov     eax, edi
0x18004a732  jmp     short loc_18004A6FC
0x18004a734  lea     eax, [rdi+2]
0x18004a737  cmp     eax, edi
0x18004a739  jb      short loc_18004A76A
0x18004a73b  mov     ecx, eax; cb
0x18004a73d  call    cs:__imp_CoTaskMemAlloc
0x18004a744  nop     dword ptr [rax+rax+00h]
0x18004a749  mov     rbx, rax
0x18004a74c  test    rax, rax
0x18004a74f  jz      short loc_18004A77C
0x18004a751  mov     r8d, edi; Size
0x18004a754  mov     rdx, rsi; Src
0x18004a757  mov     rcx, rax; void *
0x18004a75a  call    memcpy_0
0x18004a75f  mov     [rdi+rbx], bp
0x18004a763  mov     edi, ebp
0x18004a765  jmp     loc_18004A6E5
0x18004a76a  mov     edx, 1Dh
0x18004a76f  jmp     loc_18004A6C9
0x18004a774  mov     edi, r9d
0x18004a777  jmp     loc_18004A6E5
0x18004a77c  mov     rbx, rbp
0x18004a77f  jmp     loc_18004A6E0
0x18004a784  mov     rcx, [rsp+48h]; this
0x18004a789  lea     r8, aOnecorePrintsc_79; "onecore\\printscan\\appxpackaging\\mani"...
0x18004a790  mov     ebx, 80004003h
0x18004a795  mov     edx, 5Eh ; '^'; void *
0x18004a79a  mov     r9d, ebx; char *
0x18004a79d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a7a2  mov     eax, ebx
0x18004a7a4  jmp     loc_18004A6FC
```
