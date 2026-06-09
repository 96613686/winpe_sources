# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_GetIncomingToastActionIconPath(WindowsInternal::ApplicationModel::Calls::IncomingToastAction,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x180014510`
- end: `0x1800146ac`
- name: `?_GetIncomingToastActionIconPath@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJW4IncomingToastAction@234@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800021b4`
- `0x180004a0c`
- `0x180011aa4`
- `0x180011e68`
- `0x180014510`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014553`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180014549`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180014549`
- `api-ms-win-shcore-scaling-l1-1-1!GetScaleFactorForMonitor` at `0x1800145a0`
- `api-ms-win-shcore-scaling-l1-1-1!GetScaleFactorForMonitor` at `0x1800145a0`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_GetIncomingToastActionIconPath(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  signed int LastError; // eax
  __int64 v7; // r8
  signed int ScaleFactorForMonitor; // ebx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v12; // rcx
  __int64 IncomingToastActionText; // rdi
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // [rsp+30h] [rbp-D0h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v18; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+4Ah] [rbp-B6h]
  int v20; // [rsp+52h] [rbp-AEh]
  __int16 v21; // [rsp+56h] [rbp-AAh]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    ScaleFactorForMonitor = LastError;
    if ( LastError > 0 )
      ScaleFactorForMonitor = (unsigned __int16)LastError | 0x80070000;
    v9 = 0;
    v10 = 784;
    goto LABEL_5;
  }
  v12 = 4;
  if ( a2 != 1 )
    v12 = a2;
  v16 = 0;
  IncomingToastActionText = WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::GetIncomingToastActionText(v12);
  ScaleFactorForMonitor = GetScaleFactorForMonitor(0, &v16);
  if ( ScaleFactorForMonitor < 0 )
  {
    v9 = 1;
    v10 = 794;
LABEL_5:
    Log_HREvent_1((unsigned int)ScaleFactorForMonitor, v9, v7, v10);
    return (unsigned int)ScaleFactorForMonitor;
  }
  v19 = 0;
  v21 = 0;
  v20 = 0;
  Block[0] = &v18;
  Block[1] = &v18;
  v18 = 0;
  ScaleFactorForMonitor = (*(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)a1 + 160LL))(a1, v16, Block);
  if ( ScaleFactorForMonitor < 0 )
  {
    v15 = 797;
    goto LABEL_13;
  }
  ScaleFactorForMonitor = tlx::append_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                            a3,
                            L"%s\\SystemResources\\Windows.Systemtoast.Calling\\Images\\%s.scale-%s.png",
                            Buffer,
                            IncomingToastActionText,
                            Block[0]);
  if ( ScaleFactorForMonitor < 0 )
  {
    v15 = 799;
LABEL_13:
    Log_HREvent_1((unsigned int)ScaleFactorForMonitor, 1, v14, v15);
    if ( Block[0] != &v18 )
      operator delete(Block[0]);
    return (unsigned int)ScaleFactorForMonitor;
  }
  if ( Block[0] != &v18 )
    operator delete(Block[0]);
  return 0;
}

```

## disassembly

