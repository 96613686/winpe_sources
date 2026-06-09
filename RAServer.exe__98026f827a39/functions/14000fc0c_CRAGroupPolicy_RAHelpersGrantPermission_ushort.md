# CRAGroupPolicy::RAHelpersGrantPermission(ushort *)

- ea: `0x14000fc0c`
- end: `0x14000fceb`
- name: `?RAHelpersGrantPermission@CRAGroupPolicy@@AEAAKPEAG@Z`
- size: `223`
- prototype: `__int64 __fastcall(CRAGroupPolicy *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000ff18`

## callees

- `0x14000f2c8`
- `0x14000fc0c`
- `0x140010868`
- `0x140010ca4`
- `0x140010dc4`
- `0x140015240`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14000fccd`
- `KERNEL32!GetProcessHeap` at `0x14000fccd`
- `KERNEL32!HeapFree` at `0x14000fcdd`
- `KERNEL32!HeapFree` at `0x14000fcdd`

## string_xrefs

- `0x14000fc44`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000fc7b`: `AccessPermission`

## pseudocode

```c
__int64 __fastcall CRAGroupPolicy::RAHelpersGrantPermission(CRAGroupPolicy *this, unsigned __int16 *a2)
{
  struct _EVENT_DESCRIPTOR *v2; // rdx
  CEventLogger *v3; // rcx
  unsigned int PrincipalSID; // ebx
  unsigned int v5; // r9d
  unsigned __int16 *v6; // r8
  unsigned __int16 *v7; // r8
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+40h] [rbp+8h] BYREF

  lpMem = 0;
  PrincipalSID = CRAGroupPolicy::GetPrincipalSID(this, a2, &lpMem);
  if ( PrincipalSID )
  {
    v5 = 1492;
LABEL_3:
    CEventLogger::LogError(
      v3,
      v2,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      v5,
      L"CRAGroupPolicy::RAHelpersGrantPermission",
      0);
    goto LABEL_13;
  }
  PrincipalSID = CRAGroupPolicy::SetDCOMServerPermissions(v3, &v2->Id, L"LaunchPermission", lpMem);
  if ( PrincipalSID )
  {
    v5 = 1504;
    goto LABEL_3;
  }
  PrincipalSID = CRAGroupPolicy::SetDCOMServerPermissions(v3, &v2->Id, L"AccessPermission", lpMem);
  if ( PrincipalSID )
  {
    v5 = 1516;
    goto LABEL_3;
  }
  PrincipalSID = CRAGroupPolicy::SetIdentity(v3, &v2->Id, v6);
  if ( PrincipalSID )
  {
    v5 = 1528;
    goto LABEL_3;
  }
  PrincipalSID = CRAGroupPolicy::SetMachinePermissions(v3, &v2->Id, v7, lpMem);
  if ( PrincipalSID )
  {
    v5 = 1540;
    goto LABEL_3;
  }
  PrincipalSID = 0;
LABEL_13:
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  return PrincipalSID;
}

```

## disassembly

```asm
0x14000fc0c  mov     [rsp+lpMem], rcx
0x14000fc11  push    rbx
0x14000fc12  sub     rsp, 30h
0x14000fc16  lea     r8, [rsp+38h+lpMem]; void **
0x14000fc1b  mov     [rsp+38h+lpMem], 0
0x14000fc24  call    ?GetPrincipalSID@CRAGroupPolicy@@AEAAKPEAGPEAPEAX@Z; CRAGroupPolicy::GetPrincipalSID(ushort *,void * *)
0x14000fc29  mov     ebx, eax
0x14000fc2b  test    eax, eax
0x14000fc2d  jz      short loc_14000FC57
0x14000fc2f  mov     r9d, 5D4h; unsigned int
0x14000fc35  lea     rax, aCragrouppolicy_5; "CRAGroupPolicy::RAHelpersGrantPermissio"...
0x14000fc3c  mov     [rsp+38h+var_10], 0; unsigned int
0x14000fc44  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000fc4b  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x14000fc50  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000fc55  jmp     short loc_14000FCC5
0x14000fc57  mov     r9, [rsp+38h+lpMem]; void *
0x14000fc5c  lea     r8, aLaunchpermissi; "LaunchPermission"
0x14000fc63  call    ?SetDCOMServerPermissions@CRAGroupPolicy@@AEAAKPEAG0PEAX@Z; CRAGroupPolicy::SetDCOMServerPermissions(ushort *,ushort *,void *)
0x14000fc68  mov     ebx, eax
0x14000fc6a  test    eax, eax
0x14000fc6c  jz      short loc_14000FC76
0x14000fc6e  mov     r9d, 5E0h
0x14000fc74  jmp     short loc_14000FC35
0x14000fc76  mov     r9, [rsp+38h+lpMem]; void *
0x14000fc7b  lea     r8, aAccesspermissi; "AccessPermission"
0x14000fc82  call    ?SetDCOMServerPermissions@CRAGroupPolicy@@AEAAKPEAG0PEAX@Z; CRAGroupPolicy::SetDCOMServerPermissions(ushort *,ushort *,void *)
0x14000fc87  mov     ebx, eax
0x14000fc89  test    eax, eax
0x14000fc8b  jz      short loc_14000FC95
0x14000fc8d  mov     r9d, 5ECh
0x14000fc93  jmp     short loc_14000FC35
0x14000fc95  call    ?SetIdentity@CRAGroupPolicy@@AEAAKPEAG0@Z; CRAGroupPolicy::SetIdentity(ushort *,ushort *)
0x14000fc9a  mov     ebx, eax
0x14000fc9c  test    eax, eax
0x14000fc9e  jz      short loc_14000FCA8
0x14000fca0  mov     r9d, 5F8h
0x14000fca6  jmp     short loc_14000FC35
0x14000fca8  mov     r9, [rsp+38h+lpMem]; void *
0x14000fcad  call    ?SetMachinePermissions@CRAGroupPolicy@@AEAAKPEAG0PEAX@Z; CRAGroupPolicy::SetMachinePermissions(ushort *,ushort *,void *)
0x14000fcb2  mov     ebx, eax
0x14000fcb4  test    eax, eax
0x14000fcb6  jz      short loc_14000FCC3
0x14000fcb8  mov     r9d, 604h
0x14000fcbe  jmp     loc_14000FC35
0x14000fcc3  xor     ebx, ebx
0x14000fcc5  cmp     [rsp+38h+lpMem], 0
0x14000fccb  jz      short loc_14000FCE3
0x14000fccd  call    cs:__imp_GetProcessHeap
0x14000fcd3  mov     r8, [rsp+38h+lpMem]; lpMem
0x14000fcd8  xor     edx, edx; dwFlags
0x14000fcda  mov     rcx, rax; hHeap
0x14000fcdd  call    cs:__imp_HeapFree
0x14000fce3  mov     eax, ebx
0x14000fce5  add     rsp, 30h
0x14000fce9  pop     rbx
0x14000fcea  retn
```
