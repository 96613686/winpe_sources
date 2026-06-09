# Windows::Internal::AssignedAccess::AAManagerHelper::GetAssignedAccessTypeForUserWithoutGroup(ushort const *,Windows::Internal::AssignedAccess::AssignedAccessType *)

- ea: `0x18000be8c`
- end: `0x18000bfe7`
- name: `?GetAssignedAccessTypeForUserWithoutGroup@AAManagerHelper@AssignedAccess@Internal@Windows@@AEAAJPEBGPEAW4AssignedAccessType@234@@Z`
- size: `347`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::AAManagerHelper *this, const unsigned __int16 *, enum Windows::Internal::AssignedAccess::AssignedAccessType *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ab90`

## callees

- `0x180006804`
- `0x18000ba5c`
- `0x18000be24`
- `0x18000be8c`
- `0x18000e010`

## string_xrefs

- `0x18000bec0`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\aamanagerhelper.cpp`
- `0x18000bf13`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\aamanagerhelper.cpp`
- `0x18000bf73`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\aamanagerhelper.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::AAManagerHelper::GetAssignedAccessTypeForUserWithoutGroup(
        Windows::Internal::AssignedAccess::AAManagerHelper *this,
        const unsigned __int16 *a2,
        enum Windows::Internal::AssignedAccess::AssignedAccessType *a3)
{
  int AssignedAccessConfiguration; // eax
  unsigned int v5; // ebx
  void (*v6)(void); // rax
  int UserInfoIf__lambda_85f277e70fc2df7bef089658807efc79; // eax
  __int64 v9; // rbx
  int v10; // eax
  unsigned int v11; // edi
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  const unsigned __int16 *v14; // [rsp+48h] [rbp+28h] BYREF
  struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *v15; // [rsp+50h] [rbp+30h] BYREF
  __int64 v16; // [rsp+58h] [rbp+38h] BYREF

  v14 = a2;
  *(_DWORD *)a3 = 0;
  v15 = 0;
  AssignedAccessConfiguration = Windows::Internal::AssignedAccess::AAManagerHelper::GetAssignedAccessConfiguration(
                                  this,
                                  &v15);
  v5 = AssignedAccessConfiguration;
  if ( AssignedAccessConfiguration < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\aamanagerhelper.cpp",
      (const char *)(unsigned int)AssignedAccessConfiguration,
      savedregs);
    if ( !v15 )
      return v5;
    v6 = *(void (**)(void))(*(_QWORD *)v15 + 16LL);
LABEL_4:
    v6();
    return v5;
  }
  v16 = 0;
  UserInfoIf__lambda_85f277e70fc2df7bef089658807efc79 = Windows::Internal::AssignedAccess::AssignedAccessConfigurationHelper::FindUserInfoIf__lambda_85f277e70fc2df7bef089658807efc79___(
                                                          &v14,
                                                          v15,
                                                          &v16);
  v5 = UserInfoIf__lambda_85f277e70fc2df7bef089658807efc79;
  if ( UserInfoIf__lambda_85f277e70fc2df7bef089658807efc79 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\aamanagerhelper.cpp",
      (const char *)(unsigned int)UserInfoIf__lambda_85f277e70fc2df7bef089658807efc79,
      savedregs);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    if ( !v15 )
      return v5;
    v6 = *(void (**)(void))(*(_QWORD *)v15 + 16LL);
    goto LABEL_4;
  }
  v9 = v16;
  if ( v16 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, enum Windows::Internal::AssignedAccess::AssignedAccessType *))(*(_QWORD *)v16 + 80LL))(
            v16,
            a3);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCC,
        (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\aamanagerhelper.cpp",
        (const char *)(unsigned int)v10,
        savedregs);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      if ( v15 )
        (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *))(*(_QWORD *)v15 + 16LL))(v15);
      return v11;
    }
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  if ( v15 )
    (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *))(*(_QWORD *)v15 + 16LL))(v15);
  return 0;
}

```

## disassembly

