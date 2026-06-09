# SystemTimeToBstr(_SYSTEMTIME &)

- ea: `0x1800337e8`
- end: `0x1800338ae`
- name: `?SystemTimeToBstr@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_SYSTEMTIME@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180033474`
- `0x180033af0`

## callees

- `0x1800026b0`
- `0x180003230`
- `0x180022810`
- `0x1800337e8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180033862`
- `OLEAUT32!__imp_SysAllocString` at `0x180033862`

## string_xrefs

- `0x18003389c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BSTR *__fastcall SystemTimeToBstr(BSTR *a1, unsigned __int16 *a2)
{
  BSTR v3; // rax
  const char *v4; // r9
  int v6; // [rsp+20h] [rbp-268h]
  int v7; // [rsp+28h] [rbp-260h]
  int v8; // [rsp+30h] [rbp-258h]
  int v9; // [rsp+38h] [rbp-250h]
  int v10; // [rsp+40h] [rbp-248h]
  wchar_t Buffer[264]; // [rsp+60h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  v10 = a2[6];
  v9 = a2[5];
  v8 = a2[4];
  v7 = a2[3];
  v6 = a2[1];
  swprintf_s(Buffer, 0x104u, L"%04d-%02d-%02dT%02d:%02d:%02d", *a2, v6, v7, v8, v9, v10);
  v3 = SysAllocString(Buffer);
  *a1 = v3;
  if ( !v3 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v4);
  return a1;
}

```

## disassembly

```asm
0x1800337e8  push    rbx
0x1800337ea  sub     rsp, 280h
0x1800337f1  mov     rax, cs:__security_cookie
0x1800337f8  xor     rax, rsp
0x1800337fb  mov     [rsp+288h+var_18], rax
0x180033803  mov     r9, rdx
0x180033806  mov     rbx, rcx
0x180033809  mov     [rsp+288h+var_230], rcx
0x18003380e  mov     [rsp+288h+var_238], 0
0x180033816  movzx   eax, word ptr [rdx+0Ch]
0x18003381a  movzx   ecx, word ptr [rdx+0Ah]
0x18003381e  movzx   edx, word ptr [rdx+8]
0x180033822  movzx   r8d, word ptr [r9+6]
0x180033827  movzx   r10d, word ptr [r9+2]
0x18003382c  movzx   r9d, word ptr [r9]
0x180033830  mov     [rsp+288h+var_248], eax
0x180033834  mov     [rsp+288h+var_250], ecx
0x180033838  mov     [rsp+288h+var_258], edx
0x18003383c  mov     [rsp+288h+var_260], r8d
0x180033841  mov     [rsp+288h+var_268], r10d
0x180033846  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d"
0x18003384d  mov     edx, 104h; BufferCount
0x180033852  lea     rcx, [rsp+288h+Buffer]; Buffer
0x180033857  call    swprintf_s
0x18003385c  nop
0x18003385d  lea     rcx, [rsp+288h+Buffer]; psz
0x180033862  call    cs:__imp_SysAllocString
0x180033868  mov     [rbx], rax
0x18003386b  mov     [rsp+288h+var_238], 2
0x180033873  mov     rcx, [rsp+288h]; this
0x18003387b  test    rax, rax
0x18003387e  jz      short loc_18003389C
0x180033880  mov     rax, rbx
0x180033883  mov     rcx, [rsp+288h+var_18]
0x18003388b  xor     rcx, rsp; StackCookie
0x18003388e  call    __security_check_cookie
0x180033893  add     rsp, 280h
0x18003389a  pop     rbx
0x18003389b  retn
0x18003389c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800338a3  mov     edx, 15F3h; void *
0x1800338a8  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
