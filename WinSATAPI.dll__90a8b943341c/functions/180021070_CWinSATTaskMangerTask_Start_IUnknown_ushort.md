# CWinSATTaskMangerTask::Start(IUnknown *,ushort *)

- ea: `0x180021070`
- end: `0x180021326`
- name: `?Start@CWinSATTaskMangerTask@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `694`
- prototype: `__int64 __fastcall(CWinSATTaskMangerTask *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x18000f0e8`
- `0x18001be2c`
- `0x180021070`
- `0x180025860`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021181`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021181`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180021284`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180021284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021294`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800212ec`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800212ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021154`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021154`

## string_xrefs

- `0x18002108b`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x1800210cb`: `Cannot get the TaskHandlerStatus interface`
- `0x180021105`: `Cannot get the ITaskVariables interface`
- `0x180021138`: `Cannot create cancel event`
- `0x1800211ff`: `Starting  thread is running as ADMIN`
- `0x180021224`: `Starting thread is *NOT* running as ADMIN`
- `0x180021301`: `Cannot create task thread`

## pseudocode

```c
__int64 __fastcall CWinSATTaskMangerTask::Start(CWinSATTaskMangerTask *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  char v5; // bp
  int v6; // esi
  int TheCancelEvent; // ebx
  HANDLE *v9; // rsi
  void *v10; // rdx
  HMODULE v11; // rcx
  void (__fastcall *v12)(void *, __int64, __int64); // rax
  __int64 v13; // r8
  signed int LastError; // eax
  HANDLE Thread; // rax
  bool v16; // [rsp+50h] [rbp+8h] BYREF

  v5 = 0;
  Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 539, "Received START signal !++!");
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_ITaskHandlerStatus,
         (char *)this + 72);
  if ( v6 < 0 )
  {
    Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 544, "Cannot get the TaskHandlerStatus interface");
    return (unsigned int)v6;
  }
  TheCancelEvent = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
                     a2,
                     &IID_ITaskVariables,
                     (char *)this + 80);
  if ( TheCancelEvent >= 0 )
  {
    v9 = (HANDLE *)((char *)this + 112);
    TheCancelEvent = CreateTheCancelEvent((_QWORD *)this + 14, (__int64)this + 120);
    if ( TheCancelEvent < 0 )
    {
      Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 557, "Cannot create cancel event");
      goto LABEL_7;
    }
    v16 = 0;
    if ( (unsigned int)IsUserAdmin(&v16, v10) )
    {
      Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 563, "Cannot determine if running as admin...");
      v12 = (void (__fastcall *)(void *, __int64, __int64))*((_QWORD *)this + 17);
      if ( !v12 )
        goto LABEL_24;
      v13 = 0;
    }
    else if ( v16 )
    {
      Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 567, "Starting  thread is running as ADMIN");
      v12 = (void (__fastcall *)(void *, __int64, __int64))*((_QWORD *)this + 17);
      if ( !v12 )
        goto LABEL_24;
      v13 = 1;
    }
    else
    {
      Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 570, "Starting thread is *NOT* running as ADMIN");
      v12 = (void (__fastcall *)(void *, __int64, __int64))*((_QWORD *)this + 17);
      if ( !v12 )
        goto LABEL_24;
      v13 = 2;
    }
    v12(&unk_18004A8B0, 10268, v13);
LABEL_24:
    TheCancelEvent = (*(__int64 (__fastcall **)(CWinSATTaskMangerTask *))(*(_QWORD *)this + 8LL))(this);
    if ( TheCancelEvent >= 0 )
    {
      v5 = 1;
      if ( GetModuleHandleExW(4u, (LPCWSTR)CWinSATTaskMangerTask::TNThreadProcS, (HMODULE *)this + 12) )
      {
        Thread = CreateThread(0, 0, CWinSATTaskMangerTask::TNThreadProcS, this, 0, (LPDWORD)this + 26);
        *((_QWORD *)this + 11) = Thread;
        if ( Thread )
          return 0;
        Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 605, "Cannot create task thread");
        TheCancelEvent = -2147467259;
      }
      else
      {
        LastError = GetLastError();
        TheCancelEvent = LastError;
        if ( LastError > 0 )
          TheCancelEvent = (unsigned __int16)LastError | 0x80070000;
        Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 593, "Cannot get module handle");
        if ( TheCancelEvent >= 0 )
          return (unsigned int)TheCancelEvent;
      }
    }
