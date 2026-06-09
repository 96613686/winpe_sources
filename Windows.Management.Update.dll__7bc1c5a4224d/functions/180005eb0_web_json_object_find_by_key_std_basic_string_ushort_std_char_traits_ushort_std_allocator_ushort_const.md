# web::json::object::find_by_key(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180005eb0`
- end: `0x180005fdc`
- name: `?find_by_key@object@json@web@@AEBA?AV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@std@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z`
- size: `300`
- prototype: `_QWORD *__fastcall(__int64 *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006530`

## callees

- `0x180003650`
- `0x1800036b0`
- `0x180005eb0`
- `0x180023098`

## pseudocode

```c
_QWORD *__fastcall web::json::object::find_by_key(__int64 *a1, _QWORD *a2, __int64 a3)
{
  __int64 v4; // rbx
  __int64 v6; // rdi
  const wchar_t *v8; // rdx
  const wchar_t *v9; // rcx
  size_t v10; // r8
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rdi

  v4 = *a1;
  v6 = a1[1];
  if ( *((_BYTE *)a1 + 24) )
  {
    for ( ; v4 != v6; v4 += 40 )
    {
      if ( *(_QWORD *)(a3 + 24) <= 7u )
        v8 = (const wchar_t *)a3;
      else
        v8 = *(const wchar_t **)a3;
      if ( *(_QWORD *)(v4 + 24) <= 7u )
        v9 = (const wchar_t *)v4;
      else
        v9 = *(const wchar_t **)v4;
      v10 = *(_QWORD *)(v4 + 16);
      if ( v10 == *(_QWORD *)(a3 + 16) && (!v10 || !wmemcmp(v9, v8, v10)) )
        break;
    }
  }
  else
  {
    v12 = (__int64)((unsigned __int128)((v6 - v4) * (__int128)0x6666666666666667LL) >> 64) >> 4;
    v13 = (v12 >> 63) + v12;
    while ( (__int64)v13 > 0 )
    {
      if ( (unsigned __int8)std::operator<<unsigned short>(v4 + 40 * (v13 >> 1), a3) )
      {
        v4 += 40 * (v13 >> 1) + 40;
        v13 += -1LL - (v13 >> 1);
      }
      else
      {
        v13 >>= 1;
      }
    }
    if ( v4 != a1[1] && (unsigned __int8)std::operator!=<unsigned short>(a3, v4) )
    {
      *a2 = a1[1];
      return a2;
    }
  }
  *a2 = v4;
  return a2;
}

```

## disassembly

```asm
0x180005eb0  mov     [rsp+arg_10], rbx
0x180005eb5  mov     [rsp+arg_18], rdi
0x180005eba  push    r12
0x180005ebc  push    r14
0x180005ebe  push    r15
0x180005ec0  sub     rsp, 20h
0x180005ec4  cmp     byte ptr [rcx+18h], 0
0x180005ec8  mov     r14, r8
0x180005ecb  mov     rbx, [rcx]
0x180005ece  mov     r12, rdx
0x180005ed1  mov     rdi, [rcx+8]
0x180005ed5  mov     r15, rcx
0x180005ed8  jz      short loc_180005F3B
0x180005eda  cmp     rbx, rdi
0x180005edd  jz      short loc_180005F1F
0x180005edf  nop
0x180005ee0  cmp     qword ptr [r14+18h], 7
0x180005ee5  jbe     short loc_180005EEC
0x180005ee7  mov     rdx, [r14]
0x180005eea  jmp     short loc_180005EEF
0x180005eec  mov     rdx, r14; S2
0x180005eef  cmp     qword ptr [rbx+18h], 7
0x180005ef4  jbe     short loc_180005EFB
0x180005ef6  mov     rcx, [rbx]
0x180005ef9  jmp     short loc_180005EFE
0x180005efb  mov     rcx, rbx; S1
0x180005efe  mov     r8, [rbx+10h]; N
0x180005f02  cmp     r8, [r14+10h]
0x180005f06  jnz     short loc_180005F16
0x180005f08  test    r8, r8
0x180005f0b  jz      short loc_180005F1F
0x180005f0d  call    wmemcmp
0x180005f12  test    eax, eax
0x180005f14  jz      short loc_180005F1F
0x180005f16  add     rbx, 28h ; '('
0x180005f1a  cmp     rbx, rdi
0x180005f1d  jnz     short loc_180005EE0
0x180005f1f  mov     [r12], rbx
0x180005f23  mov     rbx, [rsp+38h+arg_10]
0x180005f28  mov     rax, r12
0x180005f2b  mov     rdi, [rsp+38h+arg_18]
0x180005f30  add     rsp, 20h
0x180005f34  pop     r15
0x180005f36  pop     r14
0x180005f38  pop     r12
0x180005f3a  retn
0x180005f3b  sub     rdi, rbx
0x180005f3e  mov     rax, 6666666666666667h
0x180005f48  imul    rdi
0x180005f4b  mov     rdi, rdx
0x180005f4e  sar     rdi, 4
0x180005f52  mov     rax, rdi
0x180005f55  shr     rax, 3Fh
0x180005f59  add     rdi, rax
0x180005f5c  test    rdi, rdi
0x180005f5f  jle     short loc_180005FB2
0x180005f61  mov     [rsp+38h+arg_0], rbp
0x180005f66  mov     [rsp+38h+arg_8], rsi
0x180005f6b  nop     dword ptr [rax+rax+00h]
0x180005f70  mov     rsi, rdi
0x180005f73  mov     rdx, r14
0x180005f76  shr     rsi, 1
0x180005f79  lea     rax, [rsi+rsi*4]
0x180005f7d  lea     rbp, [rbx+rax*8]
0x180005f81  mov     rcx, rbp
0x180005f84  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180005f89  test    al, al
0x180005f8b  jz      short loc_180005FA0
0x180005f8d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005f94  lea     rbx, [rbp+28h]
0x180005f98  sub     rax, rsi
0x180005f9b  add     rdi, rax
0x180005f9e  jmp     short loc_180005FA3
0x180005fa0  mov     rdi, rsi
0x180005fa3  test    rdi, rdi
0x180005fa6  jg      short loc_180005F70
0x180005fa8  mov     rsi, [rsp+38h+arg_8]
0x180005fad  mov     rbp, [rsp+38h+arg_0]
0x180005fb2  cmp     rbx, [r15+8]
0x180005fb6  jz      loc_180005F1F
0x180005fbc  mov     rdx, rbx
0x180005fbf  mov     rcx, r14
0x180005fc2  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator!=<ushort>(std::wstring const &,std::wstring const &)
0x180005fc7  test    al, al
0x180005fc9  jz      loc_180005F1F
0x180005fcf  mov     rax, [r15+8]
0x180005fd3  mov     [r12], rax
0x180005fd7  jmp     loc_180005F23
```