```asm
0x180014510  push    rbp
0x180014512  push    rbx
0x180014513  push    rsi
0x180014514  push    rdi
0x180014515  push    r14
0x180014517  lea     rbp, [rsp-180h]
0x18001451f  sub     rsp, 280h
0x180014526  mov     rax, cs:__security_cookie
0x18001452d  xor     rax, rsp
0x180014530  mov     [rbp+1A0h+var_30], rax
0x180014537  mov     ebx, edx
0x180014539  mov     r14, rcx
0x18001453c  mov     edx, 104h; uSize
0x180014541  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180014546  mov     rsi, r8
0x180014549  call    cs:__imp_GetSystemWindowsDirectoryW
0x18001454f  test    eax, eax
0x180014551  jnz     short loc_18001457E
0x180014553  call    cs:__imp_GetLastError
0x180014559  mov     ebx, eax
0x18001455b  test    eax, eax
0x18001455d  jle     short loc_180014568
0x18001455f  movzx   ebx, ax
0x180014562  or      ebx, 80070000h
0x180014568  xor     edx, edx
0x18001456a  mov     r9d, 310h
0x180014570  mov     ecx, ebx
0x180014572  call    Log_HREvent_1
0x180014577  mov     eax, ebx
0x180014579  jmp     loc_18001468F
0x18001457e  mov     ecx, 4
0x180014583  cmp     ebx, 1
0x180014586  cmovnz  ecx, ebx
0x180014589  call    ?GetIncomingToastActionText@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@SAPEBGW4IncomingToastAction@234@@Z; WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::GetIncomingToastActionText(WindowsInternal::ApplicationModel::Calls::IncomingToastAction)
0x18001458e  lea     rdx, [rsp+2A0h+var_270]
0x180014593  mov     [rsp+2A0h+var_270], 0
0x18001459b  xor     ecx, ecx
0x18001459d  mov     rdi, rax
0x1800145a0  call    cs:__imp_GetScaleFactorForMonitor
0x1800145a6  mov     ebx, eax
0x1800145a8  test    eax, eax
0x1800145aa  jns     short loc_1800145B9
0x1800145ac  mov     edx, 1
0x1800145b1  mov     r9d, 31Ah
0x1800145b7  jmp     short loc_180014570
0x1800145b9  mov     edx, [rsp+2A0h+var_270]
0x1800145bd  lea     r8, [rsp+2A0h+Block]
0x1800145c2  xor     eax, eax
0x1800145c4  mov     [rsp+2A0h+var_256], 0
0x1800145cd  mov     [rsp+2A0h+var_24A], ax
0x1800145d2  mov     rcx, r14
0x1800145d5  lea     rax, [rsp+2A0h+var_258]
0x1800145da  mov     [rsp+2A0h+var_24E], 0
0x1800145e2  mov     [rsp+2A0h+Block], rax
0x1800145e7  lea     rax, [rsp+2A0h+var_258]
0x1800145ec  mov     [rsp+2A0h+var_260], rax
0x1800145f1  xor     eax, eax
0x1800145f3  mov     [rsp+2A0h+var_258], ax
0x1800145f8  mov     rax, [r14]
0x1800145fb  mov     rax, [rax+0A0h]
0x180014602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014607  mov     ebx, eax
0x180014609  test    eax, eax
0x18001460b  jns     short loc_180014643
0x18001460d  mov     r9d, 31Dh
0x180014613  mov     edx, 1
0x180014618  mov     ecx, ebx
0x18001461a  call    Log_HREvent_1
0x18001461f  mov     rcx, [rsp+2A0h+Block]; Block
0x180014624  lea     rax, [rsp+2A0h+var_258]
0x180014629  cmp     rcx, rax
0x18001462c  jz      loc_180014577
0x180014632  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180014639  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001463e  jmp     loc_180014577
0x180014643  mov     rax, [rsp+2A0h+Block]
0x180014648  lea     r8, [rsp+2A0h+Buffer]
0x18001464d  mov     r9, rdi
0x180014650  mov     [rsp+2A0h+var_280], rax
0x180014655  lea     rdx, aSSystemresourc; "%s\\SystemResources\\Windows.Systemtoas"...
0x18001465c  mov     rcx, rsi
0x18001465f  call    ??$append_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::append_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180014664  mov     ebx, eax
0x180014666  test    eax, eax
0x180014668  jns     short loc_180014672
0x18001466a  mov     r9d, 31Fh
0x180014670  jmp     short loc_180014613
0x180014672  mov     rcx, [rsp+2A0h+Block]; Block
0x180014677  lea     rax, [rsp+2A0h+var_258]
0x18001467c  cmp     rcx, rax
0x18001467f  jz      short loc_18001468D
0x180014681  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180014688  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001468d  xor     eax, eax
0x18001468f  mov     rcx, [rbp+1A0h+var_30]
0x180014696  xor     rcx, rsp; StackCookie
0x180014699  call    __security_check_cookie
0x18001469e  add     rsp, 280h
0x1800146a5  pop     r14
0x1800146a7  pop     rdi
0x1800146a8  pop     rsi
0x1800146a9  pop     rbx
0x1800146aa  pop     rbp
0x1800146ab  retn
```
