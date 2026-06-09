# ScriptHelpers::JSONStringify(IDispatchEx *,ATL::CComVariant &,ATL::CComBSTR &)

- ea: `0x18002e948`
- end: `0x18002ec50`
- name: `?JSONStringify@ScriptHelpers@@YAJPEAUIDispatchEx@@AEAVCComVariant@ATL@@AEAVCComBSTR@4@@Z`
- size: `776`
- prototype: `__int64 __fastcall(ScriptHelpers *__hidden this, struct IDispatchEx *, struct ATL::CComVariant *, struct ATL::CComBSTR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180007f08`

## callees

- `0x180003858`
- `0x18002e948`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002e994`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ea89`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ebc0`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e994`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ea89`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ebc0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e984`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ead3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002eb6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002eb9c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ebb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ebe1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ec0b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e984`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ead3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002eb6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002eb9c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ebb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ebe1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ec0b`
- `OLEAUT32!__imp_VariantInit` at `0x18002e9ec`
- `OLEAUT32!__imp_VariantInit` at `0x18002eb0f`
- `OLEAUT32!__imp_VariantInit` at `0x18002e9ec`
- `OLEAUT32!__imp_VariantInit` at `0x18002eb0f`
- `OLEAUT32!__imp_VariantClear` at `0x18002ea41`
- `OLEAUT32!__imp_VariantClear` at `0x18002eb65`
- `OLEAUT32!__imp_VariantClear` at `0x18002eb90`
- `OLEAUT32!__imp_VariantClear` at `0x18002ebd7`
- `OLEAUT32!__imp_VariantClear` at `0x18002ec01`
- `OLEAUT32!__imp_VariantClear` at `0x18002ea41`
- `OLEAUT32!__imp_VariantClear` at `0x18002eb65`
- `OLEAUT32!__imp_VariantClear` at `0x18002eb90`
- `OLEAUT32!__imp_VariantClear` at `0x18002ebd7`
- `OLEAUT32!__imp_VariantClear` at `0x18002ec01`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ScriptHelpers::JSONStringify(
        ScriptHelpers *this,
        struct IDispatchEx *a2,
        BSTR *a3,
        struct ATL::CComBSTR *a4)
{
  BSTR v8; // rax
  OLECHAR *v9; // rdi
  int v10; // ebx
  __int64 v11; // rcx
  BSTR v12; // rax
  OLECHAR *v13; // rbx
  int v14; // r14d
  const OLECHAR *bstrVal; // r14
  BSTR v16; // rax
  __int64 v17; // [rsp+50h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v19[3]; // [rsp+70h] [rbp-29h] BYREF
  VARIANTARG v20; // [rsp+88h] [rbp-11h] BYREF
  __int128 v21; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v22; // [rsp+B0h] [rbp+17h]
  BSTR v23; // [rsp+B8h] [rbp+1Fh]
  BSTR v24; // [rsp+C0h] [rbp+27h]
  unsigned int v25; // [rsp+100h] [rbp+67h] BYREF
  unsigned int v26; // [rsp+118h] [rbp+7Fh] BYREF

