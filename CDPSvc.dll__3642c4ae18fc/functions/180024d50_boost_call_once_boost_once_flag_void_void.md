# boost::call_once(boost::once_flag &,void (*)(void))

- ea: `0x180024d50`
- end: `0x180024f6b`
- name: `?call_once@boost@@YAXAEAUonce_flag@1@P6AXXZ@Z`
- size: `539`
- prototype: `void __fastcall(struct boost::once_flag *, void (*)(void))`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180025510`

## callees

- `0x1800225a0`
- `0x180024d50`
- `0x1800252a0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180024ea2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180024ea2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180024e70`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180024f2a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180024e70`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180024f2a`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x180024de9`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x180024de9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180024e14`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180024e14`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180024f5f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180024f5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024e01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024e88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024eba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024f42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024e01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024e88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024eba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024f42`

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
0x180024d50  mov     [rsp+arg_10], rbx
0x180024d55  mov     [rsp+arg_18], rsi
0x180024d5a  push    rdi
0x180024d5b  sub     rsp, 0B0h
0x180024d62  mov     rax, cs:__security_cookie
0x180024d69  xor     rax, rsp
0x180024d6c  mov     [rsp+0B8h+var_18], rax
0x180024d74  mov     rsi, rdx
0x180024d77  mov     rbx, rcx
0x180024d7a  mov     [rsp+0B8h+var_90], rcx
0x180024d7f  mov     [rsp+0B8h+var_88], 0C15730E2h
0x180024d87  mov     [rsp+0B8h+var_84], 7F0725E3h
0x180024d8f  mov     [rsp+0B8h+var_80], 0
0x180024d94  mov     [rsp+0B8h+hObject], 0
0x180024d9d  mov     [rsp+0B8h+Name], 0
0x180024da2  mov     eax, [rbx]
0x180024da4  nop
0x180024da5  cmp     eax, [rsp+0B8h+var_88]
0x180024da9  jz      loc_180024EA8
0x180024daf  mov     ecx, [rsp+0B8h+var_84]
0x180024db3  xor     eax, eax
0x180024db5  lock cmpxchg [rbx], ecx
0x180024db9  jnz     loc_180024EE5
0x180024dbf  mov     rdi, [rsp+0B8h+hObject]
0x180024dc4  test    rdi, rdi
0x180024dc7  jnz     short loc_180024E11
0x180024dc9  cmp     [rsp+0B8h+Name], dil
0x180024dce  jnz     short loc_180024DDD
0x180024dd0  mov     rdx, rbx; char *
0x180024dd3  lea     rcx, [rsp+0B8h+Name]; this
0x180024dd8  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x180024ddd  lea     r8, [rsp+0B8h+Name]; lpName
0x180024de2  xor     edx, edx; bInheritHandle
0x180024de4  mov     ecx, 100002h; dwDesiredAccess
0x180024de9  call    cs:__imp_OpenEventA
0x180024def  mov     rdi, rax
0x180024df2  mov     rcx, [rsp+0B8h+hObject]; hObject
0x180024df7  lea     rax, [rcx-1]
0x180024dfb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024dff  ja      short loc_180024E07
0x180024e01  call    cs:__imp_CloseHandle
0x180024e07  mov     [rsp+0B8h+hObject], rdi
0x180024e0c  test    rdi, rdi
0x180024e0f  jz      short loc_180024E1B
0x180024e11  mov     rcx, rdi; hEvent
0x180024e14  call    cs:__imp_ResetEvent
0x180024e1a  nop
0x180024e1b  mov     rax, rsi
0x180024e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e23  nop
0x180024e24  cmp     [rsp+0B8h+var_80], 0
0x180024e29  jnz     short loc_180024E34
0x180024e2b  lock inc dword ptr [rbx+4]
0x180024e2f  mov     [rsp+0B8h+var_80], 1
0x180024e34  mov     eax, [rsp+0B8h+var_88]
0x180024e38  xchg    eax, [rbx]
0x180024e3a  mov     rdi, [rsp+0B8h+hObject]
0x180024e3f  test    rdi, rdi
0x180024e42  jnz     short loc_180024E9F
0x180024e44  mov     eax, [rbx+4]
0x180024e47  nop
0x180024e48  cmp     eax, 1
0x180024e4b  jle     short loc_180024E95
0x180024e4d  cmp     [rsp+0B8h+Name], dil
0x180024e52  jnz     short loc_180024E61
0x180024e54  mov     rdx, rbx; char *
0x180024e57  lea     rcx, [rsp+0B8h+Name]; this
0x180024e5c  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x180024e61  lea     r9, [rsp+0B8h+Name]; lpName
0x180024e66  xor     r8d, r8d; bInitialState
0x180024e69  mov     edx, 1; bManualReset
0x180024e6e  xor     ecx, ecx; lpEventAttributes
0x180024e70  call    cs:__imp_CreateEventA
0x180024e76  mov     rdi, rax
0x180024e79  mov     rcx, [rsp+0B8h+hObject]; hObject
0x180024e7e  lea     rax, [rcx-1]
0x180024e82  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024e86  ja      short loc_180024E8E
0x180024e88  call    cs:__imp_CloseHandle
0x180024e8e  mov     [rsp+0B8h+hObject], rdi
0x180024e93  jmp     short loc_180024E9A
0x180024e95  mov     rdi, [rsp+0B8h+hObject]
0x180024e9a  test    rdi, rdi
0x180024e9d  jz      short loc_180024EAD
0x180024e9f  mov     rcx, rdi; hEvent
0x180024ea2  call    cs:__imp_SetEvent
0x180024ea8  mov     rdi, [rsp+0B8h+hObject]
0x180024ead  lea     rax, [rdi-1]
0x180024eb1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024eb5  ja      short loc_180024EC0
0x180024eb7  mov     rcx, rdi; hObject
0x180024eba  call    cs:__imp_CloseHandle
0x180024ec0  mov     rcx, [rsp+0B8h+var_18]
0x180024ec8  xor     rcx, rsp; StackCookie
0x180024ecb  call    __security_check_cookie
0x180024ed0  lea     r11, [rsp+0B8h+var_8]
0x180024ed8  mov     rbx, [r11+20h]
0x180024edc  mov     rsi, [r11+28h]
0x180024ee0  mov     rsp, r11
0x180024ee3  pop     rdi
0x180024ee4  retn
0x180024ee5  cmp     [rsp+0B8h+var_80], 0
0x180024eea  jnz     short loc_180024F52
0x180024eec  lock inc dword ptr [rbx+4]
0x180024ef0  mov     [rsp+0B8h+var_80], 1
0x180024ef5  mov     eax, [rbx]
0x180024ef7  nop
0x180024ef8  cmp     eax, [rsp+0B8h+var_88]
0x180024efc  jz      short loc_180024EA8
0x180024efe  mov     rcx, [rsp+0B8h+hObject]
0x180024f03  test    rcx, rcx
0x180024f06  jnz     short loc_180024F57
0x180024f08  cmp     [rsp+0B8h+Name], cl
0x180024f0c  jnz     short loc_180024F1B
0x180024f0e  mov     rdx, rbx; char *
0x180024f11  lea     rcx, [rsp+0B8h+Name]; this
0x180024f16  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x180024f1b  lea     r9, [rsp+0B8h+Name]; lpName
0x180024f20  xor     r8d, r8d; bInitialState
0x180024f23  mov     edx, 1; bManualReset
0x180024f28  xor     ecx, ecx; lpEventAttributes
0x180024f2a  call    cs:__imp_CreateEventA
0x180024f30  mov     rdi, rax
0x180024f33  mov     rcx, [rsp+0B8h+hObject]; hObject
0x180024f38  lea     rdx, [rcx-1]
0x180024f3c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180024f40  ja      short loc_180024F48
0x180024f42  call    cs:__imp_CloseHandle
0x180024f48  mov     [rsp+0B8h+hObject], rdi
0x180024f4d  jmp     loc_180024DA2
0x180024f52  mov     rcx, [rsp+0B8h+hObject]; hHandle
0x180024f57  xor     r8d, r8d; bAlertable
0x180024f5a  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180024f5f  call    cs:__imp_WaitForSingleObjectEx
0x180024f65  jmp     loc_180024DA2
```
