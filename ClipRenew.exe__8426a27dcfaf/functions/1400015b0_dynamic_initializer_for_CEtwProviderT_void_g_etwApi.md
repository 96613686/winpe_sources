# _dynamic_initializer_for__CEtwProviderT_void_::g_etwApi__

- ea: `0x1400015b0`
- end: `0x1400016a8`
- name: `_dynamic_initializer_for__CEtwProviderT_void_::g_etwApi__`
- size: `248`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400015b0`
- `0x140001d04`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1400015ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1400015ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400015f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000160a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140001623`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000163c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400015f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000160a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140001623`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000163c`

## string_xrefs

- `0x1400015c2`: `ntdll.dll`
- `0x14000162e`: `EtwEventWrite`

## pseudocode

```c
int dynamic_initializer_for__CEtwProviderT_void_::g_etwApi__()
{
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+30h] [rbp+8h] BYREF

  phModule = 0;
  if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule) )
  {
    if ( phModule )
    {
      CEtwProviderT<void>::g_etwApi = (__int64)GetProcAddress(phModule, "EtwEventRegister");
      qword_140019D80 = (__int64)GetProcAddress(phModule, "EtwEventUnregister");
      qword_140019D88 = (__int64)GetProcAddress(phModule, "EtwEventEnabled");
      ProcAddress = GetProcAddress(phModule, "EtwEventWrite");
      qword_140019D90 = (__int64)ProcAddress;
      if ( !CEtwProviderT<void>::g_etwApi || !qword_140019D80 || !qword_140019D88 || !ProcAddress )
      {
        CEtwProviderT<void>::g_etwApi = 0;
        qword_140019D80 = 0;
        qword_140019D88 = 0;
        qword_140019D90 = 0;
      }
    }
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__CEtwProviderT_void_::g_etwApi__);
}

```

## disassembly

```asm
0x1400015b0  sub     rsp, 28h
0x1400015b4  lea     r8, [rsp+28h+phModule]; phModule
0x1400015b9  mov     [rsp+28h+phModule], 0
0x1400015c2  lea     rdx, ModuleName; "ntdll.dll"
0x1400015c9  mov     ecx, 1; dwFlags
0x1400015ce  call    cs:__imp_GetModuleHandleExW
0x1400015d4  test    eax, eax
0x1400015d6  jz      loc_140001698
0x1400015dc  mov     rcx, [rsp+28h+phModule]; hModule
0x1400015e1  test    rcx, rcx
0x1400015e4  jz      loc_140001698
0x1400015ea  lea     rdx, ProcName; "EtwEventRegister"
0x1400015f1  call    cs:__imp_GetProcAddress
0x1400015f7  mov     rcx, [rsp+28h+phModule]; hModule
0x1400015fc  lea     rdx, aEtweventunregi; "EtwEventUnregister"
0x140001603  mov     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, rax; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x14000160a  call    cs:__imp_GetProcAddress
0x140001610  mov     rcx, [rsp+28h+phModule]; hModule
0x140001615  lea     rdx, aEtweventenable; "EtwEventEnabled"
0x14000161c  mov     cs:qword_140019D80, rax
0x140001623  call    cs:__imp_GetProcAddress
0x140001629  mov     rcx, [rsp+28h+phModule]; hModule
0x14000162e  lea     rdx, aEtweventwrite; "EtwEventWrite"
0x140001635  mov     cs:qword_140019D88, rax
0x14000163c  call    cs:__imp_GetProcAddress
0x140001642  cmp     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x14000164a  mov     cs:qword_140019D90, rax
0x140001651  jz      short loc_14000166C
0x140001653  cmp     cs:qword_140019D80, 0
0x14000165b  jz      short loc_14000166C
0x14000165d  cmp     cs:qword_140019D88, 0
0x140001665  jz      short loc_14000166C
0x140001667  test    rax, rax
0x14000166a  jnz     short loc_140001698
0x14000166c  mov     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x140001677  mov     cs:qword_140019D80, 0
0x140001682  mov     cs:qword_140019D88, 0
0x14000168d  mov     cs:qword_140019D90, 0
0x140001698  lea     rcx, _dynamic_atexit_destructor_for__CEtwProviderT_void___g_etwApi__
0x14000169f  add     rsp, 28h
0x1400016a3  jmp     atexit
```
