# CUpdateDeploymentProvider::CreateUpdateDeploymentSessionFactory(wchar_t const *,_GUID,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x180013160`
- end: `0x1800133b2`
- name: `?CreateUpdateDeploymentSessionFactory@CUpdateDeploymentProvider@@UEAAJPEB_WU_GUID@@_K22@Z`
- size: `594`
- prototype: `int(CUpdateDeploymentProvider *__hidden this, const wchar_t *, struct _GUID *__struct_ptr, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180002214`
- `0x180003180`
- `0x180007b9c`
- `0x18000bbd8`
- `0x1800110fc`
- `0x180013160`
- `0x18001cadc`
- `0x180061960`
- `0x180068ea0`
- `0x180069960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800132d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800132d4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180013364`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180013364`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013247`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013247`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001326d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001326d`

## string_xrefs

- `0x180013296`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentProvider.cpp`
- `0x180013337`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentProvider.cpp`
- `0x180013379`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentProvider.cpp`
- `0x1800132b6`: `Deployment session (host process %d) parent thread/process exited..Terminating now...`
- `0x180013312`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentSession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CUpdateDeploymentProvider::CreateUpdateDeploymentSessionFactory(
        CUpdateDeploymentProvider *this,
        const wchar_t *a2,
        struct _GUID *a3,
        void *a4,
        HANDLE hEvent,
        void *a6)
{
  unsigned int v9; // edx
  __int64 v10; // rdx
  int LastError; // ebx
  __int64 v12; // rdx
  const char *v13; // r9
  __int64 v14; // rdx
  DWORD v15; // eax
  const wchar_t *v16; // r12
  unsigned int v17; // edx
  int v18; // eax
  int v20; // [rsp+20h] [rbp-60h]
  int v21; // [rsp+40h] [rbp-40h] BYREF
  struct CUpdateDeploymentSession *v22; // [rsp+48h] [rbp-38h] BYREF
  struct _GUID v23; // [rsp+50h] [rbp-30h] BYREF
  HANDLE Handles[2]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  if ( !a2 || !*a2 )
  {
    v10 = 73;
    goto LABEL_34;
  }
  if ( !memcmp(a3, &GUID_NULL, 0x10u) )
  {
    v10 = 74;
LABEL_34:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentProvider.cpp",
      (const char *)0x80070057LL,
      v20);
    return (unsigned int)LastError;
  }
  if ( !hEvent )
  {
    v10 = 75;
    goto LABEL_34;
  }
  if ( !a6 )
  {
    v10 = 76;
    goto LABEL_34;
  }
  v21 = 0;
  v22 = 0;
  *(_OWORD *)Handles = 0;
  LastError = CCoInit::Initialize((CCoInit *)&v21, v9, 1);
  if ( LastError < 0 )
  {
    v12 = 82;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentProvider.cpp",
      (const char *)(unsigned int)LastError,
      v20);
    goto LABEL_29;
  }
  v23 = *a3;
  LastError = CUpdateDeploymentSession::CreateInstance(a2, &v23, &v22);
  if ( LastError < 0 )
  {
    v12 = 86;
    goto LABEL_27;
  }
  if ( SetEvent(hEvent) )
  {
    Handles[0] = a6;
    Handles[1] = a4;
    v15 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( v15 == 258 )
    {
      LastError = -2147024638;
      v12 = 95;
      goto LABEL_27;
    }
    if ( v15 )
    {
      if ( v15 != 1 )
      {
        v14 = 96;
        goto LABEL_20;
      }
      v16 = L"Deployment session (host process %d) parent thread/process exited..Terminating now...";
    }
    else
    {
      v16 = L"Deployment session (host process %d) signalled to exit...";
    }
    GetCurrentProcessId();
    WUTrace(0, 0, 1, 4, 0, v16);
    while ( 1 )
    {
      v18 = CWuaClassFactoryBase::UnregisterClassFactory(v22, v17);
      LastError = v18;
      if ( v18 >= 0 )
        break;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentSession.cpp",
        (const char *)(unsigned int)v18,
        v20);
      if ( LastError != -2147417825 )
      {
        v12 = 121;
        goto LABEL_27;
      }
    }
    LastError = 0;
    goto LABEL_29;
  }
  v14 = 88;
LABEL_20:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v14,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentProvider.cpp",
                v13);
LABEL_29:
  if ( v22 )
    (*(void (__fastcall **)(struct CUpdateDeploymentSession *))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v21 )
    CoUninitialize();
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180013160  mov     [rsp-38h+arg_0], rbx
0x180013165  push    rbp
0x180013166  push    rsi
0x180013167  push    rdi
0x180013168  push    r12
0x18001316a  push    r13
0x18001316c  push    r14
0x18001316e  push    r15
0x180013170  mov     rbp, rsp
0x180013173  sub     rsp, 80h
0x18001317a  mov     rax, cs:__security_cookie
0x180013181  xor     rax, rsp
0x180013184  mov     [rbp+var_10], rax
0x180013188  mov     r13, r9
0x18001318b  mov     r12, r8
0x18001318e  mov     r14, rdx
0x180013191  mov     r15, [rbp+hEvent]
0x180013195  xor     ebx, ebx
0x180013197  test    rdx, rdx
0x18001319a  jz      loc_18001336C
0x1800131a0  cmp     [rdx], bx
0x1800131a3  jz      loc_18001336C
0x1800131a9  lea     r8d, [rbx+10h]; Size
0x1800131ad  lea     rdx, GUID_NULL; Buf2
0x1800131b4  mov     rcx, r12; Buf1
0x1800131b7  call    memcmp
0x1800131bc  test    eax, eax
0x1800131be  jnz     short loc_1800131C8
0x1800131c0  lea     edx, [rbx+4Ah]
0x1800131c3  jmp     loc_180013371
0x1800131c8  test    r15, r15
0x1800131cb  jnz     short loc_1800131D6
0x1800131cd  lea     edx, [r15+4Bh]
0x1800131d1  jmp     loc_180013371
0x1800131d6  mov     rsi, [rbp+arg_28]
0x1800131da  test    rsi, rsi
0x1800131dd  jnz     short loc_1800131E7
0x1800131df  lea     edx, [rsi+4Ch]
0x1800131e2  jmp     loc_180013371
0x1800131e7  mov     [rbp+var_40], ebx
0x1800131ea  mov     [rbp+var_38], rbx
0x1800131ee  xorps   xmm0, xmm0
0x1800131f1  movups  xmmword ptr [rbp+Handles], xmm0
0x1800131f5  mov     edi, 1
0x1800131fa  mov     r8b, dil; bool
0x1800131fd  lea     rcx, [rbp+var_40]; this
0x180013201  call    ?Initialize@CCoInit@@QEAAJK_N@Z; CCoInit::Initialize(ulong,bool)
0x180013206  mov     ebx, eax
0x180013208  test    eax, eax
0x18001320a  jns     short loc_180013217
0x18001320c  lea     edx, [rdi+51h]
0x18001320f  xor     r12d, r12d
0x180013212  jmp     loc_180013330
0x180013217  movups  xmm0, xmmword ptr [r12]
0x18001321c  movdqu  xmmword ptr [rbp+var_30.Data1], xmm0
0x180013221  lea     r8, [rbp+var_38]; struct CUpdateDeploymentSession **
0x180013225  lea     rdx, [rbp+var_30]; struct _GUID
0x180013229  mov     rcx, r14; wchar_t *
0x18001322c  call    ?CreateInstance@CUpdateDeploymentSession@@SAJPEB_WU_GUID@@PEAPEAV1@@Z; CUpdateDeploymentSession::CreateInstance(wchar_t const *,_GUID,CUpdateDeploymentSession * *)
0x180013231  mov     ebx, eax
0x180013233  xor     r12d, r12d
0x180013236  test    eax, eax
0x180013238  jns     short loc_180013244
0x18001323a  lea     edx, [r12+56h]
0x18001323f  jmp     loc_180013330
0x180013244  mov     rcx, r15; hEvent
0x180013247  call    cs:__imp_SetEvent
0x18001324d  test    eax, eax
0x18001324f  jnz     short loc_180013256
0x180013251  lea     edx, [rax+58h]
0x180013254  jmp     short loc_180013296
0x180013256  mov     [rbp+Handles], rsi
0x18001325a  mov     [rbp+Handles+8], r13
0x18001325e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180013262  xor     r8d, r8d; bWaitAll
0x180013265  lea     rdx, [rbp+Handles]; lpHandles
0x180013269  lea     ecx, [r8+2]; nCount
0x18001326d  call    cs:__imp_WaitForMultipleObjects
0x180013273  cmp     eax, 102h
0x180013278  jnz     short loc_180013289
0x18001327a  mov     ebx, 80070102h
0x18001327f  mov     edx, 5Fh ; '_'
0x180013284  jmp     loc_180013330
0x180013289  test    eax, eax
0x18001328b  jz      short loc_1800132BF
0x18001328d  cmp     eax, edi
0x18001328f  jz      short loc_1800132AD
0x180013291  mov     edx, 60h ; '`'; void *
0x180013296  lea     r8, aCW1SSrcClientU_13; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001329d  mov     rcx, [rbp+38h]; this
0x1800132a1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800132a6  mov     ebx, eax
0x1800132a8  jmp     loc_180013348
0x1800132ad  mov     rsi, r12
0x1800132b0  mov     r14, r12
0x1800132b3  mov     r15, r12
0x1800132b6  lea     r12, aDeploymentSess; "Deployment session (host process %d) pa"...
0x1800132bd  jmp     short loc_1800132CF
0x1800132bf  mov     rsi, r12
0x1800132c2  mov     r14, r12
0x1800132c5  mov     r15, r12
0x1800132c8  lea     r12, aDeploymentSess_0; "Deployment session (host process %d) si"...
0x1800132cf  mov     ebx, 4
0x1800132d4  call    cs:__imp_GetCurrentProcessId
0x1800132da  mov     [rsp+80h+var_50], eax
0x1800132de  mov     [rsp+80h+var_58], r12
0x1800132e3  mov     qword ptr [rsp+80h+var_60], r15; int
0x1800132e8  mov     r9d, ebx
0x1800132eb  mov     r8d, edi
0x1800132ee  mov     rdx, r14
0x1800132f1  mov     rcx, rsi
0x1800132f4  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800132f9  xor     r12d, r12d
0x1800132fc  mov     rcx, [rbp+var_38]; this
0x180013300  call    ?UnregisterClassFactory@CWuaClassFactoryBase@@QEAAJK@Z; CWuaClassFactoryBase::UnregisterClassFactory(ulong)
0x180013305  mov     ebx, eax
0x180013307  test    eax, eax
0x180013309  jns     short loc_180013345
0x18001330b  mov     rcx, [rbp+38h]; this
0x18001330f  mov     r9d, eax; char *
0x180013312  lea     r8, aCW1SSrcClientU_7; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180013319  mov     edx, 25h ; '%'; void *
0x18001331e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013323  cmp     ebx, 8001011Fh
0x180013329  jz      short loc_1800132FC
0x18001332b  mov     edx, 79h ; 'y'; void *
0x180013330  mov     rcx, [rbp+38h]; this
0x180013334  mov     r9d, ebx; char *
0x180013337  lea     r8, aCW1SSrcClientU_13; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001333e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013343  jmp     short loc_180013348
0x180013345  mov     ebx, r12d
0x180013348  mov     rcx, [rbp+var_38]
0x18001334c  test    rcx, rcx
0x18001334f  jz      short loc_18001335E
0x180013351  mov     rdx, [rcx]
0x180013354  mov     rax, [rdx+10h]
0x180013358  call    _guard_dispatch_icall
0x18001335d  nop
0x18001335e  cmp     [rbp+var_40], r12d
0x180013362  jz      short loc_180013389
0x180013364  call    cs:__imp_CoUninitialize
0x18001336a  jmp     short loc_180013389
0x18001336c  mov     edx, 49h ; 'I'; void *
0x180013371  mov     ebx, 80070057h
0x180013376  mov     r9d, ebx; char *
0x180013379  lea     r8, aCW1SSrcClientU_13; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180013380  mov     rcx, [rbp+38h]; this
0x180013384  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013389  mov     eax, ebx
0x18001338b  mov     rcx, [rbp+var_10]
0x18001338f  xor     rcx, rsp; StackCookie
0x180013392  call    __security_check_cookie
0x180013397  mov     rbx, [rsp+80h+arg_0]
0x18001339f  add     rsp, 80h
0x1800133a6  pop     r15
0x1800133a8  pop     r14
0x1800133aa  pop     r13
0x1800133ac  pop     r12
0x1800133ae  pop     rdi
0x1800133af  pop     rsi
0x1800133b0  pop     rbp
0x1800133b1  retn
```
