# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)

- ea: `0x180012b48`
- end: `0x180012c0a`
- name: `?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z`
- size: `194`
- prototype: `__int64 __fastcall(_QWORD *, _WORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800120b8`
- `0x180016e40`

## callees

- `0x1800129e4`
- `0x180012b0c`
- `0x180012b48`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        _QWORD *a1,
        _WORD *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // rdi
  _WORD *v4; // r14
  unsigned __int64 v6; // rbx
  int v7; // ebp
  unsigned __int64 v8; // rdi
  _WORD *v9; // rdx
  unsigned __int64 v10; // rax
  _WORD *v11; // rcx

  v3 = a3;
  v4 = a2;
  if ( a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    if ( a3 == -1 )
    {
      v3 = v6;
    }
    else if ( a3 < v6 )
    {
      v6 = a3;
    }
    v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
           (__int64)a1,
           v3);
    if ( v7 >= 0 )
    {
      v8 = v3 + 1;
      if ( v8 )
      {
        v9 = (_WORD *)*a1;
        if ( v8 <= 0x7FFFFFFF && v6 <= 0x7FFFFFFE )
        {
          v10 = v6;
          do
          {
            if ( !v10 )
              break;
            if ( !*v4 )
              break;
            *v9++ = *v4++;
            --v10;
            --v8;
          }
          while ( v8 );
          v11 = v9 - 1;
          if ( v8 )
            v11 = v9;
          *v11 = 0;
        }
        else
        {
          *v9 = 0;
        }
      }
      a1[1] = v6;
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
0x180012b48  push    rbx
0x180012b4a  push    rbp
0x180012b4b  push    rsi
0x180012b4c  push    rdi
0x180012b4d  push    r14
0x180012b4f  push    r15
0x180012b51  sub     rsp, 28h
0x180012b55  xor     r15d, r15d
0x180012b58  mov     rdi, r8
0x180012b5b  mov     r14, rdx
0x180012b5e  mov     rsi, rcx
0x180012b61  test    rdx, rdx
0x180012b64  jz      loc_180012BF3
0x180012b6a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012b6e  inc     rbx
0x180012b71  cmp     [rdx+rbx*2], r15w
0x180012b76  jnz     short loc_180012B6E
0x180012b78  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180012b7c  jnz     short loc_180012B83
0x180012b7e  mov     rdi, rbx
0x180012b81  jmp     short loc_180012B8A
0x180012b83  cmp     r8, rbx
0x180012b86  cmovb   rbx, r8
0x180012b8a  mov     rdx, rdi
0x180012b8d  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180012b92  mov     ebp, eax
0x180012b94  test    eax, eax
0x180012b96  js      short loc_180012BFB
0x180012b98  add     rdi, 1
0x180012b9c  jz      short loc_180012BED
0x180012b9e  mov     rdx, [rsi]
0x180012ba1  cmp     rdi, 7FFFFFFFh
0x180012ba8  ja      short loc_180012BB3
0x180012baa  cmp     rbx, 7FFFFFFEh
0x180012bb1  jbe     short loc_180012BB9
0x180012bb3  mov     [rdx], r15w
0x180012bb7  jmp     short loc_180012BED
0x180012bb9  mov     rax, rbx
0x180012bbc  test    rax, rax
0x180012bbf  jz      short loc_180012BDE
0x180012bc1  movzx   ecx, word ptr [r14]
0x180012bc5  test    cx, cx
0x180012bc8  jz      short loc_180012BDE
0x180012bca  mov     [rdx], cx
0x180012bcd  add     r14, 2
0x180012bd1  add     rdx, 2
0x180012bd5  dec     rax
0x180012bd8  sub     rdi, 1
0x180012bdc  jnz     short loc_180012BBC
0x180012bde  test    rdi, rdi
0x180012be1  lea     rcx, [rdx-2]
0x180012be5  cmovnz  rcx, rdx
0x180012be9  mov     [rcx], r15w
0x180012bed  mov     [rsi+8], rbx
0x180012bf1  jmp     short loc_180012BFB
0x180012bf3  mov     ebp, r15d
0x180012bf6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180012bfb  mov     eax, ebp
0x180012bfd  add     rsp, 28h
0x180012c01  pop     r15
0x180012c03  pop     r14
0x180012c05  pop     rdi
0x180012c06  pop     rsi
0x180012c07  pop     rbp
0x180012c08  pop     rbx
0x180012c09  retn
```
