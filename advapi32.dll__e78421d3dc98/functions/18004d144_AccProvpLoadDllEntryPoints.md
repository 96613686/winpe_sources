# AccProvpLoadDllEntryPoints

- ea: `0x18004d144`
- end: `0x18004d3c7`
- name: `AccProvpLoadDllEntryPoints`
- size: `643`
- prototype: `DWORD __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004d000`
- `0x18004d0a8`
- `0x18004d3d0`

## callees

- `0x18004d144`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004d3c0`
- `KERNEL32!GetProcAddress` at `0x18004d158`
- `KERNEL32!GetProcAddress` at `0x18004d176`
- `KERNEL32!GetProcAddress` at `0x18004d194`
- `KERNEL32!GetProcAddress` at `0x18004d1b2`
- `KERNEL32!GetProcAddress` at `0x18004d1d0`
- `KERNEL32!GetProcAddress` at `0x18004d1ee`
- `KERNEL32!GetProcAddress` at `0x18004d20c`
- `KERNEL32!GetProcAddress` at `0x18004d22a`
- `KERNEL32!GetProcAddress` at `0x18004d248`
- `KERNEL32!GetProcAddress` at `0x18004d266`
- `KERNEL32!GetProcAddress` at `0x18004d284`
- `KERNEL32!GetProcAddress` at `0x18004d2a2`
- `KERNEL32!GetProcAddress` at `0x18004d2ca`
- `KERNEL32!GetProcAddress` at `0x18004d2eb`
- `KERNEL32!GetProcAddress` at `0x18004d30c`
- `KERNEL32!GetProcAddress` at `0x18004d32d`
- `KERNEL32!GetProcAddress` at `0x18004d34a`
- `KERNEL32!GetProcAddress` at `0x18004d367`
- `KERNEL32!GetProcAddress` at `0x18004d384`
- `KERNEL32!GetProcAddress` at `0x18004d3a1`
- `KERNEL32!GetProcAddress` at `0x18004d158`
- `KERNEL32!GetProcAddress` at `0x18004d176`
- `KERNEL32!GetProcAddress` at `0x18004d194`
- `KERNEL32!GetProcAddress` at `0x18004d1b2`
- `KERNEL32!GetProcAddress` at `0x18004d1d0`
- `KERNEL32!GetProcAddress` at `0x18004d1ee`
- `KERNEL32!GetProcAddress` at `0x18004d20c`
- `KERNEL32!GetProcAddress` at `0x18004d22a`
- `KERNEL32!GetProcAddress` at `0x18004d248`
- `KERNEL32!GetProcAddress` at `0x18004d266`
- `KERNEL32!GetProcAddress` at `0x18004d284`
- `KERNEL32!GetProcAddress` at `0x18004d2a2`
- `KERNEL32!GetProcAddress` at `0x18004d2ca`
- `KERNEL32!GetProcAddress` at `0x18004d2eb`
- `KERNEL32!GetProcAddress` at `0x18004d30c`
- `KERNEL32!GetProcAddress` at `0x18004d32d`
- `KERNEL32!GetProcAddress` at `0x18004d34a`
- `KERNEL32!GetProcAddress` at `0x18004d367`
- `KERNEL32!GetProcAddress` at `0x18004d384`
- `KERNEL32!GetProcAddress` at `0x18004d3a1`
- `KERNEL32!SetLastError` at `0x18004d3b5`
- `KERNEL32!SetLastError` at `0x18004d3b5`

## string_xrefs

- `0x18004d14d`: `AccProvGrantAccessRights`
- `0x18004d16f`: `AccProvSetAccessRights`
- `0x18004d18d`: `AccProvRevokeAccessRights`
- `0x18004d1e7`: `AccProvIsObjectAccessible`
- `0x18004d205`: `AccProvHandleIsObjectAccessible`
- `0x18004d223`: `AccProvGetTrusteesAccess`
- `0x18004d241`: `AccProvIsAccessAudited`
- `0x18004d25f`: `AccProvGetAccessInfoPerObjectType`
- `0x18004d2c3`: `AccProvHandleGrantAccessRights`
- `0x18004d2e4`: `AccProvHandleSetAccessRights`
- `0x18004d326`: `AccProvHandleRevokeAccessRights`
- `0x18004d360`: `AccProvHandleGetTrusteesAccess`
- `0x18004d37d`: `AccProvHandleIsAccessAudited`
- `0x18004d39a`: `AccProvHandleGetAccessInfoPerObjectType`

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
0x18004d144  push    rbx
0x18004d146  sub     rsp, 20h
0x18004d14a  mov     rbx, rcx
0x18004d14d  lea     rdx, aAccprovgrantac; "AccProvGrantAccessRights"
0x18004d154  mov     rcx, [rcx+10h]; hModule
0x18004d158  call    cs:__imp_GetProcAddress
0x18004d15e  mov     [rbx+40h], rax
0x18004d162  test    rax, rax
0x18004d165  jz      loc_18004D3BB
0x18004d16b  mov     rcx, [rbx+10h]; hModule
0x18004d16f  lea     rdx, aAccprovsetacce; "AccProvSetAccessRights"
0x18004d176  call    cs:__imp_GetProcAddress
0x18004d17c  mov     [rbx+48h], rax
0x18004d180  test    rax, rax
0x18004d183  jz      loc_18004D3BB
0x18004d189  mov     rcx, [rbx+10h]; hModule
0x18004d18d  lea     rdx, aAccprovrevokea_0; "AccProvRevokeAccessRights"
0x18004d194  call    cs:__imp_GetProcAddress
0x18004d19a  mov     [rbx+50h], rax
0x18004d19e  test    rax, rax
0x18004d1a1  jz      loc_18004D3BB
0x18004d1a7  mov     rcx, [rbx+10h]; hModule
0x18004d1ab  lea     rdx, aAccprovrevokea; "AccProvRevokeAuditRights"
0x18004d1b2  call    cs:__imp_GetProcAddress
0x18004d1b8  mov     [rbx+58h], rax
0x18004d1bc  test    rax, rax
0x18004d1bf  jz      loc_18004D3BB
0x18004d1c5  mov     rcx, [rbx+10h]; hModule
0x18004d1c9  lea     rdx, aAccprovgetallr; "AccProvGetAllRights"
0x18004d1d0  call    cs:__imp_GetProcAddress
0x18004d1d6  mov     [rbx+60h], rax
0x18004d1da  test    rax, rax
0x18004d1dd  jz      loc_18004D3BB
0x18004d1e3  mov     rcx, [rbx+10h]; hModule
0x18004d1e7  lea     rdx, aAccprovisobjec; "AccProvIsObjectAccessible"
0x18004d1ee  call    cs:__imp_GetProcAddress
0x18004d1f4  mov     [rbx+20h], rax
0x18004d1f8  test    rax, rax
0x18004d1fb  jz      loc_18004D3BB
0x18004d201  mov     rcx, [rbx+10h]; hModule
0x18004d205  lea     rdx, aAccprovhandlei; "AccProvHandleIsObjectAccessible"
0x18004d20c  call    cs:__imp_GetProcAddress
0x18004d212  mov     [rbx+28h], rax
0x18004d216  test    rax, rax
0x18004d219  jz      loc_18004D3BB
0x18004d21f  mov     rcx, [rbx+10h]; hModule
0x18004d223  lea     rdx, aAccprovgettrus; "AccProvGetTrusteesAccess"
0x18004d22a  call    cs:__imp_GetProcAddress
0x18004d230  mov     [rbx+68h], rax
0x18004d234  test    rax, rax
0x18004d237  jz      loc_18004D3BB
0x18004d23d  mov     rcx, [rbx+10h]; hModule
0x18004d241  lea     rdx, aAccprovisacces; "AccProvIsAccessAudited"
0x18004d248  call    cs:__imp_GetProcAddress
0x18004d24e  mov     [rbx+70h], rax
0x18004d252  test    rax, rax
0x18004d255  jz      loc_18004D3BB
0x18004d25b  mov     rcx, [rbx+10h]; hModule
0x18004d25f  lea     rdx, aAccprovgetacce; "AccProvGetAccessInfoPerObjectType"
0x18004d266  call    cs:__imp_GetProcAddress
0x18004d26c  mov     [rbx+78h], rax
0x18004d270  test    rax, rax
0x18004d273  jz      loc_18004D3BB
0x18004d279  mov     rcx, [rbx+10h]; hModule
0x18004d27d  lea     rdx, aAccprovcancelo; "AccProvCancelOperation"
0x18004d284  call    cs:__imp_GetProcAddress
0x18004d28a  mov     [rbx+30h], rax
0x18004d28e  test    rax, rax
0x18004d291  jz      loc_18004D3BB
0x18004d297  mov     rcx, [rbx+10h]; hModule
0x18004d29b  lea     rdx, aAccprovgetoper; "AccProvGetOperationResults"
0x18004d2a2  call    cs:__imp_GetProcAddress
0x18004d2a8  mov     [rbx+38h], rax
0x18004d2ac  test    rax, rax
0x18004d2af  jz      loc_18004D3BB
0x18004d2b5  test    byte ptr [rbx+18h], 2
0x18004d2b9  jz      loc_18004D3B3
0x18004d2bf  mov     rcx, [rbx+10h]; hModule
0x18004d2c3  lea     rdx, aAccprovhandleg_1; "AccProvHandleGrantAccessRights"
0x18004d2ca  call    cs:__imp_GetProcAddress
0x18004d2d0  mov     [rbx+80h], rax
0x18004d2d7  test    rax, rax
0x18004d2da  jz      loc_18004D3BB
0x18004d2e0  mov     rcx, [rbx+10h]; hModule
0x18004d2e4  lea     rdx, aAccprovhandles; "AccProvHandleSetAccessRights"
0x18004d2eb  call    cs:__imp_GetProcAddress
0x18004d2f1  mov     [rbx+88h], rax
0x18004d2f8  test    rax, rax
0x18004d2fb  jz      loc_18004D3BB
0x18004d301  mov     rcx, [rbx+10h]; hModule
0x18004d305  lea     rdx, aAccprovhandler; "AccProvHandleRevokeAuditRights"
0x18004d30c  call    cs:__imp_GetProcAddress
0x18004d312  mov     [rbx+90h], rax
0x18004d319  test    rax, rax
0x18004d31c  jz      loc_18004D3BB
0x18004d322  mov     rcx, [rbx+10h]; hModule
0x18004d326  lea     rdx, aAccprovhandler_0; "AccProvHandleRevokeAccessRights"
0x18004d32d  call    cs:__imp_GetProcAddress
0x18004d333  mov     [rbx+98h], rax
0x18004d33a  test    rax, rax
0x18004d33d  jz      short loc_18004D3BB
0x18004d33f  mov     rcx, [rbx+10h]; hModule
0x18004d343  lea     rdx, aAccprovhandleg_2; "AccProvHandleGetAllRights"
0x18004d34a  call    cs:__imp_GetProcAddress
0x18004d350  mov     [rbx+0A0h], rax
0x18004d357  test    rax, rax
0x18004d35a  jz      short loc_18004D3BB
0x18004d35c  mov     rcx, [rbx+10h]; hModule
0x18004d360  lea     rdx, aAccprovhandleg_0; "AccProvHandleGetTrusteesAccess"
0x18004d367  call    cs:__imp_GetProcAddress
0x18004d36d  mov     [rbx+0A8h], rax
0x18004d374  test    rax, rax
0x18004d377  jz      short loc_18004D3BB
0x18004d379  mov     rcx, [rbx+10h]; hModule
0x18004d37d  lea     rdx, aAccprovhandlei_0; "AccProvHandleIsAccessAudited"
0x18004d384  call    cs:__imp_GetProcAddress
0x18004d38a  mov     [rbx+0B0h], rax
0x18004d391  test    rax, rax
0x18004d394  jz      short loc_18004D3BB
0x18004d396  mov     rcx, [rbx+10h]; hModule
0x18004d39a  lea     rdx, aAccprovhandleg; "AccProvHandleGetAccessInfoPerObjectType"
0x18004d3a1  call    cs:__imp_GetProcAddress
0x18004d3a7  mov     [rbx+0B8h], rax
0x18004d3ae  test    rax, rax
0x18004d3b1  jz      short loc_18004D3BB
0x18004d3b3  xor     ecx, ecx; dwErrCode
0x18004d3b5  call    cs:__imp_SetLastError
0x18004d3bb  add     rsp, 20h
0x18004d3bf  pop     rbx
0x18004d3c0  jmp     cs:__imp_GetLastError
```
