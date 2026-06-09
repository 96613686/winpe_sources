# CreateCoreIndependentInput_0

- ea: `0x1800b34dc`
- end: `0x1800b3564`
- name: `CreateCoreIndependentInput_0`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800b32ac`

## callees

- `0x1800b34dc`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b350d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b350d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b3520`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b3520`

## string_xrefs

- `0x1800b34ff`: `windows.ui.dll`

## pseudocode

```c
__int64 __fastcall CreateCoreIndependentInput_0(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  FARPROC ProcAddress; // rax
  unsigned int v6; // ebx
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18015C008;
  *a4 = 0;
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, GUID *, _QWORD *))ProcAddress)(
             0,
             4,
             0,
             &GUID_9f488807_4580_4be8_be68_92a9311713bb,
             a4);
  v6 = -2147467259;
  Library = LoadLibraryExW(L"windows.ui.dll", 0, 0);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, (LPCSTR)0x640);
    qword_18015C008 = (__int64)ProcAddress;
  }
  else
  {
    ProcAddress = (FARPROC)qword_18015C008;
  }
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, GUID *, _QWORD *))ProcAddress)(
             0,
             4,
             0,
             &GUID_9f488807_4580_4be8_be68_92a9311713bb,
             a4);
  return v6;
}

```

## disassembly

```asm
0x1800b34dc  mov     [rsp+arg_0], rbx
0x1800b34e1  push    rdi
0x1800b34e2  sub     rsp, 30h
0x1800b34e6  mov     rax, cs:qword_18015C008
0x1800b34ed  mov     rdi, r9
0x1800b34f0  mov     qword ptr [r9], 0
0x1800b34f7  test    rax, rax
0x1800b34fa  jnz     short loc_1800B353B
0x1800b34fc  xor     r8d, r8d; dwFlags
0x1800b34ff  lea     rcx, LibFileName; "windows.ui.dll"
0x1800b3506  xor     edx, edx; hFile
0x1800b3508  mov     ebx, 80004005h
0x1800b350d  call    cs:__imp_LoadLibraryExW
0x1800b3513  test    rax, rax
0x1800b3516  jz      short loc_1800B352F
0x1800b3518  mov     edx, 640h; lpProcName
0x1800b351d  mov     rcx, rax; hModule
0x1800b3520  call    cs:__imp_GetProcAddress
0x1800b3526  mov     cs:qword_18015C008, rax
0x1800b352d  jmp     short loc_1800B3536
0x1800b352f  mov     rax, cs:qword_18015C008
0x1800b3536  test    rax, rax
0x1800b3539  jz      short loc_1800B3557
0x1800b353b  xor     r8d, r8d
0x1800b353e  mov     [rsp+38h+var_18], rdi
0x1800b3543  lea     r9, _GUID_9f488807_4580_4be8_be68_92a9311713bb
0x1800b354a  xor     ecx, ecx
0x1800b354c  lea     edx, [r8+4]
0x1800b3550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3555  mov     ebx, eax
0x1800b3557  mov     eax, ebx
0x1800b3559  mov     rbx, [rsp+38h+arg_0]
0x1800b355e  add     rsp, 30h
0x1800b3562  pop     rdi
0x1800b3563  retn
```
