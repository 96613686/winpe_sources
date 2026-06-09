# SetLayoutInit(HDC__ *,ulong)

- ea: `0x180090680`
- end: `0x1800906f7`
- name: `?SetLayoutInit@@YAKPEAUHDC__@@K@Z`
- size: `119`
- prototype: `unsigned int __fastcall(HDC, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180090680`
- `0x180092010`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x1800906a3`
- `KERNEL32!GetModuleHandleA` at `0x1800906a3`
- `KERNEL32!EnterCriticalSection` at `0x180090696`
- `KERNEL32!EnterCriticalSection` at `0x180090696`
- `KERNEL32!LeaveCriticalSection` at `0x1800906e4`
- `KERNEL32!LeaveCriticalSection` at `0x1800906e4`
- `KERNEL32!GetProcAddress` at `0x1800906b8`
- `KERNEL32!GetProcAddress` at `0x1800906b8`

## string_xrefs

- `0x18009069c`: `GDI32.DLL`

## pseudocode

```c
__int64 __fastcall SetLayoutInit(HDC a1, unsigned int a2)
{
  HMODULE ModuleHandleA; // rax
  unsigned int (*ProcAddress)(HDC, unsigned int); // rax
  unsigned int v6; // ebx

  EnterCriticalSection(&g_CriticalSection);
  ModuleHandleA = GetModuleHandleA("GDI32.DLL");
  if ( !ModuleHandleA
    || (ProcAddress = (unsigned int (*)(HDC, unsigned int))GetProcAddress(ModuleHandleA, "SetLayout")) == 0 )
  {
    ProcAddress = (unsigned int (*)(HDC, unsigned int))CDisplay::GetYScroll;
  }
  CW32System::_pfnSetLayout = ProcAddress;
  v6 = ((__int64 (__fastcall *)(HDC, _QWORD))ProcAddress)(a1, a2);
  LeaveCriticalSection(&g_CriticalSection);
  return v6;
}

```

## disassembly

```asm
0x180090680  mov     [rsp+arg_0], rbx
0x180090685  push    rdi
0x180090686  sub     rsp, 20h
0x18009068a  mov     rdi, rcx
0x18009068d  mov     ebx, edx
0x18009068f  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180090696  call    cs:__imp_EnterCriticalSection
0x18009069c  lea     rcx, aGdi32Dll_0; "GDI32.DLL"
0x1800906a3  call    cs:__imp_GetModuleHandleA
0x1800906a9  test    rax, rax
0x1800906ac  jz      short loc_1800906C3
0x1800906ae  lea     rdx, aSetlayout; "SetLayout"
0x1800906b5  mov     rcx, rax; hModule
0x1800906b8  call    cs:__imp_GetProcAddress
0x1800906be  test    rax, rax
0x1800906c1  jnz     short loc_1800906CA
0x1800906c3  lea     rax, ?GetYScroll@CDisplay@@UEBAJXZ; CDisplay::GetYScroll(void)
0x1800906ca  mov     edx, ebx
0x1800906cc  mov     cs:?_pfnSetLayout@CW32System@@2P6AKPEAUHDC__@@K@ZEA, rax; ulong (*CW32System::_pfnSetLayout)(HDC__ *,ulong)
0x1800906d3  mov     rcx, rdi
0x1800906d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800906db  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800906e2  mov     ebx, eax
0x1800906e4  call    cs:__imp_LeaveCriticalSection
0x1800906ea  mov     eax, ebx
0x1800906ec  mov     rbx, [rsp+28h+arg_0]
0x1800906f1  add     rsp, 20h
0x1800906f5  pop     rdi
0x1800906f6  retn
```
