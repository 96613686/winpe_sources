# AppUtilities::FinalizeFile(FileDialogMode,int,ushort * *,ushort * *,void * *)

- ea: `0x180003a80`
- end: `0x180003b8e`
- name: `?FinalizeFile@AppUtilities@@UEAAJW4FileDialogMode@@HPEAPEAG1PEAPEAX@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64, int, int, unsigned __int16 **, __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180003a80`
- `0x180035010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180003b30`
- `KERNEL32!FreeLibrary` at `0x180003b30`
- `KERNEL32!GetProcAddress` at `0x180003b15`
- `KERNEL32!GetProcAddress` at `0x180003b6e`
- `KERNEL32!GetProcAddress` at `0x180003b15`
- `KERNEL32!GetProcAddress` at `0x180003b6e`
- `KERNEL32!LoadLibraryExW` at `0x180003afd`
- `KERNEL32!LoadLibraryExW` at `0x180003b56`
- `KERNEL32!LoadLibraryExW` at `0x180003afd`
- `KERNEL32!LoadLibraryExW` at `0x180003b56`

## string_xrefs

- `0x180003aef`: `ieframe.dll`
- `0x180003b48`: `ieframe.dll`

## pseudocode

```c
__int64 __fastcall AppUtilities::FinalizeFile(
        __int64 a1,
        int a2,
        int a3,
        unsigned __int16 **a4,
        __int64 *a5,
        __int64 *a6)
{
  __int64 v6; // rsi
  __int64 v7; // rbp
  unsigned __int16 *v8; // rax
  int v9; // edx
  int v10; // ecx
  unsigned int v11; // ebx
  HMODULE Library; // rax
  HMODULE v13; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v15; // eax
  HMODULE v17; // rax
  FARPROC v18; // rax

  if ( a2 != 1 )
    return 0;
  if ( !a3 )
    return 0;
  if ( !a6 )
    return 0;
  v6 = *a6;
  if ( !*a6 )
    return 0;
  if ( a4 && a5 )
  {
    v7 = *a5;
    v8 = *a4;
    do
    {
      v9 = *(unsigned __int16 *)((char *)v8 + v7 - (_QWORD)*a4);
      v10 = *v8 - v9;
      if ( v10 )
        break;
      ++v8;
    }
    while ( v9 );
    if ( v10 )
    {
      v11 = -2147467263;
      Library = LoadLibraryExW(L"ieframe.dll", 0, 0);
      v13 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "IESaveFile");
        if ( !ProcAddress )
          goto LABEL_15;
        v15 = ((__int64 (__fastcall *)(__int64, __int64))ProcAddress)(v6, v7);
        goto LABEL_14;
      }
      return v11;
    }
  }
  v11 = -2147467263;
  v17 = LoadLibraryExW(L"ieframe.dll", 0, 0);
  v13 = v17;
  if ( !v17 )
    return v11;
  v18 = GetProcAddress(v17, "IECancelSaveFile");
  if ( v18 )
  {
    v15 = ((__int64 (__fastcall *)(__int64))v18)(v6);
LABEL_14:
    v11 = v15;
  }
LABEL_15:
  FreeLibrary(v13);
  if ( v11 )
  {
    if ( (v11 & 0x80000000) == 0 )
      return (unsigned int)-2147467259;
    return v11;
  }
  return 0;
}

```

## disassembly

```asm
0x180003a80  push    rbx
0x180003a82  push    rbp
0x180003a83  push    rsi
0x180003a84  push    rdi
0x180003a85  sub     rsp, 28h
0x180003a89  cmp     edx, 1
0x180003a8c  jnz     loc_180003B83
0x180003a92  test    r8d, r8d
0x180003a95  jz      loc_180003B83
0x180003a9b  mov     rax, [rsp+48h+arg_28]
0x180003aa0  test    rax, rax
0x180003aa3  jz      loc_180003B83
0x180003aa9  mov     rsi, [rax]
0x180003aac  test    rsi, rsi
0x180003aaf  jz      loc_180003B83
0x180003ab5  test    r9, r9
0x180003ab8  jz      loc_180003B45
0x180003abe  mov     rax, [rsp+48h+arg_20]
0x180003ac3  test    rax, rax
0x180003ac6  jz      short loc_180003B45
0x180003ac8  mov     rbp, [rax]
0x180003acb  mov     rax, [r9]
0x180003ace  mov     r8, rbp
0x180003ad1  sub     r8, rax
0x180003ad4  movzx   ecx, word ptr [rax]
0x180003ad7  movzx   edx, word ptr [rax+r8]
0x180003adc  sub     ecx, edx
0x180003ade  jnz     short loc_180003AE8
0x180003ae0  add     rax, 2
0x180003ae4  test    edx, edx
0x180003ae6  jnz     short loc_180003AD4
0x180003ae8  test    ecx, ecx
0x180003aea  jz      short loc_180003B45
0x180003aec  xor     r8d, r8d; dwFlags
0x180003aef  lea     rcx, LibFileName; "ieframe.dll"
0x180003af6  xor     edx, edx; hFile
0x180003af8  mov     ebx, 80004001h
0x180003afd  call    cs:__imp_LoadLibraryExW
0x180003b03  mov     rdi, rax
0x180003b06  test    rax, rax
0x180003b09  jz      short loc_180003B41
0x180003b0b  lea     rdx, aIesavefile; "IESaveFile"
0x180003b12  mov     rcx, rax; hModule
0x180003b15  call    cs:__imp_GetProcAddress
0x180003b1b  test    rax, rax
0x180003b1e  jz      short loc_180003B2D
0x180003b20  mov     rdx, rbp
0x180003b23  mov     rcx, rsi
0x180003b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b2b  mov     ebx, eax
0x180003b2d  mov     rcx, rdi; hLibModule
0x180003b30  call    cs:__imp_FreeLibrary
0x180003b36  test    ebx, ebx
0x180003b38  jz      short loc_180003B83
0x180003b3a  js      short loc_180003B41
0x180003b3c  mov     ebx, 80004005h
0x180003b41  mov     eax, ebx
0x180003b43  jmp     short loc_180003B85
0x180003b45  xor     r8d, r8d; dwFlags
0x180003b48  lea     rcx, LibFileName; "ieframe.dll"
0x180003b4f  xor     edx, edx; hFile
0x180003b51  mov     ebx, 80004001h
0x180003b56  call    cs:__imp_LoadLibraryExW
0x180003b5c  mov     rdi, rax
0x180003b5f  test    rax, rax
0x180003b62  jz      short loc_180003B41
0x180003b64  lea     rdx, aIecancelsavefi; "IECancelSaveFile"
0x180003b6b  mov     rcx, rax; hModule
0x180003b6e  call    cs:__imp_GetProcAddress
0x180003b74  test    rax, rax
0x180003b77  jz      short loc_180003B2D
0x180003b79  mov     rcx, rsi
0x180003b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b81  jmp     short loc_180003B2B
0x180003b83  xor     eax, eax
0x180003b85  add     rsp, 28h
0x180003b89  pop     rdi
0x180003b8a  pop     rsi
0x180003b8b  pop     rbp
0x180003b8c  pop     rbx
0x180003b8d  retn
```
