# AiSvcOnCreateProcess

- ea: `0x180008578`
- end: `0x180008806`
- name: `AiSvcOnCreateProcess`
- size: `654`
- prototype: `int __fastcall(int, unsigned __int16, void *, __int16, int, int, __int64, __int64, int, __int64, int, __int64, int, void *, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18000b3d0`

## callees

- `0x1800011c8`
- `0x180005d5c`
- `0x180006228`
- `0x180008578`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008774`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800087c8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008774`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800087c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008745`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000873a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000873a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000879a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000879a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008612`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000878d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008612`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000878d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087e1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800085e1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800085e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800085c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800085c5`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000871d`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000871d`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800085a6`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800085a6`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000875d`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800087b1`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000875d`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800087b1`

## pseudocode

```c
int __fastcall AiSvcOnCreateProcess(
        int a1,
        unsigned __int16 a2,
        void *a3,
        __int16 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        __int64 a10,
        int a11,
        __int64 a12,
        int a13,
        void *a14,
        int a15,
        __int64 a16)
{
  int v20; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v24; // ebx
  void *v25; // r10
  void *v26; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  signed int v28; // eax
  unsigned int v29; // edi
  void *TokenHandle; // [rsp+90h] [rbp-48h] BYREF
  void *v31; // [rsp+98h] [rbp-40h]
  struct _RTL_SRWLOCK *v32; // [rsp+A0h] [rbp-38h]
  char v33; // [rsp+A8h] [rbp-30h]

  v20 = RtlRunOnceExecuteOnce(&SmartlockerRunOnce, AipInitializeSmartlockerTelemetry, 0, 0);
  if ( v20 < 0 )
    return v20 | 0x10000000;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v24 = LastError;
    if ( LastError > 0 )
      v24 = (unsigned __int16)LastError | 0x80070000;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v24;
  }
  v25 = operator new(0x108u);
  v31 = v25;
  if ( v25 )
    v26 = (void *)ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA(
                    (int)v25,
                    (int)&TokenHandle,
                    a1,
                    a2,
                    a3,
                    a4,
                    a5,
                    a6,
                    a7,
                    a8,
                    a9,
                    a12,
                    a13,
                    a10,
                    a11,
                    a14,
                    a15,
                    a16);
  else
    v26 = 0;
  v31 = v26;
  v32 = &SmLock;
  v33 = 0;
  RtlAcquireSRWLockShared(&SmLock);
  if ( SmartlockerTpCallbackEnv )
  {
    ThreadpoolWork = CreateThreadpoolWork(OnCreateProcessCallback, v26, SmartlockerTpCallbackEnv);
    if ( !ThreadpoolWork )
    {
      v28 = GetLastError();
      v29 = v28;
      if ( v28 > 0 )
        v29 = (unsigned __int16)v28 | 0x80070000;
      RtlReleaseSRWLockShared(&SmLock);
      if ( v26 )
      {
        ON_CREATE_PROC_DATA::~ON_CREATE_PROC_DATA((ON_CREATE_PROC_DATA *)v26);
        operator delete(v26);
      }
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      return v29;
    }
    SubmitThreadpoolWork(ThreadpoolWork);
    v31 = 0;
    v26 = 0;
  }
  RtlReleaseSRWLockShared(&SmLock);
  if ( v26 )
  {
    ON_CREATE_PROC_DATA::~ON_CREATE_PROC_DATA((ON_CREATE_PROC_DATA *)v26);
    operator delete(v26);
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180008578  push    rbx
0x18000857a  push    rsi
0x18000857b  push    rdi
0x18000857c  push    r14
0x18000857e  sub     rsp, 0B8h
0x180008585  movzx   ebx, r9w
0x180008589  mov     rdi, r8
0x18000858c  movzx   esi, dx
0x18000858f  mov     r14, rcx
0x180008592  xor     r9d, r9d
0x180008595  xor     r8d, r8d
0x180008598  lea     rdx, ?AipInitializeSmartlockerTelemetry@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; AipInitializeSmartlockerTelemetry(_RTL_RUN_ONCE *,void *,void * *)
0x18000859f  lea     rcx, ?SmartlockerRunOnce@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE SmartlockerRunOnce
0x1800085a6  call    cs:__imp_RtlRunOnceExecuteOnce
0x1800085ac  test    eax, eax
0x1800085ae  jns     short loc_1800085B9
0x1800085b0  bts     eax, 1Ch
0x1800085b4  jmp     loc_1800087F8
0x1800085b9  mov     [rsp+0D8h+TokenHandle], 0
0x1800085c5  call    cs:__imp_GetCurrentThread
0x1800085cb  lea     r9, [rsp+0D8h+TokenHandle]; TokenHandle
0x1800085d3  mov     edx, 2000Eh; DesiredAccess
0x1800085d8  mov     r8d, 1; OpenAsSelf
0x1800085de  mov     rcx, rax; ThreadHandle
0x1800085e1  call    cs:__imp_OpenThreadToken
0x1800085e7  test    eax, eax
0x1800085e9  jnz     short loc_18000861F
0x1800085eb  call    cs:__imp_GetLastError
0x1800085f1  mov     ebx, eax
0x1800085f3  test    eax, eax
0x1800085f5  jle     short loc_180008600
0x1800085f7  movzx   ebx, ax
0x1800085fa  or      ebx, 80070000h
0x180008600  mov     rcx, [rsp+0D8h+TokenHandle]; hObject
0x180008608  lea     rdx, [rcx-1]
0x18000860c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180008610  ja      short loc_180008618
0x180008612  call    cs:__imp_CloseHandle
0x180008618  mov     eax, ebx
0x18000861a  jmp     loc_1800087F8
0x18000861f  mov     ecx, 108h; Size
0x180008624  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008629  mov     r10, rax
0x18000862c  mov     [rsp+0D8h+var_40], rax
0x180008634  test    rax, rax
0x180008637  jz      loc_1800086F9
0x18000863d  mov     rcx, [rsp+0D8h+arg_78]
0x180008645  mov     [rsp+0D8h+var_50], rcx; __int64
0x18000864d  mov     ecx, [rsp+0D8h+arg_70]
0x180008654  mov     [rsp+0D8h+var_58], ecx; int
0x18000865b  mov     rcx, [rsp+0D8h+arg_68]
0x180008663  mov     [rsp+0D8h+var_60], rcx; void *
0x180008668  mov     ecx, [rsp+0D8h+arg_50]
0x18000866f  mov     [rsp+0D8h+var_68], ecx; int
0x180008673  mov     rax, [rsp+0D8h+arg_48]
0x18000867b  mov     [rsp+0D8h+var_70], rax; __int64
0x180008680  mov     eax, [rsp+0D8h+arg_60]
0x180008687  mov     [rsp+0D8h+var_78], eax; int
0x18000868b  mov     rax, [rsp+0D8h+arg_58]
0x180008693  mov     [rsp+0D8h+var_80], rax; __int64
0x180008698  mov     eax, [rsp+0D8h+arg_40]
0x18000869f  mov     [rsp+0D8h+var_88], eax; int
0x1800086a3  mov     rax, [rsp+0D8h+arg_38]
0x1800086ab  mov     [rsp+0D8h+var_90], rax; __int64
0x1800086b0  mov     rax, [rsp+0D8h+arg_30]
0x1800086b8  mov     [rsp+0D8h+var_98], rax; __int64
0x1800086bd  mov     eax, [rsp+0D8h+arg_28]
0x1800086c4  mov     [rsp+0D8h+var_A0], eax; int
0x1800086c8  mov     eax, [rsp+0D8h+arg_20]
0x1800086cf  mov     [rsp+0D8h+var_A8], eax; int
0x1800086d3  mov     [rsp+0D8h+var_B0], bx; __int16
0x1800086d8  mov     [rsp+0D8h+var_B8], rdi; void *
0x1800086dd  movzx   r9d, si; int
0x1800086e1  mov     r8, r14; int
0x1800086e4  lea     rdx, [rsp+0D8h+TokenHandle]; int
0x1800086ec  mov     rcx, r10; int
0x1800086ef  call    ??0ON_CREATE_PROC_DATA@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGG1GJK_KPEBEK3K3K1KPEBU_GUID@@@Z; ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,ushort const *,ushort,ushort const *,ushort,long,ulong,unsigned __int64,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,ushort const *,ulong,_GUID const *)
0x1800086f4  mov     rbx, rax
0x1800086f7  jmp     short loc_1800086FB
0x1800086f9  xor     ebx, ebx
0x1800086fb  mov     [rsp+0D8h+var_40], rbx
0x180008703  lea     rsi, ?SmLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SmLock
0x18000870a  mov     [rsp+0D8h+var_38], rsi
0x180008712  mov     [rsp+0D8h+var_30], 0
0x18000871a  mov     rcx, rsi
0x18000871d  call    cs:__imp_RtlAcquireSRWLockShared
0x180008723  nop
0x180008724  mov     r8, cs:?SmartlockerTpCallbackEnv@@3PEAU_TP_CALLBACK_ENVIRON_V3@@EA; pcbe
0x18000872b  test    r8, r8
0x18000872e  jz      short loc_1800087AE
0x180008730  mov     rdx, rbx; pv
0x180008733  lea     rcx, ?OnCreateProcessCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000873a  call    cs:__imp_CreateThreadpoolWork
0x180008740  test    rax, rax
0x180008743  jnz     short loc_180008797
0x180008745  call    cs:__imp_GetLastError
0x18000874b  mov     edi, eax
0x18000874d  test    eax, eax
0x18000874f  jle     short loc_18000875A
0x180008751  movzx   edi, ax
0x180008754  or      edi, 80070000h
0x18000875a  mov     rcx, rsi
0x18000875d  call    cs:__imp_RtlReleaseSRWLockShared
0x180008763  nop
0x180008764  test    rbx, rbx
0x180008767  jz      short loc_18000877B
0x180008769  mov     rcx, rbx; this
0x18000876c  call    ??1ON_CREATE_PROC_DATA@@QEAA@XZ; ON_CREATE_PROC_DATA::~ON_CREATE_PROC_DATA(void)
0x180008771  mov     rcx, rbx
0x180008774  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000877a  nop
0x18000877b  mov     rcx, [rsp+0D8h+TokenHandle]; hObject
0x180008783  lea     rdx, [rcx-1]
0x180008787  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000878b  ja      short loc_180008793
0x18000878d  call    cs:__imp_CloseHandle
0x180008793  mov     eax, edi
0x180008795  jmp     short loc_1800087F8
0x180008797  mov     rcx, rax; pwk
0x18000879a  call    cs:__imp_SubmitThreadpoolWork
0x1800087a0  mov     [rsp+0D8h+var_40], 0
0x1800087ac  xor     ebx, ebx
0x1800087ae  mov     rcx, rsi
0x1800087b1  call    cs:__imp_RtlReleaseSRWLockShared
0x1800087b7  nop
0x1800087b8  test    rbx, rbx
0x1800087bb  jz      short loc_1800087CF
0x1800087bd  mov     rcx, rbx; this
0x1800087c0  call    ??1ON_CREATE_PROC_DATA@@QEAA@XZ; ON_CREATE_PROC_DATA::~ON_CREATE_PROC_DATA(void)
0x1800087c5  mov     rcx, rbx
0x1800087c8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800087ce  nop
0x1800087cf  mov     rcx, [rsp+0D8h+TokenHandle]; hObject
0x1800087d7  lea     rax, [rcx-1]
0x1800087db  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800087df  ja      short loc_1800087E8
0x1800087e1  call    cs:__imp_CloseHandle
0x1800087e7  nop
0x1800087e8  xor     eax, eax
0x1800087ea  jmp     short loc_1800087F8
0x1800087ec  mov     eax, 8007000Eh
0x1800087f1  jmp     short loc_1800087F8
0x1800087f3  mov     eax, 8000FFFFh
0x1800087f8  add     rsp, 0B8h
0x1800087ff  pop     r14
0x180008801  pop     rdi
0x180008802  pop     rsi
0x180008803  pop     rbx
0x180008804  retn
```
