# SetAccessibilityName

- ea: `0x18000cb60`
- end: `0x18000cb83`
- name: `SetAccessibilityName`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009f88`

## pseudocode

```c
__int64 __fastcall SetAccessibilityName(HWND a1, const unsigned __int16 *a2)
{
  struct _GUID v3; // [rsp+20h] [rbp-18h] BYREF

  v3 = PROPID_ACC_NAME;
  return SetAccessibilityProperty(a1, &v3, a2);
}

```

## disassembly

```asm
0x18000cb60  sub     rsp, 38h
0x18000cb64  movups  xmm0, xmmword ptr cs:PROPID_ACC_NAME.Data1
0x18000cb6b  mov     r8, rdx; unsigned __int16 *
0x18000cb6e  lea     rdx, [rsp+38h+var_18]; struct _GUID
0x18000cb73  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x18000cb79  call    ?SetAccessibilityProperty@@YAJPEAUHWND__@@U_GUID@@PEBG@Z; SetAccessibilityProperty(HWND__ *,_GUID,ushort const *)
0x18000cb7e  add     rsp, 38h
0x18000cb82  retn
```
