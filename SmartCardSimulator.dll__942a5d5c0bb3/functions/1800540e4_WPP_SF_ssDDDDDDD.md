# WPP_SF_ssDDDDDDD

- ea: `0x1800540e4`
- end: `0x1800541f7`
- name: `WPP_SF_ssDDDDDDD`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800536f0`

## callees

- `0x1800540e4`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800541e9`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800541e9`

## string_xrefs

- `0x1800541c3`: `Reader::SetParameters`

## pseudocode

```c
ULONG WPP_SF_ssDDDDDDD(TRACEHANDLE a1, __int64 a2, __int64 a3, const char *a4, int a5, ...)
{
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v8; // [rsp+F8h] [rbp+30h] BYREF
  va_list va; // [rsp+F8h] [rbp+30h]
  __int64 v10; // [rsp+100h] [rbp+38h] BYREF
  va_list va1; // [rsp+100h] [rbp+38h]
  __int64 v12; // [rsp+108h] [rbp+40h] BYREF
  va_list va2; // [rsp+108h] [rbp+40h]
  __int64 v14; // [rsp+110h] [rbp+48h] BYREF
  va_list va3; // [rsp+110h] [rbp+48h]
  __int64 v16; // [rsp+118h] [rbp+50h] BYREF
  va_list va4; // [rsp+118h] [rbp+50h]
  __int64 v18; // [rsp+120h] [rbp+58h] BYREF
  va_list va5; // [rsp+120h] [rbp+58h]
  va_list va6; // [rsp+128h] [rbp+60h] BYREF

  va_start(va6, a5);
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
  va_copy(va6, va5);
  v18 = va_arg(va6, _QWORD);
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
           &WPP_3c9f0efd45c43d85f1bb3a582e5a54d3_Traceguids,
           0xFu,
           a4,
           v6,
           "Reader::SetParameters",
           22,
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
           4,
           va6,
           4,
           0);
}

```

## disassembly

```asm
0x1800540e4  sub     rsp, 0C8h
0x1800540eb  test    r9, r9
0x1800540ee  jz      short loc_180054103
0x1800540f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800540f4  inc     rax
0x1800540f7  cmp     byte ptr [r9+rax], 0
0x1800540fc  jnz     short loc_1800540F4
0x1800540fe  inc     rax
0x180054101  jmp     short loc_180054108
0x180054103  mov     eax, 5
0x180054108  mov     [rsp+0C8h+var_18], 0
0x180054114  lea     rdx, aNull; "NULL"
0x18005411b  mov     r10d, 0Fh
0x180054121  test    r9, r9
0x180054124  cmovz   r9, rdx
0x180054128  lea     rdx, [rsp+0C8h+arg_58]
0x180054130  lea     r8d, [r10-0Bh]
0x180054134  mov     [rsp+0C8h+var_20], r8
0x18005413c  mov     [rsp+0C8h+var_28], rdx
0x180054144  lea     rdx, [rsp+0C8h+arg_50]
0x18005414c  mov     [rsp+0C8h+var_30], r8
0x180054154  mov     [rsp+0C8h+var_38], rdx
0x18005415c  lea     rdx, [rsp+0C8h+arg_48]
0x180054164  mov     [rsp+0C8h+var_40], r8
0x18005416c  mov     [rsp+0C8h+var_48], rdx
0x180054174  lea     rdx, [rsp+0C8h+arg_40]
0x18005417c  mov     [rsp+0C8h+var_50], r8
0x180054181  mov     [rsp+0C8h+var_58], rdx
0x180054186  lea     rdx, [rsp+0C8h+arg_38]
0x18005418e  mov     [rsp+0C8h+var_60], r8
0x180054193  mov     [rsp+0C8h+var_68], rdx
0x180054198  lea     rdx, [rsp+0C8h+arg_30]
0x1800541a0  mov     [rsp+0C8h+var_70], r8
0x1800541a5  mov     [rsp+0C8h+var_78], rdx
0x1800541aa  lea     rdx, [rsp+0C8h+arg_28]
0x1800541b2  mov     [rsp+0C8h+var_80], r8
0x1800541b7  lea     r8, WPP_3c9f0efd45c43d85f1bb3a582e5a54d3_Traceguids; MessageGuid
0x1800541be  mov     [rsp+0C8h+var_88], rdx
0x1800541c3  lea     rdx, aReaderSetparam; "Reader::SetParameters"
0x1800541ca  mov     [rsp+0C8h+var_90], 16h
0x1800541d3  mov     [rsp+0C8h+var_98], rdx
0x1800541d8  lea     edx, [r10+1Ch]; MessageFlags
0x1800541dc  mov     [rsp+0C8h+var_A0], rax
0x1800541e1  mov     [rsp+0C8h+var_A8], r9
0x1800541e6  mov     r9d, r10d; MessageNumber
0x1800541e9  call    cs:__imp_TraceMessage
0x1800541ef  add     rsp, 0C8h
0x1800541f6  retn
```
