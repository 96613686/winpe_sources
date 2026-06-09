# UtilRegisterErrorReportingDialog(HWND__ *,ulong,uint *)

- ea: `0x14002448c`
- end: `0x14002458e`
- name: `?UtilRegisterErrorReportingDialog@@YAHPEAUHWND__@@KPEAI@Z`
- size: `258`
- prototype: `__int64 __fastcall(HWND hwnd, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400258c0`
- `0x14002927c`

## callees

- `0x140003668`
- `0x140003748`
- `0x14002448c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140024579`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140024579`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140024541`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140024541`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400244e8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400244e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140024500`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140024500`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x14002452b`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x14002452b`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x14002450f`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x14002450f`

## string_xrefs

- `0x1400244e1`: `user32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilRegisterErrorReportingDialog(HWND hwnd, unsigned int a2, unsigned int *a3)
{
  HMODULE Library; // rbx
  DWORD v7; // ecx
  unsigned int v8; // edi
  UINT v9; // eax
  unsigned int v10; // ebp
  FARPROC ProcAddress; // rax

  if ( !hwnd || !a2 )
  {
    v8 = 0;
    goto LABEL_19;
  }
  if ( a3 )
    *a3 = 0;
  if ( !(unsigned __int8)IsRegisterWindowMessageWPresent() || !(unsigned __int8)IsChangeWindowMessageFilterExPresent() )
  {
    v7 = 127;
    goto LABEL_9;
  }
  Library = LoadLibraryExW(L"user32.dll", 0, 0x800u);
  if ( !Library )
  {
    v7 = 126;
LABEL_9:
    v8 = 0;
    SetLastError(v7);
LABEL_19:
    Library = 0;
    goto LABEL_20;
  }
  v9 = RegisterWindowMessageW(L"WerHangRepMessage");
  v10 = v9;
  if ( !v9 )
    goto LABEL_11;
  v8 = ChangeWindowMessageFilterEx(hwnd, v9, 1u, 0);
  if ( !v8 )
    goto LABEL_20;
  ProcAddress = GetProcAddress(Library, "RegisterErrorReportingDialog");
  if ( !ProcAddress )
  {
LABEL_11:
    v8 = 0;
    goto LABEL_20;
  }
  v8 = ((__int64 (__fastcall *)(HWND, _QWORD))ProcAddress)(hwnd, a2);
  if ( v8 && a3 )
    *a3 = v10;
LABEL_20:
  if ( Library )
    FreeLibrary(Library);
  return v8;
}

```

## disassembly

```asm
0x14002448c  push    rbx
0x14002448e  push    rbp
0x14002448f  push    rsi
0x140024490  push    rdi
0x140024491  push    r14
0x140024493  push    r15
0x140024495  sub     rsp, 28h
0x140024499  mov     rsi, r8
0x14002449c  mov     r15d, edx
0x14002449f  mov     r14, rcx
0x1400244a2  test    rcx, rcx
0x1400244a5  jz      loc_14002456D
0x1400244ab  test    edx, edx
0x1400244ad  jz      loc_14002456D
0x1400244b3  test    r8, r8
0x1400244b6  jz      short loc_1400244BF
0x1400244b8  mov     dword ptr [r8], 0
0x1400244bf  call    IsRegisterWindowMessageWPresent
0x1400244c4  test    al, al
0x1400244c6  jz      loc_140024566
0x1400244cc  call    IsChangeWindowMessageFilterExPresent
0x1400244d1  test    al, al
0x1400244d3  jz      loc_140024566
0x1400244d9  xor     edx, edx; hFile
0x1400244db  mov     r8d, 800h; dwFlags
0x1400244e1  lea     rcx, aUser32Dll; "user32.dll"
0x1400244e8  call    cs:__imp_LoadLibraryExW
0x1400244ee  mov     rbx, rax
0x1400244f1  mov     [rsp+58h+arg_0], rax
0x1400244f6  test    rax, rax
0x1400244f9  jnz     short loc_140024508
0x1400244fb  lea     ecx, [rax+7Eh]; dwErrCode
0x1400244fe  xor     edi, edi
0x140024500  call    cs:__imp_SetLastError
0x140024506  jmp     short loc_14002456F
0x140024508  lea     rcx, String; "WerHangRepMessage"
0x14002450f  call    cs:__imp_RegisterWindowMessageW
0x140024515  mov     ebp, eax
0x140024517  test    eax, eax
0x140024519  jnz     short loc_14002451F
0x14002451b  xor     edi, edi
0x14002451d  jmp     short loc_140024571
0x14002451f  xor     r9d, r9d; pChangeFilterStruct
0x140024522  lea     r8d, [r9+1]; action
0x140024526  mov     edx, ebp; message
0x140024528  mov     rcx, r14; hwnd
0x14002452b  call    cs:__imp_ChangeWindowMessageFilterEx
0x140024531  mov     edi, eax
0x140024533  test    eax, eax
0x140024535  jz      short loc_140024571
0x140024537  lea     rdx, aRegistererrorr; "RegisterErrorReportingDialog"
0x14002453e  mov     rcx, rbx; hModule
0x140024541  call    cs:__imp_GetProcAddress
0x140024547  test    rax, rax
0x14002454a  jz      short loc_14002451B
0x14002454c  mov     edx, r15d
0x14002454f  mov     rcx, r14
0x140024552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024557  mov     edi, eax
0x140024559  test    eax, eax
0x14002455b  jz      short loc_140024571
0x14002455d  test    rsi, rsi
0x140024560  jz      short loc_140024571
0x140024562  mov     [rsi], ebp
0x140024564  jmp     short loc_140024571
0x140024566  mov     ecx, 7Fh
0x14002456b  jmp     short loc_1400244FE
0x14002456d  xor     edi, edi
0x14002456f  xor     ebx, ebx
0x140024571  test    rbx, rbx
0x140024574  jz      short loc_14002457F
0x140024576  mov     rcx, rbx; hLibModule
0x140024579  call    cs:__imp_FreeLibrary
0x14002457f  mov     eax, edi
0x140024581  add     rsp, 28h
0x140024585  pop     r15
0x140024587  pop     r14
0x140024589  pop     rdi
0x14002458a  pop     rsi
0x14002458b  pop     rbp
0x14002458c  pop     rbx
0x14002458d  retn
```
