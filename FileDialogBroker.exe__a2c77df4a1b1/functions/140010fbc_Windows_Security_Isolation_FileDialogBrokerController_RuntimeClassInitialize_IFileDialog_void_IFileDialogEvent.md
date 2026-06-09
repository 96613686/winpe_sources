# Windows::Security::Isolation::FileDialogBrokerController::RuntimeClassInitialize(IFileDialog *,void *,IFileDialogEvents *,Windows::Security::Isolation::FDBControllerType)

- ea: `0x140010fbc`
- end: `0x14001120c`
- name: `?RuntimeClassInitialize@FileDialogBrokerController@Isolation@Security@Windows@@QEAAJPEAUIFileDialog@@PEAXPEAUIFileDialogEvents@@W4FDBControllerType@234@@Z`
- size: `592`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000842c`

## callees

- `0x140007df4`
- `0x140007e14`
- `0x140009194`
- `0x14000f8d0`
- `0x1400108a0`
- `0x140010964`
- `0x140010a28`
- `0x140010aec`
- `0x140010fbc`
- `0x140014010`

## string_xrefs

- `0x140010fe3`: `FileDialogBrokerController::RuntimeClassInitialize`
- `0x140011007`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbrokercontroller.cpp`
- `0x140011034`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbrokercontroller.cpp`
- `0x140011058`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbrokercontroller.cpp`
- `0x140011097`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbrokercontroller.cpp`
- `0x1400110dd`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbrokercontroller.cpp`
- `0x140011123`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbrokercontroller.cpp`
- `0x140011165`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbrokercontroller.cpp`
- `0x1400111a7`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbrokercontroller.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBrokerController::RuntimeClassInitialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rbx
  __int64 result; // rax
  const char *v15; // r9
  int v16[26]; // [rsp+20h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v16, "FileDialogBrokerController::RuntimeClassInitialize");
  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
        (const char *)0x80004003LL,
        v16[0]);
    if ( (unsigned __int64)(a3 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x17,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
        (const char *)0x80070006LL,
        v16[0]);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
        (const char *)0x80004003LL,
        v16[0]);
    if ( a5 )
    {
      switch ( a5 )
      {
        case 1:
          wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(a1 + 32);
          v11 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileSaveDialogBroker,IFileDialog,IFileDialog * &,void * &>((void **)(a1 + 32));
          if ( v11 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x21,
              (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
              (const char *)(unsigned int)v11,
              v16[0]);
          break;
        case 2:
          wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(a1 + 32);
          v10 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileOpenDialogLegacyBroker,IFileDialog,IFileDialog * &,void * &>((void **)(a1 + 32));
          if ( v10 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x25,
              (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
              (const char *)(unsigned int)v10,
              v16[0]);
          break;
        case 3:
          wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(a1 + 32);
          v9 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileSaveDialogLegacyBroker,IFileDialog,IFileDialog * &,void * &>((void **)(a1 + 32));
          if ( v9 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x29,
              (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
              (const char *)(unsigned int)v9,
              v16[0]);
          break;
        default:
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2D,
            (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
            (const char *)0x80070057LL,
            v16[0]);
      }
    }
    else
    {
      wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(a1 + 32);
      v12 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileOpenDialogBroker,IFileDialog,IFileDialog * &,void * &>((void **)(a1 + 32));
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D,
          (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
          (const char *)(unsigned int)v12,
          v16[0]);
    }
    v13 = *(_QWORD *)(a1 + 40);
    *(_QWORD *)(a1 + 40) = a4;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v16);
    result = 0;
  }
  catch ( ... )
  {
    wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(a1 + 40);
    wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(a1 + 32);
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x39,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x140010fbc  mov     rax, rsp
0x140010fbf  mov     [rax+20h], rbx
0x140010fc3  mov     [rax+18h], r8
0x140010fc7  mov     [rax+10h], rdx
0x140010fcb  mov     [rax+8], rcx
0x140010fcf  push    rsi
0x140010fd0  push    rdi
0x140010fd1  push    r14
0x140010fd3  sub     rsp, 70h
0x140010fd7  mov     rsi, r9
0x140010fda  mov     rbx, r8
0x140010fdd  mov     r14, rdx
0x140010fe0  mov     rdi, rcx
0x140010fe3  lea     rdx, aFiledialogbrok_12; "FileDialogBrokerController::RuntimeClas"...
0x140010fea  lea     rcx, [rax-68h]
0x140010fee  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140010ff3  nop
0x140010ff4  mov     rcx, [rsp+88h]; this
0x140010ffc  test    r14, r14
0x140010fff  jnz     short loc_140011017
0x140011001  mov     r9d, 80004003h; char *
0x140011007  lea     r8, aOnecoreuapDsSe_3; "onecoreuap\\ds\\security\\isolation\\br"...
0x14001100e  lea     edx, [r14+16h]; void *
0x140011012  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140011017  lea     rax, [rbx-1]
0x14001101b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001101f  setnbe  al
0x140011022  mov     rcx, [rsp+88h]; this
0x14001102a  test    al, al
0x14001102c  jz      short loc_140011045
0x14001102e  mov     r9d, 80070006h; char *
0x140011034  lea     r8, aOnecoreuapDsSe_3; "onecoreuap\\ds\\security\\isolation\\br"...
0x14001103b  mov     edx, 17h; void *
0x140011040  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140011045  mov     rcx, [rsp+88h]; this
0x14001104d  test    rsi, rsi
0x140011050  jnz     short loc_140011067
0x140011052  mov     r9d, 80004003h; char *
0x140011058  lea     r8, aOnecoreuapDsSe_3; "onecoreuap\\ds\\security\\isolation\\br"...
0x14001105f  lea     edx, [rsi+18h]; void *
0x140011062  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140011067  mov     ecx, [rsp+88h+arg_20]
0x14001106e  test    ecx, ecx
0x140011070  jz      loc_140011176
0x140011076  sub     ecx, 1
0x140011079  jz      loc_140011134
0x14001107f  sub     ecx, 1
0x140011082  jz      short loc_1400110EE
0x140011084  cmp     ecx, 1
0x140011087  jz      short loc_1400110A8
0x140011089  mov     rcx, [rsp+88h]; this
0x140011091  mov     r9d, 80070057h; char *
0x140011097  lea     r8, aOnecoreuapDsSe_3; "onecoreuap\\ds\\security\\isolation\\br"...
0x14001109e  mov     edx, 2Dh ; '-'; void *
0x1400110a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400110a8  lea     rcx, [rdi+20h]
0x1400110ac  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x1400110b1  lea     r8, [rsp+88h+arg_10]
0x1400110b9  lea     rdx, [rsp+88h+arg_8]
0x1400110c1  lea     rcx, [rdi+20h]; void **
0x1400110c5  call    ??$MakeAndInitialize@VFileSaveDialogLegacyBroker@Isolation@Security@Windows@@UIFileDialog@@AEAPEAU5@AEAPEAX@Details@WRL@Microsoft@@YAJPEAPEAUIFileDialog@@AEAPEAU3@AEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileSaveDialogLegacyBroker,IFileDialog,IFileDialog * &,void * &>(IFileDialog * *,IFileDialog * &,void * &)
0x1400110ca  mov     rcx, [rsp+88h]; this
0x1400110d2  test    eax, eax
0x1400110d4  jns     loc_1400111B9
0x1400110da  mov     r9d, eax; char *
0x1400110dd  lea     r8, aOnecoreuapDsSe_3; "onecoreuap\\ds\\security\\isolation\\br"...
0x1400110e4  mov     edx, 29h ; ')'; void *
0x1400110e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400110ee  lea     rcx, [rdi+20h]
0x1400110f2  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x1400110f7  lea     r8, [rsp+88h+arg_10]
0x1400110ff  lea     rdx, [rsp+88h+arg_8]
0x140011107  lea     rcx, [rdi+20h]; void **
0x14001110b  call    ??$MakeAndInitialize@VFileOpenDialogLegacyBroker@Isolation@Security@Windows@@UIFileDialog@@AEAPEAU5@AEAPEAX@Details@WRL@Microsoft@@YAJPEAPEAUIFileDialog@@AEAPEAU3@AEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileOpenDialogLegacyBroker,IFileDialog,IFileDialog * &,void * &>(IFileDialog * *,IFileDialog * &,void * &)
0x140011110  mov     rcx, [rsp+88h]; this
0x140011118  test    eax, eax
0x14001111a  jns     loc_1400111B9
0x140011120  mov     r9d, eax; char *
0x140011123  lea     r8, aOnecoreuapDsSe_3; "onecoreuap\\ds\\security\\isolation\\br"...
0x14001112a  mov     edx, 25h ; '%'; void *
0x14001112f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140011134  lea     rcx, [rdi+20h]
0x140011138  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x14001113d  lea     r8, [rsp+88h+arg_10]
0x140011145  lea     rdx, [rsp+88h+arg_8]
0x14001114d  lea     rcx, [rdi+20h]; void **
0x140011151  call    ??$MakeAndInitialize@VFileSaveDialogBroker@Isolation@Security@Windows@@UIFileDialog@@AEAPEAU5@AEAPEAX@Details@WRL@Microsoft@@YAJPEAPEAUIFileDialog@@AEAPEAU3@AEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileSaveDialogBroker,IFileDialog,IFileDialog * &,void * &>(IFileDialog * *,IFileDialog * &,void * &)
0x140011156  mov     rcx, [rsp+88h]; this
0x14001115e  test    eax, eax
0x140011160  jns     short loc_1400111B9
0x140011162  mov     r9d, eax; char *
0x140011165  lea     r8, aOnecoreuapDsSe_3; "onecoreuap\\ds\\security\\isolation\\br"...
0x14001116c  mov     edx, 21h ; '!'; void *
0x140011171  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140011176  lea     rcx, [rdi+20h]
0x14001117a  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x14001117f  lea     r8, [rsp+88h+arg_10]
0x140011187  lea     rdx, [rsp+88h+arg_8]
0x14001118f  lea     rcx, [rdi+20h]; void **
0x140011193  call    ??$MakeAndInitialize@VFileOpenDialogBroker@Isolation@Security@Windows@@UIFileDialog@@AEAPEAU5@AEAPEAX@Details@WRL@Microsoft@@YAJPEAPEAUIFileDialog@@AEAPEAU3@AEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileOpenDialogBroker,IFileDialog,IFileDialog * &,void * &>(IFileDialog * *,IFileDialog * &,void * &)
0x140011198  mov     rcx, [rsp+88h]; this
0x1400111a0  test    eax, eax
0x1400111a2  jns     short loc_1400111B9
0x1400111a4  mov     r9d, eax; char *
0x1400111a7  lea     r8, aOnecoreuapDsSe_3; "onecoreuap\\ds\\security\\isolation\\br"...
0x1400111ae  mov     edx, 1Dh; void *
0x1400111b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400111b9  mov     rbx, [rdi+28h]
0x1400111bd  mov     [rdi+28h], rsi
0x1400111c1  mov     rax, [rsi]
0x1400111c4  mov     rcx, rsi
0x1400111c7  mov     rax, [rax+8]
0x1400111cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400111d0  test    rbx, rbx
0x1400111d3  jz      short loc_1400111E5
0x1400111d5  mov     rax, [rbx]
0x1400111d8  mov     rcx, rbx
0x1400111db  mov     rax, [rax+10h]
0x1400111df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400111e4  nop
0x1400111e5  lea     rcx, [rsp+88h+var_68]; this
0x1400111ea  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1400111ef  xor     eax, eax
0x1400111f1  jmp     short loc_1400111FA
0x1400111f3  mov     eax, [rsp+88h+arg_8]
0x1400111fa  mov     rbx, [rsp+88h+arg_18]
0x140011202  add     rsp, 70h
0x140011206  pop     r14
0x140011208  pop     rdi
0x140011209  pop     rsi
0x14001120a  retn
```
