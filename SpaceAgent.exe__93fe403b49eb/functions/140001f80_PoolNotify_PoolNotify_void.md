# PoolNotify::~PoolNotify(void)

- ea: `0x140001f80`
- end: `0x140001ff7`
- name: `??1PoolNotify@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(PoolNotify *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002868`

## callees

- `0x140001f80`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140001fcd`
- `KERNEL32!DeleteCriticalSection` at `0x140001fcd`
- `KERNEL32!CloseHandle` at `0x140001fdc`
- `KERNEL32!CloseHandle` at `0x140001feb`
- `KERNEL32!CloseHandle` at `0x140001fdc`
- `KERNEL32!CloseHandle` at `0x140001feb`
- `KERNEL32!WaitForSingleObject` at `0x140001faf`
- `KERNEL32!WaitForSingleObject` at `0x140001faf`
- `USER32!PostThreadMessageW` at `0x140001fa2`
- `USER32!PostThreadMessageW` at `0x140001fa2`

## pseudocode

```c
void __fastcall PoolNotify::~PoolNotify(PoolNotify *this)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( *((_DWORD *)this + 8) && *((_QWORD *)this + 1) )
  {
    PostThreadMessageW(*(_DWORD *)this, 0x12u, 0, 0);
    WaitForSingleObject(*((HANDLE *)this + 1), 0xFFFFFFFF);
    *((_QWORD *)this + 1) = 0;
    *(_DWORD *)this = 0;
  }
  if ( *((_DWORD *)this + 20) )
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    CloseHandle(v3);
}

```

## disassembly

```asm
0x140001f80  push    rbx
0x140001f82  sub     rsp, 20h
0x140001f86  cmp     dword ptr [rcx+20h], 0
0x140001f8a  mov     rbx, rcx
0x140001f8d  jz      short loc_140001FC3
0x140001f8f  cmp     qword ptr [rcx+8], 0
0x140001f94  jz      short loc_140001FC3
0x140001f96  mov     ecx, [rcx]; idThread
0x140001f98  xor     r9d, r9d; lParam
0x140001f9b  xor     r8d, r8d; wParam
0x140001f9e  lea     edx, [r9+12h]; Msg
0x140001fa2  call    cs:__imp_PostThreadMessageW
0x140001fa8  mov     rcx, [rbx+8]; hHandle
0x140001fac  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140001faf  call    cs:__imp_WaitForSingleObject
0x140001fb5  mov     qword ptr [rbx+8], 0
0x140001fbd  mov     dword ptr [rbx], 0
0x140001fc3  cmp     dword ptr [rbx+50h], 0
0x140001fc7  jz      short loc_140001FD3
0x140001fc9  lea     rcx, [rbx+28h]; lpCriticalSection
0x140001fcd  call    cs:__imp_DeleteCriticalSection
0x140001fd3  mov     rcx, [rbx+10h]; hObject
0x140001fd7  test    rcx, rcx
0x140001fda  jz      short loc_140001FE2
0x140001fdc  call    cs:__imp_CloseHandle
0x140001fe2  mov     rcx, [rbx+18h]; hObject
0x140001fe6  test    rcx, rcx
0x140001fe9  jz      short loc_140001FF1
0x140001feb  call    cs:__imp_CloseHandle
0x140001ff1  add     rsp, 20h
0x140001ff5  pop     rbx
0x140001ff6  retn
```
