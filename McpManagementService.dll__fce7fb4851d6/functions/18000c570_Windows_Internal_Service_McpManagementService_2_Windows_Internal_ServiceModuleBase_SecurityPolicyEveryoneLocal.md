# Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::RunServiceMain(uchar)

- ea: `0x18000c570`
- end: `0x18000c63b`
- name: `?RunServiceMain@?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@QEAAJE@Z`
- size: `203`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ed30`

## callees

- `0x180006a80`
- `0x180007980`
- `0x18000c4cc`
- `0x18000c570`
- `0x18000d58c`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c600`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c600`

## string_xrefs

- `0x18000c613`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::RunServiceMain(
        __int64 a1,
        char a2)
{
  __int64 v3; // rax
  int v4; // eax
  SERVICE_STATUS_HANDLE v5; // rcx
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-48h]
  char v9; // [rsp+30h] [rbp-38h] BYREF
  __int64 v10; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  Windows::Internal::ServiceModuleBase *v12; // [rsp+70h] [rbp+8h] BYREF
  char *v13; // [rsp+78h] [rbp+10h] BYREF

  LOBYTE(v13) = a2;
  *(_DWORD *)(a1 + 24) |= 1u;
  v9 = 0;
  v12 = 0;
  v3 = _lambda_ee4f524e8f107cd4e9b9ec23951f1e48_::_lambda_ee4f524e8f107cd4e9b9ec23951f1e48_(
         (unsigned int)&v10,
         a1,
         (unsigned int)&v9,
         (unsigned int)&v12,
         (__int64)&v13);
  v4 = _lambda_ee4f524e8f107cd4e9b9ec23951f1e48_::operator()(v3);
  LODWORD(v13) = v4;
  if ( (v4 & 0x1FFF0000) == 0x70000 )
  {
    *(_DWORD *)(a1 + 28) = (unsigned __int16)v4;
  }
  else
  {
    if ( v4 < 0 )
      *(_DWORD *)(a1 + 28) = 1066;
    *(_DWORD *)(a1 + 32) = v4;
  }
  if ( v12 )
    Windows::Internal::ServiceModuleBase::Uninitialize(v12);
  v5 = *(SERVICE_STATUS_HANDLE *)(a1 + 8);
  *(_DWORD *)(a1 + 20) = 1;
  SetServiceStatus(v5, (LPSERVICE_STATUS)(a1 + 16));
  v6 = (unsigned int)v13;
  if ( (int)v13 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x275,
    (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
    (const char *)(unsigned int)v13,
    v8);
  return v6;
}

```

## disassembly

```asm
0x18000c570  mov     r11, rsp
0x18000c573  mov     [r11+18h], rbx
0x18000c577  mov     byte ptr [rsp+arg_8], dl
0x18000c57b  push    rdi
0x18000c57c  sub     rsp, 60h
0x18000c580  or      dword ptr [rcx+18h], 1
0x18000c584  lea     rax, [r11+10h]
0x18000c588  mov     rdx, rcx
0x18000c58b  mov     [r11-48h], rax
0x18000c58f  mov     rbx, rcx
0x18000c592  mov     [rsp+68h+var_38], 0
0x18000c597  lea     rcx, [r11-30h]
0x18000c59b  mov     qword ptr [r11+8], 0
0x18000c5a3  lea     r9, [r11+8]
0x18000c5a7  lea     r8, [r11-38h]
0x18000c5ab  call    ??0_lambda_ee4f524e8f107cd4e9b9ec23951f1e48_@@QEAA@PEAV?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@AEAEAEAPEAVServiceModuleBase@23@AEAJ@Z; _lambda_ee4f524e8f107cd4e9b9ec23951f1e48_::_lambda_ee4f524e8f107cd4e9b9ec23951f1e48_(Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor> *,uchar &,Windows::Internal::ServiceModuleBase * &,long &)
0x18000c5b0  mov     rcx, rax
0x18000c5b3  call    ??R_lambda_ee4f524e8f107cd4e9b9ec23951f1e48_@@QEBA@XZ; _lambda_ee4f524e8f107cd4e9b9ec23951f1e48_::operator()(void)
0x18000c5b8  mov     ecx, eax
0x18000c5ba  mov     dword ptr [rsp+68h+arg_8], eax
0x18000c5be  and     ecx, 1FFF0000h
0x18000c5c4  cmp     ecx, 70000h
0x18000c5ca  jnz     short loc_18000C5D4
0x18000c5cc  movzx   eax, ax
0x18000c5cf  mov     [rbx+1Ch], eax
0x18000c5d2  jmp     short loc_18000C5E2
0x18000c5d4  test    eax, eax
0x18000c5d6  jns     short loc_18000C5DF
0x18000c5d8  mov     dword ptr [rbx+1Ch], 42Ah
0x18000c5df  mov     [rbx+20h], eax
0x18000c5e2  mov     rcx, [rsp+68h+arg_0]; this
0x18000c5e7  test    rcx, rcx
0x18000c5ea  jz      short loc_18000C5F1
0x18000c5ec  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18000c5f1  mov     rcx, [rbx+8]; hServiceStatus
0x18000c5f5  lea     rdx, [rbx+10h]; lpServiceStatus
0x18000c5f9  mov     dword ptr [rbx+14h], 1
0x18000c600  call    cs:__imp_SetServiceStatus
0x18000c606  mov     ebx, dword ptr [rsp+68h+arg_8]
0x18000c60a  test    ebx, ebx
0x18000c60c  jns     short loc_18000C62B
0x18000c60e  mov     rcx, [rsp+68h]; this
0x18000c613  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18000c61a  mov     r9d, ebx; char *
0x18000c61d  mov     edx, 275h; void *
0x18000c622  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c627  mov     eax, ebx
0x18000c629  jmp     short loc_18000C62D
0x18000c62b  xor     eax, eax
0x18000c62d  mov     rbx, [rsp+68h+arg_10]
0x18000c635  add     rsp, 60h
0x18000c639  pop     rdi
0x18000c63a  retn
```
