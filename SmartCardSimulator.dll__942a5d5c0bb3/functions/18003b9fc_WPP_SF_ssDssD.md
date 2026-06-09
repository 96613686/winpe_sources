# WPP_SF_ssDssD

- ea: `0x18003b9fc`
- end: `0x18003bb1c`
- name: `WPP_SF_ssDssD`
- size: `288`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, int, char, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002de50`

## callees

- `0x18003b9fc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003bb05`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003bb05`

## string_xrefs

- `0x18003bae7`: `FileSystem::ElementaryFile::WriteFcpToDisk`

## pseudocode

```c
ULONG WPP_SF_ssDssD(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, const char *a4, int a5, ...)
{
  const char *v5; // r8
  __int64 v6; // rax
  __int64 v8; // r10
  __int64 v9; // rdx
  __int64 v10; // r11
  const char *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  bool v14; // zf
  __int64 v16; // [rsp+C8h] [rbp+30h] BYREF
  va_list va; // [rsp+C8h] [rbp+30h]
  const char *v18; // [rsp+D0h] [rbp+38h]
  const char *v19; // [rsp+D8h] [rbp+40h]
  va_list va1; // [rsp+E0h] [rbp+48h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v16 = va_arg(va1, _QWORD);
  v18 = va_arg(va1, const char *);
  v19 = va_arg(va1, const char *);
  v5 = v19;
  v6 = -1;
  v8 = 5;
  if ( v19 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v19[v9] );
    v10 = v9 + 1;
  }
  else
  {
    v10 = 5;
  }
  v11 = v18;
  if ( !v19 )
    v5 = "NULL";
  if ( v18 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v18[v12] );
    v13 = v12 + 1;
  }
  else
  {
    v13 = 5;
  }
  if ( !v18 )
    v11 = "NULL";
  v14 = a4 == 0;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v8 = v6 + 1;
    v14 = a4 == 0;
  }
  if ( v14 )
    a4 = "NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
           0x49u,
           a4,
           v8,
           "FileSystem::ElementaryFile::WriteFcpToDisk",
           43,
           va,
           4,
           v11,
           v13,
           v5,
           v10,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x18003b9fc  mov     [rsp+arg_0], rbx
0x18003ba01  push    rsi
0x18003ba02  sub     rsp, 90h
0x18003ba09  mov     r8, [rsp+98h+arg_38]
0x18003ba11  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003ba15  mov     rbx, rcx
0x18003ba18  mov     r10d, 5
0x18003ba1e  test    r8, r8
0x18003ba21  jz      short loc_18003BA36
0x18003ba23  mov     rdx, rax
0x18003ba26  inc     rdx
0x18003ba29  cmp     byte ptr [r8+rdx], 0
0x18003ba2e  jnz     short loc_18003BA26
0x18003ba30  lea     r11, [rdx+1]
0x18003ba34  jmp     short loc_18003BA39
0x18003ba36  mov     r11, r10
0x18003ba39  mov     rcx, [rsp+98h+arg_30]
0x18003ba41  lea     rsi, aNull; "NULL"
0x18003ba48  test    r8, r8
0x18003ba4b  cmovz   r8, rsi
0x18003ba4f  test    rcx, rcx
0x18003ba52  jz      short loc_18003BA65
0x18003ba54  mov     rdx, rax
0x18003ba57  inc     rdx
0x18003ba5a  cmp     byte ptr [rcx+rdx], 0
0x18003ba5e  jnz     short loc_18003BA57
0x18003ba60  inc     rdx
0x18003ba63  jmp     short loc_18003BA68
0x18003ba65  mov     rdx, r10
0x18003ba68  test    rcx, rcx
0x18003ba6b  cmovz   rcx, rsi
0x18003ba6f  test    r9, r9
0x18003ba72  jz      short loc_18003BA85
0x18003ba74  inc     rax
0x18003ba77  cmp     byte ptr [r9+rax], 0
0x18003ba7c  jnz     short loc_18003BA74
0x18003ba7e  lea     r10, [rax+1]
0x18003ba82  test    r9, r9
0x18003ba85  mov     [rsp+98h+var_18], 0
0x18003ba91  lea     rax, [rsp+98h+arg_40]
0x18003ba99  mov     [rsp+98h+var_20], 4
0x18003baa2  cmovz   r9, rsi
0x18003baa6  mov     [rsp+98h+var_28], rax
0x18003baab  mov     esi, 49h ; 'I'
0x18003bab0  mov     [rsp+98h+var_30], r11
0x18003bab5  lea     rax, [rsp+98h+arg_28]
0x18003babd  mov     [rsp+98h+var_38], r8
0x18003bac2  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids; MessageGuid
0x18003bac9  mov     [rsp+98h+var_40], rdx
0x18003bace  mov     [rsp+98h+var_48], rcx
0x18003bad3  lea     edx, [rsi-1Eh]; MessageFlags
0x18003bad6  mov     [rsp+98h+var_50], 4
0x18003badf  mov     rcx, rbx; LoggerHandle
0x18003bae2  mov     [rsp+98h+var_58], rax
0x18003bae7  lea     rax, aFilesystemElem_8; "FileSystem::ElementaryFile::WriteFcpToD"...
0x18003baee  mov     [rsp+98h+var_60], rdx
0x18003baf3  mov     [rsp+98h+var_68], rax
0x18003baf8  mov     [rsp+98h+var_70], r10
0x18003bafd  mov     [rsp+98h+var_78], r9
0x18003bb02  mov     r9d, esi; MessageNumber
0x18003bb05  call    cs:__imp_TraceMessage
0x18003bb0b  mov     rbx, [rsp+98h+arg_0]
0x18003bb13  add     rsp, 90h
0x18003bb1a  pop     rsi
0x18003bb1b  retn
```
