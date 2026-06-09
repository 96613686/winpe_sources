# std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>,0>>::_Find_lower_bound<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x14000ecf0`
- end: `0x14000ed91`
- name: `??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z`
- size: `161`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000f2d4`
- `0x14000fccc`

## callees

- `0x14000ecf0`
- `0x140011d08`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,0>>::_Find_lower_bound<std::wstring>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  const wchar_t *v7; // rcx
  unsigned __int64 v8; // r14
  const wchar_t *v9; // rdx
  unsigned __int64 v10; // rbp
  size_t v11; // r8
  int v12; // eax
  int v13; // eax

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    v7 = (const wchar_t *)(v6 + 4);
    v8 = *(_QWORD *)(a3 + 16);
    if ( *(_QWORD *)(a3 + 24) <= 7u )
      v9 = (const wchar_t *)a3;
    else
      v9 = *(const wchar_t **)a3;
    v10 = v6[6];
    if ( (unsigned __int64)v6[7] > 7 )
      v7 = *(const wchar_t **)v7;
    v11 = *(_QWORD *)(a3 + 16);
    if ( v8 >= v10 )
      v11 = v6[6];
    v12 = wmemcmp(v7, v9, v11);
    if ( v12 )
    {
      if ( v12 < 0 )
        goto LABEL_15;
    }
    else if ( v10 < v8 )
    {
LABEL_15:
      v6 += 2;
      v13 = 0;
      goto LABEL_12;
    }
    a2[2] = v6;
    v13 = 1;
LABEL_12:
    *((_DWORD *)a2 + 2) = v13;
  }
  return a2;
}

```

## disassembly

```asm
0x14000ecf0  push    rbx
0x14000ecf2  push    rbp
0x14000ecf3  push    rsi
0x14000ecf4  push    rdi
0x14000ecf5  push    r14
0x14000ecf7  sub     rsp, 20h
0x14000ecfb  mov     rax, [rcx]
0x14000ecfe  mov     rsi, r8
0x14000ed01  mov     rdi, rdx
0x14000ed04  mov     r9, [rax+8]
0x14000ed08  mov     [rdx], r9
0x14000ed0b  mov     rbx, r9
0x14000ed0e  mov     qword ptr [rdx+8], 0
0x14000ed16  mov     rax, [rcx]
0x14000ed19  mov     [rdx+10h], rax
0x14000ed1d  cmp     byte ptr [r9+19h], 0
0x14000ed22  jnz     short loc_14000ED76
0x14000ed24  mov     [rdi], rbx
0x14000ed27  lea     rcx, [rbx+20h]
0x14000ed2b  cmp     qword ptr [rsi+18h], 7
0x14000ed30  mov     r14, [rsi+10h]
0x14000ed34  jbe     short loc_14000ED3B
0x14000ed36  mov     rdx, [rsi]
0x14000ed39  jmp     short loc_14000ED3E
0x14000ed3b  mov     rdx, rsi; S2
0x14000ed3e  cmp     qword ptr [rcx+18h], 7
0x14000ed43  mov     rbp, [rbx+30h]
0x14000ed47  jbe     short loc_14000ED4C
0x14000ed49  mov     rcx, [rcx]; S1
0x14000ed4c  cmp     r14, rbp
0x14000ed4f  mov     r8, r14
0x14000ed52  cmovnb  r8, rbp; N
0x14000ed56  call    wmemcmp
0x14000ed5b  test    eax, eax
0x14000ed5d  jz      short loc_14000ED84
0x14000ed5f  js      short loc_14000ED89
0x14000ed61  mov     [rdi+10h], rbx
0x14000ed65  mov     eax, 1
0x14000ed6a  mov     [rdi+8], eax
0x14000ed6d  mov     rbx, [rbx]
0x14000ed70  cmp     byte ptr [rbx+19h], 0
0x14000ed74  jz      short loc_14000ED24
0x14000ed76  mov     rax, rdi
0x14000ed79  add     rsp, 20h
0x14000ed7d  pop     r14
0x14000ed7f  pop     rdi
0x14000ed80  pop     rsi
0x14000ed81  pop     rbp
0x14000ed82  pop     rbx
0x14000ed83  retn
0x14000ed84  cmp     rbp, r14
0x14000ed87  jnb     short loc_14000ED61
0x14000ed89  add     rbx, 10h
0x14000ed8d  xor     eax, eax
0x14000ed8f  jmp     short loc_14000ED6A
```
