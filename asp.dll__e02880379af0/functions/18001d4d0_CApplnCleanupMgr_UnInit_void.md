# CApplnCleanupMgr::UnInit(void)

- ea: `0x18001d4d0`
- end: `0x18001d56a`
- name: `?UnInit@CApplnCleanupMgr@@QEAAJXZ`
- size: `154`
- prototype: `__int64 __fastcall(CApplnCleanupMgr *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180024470`
- `0x180032c9c`

## callees

- `0x18001d4d0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001d519`
- `KERNEL32!WaitForSingleObject` at `0x18001d519`
- `KERNEL32!CloseHandle` at `0x18001d4fc`
- `KERNEL32!CloseHandle` at `0x18001d53d`
- `KERNEL32!CloseHandle` at `0x18001d4fc`
- `KERNEL32!CloseHandle` at `0x18001d53d`
- `KERNEL32!SetEvent` at `0x18001d4ef`
- `KERNEL32!SetEvent` at `0x18001d4ef`
- `KERNEL32!DeleteCriticalSection` at `0x18001d554`
- `KERNEL32!DeleteCriticalSection` at `0x18001d554`
- `KERNEL32!GetLastError` at `0x18001d524`
- `KERNEL32!GetLastError` at `0x18001d524`

## pseudocode

```c
__int64 __fastcall CApplnCleanupMgr::UnInit(CApplnCleanupMgr *this)
{
  void *v2; // rcx
  unsigned int v3; // edi
  void *v4; // rcx
  signed int LastError; // eax

  *(_DWORD *)this &= ~1u;
  v2 = (void *)*((_QWORD *)this + 40);
  v3 = 0;
  if ( v2 != (void *)-1LL )
  {
    SetEvent(v2);
    CloseHandle(*((HANDLE *)this + 40));
    *((_QWORD *)this + 40) = -1;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    if ( WaitForSingleObject(v4, 0xFFFFFFFF) == -1 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(*((HANDLE *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  if ( (*(_BYTE *)this & 2) != 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    *(_DWORD *)this &= ~2u;
  }
  return v3;
}

```

## disassembly

```asm
0x18001d4d0  mov     [rsp+arg_0], rbx
0x18001d4d5  push    rdi
0x18001d4d6  sub     rsp, 20h
0x18001d4da  and     dword ptr [rcx], 0FFFFFFFEh
0x18001d4dd  mov     rbx, rcx
0x18001d4e0  mov     rcx, [rcx+140h]; hEvent
0x18001d4e7  xor     edi, edi
0x18001d4e9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d4ed  jz      short loc_18001D50D
0x18001d4ef  call    cs:__imp_SetEvent
0x18001d4f5  mov     rcx, [rbx+140h]; hObject
0x18001d4fc  call    cs:__imp_CloseHandle
0x18001d502  mov     qword ptr [rbx+140h], 0FFFFFFFFFFFFFFFFh
0x18001d50d  mov     rcx, [rbx+8]; hHandle
0x18001d511  test    rcx, rcx
0x18001d514  jz      short loc_18001D54B
0x18001d516  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001d519  call    cs:__imp_WaitForSingleObject
0x18001d51f  cmp     eax, 0FFFFFFFFh
0x18001d522  jnz     short loc_18001D539
0x18001d524  call    cs:__imp_GetLastError
0x18001d52a  mov     edi, eax
0x18001d52c  test    eax, eax
0x18001d52e  jle     short loc_18001D539
0x18001d530  movzx   edi, ax
0x18001d533  or      edi, 80070000h
0x18001d539  mov     rcx, [rbx+8]; hObject
0x18001d53d  call    cs:__imp_CloseHandle
0x18001d543  mov     qword ptr [rbx+8], 0
0x18001d54b  test    byte ptr [rbx], 2
0x18001d54e  jz      short loc_18001D55D
0x18001d550  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001d554  call    cs:__imp_DeleteCriticalSection
0x18001d55a  and     dword ptr [rbx], 0FFFFFFFDh
0x18001d55d  mov     rbx, [rsp+28h+arg_0]
0x18001d562  mov     eax, edi
0x18001d564  add     rsp, 20h
0x18001d568  pop     rdi
0x18001d569  retn
```
