# Pal::IOImplWindows::readFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Pal::FileLocation)

- ea: `0x180019100`
- end: `0x1800192a1`
- name: `?readFile@IOImplWindows@Pal@@UEAA?AV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@W4FileLocation@2@@Z`
- size: `417`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800094a0`
- `0x180009988`
- `0x18000c2f8`
- `0x18000c354`
- `0x18000d80c`
- `0x180010354`
- `0x180011628`
- `0x180011f04`
- `0x180013da8`
- `0x180016058`
- `0x180019100`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180019238`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180019238`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800191aa`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800191aa`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18001917d`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18001917d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019267`

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
  File2 = (void *)CreateFile2(v5, 0x80000000LL, 1);
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
      std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(a2, v13);
      if ( v13[1] )
        std::_Ref_count_base::_Decref(v13[1]);
      if ( !ReadFile(File2, **(LPVOID **)a2, v7, &NumberOfBytesRead, 0) )
      {
        *(_OWORD *)v13 = 0;
        std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(a2, v13);
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
0x180019100  push    rbp
0x180019102  push    rbx
0x180019103  push    rsi
0x180019104  push    rdi
0x180019105  push    r14
0x180019107  push    r15
0x180019109  lea     rbp, [rsp-2Fh]
0x18001910e  sub     rsp, 0A8h
0x180019115  mov     rax, cs:__security_cookie
0x18001911c  xor     rax, rsp
0x18001911f  mov     [rbp+57h+var_40], rax
0x180019123  mov     rsi, rdx
0x180019126  mov     [rbp+57h+var_80], rdx
0x18001912a  mov     [rbp+57h+var_A0], 0
0x180019131  mov     qword ptr [rdx], 0
0x180019138  mov     qword ptr [rdx+8], 0
0x180019140  mov     ebx, 1
0x180019145  mov     [rbp+57h+var_A0], ebx
0x180019148  lea     rdx, [rbp+57h+var_60]
0x18001914c  call    ?composeFullFileName@IOImplWindows@Pal@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@W4FileLocation@2@@Z; Pal::IOImplWindows::composeFullFileName(std::wstring const &,Pal::FileLocation)
0x180019151  nop
0x180019152  lea     rcx, [rbp+57h+var_94]
0x180019156  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x18001915b  nop
0x18001915c  lea     rcx, [rbp+57h+var_60]
0x180019160  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180019165  mov     rcx, rax
0x180019168  mov     [rsp+0D0h+lpOverlapped], 0
0x180019171  lea     r9d, [rbx+2]
0x180019175  mov     r8d, ebx
0x180019178  mov     edx, 80000000h
0x18001917d  call    cs:__imp_CreateFile2
0x180019183  mov     r14, rax
0x180019186  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001918a  jz      loc_18001926E
0x180019190  xorps   xmm0, xmm0
0x180019193  xor     eax, eax
0x180019195  movups  [rbp+57h+FileInformation], xmm0
0x180019199  mov     [rbp+57h+var_68], rax
0x18001919d  lea     r9d, [rbx+17h]; dwBufferSize
0x1800191a1  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x1800191a5  mov     edx, ebx; FileInformationClass
0x1800191a7  mov     rcx, r14; hFile
0x1800191aa  call    cs:__imp_GetFileInformationByHandleEx
0x1800191b0  test    eax, eax
0x1800191b2  jz      loc_180019264
0x1800191b8  mov     r15d, dword ptr [rbp+57h+FileInformation+8]
0x1800191bc  mov     [rbp+57h+var_9C], r15d
0x1800191c0  mov     [rbp+57h+NumberOfBytesRead], 0
0x1800191c7  lea     ecx, [rbx+27h]; Size
0x1800191ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800191cf  mov     rdi, rax
0x1800191d2  mov     [rbp+57h+var_90], rax
0x1800191d6  xorps   xmm0, xmm0
0x1800191d9  movups  xmmword ptr [rax], xmm0
0x1800191dc  mov     [rax+8], ebx
0x1800191df  mov     [rax+0Ch], ebx
0x1800191e2  lea     rax, ??_7?$_Ref_count_obj2@V?$vector@EV?$allocator@E@std@@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<uchar>>::`vftable'
0x1800191e9  mov     [rdi], rax
0x1800191ec  lea     rbx, [rdi+10h]
0x1800191f0  lea     rdx, [rbp+57h+var_9C]
0x1800191f4  mov     rcx, rbx
0x1800191f7  call    ??$_Construct_in_place@V?$vector@EV?$allocator@E@std@@@std@@AEAK@std@@YAXAEAV?$vector@EV?$allocator@E@std@@@0@AEAK@Z; std::_Construct_in_place<std::vector<uchar>,ulong &>(std::vector<uchar> &,ulong &)
0x1800191fc  nop
0x1800191fd  mov     [rbp+57h+var_90], rbx
0x180019201  mov     [rbp+57h+var_90+8], rdi
0x180019205  lea     rdx, [rbp+57h+var_90]
0x180019209  mov     rcx, rsi
0x18001920c  call    ??4?$shared_ptr@VNetworkRequestInternalWinHttp@Pal@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(std::shared_ptr<Pal::NetworkRequestInternalWinHttp> &&)
0x180019211  mov     rcx, [rbp+57h+var_90+8]; this
0x180019215  test    rcx, rcx
0x180019218  jz      short loc_18001921F
0x18001921a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001921f  mov     rdx, [rsi]
0x180019222  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x18001922b  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001922f  mov     r8d, r15d; nNumberOfBytesToRead
0x180019232  mov     rdx, [rdx]; lpBuffer
0x180019235  mov     rcx, r14; hFile
0x180019238  call    cs:__imp_ReadFile
0x18001923e  test    eax, eax
0x180019240  jnz     short loc_180019264
0x180019242  xorps   xmm0, xmm0
0x180019245  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x18001924a  lea     rdx, [rbp+57h+var_90]
0x18001924e  mov     rcx, rsi
0x180019251  call    ??4?$shared_ptr@VNetworkRequestInternalWinHttp@Pal@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(std::shared_ptr<Pal::NetworkRequestInternalWinHttp> &&)
0x180019256  mov     rcx, [rbp+57h+var_90+8]; this
0x18001925a  test    rcx, rcx
0x18001925d  jz      short loc_180019264
0x18001925f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019264  mov     rcx, r14; hObject
0x180019267  call    cs:__imp_CloseHandle
0x18001926d  nop
0x18001926e  lea     rcx, [rbp+57h+var_94]; this
0x180019272  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x180019277  nop
0x180019278  lea     rcx, [rbp+57h+var_60]
0x18001927c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019281  mov     rax, rsi
0x180019284  mov     rcx, [rbp+57h+var_40]
0x180019288  xor     rcx, rsp; StackCookie
0x18001928b  call    __security_check_cookie
0x180019290  add     rsp, 0A8h
0x180019297  pop     r15
0x180019299  pop     r14
0x18001929b  pop     rdi
0x18001929c  pop     rsi
0x18001929d  pop     rbx
0x18001929e  pop     rbp
0x18001929f  retn
```
