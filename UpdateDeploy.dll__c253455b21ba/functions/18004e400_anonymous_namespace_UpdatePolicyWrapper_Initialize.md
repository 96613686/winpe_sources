# _anonymous_namespace_::UpdatePolicyWrapper::Initialize

- ea: `0x18004e400`
- end: `0x18004e648`
- name: `_anonymous_namespace_::UpdatePolicyWrapper::Initialize`
- size: `584`
- prototype: `__int64 __fastcall(CCoInit *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004e830`

## callees

- `0x180003180`
- `0x180007b9c`
- `0x180008f5c`
- `0x18000dce4`
- `0x18004e400`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e503`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e503`
- `OLEAUT32!__imp_VariantInit` at `0x18004e449`
- `OLEAUT32!__imp_VariantInit` at `0x18004e449`
- `OLEAUT32!__imp_VariantClear` at `0x18004e5f9`
- `OLEAUT32!__imp_VariantClear` at `0x18004e605`
- `OLEAUT32!__imp_VariantClear` at `0x18004e5f9`
- `OLEAUT32!__imp_VariantClear` at `0x18004e605`

## string_xrefs

- `0x18004e46b`: `SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall anonymous_namespace_::UpdatePolicyWrapper::Initialize(CCoInit *this, unsigned int a2)
{
  unsigned int v4; // edx
  const wchar_t *v5; // rax
  __int64 *v6; // rax
  int v7; // ebx
  __int64 v8; // rdx
  int v9; // edi
  HRESULT v10; // eax
  int v11; // eax
  unsigned __int64 v12; // r9
  int v13; // edi
  void *v14; // rcx
  int v15; // eax
  int ppv; // [rsp+20h] [rbp-60h]
  LPVOID v18; // [rsp+40h] [rbp-40h] BYREF
  __int128 v19; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v18 = 0;
  v19 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v5 = (const wchar_t *)qword_18007F460;
  do
  {
    if ( a2 == *(_DWORD *)v5 )
    {
      v9 = 1;
      goto LABEL_10;
    }
    v5 += 2;
  }
  while ( v5 != L"SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate" );
  v6 = &qword_18007F450;
  while ( a2 != *(_DWORD *)v6 )
  {
    v6 = (__int64 *)((char *)v6 + 4);
    if ( v6 == &qword_18007F458 )
    {
      v7 = -2147024809;
      v8 = 64;
      goto LABEL_30;
    }
  }
  v9 = 2;
LABEL_10:
  v7 = CCoInit::Initialize(this, v4, 0);
  if ( v7 < 0 )
  {
    v8 = 65;
LABEL_30:
    v12 = (unsigned int)v7;
    goto LABEL_31;
  }
  v10 = CoCreateInstance(&CLSID_UpdatePolicyReader, 0, 1u, &GUID_152807bd_4d18_46c5_ae31_dd8d597d0559, &v18);
  v7 = v10;
  if ( v10 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int128 *))(*(_QWORD *)v18 + 24LL))(v18, a2, &v19);
    v7 = v11;
    if ( v11 < 0 )
    {
      v12 = (unsigned int)v11;
      v8 = 79;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\EnterprisePolicy\\EnterpriseBackedPolicy.cpp",
        (const char *)v12,
        ppv);
      goto LABEL_37;
    }
    if ( DWORD1(v19) == 1 )
    {
      *((_BYTE *)this + 4) = 1;
      *((_DWORD *)this + 5) = DWORD2(v19);
      v13 = v9 - 1;
      if ( v13 )
      {
        if ( v13 != 1 )
        {
          *((_BYTE *)this + 4) = 0;
          v7 = -2147024809;
          v8 = 103;
          goto LABEL_30;
        }
        if ( pvarg.vt != 8 )
        {
          v8 = 96;
LABEL_29:
          v7 = -2145120257;
          goto LABEL_30;
        }
        v14 = (void *)*((_QWORD *)this + 1);
        if ( v14 )
        {
          SusFree(v14);
          *((_QWORD *)this + 1) = 0;
        }
        v15 = DuplicateOptionalString<wchar_t *,wchar_t *>(pvarg.llVal, (char *)this + 8);
        v7 = v15;
        if ( v15 < 0 )
        {
          v12 = (unsigned int)v15;
          v8 = 97;
          goto LABEL_31;
        }
      }
      else
      {
        if ( pvarg.vt != 3 )
        {
          v8 = 91;
          goto LABEL_29;
        }
        *((_DWORD *)this + 4) = pvarg.lVal;
      }
    }
    else if ( DWORD1(v19) == 2 )
    {
      *((_BYTE *)this + 5) = 1;
    }
    VariantClear(&pvarg);
    goto LABEL_36;
  }
  if ( v10 != -2147221164 )
  {
    v8 = 75;
    goto LABEL_30;
  }
LABEL_36:
  v7 = 0;
LABEL_37:
  VariantClear(&pvarg);
  if ( v18 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004e400  mov     [rsp-18h+arg_10], rbx
0x18004e405  mov     [rsp-18h+arg_18], rsi
0x18004e40a  push    rbp
0x18004e40b  push    rdi
0x18004e40c  push    r14
0x18004e40e  mov     rbp, rsp
0x18004e411  sub     rsp, 80h
0x18004e418  mov     rax, cs:__security_cookie
0x18004e41f  xor     rax, rsp
0x18004e422  mov     [rbp+var_10], rax
0x18004e426  mov     r14d, edx
0x18004e429  mov     rsi, rcx
0x18004e42c  mov     [rbp+var_40], 0
0x18004e434  xorps   xmm0, xmm0
0x18004e437  xor     eax, eax
0x18004e439  movups  [rbp+var_38], xmm0
0x18004e43d  movups  xmmword ptr [rbp+pvarg], xmm0
0x18004e441  mov     qword ptr [rbp+pvarg+10h], rax
0x18004e445  lea     rcx, [rbp+pvarg]; pvarg
0x18004e449  call    cs:__imp_VariantInit
0x18004e44f  lea     rax, [rbp+var_38]
0x18004e453  mov     [rbp+var_50], rax
0x18004e457  mov     [rbp+var_48], 1
0x18004e45b  lea     rax, qword_18007F460
0x18004e462  cmp     r14d, [rax]
0x18004e465  jz      short loc_18004E4A9
0x18004e467  add     rax, 4
0x18004e46b  lea     rcx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18004e472  cmp     rax, rcx
0x18004e475  jnz     short loc_18004E462
0x18004e477  lea     rax, qword_18007F450
0x18004e47e  cmp     r14d, [rax]
0x18004e481  jz      short loc_18004E4A2
0x18004e483  add     rax, 4
0x18004e487  lea     rcx, qword_18007F458
0x18004e48e  cmp     rax, rcx
0x18004e491  jnz     short loc_18004E47E
0x18004e493  mov     ebx, 80070057h
0x18004e498  mov     edx, 40h ; '@'
0x18004e49d  jmp     loc_18004E5CE
0x18004e4a2  mov     edi, 2
0x18004e4a7  jmp     short loc_18004E4AE
0x18004e4a9  mov     edi, 1
0x18004e4ae  xor     r8d, r8d; bool
0x18004e4b1  mov     rcx, rsi; this
0x18004e4b4  call    ?Initialize@CCoInit@@QEAAJK_N@Z; CCoInit::Initialize(ulong,bool)
0x18004e4b9  mov     ebx, eax
0x18004e4bb  test    eax, eax
0x18004e4bd  jns     short loc_18004E4C9
0x18004e4bf  mov     edx, 41h ; 'A'
0x18004e4c4  jmp     loc_18004E5CE
0x18004e4c9  mov     rcx, [rbp+var_40]
0x18004e4cd  test    rcx, rcx
0x18004e4d0  jz      short loc_18004E4E6
0x18004e4d2  mov     rax, [rcx]
0x18004e4d5  mov     rax, [rax+10h]
0x18004e4d9  call    _guard_dispatch_icall
0x18004e4de  mov     [rbp+var_40], 0
0x18004e4e6  lea     rax, [rbp+var_40]
0x18004e4ea  mov     qword ptr [rsp+80h+ppv], rax; int
0x18004e4ef  lea     r9, _GUID_152807bd_4d18_46c5_ae31_dd8d597d0559; riid
0x18004e4f6  xor     edx, edx; pUnkOuter
0x18004e4f8  lea     r8d, [rdx+1]; dwClsContext
0x18004e4fc  lea     rcx, CLSID_UpdatePolicyReader; rclsid
0x18004e503  call    cs:__imp_CoCreateInstance
0x18004e509  mov     ebx, eax
0x18004e50b  test    eax, eax
0x18004e50d  jns     short loc_18004E524
0x18004e50f  cmp     eax, 80040154h
0x18004e514  jz      loc_18004E5FF
0x18004e51a  mov     edx, 4Bh ; 'K'
0x18004e51f  jmp     loc_18004E5CE
0x18004e524  mov     rcx, [rbp+var_40]
0x18004e528  mov     rax, [rcx]
0x18004e52b  lea     r8, [rbp+var_38]
0x18004e52f  mov     edx, r14d
0x18004e532  mov     rax, [rax+18h]
0x18004e536  call    _guard_dispatch_icall
0x18004e53b  mov     ebx, eax
0x18004e53d  test    eax, eax
0x18004e53f  jns     short loc_18004E54E
0x18004e541  mov     r9d, eax
0x18004e544  mov     edx, 4Fh ; 'O'
0x18004e549  jmp     loc_18004E5D1
0x18004e54e  cmp     dword ptr [rbp+var_38+4], 1
0x18004e552  jnz     loc_18004E5EB
0x18004e558  mov     byte ptr [rsi+4], 1
0x18004e55c  mov     eax, dword ptr [rbp+var_38+8]
0x18004e55f  mov     [rsi+14h], eax
0x18004e562  sub     edi, 1
0x18004e565  jz      short loc_18004E5BD
0x18004e567  cmp     edi, 1
0x18004e56a  jz      short loc_18004E57C
0x18004e56c  mov     byte ptr [rsi+4], 0
0x18004e570  mov     ebx, 80070057h
0x18004e575  mov     edx, 67h ; 'g'
0x18004e57a  jmp     short loc_18004E5CE
0x18004e57c  cmp     word ptr [rbp+pvarg], 8
0x18004e581  jz      short loc_18004E58A
0x18004e583  mov     edx, 60h ; '`'
0x18004e588  jmp     short loc_18004E5C9
0x18004e58a  mov     rcx, [rsi+8]; lpMem
0x18004e58e  test    rcx, rcx
0x18004e591  jz      short loc_18004E5A0
0x18004e593  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18004e598  mov     qword ptr [rsi+8], 0
0x18004e5a0  lea     rdx, [rsi+8]
0x18004e5a4  mov     rcx, qword ptr [rbp+pvarg+8]
0x18004e5a8  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18004e5ad  mov     ebx, eax
0x18004e5af  test    eax, eax
0x18004e5b1  jns     short loc_18004E5F5
0x18004e5b3  mov     r9d, eax
0x18004e5b6  mov     edx, 61h ; 'a'
0x18004e5bb  jmp     short loc_18004E5D1
0x18004e5bd  cmp     word ptr [rbp+pvarg], 3
0x18004e5c2  jz      short loc_18004E5E3
0x18004e5c4  mov     edx, 5Bh ; '['; void *
0x18004e5c9  mov     ebx, 80240FFFh
0x18004e5ce  mov     r9d, ebx; char *
0x18004e5d1  mov     rcx, [rbp+18h]; this
0x18004e5d5  lea     r8, aCW1SSrcClientL_25; "C:\\__w\\1\\s\\src\\Client\\lib\\Enterp"...
0x18004e5dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e5e1  jmp     short loc_18004E601
0x18004e5e3  mov     eax, dword ptr [rbp+pvarg+8]
0x18004e5e6  mov     [rsi+10h], eax
0x18004e5e9  jmp     short loc_18004E5F5
0x18004e5eb  cmp     dword ptr [rbp+var_38+4], 2
0x18004e5ef  jnz     short loc_18004E5F5
0x18004e5f1  mov     byte ptr [rsi+5], 1
0x18004e5f5  lea     rcx, [rbp+pvarg]; pvarg
0x18004e5f9  call    cs:__imp_VariantClear
0x18004e5ff  xor     ebx, ebx
0x18004e601  lea     rcx, [rbp+pvarg]; pvarg
0x18004e605  call    cs:__imp_VariantClear
0x18004e60b  nop
0x18004e60c  mov     rcx, [rbp+var_40]
0x18004e610  test    rcx, rcx
0x18004e613  jz      short loc_18004E622
0x18004e615  mov     rdx, [rcx]
0x18004e618  mov     rax, [rdx+10h]
0x18004e61c  call    _guard_dispatch_icall
0x18004e621  nop
0x18004e622  mov     eax, ebx
0x18004e624  mov     rcx, [rbp+var_10]
0x18004e628  xor     rcx, rsp; StackCookie
0x18004e62b  call    __security_check_cookie
0x18004e630  lea     r11, [rsp+80h+var_s0]
0x18004e638  mov     rbx, [r11+30h]
0x18004e63c  mov     rsi, [r11+38h]
0x18004e640  mov     rsp, r11
0x18004e643  pop     r14
0x18004e645  pop     rdi
0x18004e646  pop     rbp
0x18004e647  retn
```
