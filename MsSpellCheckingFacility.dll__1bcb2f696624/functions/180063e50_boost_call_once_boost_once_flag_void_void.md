# boost::call_once(boost::once_flag &,void (*)(void))

- ea: `0x180063e50`
- end: `0x18006406b`
- name: `?call_once@boost@@YAXAEAUonce_flag@1@P6AXXZ@Z`
- size: `539`
- prototype: `void __fastcall(struct boost::once_flag *, void (*)(void))`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180064610`

## callees

- `0x180061320`
- `0x180063e50`
- `0x1800643a0`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063f88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063fba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064042`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063f88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063fba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064042`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180063fa2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180063fa2`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x180063ee9`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x180063ee9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180063f14`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180063f14`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18006405f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18006405f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180063f70`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18006402a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180063f70`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18006402a`

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
0x180063e50  mov     [rsp+arg_10], rbx
0x180063e55  mov     [rsp+arg_18], rsi
0x180063e5a  push    rdi
0x180063e5b  sub     rsp, 0B0h
0x180063e62  mov     rax, cs:__security_cookie
0x180063e69  xor     rax, rsp
0x180063e6c  mov     [rsp+0B8h+var_18], rax
0x180063e74  mov     rsi, rdx
0x180063e77  mov     rbx, rcx
0x180063e7a  mov     [rsp+0B8h+var_90], rcx
0x180063e7f  mov     [rsp+0B8h+var_88], 0C15730E2h
0x180063e87  mov     [rsp+0B8h+var_84], 7F0725E3h
0x180063e8f  mov     [rsp+0B8h+var_80], 0
0x180063e94  mov     [rsp+0B8h+hObject], 0
0x180063e9d  mov     [rsp+0B8h+Name], 0
0x180063ea2  mov     eax, [rbx]
0x180063ea4  nop
0x180063ea5  cmp     eax, [rsp+0B8h+var_88]
0x180063ea9  jz      loc_180063FA8
0x180063eaf  mov     ecx, [rsp+0B8h+var_84]
0x180063eb3  xor     eax, eax
0x180063eb5  lock cmpxchg [rbx], ecx
0x180063eb9  jnz     loc_180063FE5
0x180063ebf  mov     rdi, [rsp+0B8h+hObject]
0x180063ec4  test    rdi, rdi
0x180063ec7  jnz     short loc_180063F11
0x180063ec9  cmp     [rsp+0B8h+Name], dil
0x180063ece  jnz     short loc_180063EDD
0x180063ed0  mov     rdx, rbx; char *
0x180063ed3  lea     rcx, [rsp+0B8h+Name]; this
0x180063ed8  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x180063edd  lea     r8, [rsp+0B8h+Name]; lpName
0x180063ee2  xor     edx, edx; bInheritHandle
0x180063ee4  mov     ecx, 100002h; dwDesiredAccess
0x180063ee9  call    cs:__imp_OpenEventA
0x180063eef  mov     rdi, rax
0x180063ef2  mov     rcx, [rsp+0B8h+hObject]; hObject
0x180063ef7  lea     rax, [rcx-1]
0x180063efb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180063eff  ja      short loc_180063F07
0x180063f01  call    cs:__imp_CloseHandle
0x180063f07  mov     [rsp+0B8h+hObject], rdi
0x180063f0c  test    rdi, rdi
0x180063f0f  jz      short loc_180063F1B
0x180063f11  mov     rcx, rdi; hEvent
0x180063f14  call    cs:__imp_ResetEvent
0x180063f1a  nop
0x180063f1b  mov     rax, rsi
0x180063f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f23  nop
0x180063f24  cmp     [rsp+0B8h+var_80], 0
0x180063f29  jnz     short loc_180063F34
0x180063f2b  lock inc dword ptr [rbx+4]
0x180063f2f  mov     [rsp+0B8h+var_80], 1
0x180063f34  mov     eax, [rsp+0B8h+var_88]
0x180063f38  xchg    eax, [rbx]
0x180063f3a  mov     rdi, [rsp+0B8h+hObject]
0x180063f3f  test    rdi, rdi
0x180063f42  jnz     short loc_180063F9F
0x180063f44  mov     eax, [rbx+4]
0x180063f47  nop
0x180063f48  cmp     eax, 1
0x180063f4b  jle     short loc_180063F95
0x180063f4d  cmp     [rsp+0B8h+Name], dil
0x180063f52  jnz     short loc_180063F61
0x180063f54  mov     rdx, rbx; char *
0x180063f57  lea     rcx, [rsp+0B8h+Name]; this
0x180063f5c  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x180063f61  lea     r9, [rsp+0B8h+Name]; lpName
0x180063f66  xor     r8d, r8d; bInitialState
0x180063f69  mov     edx, 1; bManualReset
0x180063f6e  xor     ecx, ecx; lpEventAttributes
0x180063f70  call    cs:__imp_CreateEventA
0x180063f76  mov     rdi, rax
0x180063f79  mov     rcx, [rsp+0B8h+hObject]; hObject
0x180063f7e  lea     rax, [rcx-1]
0x180063f82  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180063f86  ja      short loc_180063F8E
0x180063f88  call    cs:__imp_CloseHandle
0x180063f8e  mov     [rsp+0B8h+hObject], rdi
0x180063f93  jmp     short loc_180063F9A
0x180063f95  mov     rdi, [rsp+0B8h+hObject]
0x180063f9a  test    rdi, rdi
0x180063f9d  jz      short loc_180063FAD
0x180063f9f  mov     rcx, rdi; hEvent
0x180063fa2  call    cs:__imp_SetEvent
0x180063fa8  mov     rdi, [rsp+0B8h+hObject]
0x180063fad  lea     rax, [rdi-1]
0x180063fb1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180063fb5  ja      short loc_180063FC0
0x180063fb7  mov     rcx, rdi; hObject
0x180063fba  call    cs:__imp_CloseHandle
0x180063fc0  mov     rcx, [rsp+0B8h+var_18]
0x180063fc8  xor     rcx, rsp; StackCookie
0x180063fcb  call    __security_check_cookie
0x180063fd0  lea     r11, [rsp+0B8h+var_8]
0x180063fd8  mov     rbx, [r11+20h]
0x180063fdc  mov     rsi, [r11+28h]
0x180063fe0  mov     rsp, r11
0x180063fe3  pop     rdi
0x180063fe4  retn
0x180063fe5  cmp     [rsp+0B8h+var_80], 0
0x180063fea  jnz     short loc_180064052
0x180063fec  lock inc dword ptr [rbx+4]
0x180063ff0  mov     [rsp+0B8h+var_80], 1
0x180063ff5  mov     eax, [rbx]
0x180063ff7  nop
0x180063ff8  cmp     eax, [rsp+0B8h+var_88]
0x180063ffc  jz      short loc_180063FA8
0x180063ffe  mov     rcx, [rsp+0B8h+hObject]
0x180064003  test    rcx, rcx
0x180064006  jnz     short loc_180064057
0x180064008  cmp     [rsp+0B8h+Name], cl
0x18006400c  jnz     short loc_18006401B
0x18006400e  mov     rdx, rbx; char *
0x180064011  lea     rcx, [rsp+0B8h+Name]; this
0x180064016  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x18006401b  lea     r9, [rsp+0B8h+Name]; lpName
0x180064020  xor     r8d, r8d; bInitialState
0x180064023  mov     edx, 1; bManualReset
0x180064028  xor     ecx, ecx; lpEventAttributes
0x18006402a  call    cs:__imp_CreateEventA
0x180064030  mov     rdi, rax
0x180064033  mov     rcx, [rsp+0B8h+hObject]; hObject
0x180064038  lea     rdx, [rcx-1]
0x18006403c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180064040  ja      short loc_180064048
0x180064042  call    cs:__imp_CloseHandle
0x180064048  mov     [rsp+0B8h+hObject], rdi
0x18006404d  jmp     loc_180063EA2
0x180064052  mov     rcx, [rsp+0B8h+hObject]; hHandle
0x180064057  xor     r8d, r8d; bAlertable
0x18006405a  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18006405f  call    cs:__imp_WaitForSingleObjectEx
0x180064065  jmp     loc_180063EA2
```
