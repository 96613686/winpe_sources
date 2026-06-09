# SuplNode::InternalGetValue(SUPLNODEINFO const *,ushort const *,tagVARIANT *)

- ea: `0x18011885c`
- end: `0x180118a80`
- name: `?InternalGetValue@SuplNode@@AEAAJPEBUSUPLNODEINFO@@PEBGPEAUtagVARIANT@@@Z`
- size: `548`
- prototype: `__int64 __fastcall(SuplNode *this, const struct SUPLNODEINFO *, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a0ac0`
- `0x180118190`
- `0x180118420`
- `0x180118760`

## callees

- `0x18000f040`
- `0x180032d80`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x180117efc`
- `0x180117fbc`
- `0x180118324`
- `0x1801185f8`
- `0x18011885c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1801188c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1801188c8`
- `OLEAUT32!__imp_VariantInit` at `0x1801188b4`
- `OLEAUT32!__imp_VariantInit` at `0x1801188b4`
- `OLEAUT32!__imp_VariantClear` at `0x18011897a`
- `OLEAUT32!__imp_VariantClear` at `0x18011897a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180118a5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180118a5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180118a41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180118a41`

## string_xrefs

- `0x180118911`: `SYSTEM\CurrentControlSet\Services\lfsvc\`
- `0x180118918`: `Components\SUPL`

## pseudocode

```c
__int64 __fastcall SuplNode::InternalGetValue(
        SuplNode *this,
        const struct SUPLNODEINFO *a2,
        const unsigned __int16 *a3,
        struct tagVARIANT *a4)
{
  int PersistedRegPath; // ebx
  BSTR v8; // rax
  SuplNode *v9; // rcx
  HKEY v10; // rdx
  int v11; // ecx
  SuplNode *v12; // rcx
  SuplNode *v13; // rcx
  HKEY hKey[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v18[256]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR SubKey[264]; // [rsp+450h] [rbp+350h] BYREF

  LODWORD(hKey[0]) = 0;
  memset_0(v18, 0, 0x1FEu);
  v17[0] = 0;
  PersistedRegPath = 0;
  VariantInit(a4);
  if ( *((_DWORD *)a2 + 2) == 2 )
  {
    v8 = SysAllocString(L"ap0004");
    a4->llVal = (LONGLONG)v8;
    if ( v8 )
      a4->vt = 8;
    else
      return (unsigned int)-2147024882;
  }
  else if ( *((_DWORD *)a2 + 2) == 38 )
  {
    a4->lVal = 3;
    a4->vt = 19;
  }
  else
  {
    PersistedRegPath = CLocationPersistedRegPathHelper::GetPersistedRegPath(
                         L"Components\\SUPL",
                         L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\",
                         v18,
                         L"LfSvc");
    if ( PersistedRegPath >= 0 )
    {
      PersistedRegPath = StringCchPrintfW(v17, 0x104u, L"%s\\%s", v18, *((_QWORD *)a2 + 7));
      if ( PersistedRegPath >= 0 )
      {
        PersistedRegPath = SuplNode::EnsureRegKeyExists(v9, v17, (int *)hKey);
        if ( PersistedRegPath >= 0 )
        {
          VariantClear(a4);
          if ( !a3 )
            a3 = (const unsigned __int16 *)*((_QWORD *)a2 + 8);
          v11 = *((_DWORD *)a2 + 18);
          if ( v11 )
          {
            v12 = (SuplNode *)(unsigned int)(v11 - 1);
            if ( (_DWORD)v12 )
            {
              v13 = (SuplNode *)(unsigned int)((_DWORD)v12 - 2);
              if ( (_DWORD)v13 )
              {
                if ( (_DWORD)v13 != 1 )
                  return (unsigned int)PersistedRegPath;
                return (unsigned int)SuplNode::GetDwordRegValue(v13, v10, v17, a3, a4);
              }
              else
              {
                return (unsigned int)SuplNode::GetBinaryRegValue(v13, v10, v17, a3, a4);
              }
            }
            else
            {
              return (unsigned int)SuplNode::GetStringRegValue(v12, v10, v17, a3, a4);
            }
          }
          if ( a3 )
          {
            SubKey[0] = 0;
            hKey[0] = 0;
            PersistedRegPath = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", v17, a3);
            if ( PersistedRegPath >= 0 )
            {
              if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, hKey) )
                PersistedRegPath = -2046820350;
              if ( hKey[0] )
                RegCloseKey(hKey[0]);
            }
          }
        }
      }
    }
  }
  return (unsigned int)PersistedRegPath;
}

