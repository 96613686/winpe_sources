# AccProvpLoadDllEntryPoints

- ea: `0x180053158`
- end: `0x180053462`
- name: `AccProvpLoadDllEntryPoints`
- size: `778`
- prototype: `DWORD __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180053004`
- `0x1800530b4`
- `0x180053468`

## callees

- `0x180053158`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180053456`
- `KERNEL32!GetProcAddress` at `0x18005316c`
- `KERNEL32!GetProcAddress` at `0x180053190`
- `KERNEL32!GetProcAddress` at `0x1800531b4`
- `KERNEL32!GetProcAddress` at `0x1800531d8`
- `KERNEL32!GetProcAddress` at `0x1800531fc`
- `KERNEL32!GetProcAddress` at `0x180053220`
- `KERNEL32!GetProcAddress` at `0x180053244`
- `KERNEL32!GetProcAddress` at `0x180053268`
- `KERNEL32!GetProcAddress` at `0x18005328c`
- `KERNEL32!GetProcAddress` at `0x1800532b0`
- `KERNEL32!GetProcAddress` at `0x1800532d4`
- `KERNEL32!GetProcAddress` at `0x1800532f8`
- `KERNEL32!GetProcAddress` at `0x180053326`
- `KERNEL32!GetProcAddress` at `0x18005334d`
- `KERNEL32!GetProcAddress` at `0x180053374`
- `KERNEL32!GetProcAddress` at `0x18005339b`
- `KERNEL32!GetProcAddress` at `0x1800533c2`
- `KERNEL32!GetProcAddress` at `0x1800533e5`
- `KERNEL32!GetProcAddress` at `0x180053408`
- `KERNEL32!GetProcAddress` at `0x18005342b`
- `KERNEL32!GetProcAddress` at `0x18005316c`
- `KERNEL32!GetProcAddress` at `0x180053190`
- `KERNEL32!GetProcAddress` at `0x1800531b4`
- `KERNEL32!GetProcAddress` at `0x1800531d8`
- `KERNEL32!GetProcAddress` at `0x1800531fc`
- `KERNEL32!GetProcAddress` at `0x180053220`
- `KERNEL32!GetProcAddress` at `0x180053244`
- `KERNEL32!GetProcAddress` at `0x180053268`
- `KERNEL32!GetProcAddress` at `0x18005328c`
- `KERNEL32!GetProcAddress` at `0x1800532b0`
- `KERNEL32!GetProcAddress` at `0x1800532d4`
- `KERNEL32!GetProcAddress` at `0x1800532f8`
- `KERNEL32!GetProcAddress` at `0x180053326`
- `KERNEL32!GetProcAddress` at `0x18005334d`
- `KERNEL32!GetProcAddress` at `0x180053374`
- `KERNEL32!GetProcAddress` at `0x18005339b`
- `KERNEL32!GetProcAddress` at `0x1800533c2`
- `KERNEL32!GetProcAddress` at `0x1800533e5`
- `KERNEL32!GetProcAddress` at `0x180053408`
- `KERNEL32!GetProcAddress` at `0x18005342b`
- `KERNEL32!SetLastError` at `0x180053445`
- `KERNEL32!SetLastError` at `0x180053445`

## string_xrefs

- `0x180053161`: `AccProvGrantAccessRights`
- `0x180053189`: `AccProvSetAccessRights`
- `0x1800531ad`: `AccProvRevokeAccessRights`
- `0x180053219`: `AccProvIsObjectAccessible`
- `0x18005323d`: `AccProvHandleIsObjectAccessible`
- `0x180053261`: `AccProvGetTrusteesAccess`
- `0x180053285`: `AccProvIsAccessAudited`
- `0x1800532a9`: `AccProvGetAccessInfoPerObjectType`
- `0x18005331f`: `AccProvHandleGrantAccessRights`
- `0x180053346`: `AccProvHandleSetAccessRights`
- `0x180053394`: `AccProvHandleRevokeAccessRights`
- `0x1800533de`: `AccProvHandleGetTrusteesAccess`
- `0x180053401`: `AccProvHandleIsAccessAudited`
- `0x180053424`: `AccProvHandleGetAccessInfoPerObjectType`

## pseudocode

```c
DWORD __fastcall AccProvpLoadDllEntryPoints(__int64 a1)
{
  FARPROC ProcAddress; // rax
  FARPROC v3; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax
  FARPROC v17; // rax
  FARPROC v18; // rax
  FARPROC v19; // rax
  FARPROC v20; // rax
  FARPROC v21; // rax

  ProcAddress = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvGrantAccessRights");
  *(_QWORD *)(a1 + 64) = ProcAddress;
  if ( ProcAddress )
  {
    v3 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvSetAccessRights");
    *(_QWORD *)(a1 + 72) = v3;
    if ( v3 )
    {
      v4 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvRevokeAccessRights");
      *(_QWORD *)(a1 + 80) = v4;
      if ( v4 )
      {
        v5 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvRevokeAuditRights");
        *(_QWORD *)(a1 + 88) = v5;
        if ( v5 )
        {
          v6 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvGetAllRights");
          *(_QWORD *)(a1 + 96) = v6;
          if ( v6 )
          {
            v7 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvIsObjectAccessible");
            *(_QWORD *)(a1 + 32) = v7;
            if ( v7 )
            {
              v8 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvHandleIsObjectAccessible");
              *(_QWORD *)(a1 + 40) = v8;
              if ( v8 )
              {
                v9 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvGetTrusteesAccess");
                *(_QWORD *)(a1 + 104) = v9;
                if ( v9 )
                {
                  v10 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvIsAccessAudited");
                  *(_QWORD *)(a1 + 112) = v10;
                  if ( v10 )
                  {
                    v11 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvGetAccessInfoPerObjectType");
                    *(_QWORD *)(a1 + 120) = v11;
                    if ( v11 )
                    {
                      v12 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvCancelOperation");
                      *(_QWORD *)(a1 + 48) = v12;
                      if ( v12 )
                      {
                        v13 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvGetOperationResults");
                        *(_QWORD *)(a1 + 56) = v13;
                        if ( v13 )
                        {
                          if ( (*(_BYTE *)(a1 + 24) & 2) == 0 )
                            goto LABEL_22;
                          v14 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvHandleGrantAccessRights");
                          *(_QWORD *)(a1 + 128) = v14;
                          if ( v14 )
                          {
                            v15 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvHandleSetAccessRights");
                            *(_QWORD *)(a1 + 136) = v15;
                            if ( v15 )
                            {
                              v16 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvHandleRevokeAuditRights");
                              *(_QWORD *)(a1 + 144) = v16;
                              if ( v16 )
                              {
                                v17 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvHandleRevokeAccessRights");
                                *(_QWORD *)(a1 + 152) = v17;
                                if ( v17 )
                                {
                                  v18 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvHandleGetAllRights");
                                  *(_QWORD *)(a1 + 160) = v18;
                                  if ( v18 )
                                  {
                                    v19 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvHandleGetTrusteesAccess");
                                    *(_QWORD *)(a1 + 168) = v19;
                                    if ( v19 )
                                    {
                                      v20 = GetProcAddress(*(HMODULE *)(a1 + 16), "AccProvHandleIsAccessAudited");
                                      *(_QWORD *)(a1 + 176) = v20;
                                      if ( v20 )
                                      {
                                        v21 = GetProcAddress(
                                                *(HMODULE *)(a1 + 16),
                                                "AccProvHandleGetAccessInfoPerObjectType");
                                        *(_QWORD *)(a1 + 184) = v21;
                                        if ( v21 )
LABEL_22:
                                          SetLastError(0);
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return GetLastError();
}

```

## disassembly

```asm
0x180053158  push    rbx
0x18005315a  sub     rsp, 20h
0x18005315e  mov     rbx, rcx
0x180053161  lea     rdx, aAccprovgrantac; "AccProvGrantAccessRights"
0x180053168  mov     rcx, [rcx+10h]; hModule
0x18005316c  call    cs:__imp_GetProcAddress
0x180053173  nop     dword ptr [rax+rax+00h]
0x180053178  mov     [rbx+40h], rax
0x18005317c  test    rax, rax
0x18005317f  jz      loc_180053451
0x180053185  mov     rcx, [rbx+10h]; hModule
0x180053189  lea     rdx, aAccprovsetacce; "AccProvSetAccessRights"
0x180053190  call    cs:__imp_GetProcAddress
0x180053197  nop     dword ptr [rax+rax+00h]
0x18005319c  mov     [rbx+48h], rax
0x1800531a0  test    rax, rax
0x1800531a3  jz      loc_180053451
0x1800531a9  mov     rcx, [rbx+10h]; hModule
0x1800531ad  lea     rdx, aAccprovrevokea_0; "AccProvRevokeAccessRights"
0x1800531b4  call    cs:__imp_GetProcAddress
0x1800531bb  nop     dword ptr [rax+rax+00h]
0x1800531c0  mov     [rbx+50h], rax
0x1800531c4  test    rax, rax
0x1800531c7  jz      loc_180053451
0x1800531cd  mov     rcx, [rbx+10h]; hModule
0x1800531d1  lea     rdx, aAccprovrevokea; "AccProvRevokeAuditRights"
0x1800531d8  call    cs:__imp_GetProcAddress
0x1800531df  nop     dword ptr [rax+rax+00h]
0x1800531e4  mov     [rbx+58h], rax
0x1800531e8  test    rax, rax
0x1800531eb  jz      loc_180053451
0x1800531f1  mov     rcx, [rbx+10h]; hModule
0x1800531f5  lea     rdx, aAccprovgetallr; "AccProvGetAllRights"
0x1800531fc  call    cs:__imp_GetProcAddress
0x180053203  nop     dword ptr [rax+rax+00h]
0x180053208  mov     [rbx+60h], rax
0x18005320c  test    rax, rax
0x18005320f  jz      loc_180053451
0x180053215  mov     rcx, [rbx+10h]; hModule
0x180053219  lea     rdx, aAccprovisobjec; "AccProvIsObjectAccessible"
0x180053220  call    cs:__imp_GetProcAddress
0x180053227  nop     dword ptr [rax+rax+00h]
0x18005322c  mov     [rbx+20h], rax
0x180053230  test    rax, rax
0x180053233  jz      loc_180053451
0x180053239  mov     rcx, [rbx+10h]; hModule
0x18005323d  lea     rdx, aAccprovhandlei; "AccProvHandleIsObjectAccessible"
0x180053244  call    cs:__imp_GetProcAddress
0x18005324b  nop     dword ptr [rax+rax+00h]
0x180053250  mov     [rbx+28h], rax
0x180053254  test    rax, rax
0x180053257  jz      loc_180053451
0x18005325d  mov     rcx, [rbx+10h]; hModule
0x180053261  lea     rdx, aAccprovgettrus; "AccProvGetTrusteesAccess"
0x180053268  call    cs:__imp_GetProcAddress
0x18005326f  nop     dword ptr [rax+rax+00h]
0x180053274  mov     [rbx+68h], rax
0x180053278  test    rax, rax
0x18005327b  jz      loc_180053451
0x180053281  mov     rcx, [rbx+10h]; hModule
0x180053285  lea     rdx, aAccprovisacces; "AccProvIsAccessAudited"
0x18005328c  call    cs:__imp_GetProcAddress
0x180053293  nop     dword ptr [rax+rax+00h]
0x180053298  mov     [rbx+70h], rax
0x18005329c  test    rax, rax
0x18005329f  jz      loc_180053451
0x1800532a5  mov     rcx, [rbx+10h]; hModule
0x1800532a9  lea     rdx, aAccprovgetacce; "AccProvGetAccessInfoPerObjectType"
0x1800532b0  call    cs:__imp_GetProcAddress
0x1800532b7  nop     dword ptr [rax+rax+00h]
0x1800532bc  mov     [rbx+78h], rax
0x1800532c0  test    rax, rax
0x1800532c3  jz      loc_180053451
0x1800532c9  mov     rcx, [rbx+10h]; hModule
0x1800532cd  lea     rdx, aAccprovcancelo; "AccProvCancelOperation"
0x1800532d4  call    cs:__imp_GetProcAddress
0x1800532db  nop     dword ptr [rax+rax+00h]
0x1800532e0  mov     [rbx+30h], rax
0x1800532e4  test    rax, rax
0x1800532e7  jz      loc_180053451
0x1800532ed  mov     rcx, [rbx+10h]; hModule
0x1800532f1  lea     rdx, aAccprovgetoper; "AccProvGetOperationResults"
0x1800532f8  call    cs:__imp_GetProcAddress
0x1800532ff  nop     dword ptr [rax+rax+00h]
0x180053304  mov     [rbx+38h], rax
0x180053308  test    rax, rax
0x18005330b  jz      loc_180053451
0x180053311  test    byte ptr [rbx+18h], 2
0x180053315  jz      loc_180053443
0x18005331b  mov     rcx, [rbx+10h]; hModule
0x18005331f  lea     rdx, aAccprovhandleg_1; "AccProvHandleGrantAccessRights"
0x180053326  call    cs:__imp_GetProcAddress
0x18005332d  nop     dword ptr [rax+rax+00h]
0x180053332  mov     [rbx+80h], rax
0x180053339  test    rax, rax
0x18005333c  jz      loc_180053451
0x180053342  mov     rcx, [rbx+10h]; hModule
0x180053346  lea     rdx, aAccprovhandles; "AccProvHandleSetAccessRights"
0x18005334d  call    cs:__imp_GetProcAddress
0x180053354  nop     dword ptr [rax+rax+00h]
0x180053359  mov     [rbx+88h], rax
0x180053360  test    rax, rax
0x180053363  jz      loc_180053451
0x180053369  mov     rcx, [rbx+10h]; hModule
0x18005336d  lea     rdx, aAccprovhandler; "AccProvHandleRevokeAuditRights"
0x180053374  call    cs:__imp_GetProcAddress
0x18005337b  nop     dword ptr [rax+rax+00h]
0x180053380  mov     [rbx+90h], rax
0x180053387  test    rax, rax
0x18005338a  jz      loc_180053451
0x180053390  mov     rcx, [rbx+10h]; hModule
0x180053394  lea     rdx, aAccprovhandler_0; "AccProvHandleRevokeAccessRights"
0x18005339b  call    cs:__imp_GetProcAddress
0x1800533a2  nop     dword ptr [rax+rax+00h]
0x1800533a7  mov     [rbx+98h], rax
0x1800533ae  test    rax, rax
0x1800533b1  jz      loc_180053451
0x1800533b7  mov     rcx, [rbx+10h]; hModule
0x1800533bb  lea     rdx, aAccprovhandleg_2; "AccProvHandleGetAllRights"
0x1800533c2  call    cs:__imp_GetProcAddress
0x1800533c9  nop     dword ptr [rax+rax+00h]
0x1800533ce  mov     [rbx+0A0h], rax
0x1800533d5  test    rax, rax
0x1800533d8  jz      short loc_180053451
0x1800533da  mov     rcx, [rbx+10h]; hModule
0x1800533de  lea     rdx, aAccprovhandleg_0; "AccProvHandleGetTrusteesAccess"
0x1800533e5  call    cs:__imp_GetProcAddress
0x1800533ec  nop     dword ptr [rax+rax+00h]
0x1800533f1  mov     [rbx+0A8h], rax
0x1800533f8  test    rax, rax
0x1800533fb  jz      short loc_180053451
0x1800533fd  mov     rcx, [rbx+10h]; hModule
0x180053401  lea     rdx, aAccprovhandlei_0; "AccProvHandleIsAccessAudited"
0x180053408  call    cs:__imp_GetProcAddress
0x18005340f  nop     dword ptr [rax+rax+00h]
0x180053414  mov     [rbx+0B0h], rax
0x18005341b  test    rax, rax
0x18005341e  jz      short loc_180053451
0x180053420  mov     rcx, [rbx+10h]; hModule
0x180053424  lea     rdx, aAccprovhandleg; "AccProvHandleGetAccessInfoPerObjectType"
0x18005342b  call    cs:__imp_GetProcAddress
0x180053432  nop     dword ptr [rax+rax+00h]
0x180053437  mov     [rbx+0B8h], rax
0x18005343e  test    rax, rax
0x180053441  jz      short loc_180053451
0x180053443  xor     ecx, ecx; dwErrCode
0x180053445  call    cs:__imp_SetLastError
0x18005344c  nop     dword ptr [rax+rax+00h]
0x180053451  add     rsp, 20h
0x180053455  pop     rbx
0x180053456  jmp     cs:__imp_GetLastError
```
