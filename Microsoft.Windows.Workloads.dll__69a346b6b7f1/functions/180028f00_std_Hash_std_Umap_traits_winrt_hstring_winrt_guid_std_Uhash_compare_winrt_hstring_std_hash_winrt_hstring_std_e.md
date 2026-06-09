# std::_Hash<std::_Umap_traits<winrt::hstring,winrt::guid,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::guid>>,0>>::_Find_last<winrt::hstring>(winrt::hstring const &,unsigned __int64)

- ea: `0x180028f00`
- end: `0x180028ff8`
- name: `??$_Find_last@Uhstring@winrt@@@?$_Hash@V?$_Umap_traits@Uhstring@winrt@@Uguid@2@V?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@Uguid@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUhstring@winrt@@Uguid@2@@std@@PEAX@std@@@1@AEBUhstring@winrt@@_K@Z`
- size: `248`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180025730`

## callees

- `0x180015250`
- `0x180028f00`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<winrt::hstring,winrt::guid,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::guid>>,0>>::_Find_last<winrt::hstring>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 *a3,
        __int64 a4)
{
  _QWORD *v4; // rax
  _QWORD *v7; // rdx
  _QWORD *v8; // rbx
  _QWORD *result; // rax
  _QWORD *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rcx
  const wchar_t *v13; // rdx
  __int64 v14; // rax
  size_t v15; // r8
  const wchar_t *v16; // r9

  v4 = (_QWORD *)a1[1];
  v7 = (_QWORD *)(a1[3] + 16 * (a4 & a1[6]));
  v8 = (_QWORD *)v7[1];
  if ( v8 == v4 )
  {
    *a2 = v4;
    result = a2;
    a2[1] = 0;
  }
  else
  {
    v10 = (_QWORD *)*v7;
    while ( 1 )
    {
      v11 = v8[2];
      if ( v11 )
      {
        v12 = *(unsigned int *)(v11 + 4);
        v13 = *(const wchar_t **)(v11 + 16);
      }
      else
      {
        v12 = 0;
        v13 = &Src;
      }
      v14 = *a3;
      if ( *a3 )
      {
        v15 = *(unsigned int *)(v14 + 4);
        v16 = *(const wchar_t **)(v14 + 16);
      }
      else
      {
        v15 = 0;
        v16 = &Src;
      }
      if ( v15 == v12 && (!v15 || wmemcmp(v16, v13, v15) == 0) )
        break;
      if ( v8 == v10 )
      {
        *a2 = v8;
        a2[1] = 0;
        return a2;
      }
      v8 = (_QWORD *)v8[1];
    }
    *a2 = *v8;
    a2[1] = v8;
    return a2;
  }
  return result;
}

```

## disassembly

```asm
0x180028f00  mov     [rsp+arg_8], rbx
0x180028f05  mov     [rsp+arg_10], rdi
0x180028f0a  push    r14
0x180028f0c  sub     rsp, 20h
0x180028f10  mov     rax, [rcx+8]
0x180028f14  mov     rdi, rdx
0x180028f17  mov     rdx, [rcx+30h]
0x180028f1b  mov     r14, r8
0x180028f1e  and     rdx, r9
0x180028f21  shl     rdx, 4
0x180028f25  add     rdx, [rcx+18h]
0x180028f29  mov     rbx, [rdx+8]
0x180028f2d  cmp     rbx, rax
0x180028f30  jnz     short loc_180028F51
0x180028f32  mov     [rdi], rax
0x180028f35  mov     rax, rdi
0x180028f38  mov     qword ptr [rdi+8], 0
0x180028f40  mov     rbx, [rsp+28h+arg_8]
0x180028f45  mov     rdi, [rsp+28h+arg_10]
0x180028f4a  add     rsp, 20h
0x180028f4e  pop     r14
0x180028f50  retn
0x180028f51  mov     [rsp+28h+arg_0], rsi
0x180028f56  mov     rsi, [rdx]
0x180028f59  nop     dword ptr [rax+00000000h]
0x180028f60  mov     rax, [rbx+10h]
0x180028f64  test    rax, rax
0x180028f67  jz      short loc_180028F72
0x180028f69  mov     ecx, [rax+4]
0x180028f6c  mov     rdx, [rax+10h]
0x180028f70  jmp     short loc_180028F7B
0x180028f72  xor     ecx, ecx
0x180028f74  lea     rdx, Src; S2
0x180028f7b  mov     rax, [r14]
0x180028f7e  test    rax, rax
0x180028f81  jz      short loc_180028F8D
0x180028f83  mov     r8d, [rax+4]
0x180028f87  mov     r9, [rax+10h]
0x180028f8b  jmp     short loc_180028F97
0x180028f8d  xor     r8d, r8d; N
0x180028f90  lea     r9, Src
0x180028f97  cmp     r8, rcx
0x180028f9a  jz      short loc_180028FA3
0x180028f9c  mov     ecx, 1
0x180028fa1  jmp     short loc_180028FB9
0x180028fa3  test    r8, r8
0x180028fa6  jnz     short loc_180028FAC
0x180028fa8  xor     ecx, ecx
0x180028faa  jmp     short loc_180028FB9
0x180028fac  mov     rcx, r9; S1
0x180028faf  call    wmemcmp
0x180028fb4  test    eax, eax
0x180028fb6  setnz   cl
0x180028fb9  test    cl, cl
0x180028fbb  jz      short loc_180028FD5
0x180028fbd  cmp     rbx, rsi
0x180028fc0  jz      short loc_180028FC8
0x180028fc2  mov     rbx, [rbx+8]
0x180028fc6  jmp     short loc_180028F60
0x180028fc8  mov     [rdi], rbx
0x180028fcb  mov     qword ptr [rdi+8], 0
0x180028fd3  jmp     short loc_180028FDF
0x180028fd5  mov     rax, [rbx]
0x180028fd8  mov     [rdi], rax
0x180028fdb  mov     [rdi+8], rbx
0x180028fdf  mov     rsi, [rsp+28h+arg_0]
0x180028fe4  mov     rax, rdi
0x180028fe7  mov     rdi, [rsp+28h+arg_10]
0x180028fec  mov     rbx, [rsp+28h+arg_8]
0x180028ff1  add     rsp, 20h
0x180028ff5  pop     r14
0x180028ff7  retn
```
