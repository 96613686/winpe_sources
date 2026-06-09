# CCabDecompressor::CabDecompressorFileWrite(__int64,void const *,uint)

- ea: `0x1800599b0`
- end: `0x180059aa1`
- name: `?CabDecompressorFileWrite@CCabDecompressor@@CAI_JPEBXI@Z`
- size: `241`
- prototype: `__int64 __fastcall(INT_PTR hf, void *pv, __int64 cb)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800110fc`
- `0x1800128ec`
- `0x1800599b0`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a02`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800599f4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800599f4`

## string_xrefs

- `0x180059a5e`: `Write decompressed file to buffer`
- `0x180059a20`: `CabDecompressorFileWrite - WriteFile`
- `0x180059a3d`: `CabDecompressorFileWrite - invalid buffer`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::CabDecompressorFileWrite(INT_PTR hf, void *pv, __int64 cb)
{
  unsigned int v3; // ebx
  bool v5; // zf
  int v6; // esi
  void *v7; // rcx
  __int64 v8; // r9
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-28h] BYREF

  v3 = -1;
  v5 = *(_DWORD *)(hf + 16) == 1;
  v6 = cb;
  v7 = *(void **)(hf + 8);
  NumberOfBytesWritten = -1;
  if ( !v5 )
  {
    if ( !v7 )
      goto LABEL_4;
    if ( (int)CSafeBuffer<unsigned char>::SafeAppend(v7, pv, cb, &NumberOfBytesWritten) < 0 )
    {
      v8 = 5;
      goto LABEL_8;
    }
    *(_DWORD *)(hf + 20) += v6;
    return NumberOfBytesWritten;
  }
  NumberOfBytesWritten = 0;
  if ( WriteFile(v7, pv, cb, &NumberOfBytesWritten, 0) )
    return NumberOfBytesWritten;
  GetLastError();
LABEL_4:
  v8 = 3;
LABEL_8:
  WUTrace(0, 0, 32, v8);
  return v3;
}

```

## disassembly

```asm
0x1800599b0  push    rbx
0x1800599b2  push    rsi
0x1800599b3  push    rdi
0x1800599b4  sub     rsp, 40h
0x1800599b8  mov     rax, cs:__security_cookie
0x1800599bf  xor     rax, rsp
0x1800599c2  mov     [rsp+58h+var_20], rax
0x1800599c7  or      ebx, 0FFFFFFFFh
0x1800599ca  mov     rdi, rcx
0x1800599cd  cmp     dword ptr [rcx+10h], 1
0x1800599d1  mov     esi, r8d
0x1800599d4  mov     rcx, [rcx+8]; hFile
0x1800599d8  mov     [rsp+58h+NumberOfBytesWritten], ebx
0x1800599dc  jnz     short loc_180059A38
0x1800599de  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800599e3  mov     [rsp+58h+NumberOfBytesWritten], 0
0x1800599eb  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1800599f4  call    cs:__imp_WriteFile
0x1800599fa  test    eax, eax
0x1800599fc  jnz     loc_180059A86
0x180059a02  call    cs:__imp_GetLastError
0x180059a08  movzx   ecx, ax
0x180059a0b  or      ecx, 80070000h
0x180059a11  test    eax, eax
0x180059a13  cmovle  ecx, eax
0x180059a16  mov     eax, 8000FFFFh
0x180059a1b  test    ecx, ecx
0x180059a1d  cmovns  ecx, eax
0x180059a20  lea     rax, aCabdecompresso_3; "CabDecompressorFileWrite - WriteFile"
0x180059a27  mov     [rsp+58h+var_30], rax
0x180059a2c  mov     dword ptr [rsp+58h+lpOverlapped], ecx
0x180059a30  mov     r9d, 3
0x180059a36  jmp     short loc_180059A74
0x180059a38  test    rcx, rcx
0x180059a3b  jnz     short loc_180059A50
0x180059a3d  lea     rax, aCabdecompresso_1; "CabDecompressorFileWrite - invalid buff"...
0x180059a44  mov     [rsp+58h+var_30], rax
0x180059a49  mov     [rsp+58h+lpOverlapped], rcx
0x180059a4e  jmp     short loc_180059A30
0x180059a50  lea     r9, [rsp+58h+NumberOfBytesWritten]
0x180059a55  call    ?SafeAppend@?$CSafeBuffer@E@@QEAAJPEBEIPEAI@Z; CSafeBuffer<uchar>::SafeAppend(uchar const *,uint,uint *)
0x180059a5a  test    eax, eax
0x180059a5c  jns     short loc_180059A83
0x180059a5e  lea     rcx, aWriteDecompres; "Write decompressed file to buffer"
0x180059a65  mov     r9d, 5
0x180059a6b  mov     [rsp+58h+var_30], rcx
0x180059a70  mov     dword ptr [rsp+58h+lpOverlapped], eax
0x180059a74  xor     edx, edx
0x180059a76  xor     ecx, ecx
0x180059a78  lea     r8d, [rdx+20h]
0x180059a7c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180059a81  jmp     short loc_180059A8A
0x180059a83  add     [rdi+14h], esi
0x180059a86  mov     ebx, [rsp+58h+NumberOfBytesWritten]
0x180059a8a  mov     eax, ebx
0x180059a8c  mov     rcx, [rsp+58h+var_20]
0x180059a91  xor     rcx, rsp; StackCookie
0x180059a94  call    __security_check_cookie
0x180059a99  add     rsp, 40h
0x180059a9d  pop     rdi
0x180059a9e  pop     rsi
0x180059a9f  pop     rbx
0x180059aa0  retn
```
