# DriverPackageConfigurable

- ea: `0x140011274`
- end: `0x140011631`
- name: `DriverPackageConfigurable`
- size: `957`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140011a78`

## callees

- `0x1400070bc`
- `0x14000bcbc`
- `0x14000c354`
- `0x140011274`
- `0x140023b40`
- `0x140045ec6`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400113f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400113f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400115fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400115fc`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001137a`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400115a0`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400115cc`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001137a`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400115a0`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400115cc`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14001134e`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x1400113e4`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140011488`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x1400114ec`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14001154d`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14001134e`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x1400113e4`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140011488`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x1400114ec`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14001154d`

## string_xrefs

- `0x140011362`: `Unable to determine if driver package %ws is configurable. Err = 0x%08X`
- `0x140011574`: `Device class %ws is configurable for driver package class version %u.%u.`
- `0x1400115ba`: `Device class %ws is not configurable.`
- `0x1400115ec`: `Unable to determine if driver package %ws is configurable.`
- `0x140011421`: `Driver package %ws is not configurable.`

## pseudocode

```c
_BOOL8 __fastcall DriverPackageConfigurable(__int64 a1, size_t *a2, __int64 a3)
{
  __int64 FileTitle; // rdi
  DWORD LastError; // ebx
  __int128 *p_Buf1; // [rsp+28h] [rbp-D8h]
  int v9; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v10[2]; // [rsp+5Ch] [rbp-A4h] BYREF
  int v11; // [rsp+64h] [rbp-9Ch] BYREF
  __int128 Buf1; // [rsp+68h] [rbp-98h] BYREF
  _WORD v13[40]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v14[264]; // [rsp+D0h] [rbp-30h] BYREF

  v10[0] = 0;
  v10[1] = 0;
  v11 = 0;
  Buf1 = 0;
  v9 = 0;
  if ( (int)StringCchCopyW(v14, 0x104u, a2) < 0
    || !(unsigned int)pSetupTrimFileTitle(v14)
    || (FileTitle = pSetupGetFileTitle(v14)) == 0 )
  {
    LastError = 13;
    goto LABEL_18;
  }
  p_Buf1 = &Buf1;
  if ( !(unsigned int)DriverStoreGetObjectPropertyW(a1, 2, FileTitle, DEVPKEY_DriverPackage_ClassGuid) )
  {
    LODWORD(p_Buf1) = GetLastError();
    LastError = (unsigned int)p_Buf1;
    DevRtlWriteTextLog(
      a3,
      1,
      2,
      "Unable to determine if driver package %ws is configurable. Err = 0x%08X",
      FileTitle,
      p_Buf1,
      16,
      &v9,
      0);
    goto LABEL_18;
  }
  if ( memcmp_0(&Buf1, &GUID_DEVCLASS_EXTENSION, 0x10u) )
  {
    if ( (unsigned int)SpUtilsStringFromGuid(&Buf1, v13) )
      v13[0] = 0;
    DriverStoreGetObjectPropertyW(a1, 6, v13, DEVPKEY_DeviceClass_Configurable);
    DriverStoreGetObjectPropertyW(a1, 6, v13, DEVPKEY_DeviceClass_ConfigurableClassVersion);
    v10[0] = 0;
    DevRtlWriteTextLog(a3, 1, 2, "Device class %ws is not configurable.", v13, v10, 4, &v9, 0);
    goto LABEL_15;
  }
  if ( (unsigned int)DriverStoreGetObjectPropertyW(a1, 2, FileTitle, DEVPKEY_DriverPackage_ConfigurableFlags) )
    goto LABEL_16;
  LastError = GetLastError();
  if ( LastError == 1168 )
  {
    LastError = 0;
    v11 = 0;
  }
  if ( LastError )
  {
LABEL_16:
    DevRtlWriteTextLog(
      a3,
      1,
      2,
      "Unable to determine if driver package %ws is configurable.",
      FileTitle,
      &v11,
      4,
      &v9,
      0);
LABEL_15:
    LastError = 50;
  }
LABEL_18:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x140011274  mov     [rsp-8+arg_18], rbx
0x140011279  push    rbp
0x14001127a  push    rdi
0x14001127b  push    r12
0x14001127d  push    r14
0x14001127f  push    r15
0x140011281  lea     rbp, [rsp-1F0h]
0x140011289  sub     rsp, 2F0h
0x140011290  mov     rax, cs:__security_cookie
0x140011297  xor     rax, rsp
0x14001129a  mov     [rbp+210h+var_30], rax
0x1400112a1  xor     r15d, r15d
0x1400112a4  mov     r14, r8
0x1400112a7  mov     r8, rdx; unsigned __int16 *
0x1400112aa  mov     [rsp+310h+var_2C0], r15b
0x1400112af  mov     rbx, rcx
0x1400112b2  mov     [rsp+310h+var_2B4], r15d
0x1400112b7  xorps   xmm0, xmm0
0x1400112ba  mov     [rsp+310h+var_2B0], r15d
0x1400112bf  mov     edx, 104h; unsigned __int64
0x1400112c4  mov     [rsp+310h+var_2AC], r15d
0x1400112c9  lea     rcx, [rbp+210h+var_240]; unsigned __int16 *
0x1400112cd  mov     [rsp+310h+var_2BC], r15d
0x1400112d2  movups  [rsp+310h+Buf1], xmm0
0x1400112d7  mov     [rsp+310h+var_2B8], r15d
0x1400112dc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400112e1  test    eax, eax
0x1400112e3  js      loc_1400115F5
0x1400112e9  lea     rcx, [rbp+210h+var_240]
0x1400112ed  call    pSetupTrimFileTitle
0x1400112f2  test    eax, eax
0x1400112f4  jz      loc_1400115F5
0x1400112fa  lea     rcx, [rbp+210h+var_240]
0x1400112fe  call    pSetupGetFileTitle
0x140011303  mov     rdi, rax
0x140011306  test    rax, rax
0x140011309  jz      loc_1400115F5
0x14001130f  mov     [rsp+310h+var_2D0], r15d
0x140011314  lea     rax, [rsp+310h+var_2B8]
0x140011319  mov     [rsp+310h+var_2D8], rax
0x14001131e  lea     r12d, [r15+2]
0x140011322  lea     rax, [rsp+310h+Buf1]
0x140011327  mov     [rsp+310h+var_2E0], 10h
0x14001132f  mov     [rsp+310h+var_2E8], rax
0x140011334  lea     r9, DEVPKEY_DriverPackage_ClassGuid
0x14001133b  lea     rax, [rsp+310h+var_2BC]
0x140011340  mov     r8, rdi
0x140011343  mov     edx, r12d
0x140011346  mov     [rsp+310h+var_2F0], rax
0x14001134b  mov     rcx, rbx
0x14001134e  call    cs:__imp_DriverStoreGetObjectPropertyW
0x140011354  test    eax, eax
0x140011356  jnz     short loc_140011385
0x140011358  call    cs:__imp_GetLastError
0x14001135e  mov     dword ptr [rsp+310h+var_2E8], eax
0x140011362  lea     r9, aUnableToDeterm_9; "Unable to determine if driver package %"...
0x140011369  mov     r8d, r12d
0x14001136c  mov     [rsp+310h+var_2F0], rdi
0x140011371  lea     edx, [r15+1]
0x140011375  mov     rcx, r14
0x140011378  mov     ebx, eax
0x14001137a  call    cs:__imp_DevRtlWriteTextLog
0x140011380  jmp     loc_1400115FA
0x140011385  mov     r8d, 10h; Size
0x14001138b  lea     rdx, GUID_DEVCLASS_EXTENSION; Buf2
0x140011392  lea     rcx, [rsp+310h+Buf1]; Buf1
0x140011397  call    memcmp_0
0x14001139c  test    eax, eax
0x14001139e  jnz     loc_140011433
0x1400113a4  mov     [rsp+310h+var_2C0], 0FFh
0x1400113a9  mov     [rsp+310h+var_2D0], r15d
0x1400113ae  lea     rax, [rsp+310h+var_2B8]
0x1400113b3  mov     [rsp+310h+var_2D8], rax
0x1400113b8  lea     r9, DEVPKEY_DriverPackage_ConfigurableFlags
0x1400113bf  lea     rax, [rsp+310h+var_2AC]
0x1400113c4  mov     [rsp+310h+var_2E0], 4
0x1400113cc  mov     [rsp+310h+var_2E8], rax
0x1400113d1  mov     r8, rdi
0x1400113d4  lea     rax, [rsp+310h+var_2BC]
0x1400113d9  mov     edx, r12d
0x1400113dc  mov     rcx, rbx
0x1400113df  mov     [rsp+310h+var_2F0], rax
0x1400113e4  call    cs:__imp_DriverStoreGetObjectPropertyW
0x1400113ea  test    eax, eax
0x1400113ec  jnz     loc_1400115D9
0x1400113f2  call    cs:__imp_GetLastError
0x1400113f8  mov     ebx, eax
0x1400113fa  cmp     eax, 490h
0x1400113ff  jnz     short loc_140011409
0x140011401  mov     ebx, r15d
0x140011404  mov     [rsp+310h+var_2AC], r15d
0x140011409  test    ebx, ebx
0x14001140b  jnz     loc_1400115E7
0x140011411  cmp     [rsp+310h+var_2AC], r15d
0x140011416  jz      loc_1400115FA
0x14001141c  mov     [rsp+310h+var_2F0], rdi
0x140011421  lea     r9, aDriverPackageW_2; "Driver package %ws is not configurable."
0x140011428  mov     r8d, 5
0x14001142e  jmp     loc_1400115C4
0x140011433  lea     rdx, [rbp+210h+var_290]
0x140011437  lea     rcx, [rsp+310h+Buf1]
0x14001143c  call    SpUtilsStringFromGuid
0x140011441  test    eax, eax
0x140011443  jz      short loc_14001144A
0x140011445  mov     [rbp+210h+var_290], r15w
0x14001144a  mov     [rsp+310h+var_2D0], r15d
0x14001144f  lea     rax, [rsp+310h+var_2B8]
0x140011454  mov     [rsp+310h+var_2D8], rax
0x140011459  lea     r9, DEVPKEY_DeviceClass_Configurable
0x140011460  lea     rax, [rsp+310h+var_2C0]
0x140011465  mov     [rsp+310h+var_2E0], 1
0x14001146d  mov     [rsp+310h+var_2E8], rax
0x140011472  lea     r8, [rbp+210h+var_290]
0x140011476  lea     rax, [rsp+310h+var_2BC]
0x14001147b  mov     edx, 6
0x140011480  mov     rcx, rbx
0x140011483  mov     [rsp+310h+var_2F0], rax
0x140011488  call    cs:__imp_DriverStoreGetObjectPropertyW
0x14001148e  test    eax, eax
0x140011490  jz      short loc_14001149F
0x140011492  cmp     [rsp+310h+var_2BC], 11h
0x140011497  jnz     short loc_14001149F
0x140011499  mov     al, [rsp+310h+var_2C0]
0x14001149d  jmp     short loc_1400114A6
0x14001149f  mov     al, r15b
0x1400114a2  mov     [rsp+310h+var_2C0], al
0x1400114a6  test    al, al
0x1400114a8  jnz     loc_1400113A9
0x1400114ae  mov     [rsp+310h+var_2D0], r15d
0x1400114b3  lea     rax, [rsp+310h+var_2B8]
0x1400114b8  mov     [rsp+310h+var_2D8], rax
0x1400114bd  lea     r9, DEVPKEY_DeviceClass_ConfigurableClassVersion
0x1400114c4  lea     rax, [rsp+310h+var_2B4]
0x1400114c9  mov     [rsp+310h+var_2E0], 4
0x1400114d1  mov     [rsp+310h+var_2E8], rax
0x1400114d6  lea     r8, [rbp+210h+var_290]
0x1400114da  lea     rax, [rsp+310h+var_2BC]
0x1400114df  mov     edx, 6
0x1400114e4  mov     rcx, rbx
0x1400114e7  mov     [rsp+310h+var_2F0], rax
0x1400114ec  call    cs:__imp_DriverStoreGetObjectPropertyW
0x1400114f2  test    eax, eax
0x1400114f4  jz      short loc_140011503
0x1400114f6  cmp     [rsp+310h+var_2BC], 7
0x1400114fb  jnz     short loc_140011503
0x1400114fd  mov     eax, [rsp+310h+var_2B4]
0x140011501  jmp     short loc_14001150A
0x140011503  mov     eax, r15d
0x140011506  mov     [rsp+310h+var_2B4], eax
0x14001150a  test    eax, eax
0x14001150c  jz      loc_1400115A6
0x140011512  mov     [rsp+310h+var_2D0], r15d
0x140011517  lea     rax, [rsp+310h+var_2B8]
0x14001151c  mov     [rsp+310h+var_2D8], rax
0x140011521  lea     r9, DEVPKEY_DriverPackage_ClassVersion
0x140011528  lea     rax, [rsp+310h+var_2B0]
0x14001152d  mov     [rsp+310h+var_2E0], 4
0x140011535  mov     [rsp+310h+var_2E8], rax
0x14001153a  mov     r8, rdi
0x14001153d  lea     rax, [rsp+310h+var_2BC]
0x140011542  mov     edx, r12d
0x140011545  mov     rcx, rbx
0x140011548  mov     [rsp+310h+var_2F0], rax
0x14001154d  call    cs:__imp_DriverStoreGetObjectPropertyW
0x140011553  test    eax, eax
0x140011555  jz      short loc_140011564
0x140011557  cmp     [rsp+310h+var_2BC], 7
0x14001155c  jnz     short loc_140011564
0x14001155e  mov     ecx, [rsp+310h+var_2B0]
0x140011562  jmp     short loc_14001156B
0x140011564  mov     ecx, r15d
0x140011567  mov     [rsp+310h+var_2B0], ecx
0x14001156b  cmp     ecx, [rsp+310h+var_2B4]
0x14001156f  jb      short loc_1400115A6
0x140011571  movzx   eax, cx
0x140011574  lea     r9, aDeviceClassWsI; "Device class %ws is configurable for dr"...
0x14001157b  mov     [rsp+310h+var_2E0], eax
0x14001157f  mov     edx, 1
0x140011584  shr     ecx, 10h
0x140011587  lea     rax, [rbp+210h+var_290]
0x14001158b  mov     dword ptr [rsp+310h+var_2E8], ecx
0x14001158f  mov     rcx, r14
0x140011592  mov     [rsp+310h+var_2C0], 0FFh
0x140011597  lea     r8d, [rdx+3]
0x14001159b  mov     [rsp+310h+var_2F0], rax
0x1400115a0  call    cs:__imp_DevRtlWriteTextLog
0x1400115a6  cmp     [rsp+310h+var_2C0], r15b
0x1400115ab  jnz     loc_1400113A9
0x1400115b1  lea     rax, [rbp+210h+var_290]
0x1400115b5  mov     [rsp+310h+var_2F0], rax
0x1400115ba  lea     r9, aDeviceClassWsI_0; "Device class %ws is not configurable."
0x1400115c1  mov     r8d, r12d
0x1400115c4  mov     edx, 1
0x1400115c9  mov     rcx, r14
0x1400115cc  call    cs:__imp_DevRtlWriteTextLog
0x1400115d2  mov     ebx, 32h ; '2'
0x1400115d7  jmp     short loc_1400115FA
0x1400115d9  cmp     [rsp+310h+var_2BC], 7
0x1400115de  mov     ebx, r15d
0x1400115e1  jz      loc_140011411
0x1400115e7  mov     [rsp+310h+var_2F0], rdi
0x1400115ec  lea     r9, aUnableToDeterm_7; "Unable to determine if driver package %"...
0x1400115f3  jmp     short loc_1400115C1
0x1400115f5  mov     ebx, 0Dh
0x1400115fa  mov     ecx, ebx; dwErrCode
0x1400115fc  call    cs:__imp_SetLastError
0x140011602  test    ebx, ebx
0x140011604  mov     eax, r15d
0x140011607  setz    al
0x14001160a  mov     rcx, [rbp+210h+var_30]
0x140011611  xor     rcx, rsp; StackCookie
0x140011614  call    __security_check_cookie
0x140011619  mov     rbx, [rsp+310h+arg_18]
0x140011621  add     rsp, 2F0h
0x140011628  pop     r15
0x14001162a  pop     r14
0x14001162c  pop     r12
0x14001162e  pop     rdi
0x14001162f  pop     rbp
0x140011630  retn
```
