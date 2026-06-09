# UpdateLoginTask(bool,ulong)

- ea: `0x1800338b4`
- end: `0x180033aea`
- name: `?UpdateLoginTask@@YAX_NK@Z`
- size: `566`
- prototype: `void __fastcall(unsigned __int8)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x18002f800`
- `0x18002fb4c`

## callees

- `0x18002008c`
- `0x18003331c`
- `0x180033474`
- `0x180033520`
- `0x180033650`
- `0x1800338b4`
- `0x18004f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180033989`
- `OLEAUT32!__imp_SysFreeString` at `0x180033989`

## string_xrefs

- `0x180033a98`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x180033aad`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x180033ac2`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x180033ad7`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`

## pseudocode

```c
void __fastcall UpdateLoginTask(unsigned __int8 a1)
{
  int v2; // eax
  int v3; // eax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD); // rsi
  _QWORD *TimeInFuture; // rax
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  const char *v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rcx
  OLECHAR *v13; // rcx
  OLECHAR *v14; // [rsp+20h] [rbp-28h] BYREF
  __int64 v15; // [rsp+28h] [rbp-20h] BYREF
  __int64 v16; // [rsp+30h] [rbp-18h] BYREF
  BSTR bstrString[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v19; // [rsp+60h] [rbp+18h] BYREF
  __int64 v20; // [rsp+68h] [rbp+20h] BYREF

  try
  {
    GetPTITaskFolder(&v14);
    v20 = 0;
    v2 = (*(__int64 (__fastcall **)(OLECHAR *, const wchar_t *, __int64 *))(*(_QWORD *)v14 + 104LL))(
           v14,
           L"LoginCheck",
           &v20);
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
        (const char *)(unsigned int)v2,
        (int)v14);
    v19 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 152LL))(v20, &v19);
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
        (const char *)(unsigned int)v3,
        (int)v14);
    if ( a1 )
    {
      GetTriggerForTask(&v15, &v19);
      v4 = v15;
      v5 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 136LL);
      TimeInFuture = (_QWORD *)GetTimeInFuture(bstrString);
      v7 = v5(v4, *TimeInFuture);
      if ( v7 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x64,
          (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
          (const char *)(unsigned int)v7,
          (int)v14);
      if ( bstrString[0] )
        SysFreeString(bstrString[0]);
      v16 = v19;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
      bstrString[0] = v14;
      if ( v14 )
        (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v14 + 8LL))(v14);
      ModifyTaskDefinition(bstrString, L"LoginCheck", &v16);
      v8 = v15;
      if ( v15 )
      {
        v15 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 88LL))(v20, (unsigned __int16)((a1 ^ 1) - 1));
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
        (const char *)(unsigned int)v9,
        (int)v14);
    v11 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v13 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
      v10);
  }
}

```

## disassembly

