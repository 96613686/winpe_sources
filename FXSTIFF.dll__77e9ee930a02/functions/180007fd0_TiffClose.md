# TiffClose

- ea: `0x180007fd0`
- end: `0x180008068`
- name: `TiffClose`
- size: `152`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180004540`
- `0x180005450`
- `0x180005c30`
- `0x180005ed0`
- `0x1800066d0`
- `0x180008620`
- `0x1800094c0`
- `0x18000b120`
- `0x18000bb50`
- `0x18000d8c0`
- `0x18000eb70`

## callees

- `0x180007fd0`
- `0x18000f1c8`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x180008004`
- `KERNEL32!UnmapViewOfFile` at `0x180008004`
- `KERNEL32!VirtualFree` at `0x180007fed`
- `KERNEL32!VirtualFree` at `0x180007fed`
- `KERNEL32!CloseHandle` at `0x180008014`
- `KERNEL32!CloseHandle` at `0x18000802b`
- `KERNEL32!CloseHandle` at `0x180008014`
- `KERNEL32!CloseHandle` at `0x18000802b`

## pseudocode

```c
__int64 __fastcall TiffClose(LPVOID lpMem)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)lpMem + 192);
  if ( v2 )
    VirtualFree(v2, 0, 0x8000u);
  if ( *((_QWORD *)lpMem + 1) )
  {
    UnmapViewOfFile(*((LPCVOID *)lpMem + 2));
    CloseHandle(*((HANDLE *)lpMem + 1));
  }
  else if ( *(_QWORD *)lpMem == -1 )
  {
    goto LABEL_7;
  }
  CloseHandle(*(HANDLE *)lpMem);
LABEL_7:
  v3 = (void *)*((_QWORD *)lpMem + 4);
  if ( v3 )
  {
    pMemFree(v3);
    *((_QWORD *)lpMem + 4) = 0;
    *((_DWORD *)lpMem + 10) = 0;
  }
  pMemFree(lpMem);
  return 1;
}

```

## disassembly

```asm
0x180007fd0  push    rbx
0x180007fd2  sub     rsp, 20h
0x180007fd6  mov     rbx, rcx
0x180007fd9  mov     rcx, [rcx+600h]; lpAddress
0x180007fe0  test    rcx, rcx
0x180007fe3  jz      short loc_180007FF9
0x180007fe5  xor     edx, edx; dwSize
0x180007fe7  mov     r8d, 8000h; dwFreeType
0x180007fed  call    cs:__imp_VirtualFree
0x180007ff4  nop     dword ptr [rax+rax+00h]
0x180007ff9  cmp     qword ptr [rbx+8], 0
0x180007ffe  jz      short loc_180008022
0x180008000  mov     rcx, [rbx+10h]; lpBaseAddress
0x180008004  call    cs:__imp_UnmapViewOfFile
0x18000800b  nop     dword ptr [rax+rax+00h]
0x180008010  mov     rcx, [rbx+8]; hObject
0x180008014  call    cs:__imp_CloseHandle
0x18000801b  nop     dword ptr [rax+rax+00h]
0x180008020  jmp     short loc_180008028
0x180008022  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180008026  jz      short loc_180008037
0x180008028  mov     rcx, [rbx]; hObject
0x18000802b  call    cs:__imp_CloseHandle
0x180008032  nop     dword ptr [rax+rax+00h]
0x180008037  mov     rcx, [rbx+20h]; lpMem
0x18000803b  test    rcx, rcx
0x18000803e  jz      short loc_180008054
0x180008040  call    pMemFree
0x180008045  mov     qword ptr [rbx+20h], 0
0x18000804d  mov     dword ptr [rbx+28h], 0
0x180008054  mov     rcx, rbx; lpMem
0x180008057  call    pMemFree
0x18000805c  mov     eax, 1
0x180008061  add     rsp, 20h
0x180008065  pop     rbx
0x180008066  retn
```
