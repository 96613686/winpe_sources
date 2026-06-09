# WPP_SF_iiZd

- ea: `0x1400185a0`
- end: `0x140018664`
- name: `WPP_SF_iiZd`
- size: `196`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c444`
- `0x1400108e0`
- `0x140012040`
- `0x1400122fc`
- `0x14001250c`
- `0x140014fe4`
- `0x14001742c`
- `0x14001d058`
- `0x140024b60`
- `0x14002d960`
- `0x14002fd94`
- `0x140030e10`
- `0x14003c7e8`
- `0x14003ca54`
- `0x14003cde0`
- `0x14003cfb4`
- `0x14003eba8`

## callees

- `0x1400185a0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14001864d`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14001864d`

## pseudocode

```c
ULONG WPP_SF_iiZd(TRACEHANDLE a1, USHORT a2, const GUID *a3, ...)
{
  const wchar_t *v3; // rax
  __int64 v4; // r9
  const wchar_t *v5; // r10
  __int64 v7; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+A8h] [rbp+20h]
  __int64 v9; // [rsp+B0h] [rbp+28h] BYREF
  va_list va1; // [rsp+B0h] [rbp+28h]
  unsigned __int16 *v11; // [rsp+B8h] [rbp+30h]
  va_list va2; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v7 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v9 = va_arg(va2, _QWORD);
  v11 = va_arg(va2, unsigned __int16 *);
  v3 = v11;
  if ( v11 )
  {
    v4 = *v11;
    if ( *v11 )
    {
      v5 = (const wchar_t *)*((_QWORD *)v11 + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v4 = 8;
  }
  v5 = L"NULL";
LABEL_6:
  if ( !v11 )
    v3 = L"\b";
  return TraceMessage(a1, 0x2Bu, a3, a2, va, 8, va1, 8, v3, 2, v5, v4, va2, 4, 0);
}

```

## disassembly

```asm
0x1400185a0  mov     [rsp+arg_0], rbx
0x1400185a5  mov     [rsp+arg_18], r9
0x1400185aa  push    rdi
0x1400185ab  sub     rsp, 80h
0x1400185b2  mov     rax, [rsp+88h+arg_28]
0x1400185ba  xor     ebx, ebx
0x1400185bc  mov     edi, 8
0x1400185c1  test    rax, rax
0x1400185c4  jz      short loc_1400185D5
0x1400185c6  movzx   r9d, word ptr [rax]
0x1400185ca  cmp     [rax], bx
0x1400185cd  jz      short loc_1400185D8
0x1400185cf  mov     r10, [rax+8]
0x1400185d3  jmp     short loc_1400185DF
0x1400185d5  mov     r9, rdi
0x1400185d8  lea     r10, aNull_1; "NULL"
0x1400185df  mov     [rsp+88h+var_18], rbx
0x1400185e4  lea     r11, asc_14004409C; "\b"
0x1400185eb  mov     [rsp+88h+var_20], 4
0x1400185f4  test    rax, rax
0x1400185f7  cmovz   rax, r11
0x1400185fb  lea     r11, [rsp+88h+arg_30]
0x140018603  mov     [rsp+88h+var_28], r11
0x140018608  mov     [rsp+88h+var_30], r9
0x14001860d  mov     [rsp+88h+var_38], r10
0x140018612  mov     [rsp+88h+var_40], 2
0x14001861b  mov     [rsp+88h+var_48], rax
0x140018620  lea     rax, [rsp+88h+arg_20]
0x140018628  mov     [rsp+88h+var_50], rdi
0x14001862d  mov     [rsp+88h+var_58], rax
0x140018632  lea     rax, [rsp+88h+arg_18]
0x14001863a  movzx   r9d, dx; MessageNumber
0x14001863e  mov     edx, 2Bh ; '+'; MessageFlags
0x140018643  mov     [rsp+88h+var_60], rdi
0x140018648  mov     [rsp+88h+var_68], rax
0x14001864d  call    cs:__imp_TraceMessage
0x140018653  mov     rbx, [rsp+88h+arg_0]
0x14001865b  add     rsp, 80h
0x140018662  pop     rdi
0x140018663  retn
```
