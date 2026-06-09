# BfspIsWindowsBinary

- ea: `0x140010194`
- end: `0x140010431`
- name: `BfspIsWindowsBinary`
- size: `669`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140009fd4`
- `0x14000d494`

## callees

- `0x140010194`
- `0x140027010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1400103d4`
- `msvcrt!_wcsicmp` at `0x1400103d4`
- `msvcrt!swprintf_s` at `0x14001039c`
- `msvcrt!swprintf_s` at `0x14001039c`
- `KERNEL32!GetLastError` at `0x140010210`
- `KERNEL32!GetLastError` at `0x140010210`
- `KERNEL32!HeapFree` at `0x1400103f3`
- `KERNEL32!HeapFree` at `0x14001040c`
- `KERNEL32!HeapFree` at `0x1400103f3`
- `KERNEL32!HeapFree` at `0x14001040c`
- `KERNEL32!HeapAlloc` at `0x1400102ef`
- `KERNEL32!HeapAlloc` at `0x14001036f`
- `KERNEL32!HeapAlloc` at `0x1400102ef`
- `KERNEL32!HeapAlloc` at `0x14001036f`
- `KERNEL32!GetProcAddress` at `0x140010239`
- `KERNEL32!GetProcAddress` at `0x140010263`
- `KERNEL32!GetProcAddress` at `0x140010290`
- `KERNEL32!GetProcAddress` at `0x140010239`
- `KERNEL32!GetProcAddress` at `0x140010263`
- `KERNEL32!GetProcAddress` at `0x140010290`
- `KERNEL32!GetProcessHeap` at `0x1400102e1`
- `KERNEL32!GetProcessHeap` at `0x14001035d`
- `KERNEL32!GetProcessHeap` at `0x1400103e5`
- `KERNEL32!GetProcessHeap` at `0x1400103fe`
- `KERNEL32!GetProcessHeap` at `0x1400102e1`
- `KERNEL32!GetProcessHeap` at `0x14001035d`
- `KERNEL32!GetProcessHeap` at `0x1400103e5`
- `KERNEL32!GetProcessHeap` at `0x1400103fe`
- `KERNEL32!LoadLibraryExW` at `0x1400101fe`
- `KERNEL32!LoadLibraryExW` at `0x1400101fe`

## string_xrefs

- `0x1400101f5`: `version.dll`

## pseudocode

```c
__int64 __fastcall BfspIsWindowsBinary(__int64 a1, const wchar_t *a2, int a3)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rcx
  __int64 (__fastcall *v7)(__int64, int *); // r8
  FARPROC v8; // rax
  unsigned int v9; // r14d
  HANDLE ProcessHeap; // rax
  LPVOID v11; // rax
  void *v12; // rsi
  wchar_t *v13; // rdi
  unsigned int v14; // ebx
  HANDLE v15; // rax
  HANDLE v16; // rax
  HANDLE v17; // rax
  int v19; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v20; // [rsp+38h] [rbp-18h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-10h] BYREF
  int v22; // [rsp+90h] [rbp+40h] BYREF
  int v23; // [rsp+98h] [rbp+48h] BYREF

  v23 = 0;
  v22 = 0;
  v19 = 0;
  String1 = 0;
  v20 = 0;
  if ( a3 != 2 )
    return 0;
  Library = g_hInstVersionDLL;
  if ( !g_hInstVersionDLL )
  {
    Library = LoadLibraryExW(L"version.dll", 0, 8u);
    g_hInstVersionDLL = Library;
    if ( !Library )
    {
      if ( !GetLastError() )
      {
        Library = g_hInstVersionDLL;
        goto LABEL_6;
      }
      return 0;
    }
  }
