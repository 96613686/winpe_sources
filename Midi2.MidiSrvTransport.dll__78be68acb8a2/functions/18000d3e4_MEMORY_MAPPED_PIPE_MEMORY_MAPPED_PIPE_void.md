# MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)

- ea: `0x18000d3e4`
- end: `0x18000d4e1`
- name: `??1MEMORY_MAPPED_PIPE@@QEAA@XZ`
- size: `253`
- prototype: `void __fastcall(MEMORY_MAPPED_PIPE *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000d190`
- `0x18000f144`
- `0x180010b10`
- `0x180012b04`

## callees

- `0x180002494`
- `0x180009014`
- `0x18000d104`
- `0x18000d3e4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d403`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d41a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d45c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d4a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d403`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d41a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d45c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d4a3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d43a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d449`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d481`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d490`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d43a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d449`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d481`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d490`

## pseudocode

```c
void __fastcall MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(MEMORY_MAPPED_PIPE *this)
{
  void *v2; // rcx
  __int64 v3; // r8
  const char *v4; // r9
  void *v5; // rcx
  __int64 v6; // r8
  const char *v7; // r9
  __int64 v8; // rdi
  const void *v9; // rcx
  const void *v10; // rcx
  __int64 v11; // rbx
  const void *v12; // rcx
  const void *v13; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  std::wstring::~wstring((char *)this + 72);
  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v3, v4);
  v5 = (void *)*((_QWORD *)this + 7);
  if ( v5 && !CloseHandle(v5) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v7);
  v8 = *((_QWORD *)this + 2);
  if ( v8 )
  {
    v9 = *(const void **)(v8 + 16);
    if ( v9 )
      UnmapViewOfFile(v9);
    v10 = *(const void **)(v8 + 8);
    if ( v10 )
      UnmapViewOfFile(v10);
    if ( (unsigned __int64)(*(_QWORD *)v8 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(*(HANDLE *)v8);
    operator delete((void *)v8);
  }
  v11 = *((_QWORD *)this + 1);
  if ( v11 )
  {
    v12 = *(const void **)(v11 + 16);
    if ( v12 )
      UnmapViewOfFile(v12);
    v13 = *(const void **)(v11 + 8);
    if ( v13 )
      UnmapViewOfFile(v13);
    if ( (unsigned __int64)(*(_QWORD *)v11 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(*(HANDLE *)v11);
    operator delete((void *)v11);
  }
}

```

## disassembly

```asm
0x18000d3e4  mov     [rsp+arg_0], rbx
0x18000d3e9  push    rdi
0x18000d3ea  sub     rsp, 20h
0x18000d3ee  mov     rbx, rcx
0x18000d3f1  add     rcx, 48h ; 'H'
0x18000d3f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d3fa  mov     rcx, [rbx+40h]; hObject
0x18000d3fe  test    rcx, rcx
0x18000d401  jz      short loc_18000D411
0x18000d403  call    cs:__imp_CloseHandle
0x18000d409  test    eax, eax
0x18000d40b  jz      loc_18000D4D1
0x18000d411  mov     rcx, [rbx+38h]; hObject
0x18000d415  test    rcx, rcx
0x18000d418  jz      short loc_18000D428
0x18000d41a  call    cs:__imp_CloseHandle
0x18000d420  test    eax, eax
0x18000d422  jz      loc_18000D4C1
0x18000d428  mov     rdi, [rbx+10h]
0x18000d42c  test    rdi, rdi
0x18000d42f  jz      short loc_18000D46F
0x18000d431  mov     rcx, [rdi+10h]; lpBaseAddress
0x18000d435  test    rcx, rcx
0x18000d438  jz      short loc_18000D440
0x18000d43a  call    cs:__imp_UnmapViewOfFile
0x18000d440  mov     rcx, [rdi+8]; lpBaseAddress
0x18000d444  test    rcx, rcx
0x18000d447  jz      short loc_18000D44F
0x18000d449  call    cs:__imp_UnmapViewOfFile
0x18000d44f  mov     rcx, [rdi]; hObject
0x18000d452  lea     rax, [rcx-1]
0x18000d456  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d45a  ja      short loc_18000D462
0x18000d45c  call    cs:__imp_CloseHandle
0x18000d462  mov     edx, 18h
0x18000d467  mov     rcx, rdi; Block
0x18000d46a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d46f  mov     rbx, [rbx+8]
0x18000d473  test    rbx, rbx
0x18000d476  jz      short loc_18000D4B6
0x18000d478  mov     rcx, [rbx+10h]; lpBaseAddress
0x18000d47c  test    rcx, rcx
0x18000d47f  jz      short loc_18000D487
0x18000d481  call    cs:__imp_UnmapViewOfFile
0x18000d487  mov     rcx, [rbx+8]; lpBaseAddress
0x18000d48b  test    rcx, rcx
0x18000d48e  jz      short loc_18000D496
0x18000d490  call    cs:__imp_UnmapViewOfFile
0x18000d496  mov     rcx, [rbx]; hObject
0x18000d499  lea     rax, [rcx-1]
0x18000d49d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d4a1  ja      short loc_18000D4A9
0x18000d4a3  call    cs:__imp_CloseHandle
0x18000d4a9  mov     edx, 18h
0x18000d4ae  mov     rcx, rbx; Block
0x18000d4b1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d4b6  mov     rbx, [rsp+28h+arg_0]
0x18000d4bb  add     rsp, 20h
0x18000d4bf  pop     rdi
0x18000d4c0  retn
0x18000d4c1  mov     rcx, [rsp+28h]; this
0x18000d4c6  mov     edx, 0A0Bh; void *
0x18000d4cb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d4d1  mov     rcx, [rsp+28h]; this
0x18000d4d6  mov     edx, 0A0Bh; void *
0x18000d4db  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
