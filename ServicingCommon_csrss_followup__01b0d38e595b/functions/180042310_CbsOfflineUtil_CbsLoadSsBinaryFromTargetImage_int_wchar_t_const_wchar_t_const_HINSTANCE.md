# CbsOfflineUtil::CbsLoadSsBinaryFromTargetImage(int,wchar_t const *,wchar_t const *,HINSTANCE__ * *)

- ea: `0x180042310`
- end: `0x1800423d2`
- name: `?CbsLoadSsBinaryFromTargetImage@CbsOfflineUtil@@UEAAJHPEB_W0PEAPEAUHINSTANCE__@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(CbsOfflineUtil *__hidden this, int, const wchar_t *, const wchar_t *, HINSTANCE *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18002d2b0`
- `0x180042310`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004236f`
- `KERNEL32!GetLastError` at `0x18004236f`
- `KERNEL32!LoadLibraryExW` at `0x18004235e`
- `KERNEL32!LoadLibraryExW` at `0x18004235e`
- `KERNEL32!GetProcessHeap` at `0x18004239b`
- `KERNEL32!GetProcessHeap` at `0x18004239b`
- `KERNEL32!HeapFree` at `0x1800423af`
- `KERNEL32!HeapFree` at `0x1800423af`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CbsLoadSsBinaryFromTargetImage(
        CbsOfflineUtil *this,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        HINSTANCE *a5)
{
  __int64 v5; // rax
  signed int v6; // ebx
  HMODULE Library; // rax
  signed int LastError; // eax
  WCHAR *v9; // rdi
  HANDLE ProcessHeap; // rax
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp-28h] BYREF

  v5 = *(_QWORD *)this;
  lpLibFileName = 0;
  v6 = (*(__int64 (__fastcall **)(CbsOfflineUtil *, __int64, const wchar_t *, const wchar_t *, LPCWSTR *))(v5 + 56))(
         this,
         a2,
         a3,
         a4,
         &lpLibFileName);
  if ( v6 >= 0 )
  {
    Library = LoadLibraryExW(lpLibFileName, 0, 8u);
    if ( Library )
    {
      *a5 = Library;
      v6 = 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  v9 = (WCHAR *)lpLibFileName;
  if ( lpLibFileName )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180042310  push    rbx
0x180042312  push    rdi
0x180042313  sub     rsp, 48h
0x180042317  mov     rax, cs:__security_cookie
0x18004231e  xor     rax, rsp
0x180042321  mov     [rsp+58h+var_20], rax
0x180042326  mov     rax, [rcx]
0x180042329  lea     r10, [rsp+58h+lpLibFileName]
0x18004232e  mov     rdi, [rsp+58h+arg_20]
0x180042336  mov     [rsp+58h+lpLibFileName], 0
0x18004233f  mov     [rsp+58h+var_38], r10
0x180042344  mov     rax, [rax+38h]
0x180042348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004234d  mov     ebx, eax
0x18004234f  test    eax, eax
0x180042351  js      short loc_180042391
0x180042353  mov     rcx, [rsp+58h+lpLibFileName]; lpLibFileName
0x180042358  xor     edx, edx; hFile
0x18004235a  lea     r8d, [rdx+8]; dwFlags
0x18004235e  call    cs:__imp_LoadLibraryExW
0x180042365  nop     dword ptr [rax+rax+00h]
0x18004236a  test    rax, rax
0x18004236d  jnz     short loc_18004238C
0x18004236f  call    cs:__imp_GetLastError
0x180042376  nop     dword ptr [rax+rax+00h]
0x18004237b  mov     ebx, eax
0x18004237d  test    eax, eax
0x18004237f  jle     short loc_180042391
0x180042381  movzx   ebx, ax
0x180042384  or      ebx, 80070000h
0x18004238a  jmp     short loc_180042391
0x18004238c  mov     [rdi], rax
0x18004238f  xor     ebx, ebx
0x180042391  mov     rdi, [rsp+58h+lpLibFileName]
0x180042396  test    rdi, rdi
0x180042399  jz      short loc_1800423BB
0x18004239b  call    cs:__imp_GetProcessHeap
0x1800423a2  nop     dword ptr [rax+rax+00h]
0x1800423a7  mov     r8, rdi; lpMem
0x1800423aa  xor     edx, edx; dwFlags
0x1800423ac  mov     rcx, rax; hHeap
0x1800423af  call    cs:__imp_HeapFree
0x1800423b6  nop     dword ptr [rax+rax+00h]
0x1800423bb  mov     eax, ebx
0x1800423bd  mov     rcx, [rsp+58h+var_20]
0x1800423c2  xor     rcx, rsp; StackCookie
0x1800423c5  call    __security_check_cookie
0x1800423ca  add     rsp, 48h
0x1800423ce  pop     rdi
0x1800423cf  pop     rbx
0x1800423d0  retn
```
