# Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::RunServiceMain(uchar)

- ea: `0x18001b750`
- end: `0x18001b81b`
- name: `?RunServiceMain@?$Service@VCCaptureService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@QEAAJE@Z`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001bb10`

## callees

- `0x18000907c`
- `0x18001ac5c`
- `0x18001adc0`
- `0x18001b750`
- `0x18001b870`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001b7e0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001b7e0`

## string_xrefs

- `0x18001b7f3`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::RunServiceMain(
        __int64 a1,
        char a2)
{
  _QWORD *v3; // rax
  int v4; // eax
  SERVICE_STATUS_HANDLE v5; // rcx
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-48h]
  _BYTE v9[8]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v10[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  Windows::Internal::ServiceModuleBase *v12; // [rsp+70h] [rbp+8h] BYREF
  char *v13; // [rsp+78h] [rbp+10h] BYREF

  LOBYTE(v13) = a2;
  *(_DWORD *)(a1 + 24) |= 1u;
  v9[0] = 0;
  v12 = 0;
  v3 = _lambda_6da1b080ac11917aad19e61c3237855d_::_lambda_6da1b080ac11917aad19e61c3237855d_(
         v10,
         a1,
         (__int64)v9,
         (__int64)&v12,
         (__int64)&v13);
  v4 = _lambda_6da1b080ac11917aad19e61c3237855d_::operator()((__int64)v3);
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
0x18001b750  mov     r11, rsp
0x18001b753  mov     [r11+18h], rbx
0x18001b757  mov     byte ptr [rsp+arg_8], dl
0x18001b75b  push    rdi
0x18001b75c  sub     rsp, 60h
0x18001b760  or      dword ptr [rcx+18h], 1
0x18001b764  lea     rax, [r11+10h]
0x18001b768  mov     rdx, rcx
0x18001b76b  mov     [r11-48h], rax
0x18001b76f  mov     rbx, rcx
0x18001b772  mov     [rsp+68h+var_38], 0
0x18001b777  lea     rcx, [r11-30h]
0x18001b77b  mov     qword ptr [r11+8], 0
0x18001b783  lea     r9, [r11+8]
0x18001b787  lea     r8, [r11-38h]
0x18001b78b  call    ??0_lambda_6da1b080ac11917aad19e61c3237855d_@@QEAA@PEAV?$Service@VCCaptureService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@AEAEAEAPEAVServiceModuleBase@23@AEAJ@Z; _lambda_6da1b080ac11917aad19e61c3237855d_::_lambda_6da1b080ac11917aad19e61c3237855d_(Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor> *,uchar &,Windows::Internal::ServiceModuleBase * &,long &)
0x18001b790  mov     rcx, rax
0x18001b793  call    ??R_lambda_6da1b080ac11917aad19e61c3237855d_@@QEBA@XZ; _lambda_6da1b080ac11917aad19e61c3237855d_::operator()(void)
0x18001b798  mov     ecx, eax
0x18001b79a  mov     dword ptr [rsp+68h+arg_8], eax
0x18001b79e  and     ecx, 1FFF0000h
0x18001b7a4  cmp     ecx, 70000h
0x18001b7aa  jnz     short loc_18001B7B4
0x18001b7ac  movzx   eax, ax
0x18001b7af  mov     [rbx+1Ch], eax
0x18001b7b2  jmp     short loc_18001B7C2
0x18001b7b4  test    eax, eax
0x18001b7b6  jns     short loc_18001B7BF
0x18001b7b8  mov     dword ptr [rbx+1Ch], 42Ah
0x18001b7bf  mov     [rbx+20h], eax
0x18001b7c2  mov     rcx, [rsp+68h+arg_0]; this
0x18001b7c7  test    rcx, rcx
0x18001b7ca  jz      short loc_18001B7D1
0x18001b7cc  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18001b7d1  mov     rcx, [rbx+8]; hServiceStatus
0x18001b7d5  lea     rdx, [rbx+10h]; lpServiceStatus
0x18001b7d9  mov     dword ptr [rbx+14h], 1
0x18001b7e0  call    cs:__imp_SetServiceStatus
0x18001b7e6  mov     ebx, dword ptr [rsp+68h+arg_8]
0x18001b7ea  test    ebx, ebx
0x18001b7ec  jns     short loc_18001B80B
0x18001b7ee  mov     rcx, [rsp+68h]; this
0x18001b7f3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18001b7fa  mov     r9d, ebx; char *
0x18001b7fd  mov     edx, 275h; void *
0x18001b802  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b807  mov     eax, ebx
0x18001b809  jmp     short loc_18001B80D
0x18001b80b  xor     eax, eax
0x18001b80d  mov     rbx, [rsp+68h+arg_10]
0x18001b815  add     rsp, 60h
0x18001b819  pop     rdi
0x18001b81a  retn
```
