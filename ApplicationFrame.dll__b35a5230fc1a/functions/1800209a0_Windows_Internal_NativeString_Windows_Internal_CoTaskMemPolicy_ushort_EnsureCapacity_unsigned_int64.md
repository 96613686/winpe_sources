# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x1800209a0`
- end: `0x180020ade`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `318`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001feb0`
- `0x180063684`

## callees

- `0x1800209a0`
- `0x18002e020`
- `0x1800532a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180020a85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180020a85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800209e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800209e0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v4; // r9
  _WORD *v5; // rdx
  __int64 result; // rax
  __int64 v7; // r9
  unsigned int v8; // ebp
  unsigned __int64 v9; // rsi
  LPVOID v10; // rax
  _QWORD *v11; // rcx
  unsigned __int64 v12; // [rsp+38h] [rbp+10h] BYREF

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return 2147942934LL;
  v4 = *(_QWORD *)(a1 + 16);
  if ( v4 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a1);
    if ( *v11 )
      v4 = v11[1] + 1LL;
    else
      v4 = 0;
    v11[2] = v4;
  }
  if ( v4 )
  {
    result = 0;
    if ( v2 > v4 )
    {
      v12 = 0;
      result = ULongLongMult(v4, 2u, &v12);
      v8 = result;
      if ( (int)result >= 0 )
      {
        v9 = v12;
        if ( v12 - v7 > 0x800 )
          v9 = v7 + 2048;
        if ( v2 > v9 )
          v9 = v2;
        v10 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v9);
        if ( v10 )
        {
          *(_QWORD *)a1 = v10;
          result = v8;
          *(_QWORD *)(a1 + 16) = v9;
        }
        else
        {
          return 2147942414LL;
        }
      }
    }
  }
  else if ( is_mul_ok(v2, 2u) )
  {
    v5 = CoTaskMemAlloc(2 * v2);
    if ( v5 )
    {
      *(_QWORD *)(a1 + 16) = v2;
      result = 0;
      *(_QWORD *)a1 = v5;
      *v5 = 0;
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    return 2147942934LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800209a0  mov     [rsp+arg_18], rbx
0x1800209a5  push    rdi
0x1800209a6  sub     rsp, 20h
0x1800209aa  lea     rdi, [rdx+1]
0x1800209ae  mov     rbx, rcx
0x1800209b1  cmp     rdi, rdx
0x1800209b4  jb      short loc_180020A0E
0x1800209b6  mov     r9, [rcx+10h]
0x1800209ba  mov     [rsp+28h+arg_10], rsi
0x1800209bf  xor     esi, esi
0x1800209c1  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1800209c5  jz      loc_180020AB0
0x1800209cb  test    r9, r9
0x1800209ce  jnz     short loc_180020A33
0x1800209d0  mov     eax, 2
0x1800209d5  mul     rdi
0x1800209d8  test    rdx, rdx
0x1800209db  jnz     short loc_180020A1E
0x1800209dd  mov     rcx, rax; cb
0x1800209e0  call    cs:__imp_CoTaskMemAlloc
0x1800209e6  mov     rdx, rax
0x1800209e9  test    rax, rax
0x1800209ec  jz      loc_180020A9B
0x1800209f2  mov     [rbx+10h], rdi
0x1800209f6  mov     eax, esi
0x1800209f8  mov     [rbx], rdx
0x1800209fb  mov     [rdx], si
0x1800209fe  mov     rsi, [rsp+28h+arg_10]
0x180020a03  mov     rbx, [rsp+28h+arg_18]
0x180020a08  add     rsp, 20h
0x180020a0c  pop     rdi
0x180020a0d  retn
0x180020a0e  mov     eax, 80070216h
0x180020a13  mov     rbx, [rsp+28h+arg_18]
0x180020a18  add     rsp, 20h
0x180020a1c  pop     rdi
0x180020a1d  retn
0x180020a1e  mov     rsi, [rsp+28h+arg_10]
0x180020a23  mov     eax, 80070216h
0x180020a28  mov     rbx, [rsp+28h+arg_18]
0x180020a2d  add     rsp, 20h
0x180020a31  pop     rdi
0x180020a32  retn
0x180020a33  mov     eax, esi
0x180020a35  cmp     rdi, r9
0x180020a38  jbe     short loc_1800209FE
0x180020a3a  lea     r8, [rsp+28h+arg_8]; unsigned __int64 *
0x180020a3f  mov     [rsp+28h+arg_0], rbp
0x180020a44  mov     edx, 2; unsigned __int64
0x180020a49  mov     [rsp+28h+arg_8], rsi
0x180020a4e  mov     rcx, r9; unsigned __int64
0x180020a51  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180020a56  mov     ebp, eax
0x180020a58  test    eax, eax
0x180020a5a  js      short loc_180020AD4
0x180020a5c  mov     rsi, [rsp+28h+arg_8]
0x180020a61  mov     rcx, rsi
0x180020a64  sub     rcx, r9
0x180020a67  cmp     rcx, 800h
0x180020a6e  jbe     short loc_180020A77
0x180020a70  lea     rsi, [r9+800h]
0x180020a77  mov     rcx, [rbx]; pv
0x180020a7a  cmp     rdi, rsi
0x180020a7d  cmova   rsi, rdi
0x180020a81  lea     rdx, [rsi+rsi]; cb
0x180020a85  call    cs:__imp_CoTaskMemRealloc
0x180020a8b  test    rax, rax
0x180020a8e  jz      short loc_180020ACF
0x180020a90  mov     [rbx], rax
0x180020a93  mov     eax, ebp
0x180020a95  mov     [rbx+10h], rsi
0x180020a99  jmp     short loc_180020AD4
0x180020a9b  mov     rsi, [rsp+28h+arg_10]
0x180020aa0  mov     eax, 8007000Eh
0x180020aa5  mov     rbx, [rsp+28h+arg_18]
0x180020aaa  add     rsp, 20h
0x180020aae  pop     rdi
0x180020aaf  retn
0x180020ab0  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180020ab5  cmp     [rcx], rsi
0x180020ab8  jz      short loc_180020AC3
0x180020aba  mov     r9, [rcx+8]
0x180020abe  inc     r9
0x180020ac1  jmp     short loc_180020AC6
0x180020ac3  mov     r9, rsi
0x180020ac6  mov     [rcx+10h], r9
0x180020aca  jmp     loc_1800209CB
0x180020acf  mov     eax, 8007000Eh
0x180020ad4  mov     rbp, [rsp+28h+arg_0]
0x180020ad9  jmp     loc_1800209FE
```
