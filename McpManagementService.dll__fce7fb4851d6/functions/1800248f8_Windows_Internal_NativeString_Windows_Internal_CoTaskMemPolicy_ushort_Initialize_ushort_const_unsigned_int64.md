# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)

- ea: `0x1800248f8`
- end: `0x18002499f`
- name: `?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD *, _WORD *)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180024370`
- `0x1800244d0`
- `0x1800245e0`
- `0x180025ba0`
- `0x180025d00`
- `0x180025e60`
- `0x180026070`
- `0x1800261d0`
- `0x180026330`

## callees

- `0x180024794`
- `0x1800248bc`
- `0x1800248f8`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        _QWORD *a1,
        _WORD *a2)
{
  _WORD *v2; // rdi
  unsigned __int64 v4; // rbx
  int v5; // ebp
  unsigned __int64 v6; // r8
  _WORD *v7; // rdx
  unsigned __int64 v8; // rax
  _WORD *v9; // rcx

  v2 = a2;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
           (__int64)a1,
           v4);
    if ( v5 >= 0 )
    {
      v6 = v4 + 1;
      if ( v4 != -1 )
      {
        v7 = (_WORD *)*a1;
        if ( v6 <= 0x7FFFFFFF && v4 <= 0x7FFFFFFE )
        {
          v8 = v4;
          do
          {
            if ( !v8 )
              break;
            if ( !*v2 )
              break;
            *v7++ = *v2++;
            --v8;
            --v6;
          }
          while ( v6 );
          v9 = v7 - 1;
          if ( v6 )
            v9 = v7;
          *v9 = 0;
        }
        else
        {
          *v7 = 0;
        }
      }
      a1[1] = v4;
    }
  }
  else
  {
    v5 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)a1);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800248f8  push    rbx
0x1800248fa  push    rbp
0x1800248fb  push    rsi
0x1800248fc  push    rdi
0x1800248fd  push    r14
0x1800248ff  sub     rsp, 20h
0x180024903  xor     r14d, r14d
0x180024906  mov     rdi, rdx
0x180024909  mov     rsi, rcx
0x18002490c  test    rdx, rdx
0x18002490f  jz      short loc_18002498A
0x180024911  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180024915  inc     rbx
0x180024918  cmp     [rdx+rbx*2], r14w
0x18002491d  jnz     short loc_180024915
0x18002491f  mov     rdx, rbx
0x180024922  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180024927  mov     ebp, eax
0x180024929  test    eax, eax
0x18002492b  js      short loc_180024992
0x18002492d  lea     r8, [rbx+1]
0x180024931  test    r8, r8
0x180024934  jz      short loc_180024984
0x180024936  mov     rdx, [rsi]
0x180024939  cmp     r8, 7FFFFFFFh
0x180024940  ja      short loc_18002494B
0x180024942  cmp     rbx, 7FFFFFFEh
0x180024949  jbe     short loc_180024951
0x18002494b  mov     [rdx], r14w
0x18002494f  jmp     short loc_180024984
0x180024951  mov     rax, rbx
0x180024954  test    rax, rax
0x180024957  jz      short loc_180024975
0x180024959  movzx   ecx, word ptr [rdi]
0x18002495c  test    cx, cx
0x18002495f  jz      short loc_180024975
0x180024961  mov     [rdx], cx
0x180024964  add     rdi, 2
0x180024968  add     rdx, 2
0x18002496c  dec     rax
0x18002496f  sub     r8, 1
0x180024973  jnz     short loc_180024954
0x180024975  test    r8, r8
0x180024978  lea     rcx, [rdx-2]
0x18002497c  cmovnz  rcx, rdx
0x180024980  mov     [rcx], r14w
0x180024984  mov     [rsi+8], rbx
0x180024988  jmp     short loc_180024992
0x18002498a  mov     ebp, r14d
0x18002498d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180024992  mov     eax, ebp
0x180024994  add     rsp, 20h
0x180024998  pop     r14
0x18002499a  pop     rdi
0x18002499b  pop     rsi
0x18002499c  pop     rbp
0x18002499d  pop     rbx
0x18002499e  retn
```