  if ( !this )
    return 2147942487LL;
  SysFreeString(*a3);
  *a3 = 0;
  v8 = SysAllocString(L"JSON");
  v9 = v8;
  v23 = v8;
  if ( !v8 )
    ATL::AtlThrowImpl(-2147024882);
  v25 = 0;
  v10 = (*(__int64 (__fastcall **)(ScriptHelpers *, BSTR, _QWORD, unsigned int *))(*(_QWORD *)this + 56LL))(
          this,
          v8,
          0,
          &v25);
  if ( v10 )
  {
    if ( v10 >= 0 )
      v10 = -2147467259;
    goto LABEL_28;
  }
  v21 = 0;
  v22 = 0;
  VariantInit(&pvarg);
  v10 = (*(__int64 (__fastcall **)(ScriptHelpers *, _QWORD, __int64, __int64, __int128 *, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)this + 64LL))(
          this,
          v25,
          1024,
          2,
          &v21,
          &pvarg,
          0,
          0);
  if ( v10 )
  {
    if ( v10 >= 0 )
      v10 = -2147467259;
    VariantClear(&pvarg);
    goto LABEL_28;
  }
  v11 = 0;
  v17 = 0;
  if ( pvarg.llVal )
  {
    (**(void (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(
      pvarg.llVal,
      &GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9,
      &v17);
    v11 = v17;
  }
  if ( v11 )
  {
    v12 = SysAllocString(L"stringify");
    v13 = v12;
    v24 = v12;
    if ( !v12 )
      ATL::AtlThrowImpl(-2147024882);
    v26 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, unsigned int *))(*(_QWORD *)v17 + 56LL))(v17, v12, 0, &v26);
    if ( v14 )
    {
      if ( v14 >= 0 )
        v14 = -2147467259;
      SysFreeString(v13);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
LABEL_27:
      VariantClear(&pvarg);
      v10 = v14;
LABEL_28:
      SysFreeString(v9);
      return (unsigned int)v10;
    }
    v19[1] = 0;
    v19[2] = 1;
    v19[0] = a2;
    VariantInit(&v20);
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, _QWORD *, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
            v17,
            v26,
            1024,
            1,
            v19,
            &v20,
            0,
            0);
    if ( v14 )
    {
      if ( v14 >= 0 )
        v14 = -2147467259;
      VariantClear(&v20);
      SysFreeString(v13);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      goto LABEL_27;
    }
    bstrVal = v20.bstrVal;
    if ( v20.bstrVal != *a3 )
    {
      SysFreeString(*a3);
      if ( bstrVal )
      {
        v16 = SysAllocString(bstrVal);
        *a3 = v16;
        if ( !v16 )
          ATL::AtlThrowImpl(-2147024882);
      }
      else
      {
        *a3 = 0;
      }
    }
    VariantClear(&v20);
    SysFreeString(v13);
    v11 = v17;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  VariantClear(&pvarg);
  SysFreeString(v9);
  return 0;
}

