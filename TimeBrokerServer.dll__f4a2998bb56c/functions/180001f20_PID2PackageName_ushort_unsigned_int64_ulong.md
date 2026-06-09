# PID2PackageName(ushort *,unsigned __int64,ulong)

- ea: `0x180001f20`
- end: `0x180001f6f`
- name: `?PID2PackageName@@YAJPEAG_KK@Z`
- size: `79`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800149d0`

## callees

- `0x180001f20`
- `0x180003f6c`
- `0x180013978`

## string_xrefs

- `0x180001f31`: `Microsoft.ProcessID%x_1.0.0.1_neutral__8wekyb3d8bbwe`

## pseudocode

```c
__int64 __fastcall PID2PackageName(unsigned __int16 *a1, __int64 a2, unsigned int a3)
{
  void **pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  __int128 v5; // [rsp+28h] [rbp-20h]
  int v6; // [rsp+38h] [rbp-10h]

  if ( !a1 )
  {
    v6 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    v5 = 0;
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
  return StringCchPrintfW(a1, 0x7Fu, L"Microsoft.ProcessID%x_1.0.0.1_neutral__8wekyb3d8bbwe", a3);
}

```

## disassembly

```asm
0x180001f20  sub     rsp, 48h
0x180001f24  test    rcx, rcx
0x180001f27  jz      short loc_180001F41
0x180001f29  mov     r9d, r8d
0x180001f2c  mov     edx, 7Fh; unsigned __int64
0x180001f31  lea     r8, aMicrosoftProce; "Microsoft.ProcessID%x_1.0.0.1_neutral__"...
0x180001f38  add     rsp, 48h
0x180001f3c  jmp     ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001f41  xorps   xmm0, xmm0
0x180001f44  mov     [rsp+48h+var_10], 4
0x180001f4c  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180001f53  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180001f5a  mov     [rsp+48h+pExceptionObject], rax
0x180001f5f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001f64  movups  [rsp+48h+var_20], xmm0
0x180001f69  call    _CxxThrowException_0
```
