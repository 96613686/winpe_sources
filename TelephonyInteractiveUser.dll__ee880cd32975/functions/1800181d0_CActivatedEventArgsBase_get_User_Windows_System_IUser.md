# CActivatedEventArgsBase::get_User(Windows::System::IUser * *)

- ea: `0x1800181d0`
- end: `0x1800183a2`
- name: `?get_User@CActivatedEventArgsBase@@UEAAJPEAPEAUIUser@System@Windows@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(CActivatedEventArgsBase *__hidden this, struct Windows::System::IUser **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001dc0`
- `0x18000e284`
- `0x18000ed10`
- `0x1800181d0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018244`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018244`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018216`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018216`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018201`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018201`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001827d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001827d`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsBase::get_User(RTL_SRWLOCK *this, struct Windows::System::IUser **a2)
{
  RTL_SRWLOCK *v2; // rdi
  PVOID Ptr; // r14
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  int ActivationFactory; // eax
  int v10; // ebx
  __int64 (__fastcall ***v11)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-40h] BYREF
  __int64 v18; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v2 = this + 17;
  AcquireSRWLockShared(this + 17);
  Ptr = this[12].Ptr;
  if ( v2 )
    ReleaseSRWLockShared(v2);
  *a2 = 0;
  if ( !Ptr )
    return 0;
  v17 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"Windows.System.Internal.UserManager", 0x23u, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    JUMPOUT(0x1800183A1LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9, &v17);
  v10 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v18 = 0;
    v10 = (**v17)(v17, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v18);
    if ( v10 < 0 )
    {
      v13 = 425;
      goto LABEL_12;
    }
    v10 = (*(__int64 (__fastcall **)(__int64, PVOID, struct Windows::System::IUser **))(*(_QWORD *)v18 + 160LL))(
            v18,
            Ptr,
            a2);
    if ( v10 < 0 )
    {
      v13 = 427;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
        (const char *)(unsigned int)v10,
        (int)v17);
      v14 = v18;
      if ( v18 )
      {
        v18 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      goto LABEL_7;
    }
    v15 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = v17;
    string = 0;
    if ( v17 )
    {
      v17 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v16)[2])(v16);
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A6,
    (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
    (const char *)(unsigned int)ActivationFactory,
    (int)v17);
LABEL_7:
  v11 = v17;
  string = 0;
  if ( v17 )
  {
    v17 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v11)[2])(v11);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800181d0  mov     [rsp-28h+arg_10], rbx
