# ClientIdentity::GetCallingProcessHandle(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18003aa54`
- end: `0x18003abde`
- name: `?GetCallingProcessHandle@ClientIdentity@@SAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800238a0`

## callees

- `0x1800075e4`
- `0x18000a464`
- `0x180013230`
- `0x18003aa54`
- `0x180068010`

## import_xrefs

- `combase!__imp_CoGetCallContextOfObject` at `0x18003aa87`
- `combase!__imp_CoGetCallContextOfObject` at `0x18003aa87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ab64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ab64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ab5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ab5c`

## string_xrefs

- `0x18003aa9a`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\clientidentity.cpp`
- `0x18003aaea`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\clientidentity.cpp`
- `0x18003ab78`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\clientidentity.cpp`
- `0x18003abc9`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\clientidentity.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ClientIdentity::GetCallingProcessHandle(__int64 a1, __int64 a2, void **a3, const char *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // rax
  int v9; // edi
  void *v10; // r15
  void *v11; // r14
  DWORD LastError; // ebx
  int v13; // [rsp+20h] [rbp-38h]
  const char *v14; // [rsp+28h] [rbp-30h]
  void **v15; // [rsp+30h] [rbp-28h]
  void *v16; // [rsp+38h] [rbp-20h] BYREF
  char v17; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  __int64 *v19; // [rsp+90h] [rbp+38h] BYREF

  if ( !a1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1A5,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\clientidentity.cpp",
      a4);
  v19 = 0;
  v5 = CoGetCallContextOfObject(a1, &GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &v19);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A8,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\clientidentity.cpp",
      (const char *)(unsigned int)v5,
      v13);
    if ( v19 )
      (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
    return v6;
  }
  if ( !v19 )
  {
    v6 = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1AD,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\clientidentity.cpp",
      (const char *)0x8000FFFFLL,
      (int)"Failed to get ICallingProcessInfo from call context.",
      v14);
    if ( v19 )
      (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
    return v6;
  }
  v8 = *v19;
  v15 = a3;
  v16 = 0;
  v17 = 1;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, void **))(v8 + 24))(v19, 1052672, &v16);
  if ( v17 )
  {
    v10 = v16;
    v11 = *v15;
    if ( *v15 )
    {
      LastError = GetLastError();
      CloseHandle(v11);
      SetLastError(LastError);
    }
    *v15 = v10;
  }
  if ( v9 >= 0 )
  {
    if ( v19 )
      (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\clientidentity.cpp",
      (const char *)(unsigned int)v9,
      v13);
    if ( v19 )
      (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x18003aa54  push    rbp
0x18003aa56  push    rbx
0x18003aa57  push    rsi
0x18003aa58  push    rdi
0x18003aa59  push    r14
0x18003aa5b  push    r15
0x18003aa5d  mov     rbp, rsp
0x18003aa60  sub     rsp, 58h
0x18003aa64  mov     rdi, r8
0x18003aa67  mov     rax, [rbp+30h]
0x18003aa6b  test    rcx, rcx
0x18003aa6e  jz      loc_18003ABC9
0x18003aa74  mov     [rbp+arg_0], 0
0x18003aa7c  lea     r8, [rbp+arg_0]
0x18003aa80  lea     rdx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541
0x18003aa87  call    cs:__imp_CoGetCallContextOfObject
0x18003aa8d  mov     ebx, eax
0x18003aa8f  test    eax, eax
0x18003aa91  jns     short loc_18003AAC9
0x18003aa93  mov     rcx, [rbp+30h]; this
0x18003aa97  mov     r9d, eax; char *
0x18003aa9a  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003aaa1  mov     edx, 1A8h; void *
0x18003aaa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aaab  nop
0x18003aaac  mov     rcx, [rbp+arg_0]
0x18003aab0  test    rcx, rcx
0x18003aab3  jz      short loc_18003AAC2
0x18003aab5  mov     rax, [rcx]
0x18003aab8  mov     rax, [rax+10h]
0x18003aabc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aac1  nop
0x18003aac2  mov     eax, ebx
0x18003aac4  jmp     loc_18003ABBC
0x18003aac9  mov     rcx, [rbp+arg_0]
0x18003aacd  test    rcx, rcx
0x18003aad0  jnz     short loc_18003AB14
0x18003aad2  mov     rcx, [rbp+30h]; this
0x18003aad6  lea     rax, aFailedToGetIca; "Failed to get ICallingProcessInfo from "...
0x18003aadd  mov     qword ptr [rsp+58h+var_38], rax; int
0x18003aae2  mov     ebx, 8000FFFFh
0x18003aae7  mov     r9d, ebx; char *
0x18003aaea  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003aaf1  mov     edx, 1ADh; void *
0x18003aaf6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003aafb  nop
0x18003aafc  mov     rcx, [rbp+arg_0]
0x18003ab00  test    rcx, rcx
0x18003ab03  jz      short loc_18003AB12
0x18003ab05  mov     rdx, [rcx]
0x18003ab08  mov     rax, [rdx+10h]
0x18003ab0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab11  nop
0x18003ab12  jmp     short loc_18003AAC2
0x18003ab14  mov     rax, [rcx]
0x18003ab17  mov     [rbp+var_28], rdi
0x18003ab1b  mov     [rbp+var_20], 0
0x18003ab23  mov     [rbp+var_18], 1
0x18003ab27  lea     r8, [rbp+var_20]
0x18003ab2b  mov     edx, 101000h
0x18003ab30  mov     rax, [rax+18h]
0x18003ab34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab39  mov     edi, eax
0x18003ab3b  cmp     [rbp+var_18], 0
0x18003ab3f  jz      short loc_18003AB6D
0x18003ab41  mov     r15, [rbp+var_20]
0x18003ab45  mov     rsi, [rbp+var_28]
0x18003ab49  mov     r14, [rsi]
0x18003ab4c  test    r14, r14
0x18003ab4f  jz      short loc_18003AB6A
0x18003ab51  call    cs:__imp_GetLastError
0x18003ab57  mov     ebx, eax
0x18003ab59  mov     rcx, r14; hObject
0x18003ab5c  call    cs:__imp_CloseHandle
0x18003ab62  mov     ecx, ebx; dwErrCode
0x18003ab64  call    cs:__imp_SetLastError
0x18003ab6a  mov     [rsi], r15
0x18003ab6d  test    edi, edi
0x18003ab6f  jns     short loc_18003ABA4
0x18003ab71  mov     rcx, [rbp+30h]; this
0x18003ab75  mov     r9d, edi; char *
0x18003ab78  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003ab7f  mov     edx, 1B4h; void *
0x18003ab84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ab89  nop
0x18003ab8a  mov     rcx, [rbp+arg_0]
0x18003ab8e  test    rcx, rcx
0x18003ab91  jz      short loc_18003ABA0
0x18003ab93  mov     rax, [rcx]
0x18003ab96  mov     rax, [rax+10h]
0x18003ab9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab9f  nop
0x18003aba0  mov     eax, edi
0x18003aba2  jmp     short loc_18003ABBC
0x18003aba4  mov     rcx, [rbp+arg_0]
0x18003aba8  test    rcx, rcx
0x18003abab  jz      short loc_18003ABBA
0x18003abad  mov     rax, [rcx]
0x18003abb0  mov     rax, [rax+10h]
0x18003abb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abb9  nop
0x18003abba  xor     eax, eax
0x18003abbc  add     rsp, 58h
0x18003abc0  pop     r15
0x18003abc2  pop     r14
0x18003abc4  pop     rdi
0x18003abc5  pop     rsi
0x18003abc6  pop     rbx
0x18003abc7  pop     rbp
0x18003abc8  retn
0x18003abc9  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003abd0  mov     edx, 1A5h; void *
0x18003abd5  mov     rcx, rax; this
0x18003abd8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
