# CRAGroupPolicy::RAHelpersRemovePermission(ushort *)

- ea: `0x14000fcf4`
- end: `0x14000fd89`
- name: `?RAHelpersRemovePermission@CRAGroupPolicy@@AEAAKPEAG@Z`
- size: `149`
- prototype: `__int64 __fastcall(CRAGroupPolicy *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000fd90`

## callees

- `0x14000f2c8`
- `0x14000fcf4`
- `0x140010178`
- `0x140010594`
- `0x140015240`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14000fd6b`
- `KERNEL32!GetProcessHeap` at `0x14000fd6b`
- `KERNEL32!HeapFree` at `0x14000fd7b`
- `KERNEL32!HeapFree` at `0x14000fd7b`

## string_xrefs

- `0x14000fd31`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000fd17`: `CRAGroupPolicy::RAHelpersRemovePermission`
- `0x14000fd55`: `AccessPermission`

## pseudocode

```c
__int64 __fastcall CRAGroupPolicy::RAHelpersRemovePermission(CRAGroupPolicy *this, unsigned __int16 *a2)
{
  struct _EVENT_DESCRIPTOR *v2; // rdx
  CEventLogger *v3; // rcx
  unsigned int PrincipalSID; // edi
  unsigned __int16 *v5; // r8
  unsigned __int16 *v6; // rdx
  CRAGroupPolicy *v7; // rcx
  unsigned __int16 *v8; // rdx
  CRAGroupPolicy *v9; // rcx
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+40h] [rbp+8h] BYREF

  lpMem = 0;
  PrincipalSID = CRAGroupPolicy::GetPrincipalSID(this, a2, &lpMem);
  if ( PrincipalSID )
  {
    CEventLogger::LogError(
      v3,
      v2,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      0x61Au,
      L"CRAGroupPolicy::RAHelpersRemovePermission",
      0);
  }
  else
  {
    CRAGroupPolicy::RemoveMachinePermissions(v3, &v2->Id, v5, lpMem);
    CRAGroupPolicy::RemoveDCOMServerPermissions(v7, v6, L"LaunchPermission");
    CRAGroupPolicy::RemoveDCOMServerPermissions(v9, v8, L"AccessPermission");
    PrincipalSID = 0;
  }
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
0x14000fcf4  mov     [rsp+lpMem], rcx
0x14000fcf9  push    rdi
0x14000fcfa  sub     rsp, 30h
0x14000fcfe  lea     r8, [rsp+38h+lpMem]; void **
0x14000fd03  mov     [rsp+38h+lpMem], 0
0x14000fd0c  call    ?GetPrincipalSID@CRAGroupPolicy@@AEAAKPEAGPEAPEAX@Z; CRAGroupPolicy::GetPrincipalSID(ushort *,void * *)
0x14000fd11  mov     edi, eax
0x14000fd13  test    eax, eax
0x14000fd15  jz      short loc_14000FD3F
0x14000fd17  lea     rax, aCragrouppolicy; "CRAGroupPolicy::RAHelpersRemovePermissi"...
0x14000fd1e  mov     [rsp+38h+var_10], 0; unsigned int
0x14000fd26  mov     r9d, 61Ah; unsigned int
0x14000fd2c  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x14000fd31  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000fd38  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000fd3d  jmp     short loc_14000FD63
0x14000fd3f  mov     r9, [rsp+38h+lpMem]; void *
0x14000fd44  call    ?RemoveMachinePermissions@CRAGroupPolicy@@AEAAKPEAG0PEAX@Z; CRAGroupPolicy::RemoveMachinePermissions(ushort *,ushort *,void *)
0x14000fd49  lea     r8, aLaunchpermissi; "LaunchPermission"
0x14000fd50  call    ?RemoveDCOMServerPermissions@CRAGroupPolicy@@AEAAKPEAG0@Z; CRAGroupPolicy::RemoveDCOMServerPermissions(ushort *,ushort *)
0x14000fd55  lea     r8, aAccesspermissi; "AccessPermission"
0x14000fd5c  call    ?RemoveDCOMServerPermissions@CRAGroupPolicy@@AEAAKPEAG0@Z; CRAGroupPolicy::RemoveDCOMServerPermissions(ushort *,ushort *)
0x14000fd61  xor     edi, edi
0x14000fd63  cmp     [rsp+38h+lpMem], 0
0x14000fd69  jz      short loc_14000FD81
0x14000fd6b  call    cs:__imp_GetProcessHeap
0x14000fd71  mov     r8, [rsp+38h+lpMem]; lpMem
0x14000fd76  xor     edx, edx; dwFlags
0x14000fd78  mov     rcx, rax; hHeap
0x14000fd7b  call    cs:__imp_HeapFree
0x14000fd81  mov     eax, edi
0x14000fd83  add     rsp, 30h
0x14000fd87  pop     rdi
0x14000fd88  retn
```
