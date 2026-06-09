# WINRT_GetActivationFactory

- ea: `0x1800080e0`
- end: `0x18000820f`
- name: `WINRT_GetActivationFactory`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ff80`

## callees

- `0x180003a7d`
- `0x180007b04`
- `0x180007b84`
- `0x180007f00`
- `0x1800080e0`
- `0x18000faa4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180008179`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180008179`

## string_xrefs

- `0x180008151`: `onecoreuap\base\appmodel\AggregatedDataPlatform\Service\ServiceHelper\cppwinrt\objfre\amd64\module.g.cpp`

## pseudocode

```c
__int64 __fastcall WINRT_GetActivationFactory(__int64 a1, char **a2)
{
  const wchar_t *v3; // rdi
  __int64 v4; // rbx
  const wchar_t *v5; // rax
  wchar_t *v6; // rcx
  char *Windows_Internal_AggregatedDataPlatform_AggregatedDataPlatform; // rax
  __int64 result; // rax
  _DWORD *v9; // r8
  unsigned int v10; // ebx
  BSTR bstrString; // [rsp+20h] [rbp-78h] BYREF
  int v12; // [rsp+28h] [rbp-70h]
  int v13; // [rsp+2Ch] [rbp-6Ch]
  __int64 v14; // [rsp+30h] [rbp-68h] BYREF
  int v15; // [rsp+38h] [rbp-60h] BYREF
  const char *v16; // [rsp+40h] [rbp-58h]
  __int64 v17; // [rsp+48h] [rbp-50h]
  _DWORD *v18; // [rsp+50h] [rbp-48h]
  _DWORD v19[4]; // [rsp+58h] [rbp-40h] BYREF
  const wchar_t *v20; // [rsp+68h] [rbp-30h]
  int v21; // [rsp+B0h] [rbp+18h] BYREF

  try
  {
    if ( a1 )
    {
      v3 = *(const wchar_t **)(a1 + 16);
      v4 = *(unsigned int *)(a1 + 4);
      if ( 2 * v4 == 124 )
      {
        v5 = v3 + 62;
        v6 = L"";
        while ( v5 != v3 )
        {
          if ( *--v5 != *--v6 )
            goto LABEL_11;
        }
        Windows_Internal_AggregatedDataPlatform_AggregatedDataPlatform = winrt_make_Windows_Internal_AggregatedDataPlatform_AggregatedDataPlatform();
        *a2 = Windows_Internal_AggregatedDataPlatform_AggregatedDataPlatform;
        if ( Windows_Internal_AggregatedDataPlatform_AggregatedDataPlatform )
          return 0;
        goto LABEL_12;
      }
    }
    else
    {
      v3 = &S2;
      LODWORD(v4) = 0;
    }
LABEL_11:
    *a2 = 0;
LABEL_12:
    v15 = 61;
    v16 = "onecoreuap\\base\\appmodel\\AggregatedDataPlatform\\Service\\ServiceHelper\\cppwinrt\\objfre\\amd64\\module.g.cpp";
    v17 = 0;
    if ( (_DWORD)v4 )
    {
      if ( v3[(unsigned int)v4] )
        abort();
      v19[0] = 1;
      v19[1] = v4;
      v20 = v3;
      v9 = v19;
      v18 = v19;
    }
    else
    {
      v9 = 0;
      v18 = 0;
    }
    bstrString = 0;
    v12 = -1430532899;
    v13 = -2147221231;
    v14 = 0;
    winrt::hresult_error::originate(&bstrString, 2147746065LL, v9, &v15);
    v10 = *(_DWORD *)winrt::hresult_error::to_abi(&bstrString, &v21);
    if ( v14 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
    if ( bstrString )
      WINRT_IMPL_SysFreeString(bstrString);
    result = v10;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v21);
  }
  return result;
}

```

## disassembly

