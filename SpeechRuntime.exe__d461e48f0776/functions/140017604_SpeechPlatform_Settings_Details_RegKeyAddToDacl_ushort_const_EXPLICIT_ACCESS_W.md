# SpeechPlatform::Settings::Details::RegKeyAddToDacl(ushort const *,_EXPLICIT_ACCESS_W &)

- ea: `0x140017604`
- end: `0x1400176ea`
- name: `?RegKeyAddToDacl@Details@Settings@SpeechPlatform@@YAJPEBGAEAU_EXPLICIT_ACCESS_W@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, PEXPLICIT_ACCESS_W pListOfExplicitEntries, struct _EXPLICIT_ACCESS_W *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140014388`

## callees

- `0x140017604`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400176ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400176c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400176ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400176c5`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140017679`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140017679`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x140017654`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x140017654`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1400176ad`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1400176ad`

## pseudocode

```c
__int64 __fastcall SpeechPlatform::Settings::Details::RegKeyAddToDacl(
        LPWSTR pObjectName,
        PEXPLICIT_ACCESS_W pListOfExplicitEntries,
        struct _EXPLICIT_ACCESS_W *a3)
{
  signed int NamedSecurityInfoW; // ebx
  HLOCAL hMem; // [rsp+40h] [rbp-18h] BYREF
  PACL NewAcl; // [rsp+70h] [rbp+18h] BYREF
  PACL OldAcl; // [rsp+78h] [rbp+20h] BYREF

  hMem = 0;
  OldAcl = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 4u, 0, 0, &OldAcl, 0, &hMem);
  if ( !NamedSecurityInfoW )
  {
    NewAcl = 0;
    NamedSecurityInfoW = SetEntriesInAclW(1u, pListOfExplicitEntries, OldAcl, &NewAcl);
    if ( !NamedSecurityInfoW )
    {
      NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 4u, 0, 0, NewAcl, 0);
      LocalFree(NewAcl);
    }
    LocalFree(hMem);
  }
  if ( NamedSecurityInfoW > 0 )
    return (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  return (unsigned int)NamedSecurityInfoW;
}

```

## disassembly

```asm
0x140017604  mov     r11, rsp
0x140017607  mov     [r11+8], rbx
0x14001760b  mov     [r11+10h], rsi
0x14001760f  push    rdi
0x140017610  sub     rsp, 50h
0x140017614  lea     rax, [r11-18h]
0x140017618  mov     qword ptr [r11-18h], 0
0x140017620  mov     [r11-20h], rax
0x140017624  xor     r9d, r9d; ppsidOwner
0x140017627  mov     qword ptr [r11-28h], 0
0x14001762f  lea     rax, [r11+20h]
0x140017633  mov     rsi, rdx
0x140017636  mov     [r11-30h], rax
0x14001763a  mov     rdi, rcx
0x14001763d  mov     qword ptr [r11+20h], 0
0x140017645  lea     edx, [r9+4]; ObjectType
0x140017649  mov     qword ptr [r11-38h], 0
0x140017651  mov     r8d, edx; SecurityInfo
0x140017654  call    cs:__imp_GetNamedSecurityInfoW
0x14001765a  mov     ebx, eax
0x14001765c  test    eax, eax
0x14001765e  jnz     short loc_1400176CB
0x140017660  mov     r8, [rsp+58h+OldAcl]; OldAcl
0x140017665  lea     r9, [rsp+58h+NewAcl]; NewAcl
0x14001766a  mov     rdx, rsi; pListOfExplicitEntries
0x14001766d  mov     [rsp+58h+NewAcl], 0
0x140017676  lea     ecx, [rax+1]; cCountOfExplicitEntries
0x140017679  call    cs:__imp_SetEntriesInAclW
0x14001767f  mov     ebx, eax
0x140017681  test    eax, eax
0x140017683  jnz     short loc_1400176C0
0x140017685  mov     rax, [rsp+58h+NewAcl]
0x14001768a  lea     edx, [rbx+4]; ObjectType
0x14001768d  mov     [rsp+58h+pSacl], 0; pSacl
0x140017696  mov     r8d, edx; SecurityInfo
0x140017699  mov     [rsp+58h+pDacl], rax; pDacl
0x14001769e  xor     r9d, r9d; psidOwner
0x1400176a1  mov     rcx, rdi; pObjectName
0x1400176a4  mov     [rsp+58h+psidGroup], 0; psidGroup
0x1400176ad  call    cs:__imp_SetNamedSecurityInfoW
0x1400176b3  mov     rcx, [rsp+58h+NewAcl]; hMem
0x1400176b8  mov     ebx, eax
0x1400176ba  call    cs:__imp_LocalFree
0x1400176c0  mov     rcx, [rsp+58h+hMem]; hMem
0x1400176c5  call    cs:__imp_LocalFree
0x1400176cb  test    ebx, ebx
0x1400176cd  jle     short loc_1400176D8
0x1400176cf  movzx   ebx, bx
0x1400176d2  or      ebx, 80070000h
0x1400176d8  mov     rsi, [rsp+58h+arg_8]
0x1400176dd  mov     eax, ebx
0x1400176df  mov     rbx, [rsp+58h+arg_0]
0x1400176e4  add     rsp, 50h
0x1400176e8  pop     rdi
0x1400176e9  retn
```
