# _anonymous_namespace_::UpdatePolicyWrapper::Initialize

- ea: `0x14003288c`
- end: `0x140032b06`
- name: `_anonymous_namespace_::UpdatePolicyWrapper::Initialize`
- size: `634`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400241c0`

## callees

- `0x140008de4`
- `0x14000ce30`
- `0x140011958`
- `0x14003288c`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140032942`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140032942`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400329be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400329be`
- `OLEAUT32!__imp_VariantInit` at `0x1400328d4`
- `OLEAUT32!__imp_VariantInit` at `0x1400328d4`
- `OLEAUT32!__imp_VariantClear` at `0x140032ab6`
- `OLEAUT32!__imp_VariantClear` at `0x140032ac2`
- `OLEAUT32!__imp_VariantClear` at `0x140032ab6`
- `OLEAUT32!__imp_VariantClear` at `0x140032ac2`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall anonymous_namespace_::UpdatePolicyWrapper::Initialize(__int64 a1)
{
  wchar_t *v2; // rax
  __int64 *v3; // rax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // esi
  HRESULT v7; // eax
  HRESULT v8; // eax
  int v9; // eax
  unsigned __int64 v10; // r9
  int v11; // esi
  void *v12; // rcx
  int v13; // eax
  int ppv; // [rsp+20h] [rbp-60h]
  LPVOID v16; // [rsp+40h] [rbp-40h] BYREF
  __int128 v17; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v16 = 0;
  v17 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v2 = (wchar_t *)qword_14006BA60;
  do
  {
    if ( *(_DWORD *)v2 == 14 )
    {
      v6 = 1;
      goto LABEL_10;
    }
    v2 += 2;
  }
  while ( v2 != L"Test override Fixed URL ==>%ws<== - " );
  v3 = &qword_14006BA50;
  while ( *(_DWORD *)v3 != 14 )
  {
    v3 = (__int64 *)((char *)v3 + 4);
    if ( v3 == &qword_14006BA58 )
    {
      v4 = -2147024809;
      v5 = 64;
      goto LABEL_35;
    }
  }
  v6 = 2;
LABEL_10:
  if ( !*(_DWORD *)a1 )
  {
    v7 = CoInitializeEx(0, 0);
    v4 = v7;
    if ( v7 >= 0 )
    {
      *(_DWORD *)a1 = 1;
    }
    else if ( v7 != -2147417850 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\CCoInit.h",
        (const char *)(unsigned int)v7,
        ppv);
      v5 = 65;
LABEL_35:
      v10 = v4;
      goto LABEL_36;
    }
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  v8 = CoCreateInstance(&CLSID_UpdatePolicyReader, 0, 1u, &GUID_152807bd_4d18_46c5_ae31_dd8d597d0559, &v16);
  v4 = v8;
  if ( v8 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int128 *))(*(_QWORD *)v16 + 24LL))(v16, 14, &v17);
    v4 = v9;
    if ( v9 < 0 )
    {
      v10 = (unsigned int)v9;
      v5 = 79;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\EnterprisePolicy\\EnterpriseBackedPolicy.cpp",
        (const char *)v10,
        ppv);
      goto LABEL_42;
    }
    if ( DWORD1(v17) == 1 )
    {
      *(_BYTE *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 20) = DWORD2(v17);
      v11 = v6 - 1;
      if ( v11 )
      {
        if ( v11 != 1 )
        {
          *(_BYTE *)(a1 + 4) = 0;
          v4 = -2147024809;
          v5 = 103;
          goto LABEL_35;
        }
        if ( pvarg.vt != 8 )
        {
          v5 = 96;
LABEL_34:
          v4 = -2145120257;
          goto LABEL_35;
        }
        v12 = *(void **)(a1 + 8);
        if ( v12 )
        {
          SusFree(v12);
          *(_QWORD *)(a1 + 8) = 0;
        }
        v13 = DuplicateOptionalString<wchar_t *,wchar_t *>(pvarg.llVal, a1 + 8);
        v4 = v13;
        if ( v13 < 0 )
        {
          v10 = (unsigned int)v13;
          v5 = 97;
          goto LABEL_36;
        }
      }
      else
      {
        if ( pvarg.vt != 3 )
        {
          v5 = 91;
          goto LABEL_34;
        }
        *(_DWORD *)(a1 + 16) = pvarg.lVal;
      }
    }
    else if ( DWORD1(v17) == 2 )
    {
      *(_BYTE *)(a1 + 5) = 1;
    }
    VariantClear(&pvarg);
    goto LABEL_41;
  }
  if ( v8 != -2147221164 )
  {
    v5 = 75;
    goto LABEL_35;
  }