LABEL_7:
    if ( *v9 )
    {
      CloseHandle(*v9);
      *v9 = 0;
    }
    if ( v5 )
      (*(void (__fastcall **)(CWinSATTaskMangerTask *))(*(_QWORD *)this + 16LL))(this);
    v11 = (HMODULE)*((_QWORD *)this + 12);
    if ( v11 )
    {
      FreeLibrary(v11);
      *((_QWORD *)this + 12) = 0;
    }
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 9) + 32LL))(
      *((_QWORD *)this + 9),
      (unsigned int)TheCancelEvent);
    return (unsigned int)TheCancelEvent;
  }
  Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 550, "Cannot get the ITaskVariables interface");
  return (unsigned int)TheCancelEvent;
}

```

## disassembly

```asm
0x180021070  mov     [rsp+arg_8], rbx
0x180021075  mov     [rsp+arg_10], rbp
0x18002107a  mov     [rsp+arg_18], rsi
0x18002107f  push    rdi
0x180021080  push    r12
0x180021082  push    r14
0x180021084  sub     rsp, 30h
0x180021088  mov     rbx, rdx
0x18002108b  lea     r12, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021092  mov     rdi, rcx
0x180021095  lea     r8, aReceivedStartS; "Received START signal !++!"
0x18002109c  mov     rcx, r12
0x18002109f  mov     edx, 21Bh
0x1800210a4  xor     bpl, bpl
0x1800210a7  call    Log_Text_F
0x1800210ac  mov     rax, [rbx]
0x1800210af  lea     r8, [rdi+48h]
0x1800210b3  lea     rdx, IID_ITaskHandlerStatus
0x1800210ba  mov     rcx, rbx
0x1800210bd  mov     rax, [rax]
0x1800210c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210c5  mov     esi, eax
0x1800210c7  test    eax, eax
0x1800210c9  jns     short loc_1800210E6
0x1800210cb  lea     r8, aCannotGetTheTa; "Cannot get the TaskHandlerStatus interf"...
0x1800210d2  mov     edx, 220h
0x1800210d7  mov     rcx, r12
0x1800210da  call    Log_Text_F
0x1800210df  mov     eax, esi
0x1800210e1  jmp     loc_1800211A6
0x1800210e6  mov     rax, [rbx]
0x1800210e9  lea     r8, [rdi+50h]
0x1800210ed  lea     rdx, IID_ITaskVariables
0x1800210f4  mov     rcx, rbx
0x1800210f7  mov     rax, [rax]
0x1800210fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210ff  mov     ebx, eax
0x180021101  test    eax, eax
0x180021103  jns     short loc_18002111E
0x180021105  lea     r8, aCannotGetTheIt; "Cannot get the ITaskVariables interface"
0x18002110c  mov     edx, 226h
0x180021111  mov     rcx, r12
0x180021114  call    Log_Text_F
0x180021119  jmp     loc_1800211A4
0x18002111e  lea     rsi, [rdi+70h]
0x180021122  mov     rcx, rsi
0x180021125  lea     rdx, [rdi+78h]
0x180021129  call    ?CreateTheCancelEvent@@YAJAEAPEAXAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; CreateTheCancelEvent(void * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x18002112e  mov     ebx, eax
0x180021130  test    eax, eax
0x180021132  jns     loc_1800211C0
0x180021138  lea     r8, aCannotCreateCa; "Cannot create cancel event"
0x18002113f  mov     edx, 22Dh
0x180021144  mov     rcx, r12
0x180021147  call    Log_Text_F
0x18002114c  mov     rcx, [rsi]; hObject
0x18002114f  test    rcx, rcx
0x180021152  jz      short loc_180021164
0x180021154  call    cs:__imp_CloseHandle
0x18002115b  nop     dword ptr [rax+rax+00h]
0x180021160  and     qword ptr [rsi], 0
0x180021164  test    bpl, bpl
0x180021167  jz      short loc_180021178
0x180021169  mov     rax, [rdi]
0x18002116c  mov     rcx, rdi
0x18002116f  mov     rax, [rax+10h]
0x180021173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021178  mov     rcx, [rdi+60h]; hLibModule
0x18002117c  test    rcx, rcx
0x18002117f  jz      short loc_180021192
0x180021181  call    cs:__imp_FreeLibrary
0x180021188  nop     dword ptr [rax+rax+00h]
0x18002118d  and     qword ptr [rdi+60h], 0
0x180021192  mov     rcx, [rdi+48h]
0x180021196  mov     edx, ebx
0x180021198  mov     rax, [rcx]
0x18002119b  mov     rax, [rax+20h]
0x18002119f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211a4  mov     eax, ebx
0x1800211a6  mov     rbx, [rsp+48h+arg_8]
0x1800211ab  mov     rbp, [rsp+48h+arg_10]
0x1800211b0  mov     rsi, [rsp+48h+arg_18]
0x1800211b5  add     rsp, 30h
0x1800211b9  pop     r14
0x1800211bb  pop     r12
0x1800211bd  pop     rdi
0x1800211be  retn
0x1800211c0  lea     rcx, [rsp+48h+arg_0]; bool *
0x1800211c5  mov     [rsp+48h+arg_0], bpl
0x1800211ca  call    ?IsUserAdmin@@YAKAEA_NPEAX@Z; IsUserAdmin(bool &,void *)
0x1800211cf  mov     rcx, r12
0x1800211d2  test    eax, eax
0x1800211d4  jz      short loc_1800211F8
0x1800211d6  lea     r8, aCannotDetermin_1; "Cannot determine if running as admin..."
0x1800211dd  mov     edx, 233h
0x1800211e2  call    Log_Text_F
0x1800211e7  mov     rax, [rdi+88h]
0x1800211ee  test    rax, rax
0x1800211f1  jz      short loc_180021258
0x1800211f3  xor     r8d, r8d
0x1800211f6  jmp     short loc_180021247
0x1800211f8  cmp     [rsp+48h+arg_0], bpl
0x1800211fd  jz      short loc_180021224
0x1800211ff  lea     r8, aStartingThread_0; "Starting  thread is running as ADMIN"
0x180021206  mov     edx, 237h
0x18002120b  call    Log_Text_F
0x180021210  mov     rax, [rdi+88h]
0x180021217  test    rax, rax
0x18002121a  jz      short loc_180021258
0x18002121c  mov     r8d, 1
0x180021222  jmp     short loc_180021247
0x180021224  lea     r8, aStartingThread; "Starting thread is *NOT* running as ADM"...
0x18002122b  mov     edx, 23Ah
0x180021230  call    Log_Text_F
0x180021235  mov     rax, [rdi+88h]
0x18002123c  test    rax, rax
0x18002123f  jz      short loc_180021258
0x180021241  mov     r8d, 2
0x180021247  mov     edx, 281Ch
0x18002124c  lea     rcx, unk_18004A8B0
0x180021253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021258  mov     rax, [rdi]
0x18002125b  mov     rcx, rdi
0x18002125e  mov     rax, [rax+8]
0x180021262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021267  mov     ebx, eax
0x180021269  test    eax, eax
0x18002126b  js      loc_18002114C
0x180021271  lea     r8, [rdi+60h]; phModule
0x180021275  mov     ecx, 4; dwFlags
0x18002127a  lea     rdx, ?TNThreadProcS@CWinSATTaskMangerTask@@CAKPEAX@Z; lpModuleName
0x180021281  mov     bpl, 1
0x180021284  call    cs:__imp_GetModuleHandleExW
0x18002128b  nop     dword ptr [rax+rax+00h]
0x180021290  test    eax, eax
0x180021292  jnz     short loc_1800212D0
0x180021294  call    cs:__imp_GetLastError
0x18002129b  nop     dword ptr [rax+rax+00h]
0x1800212a0  mov     ebx, eax
0x1800212a2  test    eax, eax
0x1800212a4  jle     short loc_1800212AF
0x1800212a6  movzx   ebx, ax
0x1800212a9  or      ebx, 80070000h
0x1800212af  lea     r8, aCannotGetModul; "Cannot get module handle"
0x1800212b6  mov     edx, 251h
0x1800212bb  mov     rcx, r12
0x1800212be  call    Log_Text_F
0x1800212c3  test    ebx, ebx
0x1800212c5  jns     loc_1800211A4
0x1800212cb  jmp     loc_18002114C
0x1800212d0  lea     rax, [rdi+68h]
0x1800212d4  mov     r9, rdi; lpParameter
0x1800212d7  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800212dc  lea     r8, ?TNThreadProcS@CWinSATTaskMangerTask@@CAKPEAX@Z; lpStartAddress
0x1800212e3  and     [rsp+48h+var_28], 0
0x1800212e8  xor     edx, edx; dwStackSize
0x1800212ea  xor     ecx, ecx; lpThreadAttributes
0x1800212ec  call    cs:__imp_CreateThread
0x1800212f3  nop     dword ptr [rax+rax+00h]
0x1800212f8  mov     [rdi+58h], rax
0x1800212fc  test    rax, rax
0x1800212ff  jnz     short loc_18002131F
0x180021301  lea     r8, aCannotCreateTa; "Cannot create task thread"
0x180021308  mov     edx, 25Dh
0x18002130d  mov     rcx, r12
0x180021310  call    Log_Text_F
0x180021315  mov     ebx, 80004005h
0x18002131a  jmp     loc_18002114C
0x18002131f  xor     ebx, ebx
0x180021321  jmp     loc_1800211A4
```
