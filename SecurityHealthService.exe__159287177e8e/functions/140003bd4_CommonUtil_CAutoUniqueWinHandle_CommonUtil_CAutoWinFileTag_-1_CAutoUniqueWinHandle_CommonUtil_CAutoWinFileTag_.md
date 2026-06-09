# CommonUtil::CAutoUniqueWinHandle<CommonUtil::CAutoWinFileTag,-1>::~CAutoUniqueWinHandle<CommonUtil::CAutoWinFileTag,-1>(void)

- ea: `0x140003bd4`
- end: `0x140003bec`
- name: `??1?$CAutoUniqueWinHandle@UCAutoWinFileTag@CommonUtil@@$0?0@CommonUtil@@QEAA@XZ`
- size: `24`
- prototype: `BOOL __fastcall(HANDLE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400125d3`

## callees

- `0x140003bd4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140003be1`
- `KERNEL32!CloseHandle` at `0x140003be1`

## pseudocode

```c
BOOL __fastcall CommonUtil::CAutoUniqueWinHandle<CommonUtil::CAutoWinFileTag,-1>::~CAutoUniqueWinHandle<CommonUtil::CAutoWinFileTag,-1>(
        HANDLE *a1)
{
  BOOL result; // eax

  if ( *a1 != (HANDLE)-1LL )
    return CloseHandle(*a1);
  return result;
}

```

## disassembly

```asm
0x140003bd4  sub     rsp, 28h
0x140003bd8  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x140003bdc  jz      short loc_140003BE7
0x140003bde  mov     rcx, [rcx]; hObject
0x140003be1  call    cs:__imp_CloseHandle
0x140003be7  add     rsp, 28h
0x140003beb  retn
```
