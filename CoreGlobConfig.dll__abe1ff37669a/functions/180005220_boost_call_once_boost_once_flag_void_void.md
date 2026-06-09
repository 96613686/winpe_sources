# boost::call_once(boost::once_flag &,void (*)(void))

- ea: `0x180005220`
- end: `0x18000543b`
- name: `?call_once@boost@@YAXAEAUonce_flag@1@P6AXXZ@Z`
- size: `539`
- prototype: `void __fastcall(struct boost::once_flag *, void (*)(void))`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800059e0`

## callees

- `0x180002380`
- `0x180005220`
- `0x180005770`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005372`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005372`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800052e4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800052e4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000542f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000542f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180005340`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800053fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180005340`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800053fa`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x1800052b9`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x1800052b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005358`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000538a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005412`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005358`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000538a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005412`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall boost::call_once(struct boost::once_flag *a1, void (*a2)(void), void *a3)
{
  HANDLE v5; // rdi
  struct boost::detail::once_context *v6; // r8
  char *v7; // rdi
  HANDLE v8; // rcx
  HANDLE EventA; // rdi
  __int32 v11; // [rsp+30h] [rbp-88h] BYREF
  signed __int32 v12; // [rsp+34h] [rbp-84h]
  char v13; // [rsp+38h] [rbp-80h]
  HANDLE hObject; // [rsp+40h] [rbp-78h]
  CHAR Name[88]; // [rsp+48h] [rbp-70h] BYREF

  v11 = -1051250462;
  v12 = 2131174883;
  v13 = 0;
  hObject = 0;
  Name[0] = 0;
  while ( 1 )
  {
    if ( *(_DWORD *)a1 == v11 )
      goto LABEL_23;
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)a1, v12, 0) )
      break;
    if ( v13 )
    {
      v8 = hObject;
      goto LABEL_36;
    }
    _InterlockedIncrement((volatile signed __int32 *)a1 + 1);
    v13 = 1;
    if ( *(_DWORD *)a1 == v11 )
      goto LABEL_23;
    v8 = hObject;
    if ( hObject )
    {
LABEL_36:
      WaitForSingleObjectEx(v8, 0xFFFFFFFF, 0);
    }
    else
    {
      if ( !Name[0] )
        boost::detail::name_once_mutex((boost::detail *)Name, (char *)a1, a3);
      EventA = CreateEventA(0, 1, 0, Name);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      hObject = EventA;
    }
  }
  v5 = hObject;
  if ( hObject )
    goto LABEL_10;
  if ( !Name[0] )
    boost::detail::name_once_mutex((boost::detail *)Name, (char *)a1, a3);
  v5 = OpenEventA(0x100002u, 0, Name);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  hObject = v5;
  if ( v5 )
LABEL_10:
    ResetEvent(v5);
  try
  {
    a2();
    if ( !v13 )
    {
      _InterlockedIncrement((volatile signed __int32 *)a1 + 1);
      v13 = 1;
    }
  }
  catch ( ... )
  {
    boost::detail::rollback_once_region(a1, (struct boost::once_flag *)&v11, v6);
    throw;
  }
  _InterlockedExchange((volatile __int32 *)a1, v11);
  v7 = (char *)hObject;
  if ( hObject )
    goto LABEL_22;
  if ( *((int *)a1 + 1) <= 1 )
  {
    v7 = (char *)hObject;
  }
  else
  {
    if ( Name[0] == (_BYTE)hObject )
      boost::detail::name_once_mutex((boost::detail *)Name, (char *)a1, v6);
    v7 = (char *)CreateEventA(0, 1, 0, Name);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    hObject = v7;
  }
  if ( v7 )
  {
LABEL_22:
    SetEvent(v7);
LABEL_23:
    v7 = (char *)hObject;
  }
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
}

```

## disassembly

