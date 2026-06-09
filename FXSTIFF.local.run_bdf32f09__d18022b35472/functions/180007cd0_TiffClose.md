# TiffClose

- ea: `0x180007cd0`
- end: `0x180007d4f`
- name: `TiffClose`
- size: `127`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x1800044f0`
- `0x180005380`
- `0x180005b00`
- `0x180005d80`
- `0x180006530`
- `0x1800082c0`
- `0x180009070`
- `0x18000ac38`
- `0x18000b604`
- `0x18000d310`
- `0x18000e530`

## callees

- `0x180007cd0`
- `0x18000eac0`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x180007cfe`
- `KERNEL32!UnmapViewOfFile` at `0x180007cfe`
- `KERNEL32!VirtualFree` at `0x180007ced`
- `KERNEL32!VirtualFree` at `0x180007ced`
- `KERNEL32!CloseHandle` at `0x180007d08`
- `KERNEL32!CloseHandle` at `0x180007d19`
- `KERNEL32!CloseHandle` at `0x180007d08`
- `KERNEL32!CloseHandle` at `0x180007d19`

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
0x180007cd0  push    rbx
0x180007cd2  sub     rsp, 20h
0x180007cd6  mov     rbx, rcx
0x180007cd9  mov     rcx, [rcx+600h]; lpAddress
0x180007ce0  test    rcx, rcx
0x180007ce3  jz      short loc_180007CF3
0x180007ce5  xor     edx, edx; dwSize
0x180007ce7  mov     r8d, 8000h; dwFreeType
0x180007ced  call    cs:__imp_VirtualFree
0x180007cf3  cmp     qword ptr [rbx+8], 0
0x180007cf8  jz      short loc_180007D10
0x180007cfa  mov     rcx, [rbx+10h]; lpBaseAddress
0x180007cfe  call    cs:__imp_UnmapViewOfFile
0x180007d04  mov     rcx, [rbx+8]; hObject
0x180007d08  call    cs:__imp_CloseHandle
0x180007d0e  jmp     short loc_180007D16
0x180007d10  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180007d14  jz      short loc_180007D1F
0x180007d16  mov     rcx, [rbx]; hObject
0x180007d19  call    cs:__imp_CloseHandle
0x180007d1f  mov     rcx, [rbx+20h]; lpMem
0x180007d23  test    rcx, rcx
0x180007d26  jz      short loc_180007D3C
0x180007d28  call    pMemFree
0x180007d2d  mov     qword ptr [rbx+20h], 0
0x180007d35  mov     dword ptr [rbx+28h], 0
0x180007d3c  mov     rcx, rbx; lpMem
0x180007d3f  call    pMemFree
0x180007d44  mov     eax, 1
0x180007d49  add     rsp, 20h
0x180007d4d  pop     rbx
0x180007d4e  retn
```
