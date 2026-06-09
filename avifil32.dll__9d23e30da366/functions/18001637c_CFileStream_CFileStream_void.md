# CFileStream::~CFileStream(void)

- ea: `0x18001637c`
- end: `0x1800163ce`
- name: `??1CFileStream@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(CFileStream *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014580`
- `0x180014744`
- `0x1800148c4`

## callees

- `0x180016370`
- `0x18001637c`
- `0x180016498`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001639f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001639f`

## pseudocode

```c
void __fastcall CFileStream::~CFileStream(HANDLE *this)
{
  __int64 v2; // rdi
  CFileBuffer *v3; // rbx

  if ( this[48] != (HANDLE)-1LL )
  {
    CFileStream::CommitAndWait((CFileStream *)this);
    CloseHandle(this[48]);
  }
  v2 = 4;
  v3 = (CFileBuffer *)(this + 45);
  do
  {
    v3 = (CFileBuffer *)((char *)v3 - 88);
    CFileBuffer::~CFileBuffer(v3);
    --v2;
  }
  while ( v2 );
}

```

## disassembly

```asm
0x18001637c  mov     [rsp+arg_0], rbx
0x180016381  push    rdi
0x180016382  sub     rsp, 20h
0x180016386  cmp     qword ptr [rcx+180h], 0FFFFFFFFFFFFFFFFh
0x18001638e  mov     rbx, rcx
0x180016391  jz      short loc_1800163A5
0x180016393  call    ?CommitAndWait@CFileStream@@QEAAHXZ; CFileStream::CommitAndWait(void)
0x180016398  mov     rcx, [rbx+180h]; hObject
0x18001639f  call    cs:__imp_CloseHandle
0x1800163a5  mov     edi, 4
0x1800163aa  add     rbx, 168h
0x1800163b1  sub     rbx, 58h ; 'X'
0x1800163b5  mov     rcx, rbx; this
0x1800163b8  call    ??1CFileBuffer@@QEAA@XZ; CFileBuffer::~CFileBuffer(void)
0x1800163bd  sub     rdi, 1
0x1800163c1  jnz     short loc_1800163B1
0x1800163c3  mov     rbx, [rsp+28h+arg_0]
0x1800163c8  add     rsp, 20h
0x1800163cc  pop     rdi
0x1800163cd  retn
```
