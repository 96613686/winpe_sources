# CProfileCache::_CountConnectedInterfaces(uint *,uint *)

- ea: `0x180006c28`
- end: `0x180006d9b`
- name: `?_CountConnectedInterfaces@CProfileCache@@AEAAJPEAI0@Z`
- size: `371`
- prototype: `__int64 __fastcall(CProfileCache *__hidden this, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006ef4`

## callees

- `0x18000599c`
- `0x180006c28`
- `0x18000a7d0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CProfileCache::_CountConnectedInterfaces(CProfileCache *this, unsigned int *a2, unsigned int *a3)
{
  __int64 v5; // rcx
  int v7; // ebx
  __int64 v8; // rcx
  unsigned int v9; // edx
  unsigned __int16 **v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v13; // [rsp+38h] [rbp-38h] BYREF
  int v14; // [rsp+3Ch] [rbp-34h] BYREF
  __int64 v15; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 **v16; // [rsp+48h] [rbp-28h] BYREF
  __int128 v17; // [rsp+50h] [rbp-20h] BYREF

  *a2 = 0;
  *a3 = 0;
  v5 = *((_QWORD *)this + 1);
  v15 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v5 + 32LL))(v5, 1, &v15);
  if ( v7 >= 0 )
  {
    v12 = 0;
    v14 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v15 + 24LL))(v15, 1, &v12, &v14);
    while ( !v7 )
    {
      v17 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v12 + 48LL))(v12, &v17);
      if ( v7 >= 0 )
      {
        v8 = *((_QWORD *)this + 1);
        v16 = 0;
        v13 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, unsigned int *, unsigned __int16 ***))(*(_QWORD *)v8 + 80LL))(
               v8,
               &v17,
               &v13,
               &v16);
        if ( v7 >= 0 )
        {
          v9 = v13;
          *a2 += v13;
          v10 = v16;
          ++*a3;
          FreeStringArray(v10, v9);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          v12 = 0;
          v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v15 + 24LL))(
                 v15,
                 1,
                 &v12,
                 &v14);
        }
      }
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006c28  push    rbp
0x180006c2a  push    rbx
0x180006c2b  push    rsi
0x180006c2c  push    rdi
0x180006c2d  push    r14
0x180006c2f  mov     rbp, rsp
0x180006c32  sub     rsp, 70h
0x180006c36  mov     rax, cs:__security_cookie
0x180006c3d  xor     rax, rsp
0x180006c40  mov     [rbp+var_10], rax
0x180006c44  mov     dword ptr [rdx], 0
0x180006c4a  mov     rdi, rcx
0x180006c4d  mov     dword ptr [r8], 0
0x180006c54  mov     r14, r8
0x180006c57  mov     rcx, [rcx+8]
0x180006c5b  lea     r8, [rbp+var_30]
0x180006c5f  mov     [rbp+var_30], 0
0x180006c67  mov     rsi, rdx
0x180006c6a  mov     edx, 1
0x180006c6f  mov     rax, [rcx]
0x180006c72  mov     rax, [rax+20h]
0x180006c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c7b  mov     ebx, eax
0x180006c7d  test    eax, eax
0x180006c7f  js      loc_180006D82
0x180006c85  mov     rcx, [rbp+var_30]
0x180006c89  lea     r9, [rbp+var_34]
0x180006c8d  mov     [rbp+var_40], 0
0x180006c95  lea     r8, [rbp+var_40]
0x180006c99  mov     [rbp+var_34], 0
0x180006ca0  mov     edx, 1
0x180006ca5  mov     rax, [rcx]
0x180006ca8  mov     rax, [rax+18h]
0x180006cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cb1  mov     ebx, eax
0x180006cb3  test    eax, eax
0x180006cb5  jnz     loc_180006D5D
0x180006cbb  mov     rcx, [rbp+var_40]
0x180006cbf  lea     rdx, [rbp+var_20]
0x180006cc3  xorps   xmm0, xmm0
0x180006cc6  movups  [rbp+var_20], xmm0
0x180006cca  mov     rax, [rcx]
0x180006ccd  mov     rax, [rax+30h]
0x180006cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cd6  mov     ebx, eax
0x180006cd8  test    eax, eax
0x180006cda  js      short loc_180006D55
0x180006cdc  mov     rcx, [rdi+8]
0x180006ce0  lea     r9, [rbp+var_28]
0x180006ce4  mov     [rbp+var_28], 0
0x180006cec  lea     r8, [rbp+var_38]
0x180006cf0  mov     [rbp+var_38], 0
0x180006cf7  lea     rdx, [rbp+var_20]
0x180006cfb  mov     rax, [rcx]
0x180006cfe  mov     rax, [rax+50h]
0x180006d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d07  mov     ebx, eax
0x180006d09  test    eax, eax
0x180006d0b  js      short loc_180006D55
0x180006d0d  mov     edx, [rbp+var_38]; unsigned int
0x180006d10  add     [rsi], edx
0x180006d12  mov     rcx, [rbp+var_28]; unsigned __int16 **
0x180006d16  inc     dword ptr [r14]
0x180006d19  call    ?FreeStringArray@@YAXPEAPEAGI@Z; FreeStringArray(ushort * *,uint)
0x180006d1e  mov     rcx, [rbp+var_40]
0x180006d22  mov     rax, [rcx]
0x180006d25  mov     rax, [rax+10h]
0x180006d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d2e  mov     rcx, [rbp+var_30]
0x180006d32  lea     r9, [rbp+var_34]
0x180006d36  mov     [rbp+var_40], 0
0x180006d3e  lea     r8, [rbp+var_40]
0x180006d42  mov     edx, 1
0x180006d47  mov     rax, [rcx]
0x180006d4a  mov     rax, [rax+18h]
0x180006d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d53  mov     ebx, eax
0x180006d55  test    ebx, ebx
0x180006d57  jz      loc_180006CBB
0x180006d5d  mov     rcx, [rbp+var_40]
0x180006d61  test    rcx, rcx
0x180006d64  jz      short loc_180006D72
0x180006d66  mov     rax, [rcx]
0x180006d69  mov     rax, [rax+10h]
0x180006d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d72  mov     rcx, [rbp+var_30]
0x180006d76  mov     rax, [rcx]
0x180006d79  mov     rax, [rax+10h]
0x180006d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d82  mov     eax, ebx
0x180006d84  mov     rcx, [rbp+var_10]
0x180006d88  xor     rcx, rsp; StackCookie
0x180006d8b  call    __security_check_cookie
0x180006d90  add     rsp, 70h
0x180006d94  pop     r14
0x180006d96  pop     rdi
0x180006d97  pop     rsi
0x180006d98  pop     rbx
0x180006d99  pop     rbp
0x180006d9a  retn
```
