# UpdateHtmlDocWithBSTR

- ea: `0x180009318`
- end: `0x18000947a`
- name: `UpdateHtmlDocWithBSTR`
- size: `354`
- prototype: `__int64 __fastcall(__int64, __int64 *, BSTR *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800078b0`
- `0x180009004`

## callees

- `0x180008ce8`
- `0x180009318`
- `0x18000b010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180009461`
- `OLEAUT32!__imp_SysFreeString` at `0x180009461`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180009457`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180009457`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000937d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180009430`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000937d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180009430`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800093a1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000944e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800093a1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000944e`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000935e`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000935e`

## pseudocode

```c
__int64 __fastcall UpdateHtmlDocWithBSTR(__int64 a1, __int64 *a2, BSTR *a3)
{
  HRESULT InnerTextFromBody; // ebx
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v8; // rdi
  __int64 v9; // rax
  __int64 *v11; // [rsp+20h] [rbp-10h] BYREF
  void *ppvData; // [rsp+68h] [rbp+38h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+48h] BYREF

  ppvData = 0;
  bstrString = 0;
  if ( !a2 )
  {
    InnerTextFromBody = -2147024809;
    goto LABEL_15;
  }
  Vector = SafeArrayCreateVector(0xCu, 0, 1u);
  v8 = Vector;
  if ( !Vector )
  {
    InnerTextFromBody = -2147024882;
    goto LABEL_15;
  }
  InnerTextFromBody = SafeArrayAccessData(Vector, &ppvData);
  if ( InnerTextFromBody < 0 )
  {
LABEL_14:
    SafeArrayDestroy(v8);
    goto LABEL_15;
  }
  *(_WORD *)ppvData = 8;
  *((_QWORD *)ppvData + 1) = a1;
  InnerTextFromBody = SafeArrayUnaccessData(v8);
  if ( InnerTextFromBody >= 0 )
  {
    InnerTextFromBody = (*(__int64 (__fastcall **)(__int64 *, SAFEARRAY *))(*a2 + 472))(a2, v8);
    if ( InnerTextFromBody >= 0 )
    {
      InnerTextFromBody = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 496))(a2);
      if ( InnerTextFromBody >= 0 )
      {
        if ( a3 )
        {
          v9 = *a2;
          v11 = a2;
          (*(void (__fastcall **)(__int64 *))(v9 + 8))(a2);
          InnerTextFromBody = GetInnerTextFromBody(&v11, &bstrString);
          (*(void (__fastcall **)(__int64 *))(*a2 + 16))(a2);
          if ( InnerTextFromBody >= 0 )
          {
            *a3 = bstrString;
            bstrString = 0;
          }
        }
      }
    }
  }
  if ( SafeArrayAccessData(v8, &ppvData) >= 0 )
  {
    *(_WORD *)ppvData = 0;
    *((_QWORD *)ppvData + 1) = 0;
    SafeArrayUnaccessData(v8);
    goto LABEL_14;
  }
LABEL_15:
  SysFreeString(bstrString);
  return (unsigned int)InnerTextFromBody;
}

