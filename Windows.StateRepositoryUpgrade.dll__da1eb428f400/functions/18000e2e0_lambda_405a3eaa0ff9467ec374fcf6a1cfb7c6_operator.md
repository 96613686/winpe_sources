# _lambda_405a3eaa0ff9467ec374fcf6a1cfb7c6_::operator()

- ea: `0x18000e2e0`
- end: `0x18000e42f`
- name: `_lambda_405a3eaa0ff9467ec374fcf6a1cfb7c6_::operator()`
- size: `335`
- prototype: `void __fastcall(_DWORD **, __int64, __int64, _QWORD *, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000dc30`

## callees

- `0x18000c3bc`
- `0x18000c584`
- `0x18000e2e0`
- `0x18000eae4`

## import_xrefs

- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000e317`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000e317`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!SetProtocolProperty` at `0x18000e388`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!SetProtocolProperty` at `0x18000e388`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!AddExtensionProgId` at `0x18000e3e0`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!AddExtensionProgId` at `0x18000e3e0`

## string_xrefs

- `0x18000e338`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000e399`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000e3f1`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000e355`: `FixProtocolProgId`
- `0x18000e3b6`: `SetProtocolProperty`
- `0x18000e3d1`: `windows.protocol`
- `0x18000e40e`: `Protocol::AddExtensionProgId`

## pseudocode

```c
void __fastcall lambda_405a3eaa0ff9467ec374fcf6a1cfb7c6_::operator()(
        _DWORD **a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5,
        int a6)
{
  _DWORD *v6; // rax
  int fixed; // eax
  unsigned int v10; // edi
  __int64 v11; // rcx
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-18h]
  int v19; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v6 = *a1;
  ++*v6;
  if ( *v6 == 100 * (*v6 / 100) )
    StateRepository_Service_UpdateStatus();
  fixed = FixProtocolProgId(a3, *a4, a5);
  v10 = fixed;
  if ( fixed < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)(unsigned int)fixed,
      v18);
    if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x40) != 0 )
      McTemplateU0dz_EventWriteTransfer(v11, MigrateError, v10, L"FixProtocolProgId");
  }
  v19 = a6;
  v12 = SetProtocolProperty(a4[3], a4[9], a4[1], L"ACID");
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)(unsigned int)v12,
      a6);
    if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x40) != 0 )
      McTemplateU0dz_EventWriteTransfer(v14, MigrateError, v13, L"SetProtocolProperty");
  }
  v15 = AddExtensionProgId(a4[3], L"windows.protocol", a4[1], a5);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)(unsigned int)v15,
      v19);
    if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x40) != 0 )
      McTemplateU0dz_EventWriteTransfer(v17, MigrateError, v16, L"Protocol::AddExtensionProgId");
  }
}

```

## disassembly

```asm
0x18000e2e0  mov     [rsp+arg_0], rbx
0x18000e2e5  push    rdi
0x18000e2e6  sub     rsp, 30h
0x18000e2ea  mov     rax, [rcx]
0x18000e2ed  mov     rbx, r9
0x18000e2f0  mov     ecx, 1
0x18000e2f5  mov     rdi, r8
0x18000e2f8  add     [rax], ecx
0x18000e2fa  mov     r10d, [rax]
0x18000e2fd  mov     eax, 51EB851Fh
0x18000e302  imul    r10d
0x18000e305  sar     edx, 5
0x18000e308  mov     eax, edx
0x18000e30a  shr     eax, 1Fh
0x18000e30d  add     edx, eax
0x18000e30f  imul    eax, edx, 64h ; 'd'
0x18000e312  cmp     r10d, eax
0x18000e315  jnz     short loc_18000E31D
0x18000e317  call    cs:__imp_StateRepository_Service_UpdateStatus
0x18000e31d  mov     r8, [rsp+38h+arg_20]
0x18000e322  mov     rcx, rdi
0x18000e325  mov     rdx, [rbx]
0x18000e328  call    FixProtocolProgId
0x18000e32d  mov     edi, eax
0x18000e32f  test    eax, eax
0x18000e331  jns     short loc_18000E36B
0x18000e333  mov     rcx, [rsp+38h]; this
0x18000e338  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000e33f  mov     r9d, eax; char *
0x18000e342  mov     edx, 6Ch ; 'l'; void *
0x18000e347  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e34c  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 40h
0x18000e353  jz      short loc_18000E36B
0x18000e355  lea     r9, aFixprotocolpro; "FixProtocolProgId"
0x18000e35c  mov     r8d, edi
0x18000e35f  lea     rdx, MigrateError
0x18000e366  call    McTemplateU0dz_EventWriteTransfer
0x18000e36b  mov     rax, qword ptr [rsp+38h+arg_28]
0x18000e370  lea     r9, aAcid; "ACID"
0x18000e377  mov     r8, [rbx+8]
0x18000e37b  mov     rdx, [rbx+48h]
0x18000e37f  mov     rcx, [rbx+18h]
0x18000e383  mov     qword ptr [rsp+38h+var_18], rax; int
0x18000e388  call    cs:__imp_SetProtocolProperty
0x18000e38e  mov     edi, eax
0x18000e390  test    eax, eax
0x18000e392  jns     short loc_18000E3CC
0x18000e394  mov     rcx, [rsp+38h]; this
0x18000e399  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000e3a0  mov     r9d, eax; char *
0x18000e3a3  mov     edx, 73h ; 's'; void *
0x18000e3a8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e3ad  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 40h
0x18000e3b4  jz      short loc_18000E3CC
0x18000e3b6  lea     r9, aSetprotocolpro_0; "SetProtocolProperty"
0x18000e3bd  mov     r8d, edi
0x18000e3c0  lea     rdx, MigrateError
0x18000e3c7  call    McTemplateU0dz_EventWriteTransfer
0x18000e3cc  mov     r9, [rsp+38h+arg_20]
0x18000e3d1  lea     rdx, aWindowsProtoco; "windows.protocol"
0x18000e3d8  mov     r8, [rbx+8]
0x18000e3dc  mov     rcx, [rbx+18h]
0x18000e3e0  call    cs:__imp_AddExtensionProgId
0x18000e3e6  mov     ebx, eax
0x18000e3e8  test    eax, eax
0x18000e3ea  jns     short loc_18000E424
0x18000e3ec  mov     rcx, [rsp+38h]; this
0x18000e3f1  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000e3f8  mov     r9d, eax; char *
0x18000e3fb  mov     edx, 7Ah ; 'z'; void *
0x18000e400  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e405  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 40h
0x18000e40c  jz      short loc_18000E424
0x18000e40e  lea     r9, aProtocolAddext; "Protocol::AddExtensionProgId"
0x18000e415  mov     r8d, ebx
0x18000e418  lea     rdx, MigrateError
0x18000e41f  call    McTemplateU0dz_EventWriteTransfer
0x18000e424  mov     rbx, [rsp+38h+arg_0]
0x18000e429  add     rsp, 30h
0x18000e42d  pop     rdi
0x18000e42e  retn
```
