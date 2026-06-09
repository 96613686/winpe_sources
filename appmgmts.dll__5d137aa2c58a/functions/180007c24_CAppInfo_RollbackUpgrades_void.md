# CAppInfo::RollbackUpgrades(void)

- ea: `0x180007c24`
- end: `0x180007ddd`
- name: `?RollbackUpgrades@CAppInfo@@AEAAKXZ`
- size: `441`
- prototype: `__int64 __fastcall(CAppInfo *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180007410`

## callees

- `0x180005294`
- `0x180007110`
- `0x180007c24`
- `0x18000d734`
- `0x18001b1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007da7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007dbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007da7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007dbf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007d68`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007d68`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180007d95`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180007d95`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007d72`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007d72`

## pseudocode

```c
__int64 __fastcall CAppInfo::RollbackUpgrades(CAppInfo *this)
{
  unsigned int i; // esi
  __int64 v3; // rax
  __int64 v4; // rdi
  __int64 v5; // r9
  unsigned int v6; // ecx
  unsigned int v7; // edx
  CAppInfo *v8; // rcx
  CAppInfo *v9; // rcx
  unsigned int v10; // ecx
  __int64 v11; // rax
  __int64 v12; // rcx
  DWORD LastError; // eax

  if ( *((_QWORD *)this + 14) )
  {
    for ( i = 0; i < *((_DWORD *)this + 26); ++i )
    {
      v3 = *((_QWORD *)this + 14);
      v4 = 32LL * i;
      v5 = *(_QWORD *)(v3 + v4 + 24);
      if ( v5 && (*(_BYTE *)(v3 + v4 + 16) & 4) != 0 && (*(_BYTE *)(v5 + 224) & 3) != 0 )
      {
        v6 = *((_DWORD *)this + 58);
        v7 = v6;
        if ( !v6 )
          v7 = *(_DWORD *)(v5 + 232);
        CEvents::UpgradeAbort((CEvents *)(*((_QWORD *)this + 2) + 344LL), v7, this, (struct CAppInfo *)v5, v6 == 0);
        v8 = *(CAppInfo **)(v4 + *((_QWORD *)this + 14) + 24);
        if ( !*((_DWORD *)v8 + 58) && !(unsigned int)CAppInfo::Assign(v8, ((*((_DWORD *)v8 + 56) & 1u) << 8) + 37, 1, 1) )
        {
          if ( !*(_DWORD *)(*((_QWORD *)this + 2) + 296LL)
            || *(char *)(*(_QWORD *)(v4 + *((_QWORD *)this + 14) + 24) + 224LL) < 0 )
          {
            v9 = *(CAppInfo **)(v4 + *((_QWORD *)this + 14) + 24);
            if ( (unsigned int)(*((_DWORD *)v9 + 54) - 3) <= 2 )
              CAppInfo::Install(v9);
          }
          *(_DWORD *)(*(_QWORD *)(v4 + *((_QWORD *)this + 14) + 24) + 300LL) = 1;
        }
      }
    }
  }
  v10 = 0;
  if ( (*((_DWORD *)this + 56) & 0x600) == 0x600 && *((_QWORD *)this + 11) )
  {
    v11 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v11 + 396) != 1 && *(_DWORD *)(v11 + 296) )
      RevertToSelf();
    DeleteFileW(*((LPCWSTR *)this + 11));
    v12 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v12 + 396) == 1 || !*(_DWORD *)(v12 + 296) || ImpersonateLoggedOnUser(*(HANDLE *)(v12 + 264)) )
    {
      return 0;
    }
    else
    {
      if ( *(_DWORD *)&gDebugLevel )
      {
        LastError = GetLastError();
        _DebugMsg(2, 0xBC4u, LastError);
      }
      return GetLastError();
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180007c24  mov     [rsp+arg_0], rbx
0x180007c29  mov     [rsp+arg_8], rsi
0x180007c2e  push    rdi
0x180007c2f  sub     rsp, 30h
0x180007c33  cmp     qword ptr [rcx+70h], 0
0x180007c38  mov     rbx, rcx
0x180007c3b  jz      loc_180007D3A
0x180007c41  xor     esi, esi
0x180007c43  cmp     [rcx+68h], esi
0x180007c46  jbe     loc_180007D3A
0x180007c4c  mov     rax, [rbx+70h]
0x180007c50  mov     edi, esi
0x180007c52  shl     rdi, 5
0x180007c56  mov     r9, [rax+rdi+18h]; struct CAppInfo *
0x180007c5b  test    r9, r9
0x180007c5e  jz      loc_180007D2F
0x180007c64  test    byte ptr [rax+rdi+10h], 4
0x180007c69  jz      loc_180007D2F
0x180007c6f  test    byte ptr [r9+0E0h], 3
0x180007c77  jz      loc_180007D2F
0x180007c7d  mov     ecx, [rbx+0E8h]
0x180007c83  mov     edx, ecx
0x180007c85  test    ecx, ecx
0x180007c87  jnz     short loc_180007C90
0x180007c89  mov     edx, [r9+0E8h]; unsigned int
0x180007c90  xor     eax, eax
0x180007c92  mov     r8, rbx; struct CAppInfo *
0x180007c95  test    ecx, ecx
0x180007c97  mov     rcx, [rbx+10h]
0x180007c9b  setz    al
0x180007c9e  add     rcx, 158h; this
0x180007ca5  mov     [rsp+38h+var_18], eax; int
0x180007ca9  call    ?UpgradeAbort@CEvents@@QEAAXKPEAVCAppInfo@@0H@Z; CEvents::UpgradeAbort(ulong,CAppInfo *,CAppInfo *,int)
0x180007cae  mov     rax, [rbx+70h]
0x180007cb2  mov     rcx, [rdi+rax+18h]; this
0x180007cb7  cmp     dword ptr [rcx+0E8h], 0
0x180007cbe  jnz     short loc_180007D2F
0x180007cc0  mov     edx, [rcx+0E0h]
0x180007cc6  mov     r9d, 1; int
0x180007ccc  and     edx, 1
0x180007ccf  mov     r8d, r9d; int
0x180007cd2  shl     edx, 8
0x180007cd5  add     edx, 25h ; '%'; unsigned int
0x180007cd8  call    ?Assign@CAppInfo@@QEAAKKHH@Z; CAppInfo::Assign(ulong,int,int)
0x180007cdd  test    eax, eax
0x180007cdf  jnz     short loc_180007D2F
0x180007ce1  mov     rax, [rbx+10h]
0x180007ce5  cmp     dword ptr [rax+128h], 0
0x180007cec  jz      short loc_180007D00
0x180007cee  mov     rax, [rbx+70h]
0x180007cf2  mov     rcx, [rdi+rax+18h]
0x180007cf7  test    byte ptr [rcx+0E0h], 80h
0x180007cfe  jz      short loc_180007D1C
0x180007d00  mov     rax, [rbx+70h]
0x180007d04  mov     rcx, [rdi+rax+18h]; this
0x180007d09  mov     eax, [rcx+0D8h]
0x180007d0f  sub     eax, 3
0x180007d12  cmp     eax, 2
0x180007d15  ja      short loc_180007D1C
0x180007d17  call    ?Install@CAppInfo@@QEAAKXZ; CAppInfo::Install(void)
0x180007d1c  mov     rax, [rbx+70h]
0x180007d20  mov     rcx, [rdi+rax+18h]
0x180007d25  mov     dword ptr [rcx+12Ch], 1
0x180007d2f  inc     esi
0x180007d31  cmp     esi, [rbx+68h]
0x180007d34  jb      loc_180007C4C
0x180007d3a  mov     eax, [rbx+0E0h]
0x180007d40  mov     edx, 600h
0x180007d45  and     eax, edx
0x180007d47  xor     ecx, ecx
0x180007d49  cmp     eax, edx
0x180007d4b  jnz     short loc_180007DCB
0x180007d4d  cmp     [rbx+58h], rcx
0x180007d51  jz      short loc_180007DCB
0x180007d53  mov     rax, [rbx+10h]
0x180007d57  cmp     dword ptr [rax+18Ch], 1
0x180007d5e  jz      short loc_180007D6E
0x180007d60  cmp     [rax+128h], ecx
0x180007d66  jz      short loc_180007D6E
0x180007d68  call    cs:__imp_RevertToSelf
0x180007d6e  mov     rcx, [rbx+58h]; lpFileName
0x180007d72  call    cs:__imp_DeleteFileW
0x180007d78  mov     rcx, [rbx+10h]
0x180007d7c  cmp     dword ptr [rcx+18Ch], 1
0x180007d83  jz      short loc_180007DC9
0x180007d85  cmp     dword ptr [rcx+128h], 0
0x180007d8c  jz      short loc_180007DC9
0x180007d8e  mov     rcx, [rcx+108h]; hToken
0x180007d95  call    cs:__imp_ImpersonateLoggedOnUser
0x180007d9b  test    eax, eax
0x180007d9d  jnz     short loc_180007DC9
0x180007d9f  cmp     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x180007da5  jz      short loc_180007DBF
0x180007da7  call    cs:__imp_GetLastError
0x180007dad  mov     edx, 0BC4h; unsigned int
0x180007db2  mov     ecx, 2; unsigned int
0x180007db7  mov     r8d, eax
0x180007dba  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180007dbf  call    cs:__imp_GetLastError
0x180007dc5  mov     ecx, eax
0x180007dc7  jmp     short loc_180007DCB
0x180007dc9  xor     ecx, ecx
0x180007dcb  mov     rbx, [rsp+38h+arg_0]
0x180007dd0  mov     eax, ecx
0x180007dd2  mov     rsi, [rsp+38h+arg_8]
0x180007dd7  add     rsp, 30h
0x180007ddb  pop     rdi
0x180007ddc  retn
```
