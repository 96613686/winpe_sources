# boost::call_once(boost::once_flag &,void (*)(void))

- ea: `0x14000a1b0`
- end: `0x14000a3cb`
- name: `?call_once@boost@@YAXAEAUonce_flag@1@P6AXXZ@Z`
- size: `539`
- prototype: `void __fastcall(struct boost::once_flag *, void (*)(void))`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000a5b0`

## callees

- `0x140003e50`
- `0x14000a1b0`
- `0x14000a400`
- `0x14009b010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000a261`
- `KERNEL32!CloseHandle` at `0x14000a2e8`
- `KERNEL32!CloseHandle` at `0x14000a31a`
- `KERNEL32!CloseHandle` at `0x14000a3a2`
- `KERNEL32!CloseHandle` at `0x14000a261`
- `KERNEL32!CloseHandle` at `0x14000a2e8`
- `KERNEL32!CloseHandle` at `0x14000a31a`
- `KERNEL32!CloseHandle` at `0x14000a3a2`
- `KERNEL32!OpenEventA` at `0x14000a249`
- `KERNEL32!OpenEventA` at `0x14000a249`
- `KERNEL32!ResetEvent` at `0x14000a274`
- `KERNEL32!ResetEvent` at `0x14000a274`
- `KERNEL32!CreateEventA` at `0x14000a2d0`
- `KERNEL32!CreateEventA` at `0x14000a38a`
- `KERNEL32!CreateEventA` at `0x14000a2d0`
- `KERNEL32!CreateEventA` at `0x14000a38a`
- `KERNEL32!SetEvent` at `0x14000a302`
- `KERNEL32!SetEvent` at `0x14000a302`
- `KERNEL32!WaitForSingleObjectEx` at `0x14000a3bf`
- `KERNEL32!WaitForSingleObjectEx` at `0x14000a3bf`

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
0x14000a1b0  mov     [rsp+arg_10], rbx
0x14000a1b5  mov     [rsp+arg_18], rsi
0x14000a1ba  push    rdi
0x14000a1bb  sub     rsp, 0B0h
0x14000a1c2  mov     rax, cs:__security_cookie
0x14000a1c9  xor     rax, rsp
0x14000a1cc  mov     [rsp+0B8h+var_18], rax
0x14000a1d4  mov     rsi, rdx
0x14000a1d7  mov     rbx, rcx
0x14000a1da  mov     [rsp+0B8h+var_90], rcx
0x14000a1df  mov     [rsp+0B8h+var_88], 0C15730E2h
0x14000a1e7  mov     [rsp+0B8h+var_84], 7F0725E3h
0x14000a1ef  mov     [rsp+0B8h+var_80], 0
0x14000a1f4  mov     [rsp+0B8h+hObject], 0
0x14000a1fd  mov     [rsp+0B8h+Name], 0
0x14000a202  mov     eax, [rbx]
0x14000a204  nop
0x14000a205  cmp     eax, [rsp+0B8h+var_88]
0x14000a209  jz      loc_14000A308
0x14000a20f  mov     ecx, [rsp+0B8h+var_84]
0x14000a213  xor     eax, eax
0x14000a215  lock cmpxchg [rbx], ecx
0x14000a219  jnz     loc_14000A345
0x14000a21f  mov     rdi, [rsp+0B8h+hObject]
0x14000a224  test    rdi, rdi
0x14000a227  jnz     short loc_14000A271
0x14000a229  cmp     [rsp+0B8h+Name], dil
0x14000a22e  jnz     short loc_14000A23D
0x14000a230  mov     rdx, rbx; char *
0x14000a233  lea     rcx, [rsp+0B8h+Name]; this
0x14000a238  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x14000a23d  lea     r8, [rsp+0B8h+Name]; lpName
0x14000a242  xor     edx, edx; bInheritHandle
0x14000a244  mov     ecx, 100002h; dwDesiredAccess
0x14000a249  call    cs:__imp_OpenEventA
0x14000a24f  mov     rdi, rax
0x14000a252  mov     rcx, [rsp+0B8h+hObject]; hObject
0x14000a257  lea     rax, [rcx-1]
0x14000a25b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000a25f  ja      short loc_14000A267
0x14000a261  call    cs:__imp_CloseHandle
0x14000a267  mov     [rsp+0B8h+hObject], rdi
0x14000a26c  test    rdi, rdi
0x14000a26f  jz      short loc_14000A27B
0x14000a271  mov     rcx, rdi; hEvent
0x14000a274  call    cs:__imp_ResetEvent
0x14000a27a  nop
0x14000a27b  mov     rax, rsi
0x14000a27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a283  nop
0x14000a284  cmp     [rsp+0B8h+var_80], 0
0x14000a289  jnz     short loc_14000A294
0x14000a28b  lock inc dword ptr [rbx+4]
0x14000a28f  mov     [rsp+0B8h+var_80], 1
0x14000a294  mov     eax, [rsp+0B8h+var_88]
0x14000a298  xchg    eax, [rbx]
0x14000a29a  mov     rdi, [rsp+0B8h+hObject]
0x14000a29f  test    rdi, rdi
0x14000a2a2  jnz     short loc_14000A2FF
0x14000a2a4  mov     eax, [rbx+4]
0x14000a2a7  nop
0x14000a2a8  cmp     eax, 1
0x14000a2ab  jle     short loc_14000A2F5
0x14000a2ad  cmp     [rsp+0B8h+Name], dil
0x14000a2b2  jnz     short loc_14000A2C1
0x14000a2b4  mov     rdx, rbx; char *
0x14000a2b7  lea     rcx, [rsp+0B8h+Name]; this
0x14000a2bc  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x14000a2c1  lea     r9, [rsp+0B8h+Name]; lpName
0x14000a2c6  xor     r8d, r8d; bInitialState
0x14000a2c9  mov     edx, 1; bManualReset
0x14000a2ce  xor     ecx, ecx; lpEventAttributes
0x14000a2d0  call    cs:__imp_CreateEventA
0x14000a2d6  mov     rdi, rax
0x14000a2d9  mov     rcx, [rsp+0B8h+hObject]; hObject
0x14000a2de  lea     rax, [rcx-1]
0x14000a2e2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000a2e6  ja      short loc_14000A2EE
0x14000a2e8  call    cs:__imp_CloseHandle
0x14000a2ee  mov     [rsp+0B8h+hObject], rdi
0x14000a2f3  jmp     short loc_14000A2FA
0x14000a2f5  mov     rdi, [rsp+0B8h+hObject]
0x14000a2fa  test    rdi, rdi
0x14000a2fd  jz      short loc_14000A30D
0x14000a2ff  mov     rcx, rdi; hEvent
0x14000a302  call    cs:__imp_SetEvent
0x14000a308  mov     rdi, [rsp+0B8h+hObject]
0x14000a30d  lea     rax, [rdi-1]
0x14000a311  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000a315  ja      short loc_14000A320
0x14000a317  mov     rcx, rdi; hObject
0x14000a31a  call    cs:__imp_CloseHandle
0x14000a320  mov     rcx, [rsp+0B8h+var_18]
0x14000a328  xor     rcx, rsp; StackCookie
0x14000a32b  call    __security_check_cookie
0x14000a330  lea     r11, [rsp+0B8h+var_8]
0x14000a338  mov     rbx, [r11+20h]
0x14000a33c  mov     rsi, [r11+28h]
0x14000a340  mov     rsp, r11
0x14000a343  pop     rdi
0x14000a344  retn
0x14000a345  cmp     [rsp+0B8h+var_80], 0
0x14000a34a  jnz     short loc_14000A3B2
0x14000a34c  lock inc dword ptr [rbx+4]
0x14000a350  mov     [rsp+0B8h+var_80], 1
0x14000a355  mov     eax, [rbx]
0x14000a357  nop
0x14000a358  cmp     eax, [rsp+0B8h+var_88]
0x14000a35c  jz      short loc_14000A308
0x14000a35e  mov     rcx, [rsp+0B8h+hObject]
0x14000a363  test    rcx, rcx
0x14000a366  jnz     short loc_14000A3B7
0x14000a368  cmp     [rsp+0B8h+Name], cl
0x14000a36c  jnz     short loc_14000A37B
0x14000a36e  mov     rdx, rbx; char *
0x14000a371  lea     rcx, [rsp+0B8h+Name]; this
0x14000a376  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x14000a37b  lea     r9, [rsp+0B8h+Name]; lpName
0x14000a380  xor     r8d, r8d; bInitialState
0x14000a383  mov     edx, 1; bManualReset
0x14000a388  xor     ecx, ecx; lpEventAttributes
0x14000a38a  call    cs:__imp_CreateEventA
0x14000a390  mov     rdi, rax
0x14000a393  mov     rcx, [rsp+0B8h+hObject]; hObject
0x14000a398  lea     rdx, [rcx-1]
0x14000a39c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14000a3a0  ja      short loc_14000A3A8
0x14000a3a2  call    cs:__imp_CloseHandle
0x14000a3a8  mov     [rsp+0B8h+hObject], rdi
0x14000a3ad  jmp     loc_14000A202
0x14000a3b2  mov     rcx, [rsp+0B8h+hObject]; hHandle
0x14000a3b7  xor     r8d, r8d; bAlertable
0x14000a3ba  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x14000a3bf  call    cs:__imp_WaitForSingleObjectEx
0x14000a3c5  jmp     loc_14000A202
```
