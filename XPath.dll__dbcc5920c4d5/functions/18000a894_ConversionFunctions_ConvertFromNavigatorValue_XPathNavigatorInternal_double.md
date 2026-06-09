# ConversionFunctions::ConvertFromNavigatorValue(XPathNavigatorInternal &,double &)

- ea: `0x18000a894`
- end: `0x18000a8cb`
- name: `?ConvertFromNavigatorValue@ConversionFunctions@@SAJAEAVXPathNavigatorInternal@@AEAN@Z`
- size: `55`
- prototype: `__int64 __fastcall(struct XPathNavigatorInternal *, double *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800086b0`
- `0x18000c490`

## callees

- `0x18000a894`
- `0x18000e594`

## import_xrefs

- `msvcrt!_wtof` at `0x18000a8b9`
- `msvcrt!_wtof` at `0x18000a8b9`

## pseudocode

```c
__int64 __fastcall ConversionFunctions::ConvertFromNavigatorValue(struct XPathNavigatorInternal *a1, double *a2)
{
  __int64 result; // rax
  wchar_t *String; // [rsp+40h] [rbp+18h] BYREF

  String = 0;
  result = XPathNavigatorInternal::GetValue(a1, (const unsigned __int16 **)&String);
  if ( (int)result >= 0 )
  {
    *a2 = _wtof(String);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a894  push    rbx
0x18000a896  sub     rsp, 20h
0x18000a89a  mov     rbx, rdx
0x18000a89d  mov     [rsp+28h+String], 0
0x18000a8a6  lea     rdx, [rsp+28h+String]; unsigned __int16 **
0x18000a8ab  call    ?GetValue@XPathNavigatorInternal@@QEAAJPEAPEBG@Z; XPathNavigatorInternal::GetValue(ushort const * *)
0x18000a8b0  test    eax, eax
0x18000a8b2  js      short loc_18000A8C5
0x18000a8b4  mov     rcx, [rsp+28h+String]; String
0x18000a8b9  call    cs:__imp__wtof
0x18000a8bf  movsd   qword ptr [rbx], xmm0
0x18000a8c3  xor     eax, eax
0x18000a8c5  add     rsp, 20h
0x18000a8c9  pop     rbx
0x18000a8ca  retn
```
