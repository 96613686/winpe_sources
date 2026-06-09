# WPP_SF_ss_HEX_LLLLc

- ea: `0x18003c678`
- end: `0x18003c7a1`
- name: `WPP_SF_ss_HEX_LLLLc`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002a650`

## callees

- `0x18003c678`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003c78a`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003c78a`

## string_xrefs

- `0x18003c765`: `FileSystem::DedicatedFile::AccessCheck`

## pseudocode

```c
ULONG WPP_SF_ss_HEX_LLLLc(TRACEHANDLE a1, __int64 a2, __int64 a3, const char *a4, int a5, _QWORD *a6, ...)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v9; // [rsp+100h] [rbp+38h] BYREF
  va_list va; // [rsp+100h] [rbp+38h]
  __int64 v11; // [rsp+108h] [rbp+40h] BYREF
  va_list va1; // [rsp+108h] [rbp+40h]
  __int64 v13; // [rsp+110h] [rbp+48h] BYREF
  va_list va2; // [rsp+110h] [rbp+48h]
  __int64 v15; // [rsp+118h] [rbp+50h] BYREF
  va_list va3; // [rsp+118h] [rbp+50h]
  va_list va4; // [rsp+120h] [rbp+58h] BYREF

  va_start(va4, a6);
  va_start(va3, a6);
  va_start(va2, a6);
  va_start(va1, a6);
  va_start(va, a6);
  v9 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v11 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v13 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v15 = va_arg(va4, _QWORD);
  if ( a4 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a4[v6] );
    v7 = v6 + 1;
  }
  else
  {
    v7 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
           0x6Du,
           a4,
           v7,
           "FileSystem::DedicatedFile::AccessCheck",
           39,
           a6 + 1,
           2,
           *a6,
           a6[1],
           va,
           4,
           va1,
           4,
           va2,
           4,
           va3,
           4,
           va4,
           1,
           0);
}

```

## disassembly

```asm
0x18003c678  mov     [rsp+arg_0], rbx
0x18003c67d  push    rdi
0x18003c67e  sub     rsp, 0C0h
0x18003c685  mov     rax, [rsp+0C8h+arg_28]
0x18003c68d  mov     r10, [rax]
0x18003c690  lea     rdx, [rax+8]
0x18003c694  mov     r8, [rdx]
0x18003c697  test    r9, r9
0x18003c69a  jz      short loc_18003C6AF
0x18003c69c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003c6a0  inc     rax
0x18003c6a3  cmp     byte ptr [r9+rax], 0
0x18003c6a8  jnz     short loc_18003C6A0
0x18003c6aa  inc     rax
0x18003c6ad  jmp     short loc_18003C6B4
0x18003c6af  mov     eax, 5
0x18003c6b4  mov     [rsp+0C8h+var_18], 0
0x18003c6c0  lea     r11, aNull; "NULL"
0x18003c6c7  mov     [rsp+0C8h+var_20], 1
0x18003c6d3  test    r9, r9
0x18003c6d6  mov     edi, 6Dh ; 'm'
0x18003c6db  cmovz   r9, r11
0x18003c6df  lea     r11, [rsp+0C8h+arg_50]
0x18003c6e7  mov     [rsp+0C8h+var_28], r11
0x18003c6ef  lea     r11, [rsp+0C8h+arg_48]
0x18003c6f7  lea     ebx, [rdi-69h]
0x18003c6fa  mov     [rsp+0C8h+var_30], rbx
0x18003c702  mov     [rsp+0C8h+var_38], r11
0x18003c70a  lea     r11, [rsp+0C8h+arg_40]
0x18003c712  mov     [rsp+0C8h+var_40], rbx
0x18003c71a  mov     [rsp+0C8h+var_48], r11
0x18003c722  lea     r11, [rsp+0C8h+arg_38]
0x18003c72a  mov     [rsp+0C8h+var_50], rbx
0x18003c72f  mov     [rsp+0C8h+var_58], r11
0x18003c734  lea     r11, [rsp+0C8h+arg_30]
0x18003c73c  mov     [rsp+0C8h+var_60], rbx
0x18003c741  mov     [rsp+0C8h+var_68], r11
0x18003c746  mov     [rsp+0C8h+var_70], r8
0x18003c74b  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids; MessageGuid
0x18003c752  mov     [rsp+0C8h+var_78], r10
0x18003c757  mov     [rsp+0C8h+var_80], 2
0x18003c760  mov     [rsp+0C8h+var_88], rdx
0x18003c765  lea     rdx, aFilesystemDedi_7; "FileSystem::DedicatedFile::AccessCheck"
0x18003c76c  mov     [rsp+0C8h+var_90], 27h ; '''
0x18003c775  mov     [rsp+0C8h+var_98], rdx
0x18003c77a  lea     edx, [rdi-42h]; MessageFlags
0x18003c77d  mov     [rsp+0C8h+var_A0], rax
0x18003c782  mov     [rsp+0C8h+var_A8], r9
0x18003c787  mov     r9d, edi; MessageNumber
0x18003c78a  call    cs:__imp_TraceMessage
0x18003c790  mov     rbx, [rsp+0C8h+arg_0]
0x18003c798  add     rsp, 0C0h
0x18003c79f  pop     rdi
0x18003c7a0  retn
```
