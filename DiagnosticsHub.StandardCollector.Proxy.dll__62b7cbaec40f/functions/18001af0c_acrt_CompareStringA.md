# __acrt_CompareStringA

- ea: `0x18001af0c`
- end: `0x18001af95`
- name: `__acrt_CompareStringA`
- size: `137`
- prototype: `__int64 __usercall@<rax>(struct __crt_locale_pointers *@<rcx>, int, __int64, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180014020`
- `0x1800141d0`

## callees

- `0x1800093a4`
- `0x18001ab7c`
- `0x18001af0c`

## pseudocode

```c
__int64 __fastcall _acrt_CompareStringA(
        struct __crt_locale_pointers *a1,
        __int64 a2,
        DWORD a3,
        const char *a4,
        int a5,
        char *a6,
        int a7,
        UINT a8)
{
  __int64 result; // rax
  __int64 v12; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v13[32]; // [rsp+48h] [rbp-20h] BYREF

  _LocaleUpdate::_LocaleUpdate((_LocaleUpdate *)&v12, a1);
  result = InternalCompareStringA((__int64)v13, a2, a3, a4, a5, a6, a7, a8);
  if ( v13[16] )
    *(_DWORD *)(v12 + 936) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x18001af0c  mov     [rsp+arg_0], rbx
0x18001af11  mov     [rsp+arg_8], rsi
0x18001af16  push    rdi
0x18001af17  sub     rsp, 60h
0x18001af1b  mov     rsi, rdx
0x18001af1e  mov     rbx, r9
0x18001af21  mov     rdx, rcx; struct __crt_locale_pointers *
0x18001af24  mov     edi, r8d
0x18001af27  lea     rcx, [rsp+68h+var_28]; this
0x18001af2c  call    ??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z; _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)
0x18001af31  mov     eax, [rsp+68h+arg_38]
0x18001af38  lea     rcx, [rsp+68h+var_20]
0x18001af3d  mov     [rsp+68h+var_30], eax
0x18001af41  mov     r9, rbx
0x18001af44  mov     eax, [rsp+68h+arg_30]
0x18001af4b  mov     r8d, edi
0x18001af4e  mov     [rsp+68h+var_38], eax
0x18001af52  mov     rdx, rsi
0x18001af55  mov     rax, [rsp+68h+arg_28]
0x18001af5d  mov     [rsp+68h+var_40], rax
0x18001af62  mov     eax, [rsp+68h+arg_20]
0x18001af69  mov     [rsp+68h+var_48], eax
0x18001af6d  call    InternalCompareStringA
0x18001af72  cmp     [rsp+68h+var_10], 0
0x18001af77  jz      short loc_18001AF85
0x18001af79  mov     rcx, [rsp+68h+var_28]
0x18001af7e  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x18001af85  mov     rbx, [rsp+68h+arg_0]
0x18001af8a  mov     rsi, [rsp+68h+arg_8]
0x18001af8f  add     rsp, 60h
0x18001af93  pop     rdi
0x18001af94  retn
```