```asm
0x1800080e0  push    rbx
0x1800080e2  push    rsi
0x1800080e3  push    rdi
0x1800080e4  push    r14
0x1800080e6  sub     rsp, 78h
0x1800080ea  mov     rsi, rdx
0x1800080ed  xor     r14d, r14d
0x1800080f0  test    rcx, rcx
0x1800080f3  jz      short loc_18000813C
0x1800080f5  mov     rdi, [rcx+10h]
0x1800080f9  mov     ebx, [rcx+4]
0x1800080fc  lea     rax, [rbx+rbx]
0x180008100  cmp     rax, 7Ch ; '|'
0x180008104  jnz     short loc_180008146
0x180008106  lea     rax, [rdi+7Ch]
0x18000810a  lea     rcx, aWindowsInterna_1+7Ch; ""
0x180008111  cmp     rax, rdi
0x180008114  jz      short loc_180008128
0x180008116  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18000811a  add     rax, 0FFFFFFFFFFFFFFFEh
0x18000811e  movzx   edx, word ptr [rcx]
0x180008121  cmp     [rax], dx
0x180008124  jz      short loc_180008111
0x180008126  jmp     short loc_180008146
0x180008128  call    ?winrt_make_Windows_Internal_AggregatedDataPlatform_AggregatedDataPlatform@@YAPEAXXZ; winrt_make_Windows_Internal_AggregatedDataPlatform_AggregatedDataPlatform(void)
0x18000812d  mov     [rsi], rax
0x180008130  test    rax, rax
0x180008133  jz      short loc_180008149
0x180008135  xor     eax, eax
0x180008137  jmp     loc_180008204
0x18000813c  lea     rdi, S2
0x180008143  mov     rbx, r14
0x180008146  mov     [rsi], r14
0x180008149  mov     [rsp+98h+var_60], 3Dh ; '='
0x180008151  lea     rax, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\AggregatedD"...
0x180008158  mov     [rsp+98h+var_58], rax
0x18000815d  mov     [rsp+98h+var_50], r14
0x180008162  test    ebx, ebx
0x180008164  jnz     short loc_180008170
0x180008166  mov     r8, r14
0x180008169  mov     [rsp+98h+var_48], r14
0x18000816e  jmp     short loc_18000819B
0x180008170  mov     eax, ebx
0x180008172  cmp     [rdi+rax*2], r14w
0x180008177  jz      short loc_180008180
0x180008179  call    cs:__imp_abort
0x180008180  mov     [rsp+98h+var_40], 1
0x180008188  mov     [rsp+98h+var_3C], ebx
0x18000818c  mov     [rsp+98h+var_30], rdi
0x180008191  lea     r8, [rsp+98h+var_40]
0x180008196  mov     [rsp+98h+var_48], r8
0x18000819b  mov     edx, 80040111h
0x1800081a0  mov     [rsp+98h+bstrString], r14
0x1800081a5  mov     [rsp+98h+var_70], 0AABBCCDDh
0x1800081ad  mov     [rsp+98h+var_6C], edx
0x1800081b1  mov     [rsp+98h+var_68], r14
0x1800081b6  lea     r9, [rsp+98h+var_60]
0x1800081bb  lea     rcx, [rsp+98h+bstrString]
0x1800081c0  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x1800081c5  lea     rdx, [rsp+98h+arg_10]
0x1800081cd  lea     rcx, [rsp+98h+bstrString]
0x1800081d2  call    ?to_abi@hresult_error@winrt@@QEBA?AUhresult@2@XZ; winrt::hresult_error::to_abi(void)
0x1800081d7  mov     ebx, [rax]
0x1800081d9  cmp     [rsp+98h+var_68], r14
0x1800081de  jz      short loc_1800081EA
0x1800081e0  lea     rcx, [rsp+98h+var_68]
0x1800081e5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800081ea  mov     rcx, [rsp+98h+bstrString]; bstrString
0x1800081ef  test    rcx, rcx
0x1800081f2  jz      short loc_1800081F9
0x1800081f4  call    WINRT_IMPL_SysFreeString
0x1800081f9  mov     eax, ebx
0x1800081fb  jmp     short loc_180008204
0x1800081fd  mov     eax, [rsp+98h+arg_10]
0x180008204  add     rsp, 78h
0x180008208  pop     r14
0x18000820a  pop     rdi
0x18000820b  pop     rsi
0x18000820c  pop     rbx
0x18000820d  retn
```
