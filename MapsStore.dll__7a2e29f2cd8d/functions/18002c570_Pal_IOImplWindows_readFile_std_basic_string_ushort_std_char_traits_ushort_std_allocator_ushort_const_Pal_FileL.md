# Pal::IOImplWindows::readFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Pal::FileLocation)

- ea: `0x18002c570`
- end: `0x18002c711`
- name: `?readFile@IOImplWindows@Pal@@UEAA?AV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@W4FileLocation@2@@Z`
- size: `417`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000d090`
- `0x18000d49c`
- `0x1800126c4`
- `0x180012720`
- `0x180017aa8`
- `0x18001b9e0`
- `0x180022690`
- `0x180024c14`
- `0x180025c68`
- `0x180029b4c`
- `0x18002c570`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c6d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c6d7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002c6a8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002c6a8`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18002c61a`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18002c61a`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18002c5ed`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18002c5ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Pal::IOImplWindows::readFile(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v5; // rax
  void *File2; // r14
  DWORD v7; // r15d
  _DWORD *v8; // rdi
  int v10; // [rsp+34h] [rbp-45h] BYREF
  DWORD NumberOfBytesRead; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v12[4]; // [rsp+3Ch] [rbp-3Dh] BYREF
  std::_Ref_count_base *v13[2]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v14; // [rsp+50h] [rbp-29h]
  __int128 FileInformation; // [rsp+58h] [rbp-21h] BYREF
  __int64 v16; // [rsp+68h] [rbp-11h]
  _BYTE v17[32]; // [rsp+70h] [rbp-9h] BYREF

  v14 = a2;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  Pal::IOImplWindows::composeFullFileName(a1, (__int64)v17, a3, a4);
  CallingStateTracker::CallingStateTracker(v12);
  v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
  File2 = (void *)CreateFile2(v5, 0x80000000LL, 1, 3, 0);
  if ( File2 != (void *)-1LL )
  {
    FileInformation = 0;
    v16 = 0;
    if ( GetFileInformationByHandleEx(File2, FileStandardInfo, &FileInformation, 0x18u) )
    {
      v7 = DWORD2(FileInformation);
      v10 = DWORD2(FileInformation);
      NumberOfBytesRead = 0;
      v8 = operator new(0x28u);
      v13[0] = (std::_Ref_count_base *)v8;
      *(_OWORD *)v8 = 0;
      v8[2] = 1;
      v8[3] = 1;
      *(_QWORD *)v8 = &std::_Ref_count_obj2<std::vector<unsigned char>>::`vftable';
      std::_Construct_in_place<std::vector<unsigned char>,unsigned long &>(v8 + 4, &v10);
      v13[0] = (std::_Ref_count_base *)(v8 + 4);
      v13[1] = (std::_Ref_count_base *)v8;
      std::shared_ptr<MapControl::LocalIndex>::operator=(a2, v13);
      if ( v13[1] )
        std::_Ref_count_base::_Decref(v13[1]);
      if ( !ReadFile(File2, **(LPVOID **)a2, v7, &NumberOfBytesRead, 0) )
      {
        *(_OWORD *)v13 = 0;
        std::shared_ptr<MapControl::LocalIndex>::operator=(a2, v13);
        if ( v13[1] )
          std::_Ref_count_base::_Decref(v13[1]);
      }
    }
    CloseHandle(File2);
  }
  CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v12);
  std::wstring::_Tidy_deallocate(v17);
  return a2;
}

