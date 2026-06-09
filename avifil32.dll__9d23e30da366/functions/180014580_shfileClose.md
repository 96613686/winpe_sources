# shfileClose

- ea: `0x180014580`
- end: `0x1800145f7`
- name: `shfileClose`
- size: `119`
- prototype: `__int64 __fastcall(LPCVOID pMem)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800067a0`
- `0x18000b5c0`
- `0x18000b760`

## callees

- `0x180001048`
- `0x180014580`
- `0x18001637c`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800145d2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800145d2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800145c9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800145db`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800145c9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800145db`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800145e4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800145e4`
- `WINMM!mmioClose` at `0x1800145c0`
- `WINMM!mmioClose` at `0x1800145c0`

## pseudocode

```c
__int64 __fastcall shfileClose(LPCVOID pMem)
{
  void *v1; // rdi
  HMMIO v3; // rcx
  HGLOBAL v4; // rax
  HGLOBAL v5; // rax

  v1 = (void *)*((_QWORD *)pMem + 2);
  if ( v1 )
  {
    CFileStream::~CFileStream(*((HANDLE **)pMem + 2));
    operator delete(v1);
    *((_QWORD *)pMem + 2) = 0;
  }
  else
  {
    v3 = (HMMIO)*((_QWORD *)pMem + 1);
    if ( v3 )
      mmioClose(v3, 0);
  }
  v4 = GlobalHandle(pMem);
  GlobalUnlock(v4);
  v5 = GlobalHandle(pMem);
  GlobalFree(v5);
  return 0;
}

```

## disassembly

```asm
0x180014580  mov     [rsp+arg_0], rbx
0x180014585  push    rdi
0x180014586  sub     rsp, 20h
0x18001458a  mov     rdi, [rcx+10h]
0x18001458e  mov     rbx, rcx
0x180014591  test    rdi, rdi
0x180014594  jz      short loc_1800145B5
0x180014596  mov     rcx, rdi; this
0x180014599  call    ??1CFileStream@@QEAA@XZ; CFileStream::~CFileStream(void)
0x18001459e  mov     edx, 190h; unsigned __int64
0x1800145a3  mov     rcx, rdi; void *
0x1800145a6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800145ab  mov     qword ptr [rbx+10h], 0
0x1800145b3  jmp     short loc_1800145C6
0x1800145b5  mov     rcx, [rcx+8]; hmmio
0x1800145b9  test    rcx, rcx
0x1800145bc  jz      short loc_1800145C6
0x1800145be  xor     edx, edx; fuClose
0x1800145c0  call    cs:__imp_mmioClose
0x1800145c6  mov     rcx, rbx; pMem
0x1800145c9  call    cs:__imp_GlobalHandle
0x1800145cf  mov     rcx, rax; hMem
0x1800145d2  call    cs:__imp_GlobalUnlock
0x1800145d8  mov     rcx, rbx; pMem
0x1800145db  call    cs:__imp_GlobalHandle
0x1800145e1  mov     rcx, rax; hMem
0x1800145e4  call    cs:__imp_GlobalFree
0x1800145ea  mov     rbx, [rsp+28h+arg_0]
0x1800145ef  xor     eax, eax
0x1800145f1  add     rsp, 20h
0x1800145f5  pop     rdi
0x1800145f6  retn
```