```asm
0x1800338b4  mov     [rsp+arg_0], rbx
0x1800338b9  mov     [rsp+arg_8], rsi
0x1800338be  push    rdi
0x1800338bf  sub     rsp, 40h
0x1800338c3  mov     bl, cl
0x1800338c5  lea     rcx, [rsp+48h+var_28]
0x1800338ca  call    ?GetPTITaskFolder@@YA?AV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@XZ; GetPTITaskFolder(void)
0x1800338cf  nop
0x1800338d0  mov     [rsp+48h+arg_18], 0
0x1800338d9  mov     rcx, [rsp+48h+var_28]
0x1800338de  mov     rax, [rcx]
0x1800338e1  lea     r8, [rsp+48h+arg_18]
0x1800338e6  lea     rdx, aLogincheck; "LoginCheck"
0x1800338ed  mov     rax, [rax+68h]
0x1800338f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338f6  mov     rcx, [rsp+48h]; this
0x1800338fb  test    eax, eax
0x1800338fd  js      loc_180033A95
0x180033903  mov     [rsp+48h+arg_10], 0
0x18003390c  mov     rcx, [rsp+48h+arg_18]
0x180033911  mov     rax, [rcx]
0x180033914  lea     rdx, [rsp+48h+arg_10]
0x180033919  mov     rax, [rax+98h]
0x180033920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033925  mov     rcx, [rsp+48h]; this
0x18003392a  test    eax, eax
0x18003392c  js      loc_180033AAA
0x180033932  test    bl, bl
0x180033934  jz      loc_1800339FE
0x18003393a  lea     rdx, [rsp+48h+arg_10]
0x18003393f  lea     rcx, [rsp+48h+var_20]
0x180033944  call    ?GetTriggerForTask@@YA?AV?$ComPtr@UITrigger@@@WRL@Microsoft@@AEAV?$ComPtr@UITaskDefinition@@@23@@Z; GetTriggerForTask(Microsoft::WRL::ComPtr<ITaskDefinition> &)
0x180033949  nop
0x18003394a  mov     rdi, [rsp+48h+var_20]
0x18003394f  mov     rax, [rdi]
0x180033952  mov     rsi, [rax+88h]
0x180033959  lea     rcx, [rsp+48h+bstrString]
0x18003395e  call    ?GetTimeInFuture@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; GetTimeInFuture(ulong)
0x180033963  nop
0x180033964  mov     rdx, [rax]
0x180033967  mov     rcx, rdi
0x18003396a  mov     rax, rsi
0x18003396d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033972  mov     rcx, [rsp+48h]; this
0x180033977  test    eax, eax
0x180033979  js      loc_180033ABF
0x18003397f  mov     rcx, [rsp+48h+bstrString]; bstrString
0x180033984  test    rcx, rcx
0x180033987  jz      short loc_18003398F
0x180033989  call    cs:__imp_SysFreeString
0x18003398f  mov     rcx, [rsp+48h+arg_10]
0x180033994  mov     [rsp+48h+var_18], rcx
0x180033999  test    rcx, rcx
0x18003399c  jz      short loc_1800339AB
0x18003399e  mov     rax, [rcx]
0x1800339a1  mov     rax, [rax+8]
0x1800339a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339aa  nop
0x1800339ab  mov     rcx, [rsp+48h+var_28]
0x1800339b0  mov     [rsp+48h+bstrString], rcx
0x1800339b5  test    rcx, rcx
0x1800339b8  jz      short loc_1800339C7
0x1800339ba  mov     rax, [rcx]
0x1800339bd  mov     rax, [rax+8]
0x1800339c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339c6  nop
0x1800339c7  lea     r8, [rsp+48h+var_18]
0x1800339cc  lea     rdx, aLogincheck; "LoginCheck"
0x1800339d3  lea     rcx, [rsp+48h+bstrString]
0x1800339d8  call    ?ModifyTaskDefinition@@YAXV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@PEBGV?$ComPtr@UITaskDefinition@@@23@@Z; ModifyTaskDefinition(Microsoft::WRL::ComPtr<ITaskFolder>,ushort const *,Microsoft::WRL::ComPtr<ITaskDefinition>)
0x1800339dd  nop
0x1800339de  mov     rcx, [rsp+48h+var_20]
0x1800339e3  test    rcx, rcx
0x1800339e6  jz      short loc_1800339FE
0x1800339e8  mov     [rsp+48h+var_20], 0
0x1800339f1  mov     rax, [rcx]
0x1800339f4  mov     rax, [rax+10h]
0x1800339f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339fd  nop
0x1800339fe  mov     rcx, [rsp+48h+arg_18]
0x180033a03  mov     rax, [rcx]
0x180033a06  xor     bl, 1
0x180033a09  movzx   edx, bl
0x180033a0c  dec     dx
0x180033a0f  mov     rax, [rax+58h]
0x180033a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a18  mov     rcx, [rsp+48h]; this
0x180033a1d  test    eax, eax
0x180033a1f  js      loc_180033AD4
0x180033a25  mov     rcx, [rsp+48h+arg_10]
0x180033a2a  test    rcx, rcx
0x180033a2d  jz      short loc_180033A45
0x180033a2f  mov     [rsp+48h+arg_10], 0
0x180033a38  mov     rax, [rcx]
0x180033a3b  mov     rax, [rax+10h]
0x180033a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a44  nop
0x180033a45  mov     rcx, [rsp+48h+arg_18]
0x180033a4a  test    rcx, rcx
0x180033a4d  jz      short loc_180033A65
0x180033a4f  mov     [rsp+48h+arg_18], 0
0x180033a58  mov     rax, [rcx]
0x180033a5b  mov     rax, [rax+10h]
0x180033a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a64  nop
0x180033a65  mov     rcx, [rsp+48h+var_28]
0x180033a6a  test    rcx, rcx
0x180033a6d  jz      short loc_180033A85
0x180033a6f  mov     [rsp+48h+var_28], 0
0x180033a78  mov     rax, [rcx]
0x180033a7b  mov     rax, [rax+10h]
0x180033a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a84  nop
0x180033a85  mov     rbx, [rsp+48h+arg_0]
0x180033a8a  mov     rsi, [rsp+48h+arg_8]
0x180033a8f  add     rsp, 40h
0x180033a93  pop     rdi
0x180033a94  retn
0x180033a95  mov     r9d, eax; char *
0x180033a98  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033a9f  mov     edx, 59h ; 'Y'; void *
0x180033aa4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033aaa  mov     r9d, eax; char *
0x180033aad  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033ab4  mov     edx, 5Ch ; '\'; void *
0x180033ab9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033abf  mov     r9d, eax; char *
0x180033ac2  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033ac9  mov     edx, 64h ; 'd'; void *
0x180033ace  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033ad4  mov     r9d, eax; char *
0x180033ad7  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033ade  mov     edx, 69h ; 'i'; void *
0x180033ae3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
