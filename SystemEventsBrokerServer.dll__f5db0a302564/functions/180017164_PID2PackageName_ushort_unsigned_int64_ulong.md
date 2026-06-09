# PID2PackageName(ushort *,unsigned __int64,ulong)

- ea: `0x180017164`
- end: `0x1800171b3`
- name: `?PID2PackageName@@YAJPEAG_KK@Z`
- size: `79`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b5d0`
- `0x18001bb90`
- `0x18001fd50`

## callees

- `0x18000b340`
- `0x180017164`
- `0x18001d9ac`

## string_xrefs

- `0x180017175`: `Microsoft.ProcessID%x_1.0.0.1_neutral__8wekyb3d8bbwe`

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
0x180017164  sub     rsp, 48h
0x180017168  test    rcx, rcx
0x18001716b  jz      short loc_180017185
0x18001716d  mov     r9d, r8d
0x180017170  mov     edx, 7Fh; unsigned __int64
0x180017175  lea     r8, aMicrosoftProce; "Microsoft.ProcessID%x_1.0.0.1_neutral__"...
0x18001717c  add     rsp, 48h
0x180017180  jmp     ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017185  xorps   xmm0, xmm0
0x180017188  mov     [rsp+48h+var_10], 4
0x180017190  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x180017197  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18001719e  mov     [rsp+48h+pExceptionObject], rax
0x1800171a3  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800171a8  movups  [rsp+48h+var_20], xmm0
0x1800171ad  call    _CxxThrowException_0
```
