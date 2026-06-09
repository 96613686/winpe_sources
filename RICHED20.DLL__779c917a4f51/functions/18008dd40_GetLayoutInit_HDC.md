# GetLayoutInit(HDC__ *)

- ea: `0x18008dd40`
- end: `0x18008ddaa`
- name: `?GetLayoutInit@@YAKPEAUHDC__@@@Z`
- size: `106`
- prototype: `unsigned int __fastcall(HDC)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18008dd40`
- `0x180092010`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x18008dd5d`
- `KERNEL32!GetModuleHandleA` at `0x18008dd5d`
- `KERNEL32!EnterCriticalSection` at `0x18008dd50`
- `KERNEL32!EnterCriticalSection` at `0x18008dd50`
- `KERNEL32!LeaveCriticalSection` at `0x18008dd9c`
- `KERNEL32!LeaveCriticalSection` at `0x18008dd9c`
- `KERNEL32!GetProcAddress` at `0x18008dd72`
- `KERNEL32!GetProcAddress` at `0x18008dd72`

## string_xrefs

- `0x18008dd56`: `GDI32.DLL`

## pseudocode

```c
__int64 __fastcall GetLayoutInit(HDC a1)
{
  HMODULE ModuleHandleA; // rax
  unsigned int (*ProcAddress)(HDC); // rax
  unsigned int v4; // ebx

  EnterCriticalSection(&g_CriticalSection);
  ModuleHandleA = GetModuleHandleA("GDI32.DLL");
  if ( !ModuleHandleA || (ProcAddress = (unsigned int (*)(HDC))GetProcAddress(ModuleHandleA, "GetLayout")) == 0 )
    ProcAddress = (unsigned int (*)(HDC))CDisplay::GetYScroll;
  CW32System::_pfnGetLayout = ProcAddress;
  v4 = ((__int64 (__fastcall *)(HDC))ProcAddress)(a1);
  LeaveCriticalSection(&g_CriticalSection);
  return v4;
}

```

## disassembly

```asm
0x18008dd40  push    rbx
0x18008dd42  sub     rsp, 20h
0x18008dd46  mov     rbx, rcx
0x18008dd49  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18008dd50  call    cs:__imp_EnterCriticalSection
0x18008dd56  lea     rcx, aGdi32Dll_0; "GDI32.DLL"
0x18008dd5d  call    cs:__imp_GetModuleHandleA
0x18008dd63  test    rax, rax
0x18008dd66  jz      short loc_18008DD7D
0x18008dd68  lea     rdx, aGetlayout; "GetLayout"
0x18008dd6f  mov     rcx, rax; hModule
0x18008dd72  call    cs:__imp_GetProcAddress
0x18008dd78  test    rax, rax
0x18008dd7b  jnz     short loc_18008DD84
0x18008dd7d  lea     rax, ?GetYScroll@CDisplay@@UEBAJXZ; CDisplay::GetYScroll(void)
0x18008dd84  mov     rcx, rbx
0x18008dd87  mov     cs:?_pfnGetLayout@CW32System@@2P6AKPEAUHDC__@@@ZEA, rax; ulong (*CW32System::_pfnGetLayout)(HDC__ *)
0x18008dd8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dd93  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18008dd9a  mov     ebx, eax
0x18008dd9c  call    cs:__imp_LeaveCriticalSection
0x18008dda2  mov     eax, ebx
0x18008dda4  add     rsp, 20h
0x18008dda8  pop     rbx
0x18008dda9  retn
```
