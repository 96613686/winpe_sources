# SetAccessibilityKeyboardShortcut

- ea: `0x18000cb30`
- end: `0x18000cb53`
- name: `SetAccessibilityKeyboardShortcut`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009f88`

## pseudocode

```c
__int64 __fastcall SetAccessibilityKeyboardShortcut(HWND a1, const unsigned __int16 *a2)
{
  struct _GUID v3; // [rsp+20h] [rbp-18h] BYREF

  v3 = PROPID_ACC_KEYBOARDSHORTCUT;
  return SetAccessibilityProperty(a1, &v3, a2);
}

```

## disassembly

```asm
0x18000cb30  sub     rsp, 38h
0x18000cb34  movups  xmm0, xmmword ptr cs:PROPID_ACC_KEYBOARDSHORTCUT.Data1
0x18000cb3b  mov     r8, rdx; unsigned __int16 *
0x18000cb3e  lea     rdx, [rsp+38h+var_18]; struct _GUID
0x18000cb43  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x18000cb49  call    ?SetAccessibilityProperty@@YAJPEAUHWND__@@U_GUID@@PEBG@Z; SetAccessibilityProperty(HWND__ *,_GUID,ushort const *)
0x18000cb4e  add     rsp, 38h
0x18000cb52  retn
```
