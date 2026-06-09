# Dynamo::StateEntry::GetValue(void)

- ea: `0x140048a10`
- end: `0x140048c50`
- name: `?GetValue@StateEntry@Dynamo@@UEBA?AV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@XZ`
- size: `576`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1400095b4`
- `0x14000a6e4`
- `0x140028284`
- `0x140048a10`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140048b62`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140048b62`
- `OLEAUT32!__imp_SysFreeString` at `0x140048af9`
- `OLEAUT32!__imp_SysFreeString` at `0x140048af9`
- `OLEAUT32!__imp_VariantInit` at `0x140048b0a`
- `OLEAUT32!__imp_VariantInit` at `0x140048b2e`
- `OLEAUT32!__imp_VariantInit` at `0x140048b9f`
- `OLEAUT32!__imp_VariantInit` at `0x140048bdd`
- `OLEAUT32!__imp_VariantInit` at `0x140048b0a`
- `OLEAUT32!__imp_VariantInit` at `0x140048b2e`
- `OLEAUT32!__imp_VariantInit` at `0x140048b9f`
- `OLEAUT32!__imp_VariantInit` at `0x140048bdd`
- `OLEAUT32!__imp_VariantClear` at `0x140048be8`
- `OLEAUT32!__imp_VariantClear` at `0x140048bf3`
- `OLEAUT32!__imp_VariantClear` at `0x140048be8`
- `OLEAUT32!__imp_VariantClear` at `0x140048bf3`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x140048bba`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x140048bba`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140048a8a`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140048a8a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140048a5d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140048ad6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140048a5d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140048ad6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
VARIANTARG *__fastcall Dynamo::StateEntry::GetValue(__int64 a1, VARIANTARG *a2)
{
  LONGLONG v4; // r14
  HKEY v5; // rdi
  unsigned int ValueW; // eax
  int v7; // edi
  BSTR pvData; // rbx
  unsigned int v9; // eax
  int DWORD; // eax
  VARTYPE v11; // bx
  __int64 v12; // r9
  HRESULT v13; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-60h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-60h]
  int pdwTypeb; // [rsp+20h] [rbp-60h]
  VARIANTARG pvargDest; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  DWORD len; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int vt; // [rsp+D0h] [rbp+50h] BYREF
  BSTR v23; // [rsp+D8h] [rbp+58h]

  v4 = 0;
  v23 = 0;
  v5 = *(HKEY *)(a1 + 8);
  len = 0;
  ValueW = RegGetValueW(v5, 0, L"Data", 8u, 0, 0, &len);
  if ( ValueW )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xC,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\stateentry.cpp",
           (const char *)ValueW,
           pdwType);
  }
  else
  {
    pvData = SysAllocStringByteLen(0, len);
    if ( !pvData )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\stateentry.cpp",
        (const char *)0x8007000ELL,
        pdwType);
      goto LABEL_10;
    }
    v9 = RegGetValueW(v5, 0, L"Data", 8u, 0, pvData, &len);
    if ( !v9 )
    {
      v4 = (LONGLONG)pvData;
      v23 = pvData;
      v7 = 0;
      goto LABEL_10;
    }
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x10,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\stateentry.cpp",
           (const char *)v9,
           pdwTypea);
    SysFreeString(pvData);
  }
  if ( v7 == -2147024894 )
  {
    VariantInit(a2);
    return a2;
  }
LABEL_10:
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x47,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\stateentry.cpp",
      (const char *)(unsigned int)v7,
      pdwTypea);
  VariantInit(&pvarg);
  pvarg.vt = 8;
  v23 = 0;
  pvarg.llVal = v4;
  vt = 0;
  DWORD = OmaDmRegistryGetDWORD(*(HKEY *)(a1 + 8), 0, L"VarType", &vt);
  if ( DWORD < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4F,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\stateentry.cpp",
      (const char *)(unsigned int)DWORD,
      pdwTypea);
  v11 = vt;
  if ( vt > 0xFFFF )
  {
    v11 = -1;
    v12 = 2147942934LL;
  }
  else
  {
    v12 = 0;
  }
  if ( (int)v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x52,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\stateentry.cpp",
      (const char *)v12,
      pdwTypea);
  VariantInit(&pvargDest);
  v13 = VariantChangeTypeEx(&pvargDest, &pvarg, 0x7Fu, 0, v11);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x56,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\stateentry.cpp",
      (const char *)(unsigned int)v13,
      pdwTypeb);
  *a2 = pvargDest;
  VariantInit(&pvargDest);
  VariantClear(&pvargDest);
  VariantClear(&pvarg);
  return a2;
}

