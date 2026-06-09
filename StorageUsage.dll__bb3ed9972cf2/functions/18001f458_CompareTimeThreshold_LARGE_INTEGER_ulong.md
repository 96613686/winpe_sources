# CompareTimeThreshold(_LARGE_INTEGER,ulong)

- ea: `0x18001f458`
- end: `0x18001f499`
- name: `?CompareTimeThreshold@@YAJT_LARGE_INTEGER@@K@Z`
- size: `65`
- prototype: `LONG __fastcall(union _LARGE_INTEGER, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ad40`
- `0x18001d6c0`

## callees

- `0x18001f584`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001f48e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001f48e`

## pseudocode

```c
LONG __fastcall CompareTimeThreshold(union _LARGE_INTEGER a1, unsigned int a2)
{
  FILETIME FileTime2; // [rsp+30h] [rbp+8h] BYREF
  FILETIME FileTime1; // [rsp+40h] [rbp+18h] BYREF

  FileTime1 = (FILETIME)a1.QuadPart;
  FileTime2 = 0;
  CreateTimeThreshold(a2, &FileTime2);
  return CompareFileTime(&FileTime1, &FileTime2);
}

```

## disassembly

```asm
0x18001f458  sub     rsp, 28h
0x18001f45c  mov     rax, rcx
0x18001f45f  mov     [rsp+28h+FileTime1.dwLowDateTime], ecx
0x18001f463  mov     r8d, edx
0x18001f466  shr     rax, 20h
0x18001f46a  lea     rdx, [rsp+28h+FileTime2]; struct _FILETIME *
0x18001f46f  mov     [rsp+28h+FileTime1.dwHighDateTime], eax
0x18001f473  mov     ecx, r8d; unsigned int
0x18001f476  mov     qword ptr [rsp+28h+FileTime2.dwLowDateTime], 0
0x18001f47f  call    ?CreateTimeThreshold@@YAXKPEAU_FILETIME@@@Z; CreateTimeThreshold(ulong,_FILETIME *)
0x18001f484  lea     rdx, [rsp+28h+FileTime2]; lpFileTime2
0x18001f489  lea     rcx, [rsp+28h+FileTime1]; lpFileTime1
0x18001f48e  call    cs:__imp_CompareFileTime
0x18001f494  add     rsp, 28h
0x18001f498  retn
```
