# Pal::IOImplWindows::deleteFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Pal::FileLocation)

- ea: `0x18002a230`
- end: `0x18002a2af`
- name: `?deleteFile@IOImplWindows@Pal@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FileLocation@2@@Z`
- size: `127`
- prototype: `void __fastcall(__int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000d090`
- `0x1800126c4`
- `0x180012720`
- `0x180024c14`
- `0x180025c68`
- `0x180029b4c`
- `0x18002a230`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002a27f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002a27f`

## pseudocode

```c
void __fastcall Pal::IOImplWindows::deleteFile(__int64 a1, __int64 a2, unsigned int a3)
{
  const WCHAR *v6; // rax
  _BYTE v7[8]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v8[32]; // [rsp+28h] [rbp-40h] BYREF

  if ( a3 )
  {
    CallingStateTracker::CallingStateTracker(v7);
    Pal::IOImplWindows::composeFullFileName(a1, v8, a2, a3);
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
    DeleteFileW(v6);
    std::wstring::_Tidy_deallocate(v8);
    CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v7);
  }
}

```

## disassembly

```asm
0x18002a230  test    r8d, r8d
0x18002a233  jz      short locret_18002A2AE
0x18002a235  push    rbx
0x18002a236  push    rsi
0x18002a237  push    rdi
0x18002a238  sub     rsp, 50h
0x18002a23c  mov     rax, cs:__security_cookie
0x18002a243  xor     rax, rsp
0x18002a246  mov     [rsp+68h+var_20], rax
0x18002a24b  mov     ebx, r8d
0x18002a24e  mov     rsi, rdx
0x18002a251  mov     rdi, rcx
0x18002a254  lea     rcx, [rsp+68h+var_48]
0x18002a259  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x18002a25e  nop
0x18002a25f  mov     r9d, ebx
0x18002a262  mov     r8, rsi
0x18002a265  lea     rdx, [rsp+68h+var_40]
0x18002a26a  mov     rcx, rdi
0x18002a26d  call    ?composeFullFileName@IOImplWindows@Pal@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@W4FileLocation@2@@Z; Pal::IOImplWindows::composeFullFileName(std::wstring const &,Pal::FileLocation)
0x18002a272  lea     rcx, [rsp+68h+var_40]
0x18002a277  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a27c  mov     rcx, rax; lpFileName
0x18002a27f  call    cs:__imp_DeleteFileW
0x18002a285  lea     rcx, [rsp+68h+var_40]
0x18002a28a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a28f  nop
0x18002a290  lea     rcx, [rsp+68h+var_48]; this
0x18002a295  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x18002a29a  mov     rcx, [rsp+68h+var_20]
0x18002a29f  xor     rcx, rsp; StackCookie
0x18002a2a2  call    __security_check_cookie
0x18002a2a7  add     rsp, 50h
0x18002a2ab  pop     rdi
0x18002a2ac  pop     rsi
0x18002a2ad  pop     rbx
0x18002a2ae  retn
```
