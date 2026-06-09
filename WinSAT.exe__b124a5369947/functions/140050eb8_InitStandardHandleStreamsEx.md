# InitStandardHandleStreamsEx

- ea: `0x140050eb8`
- end: `0x1400510b6`
- name: `InitStandardHandleStreamsEx`
- size: `510`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14001a54c`

## callees

- `0x1400085b4`
- `0x14000f68c`
- `0x140050624`
- `0x140050eb8`
- `0x14011a010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14005101d`
- `KERNEL32!CreateFileW` at `0x14005101d`
- `KERNEL32!GetConsoleOutputCP` at `0x140050ec2`
- `KERNEL32!GetConsoleOutputCP` at `0x140050ec2`
- `KERNEL32!GetStdHandle` at `0x140050f41`
- `KERNEL32!GetStdHandle` at `0x140050f4f`
- `KERNEL32!GetStdHandle` at `0x140050f41`
- `KERNEL32!GetStdHandle` at `0x140050f4f`

## pseudocode

```c
__int64 InitStandardHandleStreamsEx()
{
  UINT ConsoleOutputCP; // eax
  UINT v1; // edi
  __int64 v2; // rbx
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rax
  HANDLE StdHandle; // rbx
  HANDLE v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax

  ConsoleOutputCP = GetConsoleOutputCP();
  try
  {
    v1 = ConsoleOutputCP;
    v2 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdouta);
    mlib::basic_handlebuf<char,std::char_traits<char>>::ReAllocXBuf(v2, 0);
    *(_DWORD *)(v2 + 204) = 0;
    v3 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(mlib::stderra);
    mlib::basic_handlebuf<char,std::char_traits<char>>::ReAllocXBuf(v3, 0);
    *(_DWORD *)(v3 + 204) = 0;
    v4 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
    mlib::basic_handlebuf<unsigned short,std::char_traits<unsigned short>>::SetTranscodeCodePage(v4, v1);
    v5 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stderrw);
    mlib::basic_handlebuf<unsigned short,std::char_traits<unsigned short>>::SetTranscodeCodePage(v5, v1);
    StdHandle = GetStdHandle(0xFFFFFFF5);
    v7 = GetStdHandle(0xFFFFFFF4);
    v8 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdouta);
    (*(void (__fastcall **)(__int64, HANDLE, _QWORD))(*(_QWORD *)v8 + 120LL))(v8, StdHandle, 0);
    v9 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
    (*(void (__fastcall **)(__int64, HANDLE, _QWORD))(*(_QWORD *)v9 + 120LL))(v9, StdHandle, 0);
    v10 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(mlib::stderra);
    (*(void (__fastcall **)(__int64, HANDLE, _QWORD))(*(_QWORD *)v10 + 120LL))(v10, v7, 0);
    v11 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stderrw);
    (*(void (__fastcall **)(__int64, HANDLE, _QWORD))(*(_QWORD *)v11 + 120LL))(v11, v7, 0);
    if ( qword_1401689C8 == -1 )
      qword_1401689C8 = (__int64)CreateFileW(L"CONOUT$", 0xC0000000, 3u, 0, 3u, 0, 0);
    v12 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdouta);
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  if ( (unsigned __int64)(*(_QWORD *)(v12 + 136) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL
    || (unsigned __int64)(*(_QWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw)
                                    + 136)
                        - 1LL) > 0xFFFFFFFFFFFFFFFDuLL
    || (unsigned __int64)(*(_QWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(mlib::stderra)
                                    + 136)
                        - 1LL) > 0xFFFFFFFFFFFFFFFDuLL
    || (unsigned __int64)(*(_QWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stderrw)
                                    + 136)
                        - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    return 2147500037LL;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x140050eb8  mov     [rsp+arg_0], rbx
0x140050ebd  push    rdi
0x140050ebe  sub     rsp, 40h
0x140050ec2  call    cs:__imp_GetConsoleOutputCP
0x140050ec8  mov     edi, eax
0x140050eca  lea     rcx, ?stdouta@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<char,std::char_traits<char>>> mlib::stdouta
0x140050ed1  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140050ed6  mov     rbx, rax
0x140050ed9  xor     edx, edx
0x140050edb  mov     rcx, rax
0x140050ede  call    ?ReAllocXBuf@?$basic_handlebuf@DU?$char_traits@D@std@@@mlib@@QEAAX_K@Z; mlib::basic_handlebuf<char,std::char_traits<char>>::ReAllocXBuf(unsigned __int64)
0x140050ee3  mov     dword ptr [rbx+0CCh], 0
0x140050eed  lea     rcx, ?stderra@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<char,std::char_traits<char>>> mlib::stderra
0x140050ef4  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140050ef9  mov     rbx, rax
0x140050efc  xor     edx, edx
0x140050efe  mov     rcx, rax
0x140050f01  call    ?ReAllocXBuf@?$basic_handlebuf@DU?$char_traits@D@std@@@mlib@@QEAAX_K@Z; mlib::basic_handlebuf<char,std::char_traits<char>>::ReAllocXBuf(unsigned __int64)
0x140050f06  mov     dword ptr [rbx+0CCh], 0
0x140050f10  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x140050f17  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140050f1c  mov     edx, edi
0x140050f1e  mov     rcx, rax
0x140050f21  call    ?SetTranscodeCodePage@?$basic_handlebuf@GU?$char_traits@G@std@@@mlib@@QEAAXI@Z; mlib::basic_handlebuf<ushort,std::char_traits<ushort>>::SetTranscodeCodePage(uint)
0x140050f26  lea     rcx, ?stderrw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stderrw
0x140050f2d  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140050f32  mov     edx, edi
0x140050f34  mov     rcx, rax
0x140050f37  call    ?SetTranscodeCodePage@?$basic_handlebuf@GU?$char_traits@G@std@@@mlib@@QEAAXI@Z; mlib::basic_handlebuf<ushort,std::char_traits<ushort>>::SetTranscodeCodePage(uint)
0x140050f3c  mov     ecx, 0FFFFFFF5h; nStdHandle
0x140050f41  call    cs:__imp_GetStdHandle
0x140050f47  mov     rbx, rax
0x140050f4a  mov     ecx, 0FFFFFFF4h; nStdHandle
0x140050f4f  call    cs:__imp_GetStdHandle
0x140050f55  mov     rdi, rax
0x140050f58  lea     rcx, ?stdouta@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<char,std::char_traits<char>>> mlib::stdouta
0x140050f5f  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140050f64  mov     r9, rax
0x140050f67  mov     rcx, [rax]
0x140050f6a  mov     rax, [rcx+78h]
0x140050f6e  xor     r8d, r8d
0x140050f71  mov     rdx, rbx
0x140050f74  mov     rcx, r9
0x140050f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050f7c  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x140050f83  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140050f88  mov     r9, rax
0x140050f8b  mov     rcx, [rax]
0x140050f8e  mov     rax, [rcx+78h]
0x140050f92  xor     r8d, r8d
0x140050f95  mov     rdx, rbx
0x140050f98  mov     rcx, r9
0x140050f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050fa0  lea     rcx, ?stderra@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<char,std::char_traits<char>>> mlib::stderra
0x140050fa7  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140050fac  mov     r9, rax
0x140050faf  mov     rcx, [rax]
0x140050fb2  mov     rax, [rcx+78h]
0x140050fb6  xor     r8d, r8d
0x140050fb9  mov     rdx, rdi
0x140050fbc  mov     rcx, r9
0x140050fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050fc4  lea     rcx, ?stderrw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stderrw
0x140050fcb  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140050fd0  mov     r9, rax
0x140050fd3  mov     rcx, [rax]
0x140050fd6  mov     rax, [rcx+78h]
0x140050fda  xor     r8d, r8d
0x140050fdd  mov     rdx, rdi
0x140050fe0  mov     rcx, r9
0x140050fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050fe8  cmp     cs:qword_1401689C8, 0FFFFFFFFFFFFFFFFh
0x140050ff0  jnz     short loc_14005102A
0x140050ff2  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x140050ffb  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140051003  mov     r8d, 3; dwShareMode
0x140051009  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x14005100e  xor     r9d, r9d; lpSecurityAttributes
0x140051011  mov     edx, 0C0000000h; dwDesiredAccess
0x140051016  lea     rcx, FileName; "CONOUT$"
0x14005101d  call    cs:__imp_CreateFileW
0x140051023  mov     cs:qword_1401689C8, rax
0x14005102a  lea     rcx, ?stdouta@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<char,std::char_traits<char>>> mlib::stdouta
0x140051031  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140051036  mov     rax, [rax+88h]
0x14005103d  dec     rax
0x140051040  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140051044  ja      short loc_14005109E
0x140051046  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x14005104d  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140051052  mov     rax, [rax+88h]
0x140051059  dec     rax
0x14005105c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140051060  ja      short loc_14005109E
0x140051062  lea     rcx, ?stderra@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<char,std::char_traits<char>>> mlib::stderra
0x140051069  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14005106e  mov     rax, [rax+88h]
0x140051075  dec     rax
0x140051078  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14005107c  ja      short loc_14005109E
0x14005107e  lea     rcx, ?stderrw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stderrw
0x140051085  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14005108a  mov     rax, [rax+88h]
0x140051091  dec     rax
0x140051094  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140051098  ja      short loc_14005109E
0x14005109a  xor     eax, eax
0x14005109c  jmp     short loc_1400510AA
0x14005109e  mov     eax, 80004005h
0x1400510a3  jmp     short loc_1400510AA
0x1400510a5  mov     eax, 8007000Eh
0x1400510aa  mov     rbx, [rsp+48h+arg_0]
0x1400510af  add     rsp, 40h
0x1400510b3  pop     rdi
0x1400510b4  retn
```
