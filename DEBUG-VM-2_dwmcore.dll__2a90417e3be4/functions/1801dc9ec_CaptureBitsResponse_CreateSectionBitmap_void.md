# CaptureBitsResponse::CreateSectionBitmap(void)

- ea: `0x1801dc9ec`
- end: `0x1801dcaa1`
- name: `?CreateSectionBitmap@CaptureBitsResponse@@IEAAJXZ`
- size: `181`
- prototype: `__int64 __fastcall(CaptureBitsResponse *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x1801dc920`

## callees

- `0x18000b834`
- `0x180042de0`
- `0x1801dc9ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801dca06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801dca06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dca3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dca3e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1801dca2c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1801dca2c`

## pseudocode

```c
__int64 __fastcall CaptureBitsResponse::CreateSectionBitmap(DWORD *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  HANDLE FileMappingW; // rax
  signed int LastError; // eax
  int v6; // r9d
  DWORD dwMaximumSizeLow; // [rsp+20h] [rbp-18h]

  v2 = CaptureBitsResponse::CalcSectionBitmapSize((CaptureBitsResponse *)this);
  v3 = v2;
  if ( v2 < 0 )
  {
    v6 = v2;
    dwMaximumSizeLow = 228;
LABEL_9:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v6, dwMaximumSizeLow, 0);
    return v3;
  }
  SetLastError(0);
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, this[376], 0);
  *((_QWORD *)this + 186) = FileMappingW;
  if ( !FileMappingW )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    dwMaximumSizeLow = 236;
    if ( (v3 & 0x80000000) == 0 )
      v3 = -2003304445;
    v6 = v3;
    goto LABEL_9;
  }
  return v3;
}

```

## disassembly

```asm
0x1801dc9ec  mov     [rsp+arg_0], rbx
0x1801dc9f1  push    rdi
0x1801dc9f2  sub     rsp, 30h
0x1801dc9f6  mov     rdi, rcx
0x1801dc9f9  call    ?CalcSectionBitmapSize@CaptureBitsResponse@@IEAAJXZ; CaptureBitsResponse::CalcSectionBitmapSize(void)
0x1801dc9fe  mov     ebx, eax
0x1801dca00  test    eax, eax
0x1801dca02  js      short loc_1801DCA73
0x1801dca04  xor     ecx, ecx; dwErrCode
0x1801dca06  call    cs:__imp_SetLastError
0x1801dca0c  mov     edx, [rdi+5E0h]
0x1801dca12  xor     r9d, r9d; dwMaximumSizeHigh
0x1801dca15  mov     [rsp+38h+lpName], 0; lpName
0x1801dca1e  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1801dca22  mov     [rsp+38h+dwMaximumSizeLow], edx; dwMaximumSizeLow
0x1801dca26  xor     edx, edx; lpFileMappingAttributes
0x1801dca28  lea     r8d, [r9+4]; flProtect
0x1801dca2c  call    cs:__imp_CreateFileMappingW
0x1801dca32  mov     [rdi+5D0h], rax
0x1801dca39  test    rax, rax
0x1801dca3c  jnz     short loc_1801DCA94
0x1801dca3e  call    cs:__imp_GetLastError
0x1801dca44  mov     ebx, eax
0x1801dca46  test    eax, eax
0x1801dca48  jle     short loc_1801DCA53
0x1801dca4a  movzx   ebx, ax
0x1801dca4d  or      ebx, 80070000h
0x1801dca53  test    ebx, ebx
0x1801dca55  mov     [rsp+38h+lpName], 0
0x1801dca5e  mov     eax, 88980003h
0x1801dca63  mov     [rsp+38h+dwMaximumSizeLow], 0ECh
0x1801dca6b  cmovns  ebx, eax
0x1801dca6e  mov     r9d, ebx
0x1801dca71  jmp     short loc_1801DCA87
0x1801dca73  mov     [rsp+38h+lpName], 0; void *
0x1801dca7c  mov     r9d, eax; int
0x1801dca7f  mov     [rsp+38h+dwMaximumSizeLow], 0E4h; unsigned int
0x1801dca87  xor     edx, edx; int *
0x1801dca89  xor     r8d, r8d; unsigned int
0x1801dca8c  lea     ecx, [rdx+14h]; unsigned int
0x1801dca8f  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801dca94  mov     eax, ebx
0x1801dca96  mov     rbx, [rsp+38h+arg_0]
0x1801dca9b  add     rsp, 30h
0x1801dca9f  pop     rdi
0x1801dcaa0  retn
```
