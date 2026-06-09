# CommonUtil::CUniqueHandle<CommonUtil::CAutoGenericBufferDelete>::~CUniqueHandle<CommonUtil::CAutoGenericBufferDelete>(void)

- ea: `0x180007d7c`
- end: `0x180007d93`
- name: `??1?$CUniqueHandle@UCAutoGenericBufferDelete@CommonUtil@@@CommonUtil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009aa2`

## callees

- `0x180007d7c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007d88`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007d88`

## pseudocode

```c
void __fastcall CommonUtil::CUniqueHandle<CommonUtil::CAutoGenericBufferDelete>::~CUniqueHandle<CommonUtil::CAutoGenericBufferDelete>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x180007d7c  sub     rsp, 28h
0x180007d80  mov     rcx, [rcx]
0x180007d83  test    rcx, rcx
0x180007d86  jz      short loc_180007D8E
0x180007d88  call    cs:__imp_??3@YAXPEAX@Z
0x180007d8e  add     rsp, 28h
0x180007d92  retn
```
