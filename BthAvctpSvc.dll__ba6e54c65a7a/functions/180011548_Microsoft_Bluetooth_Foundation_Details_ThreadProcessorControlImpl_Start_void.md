# Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::Start(void)

- ea: `0x180011548`
- end: `0x1800116de`
- name: `?Start@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@AEAAXXZ`
- size: `406`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010ce0`

## callees

- `0x180004060`
- `0x18000dca8`
- `0x18000e0c0`
- `0x180011548`
- `0x180012130`
- `0x180012554`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800115d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800115d7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180011624`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180011624`

## string_xrefs

- `0x1800115f3`: `onecore\drivers\bluetooth\foundation\lib\threadprocessor.cpp`
- `0x18001164a`: `onecore\drivers\bluetooth\foundation\lib\threadprocessor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::Start(RTL_SRWLOCK *this)
{
  bool v2; // dl
  HANDLE Thread; // rax
  const char *v4; // r9
  bool v5; // dl
  DWORD dwCreationFlags; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  RTL_SRWLOCK *v8; // [rsp+70h] [rbp+8h] BYREF

  v2 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      4,
      1,
      19,
      &WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids,
      (char)this);
  AcquireSRWLockExclusive(this + 9);
  v8 = this + 9;
  if ( LOBYTE(this[12].Ptr) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\threadprocessor.cpp",
      (const char *)0x8000000ELL,
      dwCreationFlags);
  Thread = CreateThread(0, 0, _lambda_ffaf3c16fc6d275c581e97f8475f4c48_::_lambda_invoker_cdecl_, this, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &this[6],
    Thread);
  if ( (((unsigned __int64)this[6].Ptr + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x126,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\threadprocessor.cpp",
      v4);
  LOBYTE(this[12].Ptr) = 1;
  v5 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      4,
      1,
      22,
      &WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids,
      (char)this);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
}

```

## disassembly

```asm
0x180011548  mov     [rsp+arg_8], rbx
0x18001154d  mov     [rsp+arg_10], rbp
0x180011552  push    rdi
0x180011553  push    r14
0x180011555  push    r15
0x180011557  sub     rsp, 50h
0x18001155b  mov     rdi, rcx
0x18001155e  lea     rbp, WPP_GLOBAL_Control
0x180011565  mov     rcx, cs:WPP_GLOBAL_Control
0x18001156c  cmp     rcx, rbp
0x18001156f  jz      short loc_180011581
0x180011571  test    byte ptr [rcx+1Ch], 1
0x180011575  jz      short loc_180011581
0x180011577  cmp     byte ptr [rcx+19h], 4
0x18001157b  jb      short loc_180011581
0x18001157d  mov     dl, 1
0x18001157f  jmp     short loc_180011583
0x180011581  xor     dl, dl; int
0x180011583  lea     r14, WPP_RECORDER_INITIALIZED
0x18001158a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180011591  setnz   r8b; int
0x180011595  lea     r15, WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids
0x18001159c  test    dl, dl
0x18001159e  jnz     short loc_1800115A5
0x1800115a0  test    r8b, r8b
0x1800115a3  jz      short loc_1800115D0
0x1800115a5  mov     qword ptr [rsp+68h+var_28], rdi; char
0x1800115aa  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x1800115af  mov     [rsp+68h+var_38], 13h; __int16
0x1800115b6  mov     dword ptr [rsp+68h+lpThreadId], 1; int
0x1800115be  mov     byte ptr [rsp+68h+dwCreationFlags], 4; int
0x1800115c3  mov     r9, [rcx+28h]; int
0x1800115c7  mov     rcx, [rcx+10h]; int
0x1800115cb  call    WPP_RECORDER_AND_TRACE_SF_q
0x1800115d0  lea     rbx, [rdi+48h]
0x1800115d4  mov     rcx, rbx; SRWLock
0x1800115d7  call    cs:__imp_AcquireSRWLockExclusive
0x1800115dd  mov     [rsp+68h+arg_0], rbx
0x1800115e2  cmp     byte ptr [rdi+60h], 0
0x1800115e6  jz      short loc_180011605
0x1800115e8  mov     rcx, [rsp+68h]; this
0x1800115ed  mov     r9d, 8000000Eh; char *
0x1800115f3  lea     r8, aOnecoreDrivers_38; "onecore\\drivers\\bluetooth\\foundation"...
0x1800115fa  mov     edx, 112h; void *
0x1800115ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011605  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18001160e  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x180011616  mov     r9, rdi; lpParameter
0x180011619  lea     r8, ?_lambda_invoker_cdecl_@_lambda_ffaf3c16fc6d275c581e97f8475f4c48_@@CAKPEAX@Z; lpStartAddress
0x180011620  xor     edx, edx; dwStackSize
0x180011622  xor     ecx, ecx; lpThreadAttributes
0x180011624  call    cs:__imp_CreateThread
0x18001162a  mov     rdx, rax
0x18001162d  lea     rcx, [rdi+30h]
0x180011631  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180011636  mov     rax, [rdi+30h]
0x18001163a  inc     rax
0x18001163d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180011643  jnz     short loc_18001165C
0x180011645  mov     rcx, [rsp+68h]; this
0x18001164a  lea     r8, aOnecoreDrivers_38; "onecore\\drivers\\bluetooth\\foundation"...
0x180011651  mov     edx, 126h; void *
0x180011656  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001165c  mov     byte ptr [rdi+60h], 1
0x180011660  mov     rcx, cs:WPP_GLOBAL_Control
0x180011667  cmp     rcx, rbp
0x18001166a  jz      short loc_18001167C
0x18001166c  test    byte ptr [rcx+1Ch], 1
0x180011670  jz      short loc_18001167C
0x180011672  cmp     byte ptr [rcx+19h], 4
0x180011676  jb      short loc_18001167C
0x180011678  mov     dl, 1
0x18001167a  jmp     short loc_18001167E
0x18001167c  xor     dl, dl; int
0x18001167e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180011685  setnz   r8b; int
0x180011689  test    dl, dl
0x18001168b  jnz     short loc_180011692
0x18001168d  test    r8b, r8b
0x180011690  jz      short loc_1800116BE
0x180011692  mov     qword ptr [rsp+68h+var_28], rdi; char
0x180011697  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x18001169c  mov     [rsp+68h+var_38], 16h; __int16
0x1800116a3  mov     dword ptr [rsp+68h+lpThreadId], 1; int
0x1800116ab  mov     byte ptr [rsp+68h+dwCreationFlags], 4; char
0x1800116b0  mov     r9, [rcx+28h]; int
0x1800116b4  mov     rcx, [rcx+10h]; int
0x1800116b8  call    WPP_RECORDER_AND_TRACE_SF_q
0x1800116bd  nop
0x1800116be  lea     rcx, [rsp+68h+arg_0]
0x1800116c3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800116c8  lea     r11, [rsp+68h+var_18]
0x1800116cd  mov     rbx, [r11+28h]
0x1800116d1  mov     rbp, [r11+30h]
0x1800116d5  mov     rsp, r11
0x1800116d8  pop     r15
0x1800116da  pop     r14
0x1800116dc  pop     rdi
0x1800116dd  retn
```
