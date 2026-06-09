# PushButtonReset::Directory::GetCurrent(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)

- ea: `0x18004d6b8`
- end: `0x18004d798`
- name: `?GetCurrent@Directory@PushButtonReset@@SAJPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004db84`

## callees

- `0x180011ef4`
- `0x180037344`
- `0x18004d6b8`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004d702`
- `KERNEL32!GetLastError` at `0x18004d744`
- `KERNEL32!GetLastError` at `0x18004d702`
- `KERNEL32!GetLastError` at `0x18004d744`
- `KERNEL32!GetCurrentDirectoryW` at `0x18004d6f6`
- `KERNEL32!GetCurrentDirectoryW` at `0x18004d6f6`

## string_xrefs

- `0x18004d716`: `Failed to query current working directory`
- `0x18004d738`: `PushButtonReset::Directory::GetCurrent`

## pseudocode

```c
signed int __fastcall PushButtonReset::Directory::GetCurrent(__int64 a1)
{
  signed int LastError; // eax
  signed int result; // eax
  __int64 v4; // r8
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  if ( GetCurrentDirectoryW(0x104u, Buffer) )
  {
    v4 = -1;
    do
      ++v4;
    while ( Buffer[v4] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(a1, Buffer, v4);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "PushButtonReset::Directory::GetCurrent",
      "base\\reset\\util\\src\\filesystem.cpp",
      1548,
      L"Failed to query current working directory");
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18004d6b8  mov     [rsp+arg_8], rbx
0x18004d6bd  push    rdi
0x18004d6be  sub     rsp, 250h
0x18004d6c5  mov     rax, cs:__security_cookie
0x18004d6cc  xor     rax, rsp
0x18004d6cf  mov     [rsp+258h+var_18], rax
0x18004d6d7  mov     rbx, rcx
0x18004d6da  xor     edx, edx; Val
0x18004d6dc  lea     rcx, [rsp+258h+Buffer]; void *
0x18004d6e1  mov     r8d, 20Ah; Size
0x18004d6e7  call    memset_0
0x18004d6ec  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x18004d6f1  mov     ecx, 104h; nBufferLength
0x18004d6f6  call    cs:__imp_GetCurrentDirectoryW
0x18004d6fc  xor     edi, edi
0x18004d6fe  test    eax, eax
0x18004d700  jnz     short loc_18004D755
0x18004d702  call    cs:__imp_GetLastError
0x18004d708  mov     ebx, 80070000h
0x18004d70d  test    eax, eax
0x18004d70f  jle     short loc_18004D716
0x18004d711  movzx   eax, ax
0x18004d714  or      eax, ebx
0x18004d716  lea     rcx, aFailedToQueryC; "Failed to query current working directo"...
0x18004d71d  mov     edx, eax
0x18004d71f  mov     [rsp+258h+var_230], rcx
0x18004d724  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004d72b  mov     ecx, 2
0x18004d730  mov     [rsp+258h+var_238], 60Ch
0x18004d738  lea     r8, aPushbuttonrese_119; "PushButtonReset::Directory::GetCurrent"
0x18004d73f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004d744  call    cs:__imp_GetLastError
0x18004d74a  test    eax, eax
0x18004d74c  jle     short loc_18004D777
0x18004d74e  movzx   eax, ax
0x18004d751  or      eax, ebx
0x18004d753  jmp     short loc_18004D777
0x18004d755  lea     rax, [rsp+258h+Buffer]
0x18004d75a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004d75e  inc     r8
0x18004d761  cmp     [rax+r8*2], di
0x18004d766  jnz     short loc_18004D75E
0x18004d768  lea     rdx, [rsp+258h+Buffer]
0x18004d76d  mov     rcx, rbx
0x18004d770  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004d775  xor     eax, eax
0x18004d777  mov     rcx, [rsp+258h+var_18]
0x18004d77f  xor     rcx, rsp; StackCookie
0x18004d782  call    __security_check_cookie
0x18004d787  mov     rbx, [rsp+258h+arg_8]
0x18004d78f  add     rsp, 250h
0x18004d796  pop     rdi
0x18004d797  retn
```
