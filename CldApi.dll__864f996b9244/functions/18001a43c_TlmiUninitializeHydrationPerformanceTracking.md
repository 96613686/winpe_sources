# TlmiUninitializeHydrationPerformanceTracking

- ea: `0x18001a43c`
- end: `0x18001a4bd`
- name: `TlmiUninitializeHydrationPerformanceTracking`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001101c`
- `0x180018b98`

## callees

- `0x18001a43c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a447`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a447`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a4b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a459`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a476`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a493`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a459`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a476`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a493`

## pseudocode

```c
__int64 TlmiUninitializeHydrationPerformanceTracking()
{
  RtlAcquireSRWLockExclusive(&qword_180028A60);
  if ( hEvent )
  {
    CloseHandle(hEvent);
    hEvent = 0;
  }
  if ( qword_180028B50 )
  {
    CloseHandle(qword_180028B50);
    qword_180028B50 = 0;
  }
  if ( qword_180028B58 )
  {
    CloseHandle(qword_180028B58);
    qword_180028B58 = 0;
  }
  byte_180028A58 = 0;
  return RtlReleaseSRWLockExclusive(&qword_180028A60);
}

```

## disassembly

```asm
0x18001a43c  sub     rsp, 28h
0x18001a440  lea     rcx, qword_180028A60
0x18001a447  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001a44d  mov     rcx, cs:hEvent; hObject
0x18001a454  test    rcx, rcx
0x18001a457  jz      short loc_18001A46A
0x18001a459  call    cs:__imp_CloseHandle
0x18001a45f  mov     cs:hEvent, 0
0x18001a46a  mov     rcx, cs:qword_180028B50; hObject
0x18001a471  test    rcx, rcx
0x18001a474  jz      short loc_18001A487
0x18001a476  call    cs:__imp_CloseHandle
0x18001a47c  mov     cs:qword_180028B50, 0
0x18001a487  mov     rcx, cs:qword_180028B58; hObject
0x18001a48e  test    rcx, rcx
0x18001a491  jz      short loc_18001A4A4
0x18001a493  call    cs:__imp_CloseHandle
0x18001a499  mov     cs:qword_180028B58, 0
0x18001a4a4  lea     rcx, qword_180028A60
0x18001a4ab  mov     cs:byte_180028A58, 0
0x18001a4b2  add     rsp, 28h
0x18001a4b6  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
