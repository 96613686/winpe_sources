# WPP_SF_Zd

- ea: `0x14000b7f8`
- end: `0x14000b877`
- name: `WPP_SF_Zd`
- size: `127`
- prototype: ``
- caller_count: `57`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b490`
- `0x14000c444`
- `0x14000c648`
- `0x14000c7e0`
- `0x14000c8f8`
- `0x14000d5f0`
- `0x14000de58`
- `0x14000e9a4`
- `0x14000ea7c`
- `0x14000ef74`
- `0x14000f108`
- `0x14000f2e4`
- `0x14000f728`
- `0x14000f97c`
- `0x1400108e0`
- `0x140010d1c`
- `0x1400122fc`
- `0x1400127dc`
- `0x140015648`
- `0x140015ff0`
- `0x1400164c8`
- `0x140016d18`
- `0x140017120`
- `0x14001742c`
- `0x1400192c4`
- `0x14001a270`
- `0x14001d5a4`
- `0x14001d7ec`
- `0x14001da7c`
- `0x14001dbf0`
- `0x140020390`
- `0x1400211a4`
- `0x140021a28`
- `0x140022878`
- `0x1400237c8`
- `0x140023bb8`
- `0x1400243e8`
- `0x14002dff4`
- `0x14002e86c`
- `0x14002eef0`
- `0x140030e10`
- `0x140031e04`
- `0x1400367c0`
- `0x14003c7e8`
- `0x14003ca54`
- `0x14003cfb4`
- `0x14003d2ec`
- `0x14003d800`
- `0x14003da18`
- `0x14003db78`

## callees

- `0x14000b7f8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000b86b`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000b86b`

## pseudocode

```c
ULONG WPP_SF_Zd(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4, ...)
{
  __int64 v4; // rax
  const wchar_t *v5; // r10
  va_list va; // [rsp+90h] [rbp+28h] BYREF

  va_start(va, a4);
  if ( a4 )
  {
    v4 = *a4;
    if ( *a4 )
    {
      v5 = (const wchar_t *)*((_QWORD *)a4 + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v4 = 8;
  }
  v5 = L"NULL";
LABEL_6:
  if ( !a4 )
    a4 = L"\b";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, 2, v5, v4, va, 4, 0);
}

```

## disassembly

```asm
0x14000b7f8  push    rbx
0x14000b7fa  sub     rsp, 60h
0x14000b7fe  xor     ebx, ebx
0x14000b800  test    r9, r9
0x14000b803  jz      short loc_14000B815
0x14000b805  movzx   eax, word ptr [r9]
0x14000b809  cmp     [r9], bx
0x14000b80d  jz      short loc_14000B81A
0x14000b80f  mov     r10, [r9+8]
0x14000b813  jmp     short loc_14000B821
0x14000b815  mov     eax, 8
0x14000b81a  lea     r10, aNull_1; "NULL"
0x14000b821  mov     [rsp+68h+var_18], rbx
0x14000b826  lea     r11, asc_14004409C; "\b"
0x14000b82d  mov     [rsp+68h+var_20], 4
0x14000b836  test    r9, r9
0x14000b839  cmovz   r9, r11
0x14000b83d  lea     r11, [rsp+68h+arg_20]
0x14000b845  mov     [rsp+68h+var_28], r11
0x14000b84a  mov     [rsp+68h+var_30], rax
0x14000b84f  mov     [rsp+68h+var_38], r10
0x14000b854  mov     [rsp+68h+var_40], 2
0x14000b85d  mov     [rsp+68h+var_48], r9
0x14000b862  movzx   r9d, dx; MessageNumber
0x14000b866  mov     edx, 2Bh ; '+'; MessageFlags
0x14000b86b  call    cs:__imp_TraceMessage
0x14000b871  add     rsp, 60h
0x14000b875  pop     rbx
0x14000b876  retn
```