LABEL_6:
  if ( !qword_14003F810 )
  {
    qword_14003F810 = (__int64)GetProcAddress(Library, "VerQueryValueW");
    Library = g_hInstVersionDLL;
  }
  ProcAddress = (FARPROC)qword_14003F7F8;
  if ( !qword_14003F7F8 )
  {
    ProcAddress = GetProcAddress(Library, "GetFileVersionInfoW");
    qword_14003F7F8 = (__int64)ProcAddress;
    Library = g_hInstVersionDLL;
  }
  v7 = (__int64 (__fastcall *)(__int64, int *))qword_14003F808;
  if ( !qword_14003F808 )
  {
    v8 = GetProcAddress(Library, "GetFileVersionInfoSizeW");
    ProcAddress = (FARPROC)qword_14003F7F8;
    v7 = (__int64 (__fastcall *)(__int64, int *))v8;
    qword_14003F808 = (__int64)v8;
  }
  if ( !qword_14003F810 )
    return 0;
  if ( !ProcAddress )
    return 0;
  if ( !v7 )
    return 0;
  v9 = v7(a1, &v19);
  if ( !v9 )
    return 0;
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, v9);
  v12 = v11;
  if ( !v11 )
    return 0;
  v13 = 0;
  v14 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, LPVOID))qword_14003F7F8)(a1, 0, v9, v11);
  if ( v14 )
    v14 = (unsigned int)((__int64 (__fastcall *)(void *, const wchar_t *, unsigned __int16 **, int *))qword_14003F810)(
                          v12,
                          L"\\VarFileInfo\\Translation",
                          &v20,
                          &v22)
       && v20
       && v22
       && (v15 = GetProcessHeap(), (v13 = (wchar_t *)HeapAlloc(v15, 8u, 0x208u)) != 0)
       && (swprintf_s(v13, 0x104u, L"\\StringFileInfo\\%04x%04x\\InternalName", *v20, v20[1]),
           (unsigned int)((__int64 (__fastcall *)(void *, wchar_t *, wchar_t **, int *))qword_14003F810)(
                           v12,
                           v13,
                           &String1,
                           &v23))
       && String1
       && v23
       && _wcsicmp(String1, a2) == 0;
  v16 = GetProcessHeap();
  HeapFree(v16, 0, v12);
  if ( v13 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v13);
  }
  return v14;
}

