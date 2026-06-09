# _finish_create(void *,Concurrency::streams::details::_filestream_callback *,int,int)

- ea: `0x1800abc30`
- end: `0x1800abe9d`
- name: `?_finish_create@@YAXPEAXPEAV_filestream_callback@details@streams@Concurrency@@HH@Z`
- size: `621`
- prototype: `void __fastcall(HANDLE FileHandle, struct Concurrency::streams::details::_filestream_callback *, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800ab560`

## callees

- `0x180016c00`
- `0x180016caf`
- `0x180019024`
- `0x180019e4e`
- `0x18001ad40`
- `0x18001afc0`
- `0x1800a9d4d`
- `0x1800abc30`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abc5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abcea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abd76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abc5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abcea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abd76`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1800abcdc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1800abcdc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800abd70`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800abd70`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x1800abd63`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x1800abd63`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall _finish_create(
        HANDLE FileHandle,
        struct Concurrency::streams::details::_filestream_callback *a2,
        int a3,
        int a4)
{
  DWORD LastError; // eax
  _QWORD *system_error; // rbx
  struct _TP_IO *ThreadpoolIo; // r15
  DWORD v11; // eax
  _QWORD *v12; // rbx
  bool v13; // zf
  __int64 v14; // rbx
  _QWORD *v15; // rax
  _QWORD *v16; // rdi
  __int128 v17; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v18[48]; // [rsp+30h] [rbp-58h] BYREF

  if ( FileHandle == (HANDLE)-1LL || (ThreadpoolIo = CreateThreadpoolIo(FileHandle, IoCompletionCallback, 0, 0)) == 0 )
  {
    LastError = GetLastError();
    system_error = (_QWORD *)utility::details::create_system_error(v18, LastError);
    v17 = 0;
    __ExceptionPtrCreate(&v17);
    __ExceptionPtrCopyException(&v17, system_error, &TI4_AVsystem_error_std__);
    *system_error = &std::exception::`vftable';
    o___std_exception_destroy_0(system_error + 1);
    (*(void (__fastcall **)(struct Concurrency::streams::details::_filestream_callback *, __int128 *))(*(_QWORD *)a2 + 16LL))(
      a2,
      &v17);
    __ExceptionPtrDestroy(&v17);
  }
  else if ( SetFileCompletionNotificationModes(FileHandle, 1u) )
  {
    if ( a3 != 1 || (v13 = a4 == 16, v14 = 512, !v13) )
      v14 = 0;
    v15 = operator new(0xA0u);
    v16 = v15;
    if ( v15 )
    {
      *v15 = 0;
      v15[1] = 0;
      *((_BYTE *)v15 + 16) = 0;
      v15[3] = v14;
      v15[4] = 0;
      v15[5] = 0;
      v15[6] = 0;
      v15[7] = 0;
      *((_DWORD *)v15 + 16) = a3;
      pplx::details::critical_section_impl::critical_section_impl((pplx::details::critical_section_impl *)(v15 + 9));
      *((_DWORD *)v16 + 34) = 0;
      *((_DWORD *)v16 + 35) = -1;
      v16[18] = FileHandle;
      v16[19] = ThreadpoolIo;
    }
    else
    {
      v16 = 0;
    }
    if ( (a3 & 0xC) != 0 )
      v16[1] = -1;
    (**(void (__fastcall ***)(struct Concurrency::streams::details::_filestream_callback *, _QWORD *))a2)(a2, v16);
  }
  else
  {
    CloseThreadpoolIo(ThreadpoolIo);
    v11 = GetLastError();
    v12 = (_QWORD *)utility::details::create_system_error(v18, v11);
    v17 = 0;
    __ExceptionPtrCreate(&v17);
    __ExceptionPtrCopyException(&v17, v12, &TI4_AVsystem_error_std__);
    *v12 = &std::exception::`vftable';
    o___std_exception_destroy_0(v12 + 1);
    (*(void (__fastcall **)(struct Concurrency::streams::details::_filestream_callback *, __int128 *))(*(_QWORD *)a2 + 16LL))(
      a2,
      &v17);
    __ExceptionPtrDestroy(&v17);
  }
}

```

## disassembly

```asm
0x1800abc30  mov     [rsp+arg_8], rbx
0x1800abc35  mov     [rsp+arg_10], rbp
0x1800abc3a  push    rsi
0x1800abc3b  push    rdi
0x1800abc3c  push    r12
0x1800abc3e  push    r14
0x1800abc40  push    r15
0x1800abc42  sub     rsp, 60h
0x1800abc46  mov     ebx, r9d
0x1800abc49  mov     ebp, r8d
0x1800abc4c  mov     r14, rdx
0x1800abc4f  mov     rsi, rcx
0x1800abc52  xor     r12d, r12d
0x1800abc55  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800abc59  jnz     short loc_1800ABCCF
0x1800abc5b  call    cs:__imp_GetLastError
0x1800abc61  mov     edx, eax
0x1800abc63  lea     rcx, [rsp+88h+var_58]
0x1800abc68  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x1800abc6d  mov     rbx, rax
0x1800abc70  xorps   xmm0, xmm0
0x1800abc73  movdqu  [rsp+88h+var_68], xmm0
0x1800abc79  lea     rcx, [rsp+88h+var_68]; void *
0x1800abc7e  call    ?__ExceptionPtrCreate@@YAXPEAX@Z_0; __ExceptionPtrCreate(void *)
0x1800abc83  lea     r8, _TI4?AVsystem_error@std@@; void *
0x1800abc8a  mov     rdx, rbx; void *
0x1800abc8d  lea     rcx, [rsp+88h+var_68]; void *
0x1800abc92  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z_0; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800abc97  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800abc9e  mov     [rbx], rax
0x1800abca1  lea     rcx, [rbx+8]
0x1800abca5  call    _o___std_exception_destroy_0
0x1800abcaa  nop
0x1800abcab  mov     rax, [r14]
0x1800abcae  lea     rdx, [rsp+88h+var_68]
0x1800abcb3  mov     rcx, r14
0x1800abcb6  mov     rax, [rax+10h]
0x1800abcba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abcbf  nop
0x1800abcc0  lea     rcx, [rsp+88h+var_68]; void *
0x1800abcc5  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800abcca  jmp     loc_1800ABE84
0x1800abccf  xor     r9d, r9d; pcbe
0x1800abcd2  xor     r8d, r8d; pv
0x1800abcd5  lea     rdx, ?IoCompletionCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x1800abcdc  call    cs:__imp_CreateThreadpoolIo
0x1800abce2  mov     r15, rax
0x1800abce5  test    rax, rax
0x1800abce8  jnz     short loc_1800ABD5E
0x1800abcea  call    cs:__imp_GetLastError
0x1800abcf0  mov     edx, eax
0x1800abcf2  lea     rcx, [rsp+88h+var_58]
0x1800abcf7  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x1800abcfc  mov     rbx, rax
0x1800abcff  xorps   xmm0, xmm0
0x1800abd02  movdqu  [rsp+88h+var_68], xmm0
0x1800abd08  lea     rcx, [rsp+88h+var_68]; void *
0x1800abd0d  call    ?__ExceptionPtrCreate@@YAXPEAX@Z_0; __ExceptionPtrCreate(void *)
0x1800abd12  lea     r8, _TI4?AVsystem_error@std@@; void *
0x1800abd19  mov     rdx, rbx; void *
0x1800abd1c  lea     rcx, [rsp+88h+var_68]; void *
0x1800abd21  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z_0; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800abd26  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800abd2d  mov     [rbx], rax
0x1800abd30  lea     rcx, [rbx+8]
0x1800abd34  call    _o___std_exception_destroy_0
0x1800abd39  nop
0x1800abd3a  mov     rax, [r14]
0x1800abd3d  lea     rdx, [rsp+88h+var_68]
0x1800abd42  mov     rcx, r14
0x1800abd45  mov     rax, [rax+10h]
0x1800abd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abd4e  nop
0x1800abd4f  lea     rcx, [rsp+88h+var_68]; void *
0x1800abd54  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800abd59  jmp     loc_1800ABE84
0x1800abd5e  mov     dl, 1; Flags
0x1800abd60  mov     rcx, rsi; FileHandle
0x1800abd63  call    cs:__imp_SetFileCompletionNotificationModes
0x1800abd69  test    eax, eax
0x1800abd6b  jnz     short loc_1800ABDEA
0x1800abd6d  mov     rcx, r15; pio
0x1800abd70  call    cs:__imp_CloseThreadpoolIo
0x1800abd76  call    cs:__imp_GetLastError
0x1800abd7c  mov     edx, eax
0x1800abd7e  lea     rcx, [rsp+88h+var_58]
0x1800abd83  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x1800abd88  mov     rbx, rax
0x1800abd8b  xorps   xmm0, xmm0
0x1800abd8e  movdqu  [rsp+88h+var_68], xmm0
0x1800abd94  lea     rcx, [rsp+88h+var_68]; void *
0x1800abd99  call    ?__ExceptionPtrCreate@@YAXPEAX@Z_0; __ExceptionPtrCreate(void *)
0x1800abd9e  lea     r8, _TI4?AVsystem_error@std@@; void *
0x1800abda5  mov     rdx, rbx; void *
0x1800abda8  lea     rcx, [rsp+88h+var_68]; void *
0x1800abdad  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z_0; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800abdb2  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800abdb9  mov     [rbx], rax
0x1800abdbc  lea     rcx, [rbx+8]
0x1800abdc0  call    _o___std_exception_destroy_0
0x1800abdc5  nop
0x1800abdc6  mov     rax, [r14]
0x1800abdc9  lea     rdx, [rsp+88h+var_68]
0x1800abdce  mov     rcx, r14
0x1800abdd1  mov     rax, [rax+10h]
0x1800abdd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abdda  nop
0x1800abddb  lea     rcx, [rsp+88h+var_68]; void *
0x1800abde0  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800abde5  jmp     loc_1800ABE84
0x1800abdea  cmp     ebp, 1
0x1800abded  jnz     short loc_1800ABDF9
0x1800abdef  cmp     ebx, 10h
0x1800abdf2  mov     ebx, 200h
0x1800abdf7  jz      short loc_1800ABDFC
0x1800abdf9  mov     rbx, r12
0x1800abdfc  mov     ecx, 0A0h; Size
0x1800abe01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800abe06  mov     rdi, rax
0x1800abe09  mov     [rsp+88h+arg_0], rax
0x1800abe11  test    rax, rax
0x1800abe14  jz      short loc_1800ABE62
0x1800abe16  mov     [rax], r12
0x1800abe19  mov     [rax+8], r12
0x1800abe1d  mov     byte ptr [rax+10h], 0
0x1800abe21  mov     [rax+18h], rbx
0x1800abe25  mov     [rax+20h], r12
0x1800abe29  mov     [rax+28h], r12
0x1800abe2d  mov     [rax+30h], r12
0x1800abe31  mov     [rax+38h], r12
0x1800abe35  mov     [rax+40h], ebp
0x1800abe38  lea     rcx, [rax+48h]; this
0x1800abe3c  call    ??0critical_section_impl@details@pplx@@QEAA@XZ; pplx::details::critical_section_impl::critical_section_impl(void)
0x1800abe41  mov     [rdi+88h], r12d
0x1800abe48  mov     dword ptr [rdi+8Ch], 0FFFFFFFFh
0x1800abe52  mov     [rdi+90h], rsi
0x1800abe59  mov     [rdi+98h], r15
0x1800abe60  jmp     short loc_1800ABE65
0x1800abe62  mov     rdi, r12
0x1800abe65  test    bpl, 0Ch
0x1800abe69  jz      short loc_1800ABE73
0x1800abe6b  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x1800abe73  mov     rax, [r14]
0x1800abe76  mov     rdx, rdi
0x1800abe79  mov     rcx, r14
0x1800abe7c  mov     rax, [rax]
0x1800abe7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abe84  lea     r11, [rsp+88h+var_28]
0x1800abe89  mov     rbx, [r11+38h]
0x1800abe8d  mov     rbp, [r11+40h]
0x1800abe91  mov     rsp, r11
0x1800abe94  pop     r15
0x1800abe96  pop     r14
0x1800abe98  pop     r12
0x1800abe9a  pop     rdi
0x1800abe9b  pop     rsi
0x1800abe9c  retn
```
