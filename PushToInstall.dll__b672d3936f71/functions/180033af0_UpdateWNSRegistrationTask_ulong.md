# UpdateWNSRegistrationTask(ulong)

- ea: `0x180033af0`
- end: `0x180033e30`
- name: `?UpdateWNSRegistrationTask@@YAXK@Z`
- size: `832`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x18002fd70`
- `0x18004d3c2`

## callees

- `0x1800026b0`
- `0x1800115fc`
- `0x18002008c`
- `0x18003331c`
- `0x180033520`
- `0x180033650`
- `0x1800337e8`
- `0x180033af0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180033c42`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180033c42`
- `OLEAUT32!__imp_SysFreeString` at `0x180033c8c`
- `OLEAUT32!__imp_SysFreeString` at `0x180033c8c`

## string_xrefs

- `0x180033da2`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x180033db7`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x180033dcc`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x180033de0`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x180033df4`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x180033e08`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x180033e1d`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall UpdateWNSRegistrationTask(unsigned int a1)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, _QWORD); // rdi
  _QWORD *v10; // rax
  int v11; // eax
  const char *v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  OLECHAR *v17; // rcx
  BSTR bstrString; // [rsp+20h] [rbp-68h] BYREF
  __int64 v19; // [rsp+28h] [rbp-60h] BYREF
  __int64 v20; // [rsp+30h] [rbp-58h] BYREF
  __int64 v21; // [rsp+38h] [rbp-50h] BYREF
  __int64 v22; // [rsp+40h] [rbp-48h] BYREF
  OLECHAR *v23; // [rsp+48h] [rbp-40h] BYREF
  __int64 v24; // [rsp+50h] [rbp-38h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-30h] BYREF
  unsigned __int16 v26[8]; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  try
  {
    GetPTITaskFolder(&v23);
    v22 = 0;
    v2 = (*(__int64 (__fastcall **)(OLECHAR *, const wchar_t *, __int64 *))(*(_QWORD *)v23 + 104LL))(
           v23,
           L"Registration",
           &v22);
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
        (const char *)(unsigned int)v2,
        (int)bstrString);
    v21 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 152LL))(v22, &v21);
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
        (const char *)(unsigned int)v3,
        (int)bstrString);
    GetTriggerForTask(&v20, &v21);
    v19 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 80LL))(v20, &v19);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
        (const char *)(unsigned int)v4,
        (int)bstrString);
    v5 = StringCchPrintfW(v26, 5u, L"P%dD", a1);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
        (const char *)(unsigned int)v5,
        (int)bstrString);
    v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v19 + 64LL))(v19, v26);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7F,
        (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
        (const char *)(unsigned int)v6,
        (int)bstrString);
    v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 88LL))(v20, v19);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
        (const char *)(unsigned int)v7,
        (int)bstrString);
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    v8 = v20;
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 120LL);
    v10 = (_QWORD *)SystemTimeToBstr(&bstrString, &SystemTime);
    v11 = v9(v8, *v10);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
        (const char *)(unsigned int)v11,
        (int)bstrString);
    if ( bstrString )
      SysFreeString(bstrString);
    v24 = v21;
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    bstrString = v23;
    if ( v23 )
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v23 + 8LL))(v23);
    ModifyTaskDefinition((__int64 *)&bstrString, (__int64)L"Registration", &v24);
    v13 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
      v12);
  }
}