LABEL_41:
  v4 = 0;
LABEL_42:
  VariantClear(&pvarg);
  if ( v16 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
  return v4;
}

```

## disassembly

```asm
0x14003288c  mov     [rsp-8+arg_8], rbx
0x140032891  mov     [rsp-8+arg_10], rsi
0x140032896  mov     [rsp-8+arg_18], rdi
0x14003289b  push    rbp
0x14003289c  mov     rbp, rsp
0x14003289f  sub     rsp, 80h
0x1400328a6  mov     rax, cs:__security_cookie
0x1400328ad  xor     rax, rsp
0x1400328b0  mov     [rbp+var_10], rax
0x1400328b4  mov     rdi, rcx
0x1400328b7  mov     [rbp+var_40], 0
0x1400328bf  xorps   xmm0, xmm0
0x1400328c2  xor     eax, eax
0x1400328c4  movups  [rbp+var_38], xmm0
0x1400328c8  movups  xmmword ptr [rbp+pvarg], xmm0
0x1400328cc  mov     qword ptr [rbp+pvarg+10h], rax
0x1400328d0  lea     rcx, [rbp+pvarg]; pvarg
0x1400328d4  call    cs:__imp_VariantInit
0x1400328da  lea     rax, [rbp+var_38]
0x1400328de  mov     [rbp+var_50], rax
0x1400328e2  mov     [rbp+var_48], 1
0x1400328e6  lea     rax, qword_14006BA60
0x1400328ed  cmp     dword ptr [rax], 0Eh
0x1400328f0  jz      short loc_140032934
0x1400328f2  add     rax, 4
0x1400328f6  lea     rcx, aTestOverrideFi; "Test override Fixed URL ==>%ws<== - "
0x1400328fd  cmp     rax, rcx
0x140032900  jnz     short loc_1400328ED
0x140032902  lea     rax, qword_14006BA50
0x140032909  cmp     dword ptr [rax], 0Eh
0x14003290c  jz      short loc_14003292D
0x14003290e  add     rax, 4
0x140032912  lea     rcx, qword_14006BA58
0x140032919  cmp     rax, rcx
0x14003291c  jnz     short loc_140032909
0x14003291e  mov     ebx, 80070057h
0x140032923  mov     edx, 40h ; '@'
0x140032928  jmp     loc_140032A8B
0x14003292d  mov     esi, 2
0x140032932  jmp     short loc_140032939
0x140032934  mov     esi, 1
0x140032939  cmp     dword ptr [rdi], 0
0x14003293c  jnz     short loc_140032984
0x14003293e  xor     edx, edx; dwCoInit
0x140032940  xor     ecx, ecx; pvReserved
0x140032942  call    cs:__imp_CoInitializeEx
0x140032948  mov     ebx, eax
0x14003294a  test    eax, eax
0x14003294c  jns     short loc_140032977
0x14003294e  cmp     eax, 80010106h
0x140032953  jz      short loc_140032984
0x140032955  mov     rcx, [rbp+8]; this
0x140032959  mov     r9d, eax; char *
0x14003295c  lea     r8, aCW1SSrcClientI_1; "C:\\__w\\1\\s\\src\\Client\\inc\\CCoIni"...
0x140032963  mov     edx, 1Ah; void *
0x140032968  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003296d  mov     edx, 41h ; 'A'
0x140032972  jmp     loc_140032A8B
0x140032977  cmp     eax, 80010106h
0x14003297c  jz      short loc_140032984
0x14003297e  mov     dword ptr [rdi], 1
0x140032984  mov     rcx, [rbp+var_40]
0x140032988  test    rcx, rcx
0x14003298b  jz      short loc_1400329A1
0x14003298d  mov     rax, [rcx]
0x140032990  mov     rax, [rax+10h]
0x140032994  call    _guard_dispatch_icall
0x140032999  mov     [rbp+var_40], 0
0x1400329a1  lea     rax, [rbp+var_40]
0x1400329a5  mov     qword ptr [rsp+80h+ppv], rax; int
0x1400329aa  lea     r9, _GUID_152807bd_4d18_46c5_ae31_dd8d597d0559; riid
0x1400329b1  xor     edx, edx; pUnkOuter
0x1400329b3  lea     r8d, [rdx+1]; dwClsContext
0x1400329b7  lea     rcx, CLSID_UpdatePolicyReader; rclsid
0x1400329be  call    cs:__imp_CoCreateInstance
0x1400329c4  mov     ebx, eax
0x1400329c6  test    eax, eax
0x1400329c8  jns     short loc_1400329DF
0x1400329ca  cmp     eax, 80040154h
0x1400329cf  jz      loc_140032ABC
0x1400329d5  mov     edx, 4Bh ; 'K'
0x1400329da  jmp     loc_140032A8B
0x1400329df  mov     rcx, [rbp+var_40]
0x1400329e3  mov     rax, [rcx]
0x1400329e6  lea     r8, [rbp+var_38]
0x1400329ea  mov     edx, 0Eh
0x1400329ef  mov     rax, [rax+18h]
0x1400329f3  call    _guard_dispatch_icall
0x1400329f8  mov     ebx, eax
0x1400329fa  test    eax, eax
0x1400329fc  jns     short loc_140032A0B
0x1400329fe  mov     r9d, eax
0x140032a01  mov     edx, 4Fh ; 'O'
0x140032a06  jmp     loc_140032A8E
0x140032a0b  cmp     dword ptr [rbp+var_38+4], 1
0x140032a0f  jnz     loc_140032AA8
0x140032a15  mov     byte ptr [rdi+4], 1
0x140032a19  mov     eax, dword ptr [rbp+var_38+8]
0x140032a1c  mov     [rdi+14h], eax
0x140032a1f  sub     esi, 1
0x140032a22  jz      short loc_140032A7A
0x140032a24  cmp     esi, 1
0x140032a27  jz      short loc_140032A39
0x140032a29  mov     byte ptr [rdi+4], 0
0x140032a2d  mov     ebx, 80070057h
0x140032a32  mov     edx, 67h ; 'g'
0x140032a37  jmp     short loc_140032A8B
0x140032a39  cmp     word ptr [rbp+pvarg], 8
0x140032a3e  jz      short loc_140032A47
0x140032a40  mov     edx, 60h ; '`'
0x140032a45  jmp     short loc_140032A86
0x140032a47  mov     rcx, [rdi+8]; lpMem
0x140032a4b  test    rcx, rcx
0x140032a4e  jz      short loc_140032A5D
0x140032a50  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140032a55  mov     qword ptr [rdi+8], 0
0x140032a5d  lea     rdx, [rdi+8]
0x140032a61  mov     rcx, qword ptr [rbp+pvarg+8]
0x140032a65  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x140032a6a  mov     ebx, eax
0x140032a6c  test    eax, eax
0x140032a6e  jns     short loc_140032AB2
0x140032a70  mov     r9d, eax
0x140032a73  mov     edx, 61h ; 'a'
0x140032a78  jmp     short loc_140032A8E
0x140032a7a  cmp     word ptr [rbp+pvarg], 3
0x140032a7f  jz      short loc_140032AA0
0x140032a81  mov     edx, 5Bh ; '['; void *
0x140032a86  mov     ebx, 80240FFFh
0x140032a8b  mov     r9d, ebx; char *
0x140032a8e  mov     rcx, [rbp+8]; this
0x140032a92  lea     r8, aCW1SSrcClientL_31; "C:\\__w\\1\\s\\src\\Client\\lib\\Enterp"...
0x140032a99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140032a9e  jmp     short loc_140032ABE
0x140032aa0  mov     eax, dword ptr [rbp+pvarg+8]
0x140032aa3  mov     [rdi+10h], eax
0x140032aa6  jmp     short loc_140032AB2
0x140032aa8  cmp     dword ptr [rbp+var_38+4], 2
0x140032aac  jnz     short loc_140032AB2
0x140032aae  mov     byte ptr [rdi+5], 1
0x140032ab2  lea     rcx, [rbp+pvarg]; pvarg
0x140032ab6  call    cs:__imp_VariantClear
0x140032abc  xor     ebx, ebx
0x140032abe  lea     rcx, [rbp+pvarg]; pvarg
0x140032ac2  call    cs:__imp_VariantClear
0x140032ac8  nop
0x140032ac9  mov     rcx, [rbp+var_40]
0x140032acd  test    rcx, rcx
0x140032ad0  jz      short loc_140032ADF
0x140032ad2  mov     rdx, [rcx]
0x140032ad5  mov     rax, [rdx+10h]
0x140032ad9  call    _guard_dispatch_icall
0x140032ade  nop
0x140032adf  mov     eax, ebx
0x140032ae1  mov     rcx, [rbp+var_10]
0x140032ae5  xor     rcx, rsp; StackCookie
0x140032ae8  call    __security_check_cookie
0x140032aed  lea     r11, [rsp+80h+var_s0]
0x140032af5  mov     rbx, [r11+18h]
0x140032af9  mov     rsi, [r11+20h]
0x140032afd  mov     rdi, [r11+28h]
0x140032b01  mov     rsp, r11
0x140032b04  pop     rbp
0x140032b05  retn
```