```asm
0x180005220  mov     [rsp+arg_10], rbx
0x180005225  mov     [rsp+arg_18], rsi
0x18000522a  push    rdi
0x18000522b  sub     rsp, 0B0h
0x180005232  mov     rax, cs:__security_cookie
0x180005239  xor     rax, rsp
0x18000523c  mov     [rsp+0B8h+var_18], rax
0x180005244  mov     rsi, rdx
0x180005247  mov     rbx, rcx
0x18000524a  mov     [rsp+0B8h+var_90], rcx
0x18000524f  mov     [rsp+0B8h+var_88], 0C15730E2h
0x180005257  mov     [rsp+0B8h+var_84], 7F0725E3h
0x18000525f  mov     [rsp+0B8h+var_80], 0
0x180005264  mov     [rsp+0B8h+hObject], 0
0x18000526d  mov     [rsp+0B8h+Name], 0
0x180005272  mov     eax, [rbx]
0x180005274  nop
0x180005275  cmp     eax, [rsp+0B8h+var_88]
0x180005279  jz      loc_180005378
0x18000527f  mov     ecx, [rsp+0B8h+var_84]
0x180005283  xor     eax, eax
0x180005285  lock cmpxchg [rbx], ecx
0x180005289  jnz     loc_1800053B5
0x18000528f  mov     rdi, [rsp+0B8h+hObject]
0x180005294  test    rdi, rdi
0x180005297  jnz     short loc_1800052E1
0x180005299  cmp     [rsp+0B8h+Name], dil
0x18000529e  jnz     short loc_1800052AD
0x1800052a0  mov     rdx, rbx; char *
0x1800052a3  lea     rcx, [rsp+0B8h+Name]; this
0x1800052a8  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x1800052ad  lea     r8, [rsp+0B8h+Name]; lpName
0x1800052b2  xor     edx, edx; bInheritHandle
0x1800052b4  mov     ecx, 100002h; dwDesiredAccess
0x1800052b9  call    cs:__imp_OpenEventA
0x1800052bf  mov     rdi, rax
0x1800052c2  mov     rcx, [rsp+0B8h+hObject]; hObject
0x1800052c7  lea     rax, [rcx-1]
0x1800052cb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800052cf  ja      short loc_1800052D7
0x1800052d1  call    cs:__imp_CloseHandle
0x1800052d7  mov     [rsp+0B8h+hObject], rdi
0x1800052dc  test    rdi, rdi
0x1800052df  jz      short loc_1800052EB
0x1800052e1  mov     rcx, rdi; hEvent
0x1800052e4  call    cs:__imp_ResetEvent
0x1800052ea  nop
0x1800052eb  mov     rax, rsi
0x1800052ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052f3  nop
0x1800052f4  cmp     [rsp+0B8h+var_80], 0
0x1800052f9  jnz     short loc_180005304
0x1800052fb  lock inc dword ptr [rbx+4]
0x1800052ff  mov     [rsp+0B8h+var_80], 1
0x180005304  mov     eax, [rsp+0B8h+var_88]
0x180005308  xchg    eax, [rbx]
0x18000530a  mov     rdi, [rsp+0B8h+hObject]
0x18000530f  test    rdi, rdi
0x180005312  jnz     short loc_18000536F
0x180005314  mov     eax, [rbx+4]
0x180005317  nop
0x180005318  cmp     eax, 1
0x18000531b  jle     short loc_180005365
0x18000531d  cmp     [rsp+0B8h+Name], dil
0x180005322  jnz     short loc_180005331
0x180005324  mov     rdx, rbx; char *
0x180005327  lea     rcx, [rsp+0B8h+Name]; this
0x18000532c  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x180005331  lea     r9, [rsp+0B8h+Name]; lpName
0x180005336  xor     r8d, r8d; bInitialState
0x180005339  mov     edx, 1; bManualReset
0x18000533e  xor     ecx, ecx; lpEventAttributes
0x180005340  call    cs:__imp_CreateEventA
0x180005346  mov     rdi, rax
0x180005349  mov     rcx, [rsp+0B8h+hObject]; hObject
0x18000534e  lea     rax, [rcx-1]
0x180005352  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005356  ja      short loc_18000535E
0x180005358  call    cs:__imp_CloseHandle
0x18000535e  mov     [rsp+0B8h+hObject], rdi
0x180005363  jmp     short loc_18000536A
0x180005365  mov     rdi, [rsp+0B8h+hObject]
0x18000536a  test    rdi, rdi
0x18000536d  jz      short loc_18000537D
0x18000536f  mov     rcx, rdi; hEvent
0x180005372  call    cs:__imp_SetEvent
0x180005378  mov     rdi, [rsp+0B8h+hObject]
0x18000537d  lea     rax, [rdi-1]
0x180005381  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005385  ja      short loc_180005390
0x180005387  mov     rcx, rdi; hObject
0x18000538a  call    cs:__imp_CloseHandle
0x180005390  mov     rcx, [rsp+0B8h+var_18]
0x180005398  xor     rcx, rsp; StackCookie
0x18000539b  call    __security_check_cookie
0x1800053a0  lea     r11, [rsp+0B8h+var_8]
0x1800053a8  mov     rbx, [r11+20h]
0x1800053ac  mov     rsi, [r11+28h]
0x1800053b0  mov     rsp, r11
0x1800053b3  pop     rdi
0x1800053b4  retn
0x1800053b5  cmp     [rsp+0B8h+var_80], 0
0x1800053ba  jnz     short loc_180005422
0x1800053bc  lock inc dword ptr [rbx+4]
0x1800053c0  mov     [rsp+0B8h+var_80], 1
0x1800053c5  mov     eax, [rbx]
0x1800053c7  nop
0x1800053c8  cmp     eax, [rsp+0B8h+var_88]
0x1800053cc  jz      short loc_180005378
0x1800053ce  mov     rcx, [rsp+0B8h+hObject]
0x1800053d3  test    rcx, rcx
0x1800053d6  jnz     short loc_180005427
0x1800053d8  cmp     [rsp+0B8h+Name], cl
0x1800053dc  jnz     short loc_1800053EB
0x1800053de  mov     rdx, rbx; char *
0x1800053e1  lea     rcx, [rsp+0B8h+Name]; this
0x1800053e6  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x1800053eb  lea     r9, [rsp+0B8h+Name]; lpName
0x1800053f0  xor     r8d, r8d; bInitialState
0x1800053f3  mov     edx, 1; bManualReset
0x1800053f8  xor     ecx, ecx; lpEventAttributes
0x1800053fa  call    cs:__imp_CreateEventA
0x180005400  mov     rdi, rax
0x180005403  mov     rcx, [rsp+0B8h+hObject]; hObject
0x180005408  lea     rdx, [rcx-1]
0x18000540c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180005410  ja      short loc_180005418
0x180005412  call    cs:__imp_CloseHandle
0x180005418  mov     [rsp+0B8h+hObject], rdi
0x18000541d  jmp     loc_180005272
0x180005422  mov     rcx, [rsp+0B8h+hObject]; hHandle
0x180005427  xor     r8d, r8d; bAlertable
0x18000542a  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000542f  call    cs:__imp_WaitForSingleObjectEx
0x180005435  jmp     loc_180005272
```
