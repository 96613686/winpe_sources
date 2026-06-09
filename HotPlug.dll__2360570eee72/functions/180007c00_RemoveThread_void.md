# RemoveThread(void *)

- ea: `0x180007c00`
- end: `0x180007c1a`
- name: `?RemoveThread@@YAKPEAX@Z`
- size: `26`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000712c`
- `0x180007c00`

## pseudocode

```c
__int64 __fastcall RemoveThread(PVOID Parameter)
{
  __int64 v1; // rdx

  v1 = *((_QWORD *)Parameter + 6);
  if ( v1 )
    return HotPlugEjectDeviceBase(*((HWND *)Parameter + 3), *(WCHAR **)(v1 + 32));
  else
    return 19;
}

```

## disassembly

```asm
0x180007c00  mov     rdx, [rcx+30h]
0x180007c04  test    rdx, rdx
0x180007c07  jnz     short loc_180007C0D
0x180007c09  lea     eax, [rdx+13h]
0x180007c0c  retn
0x180007c0d  mov     rdx, [rdx+20h]; unsigned __int16 *
0x180007c11  mov     rcx, [rcx+18h]; hWnd
0x180007c15  jmp     ?HotPlugEjectDeviceBase@@YAKPEAUHWND__@@PEBGK@Z; HotPlugEjectDeviceBase(HWND__ *,ushort const *,ulong)
```
