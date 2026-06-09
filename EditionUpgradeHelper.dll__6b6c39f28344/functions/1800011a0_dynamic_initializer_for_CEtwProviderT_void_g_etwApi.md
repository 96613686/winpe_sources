# _dynamic_initializer_for__CEtwProviderT_void_::g_etwApi__

- ea: `0x1800011a0`
- end: `0x180001298`
- name: `_dynamic_initializer_for__CEtwProviderT_void_::g_etwApi__`
- size: `248`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800011a0`
- `0x180001c90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800011be`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800011be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800011e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800011fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001213`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000122c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800011e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800011fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001213`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000122c`

## string_xrefs

- `0x1800011b2`: `ntdll.dll`
- `0x18000121e`: `EtwEventWrite`

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
      qword_18002F908 = (__int64)GetProcAddress(phModule, "EtwEventUnregister");
      qword_18002F910 = (__int64)GetProcAddress(phModule, "EtwEventEnabled");
      ProcAddress = GetProcAddress(phModule, "EtwEventWrite");
      qword_18002F918 = (__int64)ProcAddress;
      if ( !CEtwProviderT<void>::g_etwApi || !qword_18002F908 || !qword_18002F910 || !ProcAddress )
      {
        CEtwProviderT<void>::g_etwApi = 0;
        qword_18002F908 = 0;
        qword_18002F910 = 0;
        qword_18002F918 = 0;
      }
    }
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__CEtwProviderT_void_::g_etwApi__);
}

```

## disassembly

```asm
0x1800011a0  sub     rsp, 28h
0x1800011a4  lea     r8, [rsp+28h+phModule]; phModule
0x1800011a9  mov     [rsp+28h+phModule], 0
0x1800011b2  lea     rdx, ModuleName; "ntdll.dll"
0x1800011b9  mov     ecx, 1; dwFlags
0x1800011be  call    cs:__imp_GetModuleHandleExW
0x1800011c4  test    eax, eax
0x1800011c6  jz      loc_180001288
0x1800011cc  mov     rcx, [rsp+28h+phModule]; hModule
0x1800011d1  test    rcx, rcx
0x1800011d4  jz      loc_180001288
0x1800011da  lea     rdx, ProcName; "EtwEventRegister"
0x1800011e1  call    cs:__imp_GetProcAddress
0x1800011e7  mov     rcx, [rsp+28h+phModule]; hModule
0x1800011ec  lea     rdx, aEtweventunregi; "EtwEventUnregister"
0x1800011f3  mov     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, rax; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x1800011fa  call    cs:__imp_GetProcAddress
0x180001200  mov     rcx, [rsp+28h+phModule]; hModule
0x180001205  lea     rdx, aEtweventenable; "EtwEventEnabled"
0x18000120c  mov     cs:qword_18002F908, rax
0x180001213  call    cs:__imp_GetProcAddress
0x180001219  mov     rcx, [rsp+28h+phModule]; hModule
0x18000121e  lea     rdx, aEtweventwrite; "EtwEventWrite"
0x180001225  mov     cs:qword_18002F910, rax
0x18000122c  call    cs:__imp_GetProcAddress
0x180001232  cmp     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x18000123a  mov     cs:qword_18002F918, rax
0x180001241  jz      short loc_18000125C
0x180001243  cmp     cs:qword_18002F908, 0
0x18000124b  jz      short loc_18000125C
0x18000124d  cmp     cs:qword_18002F910, 0
0x180001255  jz      short loc_18000125C
0x180001257  test    rax, rax
0x18000125a  jnz     short loc_180001288
0x18000125c  mov     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x180001267  mov     cs:qword_18002F908, 0
0x180001272  mov     cs:qword_18002F910, 0
0x18000127d  mov     cs:qword_18002F918, 0
0x180001288  lea     rcx, _dynamic_atexit_destructor_for__CEtwProviderT_void___g_etwApi__
0x18000128f  add     rsp, 28h
0x180001293  jmp     atexit
```
