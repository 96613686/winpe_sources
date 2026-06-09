# _dynamic_initializer_for__CEtwProviderT_void_::g_etwApi__

- ea: `0x180001250`
- end: `0x180001348`
- name: `_dynamic_initializer_for__CEtwProviderT_void_::g_etwApi__`
- size: `248`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001250`
- `0x180001e70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000126e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000126e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001291`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800012aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800012c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800012dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001291`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800012aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800012c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800012dc`

## string_xrefs

- `0x180001262`: `ntdll.dll`
- `0x1800012ce`: `EtwEventWrite`

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
      qword_18002FC80 = (__int64)GetProcAddress(phModule, "EtwEventUnregister");
      qword_18002FC88 = (__int64)GetProcAddress(phModule, "EtwEventEnabled");
      ProcAddress = GetProcAddress(phModule, "EtwEventWrite");
      qword_18002FC90 = (__int64)ProcAddress;
      if ( !CEtwProviderT<void>::g_etwApi || !qword_18002FC80 || !qword_18002FC88 || !ProcAddress )
      {
        CEtwProviderT<void>::g_etwApi = 0;
        qword_18002FC80 = 0;
        qword_18002FC88 = 0;
        qword_18002FC90 = 0;
      }
    }
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__CEtwProviderT_void_::g_etwApi__);
}

```

## disassembly

```asm
0x180001250  sub     rsp, 28h
0x180001254  lea     r8, [rsp+28h+phModule]; phModule
0x180001259  mov     [rsp+28h+phModule], 0
0x180001262  lea     rdx, ModuleName; "ntdll.dll"
0x180001269  mov     ecx, 1; dwFlags
0x18000126e  call    cs:__imp_GetModuleHandleExW
0x180001274  test    eax, eax
0x180001276  jz      loc_180001338
0x18000127c  mov     rcx, [rsp+28h+phModule]; hModule
0x180001281  test    rcx, rcx
0x180001284  jz      loc_180001338
0x18000128a  lea     rdx, ProcName; "EtwEventRegister"
0x180001291  call    cs:__imp_GetProcAddress
0x180001297  mov     rcx, [rsp+28h+phModule]; hModule
0x18000129c  lea     rdx, aEtweventunregi; "EtwEventUnregister"
0x1800012a3  mov     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, rax; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x1800012aa  call    cs:__imp_GetProcAddress
0x1800012b0  mov     rcx, [rsp+28h+phModule]; hModule
0x1800012b5  lea     rdx, aEtweventenable; "EtwEventEnabled"
0x1800012bc  mov     cs:qword_18002FC80, rax
0x1800012c3  call    cs:__imp_GetProcAddress
0x1800012c9  mov     rcx, [rsp+28h+phModule]; hModule
0x1800012ce  lea     rdx, aEtweventwrite; "EtwEventWrite"
0x1800012d5  mov     cs:qword_18002FC88, rax
0x1800012dc  call    cs:__imp_GetProcAddress
0x1800012e2  cmp     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x1800012ea  mov     cs:qword_18002FC90, rax
0x1800012f1  jz      short loc_18000130C
0x1800012f3  cmp     cs:qword_18002FC80, 0
0x1800012fb  jz      short loc_18000130C
0x1800012fd  cmp     cs:qword_18002FC88, 0
0x180001305  jz      short loc_18000130C
0x180001307  test    rax, rax
0x18000130a  jnz     short loc_180001338
0x18000130c  mov     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x180001317  mov     cs:qword_18002FC80, 0
0x180001322  mov     cs:qword_18002FC88, 0
0x18000132d  mov     cs:qword_18002FC90, 0
0x180001338  lea     rcx, _dynamic_atexit_destructor_for__CEtwProviderT_void___g_etwApi__
0x18000133f  add     rsp, 28h
0x180001343  jmp     atexit
```