```

## disassembly

```asm
0x180033af0  mov     [rsp+arg_8], rbx
0x180033af5  push    rdi
0x180033af6  sub     rsp, 80h
0x180033afd  mov     rax, cs:__security_cookie
0x180033b04  xor     rax, rsp
0x180033b07  mov     [rsp+88h+var_10], rax
0x180033b0c  mov     ebx, ecx
0x180033b0e  lea     rcx, [rsp+88h+var_40]
0x180033b13  call    ?GetPTITaskFolder@@YA?AV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@XZ; GetPTITaskFolder(void)
0x180033b18  nop
0x180033b19  mov     [rsp+88h+var_48], 0
0x180033b22  mov     rcx, [rsp+88h+var_40]
0x180033b27  mov     rax, [rcx]
0x180033b2a  lea     r8, [rsp+88h+var_48]
0x180033b2f  lea     rdx, aRegistration_0; "Registration"
0x180033b36  mov     rax, [rax+68h]
0x180033b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b3f  mov     rcx, [rsp+88h]; this
0x180033b47  test    eax, eax
0x180033b49  js      loc_180033D9F
0x180033b4f  mov     [rsp+88h+var_50], 0
0x180033b58  mov     rcx, [rsp+88h+var_48]
0x180033b5d  mov     rax, [rcx]
0x180033b60  lea     rdx, [rsp+88h+var_50]
0x180033b65  mov     rax, [rax+98h]
0x180033b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b71  mov     rcx, [rsp+88h]; this
0x180033b79  test    eax, eax
0x180033b7b  js      loc_180033DB4
0x180033b81  lea     rdx, [rsp+88h+var_50]
0x180033b86  lea     rcx, [rsp+88h+var_58]
0x180033b8b  call    ?GetTriggerForTask@@YA?AV?$ComPtr@UITrigger@@@WRL@Microsoft@@AEAV?$ComPtr@UITaskDefinition@@@23@@Z; GetTriggerForTask(Microsoft::WRL::ComPtr<ITaskDefinition> &)
0x180033b90  nop
0x180033b91  mov     [rsp+88h+var_60], 0
0x180033b9a  mov     rcx, [rsp+88h+var_58]
0x180033b9f  mov     rax, [rcx]
0x180033ba2  lea     rdx, [rsp+88h+var_60]
0x180033ba7  mov     rax, [rax+50h]
0x180033bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bb0  mov     rcx, [rsp+88h]; this
0x180033bb8  test    eax, eax
0x180033bba  js      loc_180033DC9
0x180033bc0  mov     r9d, ebx
0x180033bc3  lea     r8, aPDd; "P%dD"
0x180033bca  mov     edx, 5; unsigned __int64
0x180033bcf  lea     rcx, [rsp+88h+var_20]; unsigned __int16 *
0x180033bd4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033bd9  mov     rcx, [rsp+88h]; this
0x180033be1  test    eax, eax
0x180033be3  js      loc_180033DDD
0x180033be9  mov     rcx, [rsp+88h+var_60]
0x180033bee  mov     rax, [rcx]
0x180033bf1  lea     rdx, [rsp+88h+var_20]
0x180033bf6  mov     rax, [rax+40h]
0x180033bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bff  mov     rcx, [rsp+88h]; this
0x180033c07  test    eax, eax
0x180033c09  js      loc_180033DF1
0x180033c0f  mov     rcx, [rsp+88h+var_58]
0x180033c14  mov     rax, [rcx]
0x180033c17  mov     rdx, [rsp+88h+var_60]
0x180033c1c  mov     rax, [rax+58h]
0x180033c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c25  mov     rcx, [rsp+88h]; this
0x180033c2d  test    eax, eax
0x180033c2f  js      loc_180033E05
0x180033c35  xorps   xmm0, xmm0
0x180033c38  movups  xmmword ptr [rsp+88h+SystemTime.wYear], xmm0
0x180033c3d  lea     rcx, [rsp+88h+SystemTime]; lpSystemTime
0x180033c42  call    cs:__imp_GetLocalTime
0x180033c48  mov     rbx, [rsp+88h+var_58]
0x180033c4d  mov     rax, [rbx]
0x180033c50  mov     rdi, [rax+78h]
0x180033c54  lea     rdx, [rsp+88h+SystemTime]
0x180033c59  lea     rcx, [rsp+88h+bstrString]
0x180033c5e  call    ?SystemTimeToBstr@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_SYSTEMTIME@@@Z; SystemTimeToBstr(_SYSTEMTIME &)
0x180033c63  nop
0x180033c64  mov     rdx, [rax]
0x180033c67  mov     rcx, rbx
0x180033c6a  mov     rax, rdi
0x180033c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c72  mov     rcx, [rsp+88h]; this
0x180033c7a  test    eax, eax
0x180033c7c  js      loc_180033E1A
0x180033c82  mov     rcx, [rsp+88h+bstrString]; bstrString
0x180033c87  test    rcx, rcx
0x180033c8a  jz      short loc_180033C92
0x180033c8c  call    cs:__imp_SysFreeString
0x180033c92  mov     rcx, [rsp+88h+var_50]
0x180033c97  mov     [rsp+88h+var_38], rcx
0x180033c9c  test    rcx, rcx
0x180033c9f  jz      short loc_180033CAE
0x180033ca1  mov     rax, [rcx]
0x180033ca4  mov     rax, [rax+8]
0x180033ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cad  nop
0x180033cae  mov     rcx, [rsp+88h+var_40]
0x180033cb3  mov     [rsp+88h+bstrString], rcx
0x180033cb8  test    rcx, rcx
0x180033cbb  jz      short loc_180033CCA
0x180033cbd  mov     rax, [rcx]
0x180033cc0  mov     rax, [rax+8]
0x180033cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cc9  nop
0x180033cca  lea     r8, [rsp+88h+var_38]
0x180033ccf  lea     rdx, aRegistration_0; "Registration"
0x180033cd6  lea     rcx, [rsp+88h+bstrString]
0x180033cdb  call    ?ModifyTaskDefinition@@YAXV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@PEBGV?$ComPtr@UITaskDefinition@@@23@@Z; ModifyTaskDefinition(Microsoft::WRL::ComPtr<ITaskFolder>,ushort const *,Microsoft::WRL::ComPtr<ITaskDefinition>)
0x180033ce0  nop
0x180033ce1  mov     rcx, [rsp+88h+var_60]
0x180033ce6  test    rcx, rcx
0x180033ce9  jz      short loc_180033D01
0x180033ceb  mov     [rsp+88h+var_60], 0
0x180033cf4  mov     rax, [rcx]
0x180033cf7  mov     rax, [rax+10h]
0x180033cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d00  nop
0x180033d01  mov     rcx, [rsp+88h+var_58]
0x180033d06  test    rcx, rcx
0x180033d09  jz      short loc_180033D21
0x180033d0b  mov     [rsp+88h+var_58], 0
0x180033d14  mov     rax, [rcx]
0x180033d17  mov     rax, [rax+10h]
0x180033d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d20  nop
0x180033d21  mov     rcx, [rsp+88h+var_50]
0x180033d26  test    rcx, rcx
0x180033d29  jz      short loc_180033D41
0x180033d2b  mov     [rsp+88h+var_50], 0
0x180033d34  mov     rax, [rcx]
0x180033d37  mov     rax, [rax+10h]
0x180033d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d40  nop
0x180033d41  mov     rcx, [rsp+88h+var_48]
0x180033d46  test    rcx, rcx
0x180033d49  jz      short loc_180033D61
0x180033d4b  mov     [rsp+88h+var_48], 0
0x180033d54  mov     rax, [rcx]
0x180033d57  mov     rax, [rax+10h]
0x180033d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d60  nop
0x180033d61  mov     rcx, [rsp+88h+var_40]
0x180033d66  test    rcx, rcx
0x180033d69  jz      short loc_180033D81
0x180033d6b  mov     [rsp+88h+var_40], 0
0x180033d74  mov     rax, [rcx]
0x180033d77  mov     rax, [rax+10h]
0x180033d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d80  nop
0x180033d81  mov     rcx, [rsp+88h+var_10]
0x180033d86  xor     rcx, rsp; StackCookie
0x180033d89  call    __security_check_cookie
0x180033d8e  mov     rbx, [rsp+88h+arg_8]
0x180033d96  add     rsp, 80h
0x180033d9d  pop     rdi
0x180033d9e  retn
0x180033d9f  mov     r9d, eax; char *
0x180033da2  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033da9  mov     edx, 72h ; 'r'; void *
0x180033dae  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033db4  mov     r9d, eax; char *
0x180033db7  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033dbe  mov     edx, 75h ; 'u'; void *
0x180033dc3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033dc9  mov     r9d, eax; char *
0x180033dcc  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033dd3  mov     edx, 7Ah ; 'z'; void *
0x180033dd8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033ddd  mov     r9d, eax; char *
0x180033de0  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033de7  mov     edx, 7Dh ; '}'; void *
0x180033dec  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033df1  mov     r9d, eax; char *
0x180033df4  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033dfb  mov     edx, 7Fh; void *
0x180033e00  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033e05  mov     r9d, eax; char *
0x180033e08  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033e0f  mov     edx, 80h; void *
0x180033e14  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033e1a  mov     r9d, eax; char *
0x180033e1d  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033e24  mov     edx, 87h; void *
0x180033e29  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
