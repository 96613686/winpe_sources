# WPP_SF_ssDLLLLc

- ea: `0x18003b570`
- end: `0x18003b66f`
- name: `WPP_SF_ssDLLLLc`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002b1f0`

## callees

- `0x18003b570`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003b661`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003b661`

## string_xrefs

- `0x18003b63b`: `FileSystem::ElementaryFile::AccessCheck`

## pseudocode

```c
ULONG WPP_SF_ssDLLLLc(TRACEHANDLE a1, __int64 a2, __int64 a3, const char *a4, int a5, ...)
{
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v8; // [rsp+E8h] [rbp+30h] BYREF
  va_list va; // [rsp+E8h] [rbp+30h]
  __int64 v10; // [rsp+F0h] [rbp+38h] BYREF
  va_list va1; // [rsp+F0h] [rbp+38h]
  __int64 v12; // [rsp+F8h] [rbp+40h] BYREF
  va_list va2; // [rsp+F8h] [rbp+40h]
  __int64 v14; // [rsp+100h] [rbp+48h] BYREF
  va_list va3; // [rsp+100h] [rbp+48h]
  __int64 v16; // [rsp+108h] [rbp+50h] BYREF
  va_list va4; // [rsp+108h] [rbp+50h]
  va_list va5; // [rsp+110h] [rbp+58h] BYREF

  va_start(va5, a5);
  va_start(va4, a5);
  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v8 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v10 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v12 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v14 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v16 = va_arg(va5, _QWORD);
  if ( a4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a4[v5] );
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
           0x3Cu,
           a4,
           v6,
           "FileSystem::ElementaryFile::AccessCheck",
           40,
           va,
           4,
           va1,
           4,
           va2,
           4,
           va3,
           4,
           va4,
           4,
           va5,
           1,
           0);
}

```

## disassembly

```asm
0x18003b570  sub     rsp, 0B8h
0x18003b577  test    r9, r9
0x18003b57a  jz      short loc_18003B58F
0x18003b57c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003b580  inc     rax
0x18003b583  cmp     byte ptr [r9+rax], 0
0x18003b588  jnz     short loc_18003B580
0x18003b58a  inc     rax
0x18003b58d  jmp     short loc_18003B594
0x18003b58f  mov     eax, 5
0x18003b594  mov     [rsp+0B8h+var_18], 0
0x18003b5a0  lea     rdx, aNull; "NULL"
0x18003b5a7  mov     [rsp+0B8h+var_20], 1
0x18003b5b3  mov     r10d, 3Ch ; '<'
0x18003b5b9  test    r9, r9
0x18003b5bc  cmovz   r9, rdx
0x18003b5c0  lea     rdx, [rsp+0B8h+arg_50]
0x18003b5c8  mov     [rsp+0B8h+var_28], rdx
0x18003b5d0  lea     r8d, [r10-38h]
0x18003b5d4  mov     [rsp+0B8h+var_30], r8
0x18003b5dc  lea     rdx, [rsp+0B8h+arg_48]
0x18003b5e4  mov     [rsp+0B8h+var_38], rdx
0x18003b5ec  lea     rdx, [rsp+0B8h+arg_40]
0x18003b5f4  mov     [rsp+0B8h+var_40], r8
0x18003b5f9  mov     [rsp+0B8h+var_48], rdx
0x18003b5fe  lea     rdx, [rsp+0B8h+arg_38]
0x18003b606  mov     [rsp+0B8h+var_50], r8
0x18003b60b  mov     [rsp+0B8h+var_58], rdx
0x18003b610  lea     rdx, [rsp+0B8h+arg_30]
0x18003b618  mov     [rsp+0B8h+var_60], r8
0x18003b61d  mov     [rsp+0B8h+var_68], rdx
0x18003b622  lea     rdx, [rsp+0B8h+arg_28]
0x18003b62a  mov     [rsp+0B8h+var_70], r8
0x18003b62f  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids; MessageGuid
0x18003b636  mov     [rsp+0B8h+var_78], rdx
0x18003b63b  lea     rdx, aFilesystemElem_3; "FileSystem::ElementaryFile::AccessCheck"
0x18003b642  mov     [rsp+0B8h+var_80], 28h ; '('
0x18003b64b  mov     [rsp+0B8h+var_88], rdx
0x18003b650  lea     edx, [r10-11h]; MessageFlags
0x18003b654  mov     [rsp+0B8h+var_90], rax
0x18003b659  mov     [rsp+0B8h+var_98], r9
0x18003b65e  mov     r9d, r10d; MessageNumber
0x18003b661  call    cs:__imp_TraceMessage
0x18003b667  add     rsp, 0B8h
0x18003b66e  retn
```
