# ?__abi_GetRuntimeClassName@?QObject@Platform@@?$WriteOnlyArray@PE$AAVString@Platform@@$00@2@UE$AAAJPEAPEAUHSTRING__@@@Z

- ea: `0x14002dc90`
- end: `0x14002dca4`
- name: `?__abi_GetRuntimeClassName@?QObject@Platform@@?$WriteOnlyArray@PE$AAVString@Platform@@$00@2@UE$AAAJPEAPEAUHSTRING__@@@Z`
- size: `20`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14002dcb0`
- `0x14002dcc0`
- `0x14002dcd0`

## callees

- `0x140002850`

## string_xrefs

- `0x14002dc93`: `Platform.?$WriteOnlyArray@PE$AAVString@Platform@@$00`

## pseudocode

```c
HRESULT __fastcall ___abi_GetRuntimeClassName__QObject_Platform____WriteOnlyArray_PE_AAVString_Platform___00_2_UE_AAAJPEAPEAUHSTRING_____Z(
        __int64 a1,
        HSTRING *a2)
{
  return __winRT::__windowsCreateString(L"Platform.?$WriteOnlyArray@PE$AAVString@Platform@@$00", 0x34u, a2);
}

```

## disassembly

```asm
0x14002dc90  mov     r8, rdx; string
0x14002dc93  lea     rcx, aPlatformWriteo_0; "Platform.?$WriteOnlyArray@PE$AAVString@"...
0x14002dc9a  mov     edx, 34h ; '4'; length
0x14002dc9f  jmp     ?__windowsCreateString@__winRT@@YAJPEB_WHPEAPEAUHSTRING__@@@Z; __winRT::__windowsCreateString(wchar_t const *,int,HSTRING__ * *)
```
