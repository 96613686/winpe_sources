# boost::call_once(boost::once_flag &,void (*)(void))

- ea: `0x1800392c0`
- end: `0x1800394db`
- name: `?call_once@boost@@YAXAEAUonce_flag@1@P6AXXZ@Z`
- size: `539`
- prototype: `void __fastcall(struct boost::once_flag *, void (*)(void))`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180039a80`

## callees

- `0x18002c570`
- `0x1800392c0`
- `0x180039810`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180039384`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180039384`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800393e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18003949a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800393e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18003949a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180039412`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180039412`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x180039359`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x180039359`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800394cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800394cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039371`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800393f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003942a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800394b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039371`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800393f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003942a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800394b2`

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
0x1800392c0  mov     [rsp+arg_10], rbx
0x1800392c5  mov     [rsp+arg_18], rsi
0x1800392ca  push    rdi
0x1800392cb  sub     rsp, 0B0h
0x1800392d2  mov     rax, cs:__security_cookie
0x1800392d9  xor     rax, rsp
0x1800392dc  mov     [rsp+0B8h+var_18], rax
0x1800392e4  mov     rsi, rdx
0x1800392e7  mov     rbx, rcx
0x1800392ea  mov     [rsp+0B8h+var_90], rcx
0x1800392ef  mov     [rsp+0B8h+var_88], 0C15730E2h
0x1800392f7  mov     [rsp+0B8h+var_84], 7F0725E3h
0x1800392ff  mov     [rsp+0B8h+var_80], 0
0x180039304  mov     [rsp+0B8h+hObject], 0
0x18003930d  mov     [rsp+0B8h+Name], 0
0x180039312  mov     eax, [rbx]
0x180039314  nop
0x180039315  cmp     eax, [rsp+0B8h+var_88]
0x180039319  jz      loc_180039418
0x18003931f  mov     ecx, [rsp+0B8h+var_84]
0x180039323  xor     eax, eax
0x180039325  lock cmpxchg [rbx], ecx
0x180039329  jnz     loc_180039455
0x18003932f  mov     rdi, [rsp+0B8h+hObject]
0x180039334  test    rdi, rdi
0x180039337  jnz     short loc_180039381
0x180039339  cmp     [rsp+0B8h+Name], dil
0x18003933e  jnz     short loc_18003934D
0x180039340  mov     rdx, rbx; char *
0x180039343  lea     rcx, [rsp+0B8h+Name]; this
0x180039348  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x18003934d  lea     r8, [rsp+0B8h+Name]; lpName
0x180039352  xor     edx, edx; bInheritHandle
0x180039354  mov     ecx, 100002h; dwDesiredAccess
0x180039359  call    cs:__imp_OpenEventA
0x18003935f  mov     rdi, rax
0x180039362  mov     rcx, [rsp+0B8h+hObject]; hObject
0x180039367  lea     rax, [rcx-1]
0x18003936b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003936f  ja      short loc_180039377
0x180039371  call    cs:__imp_CloseHandle
0x180039377  mov     [rsp+0B8h+hObject], rdi
0x18003937c  test    rdi, rdi
0x18003937f  jz      short loc_18003938B
0x180039381  mov     rcx, rdi; hEvent
0x180039384  call    cs:__imp_ResetEvent
0x18003938a  nop
0x18003938b  mov     rax, rsi
0x18003938e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039393  nop
0x180039394  cmp     [rsp+0B8h+var_80], 0
0x180039399  jnz     short loc_1800393A4
0x18003939b  lock inc dword ptr [rbx+4]
0x18003939f  mov     [rsp+0B8h+var_80], 1
0x1800393a4  mov     eax, [rsp+0B8h+var_88]
0x1800393a8  xchg    eax, [rbx]
0x1800393aa  mov     rdi, [rsp+0B8h+hObject]
0x1800393af  test    rdi, rdi
0x1800393b2  jnz     short loc_18003940F
0x1800393b4  mov     eax, [rbx+4]
0x1800393b7  nop
0x1800393b8  cmp     eax, 1
0x1800393bb  jle     short loc_180039405
0x1800393bd  cmp     [rsp+0B8h+Name], dil
0x1800393c2  jnz     short loc_1800393D1
0x1800393c4  mov     rdx, rbx; char *
0x1800393c7  lea     rcx, [rsp+0B8h+Name]; this
0x1800393cc  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x1800393d1  lea     r9, [rsp+0B8h+Name]; lpName
0x1800393d6  xor     r8d, r8d; bInitialState
0x1800393d9  mov     edx, 1; bManualReset
0x1800393de  xor     ecx, ecx; lpEventAttributes
0x1800393e0  call    cs:__imp_CreateEventA
0x1800393e6  mov     rdi, rax
0x1800393e9  mov     rcx, [rsp+0B8h+hObject]; hObject
0x1800393ee  lea     rax, [rcx-1]
0x1800393f2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800393f6  ja      short loc_1800393FE
0x1800393f8  call    cs:__imp_CloseHandle
0x1800393fe  mov     [rsp+0B8h+hObject], rdi
0x180039403  jmp     short loc_18003940A
0x180039405  mov     rdi, [rsp+0B8h+hObject]
0x18003940a  test    rdi, rdi
0x18003940d  jz      short loc_18003941D
0x18003940f  mov     rcx, rdi; hEvent
0x180039412  call    cs:__imp_SetEvent
0x180039418  mov     rdi, [rsp+0B8h+hObject]
0x18003941d  lea     rax, [rdi-1]
0x180039421  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180039425  ja      short loc_180039430
0x180039427  mov     rcx, rdi; hObject
0x18003942a  call    cs:__imp_CloseHandle
0x180039430  mov     rcx, [rsp+0B8h+var_18]
0x180039438  xor     rcx, rsp; StackCookie
0x18003943b  call    __security_check_cookie
0x180039440  lea     r11, [rsp+0B8h+var_8]
0x180039448  mov     rbx, [r11+20h]
0x18003944c  mov     rsi, [r11+28h]
0x180039450  mov     rsp, r11
0x180039453  pop     rdi
0x180039454  retn
0x180039455  cmp     [rsp+0B8h+var_80], 0
0x18003945a  jnz     short loc_1800394C2
0x18003945c  lock inc dword ptr [rbx+4]
0x180039460  mov     [rsp+0B8h+var_80], 1
0x180039465  mov     eax, [rbx]
0x180039467  nop
0x180039468  cmp     eax, [rsp+0B8h+var_88]
0x18003946c  jz      short loc_180039418
0x18003946e  mov     rcx, [rsp+0B8h+hObject]
0x180039473  test    rcx, rcx
0x180039476  jnz     short loc_1800394C7
0x180039478  cmp     [rsp+0B8h+Name], cl
0x18003947c  jnz     short loc_18003948B
0x18003947e  mov     rdx, rbx; char *
0x180039481  lea     rcx, [rsp+0B8h+Name]; this
0x180039486  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x18003948b  lea     r9, [rsp+0B8h+Name]; lpName
0x180039490  xor     r8d, r8d; bInitialState
0x180039493  mov     edx, 1; bManualReset
0x180039498  xor     ecx, ecx; lpEventAttributes
0x18003949a  call    cs:__imp_CreateEventA
0x1800394a0  mov     rdi, rax
0x1800394a3  mov     rcx, [rsp+0B8h+hObject]; hObject
0x1800394a8  lea     rdx, [rcx-1]
0x1800394ac  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800394b0  ja      short loc_1800394B8
0x1800394b2  call    cs:__imp_CloseHandle
0x1800394b8  mov     [rsp+0B8h+hObject], rdi
0x1800394bd  jmp     loc_180039312
0x1800394c2  mov     rcx, [rsp+0B8h+hObject]; hHandle
0x1800394c7  xor     r8d, r8d; bAlertable
0x1800394ca  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800394cf  call    cs:__imp_WaitForSingleObjectEx
0x1800394d5  jmp     loc_180039312
```
