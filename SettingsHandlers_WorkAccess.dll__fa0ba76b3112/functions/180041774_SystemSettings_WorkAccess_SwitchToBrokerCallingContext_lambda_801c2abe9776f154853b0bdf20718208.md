# SystemSettings::WorkAccess::SwitchToBrokerCallingContext__lambda_801c2abe9776f154853b0bdf20718208___

- ea: `0x180041774`
- end: `0x18004186b`
- name: `SystemSettings::WorkAccess::SwitchToBrokerCallingContext__lambda_801c2abe9776f154853b0bdf20718208___`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800419b0`

## callees

- `0x1800096ec`
- `0x180041774`
- `0x1800418a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180041795`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180041804`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x18004182f`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180041795`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180041804`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x18004182f`

## string_xrefs

- `0x1800417af`: `shellcommon\shell\settingshandlers\workaccess\lib\SharedHelpers.h`
- `0x1800417e2`: `shellcommon\shell\settingshandlers\workaccess\lib\SharedHelpers.h`
- `0x180041847`: `shellcommon\shell\settingshandlers\workaccess\lib\SharedHelpers.h`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::SwitchToBrokerCallingContext__lambda_801c2abe9776f154853b0bdf20718208___(
        __int64 a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  unsigned __int64 v4; // r9
  __int64 v5; // rdx
  IUnknown *v7; // rdi
  int v8; // eax
  HRESULT v9; // eax
  HRESULT v10; // eax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  IUnknown *pNewObject; // [rsp+38h] [rbp+10h] BYREF
  IUnknown *ppOldObject; // [rsp+40h] [rbp+18h] BYREF

  pNewObject = 0;
  v2 = CoSwitchCallContext(0, &pNewObject);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = (unsigned int)v2;
    v5 = 55;
    goto LABEL_3;
  }
  v7 = pNewObject;
  v8 = lambda_801c2abe9776f154853b0bdf20718208_::operator()(a1);
  v3 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\SharedHelpers.h",
      (const char *)(unsigned int)v8,
      v11);
    ppOldObject = 0;
    v9 = CoSwitchCallContext(v7, &ppOldObject);
    if ( v9 >= 0 )
      return v3;
    v4 = (unsigned int)v9;
    v5 = 61;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\SharedHelpers.h",
      (const char *)v4,
      v11);
    return v3;
  }
  ppOldObject = 0;
  v10 = CoSwitchCallContext(v7, &ppOldObject);
  if ( v10 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\SharedHelpers.h",
      (const char *)(unsigned int)v10,
      v11);
  return 0;
}

```

## disassembly

```asm
0x180041774  mov     rax, rsp
0x180041777  mov     [rax+8], rbx
0x18004177b  mov     [rax+20h], rsi
0x18004177f  push    rdi; int
0x180041780  sub     rsp, 20h
0x180041784  mov     rsi, rcx
0x180041787  mov     qword ptr [rax+10h], 0
0x18004178f  lea     rdx, [rax+10h]; ppOldObject
0x180041793  xor     ecx, ecx; pNewObject
0x180041795  call    cs:__imp_CoSwitchCallContext
0x18004179c  nop     dword ptr [rax+rax+00h]
0x1800417a1  mov     ebx, eax
0x1800417a3  test    eax, eax
0x1800417a5  jns     short loc_1800417C7
0x1800417a7  mov     r9d, eax; char *
0x1800417aa  mov     edx, 37h ; '7'; void *
0x1800417af  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\settingshandlers\\w"...
0x1800417b6  mov     rcx, [rsp+28h]; this
0x1800417bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800417c0  mov     eax, ebx
0x1800417c2  jmp     loc_18004185A
0x1800417c7  mov     rdi, [rsp+28h+pNewObject]
0x1800417cc  mov     rcx, rsi
0x1800417cf  call    _lambda_801c2abe9776f154853b0bdf20718208___operator__
0x1800417d4  mov     ebx, eax
0x1800417d6  test    eax, eax
0x1800417d8  jns     short loc_18004181E
0x1800417da  mov     rcx, [rsp+28h]; this
0x1800417df  mov     r9d, eax; char *
0x1800417e2  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\settingshandlers\\w"...
0x1800417e9  mov     edx, 41h ; 'A'; void *
0x1800417ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800417f3  mov     [rsp+28h+ppOldObject], 0
0x1800417fc  lea     rdx, [rsp+28h+ppOldObject]; ppOldObject
0x180041801  mov     rcx, rdi; pNewObject
0x180041804  call    cs:__imp_CoSwitchCallContext
0x18004180b  nop     dword ptr [rax+rax+00h]
0x180041810  test    eax, eax
0x180041812  jns     short loc_1800417C0
0x180041814  mov     r9d, eax
0x180041817  mov     edx, 3Dh ; '='
0x18004181c  jmp     short loc_1800417AF
0x18004181e  mov     [rsp+28h+ppOldObject], 0
0x180041827  lea     rdx, [rsp+28h+ppOldObject]; ppOldObject
0x18004182c  mov     rcx, rdi; pNewObject
0x18004182f  call    cs:__imp_CoSwitchCallContext
0x180041836  nop     dword ptr [rax+rax+00h]
0x18004183b  test    eax, eax
0x18004183d  jns     short loc_180041858
0x18004183f  mov     rcx, [rsp+28h]; this
0x180041844  mov     r9d, eax; char *
0x180041847  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\settingshandlers\\w"...
0x18004184e  mov     edx, 3Dh ; '='; void *
0x180041853  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041858  xor     eax, eax
0x18004185a  mov     rbx, [rsp+28h+arg_0]
0x18004185f  mov     rsi, [rsp+28h+arg_18]
0x180041864  add     rsp, 20h
0x180041868  pop     rdi
0x180041869  retn
```
