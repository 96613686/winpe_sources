# sub_1800D8CBC

- ea: `0x1800d8cbc`
- end: `0x1800d8da5`
- name: `sub_1800D8CBC`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800d8da8`
- `0x1800d8ef4`

## callees

- `0x1800063e0`
- `0x18002aefc`
- `0x1800d8cbc`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1800d8d5b`
- `KERNEL32!GetFileAttributesW` at `0x1800d8d5b`
- `KERNEL32!LoadLibraryExW` at `0x1800d8cff`
- `KERNEL32!LoadLibraryExW` at `0x1800d8cff`
- `KERNEL32!GetLastError` at `0x1800d8d0a`
- `KERNEL32!GetLastError` at `0x1800d8d4f`
- `KERNEL32!GetLastError` at `0x1800d8d6d`
- `KERNEL32!GetLastError` at `0x1800d8d0a`
- `KERNEL32!GetLastError` at `0x1800d8d4f`
- `KERNEL32!GetLastError` at `0x1800d8d6d`

## pseudocode

```c
__int64 __fastcall sub_1800D8CBC(__int64 a1, const WCHAR *a2, char a3)
{
  DWORD LastError; // esi
  unsigned int i; // edi
  HMODULE Library; // rax
  DWORD FileAttributesW; // eax
  __int64 v11; // [rsp+58h] [rbp+20h] BYREF

  LastError = 0;
  for ( i = 0; i <= 0x19; ++i )
  {
    if ( !*a2 )
      __fastfail(5u);
    Library = LoadLibraryExW(a2, 0, 0x1000u);
    if ( Library )
    {
      *(_QWORD *)a1 = Library;
      *(_DWORD *)(a1 + 8) = i;
      *(_DWORD *)(a1 + 12) = LastError;
      *(_BYTE *)(a1 + 48) = 1;
      return a1;
    }
    LastError = GetLastError();
    if ( LastError == 1114 )
      __fastfail(7u);
    if ( !a3 )
      break;
    v11 = 10LL * i;
    sub_18002AEFC(&v11);
  }
  sub_1800063E0(a1, a2);
  *(_DWORD *)(a1 + 32) = GetLastError();
  FileAttributesW = GetFileAttributesW(a2);
  *(_DWORD *)(a1 + 36) = FileAttributesW;
  *(_DWORD *)(a1 + 40) = 0;
  if ( FileAttributesW == -1 )
    *(_DWORD *)(a1 + 40) = GetLastError();
  *(_BYTE *)(a1 + 48) = 0;
  return a1;
}

```

## disassembly

```asm
0x1800d8cbc  mov     [rsp+arg_0], rbx
0x1800d8cc1  mov     [rsp+arg_8], rbp
0x1800d8cc6  mov     [rsp+arg_10], rsi
0x1800d8ccb  push    rdi
0x1800d8ccc  push    r14
0x1800d8cce  push    r15
0x1800d8cd0  sub     rsp, 20h
0x1800d8cd4  mov     r14b, r8b
0x1800d8cd7  mov     rbp, rdx
0x1800d8cda  mov     rbx, rcx
0x1800d8cdd  xor     r15d, r15d
0x1800d8ce0  mov     esi, r15d
0x1800d8ce3  mov     edi, r15d
0x1800d8ce6  cmp     [rbp+0], r15w
0x1800d8ceb  jnz     short loc_1800D8CF4
0x1800d8ced  mov     ecx, 5
0x1800d8cf2  int     29h; Win8: RtlFailFast(ecx)
0x1800d8cf4  xor     edx, edx; hFile
0x1800d8cf6  mov     r8d, 1000h; dwFlags
0x1800d8cfc  mov     rcx, rbp; lpLibFileName
0x1800d8cff  call    cs:LoadLibraryExW
0x1800d8d05  test    rax, rax
0x1800d8d08  jnz     short loc_1800D8D7C
0x1800d8d0a  call    cs:GetLastError
0x1800d8d10  mov     esi, eax
0x1800d8d12  cmp     eax, 45Ah
0x1800d8d17  jnz     short loc_1800D8D20
0x1800d8d19  mov     ecx, 7
0x1800d8d1e  int     29h; Win8: RtlFailFast(ecx)
0x1800d8d20  test    r14b, r14b
0x1800d8d23  jz      short loc_1800D8D44
0x1800d8d25  mov     ecx, edi
0x1800d8d27  lea     rdx, [rcx+rcx*4]
0x1800d8d2b  add     rdx, rdx
0x1800d8d2e  mov     [rsp+38h+arg_18], rdx
0x1800d8d33  lea     rcx, [rsp+38h+arg_18]
0x1800d8d38  call    sub_18002AEFC
0x1800d8d3d  inc     edi
0x1800d8d3f  cmp     edi, 19h
0x1800d8d42  jbe     short loc_1800D8CE6
0x1800d8d44  mov     rdx, rbp
0x1800d8d47  mov     rcx, rbx
0x1800d8d4a  call    sub_1800063E0
0x1800d8d4f  call    cs:GetLastError
0x1800d8d55  mov     [rbx+20h], eax
0x1800d8d58  mov     rcx, rbp; lpFileName
0x1800d8d5b  call    cs:GetFileAttributesW
0x1800d8d61  mov     [rbx+24h], eax
0x1800d8d64  mov     [rbx+28h], r15d
0x1800d8d68  cmp     eax, 0FFFFFFFFh
0x1800d8d6b  jnz     short loc_1800D8D76
0x1800d8d6d  call    cs:GetLastError
0x1800d8d73  mov     [rbx+28h], eax
0x1800d8d76  mov     [rbx+30h], r15b
0x1800d8d7a  jmp     short loc_1800D8D89
0x1800d8d7c  mov     [rbx], rax
0x1800d8d7f  mov     [rbx+8], edi
0x1800d8d82  mov     [rbx+0Ch], esi
0x1800d8d85  mov     byte ptr [rbx+30h], 1
0x1800d8d89  mov     rax, rbx
0x1800d8d8c  mov     rbx, [rsp+38h+arg_0]
0x1800d8d91  mov     rbp, [rsp+38h+arg_8]
0x1800d8d96  mov     rsi, [rsp+38h+arg_10]
0x1800d8d9b  add     rsp, 20h
0x1800d8d9f  pop     r15
0x1800d8da1  pop     r14
0x1800d8da3  pop     rdi
0x1800d8da4  retn
```
