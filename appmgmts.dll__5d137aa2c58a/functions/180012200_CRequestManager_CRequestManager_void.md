# CRequestManager::~CRequestManager(void)

- ea: `0x180012200`
- end: `0x18001222e`
- name: `??1CRequestManager@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(CRequestManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012424`

## callees

- `0x180012200`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012222`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012222`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012213`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012213`

## pseudocode

```c
void __fastcall CRequestManager::~CRequestManager(CRequestManager *this)
{
  void *v2; // rcx

  if ( *((_DWORD *)this + 14) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    CloseHandle(v2);
}

```

## disassembly

```asm
0x180012200  push    rbx
0x180012202  sub     rsp, 20h
0x180012206  cmp     dword ptr [rcx+38h], 0
0x18001220a  mov     rbx, rcx
0x18001220d  jz      short loc_180012219
0x18001220f  add     rcx, 10h; lpCriticalSection
0x180012213  call    cs:__imp_DeleteCriticalSection
0x180012219  mov     rcx, [rbx+8]; hObject
0x18001221d  test    rcx, rcx
0x180012220  jz      short loc_180012228
0x180012222  call    cs:__imp_CloseHandle
0x180012228  add     rsp, 20h
0x18001222c  pop     rbx
0x18001222d  retn
```
