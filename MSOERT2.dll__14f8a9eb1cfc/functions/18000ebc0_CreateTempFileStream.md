# CreateTempFileStream

- ea: `0x18000ebc0`
- end: `0x18000ec61`
- name: `CreateTempFileStream`
- size: `161`
- prototype: `int __fastcall(struct IStream **)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001980`
- `0x18000ebc0`
- `0x180012fc0`

## import_xrefs

- `KERNEL32!GetTempPathW` at `0x18000ebe8`
- `KERNEL32!GetTempPathW` at `0x18000ebe8`
- `KERNEL32!GetTempFileNameW` at `0x18000ec0e`
- `KERNEL32!GetTempFileNameW` at `0x18000ec0e`

## pseudocode

```c
int __fastcall CreateTempFileStream(struct IStream **a1)
{
  WCHAR Buffer[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR TempFileName[264]; // [rsp+240h] [rbp-228h] BYREF

  if ( GetTempPathW(0x104u, Buffer) - 1 <= 0x103 && GetTempFileNameW(Buffer, L"tmp", 0, TempFileName) )
    return CreateFileStream(TempFileName, 0xC0000000, 4u, 2u, 0x4000100u, a1);
  else
    return -2147467259;
}

```

## disassembly

```asm
0x18000ebc0  push    rbx
0x18000ebc2  sub     rsp, 460h
0x18000ebc9  mov     rax, cs:__security_cookie
0x18000ebd0  xor     rax, rsp
0x18000ebd3  mov     [rsp+468h+var_18], rax
0x18000ebdb  mov     rbx, rcx
0x18000ebde  lea     rdx, [rsp+468h+Buffer]; lpBuffer
0x18000ebe3  mov     ecx, 104h; nBufferLength
0x18000ebe8  call    cs:__imp_GetTempPathW
0x18000ebee  dec     eax
0x18000ebf0  cmp     eax, 103h
0x18000ebf5  ja      short loc_18000EC43
0x18000ebf7  lea     r9, [rsp+468h+TempFileName]; lpTempFileName
0x18000ebff  xor     r8d, r8d; uUnique
0x18000ec02  lea     rdx, aTmp; "tmp"
0x18000ec09  lea     rcx, [rsp+468h+Buffer]; lpPathName
0x18000ec0e  call    cs:__imp_GetTempFileNameW
0x18000ec14  test    eax, eax
0x18000ec16  jz      short loc_18000EC43
0x18000ec18  mov     r9d, 2; unsigned int
0x18000ec1e  mov     [rsp+468h+var_440], rbx; struct IStream **
0x18000ec23  mov     edx, 0C0000000h; unsigned int
0x18000ec28  mov     [rsp+468h+var_448], 4000100h; unsigned int
0x18000ec30  lea     rcx, [rsp+468h+TempFileName]; unsigned __int16 *
0x18000ec38  lea     r8d, [r9+2]; unsigned int
0x18000ec3c  call    ?CreateFileStream@@YAJPEBGKKKKPEAPEAUIStream@@@Z; CreateFileStream(ushort const *,ulong,ulong,ulong,ulong,IStream * *)
0x18000ec41  jmp     short loc_18000EC48
0x18000ec43  mov     eax, 80004005h
0x18000ec48  mov     rcx, [rsp+468h+var_18]
0x18000ec50  xor     rcx, rsp; StackCookie
0x18000ec53  call    __security_check_cookie
0x18000ec58  add     rsp, 460h
0x18000ec5f  pop     rbx
0x18000ec60  retn
```
