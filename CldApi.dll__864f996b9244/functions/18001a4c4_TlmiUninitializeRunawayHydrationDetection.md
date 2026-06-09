# TlmiUninitializeRunawayHydrationDetection

- ea: `0x18001a4c4`
- end: `0x18001a545`
- name: `TlmiUninitializeRunawayHydrationDetection`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001101c`
- `0x180018e24`

## callees

- `0x18001a4c4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a4cf`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a4cf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a53e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a4e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a4fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a51b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a4e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a4fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a51b`

## pseudocode

```c
__int64 TlmiUninitializeRunawayHydrationDetection()
{
  RtlAcquireSRWLockExclusive(&qword_1800289B8);
  if ( qword_180028A40 )
  {
    CloseHandle(qword_180028A40);
    qword_180028A40 = 0;
  }
  if ( qword_180028A48 )
  {
    CloseHandle(qword_180028A48);
    qword_180028A48 = 0;
  }
  if ( qword_180028A50 )
  {
    CloseHandle(qword_180028A50);
    qword_180028A50 = 0;
  }
  byte_1800289B0 = 0;
  return RtlReleaseSRWLockExclusive(&qword_1800289B8);
}

```

## disassembly

```asm
0x18001a4c4  sub     rsp, 28h
0x18001a4c8  lea     rcx, qword_1800289B8
0x18001a4cf  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001a4d5  mov     rcx, cs:qword_180028A40; hObject
0x18001a4dc  test    rcx, rcx
0x18001a4df  jz      short loc_18001A4F2
0x18001a4e1  call    cs:__imp_CloseHandle
0x18001a4e7  mov     cs:qword_180028A40, 0
0x18001a4f2  mov     rcx, cs:qword_180028A48; hObject
0x18001a4f9  test    rcx, rcx
0x18001a4fc  jz      short loc_18001A50F
0x18001a4fe  call    cs:__imp_CloseHandle
0x18001a504  mov     cs:qword_180028A48, 0
0x18001a50f  mov     rcx, cs:qword_180028A50; hObject
0x18001a516  test    rcx, rcx
0x18001a519  jz      short loc_18001A52C
0x18001a51b  call    cs:__imp_CloseHandle
0x18001a521  mov     cs:qword_180028A50, 0
0x18001a52c  lea     rcx, qword_1800289B8
0x18001a533  mov     cs:byte_1800289B0, 0
0x18001a53a  add     rsp, 28h
0x18001a53e  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
