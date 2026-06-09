# CLogger::~CLogger(void)

- ea: `0x180037fa4`
- end: `0x180038012`
- name: `??1CLogger@@UEAA@XZ`
- size: `110`
- prototype: `void __fastcall(CLogger *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180038090`

## callees

- `0x180011884`
- `0x180037fa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037fbb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037fbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037fcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037fcb`

## pseudocode

```c
void __fastcall CLogger::~CLogger(CLogger *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CLogger::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v2 = (void *)*((_QWORD *)this + 6);
  if ( v2 != (void *)-1LL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 6) = -1;
  }
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 4) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 3) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 2) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 1) - 24LL));
}

```

## disassembly

```asm
0x180037fa4  push    rbx
0x180037fa6  sub     rsp, 20h
0x180037faa  lea     rax, ??_7CLogger@@6B@; const CLogger::`vftable'
0x180037fb1  mov     rbx, rcx
0x180037fb4  mov     [rcx], rax
0x180037fb7  add     rcx, 48h ; 'H'; lpCriticalSection
0x180037fbb  call    cs:__imp_DeleteCriticalSection
0x180037fc1  mov     rcx, [rbx+30h]; hObject
0x180037fc5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180037fc9  jz      short loc_180037FD9
0x180037fcb  call    cs:__imp_CloseHandle
0x180037fd1  mov     qword ptr [rbx+30h], 0FFFFFFFFFFFFFFFFh
0x180037fd9  mov     rcx, [rbx+20h]
0x180037fdd  sub     rcx, 18h; this
0x180037fe1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180037fe6  mov     rcx, [rbx+18h]
0x180037fea  sub     rcx, 18h; this
0x180037fee  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180037ff3  mov     rcx, [rbx+10h]
0x180037ff7  sub     rcx, 18h; this
0x180037ffb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180038000  mov     rcx, [rbx+8]
0x180038004  sub     rcx, 18h; this
0x180038008  add     rsp, 20h
0x18003800c  pop     rbx
0x18003800d  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
