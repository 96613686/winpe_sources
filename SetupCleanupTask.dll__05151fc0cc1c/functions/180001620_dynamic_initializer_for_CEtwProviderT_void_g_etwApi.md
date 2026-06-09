# _dynamic_initializer_for__CEtwProviderT_void_::g_etwApi__

- ea: `0x180001620`
- end: `0x180001718`
- name: `_dynamic_initializer_for__CEtwProviderT_void_::g_etwApi__`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001620`
- `0x1800026c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000163e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000163e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001661`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000167a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001693`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800016ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001661`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000167a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001693`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800016ac`

## string_xrefs

- `0x180001632`: `ntdll.dll`
- `0x18000169e`: `EtwEventWrite`

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
      qword_180053098 = (__int64)GetProcAddress(phModule, "EtwEventUnregister");
      qword_1800530A0 = (__int64)GetProcAddress(phModule, "EtwEventEnabled");
      ProcAddress = GetProcAddress(phModule, "EtwEventWrite");
      qword_1800530A8 = (__int64)ProcAddress;
      if ( !CEtwProviderT<void>::g_etwApi || !qword_180053098 || !qword_1800530A0 || !ProcAddress )
      {
        CEtwProviderT<void>::g_etwApi = 0;
        qword_180053098 = 0;
        qword_1800530A0 = 0;
        qword_1800530A8 = 0;
      }
    }
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__CEtwProviderT_void_::g_etwApi__);
}

```

## disassembly

```asm
0x180001620  sub     rsp, 28h
0x180001624  lea     r8, [rsp+28h+phModule]; phModule
0x180001629  mov     [rsp+28h+phModule], 0
0x180001632  lea     rdx, LibFileName; "ntdll.dll"
0x180001639  mov     ecx, 1; dwFlags
0x18000163e  call    cs:__imp_GetModuleHandleExW
0x180001644  test    eax, eax
0x180001646  jz      loc_180001708
0x18000164c  mov     rcx, [rsp+28h+phModule]; hModule
0x180001651  test    rcx, rcx
0x180001654  jz      loc_180001708
0x18000165a  lea     rdx, ProcName; "EtwEventRegister"
0x180001661  call    cs:__imp_GetProcAddress
0x180001667  mov     rcx, [rsp+28h+phModule]; hModule
0x18000166c  lea     rdx, aEtweventunregi; "EtwEventUnregister"
0x180001673  mov     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, rax; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x18000167a  call    cs:__imp_GetProcAddress
0x180001680  mov     rcx, [rsp+28h+phModule]; hModule
0x180001685  lea     rdx, aEtweventenable; "EtwEventEnabled"
0x18000168c  mov     cs:qword_180053098, rax
0x180001693  call    cs:__imp_GetProcAddress
0x180001699  mov     rcx, [rsp+28h+phModule]; hModule
0x18000169e  lea     rdx, aEtweventwrite; "EtwEventWrite"
0x1800016a5  mov     cs:qword_1800530A0, rax
0x1800016ac  call    cs:__imp_GetProcAddress
0x1800016b2  cmp     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x1800016ba  mov     cs:qword_1800530A8, rax
0x1800016c1  jz      short loc_1800016DC
0x1800016c3  cmp     cs:qword_180053098, 0
0x1800016cb  jz      short loc_1800016DC
0x1800016cd  cmp     cs:qword_1800530A0, 0
0x1800016d5  jz      short loc_1800016DC
0x1800016d7  test    rax, rax
0x1800016da  jnz     short loc_180001708
0x1800016dc  mov     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x1800016e7  mov     cs:qword_180053098, 0
0x1800016f2  mov     cs:qword_1800530A0, 0
0x1800016fd  mov     cs:qword_1800530A8, 0
0x180001708  lea     rcx, _dynamic_atexit_destructor_for__CEtwProviderT_void___g_etwApi__
0x18000170f  add     rsp, 28h
0x180001713  jmp     atexit
```