```asm
0x18000be8c  mov     [rsp-18h+arg_8], rdx
0x18000be91  push    rbp
0x18000be92  push    rbx
0x18000be93  push    rdi; int
0x18000be94  mov     rbp, rsp
0x18000be97  sub     rsp, 20h
0x18000be9b  lea     rdx, [rbp+arg_10]; struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration **
0x18000be9f  mov     dword ptr [r8], 0
0x18000bea6  mov     rdi, r8
0x18000bea9  mov     [rbp+arg_10], 0
0x18000beb1  call    ?GetAssignedAccessConfiguration@AAManagerHelper@AssignedAccess@Internal@Windows@@AEAAJPEAPEAUIAssignedAccessConfiguration@234@@Z; Windows::Internal::AssignedAccess::AAManagerHelper::GetAssignedAccessConfiguration(Windows::Internal::AssignedAccess::IAssignedAccessConfiguration * *)
0x18000beb6  mov     ebx, eax
0x18000beb8  test    eax, eax
0x18000beba  jns     short loc_18000BEF0
0x18000bebc  mov     rcx, [rbp+18h]; this
0x18000bec0  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x18000bec7  mov     r9d, eax; char *
0x18000beca  mov     edx, 0BDh; void *
0x18000becf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bed4  mov     rcx, [rbp+arg_10]
0x18000bed8  test    rcx, rcx
0x18000bedb  jz      short loc_18000BEE9
0x18000bedd  mov     rdx, [rcx]
0x18000bee0  mov     rax, [rdx+10h]
0x18000bee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee9  mov     eax, ebx
0x18000beeb  jmp     loc_18000BFDF
0x18000bef0  mov     rdx, [rbp+arg_10]
0x18000bef4  lea     r8, [rbp+arg_18]
0x18000bef8  lea     rcx, [rbp+arg_8]
0x18000befc  mov     [rbp+arg_18], 0
0x18000bf04  call    Windows__Internal__AssignedAccess__AssignedAccessConfigurationHelper__FindUserInfoIf__lambda_85f277e70fc2df7bef089658807efc79___
0x18000bf09  mov     ebx, eax
0x18000bf0b  test    eax, eax
0x18000bf0d  jns     short loc_18000BF4E
0x18000bf0f  mov     rcx, [rbp+18h]; this
0x18000bf13  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x18000bf1a  mov     r9d, eax; char *
0x18000bf1d  mov     edx, 0C9h; void *
0x18000bf22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bf27  mov     rcx, [rbp+arg_18]
0x18000bf2b  test    rcx, rcx
0x18000bf2e  jz      short loc_18000BF3C
0x18000bf30  mov     rdx, [rcx]
0x18000bf33  mov     rax, [rdx+10h]
0x18000bf37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf3c  mov     rcx, [rbp+arg_10]
0x18000bf40  test    rcx, rcx
0x18000bf43  jz      short loc_18000BEE9
0x18000bf45  mov     rax, [rcx]
0x18000bf48  mov     rax, [rax+10h]
0x18000bf4c  jmp     short loc_18000BEE4
0x18000bf4e  mov     rbx, [rbp+arg_18]
0x18000bf52  test    rbx, rbx
0x18000bf55  jz      short loc_18000BFC8
0x18000bf57  mov     rax, [rbx]
0x18000bf5a  mov     rdx, rdi
0x18000bf5d  mov     rcx, rbx
0x18000bf60  mov     rax, [rax+50h]
0x18000bf64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf69  mov     edi, eax
0x18000bf6b  test    eax, eax
0x18000bf6d  jns     short loc_18000BFB4
0x18000bf6f  mov     rcx, [rbp+18h]; this
0x18000bf73  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x18000bf7a  mov     r9d, eax; char *
0x18000bf7d  mov     edx, 0CCh; void *
0x18000bf82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bf87  test    rbx, rbx
0x18000bf8a  jz      short loc_18000BF9B
0x18000bf8c  mov     rcx, [rbx]
0x18000bf8f  mov     rax, [rcx+10h]
0x18000bf93  mov     rcx, rbx
0x18000bf96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf9b  mov     rcx, [rbp+arg_10]
0x18000bf9f  test    rcx, rcx
0x18000bfa2  jz      short loc_18000BFB0
0x18000bfa4  mov     rax, [rcx]
0x18000bfa7  mov     rax, [rax+10h]
0x18000bfab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfb0  mov     eax, edi
0x18000bfb2  jmp     short loc_18000BFDF
0x18000bfb4  test    rbx, rbx
0x18000bfb7  jz      short loc_18000BFC8
0x18000bfb9  mov     rax, [rbx]
0x18000bfbc  mov     rcx, rbx
0x18000bfbf  mov     rax, [rax+10h]
0x18000bfc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfc8  mov     rcx, [rbp+arg_10]
0x18000bfcc  test    rcx, rcx
0x18000bfcf  jz      short loc_18000BFDD
0x18000bfd1  mov     rax, [rcx]
0x18000bfd4  mov     rax, [rax+10h]
0x18000bfd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfdd  xor     eax, eax
0x18000bfdf  add     rsp, 20h
0x18000bfe3  pop     rdi
0x18000bfe4  pop     rbx
0x18000bfe5  pop     rbp
0x18000bfe6  retn
```
