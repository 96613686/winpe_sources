# av_bprintf

- ea: `0x18002ea70`
- end: `0x18002eb22`
- name: `av_bprintf`
- size: `178`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002e5a0`
- `0x18002e940`
- `0x180031ab0`
- `0x180032310`
- `0x180033130`
- `0x1800334a4`
- `0x180042f08`
- `0x180043010`

## callees

- `0x18002cf34`
- `0x18002e3c0`
- `0x18002e888`
- `0x18002ea70`
- `0x180078c0e`

## pseudocode

```c
__int64 av_bprintf(__int64 a1, const char *a2, ...)
{
  const char *v2; // rsi
  _QWORD *v4; // r14
  unsigned int v5; // edi
  unsigned int v6; // edx
  unsigned int v7; // edi
  char *v8; // rdx
  int v9; // esi
  __int64 result; // rax
  va_list va; // [rsp+80h] [rbp+18h] BYREF

  va_start(va, a2);
  v2 = a2;
  v4 = (_QWORD *)sub_18002CF34();
  while ( 1 )
  {
    v5 = *(_DWORD *)(a1 + 12);
    v6 = v5;
    if ( *(_DWORD *)(a1 + 8) <= v5 )
      v6 = *(_DWORD *)(a1 + 8);
    v7 = v5 - v6;
    v8 = v7 ? (char *)(*(_QWORD *)a1 + *(unsigned int *)(a1 + 8)) : 0LL;
    v9 = _stdio_common_vsprintf(*v4 | 2LL, v8, v7, v2, 0, va);
    result = 0xFFFFFFFFLL;
    if ( v9 < 0 )
      v9 = -1;
    if ( v9 <= 0 )
      break;
    if ( v9 < v7 || (_mm_lfence(), (unsigned int)sub_18002E3C0(a1, (unsigned int)v9)) )
    {
      _mm_lfence();
      return sub_18002E888(a1, (unsigned int)v9);
    }
    v2 = a2;
  }
  return result;
}

```

## disassembly

```asm
0x18002ea70  mov     [rsp+arg_8], rdx
0x18002ea75  mov     qword ptr [rsp+arg_10], r8
0x18002ea7a  mov     [rsp+arg_18], r9
0x18002ea7f  push    rbx
0x18002ea80  push    rsi
0x18002ea81  push    rdi
0x18002ea82  push    r14
0x18002ea84  sub     rsp, 48h
0x18002ea88  mov     rsi, rdx
0x18002ea8b  mov     rbx, rcx
0x18002ea8e  call    sub_18002CF34
0x18002ea93  mov     r14, rax
0x18002ea96  mov     edi, [rbx+0Ch]
0x18002ea99  mov     edx, edi
0x18002ea9b  cmp     [rbx+8], edi
0x18002ea9e  cmovbe  edx, [rbx+8]
0x18002eaa2  sub     edi, edx
0x18002eaa4  jz      short loc_18002EAAE
0x18002eaa6  mov     edx, [rbx+8]
0x18002eaa9  add     rdx, [rbx]
0x18002eaac  jmp     short loc_18002EAB0
0x18002eaae  xor     edx, edx; Buffer
0x18002eab0  mov     rcx, [r14]
0x18002eab3  lea     rax, [rsp+68h+arg_10]
0x18002eabb  mov     [rsp+68h+ArgList], rax; ArgList
0x18002eac0  or      rcx, 2; Options
0x18002eac4  mov     r8d, edi; BufferCount
0x18002eac7  mov     r9, rsi; Format
0x18002eaca  mov     [rsp+68h+Locale], 0; Locale
0x18002ead3  call    __stdio_common_vsprintf
0x18002ead8  mov     esi, eax
0x18002eada  mov     [rsp+68h+var_38], 0
0x18002eae3  or      eax, 0FFFFFFFFh
0x18002eae6  test    esi, esi
0x18002eae8  cmovs   esi, eax
0x18002eaeb  test    esi, esi
0x18002eaed  jle     short loc_18002EB18
0x18002eaef  cmp     esi, edi
0x18002eaf1  jb      short loc_18002EB0B
0x18002eaf3  lfence
0x18002eaf6  mov     edx, esi
0x18002eaf8  mov     rcx, rbx
0x18002eafb  call    sub_18002E3C0
0x18002eb00  test    eax, eax
0x18002eb02  jnz     short loc_18002EB0B
0x18002eb04  mov     rsi, [rsp+68h+arg_8]
0x18002eb09  jmp     short loc_18002EA96
0x18002eb0b  lfence
0x18002eb0e  mov     edx, esi
0x18002eb10  mov     rcx, rbx
0x18002eb13  call    sub_18002E888
0x18002eb18  add     rsp, 48h
0x18002eb1c  pop     r14
0x18002eb1e  pop     rdi
0x18002eb1f  pop     rsi
0x18002eb20  pop     rbx
0x18002eb21  retn
```
