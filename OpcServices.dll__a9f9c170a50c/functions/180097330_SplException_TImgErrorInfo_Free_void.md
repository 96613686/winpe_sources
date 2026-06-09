# SplException::TImgErrorInfo::Free(void)

- ea: `0x180097330`
- end: `0x1800973be`
- name: `?Free@TImgErrorInfo@SplException@@QEAAXXZ`
- size: `142`
- prototype: `void __fastcall(SplException::TImgErrorInfo *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800972bc`
- `0x1800acd84`
- `0x1800b7d08`
- `0x1800da814`
- `0x18010a408`
- `0x18010a524`

## callees

- `0x180097330`
- `0x1800d5fe4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097389`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097389`
- `OLEAUT32!__imp_SysFreeString` at `0x180097345`
- `OLEAUT32!__imp_SysFreeString` at `0x18009734f`
- `OLEAUT32!__imp_SysFreeString` at `0x180097359`
- `OLEAUT32!__imp_SysFreeString` at `0x180097363`
- `OLEAUT32!__imp_SysFreeString` at `0x180097378`
- `OLEAUT32!__imp_SysFreeString` at `0x180097393`
- `OLEAUT32!__imp_SysFreeString` at `0x180097345`
- `OLEAUT32!__imp_SysFreeString` at `0x18009734f`
- `OLEAUT32!__imp_SysFreeString` at `0x180097359`
- `OLEAUT32!__imp_SysFreeString` at `0x180097363`
- `OLEAUT32!__imp_SysFreeString` at `0x180097378`
- `OLEAUT32!__imp_SysFreeString` at `0x180097393`

## pseudocode

```c
void __fastcall SplException::TImgErrorInfo::Free(SplException::TImgErrorInfo *this)
{
  __int64 i; // rsi

  SysFreeString(*(BSTR *)this);
  SysFreeString(*((BSTR *)this + 4));
  SysFreeString(*((BSTR *)this + 5));
  SysFreeString(*((BSTR *)this + 6));
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 18); i = (unsigned int)(i + 1) )
    SysFreeString(*(BSTR *)(*((_QWORD *)this + 10) + 8 * i));
  CoTaskMemFree(*((LPVOID *)this + 10));
  SysFreeString(*((BSTR *)this + 11));
  memset_0(this, 0, 0x68u);
  *((_DWORD *)this + 24) = -1;
}

```

## disassembly

```asm
0x180097330  mov     [rsp+arg_0], rbx
0x180097335  mov     [rsp+arg_8], rsi
0x18009733a  push    rdi
0x18009733b  sub     rsp, 20h
0x18009733f  mov     rbx, rcx
0x180097342  mov     rcx, [rcx]; bstrString
0x180097345  call    cs:__imp_SysFreeString
0x18009734b  mov     rcx, [rbx+20h]; bstrString
0x18009734f  call    cs:__imp_SysFreeString
0x180097355  mov     rcx, [rbx+28h]; bstrString
0x180097359  call    cs:__imp_SysFreeString
0x18009735f  mov     rcx, [rbx+30h]; bstrString
0x180097363  call    cs:__imp_SysFreeString
0x180097369  xor     esi, esi
0x18009736b  cmp     [rbx+48h], esi
0x18009736e  jbe     short loc_180097385
0x180097370  mov     rcx, [rbx+50h]
0x180097374  mov     rcx, [rcx+rsi*8]; bstrString
0x180097378  call    cs:__imp_SysFreeString
0x18009737e  inc     esi
0x180097380  cmp     esi, [rbx+48h]
0x180097383  jb      short loc_180097370
0x180097385  mov     rcx, [rbx+50h]; pv
0x180097389  call    cs:__imp_CoTaskMemFree
0x18009738f  mov     rcx, [rbx+58h]; bstrString
0x180097393  call    cs:__imp_SysFreeString
0x180097399  xor     edx, edx; Val
0x18009739b  mov     rcx, rbx; void *
0x18009739e  lea     r8d, [rdx+68h]; Size
0x1800973a2  call    memset_0
0x1800973a7  mov     rsi, [rsp+28h+arg_8]
0x1800973ac  mov     dword ptr [rbx+60h], 0FFFFFFFFh
0x1800973b3  mov     rbx, [rsp+28h+arg_0]
0x1800973b8  add     rsp, 20h
0x1800973bc  pop     rdi
0x1800973bd  retn
```
