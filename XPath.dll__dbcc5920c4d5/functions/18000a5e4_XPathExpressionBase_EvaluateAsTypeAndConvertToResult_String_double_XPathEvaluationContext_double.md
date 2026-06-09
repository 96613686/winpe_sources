# XPathExpressionBase::EvaluateAsTypeAndConvertToResult<String,double>(XPathEvaluationContext *,double &)

- ea: `0x18000a5e4`
- end: `0x18000a638`
- name: `??$EvaluateAsTypeAndConvertToResult@VString@@N@XPathExpressionBase@@IEAAJPEAVXPathEvaluationContext@@AEAN@Z`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000aca0`
- `0x18000bde0`

## callees

- `0x18000a5e4`
- `0x18000a8d4`
- `0x180010fac`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathExpressionBase::EvaluateAsTypeAndConvertToResult<String,double>(
        __int64 *a1,
        __int64 a2,
        double *a3)
{
  __int64 v3; // rax
  int v5; // ebx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v3 = *a1;
  v7 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v3 + 64))(a1, a2, &v7);
  if ( v5 >= 0 )
  {
    *a3 = ConversionFunctions::ConvertToNumber((struct String *)&v7);
    v5 = 0;
  }
  String::Reset((String *)&v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a5e4  mov     [rsp+arg_8], rbx
0x18000a5e9  push    rdi
0x18000a5ea  sub     rsp, 20h
0x18000a5ee  mov     rax, [rcx]
0x18000a5f1  mov     rdi, r8
0x18000a5f4  lea     r8, [rsp+28h+arg_0]
0x18000a5f9  mov     [rsp+28h+arg_0], 0
0x18000a602  mov     rax, [rax+40h]
0x18000a606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a60b  mov     ebx, eax
0x18000a60d  test    eax, eax
0x18000a60f  js      short loc_18000A621
0x18000a611  lea     rcx, [rsp+28h+arg_0]; struct String *
0x18000a616  call    ?ConvertToNumber@ConversionFunctions@@SANAEAVString@@@Z; ConversionFunctions::ConvertToNumber(String &)
0x18000a61b  movsd   qword ptr [rdi], xmm0
0x18000a61f  xor     ebx, ebx
0x18000a621  lea     rcx, [rsp+28h+arg_0]; this
0x18000a626  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000a62b  mov     eax, ebx
0x18000a62d  mov     rbx, [rsp+28h+arg_8]
0x18000a632  add     rsp, 20h
0x18000a636  pop     rdi
0x18000a637  retn
```