```

## disassembly

```asm
0x18002e948  mov     [rsp-8+arg_8], rbx
0x18002e94d  mov     [rsp-8+arg_10], rsi
0x18002e952  push    rbp
0x18002e953  push    rdi
0x18002e954  push    r12
0x18002e956  push    r14
0x18002e958  push    r15
0x18002e95a  lea     rbp, [rsp-37h]
0x18002e95f  sub     rsp, 0D0h
0x18002e966  mov     rsi, r8
0x18002e969  mov     r15, rdx
0x18002e96c  mov     r14, rcx
0x18002e96f  xor     r12d, r12d
0x18002e972  test    rcx, rcx
0x18002e975  jnz     short loc_18002E981
0x18002e977  mov     eax, 80070057h
0x18002e97c  jmp     loc_18002EC13
0x18002e981  mov     rcx, [r8]; bstrString
0x18002e984  call    cs:__imp_SysFreeString
0x18002e98a  mov     [rsi], r12
0x18002e98d  lea     rcx, aJson; "JSON"
0x18002e994  call    cs:__imp_SysAllocString
0x18002e99a  mov     rdi, rax
0x18002e99d  mov     [rbp+57h+var_38], rax
0x18002e9a1  test    rax, rax
0x18002e9a4  jz      loc_18002EC45
0x18002e9aa  mov     [rbp+57h+arg_0], r12d
0x18002e9ae  mov     rax, [r14]
0x18002e9b1  lea     r9, [rbp+57h+arg_0]
0x18002e9b5  xor     r8d, r8d
0x18002e9b8  mov     rdx, rdi
0x18002e9bb  mov     rcx, r14
0x18002e9be  mov     rax, [rax+38h]
0x18002e9c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9c7  mov     ebx, eax
0x18002e9c9  test    eax, eax
0x18002e9cb  jz      short loc_18002E9DC
0x18002e9cd  mov     eax, 80004005h
0x18002e9d2  test    ebx, ebx
0x18002e9d4  cmovns  ebx, eax
0x18002e9d7  jmp     loc_18002EB99
0x18002e9dc  xorps   xmm0, xmm0
0x18002e9df  movdqu  [rbp+57h+var_50], xmm0
0x18002e9e4  mov     [rbp+57h+var_40], r12
0x18002e9e8  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002e9ec  call    cs:__imp_VariantInit
0x18002e9f2  nop
0x18002e9f3  mov     rax, [r14]
0x18002e9f6  mov     r9d, 2
0x18002e9fc  mov     [rsp+0F0h+var_B8], r12
0x18002ea01  mov     [rsp+0F0h+var_C0], r12
0x18002ea06  lea     rcx, [rbp+57h+pvarg]
0x18002ea0a  mov     [rsp+0F0h+var_C8], rcx
0x18002ea0f  lea     rcx, [rbp+57h+var_50]
0x18002ea13  mov     [rsp+0F0h+var_D0], rcx
0x18002ea18  mov     r8d, 400h
0x18002ea1e  mov     edx, [rbp+57h+arg_0]
0x18002ea21  mov     rcx, r14
0x18002ea24  mov     rax, [rax+40h]
0x18002ea28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea2d  mov     ebx, eax
0x18002ea2f  test    eax, eax
0x18002ea31  jz      short loc_18002EA4C
0x18002ea33  mov     eax, 80004005h
0x18002ea38  test    ebx, ebx
0x18002ea3a  cmovns  ebx, eax
0x18002ea3d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002ea41  call    cs:__imp_VariantClear
0x18002ea47  jmp     loc_18002EB99
0x18002ea4c  mov     r9, qword ptr [rbp+57h+pvarg+8]
0x18002ea50  mov     rcx, r12
0x18002ea53  mov     [rbp+57h+var_A0], rcx
0x18002ea57  test    r9, r9
0x18002ea5a  jz      short loc_18002EA79
0x18002ea5c  mov     rax, [r9]
0x18002ea5f  lea     r8, [rbp+57h+var_A0]
0x18002ea63  lea     rdx, _GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9
0x18002ea6a  mov     rcx, r9
0x18002ea6d  mov     rax, [rax]
0x18002ea70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea75  mov     rcx, [rbp+57h+var_A0]
0x18002ea79  test    rcx, rcx
0x18002ea7c  jz      loc_18002EBEB
0x18002ea82  lea     rcx, aStringify; "stringify"
0x18002ea89  call    cs:__imp_SysAllocString
0x18002ea8f  mov     rbx, rax
0x18002ea92  mov     [rbp+57h+var_30], rax
0x18002ea96  test    rax, rax
0x18002ea99  jz      loc_18002EC2F
0x18002ea9f  mov     [rbp+57h+arg_18], r12d
0x18002eaa3  mov     rcx, [rbp+57h+var_A0]
0x18002eaa7  mov     rax, [rcx]
0x18002eaaa  lea     r9, [rbp+57h+arg_18]
0x18002eaae  xor     r8d, r8d
0x18002eab1  mov     rdx, rbx
0x18002eab4  mov     rax, [rax+38h]
0x18002eab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eabd  mov     r14d, eax
0x18002eac0  test    eax, eax
0x18002eac2  jz      short loc_18002EAF5
0x18002eac4  mov     eax, 80004005h
0x18002eac9  test    r14d, r14d
0x18002eacc  cmovns  r14d, eax
0x18002ead0  mov     rcx, rbx; bstrString
0x18002ead3  call    cs:__imp_SysFreeString
0x18002ead9  nop
0x18002eada  mov     rcx, [rbp+57h+var_A0]
0x18002eade  test    rcx, rcx
0x18002eae1  jz      short loc_18002EAF0
0x18002eae3  mov     rax, [rcx]
0x18002eae6  mov     rax, [rax+10h]
0x18002eaea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eaef  nop
0x18002eaf0  jmp     loc_18002EB8C
0x18002eaf5  mov     [rbp+57h+var_78], r12
0x18002eaf9  mov     [rbp+57h+var_70], 1
0x18002eb01  mov     [rbp+57h+var_80], r15
0x18002eb05  mov     r14d, 1
0x18002eb0b  lea     rcx, [rbp+57h+var_68]; pvarg
0x18002eb0f  call    cs:__imp_VariantInit
0x18002eb15  nop
0x18002eb16  mov     rcx, [rbp+57h+var_A0]
0x18002eb1a  mov     rax, [rcx]
0x18002eb1d  mov     r9d, r14d
0x18002eb20  mov     [rsp+0F0h+var_B8], r12
0x18002eb25  mov     [rsp+0F0h+var_C0], r12
0x18002eb2a  lea     rdx, [rbp+57h+var_68]
0x18002eb2e  mov     [rsp+0F0h+var_C8], rdx
0x18002eb33  lea     rdx, [rbp+57h+var_80]
0x18002eb37  mov     [rsp+0F0h+var_D0], rdx
0x18002eb3c  mov     r8d, 400h
0x18002eb42  mov     edx, [rbp+57h+arg_18]
0x18002eb45  mov     rax, [rax+40h]
0x18002eb49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb4e  mov     r14d, eax
0x18002eb51  test    eax, eax
0x18002eb53  jz      short loc_18002EBA6
0x18002eb55  mov     eax, 80004005h
0x18002eb5a  test    r14d, r14d
0x18002eb5d  cmovns  r14d, eax
0x18002eb61  lea     rcx, [rbp+57h+var_68]; pvarg
0x18002eb65  call    cs:__imp_VariantClear
0x18002eb6b  nop
0x18002eb6c  mov     rcx, rbx; bstrString
0x18002eb6f  call    cs:__imp_SysFreeString
0x18002eb75  nop
0x18002eb76  mov     rcx, [rbp+57h+var_A0]
0x18002eb7a  test    rcx, rcx
0x18002eb7d  jz      short loc_18002EB8C
0x18002eb7f  mov     rax, [rcx]
0x18002eb82  mov     rax, [rax+10h]
0x18002eb86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb8b  nop
0x18002eb8c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002eb90  call    cs:__imp_VariantClear
0x18002eb96  mov     ebx, r14d
0x18002eb99  mov     rcx, rdi; bstrString
0x18002eb9c  call    cs:__imp_SysFreeString
0x18002eba2  mov     eax, ebx
0x18002eba4  jmp     short loc_18002EC13
0x18002eba6  mov     r14, qword ptr [rbp+57h+var_68+8]
0x18002ebaa  cmp     r14, [rsi]
0x18002ebad  jz      short loc_18002EBD3
0x18002ebaf  mov     rcx, [rsi]; bstrString
0x18002ebb2  call    cs:__imp_SysFreeString
0x18002ebb8  test    r14, r14
0x18002ebbb  jz      short loc_18002EBD0
0x18002ebbd  mov     rcx, r14; psz
0x18002ebc0  call    cs:__imp_SysAllocString
0x18002ebc6  mov     [rsi], rax
0x18002ebc9  test    rax, rax
0x18002ebcc  jz      short loc_18002EC3A
0x18002ebce  jmp     short loc_18002EBD3
0x18002ebd0  mov     [rsi], r12
0x18002ebd3  lea     rcx, [rbp+57h+var_68]; pvarg
0x18002ebd7  call    cs:__imp_VariantClear
0x18002ebdd  nop
0x18002ebde  mov     rcx, rbx; bstrString
0x18002ebe1  call    cs:__imp_SysFreeString
0x18002ebe7  mov     rcx, [rbp+57h+var_A0]
0x18002ebeb  test    rcx, rcx
0x18002ebee  jz      short loc_18002EBFD
0x18002ebf0  mov     rax, [rcx]
0x18002ebf3  mov     rax, [rax+10h]
0x18002ebf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebfc  nop
0x18002ebfd  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002ec01  call    cs:__imp_VariantClear
0x18002ec07  nop
0x18002ec08  mov     rcx, rdi; bstrString
0x18002ec0b  call    cs:__imp_SysFreeString
0x18002ec11  xor     eax, eax
0x18002ec13  lea     r11, [rsp+0F0h+var_20]
0x18002ec1b  mov     rbx, [r11+38h]
0x18002ec1f  mov     rsi, [r11+40h]
0x18002ec23  mov     rsp, r11
0x18002ec26  pop     r15
0x18002ec28  pop     r14
0x18002ec2a  pop     r12
0x18002ec2c  pop     rdi
0x18002ec2d  pop     rbp
0x18002ec2e  retn
0x18002ec2f  mov     ecx, 8007000Eh; int
0x18002ec34  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002ec3a  mov     ecx, 8007000Eh; int
0x18002ec3f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002ec45  mov     ecx, 8007000Eh; int
0x18002ec4a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
