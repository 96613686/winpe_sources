# BrainSettings::InitBool(web::json::value const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)

- ea: `0x180035fe0`
- end: `0x18003612e`
- name: `?InitBool@BrainSettings@@CA_NAEBVvalue@json@web@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z`
- size: `334`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180038884`

## callees

- `0x180029984`
- `0x180035fe0`
- `0x18003d580`
- `0x18003d5e0`
- `0x1800427d0`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
char __fastcall BrainSettings::InitBool(_QWORD *a1, __int64 a2)
{
  __int64 v2; // rbx
  char result; // al
  wchar_t *v5; // rax
  const wchar_t *v6; // r8
  char v7; // bl
  char v8; // [rsp+30h] [rbp-28h]
  __int64 v10; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = a2;
  v8 = 0;
  result = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 8LL))(*a1);
  if ( result )
  {
    v10 = 0;
    v5 = web::json::value::at(a1, v2);
    (***(void (__fastcall ****)(_QWORD, __int64 *))v5)(*(_QWORD *)v5, &v10);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v10 + 88LL))(v10) == 1 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 136LL))(v10);
      if ( v10 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 192LL))(v10, 1);
      return v7;
    }
    else
    {
      v6 = (const wchar_t *)v2;
      if ( *(_QWORD *)(v2 + 24) > 7u )
        v6 = *(const wchar_t **)v2;
      uus::UndockedUpdateTelemetry::UusOneSettingsParseFailure((const wchar_t *)"Expected type bool:", -2147024883, v6);
      if ( *(_QWORD *)(v2 + 24) > 7u )
        v2 = *(_QWORD *)v2;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x80,
        (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\BrainSettings.hpp",
        (const char *)0x8007000DLL,
        (int)"Expected type bool: %s",
        (const char *)v2,
        v8,
        a2);
      if ( v10 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 192LL))(v10, 1);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180035fe0  mov     [rsp+arg_10], rbx
0x180035fe5  push    rdi
0x180035fe6  sub     rsp, 50h
0x180035fea  mov     rax, cs:__security_cookie
0x180035ff1  xor     rax, rsp
0x180035ff4  mov     [rsp+58h+var_10], rax
0x180035ff9  mov     rbx, rdx
0x180035ffc  mov     rdi, rcx
0x180035fff  mov     [rsp+58h+var_20], rdx
0x180036004  mov     [rsp+58h+var_28], 0
0x180036009  mov     rcx, [rcx]
0x18003600c  mov     rax, [rcx]
0x18003600f  mov     rax, [rax+8]
0x180036013  call    _guard_dispatch_icall
0x180036018  test    al, al
0x18003601a  jz      loc_180036115
0x180036020  mov     [rsp+58h+var_18], 0
0x180036029  mov     rdx, rbx
0x18003602c  mov     rcx, rdi
0x18003602f  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180036034  mov     rcx, [rax]
0x180036037  mov     rax, [rcx]
0x18003603a  lea     rdx, [rsp+58h+var_18]
0x18003603f  mov     rax, [rax]
0x180036042  call    _guard_dispatch_icall
0x180036047  nop
0x180036048  mov     rcx, [rsp+58h+var_18]
0x18003604d  mov     rax, [rcx]
0x180036050  mov     rax, [rax+58h]
0x180036054  call    _guard_dispatch_icall
0x180036059  mov     edi, 1
0x18003605e  cmp     eax, edi
0x180036060  jz      short loc_1800360D7
0x180036062  mov     r8, rbx
0x180036065  cmp     qword ptr [rbx+18h], 7
0x18003606a  jbe     short loc_18003606F
0x18003606c  mov     r8, [rbx]; wchar_t *
0x18003606f  mov     edx, 8007000Dh; int
0x180036074  lea     rcx, aExpectedTypeBo; "Expected type bool:"
0x18003607b  call    ?UusOneSettingsParseFailure@UndockedUpdateTelemetry@uus@@SAXPEBDJPEB_W@Z; uus::UndockedUpdateTelemetry::UusOneSettingsParseFailure(char const *,long,wchar_t const *)
0x180036080  cmp     qword ptr [rbx+18h], 7
0x180036085  jbe     short loc_18003608A
0x180036087  mov     rbx, [rbx]
0x18003608a  mov     rcx, [rsp+58h]; this
0x18003608f  mov     [rsp+58h+var_30], rbx; char *
0x180036094  lea     rax, aExpectedTypeBo_0; "Expected type bool: %s"
0x18003609b  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800360a0  mov     r9d, 8007000Dh; char *
0x1800360a6  lea     r8, aCW1SSrcBrainLi_1; "C:\\__w\\1\\s\\src\\brain\\lib\\BrainSe"...
0x1800360ad  mov     edx, 80h; void *
0x1800360b2  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800360b7  nop
0x1800360b8  mov     rcx, [rsp+58h+var_18]
0x1800360bd  test    rcx, rcx
0x1800360c0  jz      short loc_1800360D3
0x1800360c2  mov     rax, [rcx]
0x1800360c5  mov     edx, edi
0x1800360c7  mov     rax, [rax+0C0h]
0x1800360ce  call    _guard_dispatch_icall
0x1800360d3  xor     al, al
0x1800360d5  jmp     short loc_180036115
0x1800360d7  mov     rcx, [rsp+58h+var_18]
0x1800360dc  mov     rax, [rcx]
0x1800360df  mov     rax, [rax+88h]
0x1800360e6  call    _guard_dispatch_icall
0x1800360eb  mov     bl, al
0x1800360ed  mov     [rsp+58h+var_28], al
0x1800360f1  mov     rcx, [rsp+58h+var_18]
0x1800360f6  test    rcx, rcx
0x1800360f9  jz      short loc_18003610D
0x1800360fb  mov     rax, [rcx]
0x1800360fe  mov     edx, edi
0x180036100  mov     rax, [rax+0C0h]
0x180036107  call    _guard_dispatch_icall
0x18003610c  nop
0x18003610d  jmp     short loc_180036113
0x18003610f  mov     bl, [rsp+58h+var_28]
0x180036113  mov     al, bl
0x180036115  mov     rcx, [rsp+58h+var_10]
0x18003611a  xor     rcx, rsp; StackCookie
0x18003611d  call    __security_check_cookie
0x180036122  mov     rbx, [rsp+58h+arg_10]
0x180036127  add     rsp, 50h
0x18003612b  pop     rdi
0x18003612c  retn
```
