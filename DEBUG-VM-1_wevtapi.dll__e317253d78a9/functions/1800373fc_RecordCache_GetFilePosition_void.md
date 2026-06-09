# RecordCache::GetFilePosition(void)

- ea: `0x1800373fc`
- end: `0x180037424`
- name: `?GetFilePosition@RecordCache@@QEAA_KXZ`
- size: `40`
- prototype: `unsigned __int64 __fastcall(RecordCache *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800384f8`
- `0x1800385ec`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180037414`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180037414`

## pseudocode

```c
union _LARGE_INTEGER __fastcall RecordCache::GetFilePosition(RecordCache *this)
{
  void *v1; // rcx
  union _LARGE_INTEGER NewFilePointer; // [rsp+30h] [rbp+8h] BYREF

  v1 = (void *)*((_QWORD *)this + 7);
  NewFilePointer.QuadPart = 0;
  SetFilePointerEx(v1, 0, &NewFilePointer, 1u);
  return NewFilePointer;
}

```

## disassembly

```asm
0x1800373fc  sub     rsp, 28h
0x180037400  mov     rcx, [rcx+38h]; hFile
0x180037404  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x180037409  xor     edx, edx; liDistanceToMove
0x18003740b  mov     qword ptr [rsp+28h+NewFilePointer], rdx
0x180037410  lea     r9d, [rdx+1]; dwMoveMethod
0x180037414  call    cs:__imp_SetFilePointerEx
0x18003741a  mov     rax, qword ptr [rsp+28h+NewFilePointer]
0x18003741f  add     rsp, 28h
0x180037423  retn
```
