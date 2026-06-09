# AmiUtilityGivePrivilegesToServices(HKEY__ *)

- ea: `0x180039b54`
- end: `0x180039bf8`
- name: `?AmiUtilityGivePrivilegesToServices@@YAKPEAUHKEY__@@@Z`
- size: `164`
- prototype: `unsigned int __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003a880`

## callees

- `0x1800295dc`
- `0x180039b54`
- `0x180039c00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039be5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039be5`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180039bbe`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180039bbe`

## string_xrefs

- `0x180039b8d`: `AmiUtilityInitSecurityDescriptor failed [%d]`
- `0x180039bca`: `RegSetKeySecurity failed [%d]`
- `0x180039b9a`: `AmiUtilityGivePrivilegesToServices`

## pseudocode

```c
__int64 __fastcall AmiUtilityGivePrivilegesToServices(HKEY hKey)
{
  int inited; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 v5; // r8
  _OWORD pSecurityDescriptor[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v8; // [rsp+50h] [rbp-18h]
  HLOCAL hMem; // [rsp+78h] [rbp+10h] BYREF

  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  hMem = 0;
  v8 = 0;
  inited = AmiUtilityInitSecurityDescriptor(pSecurityDescriptor, (PACL *)&hMem);
  v3 = inited;
  if ( inited )
  {
    v4 = "AmiUtilityInitSecurityDescriptor failed [%d]";
    v5 = 235;
LABEL_3:
    AslLogCallPrintf(1, "AmiUtilityGivePrivilegesToServices", v5, v4, inited);
    goto LABEL_7;
  }
  inited = RegSetKeySecurity(hKey, 4u, pSecurityDescriptor);
  v3 = inited;
  if ( inited )
  {
    v4 = "RegSetKeySecurity failed [%d]";
    v5 = 244;
    goto LABEL_3;
  }
  v3 = 0;
LABEL_7:
  if ( hMem )
    LocalFree(hMem);
  return v3;
}

```

## disassembly

```asm
0x180039b54  mov     r11, rsp
0x180039b57  mov     [r11+8], rbx
0x180039b5b  push    rdi
0x180039b5c  sub     rsp, 60h
0x180039b60  xorps   xmm0, xmm0
0x180039b63  lea     rdx, [r11+10h]; NewAcl
0x180039b67  xor     eax, eax
0x180039b69  mov     rdi, rcx
0x180039b6c  movups  [rsp+68h+pSecurityDescriptor], xmm0
0x180039b71  lea     rcx, [r11-38h]; pSecurityDescriptor
0x180039b75  mov     [r11+10h], rax
0x180039b79  movups  [rsp+68h+var_28], xmm0
0x180039b7e  mov     [r11-18h], rax
0x180039b82  call    ?AmiUtilityInitSecurityDescriptor@@YAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z; AmiUtilityInitSecurityDescriptor(_SECURITY_DESCRIPTOR &,_ACL * &)
0x180039b87  mov     ebx, eax
0x180039b89  test    eax, eax
0x180039b8b  jz      short loc_180039BB1
0x180039b8d  lea     r9, aAmiutilityinit_0; "AmiUtilityInitSecurityDescriptor failed"...
0x180039b94  mov     r8d, 0EBh
0x180039b9a  lea     rdx, aAmiutilitygive; "AmiUtilityGivePrivilegesToServices"
0x180039ba1  mov     [rsp+68h+var_48], eax
0x180039ba5  mov     ecx, 1
0x180039baa  call    AslLogCallPrintf
0x180039baf  jmp     short loc_180039BDB
0x180039bb1  lea     r8, [rsp+68h+pSecurityDescriptor]; pSecurityDescriptor
0x180039bb6  mov     edx, 4; SecurityInformation
0x180039bbb  mov     rcx, rdi; hKey
0x180039bbe  call    cs:__imp_RegSetKeySecurity
0x180039bc4  mov     ebx, eax
0x180039bc6  test    eax, eax
0x180039bc8  jz      short loc_180039BD9
0x180039bca  lea     r9, aRegsetkeysecur; "RegSetKeySecurity failed [%d]"
0x180039bd1  mov     r8d, 0F4h
0x180039bd7  jmp     short loc_180039B9A
0x180039bd9  xor     ebx, ebx
0x180039bdb  mov     rcx, [rsp+68h+hMem]; hMem
0x180039be0  test    rcx, rcx
0x180039be3  jz      short loc_180039BEB
0x180039be5  call    cs:__imp_LocalFree
0x180039beb  mov     eax, ebx
0x180039bed  mov     rbx, [rsp+68h+arg_0]
0x180039bf2  add     rsp, 60h
0x180039bf6  pop     rdi
0x180039bf7  retn
```
