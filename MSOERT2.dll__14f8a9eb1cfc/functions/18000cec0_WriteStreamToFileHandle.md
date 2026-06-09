# WriteStreamToFileHandle

- ea: `0x18000cec0`
- end: `0x18000cf99`
- name: `WriteStreamToFileHandle`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18000cec0`
- `0x180012fc0`
- `0x180014010`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18000cf50`
- `KERNEL32!WriteFile` at `0x18000cf50`

## pseudocode

```c
__int64 __fastcall WriteStreamToFileHandle(__int64 a1, void *a2, _DWORD *a3)
{
  int v6; // ebx
  __int64 result; // rax
  DWORD nNumberOfBytesToWrite; // [rsp+30h] [rbp-838h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-834h] BYREF
  _BYTE Buffer[2048]; // [rsp+40h] [rbp-828h] BYREF

  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  if ( !a1 )
    return 2147942487LL;
  if ( !a2 )
    return 2147942487LL;
  v6 = 0;
  if ( a2 == (void *)-1LL )
    return 2147942487LL;
  while ( 1 )
  {
    result = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, DWORD *))(*(_QWORD *)a1 + 24LL))(
               a1,
               Buffer,
               2048,
               &nNumberOfBytesToWrite);
    if ( (int)result < 0 )
      break;
    if ( !nNumberOfBytesToWrite )
    {
      if ( a3 )
        *a3 = v6;
      return result;
    }
    if ( !WriteFile(a2, Buffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
      return 2147500037LL;
    v6 += NumberOfBytesWritten;
  }
  return result;
}

```

## disassembly

```asm
0x18000cec0  mov     [rsp+arg_18], rbx
0x18000cec5  push    rsi
0x18000cec6  push    rdi
0x18000cec7  push    r14
0x18000cec9  sub     rsp, 850h
0x18000ced0  mov     rax, cs:__security_cookie
0x18000ced7  xor     rax, rsp
0x18000ceda  mov     [rsp+868h+var_28], rax
0x18000cee2  mov     [rsp+868h+nNumberOfBytesToWrite], 0
0x18000ceea  mov     rsi, r8
0x18000ceed  mov     [rsp+868h+NumberOfBytesWritten], 0
0x18000cef5  mov     rdi, rdx
0x18000cef8  mov     r14, rcx
0x18000cefb  test    rcx, rcx
0x18000cefe  jz      short loc_18000CF70
0x18000cf00  test    rdx, rdx
0x18000cf03  jz      short loc_18000CF70
0x18000cf05  xor     ebx, ebx
0x18000cf07  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18000cf0b  jz      short loc_18000CF70
0x18000cf0d  mov     rax, [r14]
0x18000cf10  lea     r9, [rsp+868h+nNumberOfBytesToWrite]
0x18000cf15  mov     r8d, 800h
0x18000cf1b  lea     rdx, [rsp+868h+Buffer]
0x18000cf20  mov     rcx, r14
0x18000cf23  mov     rax, [rax+18h]
0x18000cf27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf2c  test    eax, eax
0x18000cf2e  js      short loc_18000CF75
0x18000cf30  mov     r8d, [rsp+868h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18000cf35  test    r8d, r8d
0x18000cf38  jz      short loc_18000CF67
0x18000cf3a  lea     r9, [rsp+868h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000cf3f  mov     [rsp+868h+lpOverlapped], 0; lpOverlapped
0x18000cf48  lea     rdx, [rsp+868h+Buffer]; lpBuffer
0x18000cf4d  mov     rcx, rdi; hFile
0x18000cf50  call    cs:__imp_WriteFile
0x18000cf56  test    eax, eax
0x18000cf58  jz      short loc_18000CF60
0x18000cf5a  add     ebx, [rsp+868h+NumberOfBytesWritten]
0x18000cf5e  jmp     short loc_18000CF0D
0x18000cf60  mov     eax, 80004005h
0x18000cf65  jmp     short loc_18000CF75
0x18000cf67  test    rsi, rsi
0x18000cf6a  jz      short loc_18000CF75
0x18000cf6c  mov     [rsi], ebx
0x18000cf6e  jmp     short loc_18000CF75
0x18000cf70  mov     eax, 80070057h
0x18000cf75  mov     rcx, [rsp+868h+var_28]
0x18000cf7d  xor     rcx, rsp; StackCookie
0x18000cf80  call    __security_check_cookie
0x18000cf85  mov     rbx, [rsp+868h+arg_18]
0x18000cf8d  add     rsp, 850h
0x18000cf94  pop     r14
0x18000cf96  pop     rdi
0x18000cf97  pop     rsi
0x18000cf98  retn
```
