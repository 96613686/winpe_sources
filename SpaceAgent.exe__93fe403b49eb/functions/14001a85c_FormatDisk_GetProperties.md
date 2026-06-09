# FormatDisk_GetProperties

- ea: `0x14001a85c`
- end: `0x14001a8f9`
- name: `FormatDisk_GetProperties`
- size: `157`
- prototype: `__int64 __fastcall(const WCHAR *, int *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14001a714`

## callees

- `0x14001a85c`
- `0x14001aed0`
- `0x14001b430`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14001a8a2`
- `KERNEL32!CreateFileW` at `0x14001a8a2`

## pseudocode

```c
__int64 __fastcall FormatDisk_GetProperties(const WCHAR *a1, int *a2, _DWORD *a3)
{
  HANDLE FileW; // rax
  void *v6; // rdi
  unsigned int DiskPropertiesByHandle_DiskAttributes; // ecx
  __int64 result; // rax
  int v9; // [rsp+70h] [rbp+18h] BYREF
  int v10; // [rsp+78h] [rbp+20h] BYREF

  v10 = 0;
  v9 = 1;
  FileW = CreateFileW(a1, 0x20000u, 3u, 0, 3u, 0, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    DiskPropertiesByHandle_DiskAttributes = 0;
  }
  else
  {
    DiskPropertiesByHandle_DiskAttributes = GetDiskPropertiesByHandle_DiskAttributes(FileW, &v10, &v9);
    if ( DiskPropertiesByHandle_DiskAttributes )
      DiskPropertiesByHandle_DiskAttributes = GetDiskPropertiesByHandle_WriteProtection(v6);
  }
  *a2 = v9;
  result = DiskPropertiesByHandle_DiskAttributes;
  *a3 = 1;
  return result;
}

```

## disassembly

```asm
0x14001a85c  mov     rax, rsp
0x14001a85f  mov     [rax+8], rbx
0x14001a863  push    rsi
0x14001a864  push    rdi
0x14001a865  push    r14
0x14001a867  sub     rsp, 40h
0x14001a86b  mov     ebx, 1
0x14001a870  mov     qword ptr [rax-28h], 0
0x14001a878  mov     rsi, r8
0x14001a87b  mov     dword ptr [rax-30h], 0
0x14001a882  mov     r14, rdx
0x14001a885  mov     dword ptr [rax+20h], 0
0x14001a88c  xor     r9d, r9d; lpSecurityAttributes
0x14001a88f  mov     [rax+18h], ebx
0x14001a892  lea     r8d, [rbx+2]; dwShareMode
0x14001a896  mov     [rax+10h], ebx
0x14001a899  mov     edx, 20000h; dwDesiredAccess
0x14001a89e  mov     [rax-38h], r8d
0x14001a8a2  call    cs:__imp_CreateFileW
0x14001a8a8  mov     rdi, rax
0x14001a8ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001a8af  jnz     short loc_14001A8B5
0x14001a8b1  xor     ecx, ecx
0x14001a8b3  jmp     short loc_14001A8E0
0x14001a8b5  lea     r8, [rsp+58h+arg_10]
0x14001a8ba  mov     rcx, rdi
0x14001a8bd  lea     rdx, [rsp+58h+arg_18]
0x14001a8c2  call    GetDiskPropertiesByHandle_DiskAttributes
0x14001a8c7  mov     ecx, eax
0x14001a8c9  test    eax, eax
0x14001a8cb  jz      short loc_14001A8E0
0x14001a8cd  lea     rdx, [rsp+58h+arg_8]
0x14001a8d2  mov     rcx, rdi; hDevice
0x14001a8d5  call    GetDiskPropertiesByHandle_WriteProtection
0x14001a8da  mov     ebx, [rsp+58h+arg_8]
0x14001a8de  mov     ecx, eax
0x14001a8e0  mov     eax, [rsp+58h+arg_10]
0x14001a8e4  mov     [r14], eax
0x14001a8e7  mov     eax, ecx
0x14001a8e9  mov     [rsi], ebx
0x14001a8eb  mov     rbx, [rsp+58h+arg_0]
0x14001a8f0  add     rsp, 40h
0x14001a8f4  pop     r14
0x14001a8f6  pop     rdi
0x14001a8f7  pop     rsi
0x14001a8f8  retn
```
