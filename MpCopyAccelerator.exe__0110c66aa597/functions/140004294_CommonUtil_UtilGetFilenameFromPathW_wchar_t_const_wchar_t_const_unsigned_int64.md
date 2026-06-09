# CommonUtil::UtilGetFilenameFromPathW(wchar_t const *,wchar_t const * *,unsigned __int64 *)

- ea: `0x140004294`
- end: `0x140004299`
- name: `?UtilGetFilenameFromPathW@CommonUtil@@YAJPEB_WPEAPEB_WPEA_K@Z`
- size: `5`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, const wchar_t *, const wchar_t **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001f304`

## callees

- `0x140004064`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CommonUtil::UtilGetFilenameFromPathW(
        _WORD *this,
        _QWORD *a2,
        unsigned __int64 *a3,
        unsigned __int64 *a4)
{
  return CommonUtil::UtilGetFilenameFromPath<wchar_t>(this, a2, a3);
}

```

## disassembly

```asm
0x140004294  jmp     ??$UtilGetFilenameFromPath@_W@CommonUtil@@YAJPEB_WPEAPEB_WPEA_K@Z; CommonUtil::UtilGetFilenameFromPath<wchar_t>(wchar_t const *,wchar_t const * *,unsigned __int64 *)
```