```

## disassembly

```asm
0x18011885c  push    rbp
0x18011885e  push    rbx
0x18011885f  push    rsi
0x180118860  push    rdi
0x180118861  push    r14
0x180118863  lea     rbp, [rsp-570h]
0x18011886b  sub     rsp, 670h
0x180118872  mov     rax, cs:__security_cookie
0x180118879  xor     rax, rsp
0x18011887c  mov     [rbp+590h+var_30], rax
0x180118883  mov     rsi, r8
0x180118886  mov     dword ptr [rsp+690h+hKey], 0
0x18011888e  mov     r14, rdx
0x180118891  lea     rcx, [rbp+590h+var_440]; void *
0x180118898  xor     edx, edx; Val
0x18011889a  mov     r8d, 1FEh; Size
0x1801188a0  mov     rdi, r9
0x1801188a3  call    memset_0
0x1801188a8  xor     eax, eax
0x1801188aa  mov     rcx, rdi; pvarg
0x1801188ad  mov     [rsp+690h+var_650], ax
0x1801188b2  xor     ebx, ebx
0x1801188b4  call    cs:__imp_VariantInit
0x1801188ba  cmp     dword ptr [r14+8], 2
0x1801188bf  jnz     short loc_1801188EB
0x1801188c1  lea     rcx, aAp0004; "ap0004"
0x1801188c8  call    cs:__imp_SysAllocString
0x1801188ce  mov     [rdi+8], rax
0x1801188d2  test    rax, rax
0x1801188d5  jnz     short loc_1801188E1
0x1801188d7  mov     ebx, 8007000Eh
0x1801188dc  jmp     loc_180118A61
0x1801188e1  mov     word ptr [rdi], 8
0x1801188e6  jmp     loc_180118A61
0x1801188eb  cmp     dword ptr [r14+8], 26h ; '&'
0x1801188f0  jnz     short loc_180118903
0x1801188f2  mov     dword ptr [rdi+8], 3
0x1801188f9  mov     word ptr [rdi], 13h
0x1801188fe  jmp     loc_180118A61
0x180118903  lea     r9, aLfsvc_1; "LfSvc"
0x18011890a  lea     r8, [rbp+590h+var_440]; unsigned __int16 *
0x180118911  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x180118918  lea     rcx, aComponentsSupl; "Components\\SUPL"
0x18011891f  call    ?GetPersistedRegPath@CLocationPersistedRegPathHelper@@SAJPEBG0PEAG0@Z; CLocationPersistedRegPathHelper::GetPersistedRegPath(ushort const *,ushort const *,ushort *,ushort const *)
0x180118924  mov     ebx, eax
0x180118926  test    eax, eax
0x180118928  js      loc_180118A61
0x18011892e  mov     rax, [r14+38h]
0x180118932  lea     r9, [rbp+590h+var_440]
0x180118939  lea     r8, aSS_0; "%s\\%s"
0x180118940  mov     [rsp+690h+phkResult], rax
0x180118945  mov     edx, 104h; unsigned __int64
0x18011894a  lea     rcx, [rsp+690h+var_650]; unsigned __int16 *
0x18011894f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180118954  mov     ebx, eax
0x180118956  test    eax, eax
0x180118958  js      loc_180118A61
0x18011895e  lea     r8, [rsp+690h+hKey]; int *
0x180118963  lea     rdx, [rsp+690h+var_650]; unsigned __int16 *
0x180118968  call    ?EnsureRegKeyExists@SuplNode@@AEAAJPEAGPEAH@Z; SuplNode::EnsureRegKeyExists(ushort *,int *)
0x18011896d  mov     ebx, eax
0x18011896f  test    eax, eax
0x180118971  js      loc_180118A61
0x180118977  mov     rcx, rdi; pvarg
0x18011897a  call    cs:__imp_VariantClear
0x180118980  test    rsi, rsi
0x180118983  jnz     short loc_180118989
0x180118985  mov     rsi, [r14+40h]
0x180118989  mov     ecx, [r14+48h]
0x18011898d  test    ecx, ecx
0x18011898f  jz      short loc_1801189E5
0x180118991  sub     ecx, 1; this
0x180118994  jz      short loc_1801189D1
0x180118996  sub     ecx, 2; this
0x180118999  jz      short loc_1801189BD
0x18011899b  cmp     ecx, 1
0x18011899e  jnz     loc_180118A61
0x1801189a4  mov     r9, rsi; unsigned __int16 *
0x1801189a7  mov     [rsp+690h+phkResult], rdi; struct tagVARIANT *
0x1801189ac  lea     r8, [rsp+690h+var_650]; unsigned __int16 *
0x1801189b1  call    ?GetDwordRegValue@SuplNode@@AEAAJPEAUHKEY__@@PEBG1PEAUtagVARIANT@@@Z; SuplNode::GetDwordRegValue(HKEY__ *,ushort const *,ushort const *,tagVARIANT *)
0x1801189b6  mov     ebx, eax
0x1801189b8  jmp     loc_180118A61
0x1801189bd  mov     r9, rsi; unsigned __int16 *
0x1801189c0  mov     [rsp+690h+phkResult], rdi; struct tagVARIANT *
0x1801189c5  lea     r8, [rsp+690h+var_650]; unsigned __int16 *
0x1801189ca  call    ?GetBinaryRegValue@SuplNode@@AEAAJPEAUHKEY__@@PEBG1PEAUtagVARIANT@@@Z; SuplNode::GetBinaryRegValue(HKEY__ *,ushort const *,ushort const *,tagVARIANT *)
0x1801189cf  jmp     short loc_1801189B6
0x1801189d1  mov     r9, rsi; unsigned __int16 *
0x1801189d4  mov     [rsp+690h+phkResult], rdi; struct tagVARIANT *
0x1801189d9  lea     r8, [rsp+690h+var_650]; unsigned __int16 *
0x1801189de  call    ?GetStringRegValue@SuplNode@@AEAAJPEAUHKEY__@@PEBG1PEAUtagVARIANT@@@Z; SuplNode::GetStringRegValue(HKEY__ *,ushort const *,ushort const *,tagVARIANT *)
0x1801189e3  jmp     short loc_1801189B6
0x1801189e5  test    rsi, rsi
0x1801189e8  jz      short loc_180118A61
0x1801189ea  xor     eax, eax
0x1801189ec  mov     [rsp+690h+phkResult], rsi
0x1801189f1  lea     r9, [rsp+690h+var_650]
0x1801189f6  mov     [rbp+590h+SubKey], ax
0x1801189fd  lea     r8, aSS_0; "%s\\%s"
0x180118a04  mov     [rsp+690h+hKey], rax
0x180118a09  mov     edx, 104h; unsigned __int64
0x180118a0e  lea     rcx, [rbp+590h+SubKey]; unsigned __int16 *
0x180118a15  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180118a1a  mov     ebx, eax
0x180118a1c  test    eax, eax
0x180118a1e  js      short loc_180118A61
0x180118a20  lea     rax, [rsp+690h+hKey]
0x180118a25  mov     r9d, 20019h; samDesired
0x180118a2b  xor     r8d, r8d; ulOptions
0x180118a2e  mov     [rsp+690h+phkResult], rax; phkResult
0x180118a33  lea     rdx, [rbp+590h+SubKey]; lpSubKey
0x180118a3a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180118a41  call    cs:__imp_RegOpenKeyExW
0x180118a47  test    eax, eax
0x180118a49  mov     ecx, 86000002h
0x180118a4e  cmovnz  ebx, ecx
0x180118a51  mov     rcx, [rsp+690h+hKey]; hKey
0x180118a56  test    rcx, rcx
0x180118a59  jz      short loc_180118A61
0x180118a5b  call    cs:__imp_RegCloseKey
0x180118a61  mov     eax, ebx
0x180118a63  mov     rcx, [rbp+590h+var_30]
0x180118a6a  xor     rcx, rsp; StackCookie
0x180118a6d  call    __security_check_cookie
0x180118a72  add     rsp, 670h
0x180118a79  pop     r14
0x180118a7b  pop     rdi
0x180118a7c  pop     rsi
0x180118a7d  pop     rbx
0x180118a7e  pop     rbp
0x180118a7f  retn
```
