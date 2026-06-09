# SafeArrayAccessor<uint>::Access(tagSAFEARRAY *,ushort)

- ea: `0x180039aa4`
- end: `0x180039bea`
- name: `?Access@?$SafeArrayAccessor@I@@QEAAJPEAUtagSAFEARRAY@@G@Z`
- size: `326`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003974c`
- `0x1800398b8`
- `0x180039984`
- `0x180039a50`

## callees

- `0x180006edc`
- `0x180039aa4`
- `0x18004da00`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180039b04`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180039b04`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180039ba0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180039ba0`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180039b80`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180039b80`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180039bc7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180039bc7`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180039b25`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180039b25`

## string_xrefs

- `0x180039ac2`: `onecore\windows\accessibletech\Common\SafeArray.h`
- `0x180039ae8`: `onecore\windows\accessibletech\Common\SafeArray.h`
- `0x180039b3b`: `onecore\windows\accessibletech\Common\SafeArray.h`

## pseudocode

```c
__int64 __fastcall SafeArrayAccessor<unsigned int>::Access(__int64 a1, SAFEARRAY *a2, VARTYPE a3, const char *a4)
{
  __int64 v5; // rdx
  HRESULT v6; // ebx
  SAFEARRAY *v8; // rcx
  HRESULT Vartype; // edi
  __int64 v10; // rdx
  SAFEARRAY *v11; // rcx
  SAFEARRAY *v12; // rcx
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LONG plUbound; // [rsp+30h] [rbp+8h] BYREF
  VARTYPE pvt; // [rsp+40h] [rbp+18h] BYREF
  LONG plLbound; // [rsp+48h] [rbp+20h] BYREF

  pvt = a3;
  if ( *(_QWORD *)a1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\windows\\accessibletech\\Common\\SafeArray.h",
      a4);
  if ( !a2 )
  {
    v5 = 87;
LABEL_5:
    v6 = -2147024809;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\windows\\accessibletech\\Common\\SafeArray.h",
      (const char *)(unsigned int)v6,
      v13);
    return (unsigned int)v6;
  }
  *(_QWORD *)a1 = a2;
  if ( SafeArrayGetDim(a2) != 1 )
  {
    v5 = 92;
    goto LABEL_5;
  }
  v8 = *(SAFEARRAY **)a1;
  pvt = 0;
  Vartype = SafeArrayGetVartype(v8, &pvt);
  if ( Vartype < 0 )
  {
    v10 = 95;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\windows\\accessibletech\\Common\\SafeArray.h",
      (const char *)(unsigned int)Vartype,
      v13);
    return (unsigned int)Vartype;
  }
  if ( pvt != 19 )
  {
    v5 = 106;
    goto LABEL_5;
  }
  v11 = *(SAFEARRAY **)a1;
  plLbound = 0;
  plUbound = 0;
  Vartype = SafeArrayGetLBound(v11, 1u, &plLbound);
  if ( Vartype < 0 )
  {
    v10 = 111;
    goto LABEL_11;
  }
  Vartype = SafeArrayGetUBound(*(SAFEARRAY **)a1, 1u, &plUbound);
  if ( Vartype < 0 )
  {
    v10 = 112;
    goto LABEL_11;
  }
  v12 = *(SAFEARRAY **)a1;
  *(_DWORD *)(a1 + 8) = plUbound - plLbound + 1;
  v6 = SafeArrayAccessData(v12, (void **)(a1 + 16));
  if ( v6 < 0 )
  {
    v5 = 115;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x180039aa4  mov     [rsp+arg_8], rbx
0x180039aa9  mov     [rsp+pvt], r8w
0x180039aaf  push    rdi; int
0x180039ab0  sub     rsp, 20h
0x180039ab4  cmp     qword ptr [rcx], 0
0x180039ab8  mov     rbx, rcx
0x180039abb  jz      short loc_180039AD4
0x180039abd  mov     rcx, [rsp+28h]; this
0x180039ac2  lea     r8, aOnecoreWindows_18; "onecore\\windows\\accessibletech\\Commo"...
0x180039ac9  mov     edx, 55h ; 'U'; void *
0x180039ace  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180039ad4  test    rdx, rdx
0x180039ad7  jnz     short loc_180039AFE
0x180039ad9  mov     edx, 57h ; 'W'; void *
0x180039ade  mov     ebx, 80070057h
0x180039ae3  mov     rcx, [rsp+28h]; this
0x180039ae8  lea     r8, aOnecoreWindows_18; "onecore\\windows\\accessibletech\\Commo"...
0x180039aef  mov     r9d, ebx; char *
0x180039af2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039af7  mov     eax, ebx
0x180039af9  jmp     loc_180039BDF
0x180039afe  mov     [rcx], rdx
0x180039b01  mov     rcx, rdx; psa
0x180039b04  call    cs:__imp_SafeArrayGetDim
0x180039b0a  cmp     eax, 1
0x180039b0d  jz      short loc_180039B16
0x180039b0f  mov     edx, 5Ch ; '\'
0x180039b14  jmp     short loc_180039ADE
0x180039b16  mov     rcx, [rbx]; psa
0x180039b19  lea     rdx, [rsp+28h+pvt]; pvt
0x180039b1e  xor     eax, eax
0x180039b20  mov     [rsp+28h+pvt], ax
0x180039b25  call    cs:__imp_SafeArrayGetVartype
0x180039b2b  mov     edi, eax
0x180039b2d  test    eax, eax
0x180039b2f  jns     short loc_180039B51
0x180039b31  mov     edx, 5Fh ; '_'; void *
0x180039b36  mov     rcx, [rsp+28h]; this
0x180039b3b  lea     r8, aOnecoreWindows_18; "onecore\\windows\\accessibletech\\Commo"...
0x180039b42  mov     r9d, edi; char *
0x180039b45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039b4a  mov     eax, edi
0x180039b4c  jmp     loc_180039BDF
0x180039b51  cmp     [rsp+28h+pvt], 13h
0x180039b57  jz      short loc_180039B63
0x180039b59  mov     edx, 6Ah ; 'j'
0x180039b5e  jmp     loc_180039ADE
0x180039b63  mov     rcx, [rbx]; psa
0x180039b66  lea     r8, [rsp+28h+plLbound]; plLbound
0x180039b6b  mov     edx, 1; nDim
0x180039b70  mov     [rsp+28h+plLbound], 0
0x180039b78  mov     [rsp+28h+plUbound], 0
0x180039b80  call    cs:__imp_SafeArrayGetLBound
0x180039b86  mov     edi, eax
0x180039b88  test    eax, eax
0x180039b8a  jns     short loc_180039B93
0x180039b8c  mov     edx, 6Fh ; 'o'
0x180039b91  jmp     short loc_180039B36
0x180039b93  mov     rcx, [rbx]; psa
0x180039b96  lea     r8, [rsp+28h+plUbound]; plUbound
0x180039b9b  mov     edx, 1; nDim
0x180039ba0  call    cs:__imp_SafeArrayGetUBound
0x180039ba6  mov     edi, eax
0x180039ba8  test    eax, eax
0x180039baa  jns     short loc_180039BB3
0x180039bac  mov     edx, 70h ; 'p'
0x180039bb1  jmp     short loc_180039B36
0x180039bb3  mov     eax, [rsp+28h+plUbound]
0x180039bb7  lea     rdx, [rbx+10h]; ppvData
0x180039bbb  sub     eax, [rsp+28h+plLbound]
0x180039bbf  mov     rcx, [rbx]; psa
0x180039bc2  inc     eax
0x180039bc4  mov     [rbx+8], eax
0x180039bc7  call    cs:__imp_SafeArrayAccessData
0x180039bcd  mov     ebx, eax
0x180039bcf  test    eax, eax
0x180039bd1  jns     short loc_180039BDD
0x180039bd3  mov     edx, 73h ; 's'
0x180039bd8  jmp     loc_180039AE3
0x180039bdd  xor     eax, eax
0x180039bdf  mov     rbx, [rsp+28h+arg_8]
0x180039be4  add     rsp, 20h
0x180039be8  pop     rdi
0x180039be9  retn
```
