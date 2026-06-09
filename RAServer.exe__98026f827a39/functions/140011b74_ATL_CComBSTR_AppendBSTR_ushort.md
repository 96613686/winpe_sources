# ATL::CComBSTR::AppendBSTR(ushort *)

- ea: `0x140011b74`
- end: `0x140011bcf`
- name: `?AppendBSTR@CComBSTR@ATL@@QEAAJPEAG@Z`
- size: `91`
- prototype: `UINT __fastcall(BSTR *this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140011fc0`
- `0x140013250`
- `0x140013ef8`
- `0x140014ccc`

## callees

- `0x140011b74`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140011bb4`
- `OLEAUT32!__imp_SysFreeString` at `0x140011bb4`
- `OLEAUT32!__imp_SysStringLen` at `0x140011b87`
- `OLEAUT32!__imp_SysStringLen` at `0x140011b87`
- `OLEAUT32!__imp_VarBstrCat` at `0x140011ba5`
- `OLEAUT32!__imp_VarBstrCat` at `0x140011ba5`

## pseudocode

```c
UINT __fastcall ATL::CComBSTR::AppendBSTR(BSTR *this, unsigned __int16 *a2)
{
  UINT result; // eax
  OLECHAR *v5; // rcx
  HRESULT v6; // edi
  BSTR pbstrResult; // [rsp+40h] [rbp+18h] BYREF

  result = SysStringLen(a2);
  if ( result )
  {
    v5 = *this;
    pbstrResult = 0;
    v6 = VarBstrCat(v5, a2, &pbstrResult);
    if ( v6 >= 0 )
    {
      SysFreeString(*this);
      *this = pbstrResult;
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x140011b74  mov     [rsp+arg_0], rbx
0x140011b79  push    rdi
0x140011b7a  sub     rsp, 20h
0x140011b7e  mov     rbx, rcx
0x140011b81  mov     rdi, rdx
0x140011b84  mov     rcx, rdx; pbstr
0x140011b87  call    cs:__imp_SysStringLen
0x140011b8d  test    eax, eax
0x140011b8f  jz      short loc_140011BC4
0x140011b91  mov     rcx, [rbx]; bstrLeft
0x140011b94  lea     r8, [rsp+28h+pbstrResult]; pbstrResult
0x140011b99  mov     rdx, rdi; bstrRight
0x140011b9c  mov     [rsp+28h+pbstrResult], 0
0x140011ba5  call    cs:__imp_VarBstrCat
0x140011bab  mov     edi, eax
0x140011bad  test    eax, eax
0x140011baf  js      short loc_140011BC2
0x140011bb1  mov     rcx, [rbx]; bstrString
0x140011bb4  call    cs:__imp_SysFreeString
0x140011bba  mov     rcx, [rsp+28h+pbstrResult]
0x140011bbf  mov     [rbx], rcx
0x140011bc2  mov     eax, edi
0x140011bc4  mov     rbx, [rsp+28h+arg_0]
0x140011bc9  add     rsp, 20h
0x140011bcd  pop     rdi
0x140011bce  retn
```
