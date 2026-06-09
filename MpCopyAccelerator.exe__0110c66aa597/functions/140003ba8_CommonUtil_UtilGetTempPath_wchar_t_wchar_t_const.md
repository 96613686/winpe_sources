# CommonUtil::UtilGetTempPath(wchar_t * *,wchar_t const *)

- ea: `0x140003ba8`
- end: `0x140003bc0`
- name: `?UtilGetTempPath@CommonUtil@@YAJPEAPEA_WPEB_W@Z`
- size: `24`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, wchar_t **, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001d700`

## callees

- `0x140003bc0`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetTempPath(CommonUtil *this, wchar_t **a2, const wchar_t *a3)
{
  return CommonUtil::UtilGetWindowsPath(CommonUtil::MpGetTempPathW, this, a2, 1);
}

```

## disassembly

```asm
0x140003ba8  mov     r8, rdx
0x140003bab  mov     r9d, 1
0x140003bb1  mov     rdx, rcx
0x140003bb4  lea     rcx, CommonUtil__MpGetTempPathW
0x140003bbb  jmp     $+5
```
