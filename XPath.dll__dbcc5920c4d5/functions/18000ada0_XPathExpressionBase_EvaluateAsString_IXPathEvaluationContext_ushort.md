# XPathExpressionBase::EvaluateAsString(IXPathEvaluationContext *,ushort * *)

- ea: `0x18000ada0`
- end: `0x18000ae35`
- name: `?EvaluateAsString@XPathExpressionBase@@UEAAJPEAUIXPathEvaluationContext@@PEAPEAG@Z`
- size: `149`
- prototype: `__int64 __fastcall(XPathExpressionBase *__hidden this, struct IXPathEvaluationContext *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000ada0`
- `0x180010f98`
- `0x180010fac`
- `0x180012010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000adf6`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000adf6`

## pseudocode

```c
__int64 __fastcall XPathExpressionBase::EvaluateAsString(
        XPathExpressionBase *this,
        struct IXPathEvaluationContext *a2,
        unsigned __int16 **a3)
{
  __int64 v4; // rax
  int v5; // ebx
  UINT CCH; // eax
  OLECHAR *v7; // rcx
  unsigned __int16 *v8; // rax
  OLECHAR *strIn; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  v4 = *(_QWORD *)this;
  strIn = 0;
  v5 = (*(__int64 (__fastcall **)(XPathExpressionBase *, struct IXPathEvaluationContext *, OLECHAR **))(v4 + 64))(
         this,
         a2,
         &strIn);
  if ( v5 < 0 )
  {
LABEL_8:
    String::Reset((String *)&strIn);
    return (unsigned int)v5;
  }
  CCH = String::QueryCCH((String *)&strIn);
  v7 = (OLECHAR *)&qword_180016F98;
  if ( strIn )
    v7 = strIn;
  v8 = SysAllocStringLen(v7, CCH);
  *a3 = v8;
  if ( !v8 )
  {
    v5 = -2147024882;
    goto LABEL_8;
  }
  String::Reset((String *)&strIn);
  return 0;
}

```

## disassembly

```asm
0x18000ada0  mov     [rsp+arg_0], rbx
0x18000ada5  push    rdi
0x18000ada6  sub     rsp, 20h
0x18000adaa  mov     rdi, r8
0x18000adad  test    rdx, rdx
0x18000adb0  jz      short loc_18000AE25
0x18000adb2  test    r8, r8
0x18000adb5  jz      short loc_18000AE25
0x18000adb7  mov     rax, [rcx]
0x18000adba  lea     r8, [rsp+28h+strIn]
0x18000adbf  mov     [rsp+28h+strIn], 0
0x18000adc8  mov     rax, [rax+40h]
0x18000adcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000add1  mov     ebx, eax
0x18000add3  test    eax, eax
0x18000add5  js      short loc_18000AE09
0x18000add7  lea     rcx, [rsp+28h+strIn]; this
0x18000addc  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x18000ade1  mov     rdx, [rsp+28h+strIn]
0x18000ade6  lea     rcx, qword_180016F98
0x18000aded  test    rdx, rdx
0x18000adf0  cmovnz  rcx, rdx; strIn
0x18000adf4  mov     edx, eax; ui
0x18000adf6  call    cs:__imp_SysAllocStringLen
0x18000adfc  mov     [rdi], rax
0x18000adff  test    rax, rax
0x18000ae02  jnz     short loc_18000AE17
0x18000ae04  mov     ebx, 8007000Eh
0x18000ae09  lea     rcx, [rsp+28h+strIn]; this
0x18000ae0e  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000ae13  mov     eax, ebx
0x18000ae15  jmp     short loc_18000AE2A
0x18000ae17  lea     rcx, [rsp+28h+strIn]; this
0x18000ae1c  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000ae21  xor     eax, eax
0x18000ae23  jmp     short loc_18000AE2A
0x18000ae25  mov     eax, 80070057h
0x18000ae2a  mov     rbx, [rsp+28h+arg_0]
0x18000ae2f  add     rsp, 20h
0x18000ae33  pop     rdi
0x18000ae34  retn
```
