# HotPlugEjectDeviceStub(void *)

- ea: `0x180007520`
- end: `0x18000754f`
- name: `?HotPlugEjectDeviceStub@@YAKPEAX@Z`
- size: `47`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000712c`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x180007548`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180007548`
- `KERNEL32!LocalFree` at `0x180007536`
- `KERNEL32!LocalFree` at `0x180007536`

## pseudocode

```c
void __fastcall __noreturn HotPlugEjectDeviceStub(WCHAR *Parameter)
{
  HotPlugEjectDeviceBase(0, Parameter);
  LocalFree(Parameter);
  FreeLibraryAndExitThread(hHotPlug, 1u);
}

```

## disassembly

```asm
0x180007520  push    rbx
0x180007522  sub     rsp, 20h
0x180007526  mov     rbx, rcx
0x180007529  mov     rdx, rcx; unsigned __int16 *
0x18000752c  xor     ecx, ecx; hWnd
0x18000752e  call    ?HotPlugEjectDeviceBase@@YAKPEAUHWND__@@PEBGK@Z; HotPlugEjectDeviceBase(HWND__ *,ushort const *,ulong)
0x180007533  mov     rcx, rbx; hMem
0x180007536  call    cs:__imp_LocalFree
0x18000753c  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hLibModule
0x180007543  mov     edx, 1; dwExitCode
0x180007548  call    cs:__imp_FreeLibraryAndExitThread
```
