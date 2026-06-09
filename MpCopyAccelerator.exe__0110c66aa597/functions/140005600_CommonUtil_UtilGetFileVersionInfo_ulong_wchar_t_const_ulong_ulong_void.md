# CommonUtil::UtilGetFileVersionInfo(ulong,wchar_t const *,ulong,ulong,void *)

- ea: `0x140005600`
- end: `0x14000562f`
- name: `?UtilGetFileVersionInfo@CommonUtil@@YAJKPEB_WKKPEAX@Z`
- size: `47`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned int, const wchar_t *, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000355c`

## callees

- `0x14000493c`
- `0x140005600`
- `0x140024c40`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetFileVersionInfo(CommonUtil *this, __int64 a2, const wchar_t *a3)
{
  int v3; // eax
  unsigned int v4; // ecx

  v3 = ((__int64 (__fastcall *)(CommonUtil *, __int64, const wchar_t *))off_14003B130)(this, a2, a3);
  v4 = 0;
  if ( !v3 )
    return (unsigned int)HrGetLastFailure(0);
  return v4;
}

```

## disassembly

```asm
0x140005600  sub     rsp, 38h
0x140005604  mov     r10, qword ptr [rsp+38h+arg_20]
0x140005609  mov     [rsp+38h+var_18], r10
0x14000560e  mov     rax, cs:off_14003B130
0x140005615  call    cs:__guard_dispatch_icall_fptr
0x14000561b  xor     ecx, ecx
0x14000561d  test    eax, eax
0x14000561f  jnz     short loc_140005628
0x140005621  call    HrGetLastFailure
0x140005626  mov     ecx, eax
0x140005628  mov     eax, ecx
0x14000562a  add     rsp, 38h
0x14000562e  retn
```
