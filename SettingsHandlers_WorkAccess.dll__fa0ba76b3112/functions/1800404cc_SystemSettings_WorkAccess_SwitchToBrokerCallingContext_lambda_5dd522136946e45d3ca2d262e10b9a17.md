# SystemSettings::WorkAccess::SwitchToBrokerCallingContext__lambda_5dd522136946e45d3ca2d262e10b9a17___

- ea: `0x1800404cc`
- end: `0x1800405c3`
- name: `SystemSettings::WorkAccess::SwitchToBrokerCallingContext__lambda_5dd522136946e45d3ca2d262e10b9a17___`
- size: `247`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180040c40`

## callees

- `0x1800096ec`
- `0x1800404cc`
- `0x180040734`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800404ed`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x18004055c`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180040587`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800404ed`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x18004055c`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180040587`

## string_xrefs

- `0x180040507`: `shellcommon\shell\settingshandlers\workaccess\lib\SharedHelpers.h`
- `0x18004053a`: `shellcommon\shell\settingshandlers\workaccess\lib\SharedHelpers.h`
- `0x18004059f`: `shellcommon\shell\settingshandlers\workaccess\lib\SharedHelpers.h`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::SwitchToBrokerCallingContext__lambda_5dd522136946e45d3ca2d262e10b9a17___(
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
  v8 = lambda_5dd522136946e45d3ca2d262e10b9a17_::operator()(a1);
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
0x1800404cc  mov     rax, rsp
0x1800404cf  mov     [rax+8], rbx
0x1800404d3  mov     [rax+20h], rsi
0x1800404d7  push    rdi; int
0x1800404d8  sub     rsp, 20h
0x1800404dc  mov     rsi, rcx
0x1800404df  mov     qword ptr [rax+10h], 0
0x1800404e7  lea     rdx, [rax+10h]; ppOldObject
0x1800404eb  xor     ecx, ecx; pNewObject
0x1800404ed  call    cs:__imp_CoSwitchCallContext
0x1800404f4  nop     dword ptr [rax+rax+00h]
0x1800404f9  mov     ebx, eax
0x1800404fb  test    eax, eax
0x1800404fd  jns     short loc_18004051F
0x1800404ff  mov     r9d, eax; char *
0x180040502  mov     edx, 37h ; '7'; void *
0x180040507  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\settingshandlers\\w"...
0x18004050e  mov     rcx, [rsp+28h]; this
0x180040513  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040518  mov     eax, ebx
0x18004051a  jmp     loc_1800405B2
0x18004051f  mov     rdi, [rsp+28h+pNewObject]
0x180040524  mov     rcx, rsi
0x180040527  call    _lambda_5dd522136946e45d3ca2d262e10b9a17___operator__
0x18004052c  mov     ebx, eax
0x18004052e  test    eax, eax
0x180040530  jns     short loc_180040576
0x180040532  mov     rcx, [rsp+28h]; this
0x180040537  mov     r9d, eax; char *
0x18004053a  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\settingshandlers\\w"...
0x180040541  mov     edx, 41h ; 'A'; void *
0x180040546  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004054b  mov     [rsp+28h+ppOldObject], 0
0x180040554  lea     rdx, [rsp+28h+ppOldObject]; ppOldObject
0x180040559  mov     rcx, rdi; pNewObject
0x18004055c  call    cs:__imp_CoSwitchCallContext
0x180040563  nop     dword ptr [rax+rax+00h]
0x180040568  test    eax, eax
0x18004056a  jns     short loc_180040518
0x18004056c  mov     r9d, eax
0x18004056f  mov     edx, 3Dh ; '='
0x180040574  jmp     short loc_180040507
0x180040576  mov     [rsp+28h+ppOldObject], 0
0x18004057f  lea     rdx, [rsp+28h+ppOldObject]; ppOldObject
0x180040584  mov     rcx, rdi; pNewObject
0x180040587  call    cs:__imp_CoSwitchCallContext
0x18004058e  nop     dword ptr [rax+rax+00h]
0x180040593  test    eax, eax
0x180040595  jns     short loc_1800405B0
0x180040597  mov     rcx, [rsp+28h]; this
0x18004059c  mov     r9d, eax; char *
0x18004059f  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\settingshandlers\\w"...
0x1800405a6  mov     edx, 3Dh ; '='; void *
0x1800405ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800405b0  xor     eax, eax
0x1800405b2  mov     rbx, [rsp+28h+arg_0]
0x1800405b7  mov     rsi, [rsp+28h+arg_18]
0x1800405bc  add     rsp, 20h
0x1800405c0  pop     rdi
0x1800405c1  retn
```
