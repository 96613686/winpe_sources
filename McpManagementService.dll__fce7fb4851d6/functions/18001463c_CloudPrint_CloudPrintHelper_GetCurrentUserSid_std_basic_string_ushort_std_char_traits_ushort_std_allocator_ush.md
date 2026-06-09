# CloudPrint::CloudPrintHelper::GetCurrentUserSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001463c`
- end: `0x1800146b2`
- name: `?GetCurrentUserSid@CloudPrintHelper@CloudPrint@@IEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `118`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18001a404`

## callees

- `0x18000e164`
- `0x18001227c`
- `0x180012a44`
- `0x18001463c`
- `0x180017614`
- `0x18001c298`

## string_xrefs

- `0x180014686`: `Couldn't get User SID. hr=%#x`
- `0x18001468d`: `CloudPrint::CloudPrintHelper::GetCurrentUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
__int64 __fastcall CloudPrint::CloudPrintHelper::GetCurrentUserSid(__int64 a1, __int64 a2)
{
  _WORD *v3; // rax
  _QWORD *v4; // rdx
  void *v5; // r9
  int (*v6)(void *); // r8
  int (*v7)(void *); // rdx
  int UserSid; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  _BYTE v12[40]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)(a2 + 16) = 0;
  v3 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  *v3 = 0;
  v5 = (void *)v4[4];
  v6 = (int (*)(void *))v4[3];
  v7 = (int (*)(void *))v4[2];
  try
  {
    CloudPrint::ImpersonateClientRAII::ImpersonateClientRAII((CloudPrint::ImpersonateClientRAII *)v12, v7, v6, v5);
    UserSid = PrintCore::TokenHelpers::GetUserSid(a2);
    v9 = UserSid;
    if ( UserSid < 0 )
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::GetCurrentUserSid",
        L"Couldn't get User SID. hr=%#x",
        (unsigned int)UserSid);
    CloudPrint::ImpersonateClientRAII::~ImpersonateClientRAII((CloudPrint::ImpersonateClientRAII *)v12);
    result = v9;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x703,
                           (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x18001463c  push    rbx
0x18001463e  sub     rsp, 40h
0x180014642  mov     rbx, rdx
0x180014645  mov     rdx, rcx
0x180014648  mov     qword ptr [rbx+10h], 0
0x180014650  mov     rcx, rbx
0x180014653  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014658  xor     r8d, r8d
0x18001465b  mov     [rax], r8w
0x18001465f  mov     r9, [rdx+20h]; void *
0x180014663  mov     r8, [rdx+18h]; int (*)(void *)
0x180014667  mov     rdx, [rdx+10h]; int (*)(void *)
0x18001466b  lea     rcx, [rsp+48h+var_28]; this
0x180014670  call    ??0ImpersonateClientRAII@CloudPrint@@QEAA@P6AJPEAX@Z10@Z; CloudPrint::ImpersonateClientRAII::ImpersonateClientRAII(long (*)(void *),long (*)(void *),void *)
0x180014675  mov     rcx, rbx
0x180014678  call    ?GetUserSid@TokenHelpers@PrintCore@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::TokenHelpers::GetUserSid(std::wstring &)
0x18001467d  mov     ebx, eax
0x18001467f  test    eax, eax
0x180014681  jns     short loc_180014699
0x180014683  mov     r8d, eax
0x180014686  lea     rdx, aCouldnTGetUser_0; "Couldn't get User SID. hr=%#x"
0x18001468d  lea     rcx, aCloudprintClou_13; "CloudPrint::CloudPrintHelper::GetCurren"...
0x180014694  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180014699  lea     rcx, [rsp+48h+var_28]; this
0x18001469e  call    ??1ImpersonateClientRAII@CloudPrint@@QEAA@XZ; CloudPrint::ImpersonateClientRAII::~ImpersonateClientRAII(void)
0x1800146a3  mov     eax, ebx
0x1800146a5  jmp     short loc_1800146AB
0x1800146a7  mov     eax, [rsp+48h+arg_0]
0x1800146ab  add     rsp, 40h
0x1800146af  pop     rbx
0x1800146b0  retn
```
