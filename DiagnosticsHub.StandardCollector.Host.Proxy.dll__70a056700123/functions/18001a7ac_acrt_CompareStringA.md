# __acrt_CompareStringA

- ea: `0x18001a7ac`
- end: `0x18001a835`
- name: `__acrt_CompareStringA`
- size: `137`
- prototype: `__int64 __usercall@<rax>(struct __crt_locale_pointers *@<rcx>, int, __int64, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800138c0`
- `0x180013a70`

## callees

- `0x180008c44`
- `0x18001a41c`
- `0x18001a7ac`

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
0x18001a7ac  mov     [rsp+arg_0], rbx
0x18001a7b1  mov     [rsp+arg_8], rsi
0x18001a7b6  push    rdi
0x18001a7b7  sub     rsp, 60h
0x18001a7bb  mov     rsi, rdx
0x18001a7be  mov     rbx, r9
0x18001a7c1  mov     rdx, rcx; struct __crt_locale_pointers *
0x18001a7c4  mov     edi, r8d
0x18001a7c7  lea     rcx, [rsp+68h+var_28]; this
0x18001a7cc  call    ??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z; _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)
0x18001a7d1  mov     eax, [rsp+68h+arg_38]
0x18001a7d8  lea     rcx, [rsp+68h+var_20]
0x18001a7dd  mov     [rsp+68h+var_30], eax
0x18001a7e1  mov     r9, rbx
0x18001a7e4  mov     eax, [rsp+68h+arg_30]
0x18001a7eb  mov     r8d, edi
0x18001a7ee  mov     [rsp+68h+var_38], eax
0x18001a7f2  mov     rdx, rsi
0x18001a7f5  mov     rax, [rsp+68h+arg_28]
0x18001a7fd  mov     [rsp+68h+var_40], rax
0x18001a802  mov     eax, [rsp+68h+arg_20]
0x18001a809  mov     [rsp+68h+var_48], eax
0x18001a80d  call    InternalCompareStringA
0x18001a812  cmp     [rsp+68h+var_10], 0
0x18001a817  jz      short loc_18001A825
0x18001a819  mov     rcx, [rsp+68h+var_28]
0x18001a81e  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x18001a825  mov     rbx, [rsp+68h+arg_0]
0x18001a82a  mov     rsi, [rsp+68h+arg_8]
0x18001a82f  add     rsp, 60h
0x18001a833  pop     rdi
0x18001a834  retn
```
