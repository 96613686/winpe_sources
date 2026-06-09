# NumberExpressionBase::Evaluate(XPathEvaluationContext *,String &)

- ea: `0x18000ab90`
- end: `0x18000ac2d`
- name: `?Evaluate@NumberExpressionBase@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z`
- size: `157`
- prototype: `int(NumberExpressionBase *__hidden this, struct XPathEvaluationContext *, struct String *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000a8f4`
- `0x18000ab90`
- `0x180010ee0`
- `0x180012010`

## import_xrefs

- `msvcrt!_fpclass` at `0x18000abc5`
- `msvcrt!_fpclass` at `0x18000abc5`

## pseudocode

```c
__int64 __fastcall NumberExpressionBase::Evaluate(
        NumberExpressionBase *this,
        struct XPathEvaluationContext *a2,
        struct String *a3)
{
  __int64 v3; // rax
  __int64 result; // rax
  double v6; // xmm6_8
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  const unsigned __int16 *v12; // rdx
  double X; // [rsp+40h] [rbp+8h] BYREF

  v3 = *(_QWORD *)this;
  X = 0.0;
  result = (*(__int64 (__fastcall **)(NumberExpressionBase *, struct XPathEvaluationContext *, double *))(v3 + 72))(
             this,
             a2,
             &X);
  if ( (int)result >= 0 )
  {
    v6 = X;
    v7 = _fpclass(X) - 1;
    if ( v7 && (v8 = v7 - 1) != 0 )
    {
      v9 = v8 - 2;
      if ( v9 )
      {
        v10 = v9 - 28;
        if ( v10 && (v11 = v10 - 32) != 0 )
        {
          if ( v11 != 448 )
            return ConversionFunctions::ConvertXPathNumberToXPathString(v6, a3);
          v12 = L"Infinity";
        }
        else
        {
          v12 = L"0";
        }
      }
      else
      {
        v12 = L"-Infinity";
      }
    }
    else
    {
      v12 = L"NaN";
    }
    return String::Initialize(a3, v12);
  }
  return result;
}

```

## disassembly

```asm
0x18000ab90  push    rbx
0x18000ab92  sub     rsp, 30h
0x18000ab96  mov     rax, [rcx]
0x18000ab99  mov     rbx, r8
0x18000ab9c  xorps   xmm0, xmm0
0x18000ab9f  movaps  [rsp+38h+var_18], xmm6
0x18000aba4  lea     r8, [rsp+38h+X]
0x18000aba9  movsd   [rsp+38h+X], xmm0
0x18000abaf  mov     rax, [rax+48h]
0x18000abb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abb8  test    eax, eax
0x18000abba  js      short loc_18000AC22
0x18000abbc  movsd   xmm6, [rsp+38h+X]
0x18000abc2  movaps  xmm0, xmm6; X
0x18000abc5  call    cs:__imp__fpclass
0x18000abcb  sub     eax, 1
0x18000abce  jz      short loc_18000AC13
0x18000abd0  sub     eax, 1
0x18000abd3  jz      short loc_18000AC13
0x18000abd5  sub     eax, 2
0x18000abd8  jz      short loc_18000AC0A
0x18000abda  sub     eax, 1Ch
0x18000abdd  jz      short loc_18000AC01
0x18000abdf  sub     eax, 20h ; ' '
0x18000abe2  jz      short loc_18000AC01
0x18000abe4  cmp     eax, 1C0h
0x18000abe9  jz      short loc_18000ABF8
0x18000abeb  mov     rdx, rbx; struct String *
0x18000abee  movaps  xmm0, xmm6; double
0x18000abf1  call    ?ConvertXPathNumberToXPathString@ConversionFunctions@@CAJNAEAVString@@@Z; ConversionFunctions::ConvertXPathNumberToXPathString(double,String &)
0x18000abf6  jmp     short loc_18000AC22
0x18000abf8  lea     rdx, aInfinity; "Infinity"
0x18000abff  jmp     short loc_18000AC1A
0x18000ac01  lea     rdx, a0; "0"
0x18000ac08  jmp     short loc_18000AC1A
0x18000ac0a  lea     rdx, aInfinity_0; "-Infinity"
0x18000ac11  jmp     short loc_18000AC1A
0x18000ac13  lea     rdx, aNan; "NaN"
0x18000ac1a  mov     rcx, rbx; this
0x18000ac1d  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000ac22  movaps  xmm6, [rsp+38h+var_18]
0x18000ac27  add     rsp, 30h
0x18000ac2b  pop     rbx
0x18000ac2c  retn
```
