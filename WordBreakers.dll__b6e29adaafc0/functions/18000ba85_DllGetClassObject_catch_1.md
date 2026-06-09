# DllGetClassObject$catch$1

- ea: `0x18000ba85`
- end: `0x18000bace`
- name: `DllGetClassObject$catch$1`
- size: `73`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002e3c`
- `0x18000ba85`

## string_xrefs

- `0x18000bab0`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall DllGetClassObject_catch_1(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 96) = -2147024882;
  if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    McTemplateU0sqq_EventWriteTransfer(a1, a2, (unsigned int)"DllGetClassObject", 52, 14);
  return 0;
}

```

## disassembly

```asm
0x18000ba85  mov     [rsp+arg_8], rdx
0x18000ba8a  push    rbp
0x18000ba8b  sub     rsp, 30h
0x18000ba8f  mov     rbp, rdx
0x18000ba92  mov     dword ptr [rbp+60h], 8007000Eh
0x18000ba99  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18000baa0  jz      short loc_18000BABD
0x18000baa2  mov     [rsp+38h+var_18], 8007000Eh
0x18000baaa  mov     r9d, 34h ; '4'
0x18000bab0  lea     r8, aDllgetclassobj_0; "DllGetClassObject"
0x18000bab7  call    McTemplateU0sqq_EventWriteTransfer
0x18000babc  nop
0x18000babd  mov     rax, 0
0x18000bac7  add     rsp, 30h
0x18000bacb  pop     rbp
0x18000bacc  retn
```
