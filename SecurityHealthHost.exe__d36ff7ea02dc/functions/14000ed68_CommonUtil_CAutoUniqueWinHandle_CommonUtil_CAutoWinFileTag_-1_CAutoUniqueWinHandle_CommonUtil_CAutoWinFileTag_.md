# CommonUtil::CAutoUniqueWinHandle<CommonUtil::CAutoWinFileTag,-1>::~CAutoUniqueWinHandle<CommonUtil::CAutoWinFileTag,-1>(void)

- ea: `0x14000ed68`
- end: `0x14000ed80`
- name: `??1?$CAutoUniqueWinHandle@UCAutoWinFileTag@CommonUtil@@$0?0@CommonUtil@@QEAA@XZ`
- size: `24`
- prototype: `BOOL __fastcall(HANDLE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000fec0`

## callees

- `0x14000ed68`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000ed75`
- `KERNEL32!CloseHandle` at `0x14000ed75`

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
0x14000ed68  sub     rsp, 28h
0x14000ed6c  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x14000ed70  jz      short loc_14000ED7B
0x14000ed72  mov     rcx, [rcx]; hObject
0x14000ed75  call    cs:__imp_CloseHandle
0x14000ed7b  add     rsp, 28h
0x14000ed7f  retn
```