```

## disassembly

```asm
0x140010194  mov     [rsp-28h+arg_0], rbx
0x140010199  mov     [rsp-28h+arg_8], rsi
0x14001019e  push    rbp
0x14001019f  push    rdi
0x1400101a0  push    r12
0x1400101a2  push    r14
0x1400101a4  push    r15
0x1400101a6  mov     rbp, rsp
0x1400101a9  sub     rsp, 50h
0x1400101ad  mov     [rbp+arg_18], 0
0x1400101b4  mov     r12, rdx
0x1400101b7  mov     [rbp+arg_10], 0
0x1400101be  mov     r15, rcx
0x1400101c1  mov     [rbp+var_20], 0
0x1400101c8  mov     [rbp+String1], 0
0x1400101d0  mov     [rbp+var_18], 0
0x1400101d8  cmp     r8d, 2
0x1400101dc  jnz     loc_140010414
0x1400101e2  mov     rax, cs:g_hInstVersionDLL
0x1400101e9  lea     edi, [r8+6]
0x1400101ed  test    rax, rax
0x1400101f0  jnz     short loc_140010225
0x1400101f2  mov     r8d, edi; dwFlags
0x1400101f5  lea     rcx, aVersionDll; "version.dll"
0x1400101fc  xor     edx, edx; hFile
0x1400101fe  call    cs:__imp_LoadLibraryExW
0x140010204  mov     cs:g_hInstVersionDLL, rax
0x14001020b  test    rax, rax
0x14001020e  jnz     short loc_140010225
0x140010210  call    cs:__imp_GetLastError
0x140010216  test    eax, eax
0x140010218  jnz     loc_140010414
0x14001021e  mov     rax, cs:g_hInstVersionDLL
0x140010225  cmp     cs:qword_14003F810, 0
0x14001022d  jnz     short loc_14001024D
0x14001022f  lea     rdx, aVerqueryvaluew; "VerQueryValueW"
0x140010236  mov     rcx, rax; hModule
0x140010239  call    cs:__imp_GetProcAddress
0x14001023f  mov     cs:qword_14003F810, rax
0x140010246  mov     rax, cs:g_hInstVersionDLL
0x14001024d  mov     rcx, cs:qword_14003F7F8
0x140010254  test    rcx, rcx
0x140010257  jnz     short loc_14001027A
0x140010259  lea     rdx, aGetfileversion_0; "GetFileVersionInfoW"
0x140010260  mov     rcx, rax; hModule
0x140010263  call    cs:__imp_GetProcAddress
0x140010269  mov     rcx, rax
0x14001026c  mov     cs:qword_14003F7F8, rax
0x140010273  mov     rax, cs:g_hInstVersionDLL
0x14001027a  mov     r8, cs:qword_14003F808
0x140010281  test    r8, r8
0x140010284  jnz     short loc_1400102A7
0x140010286  lea     rdx, aGetfileversion; "GetFileVersionInfoSizeW"
0x14001028d  mov     rcx, rax; hModule
0x140010290  call    cs:__imp_GetProcAddress
0x140010296  mov     rcx, cs:qword_14003F7F8
0x14001029d  mov     r8, rax
0x1400102a0  mov     cs:qword_14003F808, rax
0x1400102a7  cmp     cs:qword_14003F810, 0
0x1400102af  jz      loc_140010414
0x1400102b5  test    rcx, rcx
0x1400102b8  jz      loc_140010414
0x1400102be  test    r8, r8
0x1400102c1  jz      loc_140010414
0x1400102c7  lea     rdx, [rbp+var_20]
0x1400102cb  mov     rcx, r15
0x1400102ce  mov     rax, r8
0x1400102d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102d6  mov     r14d, eax
0x1400102d9  test    eax, eax
0x1400102db  jz      loc_140010414
0x1400102e1  call    cs:__imp_GetProcessHeap
0x1400102e7  mov     r8d, r14d; dwBytes
0x1400102ea  mov     edx, edi; dwFlags
0x1400102ec  mov     rcx, rax; hHeap
0x1400102ef  call    cs:__imp_HeapAlloc
0x1400102f5  mov     rsi, rax
0x1400102f8  test    rax, rax
0x1400102fb  jz      loc_140010414
0x140010301  mov     r9, rax
0x140010304  mov     r8d, r14d
0x140010307  mov     rax, cs:qword_14003F7F8
0x14001030e  xor     edx, edx
0x140010310  mov     rcx, r15
0x140010313  xor     edi, edi
0x140010315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001031a  mov     ebx, eax
0x14001031c  test    eax, eax
0x14001031e  jz      loc_1400103E5
0x140010324  mov     rax, cs:qword_14003F810
0x14001032b  lea     r9, [rbp+arg_10]
0x14001032f  lea     r8, [rbp+var_18]
0x140010333  mov     rcx, rsi
0x140010336  lea     rdx, aVarfileinfoTra; "\\VarFileInfo\\Translation"
0x14001033d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010342  test    eax, eax
0x140010344  jz      loc_1400103E3
0x14001034a  cmp     [rbp+var_18], rdi
0x14001034e  jz      loc_1400103E3
0x140010354  cmp     [rbp+arg_10], edi
0x140010357  jz      loc_1400103E3
0x14001035d  call    cs:__imp_GetProcessHeap
0x140010363  lea     edx, [rdi+8]; dwFlags
0x140010366  mov     r8d, 208h; dwBytes
0x14001036c  mov     rcx, rax; hHeap
0x14001036f  call    cs:__imp_HeapAlloc
0x140010375  mov     rdi, rax
0x140010378  test    rax, rax
0x14001037b  jz      short loc_1400103E3
0x14001037d  mov     rax, [rbp+var_18]
0x140010381  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\InternalNam"...
0x140010388  mov     edx, 104h; BufferCount
0x14001038d  movzx   ecx, word ptr [rax+2]
0x140010391  movzx   r9d, word ptr [rax]
0x140010395  mov     [rsp+50h+var_30], ecx
0x140010399  mov     rcx, rdi; Buffer
0x14001039c  call    cs:__imp_swprintf_s
0x1400103a2  mov     rax, cs:qword_14003F810
0x1400103a9  lea     r9, [rbp+arg_18]
0x1400103ad  lea     r8, [rbp+String1]
0x1400103b1  mov     rdx, rdi
0x1400103b4  mov     rcx, rsi
0x1400103b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400103bc  test    eax, eax
0x1400103be  jz      short loc_1400103E3
0x1400103c0  mov     rcx, [rbp+String1]; String1
0x1400103c4  test    rcx, rcx
0x1400103c7  jz      short loc_1400103E3
0x1400103c9  cmp     [rbp+arg_18], 0
0x1400103cd  jz      short loc_1400103E3
0x1400103cf  mov     rdx, r12; String2
0x1400103d2  xor     ebx, ebx
0x1400103d4  call    cs:__imp__wcsicmp
0x1400103da  test    eax, eax
0x1400103dc  jnz     short loc_1400103E5
0x1400103de  lea     ebx, [rax+1]
0x1400103e1  jmp     short loc_1400103E5
0x1400103e3  xor     ebx, ebx
0x1400103e5  call    cs:__imp_GetProcessHeap
0x1400103eb  mov     r8, rsi; lpMem
0x1400103ee  xor     edx, edx; dwFlags
0x1400103f0  mov     rcx, rax; hHeap
0x1400103f3  call    cs:__imp_HeapFree
0x1400103f9  test    rdi, rdi
0x1400103fc  jz      short loc_140010416
0x1400103fe  call    cs:__imp_GetProcessHeap
0x140010404  mov     r8, rdi; lpMem
0x140010407  xor     edx, edx; dwFlags
0x140010409  mov     rcx, rax; hHeap
0x14001040c  call    cs:__imp_HeapFree
0x140010412  jmp     short loc_140010416
0x140010414  xor     ebx, ebx
0x140010416  lea     r11, [rsp+50h+var_s0]
0x14001041b  mov     eax, ebx
0x14001041d  mov     rbx, [r11+30h]
0x140010421  mov     rsi, [r11+38h]
0x140010425  mov     rsp, r11
0x140010428  pop     r15
0x14001042a  pop     r14
0x14001042c  pop     r12
0x14001042e  pop     rdi
0x14001042f  pop     rbp
0x140010430  retn
```
