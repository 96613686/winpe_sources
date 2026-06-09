# _anonymous_namespace_::UpdatePolicyWrapper::Initialize_0

- ea: `0x18004e650`
- end: `0x18004e82a`
- name: `_anonymous_namespace_::UpdatePolicyWrapper::Initialize_0`
- size: `474`
- prototype: `__int64 __fastcall(CCoInit *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004eb2c`
- `0x18004ebd0`

## callees

- `0x180003180`
- `0x180007b9c`
- `0x180008f5c`
- `0x18000dce4`
- `0x18004e650`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e6f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e6f7`
- `OLEAUT32!__imp_VariantInit` at `0x18004e690`
- `OLEAUT32!__imp_VariantInit` at `0x18004e690`
- `OLEAUT32!__imp_VariantClear` at `0x18004e78f`
- `OLEAUT32!__imp_VariantClear` at `0x18004e78f`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall anonymous_namespace_::UpdatePolicyWrapper::Initialize_0(CCoInit *this, unsigned int a2)
{
  unsigned int v4; // edx
  int v5; // ebx
  __int64 v6; // rdx
  HRESULT v7; // eax
  int v8; // eax
  unsigned __int64 v9; // r9
  int v10; // eax
  void *v12; // rcx
  int v13; // eax
  int ppv; // [rsp+20h] [rbp-60h]
  LPVOID v15; // [rsp+40h] [rbp-40h] BYREF
  __int128 v16; // [rsp+48h] [rbp-38h] BYREF
  _BYTE pvarg[32]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v15 = 0;
  v16 = 0;
  memset(pvarg, 0, sizeof(pvarg));
  VariantInit((VARIANTARG *)pvarg);
  v5 = CCoInit::Initialize(this, v4, 0);
  if ( v5 < 0 )
  {
    v6 = 125;
LABEL_28:
    v9 = (unsigned int)v5;
    goto LABEL_29;
  }
  v7 = CoCreateInstance(&CLSID_UpdatePolicyReader, 0, 1u, &GUID_152807bd_4d18_46c5_ae31_dd8d597d0559, &v15);
  v5 = v7;
  if ( v7 < 0 )
  {
    if ( v7 != -2147221164 )
    {
      v6 = 135;
      goto LABEL_28;
    }
LABEL_18:
    v5 = 0;
    goto LABEL_19;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int128 *))(*(_QWORD *)v15 + 32LL))(v15, a2, &v16);
  v5 = v8;
  if ( v8 >= 0 )
  {
    *((_QWORD *)this + 4) = *(_QWORD *)&pvarg[24];
    v10 = DWORD1(v16);
    if ( DWORD1(v16) == 1 )
    {
      *((_BYTE *)this + 4) = 1;
    }
    else
    {
      if ( DWORD1(v16) == 2 )
        *((_BYTE *)this + 5) = 1;
      if ( v10 != 3 )
        goto LABEL_18;
    }
    switch ( *(_WORD *)pvarg )
    {
      case 0x15:
        *((_QWORD *)this + 3) = *(_QWORD *)&pvarg[8];
        break;
      case 3:
        *((_DWORD *)this + 4) = *(_DWORD *)&pvarg[8];
        break;
      case 8:
        v12 = (void *)*((_QWORD *)this + 1);
        if ( v12 )
        {
          SusFree(v12);
          *((_QWORD *)this + 1) = 0;
        }
        v13 = DuplicateOptionalString<wchar_t *,wchar_t *>(*(_QWORD *)&pvarg[8], (char *)this + 8);
        v5 = v13;
        if ( v13 < 0 )
        {
          v9 = (unsigned int)v13;
          v6 = 168;
          goto LABEL_29;
        }
        break;
      default:
        v5 = -2145120257;
        v6 = 174;
        goto LABEL_28;
    }
    *((_DWORD *)this + 5) = DWORD2(v16);
    goto LABEL_18;
  }
  v9 = (unsigned int)v8;
  v6 = 139;
LABEL_29:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\EnterprisePolicy\\EnterpriseBackedPolicy.cpp",
    (const char *)v9,
    ppv);
LABEL_19:
  VariantClear((VARIANTARG *)pvarg);
  if ( v15 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004e650  mov     [rsp-18h+arg_10], rbx
0x18004e655  push    rbp
0x18004e656  push    rsi
0x18004e657  push    rdi
0x18004e658  mov     rbp, rsp
0x18004e65b  sub     rsp, 80h
0x18004e662  mov     rax, cs:__security_cookie
0x18004e669  xor     rax, rsp
0x18004e66c  mov     [rbp+var_8], rax
0x18004e670  mov     esi, edx
0x18004e672  mov     rdi, rcx
0x18004e675  mov     [rbp+var_40], 0
0x18004e67d  xorps   xmm0, xmm0
0x18004e680  movups  [rbp+var_38], xmm0
0x18004e684  movups  xmmword ptr [rbp+pvarg], xmm0
0x18004e688  movups  xmmword ptr [rbp+pvarg+10h], xmm0
0x18004e68c  lea     rcx, [rbp+pvarg]; pvarg
0x18004e690  call    cs:__imp_VariantInit
0x18004e696  lea     rax, [rbp+var_38]
0x18004e69a  mov     [rbp+var_50], rax
0x18004e69e  mov     [rbp+var_48], 1
0x18004e6a2  xor     r8d, r8d; bool
0x18004e6a5  mov     rcx, rdi; this
0x18004e6a8  call    ?Initialize@CCoInit@@QEAAJK_N@Z; CCoInit::Initialize(ulong,bool)
0x18004e6ad  mov     ebx, eax
0x18004e6af  test    eax, eax
0x18004e6b1  jns     short loc_18004E6BD
0x18004e6b3  mov     edx, 7Dh ; '}'
0x18004e6b8  jmp     loc_18004E811
0x18004e6bd  mov     rcx, [rbp+var_40]
0x18004e6c1  test    rcx, rcx
0x18004e6c4  jz      short loc_18004E6DA
0x18004e6c6  mov     rax, [rcx]
0x18004e6c9  mov     rax, [rax+10h]
0x18004e6cd  call    _guard_dispatch_icall
0x18004e6d2  mov     [rbp+var_40], 0
0x18004e6da  lea     rax, [rbp+var_40]
0x18004e6de  mov     qword ptr [rsp+80h+ppv], rax; int
0x18004e6e3  lea     r9, _GUID_152807bd_4d18_46c5_ae31_dd8d597d0559; riid
0x18004e6ea  xor     edx, edx; pUnkOuter
0x18004e6ec  lea     r8d, [rdx+1]; dwClsContext
0x18004e6f0  lea     rcx, CLSID_UpdatePolicyReader; rclsid
0x18004e6f7  call    cs:__imp_CoCreateInstance
0x18004e6fd  mov     ebx, eax
0x18004e6ff  test    eax, eax
0x18004e701  jns     short loc_18004E714
0x18004e703  cmp     eax, 80040154h
0x18004e708  jz      short loc_18004E789
0x18004e70a  mov     edx, 87h
0x18004e70f  jmp     loc_18004E811
0x18004e714  mov     rcx, [rbp+var_40]
0x18004e718  mov     rax, [rcx]
0x18004e71b  lea     r8, [rbp+var_38]
0x18004e71f  mov     edx, esi
0x18004e721  mov     rax, [rax+20h]
0x18004e725  call    _guard_dispatch_icall
0x18004e72a  mov     ebx, eax
0x18004e72c  test    eax, eax
0x18004e72e  jns     short loc_18004E73D
0x18004e730  mov     r9d, eax
0x18004e733  mov     edx, 8Bh
0x18004e738  jmp     loc_18004E814
0x18004e73d  mov     rax, qword ptr [rbp+pvarg+18h]
0x18004e741  mov     [rdi+20h], rax
0x18004e745  mov     ecx, 3
0x18004e74a  mov     eax, dword ptr [rbp+var_38+4]
0x18004e74d  cmp     eax, 1
0x18004e750  jnz     short loc_18004E757
0x18004e752  mov     [rdi+4], al
0x18004e755  jmp     short loc_18004E764
0x18004e757  cmp     eax, 2
0x18004e75a  jnz     short loc_18004E760
0x18004e75c  mov     byte ptr [rdi+5], 1
0x18004e760  cmp     eax, ecx
0x18004e762  jnz     short loc_18004E789
0x18004e764  movzx   eax, word ptr [rbp+pvarg]
0x18004e768  cmp     ax, 15h
0x18004e76c  jnz     short loc_18004E778
0x18004e76e  mov     rax, qword ptr [rbp+pvarg+8]
0x18004e772  mov     [rdi+18h], rax
0x18004e776  jmp     short loc_18004E783
0x18004e778  cmp     ax, cx
0x18004e77b  jnz     short loc_18004E7CD
0x18004e77d  mov     eax, dword ptr [rbp+pvarg+8]
0x18004e780  mov     [rdi+10h], eax
0x18004e783  mov     eax, dword ptr [rbp+var_38+8]
0x18004e786  mov     [rdi+14h], eax
0x18004e789  xor     ebx, ebx
0x18004e78b  lea     rcx, [rbp+pvarg]; pvarg
0x18004e78f  call    cs:__imp_VariantClear
0x18004e795  nop
0x18004e796  mov     rcx, [rbp+var_40]
0x18004e79a  test    rcx, rcx
0x18004e79d  jz      short loc_18004E7AC
0x18004e79f  mov     rdx, [rcx]
0x18004e7a2  mov     rax, [rdx+10h]
0x18004e7a6  call    _guard_dispatch_icall
0x18004e7ab  nop
0x18004e7ac  mov     eax, ebx
0x18004e7ae  mov     rcx, [rbp+var_8]
0x18004e7b2  xor     rcx, rsp; StackCookie
0x18004e7b5  call    __security_check_cookie
0x18004e7ba  mov     rbx, [rsp+80h+arg_10]
0x18004e7c2  add     rsp, 80h
0x18004e7c9  pop     rdi
0x18004e7ca  pop     rsi
0x18004e7cb  pop     rbp
0x18004e7cc  retn
0x18004e7cd  cmp     ax, 8
0x18004e7d1  jnz     short loc_18004E807
0x18004e7d3  lea     rbx, [rdi+8]
0x18004e7d7  mov     rcx, [rbx]; lpMem
0x18004e7da  test    rcx, rcx
0x18004e7dd  jz      short loc_18004E7EB
0x18004e7df  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18004e7e4  mov     qword ptr [rbx], 0
0x18004e7eb  mov     rdx, rbx
0x18004e7ee  mov     rcx, qword ptr [rbp+pvarg+8]
0x18004e7f2  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18004e7f7  mov     ebx, eax
0x18004e7f9  test    eax, eax
0x18004e7fb  jns     short loc_18004E783
0x18004e7fd  mov     r9d, eax
0x18004e800  mov     edx, 0A8h
0x18004e805  jmp     short loc_18004E814
0x18004e807  mov     ebx, 80240FFFh
0x18004e80c  mov     edx, 0AEh; void *
0x18004e811  mov     r9d, ebx; char *
0x18004e814  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\Enterp"...
0x18004e81b  mov     rcx, [rbp+18h]; this
0x18004e81f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e824  jmp     loc_18004E78B
```
