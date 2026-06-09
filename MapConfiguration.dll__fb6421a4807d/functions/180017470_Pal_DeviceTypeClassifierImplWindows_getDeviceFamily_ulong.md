# Pal::DeviceTypeClassifierImplWindows::getDeviceFamily(ulong *)

- ea: `0x180017470`
- end: `0x180017547`
- name: `?getDeviceFamily@DeviceTypeClassifierImplWindows@Pal@@CA_NPEAK@Z`
- size: `215`
- prototype: `bool __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015b0c`

## callees

- `0x180017470`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800174d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800174d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800174c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800174c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001748c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001748c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800174a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017534`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800174a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017534`

## string_xrefs

- `0x1800174bc`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Pal::DeviceTypeClassifierImplWindows::getDeviceFamily(unsigned int *a1)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v5; // eax
  char v6; // bl
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF
  __int64 v9; // [rsp+58h] [rbp+20h] BYREF

  EnterCriticalSection(&stru_18007B7F0);
  if ( byte_18007B81C )
  {
    *a1 = dword_18007B818;
    LeaveCriticalSection(&stru_18007B7F0);
    return 1;
  }
  else
  {
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    if ( Library && (ProcAddress = GetProcAddress(Library, "RtlGetDeviceFamilyInfoEnum")) != 0 )
    {
      v9 = 0;
      v7 = 0;
      v8 = 0;
      ((void (__fastcall *)(__int64 *, unsigned int *, int *))ProcAddress)(&v9, &v7, &v8);
      v5 = v7;
      *a1 = v7;
      v6 = 1;
      dword_18007B818 = v5;
      if ( !byte_18007B81C )
        byte_18007B81C = 1;
    }
    else
    {
      v6 = 0;
    }
    LeaveCriticalSection(&stru_18007B7F0);
    return v6;
  }
}

```

## disassembly

```asm
0x180017470  mov     [rsp+arg_0], rbx
0x180017475  push    rsi
0x180017476  sub     rsp, 30h
0x18001747a  mov     rbx, rcx
0x18001747d  lea     rsi, stru_18007B7F0
0x180017484  mov     [rsp+38h+var_18], rsi
0x180017489  mov     rcx, rsi; lpCriticalSection
0x18001748c  call    cs:__imp_EnterCriticalSection
0x180017492  nop
0x180017493  cmp     cs:byte_18007B81C, 0
0x18001749a  jz      short loc_1800174B4
0x18001749c  mov     eax, cs:dword_18007B818
0x1800174a2  mov     [rbx], eax
0x1800174a4  mov     rcx, rsi; lpCriticalSection
0x1800174a7  call    cs:__imp_LeaveCriticalSection
0x1800174ad  mov     al, 1
0x1800174af  jmp     loc_18001753C
0x1800174b4  xor     edx, edx; hFile
0x1800174b6  mov     r8d, 800h; dwFlags
0x1800174bc  lea     rcx, LibFileName; "ntdll.dll"
0x1800174c3  call    cs:__imp_LoadLibraryExW
0x1800174c9  test    rax, rax
0x1800174cc  jz      short loc_18001752F
0x1800174ce  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x1800174d5  mov     rcx, rax; hModule
0x1800174d8  call    cs:__imp_GetProcAddress
0x1800174de  test    rax, rax
0x1800174e1  jz      short loc_18001752F
0x1800174e3  mov     [rsp+38h+arg_18], 0
0x1800174ec  mov     [rsp+38h+arg_8], 0
0x1800174f4  mov     [rsp+38h+arg_10], 0
0x1800174fc  lea     r8, [rsp+38h+arg_10]
0x180017501  lea     rdx, [rsp+38h+arg_8]
0x180017506  lea     rcx, [rsp+38h+arg_18]
0x18001750b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017510  mov     eax, [rsp+38h+arg_8]
0x180017514  mov     [rbx], eax
0x180017516  mov     bl, 1
0x180017518  mov     cs:dword_18007B818, eax
0x18001751e  cmp     cs:byte_18007B81C, 0
0x180017525  jnz     short loc_180017531
0x180017527  mov     cs:byte_18007B81C, bl
0x18001752d  jmp     short loc_180017531
0x18001752f  xor     ebx, ebx
0x180017531  mov     rcx, rsi; lpCriticalSection
0x180017534  call    cs:__imp_LeaveCriticalSection
0x18001753a  mov     al, bl
0x18001753c  mov     rbx, [rsp+38h+arg_0]
0x180017541  add     rsp, 30h
0x180017545  pop     rsi
0x180017546  retn
```
