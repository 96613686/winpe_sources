# ServiceManager::CancelOperation(ServiceManager::CANCELLATION_TYPE)

- ea: `0x180013400`
- end: `0x1800134b0`
- name: `?CancelOperation@ServiceManager@@AEAAJW4CANCELLATION_TYPE@1@@Z`
- size: `176`
- prototype: `__int64 __fastcall(_DWORD *, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180013340`
- `0x1800134b8`
- `0x180013580`

## callees

- `0x18000b61c`
- `0x180013400`

## import_xrefs

- `MapsStore!MapsStore_CancelInstallation` at `0x18001345d`
- `MapsStore!MapsStore_CancelInstallation` at `0x18001345d`
- `MapsStore!MapsStore_SuspendInstallation` at `0x180013483`
- `MapsStore!MapsStore_SuspendInstallation` at `0x180013483`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180013479`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180013479`

## string_xrefs

- `0x180013470`: `ServiceManager::CancelOperation`

## pseudocode

```c
__int64 __fastcall ServiceManager::CancelOperation(_DWORD *a1, int a2)
{
  unsigned int v2; // r8d
  unsigned int v3; // edi
  unsigned int v5; // r8d
  unsigned int v6; // r8d
  int v7; // eax
  int v8; // r8d

  v2 = a1[881];
  v3 = 0;
  if ( v2 > 2 )
  {
    a1[883] = a2;
    v5 = v2 - 3;
    if ( !v5 )
    {
      __int2c();
      return v3;
    }
    v6 = v5 - 1;
    if ( !v6 )
    {
      if ( a2 )
      {
        v7 = MapsStore_SuspendInstallation();
        if ( v7 < 0 )
        {
          v8 = 2541;
          return (unsigned int)ZTraceReportOrigination(v7, "ServiceManager::CancelOperation", v8, a1);
        }
      }
      else
      {
        v7 = MapsStore_CancelInstallation();
        if ( v7 < 0 )
        {
          v8 = 2536;
          return (unsigned int)ZTraceReportOrigination(v7, "ServiceManager::CancelOperation", v8, a1);
        }
      }
      a1[881] = 6;
      return v3;
    }
    if ( v6 - 5 <= 1 )
    {
      v7 = MigrationEngine::CancelMigration((MigrationEngine *)(a1 + 2), a2 == 2);
      if ( v7 < 0 )
      {
        v8 = 2548;
        return (unsigned int)ZTraceReportOrigination(v7, "ServiceManager::CancelOperation", v8, a1);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180013400  mov     [rsp+arg_0], rbx
0x180013405  push    rdi
0x180013406  sub     rsp, 20h
0x18001340a  mov     r8d, [rcx+0DC4h]
0x180013411  xor     edi, edi
0x180013413  mov     rbx, rcx
0x180013416  cmp     r8d, 2
0x18001341a  jbe     loc_1800134A3
0x180013420  mov     [rcx+0DCCh], edx
0x180013426  sub     r8d, 3
0x18001342a  jz      short loc_1800134A1
0x18001342c  sub     r8d, 1
0x180013430  jz      short loc_180013459
0x180013432  sub     r8d, 5
0x180013436  jz      short loc_18001343E
0x180013438  cmp     r8d, 1
0x18001343c  jnz     short loc_1800134A3
0x18001343e  cmp     edx, 2
0x180013441  setz    dl; bool
0x180013444  add     rcx, 8; this
0x180013448  call    ?CancelMigration@MigrationEngine@@IEAAJ_N@Z; MigrationEngine::CancelMigration(bool)
0x18001344d  test    eax, eax
0x18001344f  jns     short loc_1800134A3
0x180013451  mov     r8d, 9F4h
0x180013457  jmp     short loc_18001346D
0x180013459  test    edx, edx
0x18001345b  jnz     short loc_180013483
0x18001345d  call    cs:__imp_?MapsStore_CancelInstallation@@YAJXZ; MapsStore_CancelInstallation(void)
0x180013463  test    eax, eax
0x180013465  jns     short loc_180013495
0x180013467  mov     r8d, 9E8h
0x18001346d  mov     r9, rbx
0x180013470  lea     rdx, aServicemanager_11; "ServiceManager::CancelOperation"
0x180013477  mov     ecx, eax
0x180013479  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001347f  mov     edi, eax
0x180013481  jmp     short loc_1800134A3
0x180013483  call    cs:__imp_?MapsStore_SuspendInstallation@@YAJXZ; MapsStore_SuspendInstallation(void)
0x180013489  test    eax, eax
0x18001348b  jns     short loc_180013495
0x18001348d  mov     r8d, 9EDh
0x180013493  jmp     short loc_18001346D
0x180013495  mov     dword ptr [rbx+0DC4h], 6
0x18001349f  jmp     short loc_1800134A3
0x1800134a1  int     2Ch; Windows NT - assertion failure
0x1800134a3  mov     rbx, [rsp+28h+arg_0]
0x1800134a8  mov     eax, edi
0x1800134aa  add     rsp, 20h
0x1800134ae  pop     rdi
0x1800134af  retn
```
