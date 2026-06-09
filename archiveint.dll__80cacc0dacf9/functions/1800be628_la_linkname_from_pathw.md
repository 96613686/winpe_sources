# la_linkname_from_pathw

- ea: `0x1800be628`
- end: `0x1800be6b5`
- name: `la_linkname_from_pathw`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800be410`

## callees

- `0x1800149c0`
- `0x1800be480`
- `0x1800be628`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be679`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800be66a`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800be66a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be69d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be69d`

## pseudocode

```c
__int64 __fastcall la_linkname_from_pathw(__int64 a1)
{
  void *File2; // rax
  void *v2; // rdi
  DWORD LastError; // eax
  unsigned int v5; // ebx
  _DWORD v6[10]; // [rsp+30h] [rbp-28h] BYREF

  memset(v6, 0, 32);
  v6[0] = 32;
  v6[2] = 35651584;
  File2 = (void *)CreateFile2(a1, 0, 7, 3, v6);
  v2 = File2;
  if ( File2 == (void *)-1LL )
  {
    LastError = GetLastError();
    _la_dosmaperr(LastError);
    return 0xFFFFFFFFLL;
  }
  else
  {
    v5 = la_linkname_from_handle(File2);
    CloseHandle(v2);
    return v5;
  }
}

```

## disassembly

```asm
0x1800be628  mov     rax, rsp
0x1800be62b  mov     [rax+8], rbx
0x1800be62f  mov     [rax+10h], rsi
0x1800be633  push    rdi
0x1800be634  sub     rsp, 50h
0x1800be638  xorps   xmm0, xmm0
0x1800be63b  mov     rsi, rdx
0x1800be63e  xor     edx, edx
0x1800be640  mov     rbx, r8
0x1800be643  movups  xmmword ptr [rax-28h], xmm0
0x1800be647  mov     dword ptr [rax-28h], 20h ; ' '
0x1800be64e  mov     dword ptr [rax-20h], 2200000h
0x1800be655  movups  xmmword ptr [rax-18h], xmm0
0x1800be659  lea     rax, [rax-28h]
0x1800be65d  lea     r9d, [rdx+3]
0x1800be661  mov     [rsp+58h+var_38], rax
0x1800be666  lea     r8d, [rdx+7]
0x1800be66a  call    cs:__imp_CreateFile2
0x1800be670  mov     rdi, rax
0x1800be673  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800be677  jnz     short loc_1800BE68A
0x1800be679  call    cs:__imp_GetLastError
0x1800be67f  mov     ecx, eax
0x1800be681  call    __la_dosmaperr
0x1800be686  or      eax, edi
0x1800be688  jmp     short loc_1800BE6A5
0x1800be68a  mov     r8, rbx
0x1800be68d  mov     rdx, rsi
0x1800be690  mov     rcx, rdi; hDevice
0x1800be693  call    la_linkname_from_handle
0x1800be698  mov     rcx, rdi; hObject
0x1800be69b  mov     ebx, eax
0x1800be69d  call    cs:__imp_CloseHandle
0x1800be6a3  mov     eax, ebx
0x1800be6a5  mov     rbx, [rsp+58h+arg_0]
0x1800be6aa  mov     rsi, [rsp+58h+arg_8]
0x1800be6af  add     rsp, 50h
0x1800be6b3  pop     rdi
0x1800be6b4  retn
```
