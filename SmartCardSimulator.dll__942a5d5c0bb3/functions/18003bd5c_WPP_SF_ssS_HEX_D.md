# WPP_SF_ssS_HEX_D

- ea: `0x18003bd5c`
- end: `0x18003be60`
- name: `WPP_SF_ssS_HEX_D`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002a9b4`

## callees

- `0x18003bd5c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003be4e`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003be4e`

## string_xrefs

- `0x18003be1d`: `FileSystem::DiskOperations::WriteFileToDisk`

## pseudocode

```c
ULONG WPP_SF_ssS_HEX_D(
        TRACEHANDLE a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        const wchar_t *a6,
        _QWORD *a7,
        ...)
{
  const wchar_t *v7; // r8
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rax
  va_list va; // [rsp+F8h] [rbp+40h] BYREF

  va_start(va, a7);
  v7 = a6;
  v8 = -1;
  if ( a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a6[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  if ( !a6 )
    v7 = L"NULL";
  if ( a4 )
  {
    do
      ++v8;
    while ( a4[v8] );
    v11 = v8 + 1;
  }
  else
  {
    v11 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
           0x20u,
           a4,
           v11,
           "FileSystem::DiskOperations::WriteFileToDisk",
           44,
           v7,
           v10,
           a7 + 1,
           2,
           *a7,
           a7[1],
           va,
           4,
           0);
}

```

## disassembly

```asm
0x18003bd5c  push    rbx
0x18003bd5e  push    rbp
0x18003bd5f  push    rsi
0x18003bd60  push    rdi
0x18003bd61  sub     rsp, 98h
0x18003bd68  mov     rax, [rsp+0B8h+arg_30]
0x18003bd70  xor     ebp, ebp
0x18003bd72  mov     r8, [rsp+0B8h+arg_28]
0x18003bd7a  mov     rbx, [rax]
0x18003bd7d  lea     r10, [rax+8]
0x18003bd81  mov     r11, [r10]
0x18003bd84  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003bd88  test    r8, r8
0x18003bd8b  jz      short loc_18003BDA4
0x18003bd8d  mov     rdx, rax
0x18003bd90  inc     rdx
0x18003bd93  cmp     [r8+rdx*2], bp
0x18003bd98  jnz     short loc_18003BD90
0x18003bd9a  lea     rdx, ds:2[rdx*2]
0x18003bda2  jmp     short loc_18003BDA9
0x18003bda4  mov     edx, 0Ah
0x18003bda9  test    r8, r8
0x18003bdac  lea     rdi, aNull_0; "NULL"
0x18003bdb3  cmovz   r8, rdi
0x18003bdb7  test    r9, r9
0x18003bdba  jz      short loc_18003BDCA
0x18003bdbc  inc     rax
0x18003bdbf  cmp     [r9+rax], bpl
0x18003bdc3  jnz     short loc_18003BDBC
0x18003bdc5  inc     rax
0x18003bdc8  jmp     short loc_18003BDCF
0x18003bdca  mov     eax, 5
0x18003bdcf  mov     [rsp+0B8h+var_38], rbp
0x18003bdd7  lea     rdi, aNull; "NULL"
0x18003bdde  mov     [rsp+0B8h+var_40], 4
0x18003bde7  test    r9, r9
0x18003bdea  mov     esi, 20h ; ' '
0x18003bdef  cmovz   r9, rdi
0x18003bdf3  lea     rdi, [rsp+0B8h+arg_38]
0x18003bdfb  mov     [rsp+0B8h+var_48], rdi
0x18003be00  mov     [rsp+0B8h+var_50], r11
0x18003be05  mov     [rsp+0B8h+var_58], rbx
0x18003be0a  mov     [rsp+0B8h+var_60], 2
0x18003be13  mov     [rsp+0B8h+var_68], r10
0x18003be18  mov     [rsp+0B8h+var_70], rdx
0x18003be1d  lea     rdx, aFilesystemDisk_3; "FileSystem::DiskOperations::WriteFileTo"...
0x18003be24  mov     [rsp+0B8h+var_78], r8
0x18003be29  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids; MessageGuid
0x18003be30  mov     [rsp+0B8h+var_80], 2Ch ; ','
0x18003be39  mov     [rsp+0B8h+var_88], rdx
0x18003be3e  lea     edx, [rsi+0Bh]; MessageFlags
0x18003be41  mov     [rsp+0B8h+var_90], rax
0x18003be46  mov     [rsp+0B8h+var_98], r9
0x18003be4b  mov     r9d, esi; MessageNumber
0x18003be4e  call    cs:__imp_TraceMessage
0x18003be54  add     rsp, 98h
0x18003be5b  pop     rdi
0x18003be5c  pop     rsi
0x18003be5d  pop     rbp
0x18003be5e  pop     rbx
0x18003be5f  retn
```