0x1800181d5  push    rbp
0x1800181d6  push    rsi
0x1800181d7  push    rdi
0x1800181d8  push    r14
0x1800181da  push    r15
0x1800181dc  mov     rbp, rsp
0x1800181df  sub     rsp, 60h
0x1800181e3  mov     rax, cs:__security_cookie
0x1800181ea  xor     rax, rsp
0x1800181ed  mov     [rbp+var_10], rax
0x1800181f1  lea     rdi, [rcx+88h]
0x1800181f8  mov     rbx, rcx
0x1800181fb  mov     rcx, rdi; SRWLock
0x1800181fe  mov     rsi, rdx
0x180018201  call    cs:__imp_AcquireSRWLockShared
0x180018207  mov     r14, [rbx+60h]
0x18001820b  xor     r15d, r15d
0x18001820e  test    rdi, rdi
0x180018211  jz      short loc_18001821C
0x180018213  mov     rcx, rdi; SRWLock
0x180018216  call    cs:__imp_ReleaseSRWLockShared
0x18001821c  mov     [rsi], r15
0x18001821f  test    r14, r14
0x180018222  jz      loc_180018378
0x180018228  lea     r9, [rbp+string]; string
0x18001822c  mov     [rbp+var_40], r15
0x180018230  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180018234  mov     [rbp+string], r15
0x180018238  mov     edx, 23h ; '#'; length
0x18001823d  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180018244  call    cs:__imp_WindowsCreateStringReference
0x18001824a  test    eax, eax
0x18001824c  js      loc_18001839A
0x180018252  mov     rcx, [rbp+var_40]
0x180018256  mov     rbx, [rbp+string]
0x18001825a  test    rcx, rcx
0x18001825d  jz      short loc_18001826F
0x18001825f  mov     [rbp+var_40], r15
0x180018263  mov     rax, [rcx]
0x180018266  mov     rax, [rax+10h]
0x18001826a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001826f  lea     r8, [rbp+var_40]
0x180018273  mov     rcx, rbx
0x180018276  lea     rdx, _GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9
0x18001827d  call    cs:__imp_RoGetActivationFactory
0x180018283  mov     ebx, eax
0x180018285  test    eax, eax
0x180018287  jns     short loc_1800182C5
0x180018289  mov     rcx, [rbp+28h]; this
0x18001828d  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180018294  mov     r9d, eax; char *
0x180018297  mov     edx, 1A6h; void *
0x18001829c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800182a1  mov     rcx, [rbp+var_40]
0x1800182a5  mov     [rbp+string], r15
0x1800182a9  test    rcx, rcx
0x1800182ac  jz      short loc_1800182BE
0x1800182ae  mov     [rbp+var_40], r15
0x1800182b2  mov     rax, [rcx]
0x1800182b5  mov     rax, [rax+10h]
0x1800182b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182be  mov     eax, ebx
0x1800182c0  jmp     loc_18001837A
0x1800182c5  mov     rcx, [rbp+var_40]
0x1800182c9  lea     r8, [rbp+var_38]
0x1800182cd  mov     [rbp+var_38], r15
0x1800182d1  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x1800182d8  mov     rax, [rcx]
0x1800182db  mov     rax, [rax]
0x1800182de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182e3  mov     ebx, eax
0x1800182e5  test    eax, eax
0x1800182e7  jns     short loc_18001831C
0x1800182e9  mov     edx, 1A9h; void *
0x1800182ee  mov     rcx, [rbp+28h]; this
0x1800182f2  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800182f9  mov     r9d, ebx; char *
0x1800182fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018301  mov     rcx, [rbp+var_38]
0x180018305  test    rcx, rcx
0x180018308  jz      short loc_1800182A1
0x18001830a  mov     [rbp+var_38], r15
0x18001830e  mov     rax, [rcx]
0x180018311  mov     rax, [rax+10h]
0x180018315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001831a  jmp     short loc_1800182A1
0x18001831c  mov     rcx, [rbp+var_38]
0x180018320  mov     r8, rsi
0x180018323  mov     rdx, r14
0x180018326  mov     rax, [rcx]
0x180018329  mov     rax, [rax+0A0h]
0x180018330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018335  mov     ebx, eax
0x180018337  test    eax, eax
0x180018339  jns     short loc_180018342
0x18001833b  mov     edx, 1ABh
0x180018340  jmp     short loc_1800182EE
0x180018342  mov     rcx, [rbp+var_38]
0x180018346  test    rcx, rcx
0x180018349  jz      short loc_18001835B
0x18001834b  mov     [rbp+var_38], r15
0x18001834f  mov     rax, [rcx]
0x180018352  mov     rax, [rax+10h]
0x180018356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001835b  mov     rcx, [rbp+var_40]
0x18001835f  mov     [rbp+string], r15
0x180018363  test    rcx, rcx
0x180018366  jz      short loc_180018378
0x180018368  mov     [rbp+var_40], r15
0x18001836c  mov     rax, [rcx]
0x18001836f  mov     rax, [rax+10h]
0x180018373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018378  xor     eax, eax
0x18001837a  mov     rcx, [rbp+var_10]
0x18001837e  xor     rcx, rsp; StackCookie
0x180018381  call    __security_check_cookie
0x180018386  mov     rbx, [rsp+60h+arg_10]
0x18001838e  add     rsp, 60h
0x180018392  pop     r15
0x180018394  pop     r14
0x180018396  pop     rdi
0x180018397  pop     rsi
0x180018398  pop     rbp
0x180018399  retn
0x18001839a  mov     ecx, eax; this
0x18001839c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
