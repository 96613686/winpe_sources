# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18001ed70`
- end: `0x18001eeac`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `316`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000fe34`
- `0x1800129b0`
- `0x180012b88`
- `0x18001d5b0`

## callees

- `0x18001e530`
- `0x18001ed70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001ee77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001ee77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ee0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ee0c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rbp
  int v4; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rcx
  _WORD *v7; // rax
  __int64 v8; // r9
  SIZE_T v9; // rsi
  LPVOID v10; // rax
  SIZE_T cb; // [rsp+48h] [rbp+10h] BYREF

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v5 = *(_QWORD *)(a1 + 16);
  v6 = -1;
  if ( v5 == -1 )
  {
    if ( *(_QWORD *)(a1 + 8) == -1 )
    {
      if ( *(_QWORD *)a1 )
      {
        do
          ++v6;
        while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v6) );
      }
      else
      {
        v6 = 0;
      }
      *(_QWORD *)(a1 + 8) = v6;
    }
    else
    {
      v6 = *(_QWORD *)(a1 + 8);
    }
    v5 = (v6 + 1) & -(__int64)(*(_QWORD *)a1 != 0);
    *(_QWORD *)(a1 + 16) = v5;
  }
  if ( !v5 )
  {
    cb = 0;
    v4 = ULongLongMult(v2, 2u, &cb);
    if ( v4 < 0 )
      return (unsigned int)v4;
    v7 = CoTaskMemAlloc(cb);
    if ( v7 )
    {
      *(_QWORD *)(a1 + 16) = v2;
      *(_QWORD *)a1 = v7;
      *v7 = 0;
      return (unsigned int)v4;
    }
    return (unsigned int)-2147024882;
  }
  v4 = 0;
  if ( v2 > v5 )
  {
    cb = 0;
    v4 = ULongLongMult(v5, 2u, &cb);
    if ( v4 >= 0 )
    {
      v9 = cb;
      if ( cb - v8 > 0x800 )
        v9 = v8 + 2048;
      if ( v2 > v9 )
        v9 = v2;
      v10 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v9);
      if ( v10 )
      {
        *(_QWORD *)(a1 + 16) = v9;
        *(_QWORD *)a1 = v10;
        return (unsigned int)v4;
      }
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001ed70  mov     [rsp+arg_0], rbx
0x18001ed75  mov     [rsp+arg_10], rbp
0x18001ed7a  push    rsi
0x18001ed7b  push    rdi
0x18001ed7c  push    r14
0x18001ed7e  sub     rsp, 20h
0x18001ed82  lea     rbp, [rdx+1]
0x18001ed86  mov     rdi, rcx
0x18001ed89  cmp     rbp, rdx
0x18001ed8c  jnb     short loc_18001ED98
0x18001ed8e  mov     ebx, 80070216h
0x18001ed93  jmp     loc_18001EE96
0x18001ed98  mov     r9, [rcx+10h]
0x18001ed9c  xor     r14d, r14d
0x18001ed9f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001eda3  cmp     r9, rcx
0x18001eda6  jnz     short loc_18001EDE2
0x18001eda8  cmp     [rdi+8], rcx
0x18001edac  jnz     short loc_18001EDCB
0x18001edae  mov     rax, [rdi]
0x18001edb1  test    rax, rax
0x18001edb4  jz      short loc_18001EDC2
0x18001edb6  inc     rcx
0x18001edb9  cmp     [rax+rcx*2], r14w
0x18001edbe  jnz     short loc_18001EDB6
0x18001edc0  jmp     short loc_18001EDC5
0x18001edc2  mov     rcx, r14
0x18001edc5  mov     [rdi+8], rcx
0x18001edc9  jmp     short loc_18001EDCF
0x18001edcb  mov     rcx, [rdi+8]
0x18001edcf  mov     rax, [rdi]
0x18001edd2  inc     rcx
0x18001edd5  neg     rax
0x18001edd8  sbb     r9, r9
0x18001eddb  and     r9, rcx
0x18001edde  mov     [rdi+10h], r9
0x18001ede2  test    r9, r9
0x18001ede5  jnz     short loc_18001EE2A
0x18001ede7  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x18001edec  mov     [rsp+38h+cb], r14
0x18001edf1  lea     edx, [r9+2]; unsigned __int64
0x18001edf5  mov     rcx, rbp; unsigned __int64
0x18001edf8  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001edfd  mov     ebx, eax
0x18001edff  test    eax, eax
0x18001ee01  js      loc_18001EE96
0x18001ee07  mov     rcx, [rsp+38h+cb]; cb
0x18001ee0c  call    cs:__imp_CoTaskMemAlloc
0x18001ee13  nop     dword ptr [rax+rax+00h]
0x18001ee18  test    rax, rax
0x18001ee1b  jz      short loc_18001EE91
0x18001ee1d  mov     [rdi+10h], rbp
0x18001ee21  mov     [rdi], rax
0x18001ee24  mov     [rax], r14w
0x18001ee28  jmp     short loc_18001EE96
0x18001ee2a  mov     ebx, r14d
0x18001ee2d  cmp     rbp, r9
0x18001ee30  jbe     short loc_18001EE96
0x18001ee32  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x18001ee37  mov     [rsp+38h+cb], r14
0x18001ee3c  mov     edx, 2; unsigned __int64
0x18001ee41  mov     rcx, r9; unsigned __int64
0x18001ee44  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001ee49  mov     ebx, eax
0x18001ee4b  test    eax, eax
0x18001ee4d  js      short loc_18001EE96
0x18001ee4f  mov     rsi, [rsp+38h+cb]
0x18001ee54  mov     rax, rsi
0x18001ee57  sub     rax, r9
0x18001ee5a  cmp     rax, 800h
0x18001ee60  jbe     short loc_18001EE69
0x18001ee62  lea     rsi, [r9+800h]
0x18001ee69  mov     rcx, [rdi]; pv
0x18001ee6c  cmp     rbp, rsi
0x18001ee6f  cmova   rsi, rbp
0x18001ee73  lea     rdx, [rsi+rsi]; cb
0x18001ee77  call    cs:__imp_CoTaskMemRealloc
0x18001ee7e  nop     dword ptr [rax+rax+00h]
0x18001ee83  test    rax, rax
0x18001ee86  jz      short loc_18001EE91
0x18001ee88  mov     [rdi+10h], rsi
0x18001ee8c  mov     [rdi], rax
0x18001ee8f  jmp     short loc_18001EE96
0x18001ee91  mov     ebx, 8007000Eh
0x18001ee96  mov     rbp, [rsp+38h+arg_10]
0x18001ee9b  mov     eax, ebx
0x18001ee9d  mov     rbx, [rsp+38h+arg_0]
0x18001eea2  add     rsp, 20h
0x18001eea6  pop     r14
0x18001eea8  pop     rdi
0x18001eea9  pop     rsi
0x18001eeaa  retn
```
