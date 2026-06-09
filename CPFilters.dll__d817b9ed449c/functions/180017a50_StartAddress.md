# StartAddress

- ea: `0x180017a50`
- end: `0x180017ad3`
- name: `StartAddress`
- size: `131`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***Parameter)(_QWORD))`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180017a50`
- `0x18006ccc0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180017a69`
- `KERNEL32!GetModuleHandleW` at `0x180017a69`
- `KERNEL32!GetProcAddress` at `0x180017a84`
- `KERNEL32!GetProcAddress` at `0x180017a84`
- `ole32!CoUninitialize` at `0x180017ab9`
- `ole32!CoUninitialize` at `0x180017ab9`

## string_xrefs

- `0x180017a62`: `ole32.dll`

## pseudocode

```c
__int64 __fastcall StartAddress(__int64 (__fastcall ***Parameter)(_QWORD))
{
  int v2; // edi
  HMODULE ModuleHandleW; // rax
  HRESULT (__stdcall *CoInitializeEx)(LPVOID, DWORD); // rax
  unsigned int v5; // ebx

  v2 = -2147467259;
  ModuleHandleW = GetModuleHandleW(L"ole32.dll");
  if ( ModuleHandleW )
  {
    CoInitializeEx = (HRESULT (__stdcall *)(LPVOID, DWORD))GetProcAddress(ModuleHandleW, "CoInitializeEx");
    if ( CoInitializeEx )
      v2 = ((__int64 (__fastcall *)(_QWORD, __int64))CoInitializeEx)(0, 4);
  }
  v5 = (**Parameter)(Parameter);
  if ( v2 >= 0 )
    CoUninitialize();
  return v5;
}

```

## disassembly

```asm
0x180017a50  mov     [rsp+arg_0], rbx
0x180017a55  push    rdi
0x180017a56  sub     rsp, 20h
0x180017a5a  mov     rbx, rcx
0x180017a5d  mov     edi, 80004005h
0x180017a62  lea     rcx, aOle32Dll_0; "ole32.dll"
0x180017a69  call    cs:GetModuleHandleW
0x180017a70  nop     dword ptr [rax+rax+00h]
0x180017a75  test    rax, rax
0x180017a78  jz      short loc_180017AA4
0x180017a7a  lea     rdx, aCoinitializeex; "CoInitializeEx"
0x180017a81  mov     rcx, rax; hModule
0x180017a84  call    cs:GetProcAddress
0x180017a8b  nop     dword ptr [rax+rax+00h]
0x180017a90  test    rax, rax
0x180017a93  jz      short loc_180017AA4
0x180017a95  mov     edx, 4
0x180017a9a  xor     ecx, ecx
0x180017a9c  call    cs:__guard_dispatch_icall_fptr
0x180017aa2  mov     edi, eax
0x180017aa4  mov     rcx, [rbx]
0x180017aa7  mov     rax, [rcx]
0x180017aaa  mov     rcx, rbx
0x180017aad  call    cs:__guard_dispatch_icall_fptr
0x180017ab3  mov     ebx, eax
0x180017ab5  test    edi, edi
0x180017ab7  js      short loc_180017AC5
0x180017ab9  call    cs:CoUninitialize
0x180017ac0  nop     dword ptr [rax+rax+00h]
0x180017ac5  mov     eax, ebx
0x180017ac7  mov     rbx, [rsp+28h+arg_0]
0x180017acc  add     rsp, 20h
0x180017ad0  pop     rdi
0x180017ad1  retn
```
