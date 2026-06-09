# COpenSearchRowset::CUrlInfo::Clear(void)

- ea: `0x180041da4`
- end: `0x180041e26`
- name: `?Clear@CUrlInfo@COpenSearchRowset@@QEAAXXZ`
- size: `130`
- prototype: `void __fastcall(COpenSearchRowset::CUrlInfo *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043830`
- `0x180043b28`
- `0x180043dd4`
- `0x1800463e0`
- `0x180047a8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041de2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041dec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041df6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041de2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041dec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041df6`
- `OLEAUT32!__imp_SysFreeString` at `0x180041db0`
- `OLEAUT32!__imp_SysFreeString` at `0x180041dba`
- `OLEAUT32!__imp_SysFreeString` at `0x180041dc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180041dce`
- `OLEAUT32!__imp_SysFreeString` at `0x180041dd8`
- `OLEAUT32!__imp_SysFreeString` at `0x180041db0`
- `OLEAUT32!__imp_SysFreeString` at `0x180041dba`
- `OLEAUT32!__imp_SysFreeString` at `0x180041dc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180041dce`
- `OLEAUT32!__imp_SysFreeString` at `0x180041dd8`

## pseudocode

```c
void __fastcall COpenSearchRowset::CUrlInfo::Clear(COpenSearchRowset::CUrlInfo *this)
{
  SysFreeString(*(BSTR *)this);
  SysFreeString(*((BSTR *)this + 1));
  SysFreeString(*((BSTR *)this + 2));
  SysFreeString(*((BSTR *)this + 3));
  SysFreeString(*((BSTR *)this + 4));
  CoTaskMemFree(*((LPVOID *)this + 5));
  CoTaskMemFree(*((LPVOID *)this + 6));
  CoTaskMemFree(*((LPVOID *)this + 7));
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
}

```

## disassembly

```asm
0x180041da4  push    rbx
0x180041da6  sub     rsp, 20h
0x180041daa  mov     rbx, rcx
0x180041dad  mov     rcx, [rcx]; bstrString
0x180041db0  call    cs:__imp_SysFreeString
0x180041db6  mov     rcx, [rbx+8]; bstrString
0x180041dba  call    cs:__imp_SysFreeString
0x180041dc0  mov     rcx, [rbx+10h]; bstrString
0x180041dc4  call    cs:__imp_SysFreeString
0x180041dca  mov     rcx, [rbx+18h]; bstrString
0x180041dce  call    cs:__imp_SysFreeString
0x180041dd4  mov     rcx, [rbx+20h]; bstrString
0x180041dd8  call    cs:__imp_SysFreeString
0x180041dde  mov     rcx, [rbx+28h]; pv
0x180041de2  call    cs:__imp_CoTaskMemFree
0x180041de8  mov     rcx, [rbx+30h]; pv
0x180041dec  call    cs:__imp_CoTaskMemFree
0x180041df2  mov     rcx, [rbx+38h]; pv
0x180041df6  call    cs:__imp_CoTaskMemFree
0x180041dfc  xor     eax, eax
0x180041dfe  mov     [rbx], rax
0x180041e01  mov     [rbx+8], rax
0x180041e05  mov     [rbx+10h], rax
0x180041e09  mov     [rbx+18h], rax
0x180041e0d  mov     [rbx+20h], rax
0x180041e11  mov     [rbx+28h], rax
0x180041e15  mov     [rbx+30h], rax
0x180041e19  mov     [rbx+38h], rax
0x180041e1d  mov     [rbx+40h], eax
0x180041e20  add     rsp, 20h
0x180041e24  pop     rbx
0x180041e25  retn
```
