# Pal::IOImplWindows::deleteFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Pal::FileLocation)

- ea: `0x180016850`
- end: `0x1800168cf`
- name: `?deleteFile@IOImplWindows@Pal@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FileLocation@2@@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800094a0`
- `0x18000c2f8`
- `0x18000c354`
- `0x180010354`
- `0x180011628`
- `0x180016058`
- `0x180016850`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001689f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001689f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Pal::IOImplWindows::deleteFile(__int64 a1, __int64 a2, unsigned int a3)
{
  const WCHAR *v6; // rax
  _BYTE v7[8]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v8[32]; // [rsp+28h] [rbp-40h] BYREF

  if ( a3 )
  {
    CallingStateTracker::CallingStateTracker(v7);
    Pal::IOImplWindows::composeFullFileName(a1, (__int64)v8, a2, a3);
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
    DeleteFileW(v6);
    std::wstring::_Tidy_deallocate(v8);
    CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v7);
  }
}

```

## disassembly

```asm
0x180016850  test    r8d, r8d
0x180016853  jz      short locret_1800168CE
0x180016855  push    rbx
0x180016856  push    rsi
0x180016857  push    rdi
0x180016858  sub     rsp, 50h
0x18001685c  mov     rax, cs:__security_cookie
0x180016863  xor     rax, rsp
0x180016866  mov     [rsp+68h+var_20], rax
0x18001686b  mov     ebx, r8d
0x18001686e  mov     rsi, rdx
0x180016871  mov     rdi, rcx
0x180016874  lea     rcx, [rsp+68h+var_48]
0x180016879  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x18001687e  nop
0x18001687f  mov     r9d, ebx
0x180016882  mov     r8, rsi
0x180016885  lea     rdx, [rsp+68h+var_40]
0x18001688a  mov     rcx, rdi
0x18001688d  call    ?composeFullFileName@IOImplWindows@Pal@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@W4FileLocation@2@@Z; Pal::IOImplWindows::composeFullFileName(std::wstring const &,Pal::FileLocation)
0x180016892  lea     rcx, [rsp+68h+var_40]
0x180016897  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001689c  mov     rcx, rax; lpFileName
0x18001689f  call    cs:__imp_DeleteFileW
0x1800168a5  lea     rcx, [rsp+68h+var_40]
0x1800168aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800168af  nop
0x1800168b0  lea     rcx, [rsp+68h+var_48]; this
0x1800168b5  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x1800168ba  mov     rcx, [rsp+68h+var_20]
0x1800168bf  xor     rcx, rsp; StackCookie
0x1800168c2  call    __security_check_cookie
0x1800168c7  add     rsp, 50h
0x1800168cb  pop     rdi
0x1800168cc  pop     rsi
0x1800168cd  pop     rbx
0x1800168ce  retn
```
