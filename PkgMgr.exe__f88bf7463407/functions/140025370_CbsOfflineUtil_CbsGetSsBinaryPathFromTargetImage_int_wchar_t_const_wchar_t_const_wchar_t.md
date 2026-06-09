# CbsOfflineUtil::CbsGetSsBinaryPathFromTargetImage(int,wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x140025370`
- end: `0x1400253a9`
- name: `?CbsGetSsBinaryPathFromTargetImage@CbsOfflineUtil@@UEAAJHPEB_W0PEAPEA_W@Z`
- size: `57`
- prototype: `__int64 __fastcall(CbsOfflineUtil *__hidden this, int, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14002a010`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CbsGetSsBinaryPathFromTargetImage(
        CbsOfflineUtil *this,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        wchar_t **a5)
{
  return (*(__int64 (__fastcall **)(CbsOfflineUtil *, __int64, const wchar_t *, const wchar_t *, _QWORD, _QWORD, _QWORD, wchar_t **, _QWORD))(*(_QWORD *)this + 64LL))(
           this,
           a2,
           a3,
           a4,
           0,
           0,
           0,
           a5,
           0);
}

```

## disassembly

```asm
0x140025370  sub     rsp, 58h
0x140025374  mov     rax, [rcx]
0x140025377  xor     r11d, r11d
0x14002537a  mov     r10, [rsp+58h+arg_20]
0x140025382  mov     [rsp+58h+var_18], r11
0x140025387  mov     [rsp+58h+var_20], r10
0x14002538c  mov     rax, [rax+40h]
0x140025390  mov     [rsp+58h+var_28], r11
0x140025395  mov     [rsp+58h+var_30], r11
0x14002539a  mov     [rsp+58h+var_38], r11
0x14002539f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400253a4  add     rsp, 58h
0x1400253a8  retn
```