```

## disassembly

```asm
0x18002c570  push    rbp
0x18002c572  push    rbx
0x18002c573  push    rsi
0x18002c574  push    rdi
0x18002c575  push    r14
0x18002c577  push    r15
0x18002c579  lea     rbp, [rsp-2Fh]
0x18002c57e  sub     rsp, 0A8h
0x18002c585  mov     rax, cs:__security_cookie
0x18002c58c  xor     rax, rsp
0x18002c58f  mov     [rbp+57h+var_40], rax
0x18002c593  mov     rsi, rdx
0x18002c596  mov     [rbp+57h+var_80], rdx
0x18002c59a  mov     [rbp+57h+var_A0], 0
0x18002c5a1  mov     qword ptr [rdx], 0
0x18002c5a8  mov     qword ptr [rdx+8], 0
0x18002c5b0  mov     ebx, 1
0x18002c5b5  mov     [rbp+57h+var_A0], ebx
0x18002c5b8  lea     rdx, [rbp+57h+var_60]
0x18002c5bc  call    ?composeFullFileName@IOImplWindows@Pal@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@W4FileLocation@2@@Z; Pal::IOImplWindows::composeFullFileName(std::wstring const &,Pal::FileLocation)
0x18002c5c1  nop
0x18002c5c2  lea     rcx, [rbp+57h+var_94]
0x18002c5c6  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x18002c5cb  nop
0x18002c5cc  lea     rcx, [rbp+57h+var_60]
0x18002c5d0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002c5d5  mov     rcx, rax
0x18002c5d8  mov     [rsp+0D0h+lpOverlapped], 0
0x18002c5e1  lea     r9d, [rbx+2]
0x18002c5e5  mov     r8d, ebx
0x18002c5e8  mov     edx, 80000000h
0x18002c5ed  call    cs:__imp_CreateFile2
0x18002c5f3  mov     r14, rax
0x18002c5f6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c5fa  jz      loc_18002C6DE
0x18002c600  xorps   xmm0, xmm0
0x18002c603  xor     eax, eax
0x18002c605  movups  [rbp+57h+FileInformation], xmm0
0x18002c609  mov     [rbp+57h+var_68], rax
0x18002c60d  lea     r9d, [rbx+17h]; dwBufferSize
0x18002c611  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x18002c615  mov     edx, ebx; FileInformationClass
0x18002c617  mov     rcx, r14; hFile
0x18002c61a  call    cs:__imp_GetFileInformationByHandleEx
0x18002c620  test    eax, eax
0x18002c622  jz      loc_18002C6D4
0x18002c628  mov     r15d, dword ptr [rbp+57h+FileInformation+8]
0x18002c62c  mov     [rbp+57h+var_9C], r15d
0x18002c630  mov     [rbp+57h+NumberOfBytesRead], 0
0x18002c637  lea     ecx, [rbx+27h]; Size
0x18002c63a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c63f  mov     rdi, rax
0x18002c642  mov     [rbp+57h+var_90], rax
0x18002c646  xorps   xmm0, xmm0
0x18002c649  movups  xmmword ptr [rax], xmm0
0x18002c64c  mov     [rax+8], ebx
0x18002c64f  mov     [rax+0Ch], ebx
0x18002c652  lea     rax, ??_7?$_Ref_count_obj2@V?$vector@EV?$allocator@E@std@@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<uchar>>::`vftable'
0x18002c659  mov     [rdi], rax
0x18002c65c  lea     rbx, [rdi+10h]
0x18002c660  lea     rdx, [rbp+57h+var_9C]
0x18002c664  mov     rcx, rbx
0x18002c667  call    ??$_Construct_in_place@V?$vector@EV?$allocator@E@std@@@std@@AEAK@std@@YAXAEAV?$vector@EV?$allocator@E@std@@@0@AEAK@Z; std::_Construct_in_place<std::vector<uchar>,ulong &>(std::vector<uchar> &,ulong &)
0x18002c66c  nop
0x18002c66d  mov     [rbp+57h+var_90], rbx
0x18002c671  mov     [rbp+57h+var_90+8], rdi
0x18002c675  lea     rdx, [rbp+57h+var_90]
0x18002c679  mov     rcx, rsi
0x18002c67c  call    ??4?$shared_ptr@VLocalIndex@MapControl@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<MapControl::LocalIndex>::operator=(std::shared_ptr<MapControl::LocalIndex> &&)
0x18002c681  mov     rcx, [rbp+57h+var_90+8]; this
0x18002c685  test    rcx, rcx
0x18002c688  jz      short loc_18002C68F
0x18002c68a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c68f  mov     rdx, [rsi]
0x18002c692  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x18002c69b  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002c69f  mov     r8d, r15d; nNumberOfBytesToRead
0x18002c6a2  mov     rdx, [rdx]; lpBuffer
0x18002c6a5  mov     rcx, r14; hFile
0x18002c6a8  call    cs:__imp_ReadFile
0x18002c6ae  test    eax, eax
0x18002c6b0  jnz     short loc_18002C6D4
0x18002c6b2  xorps   xmm0, xmm0
0x18002c6b5  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x18002c6ba  lea     rdx, [rbp+57h+var_90]
0x18002c6be  mov     rcx, rsi
0x18002c6c1  call    ??4?$shared_ptr@VLocalIndex@MapControl@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<MapControl::LocalIndex>::operator=(std::shared_ptr<MapControl::LocalIndex> &&)
0x18002c6c6  mov     rcx, [rbp+57h+var_90+8]; this
0x18002c6ca  test    rcx, rcx
0x18002c6cd  jz      short loc_18002C6D4
0x18002c6cf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c6d4  mov     rcx, r14; hObject
0x18002c6d7  call    cs:__imp_CloseHandle
0x18002c6dd  nop
0x18002c6de  lea     rcx, [rbp+57h+var_94]; this
0x18002c6e2  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x18002c6e7  nop
0x18002c6e8  lea     rcx, [rbp+57h+var_60]
0x18002c6ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c6f1  mov     rax, rsi
0x18002c6f4  mov     rcx, [rbp+57h+var_40]
0x18002c6f8  xor     rcx, rsp; StackCookie
0x18002c6fb  call    __security_check_cookie
0x18002c700  add     rsp, 0A8h
0x18002c707  pop     r15
0x18002c709  pop     r14
0x18002c70b  pop     rdi
0x18002c70c  pop     rsi
0x18002c70d  pop     rbx
0x18002c70e  pop     rbp
0x18002c70f  retn
```
