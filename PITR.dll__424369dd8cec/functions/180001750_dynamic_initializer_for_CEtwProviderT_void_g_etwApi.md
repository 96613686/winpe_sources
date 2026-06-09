# _dynamic_initializer_for__CEtwProviderT_void_::g_etwApi__

- ea: `0x180001750`
- end: `0x180001848`
- name: `_dynamic_initializer_for__CEtwProviderT_void_::g_etwApi__`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001750`
- `0x180002140`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000176e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000176e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001791`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800017aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800017c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800017dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001791`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800017aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800017c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800017dc`

## string_xrefs

- `0x180001762`: `ntdll.dll`
- `0x1800017ce`: `EtwEventWrite`

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
      qword_180080C78 = (__int64)GetProcAddress(phModule, "EtwEventUnregister");
      qword_180080C80 = (__int64)GetProcAddress(phModule, "EtwEventEnabled");
      ProcAddress = GetProcAddress(phModule, "EtwEventWrite");
      qword_180080C88 = (__int64)ProcAddress;
      if ( !CEtwProviderT<void>::g_etwApi || !qword_180080C78 || !qword_180080C80 || !ProcAddress )
      {
        CEtwProviderT<void>::g_etwApi = 0;
        qword_180080C78 = 0;
        qword_180080C80 = 0;
        qword_180080C88 = 0;
      }
    }
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__CEtwProviderT_void_::g_etwApi__);
}

```

## disassembly

```asm
0x180001750  sub     rsp, 28h
0x180001754  lea     r8, [rsp+28h+phModule]; phModule
0x180001759  mov     [rsp+28h+phModule], 0
0x180001762  lea     rdx, aNtdllDll_2; "ntdll.dll"
0x180001769  mov     ecx, 1; dwFlags
0x18000176e  call    cs:__imp_GetModuleHandleExW
0x180001774  test    eax, eax
0x180001776  jz      loc_180001838
0x18000177c  mov     rcx, [rsp+28h+phModule]; hModule
0x180001781  test    rcx, rcx
0x180001784  jz      loc_180001838
0x18000178a  lea     rdx, aEtweventregist; "EtwEventRegister"
0x180001791  call    cs:__imp_GetProcAddress
0x180001797  mov     rcx, [rsp+28h+phModule]; hModule
0x18000179c  lea     rdx, aEtweventunregi; "EtwEventUnregister"
0x1800017a3  mov     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, rax; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x1800017aa  call    cs:__imp_GetProcAddress
0x1800017b0  mov     rcx, [rsp+28h+phModule]; hModule
0x1800017b5  lea     rdx, aEtweventenable; "EtwEventEnabled"
0x1800017bc  mov     cs:qword_180080C78, rax
0x1800017c3  call    cs:__imp_GetProcAddress
0x1800017c9  mov     rcx, [rsp+28h+phModule]; hModule
0x1800017ce  lea     rdx, aEtweventwrite; "EtwEventWrite"
0x1800017d5  mov     cs:qword_180080C80, rax
0x1800017dc  call    cs:__imp_GetProcAddress
0x1800017e2  cmp     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x1800017ea  mov     cs:qword_180080C88, rax
0x1800017f1  jz      short loc_18000180C
0x1800017f3  cmp     cs:qword_180080C78, 0
0x1800017fb  jz      short loc_18000180C
0x1800017fd  cmp     cs:qword_180080C80, 0
0x180001805  jz      short loc_18000180C
0x180001807  test    rax, rax
0x18000180a  jnz     short loc_180001838
0x18000180c  mov     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x180001817  mov     cs:qword_180080C78, 0
0x180001822  mov     cs:qword_180080C80, 0
0x18000182d  mov     cs:qword_180080C88, 0
0x180001838  lea     rcx, _dynamic_atexit_destructor_for__CEtwProviderT_void___g_etwApi__
0x18000183f  add     rsp, 28h
0x180001843  jmp     atexit
```
