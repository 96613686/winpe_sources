# FwServiceRestriction::Initialize(void)

- ea: `0x180017aa8`
- end: `0x180017bd4`
- name: `?Initialize@FwServiceRestriction@@AEAAJXZ`
- size: `300`
- prototype: `__int64 __fastcall(FwServiceRestriction *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001791c`

## callees

- `0x180017aa8`
- `0x180017d8c`
- `0x18003104c`
- `0x18005e010`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180017b3d`
- `fwbase!FwReportReturnError` at `0x180017b52`
- `fwbase!FwReportReturnError` at `0x180017b61`
- `fwbase!FwReportReturnError` at `0x180017baf`
- `fwbase!FwReportReturnError` at `0x180017b3d`
- `fwbase!FwReportReturnError` at `0x180017b52`
- `fwbase!FwReportReturnError` at `0x180017b61`
- `fwbase!FwReportReturnError` at `0x180017baf`

## string_xrefs

- `0x180017b36`: `FwRules::CreateInstance`
- `0x180017ba8`: `FwRules::CreateInstance`
- `0x180017b4b`: `FwServiceRestriction::Initialize`
- `0x180017b5a`: `FwServiceRestriction::Initialize`

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
0x180017aa8  mov     [rsp+arg_8], rbx
0x180017aad  push    rdi
0x180017aae  sub     rsp, 20h
0x180017ab2  mov     rdi, rcx
0x180017ab5  mov     rcx, cs:WPP_GLOBAL_Control
0x180017abc  lea     rbx, WPP_GLOBAL_Control
0x180017ac3  cmp     rcx, rbx
0x180017ac6  jz      short loc_180017AD2
0x180017ac8  test    byte ptr [rcx+1Ch], 8
0x180017acc  jnz     loc_180017B6B
0x180017ad2  mov     [rsp+28h+arg_0], 0
0x180017adb  cmp     rcx, rbx
0x180017ade  jz      short loc_180017AEA
0x180017ae0  test    byte ptr [rcx+1Ch], 8
0x180017ae4  jnz     loc_180017B8C
0x180017aea  lea     rcx, [rsp+28h+arg_0]
0x180017aef  mov     qword ptr [rdi+20h], 0
0x180017af7  call    ?CreateInstance@?$CComObject@VFwRules@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<FwRules>::CreateInstance(ATL::CComObject<FwRules> * *)
0x180017afc  mov     ebx, eax
0x180017afe  test    eax, eax
0x180017b00  js      loc_180017BA6
0x180017b06  mov     rbx, [rsp+28h+arg_0]
0x180017b0b  mov     rcx, rbx
0x180017b0e  mov     rax, [rbx]
0x180017b11  mov     rax, [rax+8]
0x180017b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b1a  mov     dword ptr [rbx+18h], 3
0x180017b21  mov     [rdi+20h], rbx
0x180017b25  xor     ebx, ebx
0x180017b27  mov     eax, ebx
0x180017b29  mov     rbx, [rsp+28h+arg_8]
0x180017b2e  add     rsp, 20h
0x180017b32  pop     rdi
0x180017b33  retn
0x180017b34  mov     edx, ebx
0x180017b36  lea     rcx, aFwrulesCreatei; "FwRules::CreateInstance"
0x180017b3d  call    cs:__imp_FwReportReturnError
0x180017b43  mov     ebx, eax
0x180017b45  test    eax, eax
0x180017b47  jns     short loc_180017B27
0x180017b49  mov     edx, eax
0x180017b4b  lea     rcx, aFwservicerestr; "FwServiceRestriction::Initialize"
0x180017b52  call    cs:__imp_FwReportReturnError
0x180017b58  mov     edx, ebx
0x180017b5a  lea     rcx, aFwservicerestr; "FwServiceRestriction::Initialize"
0x180017b61  call    cs:__imp_FwReportReturnError
0x180017b67  mov     ebx, eax
0x180017b69  jmp     short loc_180017B27
0x180017b6b  mov     rcx, [rcx+10h]
0x180017b6f  lea     r8, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids
0x180017b76  mov     edx, 22h ; '"'
0x180017b7b  call    WPP_SF_
0x180017b80  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b87  jmp     loc_180017AD2
0x180017b8c  mov     rcx, [rcx+10h]
0x180017b90  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x180017b97  mov     edx, 13h
0x180017b9c  call    WPP_SF_
0x180017ba1  jmp     loc_180017AEA
0x180017ba6  mov     edx, ebx
0x180017ba8  lea     rcx, aFwrulesCreatei; "FwRules::CreateInstance"
0x180017baf  call    cs:__imp_FwReportReturnError
0x180017bb5  mov     rcx, [rsp+28h+arg_0]
0x180017bba  test    rcx, rcx
0x180017bbd  jz      loc_180017B34
0x180017bc3  mov     rdx, [rcx]
0x180017bc6  mov     rax, [rdx+10h]
0x180017bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bcf  jmp     loc_180017B34
```
