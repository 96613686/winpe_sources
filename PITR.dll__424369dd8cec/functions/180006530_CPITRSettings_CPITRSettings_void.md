# CPITRSettings::~CPITRSettings(void)

- ea: `0x180006530`
- end: `0x180006611`
- name: `??1CPITRSettings@@UEAA@XZ`
- size: `225`
- prototype: `void __fastcall(CPITRSettings *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007420`

## callees

- `0x180006530`
- `0x18001cd2c`
- `0x180020a10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800065b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800065b3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18000656e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18000656e`
- `unbcl!??1Object@UnBCL@@UEAA@XZ` at `0x18000660a`

## string_xrefs

- `0x180006583`: `SeBackupPrivilege`
- `0x1800065d8`: `SeBackupPrivilege`
- `0x180006596`: `SeRestorePrivilege`
- `0x1800065ed`: `SeRestorePrivilege`

## pseudocode

```c
void __fastcall CPITRSettings::~CPITRSettings(CPITRSettings *this)
{
  int v2; // esi
  int v3; // edi
  __int64 v4; // rcx
  HKEY v5; // rcx
  CPITRBase *v6; // rcx
  int v7; // [rsp+40h] [rbp+8h] BYREF
  int v8; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)this = &CPITRSettings::`vftable'{for `PITR::IPITRSettings'};
  *((_QWORD *)this + 1) = &CPITRSettings::`vftable'{for `UnBCL::Object'};
  v2 = 0;
  v7 = 0;
  v3 = 0;
  v8 = 0;
  v4 = *((_QWORD *)this + 3);
  if ( v4 && UnBCL::SmartPtr<UnBCL::String>::get_P(v4 + 24) )
  {
    pEnablePrivilege(L"SeBackupPrivilege", 1, &v7);
    pEnablePrivilege(L"SeRestorePrivilege", 1, &v8);
    v2 = v7;
    v3 = v8;
  }
  v5 = (HKEY)*((_QWORD *)this + 4);
  if ( v5 )
  {
    RegCloseKey(v5);
    *((_QWORD *)this + 4) = 0;
  }
  v6 = (CPITRBase *)*((_QWORD *)this + 3);
  if ( v6 )
    CPITRBase::UnlockSoftwareKey(v6);
  if ( v2 )
    pEnablePrivilege(L"SeBackupPrivilege", 0, 0);
  if ( v3 )
    pEnablePrivilege(L"SeRestorePrivilege", 0, 0);
  UnBCL::Object::~Object((CPITRSettings *)((char *)this + 8));
}

```

## disassembly

```asm
0x180006530  mov     [rsp+arg_10], rbx
0x180006535  push    rsi
0x180006536  push    rdi
0x180006537  push    r14
0x180006539  sub     rsp, 20h
0x18000653d  mov     rbx, rcx
0x180006540  lea     rax, ??_7CPITRSettings@@6BIPITRSettings@PITR@@@; const CPITRSettings::`vftable'{for `PITR::IPITRSettings'}
0x180006547  mov     [rcx], rax
0x18000654a  lea     rax, ??_7CPITRSettings@@6BObject@UnBCL@@@; const CPITRSettings::`vftable'{for `UnBCL::Object'}
0x180006551  mov     [rcx+8], rax
0x180006555  xor     esi, esi
0x180006557  mov     [rsp+38h+arg_0], esi
0x18000655b  xor     edi, edi
0x18000655d  mov     [rsp+38h+arg_8], edi
0x180006561  mov     rcx, [rcx+18h]
0x180006565  test    rcx, rcx
0x180006568  jz      short loc_1800065AA
0x18000656a  add     rcx, 18h
0x18000656e  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180006574  test    rax, rax
0x180006577  jz      short loc_1800065AA
0x180006579  lea     r8, [rsp+38h+arg_0]; int *
0x18000657e  lea     edi, [rsi+1]
0x180006581  mov     edx, edi; int
0x180006583  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18000658a  call    ?pEnablePrivilege@@YAHPEBGHPEAH@Z; pEnablePrivilege(ushort const *,int,int *)
0x18000658f  lea     r8, [rsp+38h+arg_8]; int *
0x180006594  mov     edx, edi; int
0x180006596  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18000659d  call    ?pEnablePrivilege@@YAHPEBGHPEAH@Z; pEnablePrivilege(ushort const *,int,int *)
0x1800065a2  mov     esi, [rsp+38h+arg_0]
0x1800065a6  mov     edi, [rsp+38h+arg_8]
0x1800065aa  mov     rcx, [rbx+20h]; hKey
0x1800065ae  test    rcx, rcx
0x1800065b1  jz      short loc_1800065C1
0x1800065b3  call    cs:__imp_RegCloseKey
0x1800065b9  mov     qword ptr [rbx+20h], 0
0x1800065c1  mov     rcx, [rbx+18h]; this
0x1800065c5  test    rcx, rcx
0x1800065c8  jz      short loc_1800065CF
0x1800065ca  call    ?UnlockSoftwareKey@CPITRBase@@QEAAJXZ; CPITRBase::UnlockSoftwareKey(void)
0x1800065cf  test    esi, esi
0x1800065d1  jz      short loc_1800065E4
0x1800065d3  xor     r8d, r8d; int *
0x1800065d6  xor     edx, edx; int
0x1800065d8  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x1800065df  call    ?pEnablePrivilege@@YAHPEBGHPEAH@Z; pEnablePrivilege(ushort const *,int,int *)
0x1800065e4  test    edi, edi
0x1800065e6  jz      short loc_1800065F9
0x1800065e8  xor     r8d, r8d; int *
0x1800065eb  xor     edx, edx; int
0x1800065ed  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x1800065f4  call    ?pEnablePrivilege@@YAHPEBGHPEAH@Z; pEnablePrivilege(ushort const *,int,int *)
0x1800065f9  lea     rcx, [rbx+8]
0x1800065fd  mov     rbx, [rsp+38h+arg_10]
0x180006602  add     rsp, 20h
0x180006606  pop     r14
0x180006608  pop     rdi
0x180006609  pop     rsi
0x18000660a  jmp     cs:__imp_??1Object@UnBCL@@UEAA@XZ; UnBCL::Object::~Object(void)
```
