# CMTACallbackThread::UnInit(void)

- ea: `0x180049b2c`
- end: `0x180049bdb`
- name: `?UnInit@CMTACallbackThread@@QEAAJXZ`
- size: `175`
- prototype: `__int64 __fastcall(CMTACallbackThread *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a64`
- `0x18003db14`

## callees

- `0x180049b2c`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180049b58`
- `KERNEL32!WaitForSingleObject` at `0x180049b58`
- `KERNEL32!CloseHandle` at `0x180049b65`
- `KERNEL32!CloseHandle` at `0x180049b9f`
- `KERNEL32!CloseHandle` at `0x180049bbc`
- `KERNEL32!CloseHandle` at `0x180049b65`
- `KERNEL32!CloseHandle` at `0x180049b9f`
- `KERNEL32!CloseHandle` at `0x180049bbc`
- `KERNEL32!SetEvent` at `0x180049b48`
- `KERNEL32!SetEvent` at `0x180049b48`
- `KERNEL32!DeleteCriticalSection` at `0x180049b86`
- `KERNEL32!DeleteCriticalSection` at `0x180049b86`

## pseudocode

```c
__int64 __fastcall CMTACallbackThread::UnInit(CMTACallbackThread *this)
{
  if ( hHandle )
  {
    dword_18007A180 |= 4u;
    SetEvent(qword_18007A1B0);
    WaitForSingleObject(hHandle, 0xFFFFFFFF);
    CloseHandle(hHandle);
    hHandle = 0;
  }
  if ( (dword_18007A180 & 2) != 0 )
  {
    DeleteCriticalSection(&stru_18007A188);
    dword_18007A180 &= ~2u;
  }
  if ( qword_18007A1B0 )
  {
    CloseHandle(qword_18007A1B0);
    qword_18007A1B0 = 0;
  }
  if ( pHandles )
  {
    CloseHandle(pHandles);
    pHandles = 0;
  }
  dword_18007A180 &= ~1u;
  return 0;
}

```

## disassembly

```asm
0x180049b2c  sub     rsp, 28h
0x180049b30  cmp     cs:hHandle, 0
0x180049b38  jz      short loc_180049B76
0x180049b3a  mov     rcx, cs:qword_18007A1B0; hEvent
0x180049b41  or      cs:dword_18007A180, 4
0x180049b48  call    cs:__imp_SetEvent
0x180049b4e  mov     rcx, cs:hHandle; hHandle
0x180049b55  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180049b58  call    cs:__imp_WaitForSingleObject
0x180049b5e  mov     rcx, cs:hHandle; hObject
0x180049b65  call    cs:__imp_CloseHandle
0x180049b6b  mov     cs:hHandle, 0
0x180049b76  test    byte ptr cs:dword_18007A180, 2
0x180049b7d  jz      short loc_180049B93
0x180049b7f  lea     rcx, stru_18007A188; lpCriticalSection
0x180049b86  call    cs:__imp_DeleteCriticalSection
0x180049b8c  and     cs:dword_18007A180, 0FFFFFFFDh
0x180049b93  mov     rcx, cs:qword_18007A1B0; hObject
0x180049b9a  test    rcx, rcx
0x180049b9d  jz      short loc_180049BB0
0x180049b9f  call    cs:__imp_CloseHandle
0x180049ba5  mov     cs:qword_18007A1B0, 0
0x180049bb0  mov     rcx, cs:pHandles; hObject
0x180049bb7  test    rcx, rcx
0x180049bba  jz      short loc_180049BCD
0x180049bbc  call    cs:__imp_CloseHandle
0x180049bc2  mov     cs:pHandles, 0
0x180049bcd  and     cs:dword_18007A180, 0FFFFFFFEh
0x180049bd4  xor     eax, eax
0x180049bd6  add     rsp, 28h
0x180049bda  retn
```