```

## disassembly

```asm
0x140048a10  push    rbp
0x140048a12  push    rbx
0x140048a13  push    rsi
0x140048a14  push    rdi
0x140048a15  push    r13
0x140048a17  push    r14
0x140048a19  push    r15
0x140048a1b  mov     rbp, rsp
0x140048a1e  sub     rsp, 80h
0x140048a25  mov     rsi, rdx
0x140048a28  mov     r15, rcx
0x140048a2b  xor     r14d, r14d
0x140048a2e  mov     [rbp+arg_18], r14
0x140048a32  mov     rdi, [rcx+8]
0x140048a36  mov     [rbp+len], r14d
0x140048a3a  lea     rax, [rbp+len]
0x140048a3e  mov     [rsp+80h+pcbData], rax; pcbData
0x140048a43  mov     [rsp+80h+pvData], r14; pvData
0x140048a48  mov     [rsp+80h+pdwType], r14; int
0x140048a4d  lea     r9d, [r14+8]; dwFlags
0x140048a51  lea     r8, aData; "Data"
0x140048a58  xor     edx, edx; lpSubKey
0x140048a5a  mov     rcx, rdi; hkey
0x140048a5d  call    cs:__imp_RegGetValueW
0x140048a63  lea     r13, aOnecoreuapAdmi_29; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140048a6a  test    eax, eax
0x140048a6c  jz      short loc_140048A85
0x140048a6e  mov     rcx, [rbp+38h]; this
0x140048a72  mov     r9d, eax; char *
0x140048a75  mov     r8, r13; unsigned int
0x140048a78  lea     edx, [r14+0Ch]; void *
0x140048a7c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140048a81  mov     edi, eax
0x140048a83  jmp     short loc_140048AFF
0x140048a85  mov     edx, [rbp+len]; len
0x140048a88  xor     ecx, ecx; psz
0x140048a8a  call    cs:__imp_SysAllocStringByteLen
0x140048a90  mov     rbx, rax
0x140048a93  test    rax, rax
0x140048a96  jnz     short loc_140048AB1
0x140048a98  mov     rcx, [rbp+38h]; this
0x140048a9c  mov     edi, 8007000Eh
0x140048aa1  mov     r9d, edi; char *
0x140048aa4  mov     r8, r13; unsigned int
0x140048aa7  lea     edx, [rax+0Fh]; void *
0x140048aaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140048aaf  jmp     short loc_140048B1E
0x140048ab1  lea     rax, [rbp+len]
0x140048ab5  mov     [rsp+80h+pcbData], rax; pcbData
0x140048aba  mov     [rsp+80h+pvData], rbx; pvData
0x140048abf  mov     [rsp+80h+pdwType], r14; int
0x140048ac4  mov     r9d, 8; dwFlags
0x140048aca  lea     r8, aData; "Data"
0x140048ad1  xor     edx, edx; lpSubKey
0x140048ad3  mov     rcx, rdi; hkey
0x140048ad6  call    cs:__imp_RegGetValueW
0x140048adc  test    eax, eax
0x140048ade  jz      short loc_140048B15
0x140048ae0  mov     rcx, [rbp+38h]; this
0x140048ae4  mov     r9d, eax; char *
0x140048ae7  mov     r8, r13; unsigned int
0x140048aea  mov     edx, 10h; void *
0x140048aef  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140048af4  mov     edi, eax
0x140048af6  mov     rcx, rbx; bstrString
0x140048af9  call    cs:__imp_SysFreeString
0x140048aff  cmp     edi, 80070002h
0x140048b05  jnz     short loc_140048B1E
0x140048b07  mov     rcx, rsi; pvarg
0x140048b0a  call    cs:__imp_VariantInit
0x140048b10  jmp     loc_140048BFA
0x140048b15  mov     r14, rbx
0x140048b18  mov     [rbp+arg_18], rbx
0x140048b1c  xor     edi, edi
0x140048b1e  mov     rcx, [rbp+38h]; this
0x140048b22  test    edi, edi
0x140048b24  js      loc_140048C20
0x140048b2a  lea     rcx, [rbp+pvarg]; pvarg
0x140048b2e  call    cs:__imp_VariantInit
0x140048b34  nop
0x140048b35  mov     eax, 8
0x140048b3a  mov     word ptr [rbp+pvarg], ax
0x140048b3e  mov     [rbp+arg_18], 0
0x140048b46  mov     qword ptr [rbp+pvarg+8], r14
0x140048b4a  mov     [rbp+vt], 0
0x140048b51  lea     r9, [rbp+vt]
0x140048b55  lea     r8, aVartype; "VarType"
0x140048b5c  xor     edx, edx
0x140048b5e  mov     rcx, [r15+8]
0x140048b62  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140048b68  mov     rcx, [rbp+38h]; this
0x140048b6c  test    eax, eax
0x140048b6e  js      loc_140048C31
0x140048b74  mov     ebx, [rbp+vt]
0x140048b77  mov     eax, 0FFFFh
0x140048b7c  cmp     ebx, eax
0x140048b7e  ja      short loc_140048B85
0x140048b80  xor     r9d, r9d
0x140048b83  jmp     short loc_140048B8E
0x140048b85  movzx   ebx, ax
0x140048b88  mov     r9d, 80070216h; char *
0x140048b8e  mov     rcx, [rbp+38h]; this
0x140048b92  test    r9d, r9d
0x140048b95  js      loc_140048C42
0x140048b9b  lea     rcx, [rbp+pvargDest]; pvarg
0x140048b9f  call    cs:__imp_VariantInit
0x140048ba5  nop
0x140048ba6  xor     r9d, r9d; wFlags
0x140048ba9  mov     word ptr [rsp+80h+pdwType], bx; int
0x140048bae  lea     r8d, [r9+7Fh]; lcid
0x140048bb2  lea     rdx, [rbp+pvarg]; pvarSrc
0x140048bb6  lea     rcx, [rbp+pvargDest]; pvargDest
0x140048bba  call    cs:__imp_VariantChangeTypeEx
0x140048bc0  mov     rcx, [rbp+38h]; this
0x140048bc4  test    eax, eax
0x140048bc6  js      short loc_140048C0F
0x140048bc8  movups  xmm0, xmmword ptr [rbp+pvargDest]
0x140048bcc  movups  xmmword ptr [rsi], xmm0
0x140048bcf  movsd   xmm1, qword ptr [rbp+pvargDest+10h]
0x140048bd4  movsd   qword ptr [rsi+10h], xmm1
0x140048bd9  lea     rcx, [rbp+pvargDest]; pvarg
0x140048bdd  call    cs:__imp_VariantInit
0x140048be3  nop
0x140048be4  lea     rcx, [rbp+pvargDest]; pvarg
0x140048be8  call    cs:__imp_VariantClear
0x140048bee  nop
0x140048bef  lea     rcx, [rbp+pvarg]; pvarg
0x140048bf3  call    cs:__imp_VariantClear
0x140048bf9  nop
0x140048bfa  mov     rax, rsi
0x140048bfd  add     rsp, 80h
0x140048c04  pop     r15
0x140048c06  pop     r14
0x140048c08  pop     r13
0x140048c0a  pop     rdi
0x140048c0b  pop     rsi
0x140048c0c  pop     rbx
0x140048c0d  pop     rbp
0x140048c0e  retn
0x140048c0f  mov     r9d, eax; char *
0x140048c12  mov     r8, r13; unsigned int
0x140048c15  mov     edx, 56h ; 'V'; void *
0x140048c1a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140048c20  mov     r9d, edi; char *
0x140048c23  mov     r8, r13; unsigned int
0x140048c26  mov     edx, 47h ; 'G'; void *
0x140048c2b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140048c31  mov     r9d, eax; char *
0x140048c34  mov     r8, r13; unsigned int
0x140048c37  mov     edx, 4Fh ; 'O'; void *
0x140048c3c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140048c42  mov     r8, r13; unsigned int
0x140048c45  mov     edx, 52h ; 'R'; void *
0x140048c4a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
