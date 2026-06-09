# SystemSettings::WorkAccess::SwitchToBrokerCallingContext__lambda_6e156cf47127949868d32e176a6524b2___

- ea: `0x180019820`
- end: `0x18001996a`
- name: `SystemSettings::WorkAccess::SwitchToBrokerCallingContext__lambda_6e156cf47127949868d32e176a6524b2___`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c960`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x180019820`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180019844`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800198ef`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x18001992b`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180019844`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800198ef`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x18001992b`

## string_xrefs

- `0x1800198b4`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001985e`: `shellcommon\shell\settingshandlers\workaccess\lib\SharedHelpers.h`
- `0x1800198cd`: `shellcommon\shell\settingshandlers\workaccess\lib\SharedHelpers.h`
- `0x180019943`: `shellcommon\shell\settingshandlers\workaccess\lib\SharedHelpers.h`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::SwitchToBrokerCallingContext__lambda_6e156cf47127949868d32e176a6524b2___(
        _QWORD *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  unsigned __int64 v4; // r9
  __int64 v5; // rdx
  IUnknown *v7; // rbp
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, __int64); // rdi
  __int64 v10; // rbx
  int v11; // eax
  HRESULT v12; // eax
  HRESULT v13; // eax
  int v14; // [rsp+20h] [rbp-18h]
  int v15; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  IUnknown *pNewObject; // [rsp+48h] [rbp+10h] BYREF
  IUnknown *ppOldObject; // [rsp+50h] [rbp+18h] BYREF

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
  v8 = *(_QWORD *)(*a1 + 304LL);
  v9 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 96LL);
  v10 = a1[1];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v10);
  v11 = v9(v8, v10);
  v3 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x108,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)v11,
      v14);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\SharedHelpers.h",
      (const char *)v3,
      v15);
    ppOldObject = 0;
    v12 = CoSwitchCallContext(v7, &ppOldObject);
    if ( v12 >= 0 )
      return v3;
    v4 = (unsigned int)v12;
    v5 = 61;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\SharedHelpers.h",
      (const char *)v4,
      v14);
    return v3;
  }
  *(_BYTE *)(*a1 + 297LL) = 1;
  ppOldObject = 0;
  v13 = CoSwitchCallContext(v7, &ppOldObject);
  if ( v13 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\SharedHelpers.h",
      (const char *)(unsigned int)v13,
      v14);
  return 0;
}

```

## disassembly

```asm
0x180019820  mov     rax, rsp
0x180019823  mov     [rax+8], rbx
0x180019827  mov     [rax+20h], rbp
0x18001982b  push    rsi
0x18001982c  push    rdi
0x18001982d  push    r14; int
0x18001982f  sub     rsp, 20h
0x180019833  mov     r14, rcx
0x180019836  mov     qword ptr [rax+10h], 0
0x18001983e  lea     rdx, [rax+10h]; ppOldObject
0x180019842  xor     ecx, ecx; pNewObject
0x180019844  call    cs:__imp_CoSwitchCallContext
0x18001984b  nop     dword ptr [rax+rax+00h]
0x180019850  mov     ebx, eax
0x180019852  test    eax, eax
0x180019854  jns     short loc_180019876
0x180019856  mov     r9d, eax; char *
0x180019859  mov     edx, 37h ; '7'; void *
0x18001985e  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\settingshandlers\\w"...
0x180019865  mov     rcx, [rsp+38h]; this
0x18001986a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001986f  mov     eax, ebx
0x180019871  jmp     loc_180019956
0x180019876  mov     rbp, [rsp+38h+pNewObject]
0x18001987b  mov     rax, [r14]
0x18001987e  mov     rsi, [rax+130h]
0x180019885  mov     rax, [rsi]
0x180019888  mov     rdi, [rax+60h]
0x18001988c  mov     rbx, [r14+8]
0x180019890  mov     rcx, rbx
0x180019893  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019898  mov     rdx, rbx
0x18001989b  mov     rcx, rsi
0x18001989e  mov     rax, rdi
0x1800198a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198a6  mov     ebx, eax
0x1800198a8  test    eax, eax
0x1800198aa  jns     short loc_180019910
0x1800198ac  mov     rcx, [rsp+38h]; this
0x1800198b1  mov     r9d, eax; char *
0x1800198b4  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x1800198bb  mov     edx, 108h; void *
0x1800198c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800198c5  mov     rcx, [rsp+38h]; this
0x1800198ca  mov     r9d, ebx; char *
0x1800198cd  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\settingshandlers\\w"...
0x1800198d4  mov     edx, 41h ; 'A'; void *
0x1800198d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800198de  mov     [rsp+38h+ppOldObject], 0
0x1800198e7  lea     rdx, [rsp+38h+ppOldObject]; ppOldObject
0x1800198ec  mov     rcx, rbp; pNewObject
0x1800198ef  call    cs:__imp_CoSwitchCallContext
0x1800198f6  nop     dword ptr [rax+rax+00h]
0x1800198fb  test    eax, eax
0x1800198fd  jns     loc_18001986F
0x180019903  mov     r9d, eax
0x180019906  mov     edx, 3Dh ; '='
0x18001990b  jmp     loc_18001985E
0x180019910  mov     rax, [r14]
0x180019913  mov     byte ptr [rax+129h], 1
0x18001991a  mov     [rsp+38h+ppOldObject], 0
0x180019923  lea     rdx, [rsp+38h+ppOldObject]; ppOldObject
0x180019928  mov     rcx, rbp; pNewObject
0x18001992b  call    cs:__imp_CoSwitchCallContext
0x180019932  nop     dword ptr [rax+rax+00h]
0x180019937  test    eax, eax
0x180019939  jns     short loc_180019954
0x18001993b  mov     rcx, [rsp+38h]; this
0x180019940  mov     r9d, eax; char *
0x180019943  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\settingshandlers\\w"...
0x18001994a  mov     edx, 3Dh ; '='; void *
0x18001994f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019954  xor     eax, eax
0x180019956  mov     rbx, [rsp+38h+arg_0]
0x18001995b  mov     rbp, [rsp+38h+arg_18]
0x180019960  add     rsp, 20h
0x180019964  pop     r14
0x180019966  pop     rdi
0x180019967  pop     rsi
0x180019968  retn
```