```

## disassembly

```asm
0x180009318  mov     [rsp-28h+arg_0], rbx
0x18000931d  push    rbp
0x18000931e  push    rsi
0x18000931f  push    rdi
0x180009320  push    r14
0x180009322  push    r15
0x180009324  mov     rbp, rsp
0x180009327  sub     rsp, 30h
0x18000932b  mov     [rbp+ppvData], 0
0x180009333  mov     r14, r8
0x180009336  mov     [rbp+bstrString], 0
0x18000933e  mov     rsi, rdx
0x180009341  mov     r15, rcx
0x180009344  test    rdx, rdx
0x180009347  jnz     short loc_180009353
0x180009349  mov     ebx, 80070057h
0x18000934e  jmp     loc_18000945D
0x180009353  mov     ecx, 0Ch; vt
0x180009358  xor     edx, edx; lLbound
0x18000935a  lea     r8d, [rcx-0Bh]; cElements
0x18000935e  call    cs:__imp_SafeArrayCreateVector
0x180009364  mov     rdi, rax
0x180009367  test    rax, rax
0x18000936a  jnz     short loc_180009376
0x18000936c  mov     ebx, 8007000Eh
0x180009371  jmp     loc_18000945D
0x180009376  lea     rdx, [rbp+ppvData]; ppvData
0x18000937a  mov     rcx, rdi; psa
0x18000937d  call    cs:__imp_SafeArrayAccessData
0x180009383  mov     ebx, eax
0x180009385  test    eax, eax
0x180009387  js      loc_180009454
0x18000938d  mov     rax, [rbp+ppvData]
0x180009391  mov     rcx, rdi; psa
0x180009394  mov     word ptr [rax], 8
0x180009399  mov     rax, [rbp+ppvData]
0x18000939d  mov     [rax+8], r15
0x1800093a1  call    cs:__imp_SafeArrayUnaccessData
0x1800093a7  mov     ebx, eax
0x1800093a9  test    eax, eax
0x1800093ab  js      short loc_180009429
0x1800093ad  mov     rax, [rsi]
0x1800093b0  mov     rdx, rdi
0x1800093b3  mov     rcx, rsi
0x1800093b6  mov     rax, [rax+1D8h]
0x1800093bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093c2  mov     ebx, eax
0x1800093c4  test    eax, eax
0x1800093c6  js      short loc_180009429
0x1800093c8  mov     rax, [rsi]
0x1800093cb  mov     rcx, rsi
0x1800093ce  mov     rax, [rax+1F0h]
0x1800093d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093da  mov     ebx, eax
0x1800093dc  test    eax, eax
0x1800093de  js      short loc_180009429
0x1800093e0  test    r14, r14
0x1800093e3  jz      short loc_180009429
0x1800093e5  mov     rax, [rsi]
0x1800093e8  mov     rcx, rsi
0x1800093eb  mov     [rbp+var_10], rsi
0x1800093ef  mov     rax, [rax+8]
0x1800093f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093f8  lea     rdx, [rbp+bstrString]
0x1800093fc  lea     rcx, [rbp+var_10]
0x180009400  call    GetInnerTextFromBody
0x180009405  mov     ebx, eax
0x180009407  mov     rcx, rsi
0x18000940a  mov     rax, [rsi]
0x18000940d  mov     rax, [rax+10h]
0x180009411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009416  test    ebx, ebx
0x180009418  js      short loc_180009429
0x18000941a  mov     rax, [rbp+bstrString]
0x18000941e  mov     [r14], rax
0x180009421  mov     [rbp+bstrString], 0
0x180009429  lea     rdx, [rbp+ppvData]; ppvData
0x18000942d  mov     rcx, rdi; psa
0x180009430  call    cs:__imp_SafeArrayAccessData
0x180009436  test    eax, eax
0x180009438  js      short loc_18000945D
0x18000943a  mov     rax, [rbp+ppvData]
0x18000943e  xor     ecx, ecx
0x180009440  mov     [rax], cx
0x180009443  mov     rax, [rbp+ppvData]
0x180009447  mov     [rax+8], rcx
0x18000944b  mov     rcx, rdi; psa
0x18000944e  call    cs:__imp_SafeArrayUnaccessData
0x180009454  mov     rcx, rdi; psa
0x180009457  call    cs:__imp_SafeArrayDestroy
0x18000945d  mov     rcx, [rbp+bstrString]; bstrString
0x180009461  call    cs:__imp_SysFreeString
0x180009467  mov     eax, ebx
0x180009469  mov     rbx, [rsp+30h+arg_0]
0x18000946e  add     rsp, 30h
0x180009472  pop     r15
0x180009474  pop     r14
0x180009476  pop     rdi
0x180009477  pop     rsi
0x180009478  pop     rbp
0x180009479  retn
```
