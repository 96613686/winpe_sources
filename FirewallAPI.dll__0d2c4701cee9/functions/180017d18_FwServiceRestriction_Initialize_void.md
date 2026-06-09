# FwServiceRestriction::Initialize(void)

- ea: `0x180017d18`
- end: `0x180017e5d`
- name: `?Initialize@FwServiceRestriction@@AEAAJXZ`
- size: `325`
- prototype: `__int64 __fastcall(FwServiceRestriction *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017b80`

## callees

- `0x180017d18`
- `0x18001803c`
- `0x18003336c`
- `0x180062010`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180017dae`
- `fwbase!FwReportReturnError` at `0x180017dc9`
- `fwbase!FwReportReturnError` at `0x180017dde`
- `fwbase!FwReportReturnError` at `0x180017e32`
- `fwbase!FwReportReturnError` at `0x180017dae`
- `fwbase!FwReportReturnError` at `0x180017dc9`
- `fwbase!FwReportReturnError` at `0x180017dde`
- `fwbase!FwReportReturnError` at `0x180017e32`

## string_xrefs

- `0x180017da7`: `FwRules::CreateInstance`
- `0x180017e2b`: `FwRules::CreateInstance`
- `0x180017dc2`: `FwServiceRestriction::Initialize`
- `0x180017dd7`: `FwServiceRestriction::Initialize`

## pseudocode

```c
__int64 __fastcall FwServiceRestriction::Initialize(FwServiceRestriction *this)
{
  FwPolicy2 *v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rbx
  unsigned int v6; // ebx
  int v8; // eax
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v9 = 0;
  if ( v2 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v2 + 2), 19, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids);
  *((_QWORD *)this + 4) = 0;
  v3 = ATL::CComObject<FwRules>::CreateInstance(&v9);
  v4 = v3;
  if ( v3 < 0 )
  {
    FwReportReturnError("FwRules::CreateInstance", (unsigned int)v3);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v8 = FwReportReturnError("FwRules::CreateInstance", v4);
    v6 = v8;
    if ( v8 < 0 )
    {
      FwReportReturnError("FwServiceRestriction::Initialize", (unsigned int)v8);
      return (unsigned int)FwReportReturnError("FwServiceRestriction::Initialize", v6);
    }
  }
  else
  {
    v5 = v9;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    *(_DWORD *)(v5 + 24) = 3;
    *((_QWORD *)this + 4) = v5;
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180017d18  mov     [rsp+arg_8], rbx
0x180017d1d  push    rdi
0x180017d1e  sub     rsp, 20h
0x180017d22  mov     rdi, rcx
0x180017d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d2c  lea     rbx, WPP_GLOBAL_Control
0x180017d33  cmp     rcx, rbx
0x180017d36  jz      short loc_180017D42
0x180017d38  test    byte ptr [rcx+1Ch], 8
0x180017d3c  jnz     loc_180017DEE
0x180017d42  mov     [rsp+28h+arg_0], 0
0x180017d4b  cmp     rcx, rbx
0x180017d4e  jz      short loc_180017D5A
0x180017d50  test    byte ptr [rcx+1Ch], 8
0x180017d54  jnz     loc_180017E0F
0x180017d5a  lea     rcx, [rsp+28h+arg_0]
0x180017d5f  mov     qword ptr [rdi+20h], 0
0x180017d67  call    ?CreateInstance@?$CComObject@VFwRules@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<FwRules>::CreateInstance(ATL::CComObject<FwRules> * *)
0x180017d6c  mov     ebx, eax
0x180017d6e  test    eax, eax
0x180017d70  js      loc_180017E29
0x180017d76  mov     rbx, [rsp+28h+arg_0]
0x180017d7b  mov     rcx, rbx
0x180017d7e  mov     rax, [rbx]
0x180017d81  mov     rax, [rax+8]
0x180017d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d8a  mov     dword ptr [rbx+18h], 3
0x180017d91  mov     [rdi+20h], rbx
0x180017d95  xor     ebx, ebx
0x180017d97  mov     eax, ebx
0x180017d99  mov     rbx, [rsp+28h+arg_8]
0x180017d9e  add     rsp, 20h
0x180017da2  pop     rdi
0x180017da3  retn
0x180017da5  mov     edx, ebx
0x180017da7  lea     rcx, aFwrulesCreatei; "FwRules::CreateInstance"
0x180017dae  call    cs:__imp_FwReportReturnError
0x180017db5  nop     dword ptr [rax+rax+00h]
0x180017dba  mov     ebx, eax
0x180017dbc  test    eax, eax
0x180017dbe  jns     short loc_180017D97
0x180017dc0  mov     edx, eax
0x180017dc2  lea     rcx, aFwservicerestr; "FwServiceRestriction::Initialize"
0x180017dc9  call    cs:__imp_FwReportReturnError
0x180017dd0  nop     dword ptr [rax+rax+00h]
0x180017dd5  mov     edx, ebx
0x180017dd7  lea     rcx, aFwservicerestr; "FwServiceRestriction::Initialize"
0x180017dde  call    cs:__imp_FwReportReturnError
0x180017de5  nop     dword ptr [rax+rax+00h]
0x180017dea  mov     ebx, eax
0x180017dec  jmp     short loc_180017D97
0x180017dee  mov     rcx, [rcx+10h]
0x180017df2  lea     r8, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids
0x180017df9  mov     edx, 22h ; '"'
0x180017dfe  call    WPP_SF_
0x180017e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e0a  jmp     loc_180017D42
0x180017e0f  mov     rcx, [rcx+10h]
0x180017e13  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x180017e1a  mov     edx, 13h
0x180017e1f  call    WPP_SF_
0x180017e24  jmp     loc_180017D5A
0x180017e29  mov     edx, ebx
0x180017e2b  lea     rcx, aFwrulesCreatei; "FwRules::CreateInstance"
0x180017e32  call    cs:__imp_FwReportReturnError
0x180017e39  nop     dword ptr [rax+rax+00h]
0x180017e3e  mov     rcx, [rsp+28h+arg_0]
0x180017e43  test    rcx, rcx
0x180017e46  jz      loc_180017DA5
0x180017e4c  mov     rdx, [rcx]
0x180017e4f  mov     rax, [rdx+10h]
0x180017e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e58  jmp     loc_180017DA5
```
