# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)

- ea: `0x140017de4`
- end: `0x140017e81`
- name: `?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z`
- size: `157`
- prototype: `__int64 __fastcall(wchar_t **, const wchar_t *, size_t)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x14000d090`

## callees

- `0x140016474`
- `0x140017c28`
- `0x140017da8`
- `0x140017de4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        wchar_t **a1,
        const wchar_t *a2,
        size_t a3)
{
  unsigned __int64 v3; // rdi
  size_t cchToCopy; // rbx
  int v7; // ebp
  size_t v8; // rdx
  wchar_t *v9; // rcx

  v3 = a3;
  if ( a2 )
  {
    cchToCopy = -1;
    do
      ++cchToCopy;
    while ( a2[cchToCopy] );
    if ( a3 == -1 )
    {
      v3 = cchToCopy;
    }
    else if ( a3 < cchToCopy )
    {
      cchToCopy = a3;
    }
    v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
           (__int64)a1,
           v3);
    if ( v7 >= 0 )
    {
      v8 = v3 + 1;
      if ( v3 != -1 )
      {
        v9 = *a1;
        if ( v8 > 0x7FFFFFFF || cchToCopy > 0x7FFFFFFE )
          *v9 = 0;
        else
          StringCopyWorkerW(v9, v8, 0, a2, cchToCopy);
      }
      a1[1] = (wchar_t *)cchToCopy;
    }
  }
  else
  {
    v7 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)a1);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140017de4  push    rbx
0x140017de6  push    rbp
0x140017de7  push    rsi
0x140017de8  push    rdi
0x140017de9  push    r14
0x140017deb  push    r15
0x140017ded  sub     rsp, 38h
0x140017df1  xor     r15d, r15d
0x140017df4  mov     rdi, r8
0x140017df7  mov     r14, rdx
0x140017dfa  mov     rsi, rcx
0x140017dfd  test    rdx, rdx
0x140017e00  jz      short loc_140017E6A
0x140017e02  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140017e06  inc     rbx
0x140017e09  cmp     [rdx+rbx*2], r15w
0x140017e0e  jnz     short loc_140017E06
0x140017e10  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140017e14  jnz     short loc_140017E1B
0x140017e16  mov     rdi, rbx
0x140017e19  jmp     short loc_140017E22
0x140017e1b  cmp     r8, rbx
0x140017e1e  cmovb   rbx, r8
0x140017e22  mov     rdx, rdi
0x140017e25  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x140017e2a  mov     ebp, eax
0x140017e2c  test    eax, eax
0x140017e2e  js      short loc_140017E72
0x140017e30  lea     rdx, [rdi+1]; cchDest
0x140017e34  test    rdx, rdx
0x140017e37  jz      short loc_140017E64
0x140017e39  mov     rcx, [rsi]; pszDest
0x140017e3c  cmp     rdx, 7FFFFFFFh
0x140017e43  ja      short loc_140017E60
0x140017e45  cmp     rbx, 7FFFFFFEh
0x140017e4c  ja      short loc_140017E60
0x140017e4e  mov     r9, r14; pszSrc
0x140017e51  mov     [rsp+68h+cchToCopy], rbx; cchToCopy
0x140017e56  xor     r8d, r8d; pcchNewDestLength
0x140017e59  call    StringCopyWorkerW
0x140017e5e  jmp     short loc_140017E64
0x140017e60  mov     [rcx], r15w
0x140017e64  mov     [rsi+8], rbx
0x140017e68  jmp     short loc_140017E72
0x140017e6a  mov     ebp, r15d
0x140017e6d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x140017e72  mov     eax, ebp
0x140017e74  add     rsp, 38h
0x140017e78  pop     r15
0x140017e7a  pop     r14
0x140017e7c  pop     rdi
0x140017e7d  pop     rsi
0x140017e7e  pop     rbp
0x140017e7f  pop     rbx
0x140017e80  retn
```
