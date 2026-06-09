# VDIR_OBJECT::SerializeText(ushort *,ulong)

- ea: `0x180016d70`
- end: `0x180016e1f`
- name: `?SerializeText@VDIR_OBJECT@@UEAAJPEAGK@Z`
- size: `175`
- prototype: `int(VDIR_OBJECT *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000d654`
- `0x180016d70`
- `0x180036010`

## string_xrefs

- `0x180016dcc`: `physicalPath`
- `0x180016df4`: `%ws "%ws" (physicalPath:%ws)`

## pseudocode

```c
__int64 __fastcall VDIR_OBJECT::SerializeText(VDIR_OBJECT *this, unsigned __int16 *a2, unsigned int a3)
{
  _QWORD *v3; // rax
  __int64 result; // rax
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+58h] [rbp+20h] BYREF

  v3 = *(_QWORD **)this;
  v9 = 0;
  v8 = 0;
  result = ((__int64 (__fastcall *)(VDIR_OBJECT *, const unsigned __int16 *, __int64 *))v3[10])(this, L"VDIR.NAME", &v9);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64 *, _QWORD, _QWORD))(**((_QWORD **)this + 23) + 64LL))(
               *((_QWORD *)this + 23),
               L"physicalPath",
               &v8,
               0,
               0);
    if ( (int)result >= 0 )
      return StringCchPrintfW(a2, a3, L"%ws \"%ws\" (physicalPath:%ws)", L"VDIR", v9, v8);
  }
  return result;
}

```

## disassembly

```asm
0x180016d70  mov     r11, rsp
0x180016d73  mov     [r11+10h], rbx
0x180016d77  mov     [r11+18h], rsi
0x180016d7b  push    rdi
0x180016d7c  sub     rsp, 30h
0x180016d80  mov     rax, [rcx]
0x180016d83  mov     rsi, rdx
0x180016d86  mov     edi, r8d
0x180016d89  lea     rdx, aVdirName; "VDIR.NAME"
0x180016d90  lea     r8, [r11+20h]
0x180016d94  mov     qword ptr [r11+20h], 0
0x180016d9c  mov     rbx, rcx
0x180016d9f  mov     qword ptr [r11+8], 0
0x180016da7  mov     rax, [rax+50h]
0x180016dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016db0  test    eax, eax
0x180016db2  js      short loc_180016E0F
0x180016db4  mov     rcx, [rbx+0B8h]
0x180016dbb  lea     r8, [rsp+38h+arg_0]
0x180016dc0  xor     r9d, r9d
0x180016dc3  mov     [rsp+38h+var_18], 0
0x180016dcc  lea     rdx, aPhysicalpath; "physicalPath"
0x180016dd3  mov     rax, [rcx]
0x180016dd6  mov     rax, [rax+40h]
0x180016dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ddf  test    eax, eax
0x180016de1  js      short loc_180016E0F
0x180016de3  mov     rax, [rsp+38h+arg_0]
0x180016de8  lea     r9, aVdir; "VDIR"
0x180016def  mov     [rsp+38h+var_10], rax
0x180016df4  lea     r8, aWsWsPhysicalpa; "%ws \"%ws\" (physicalPath:%ws)"
0x180016dfb  mov     rax, [rsp+38h+arg_18]
0x180016e00  mov     edx, edi; unsigned __int64
0x180016e02  mov     rcx, rsi; unsigned __int16 *
0x180016e05  mov     [rsp+38h+var_18], rax
0x180016e0a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016e0f  mov     rbx, [rsp+38h+arg_8]
0x180016e14  mov     rsi, [rsp+38h+arg_10]
0x180016e19  add     rsp, 30h
0x180016e1d  pop     rdi
0x180016e1e  retn
```
