# ApphelpFixMsiPackage

- ea: `0x18003a3d0`
- end: `0x18003a698`
- name: `ApphelpFixMsiPackage`
- size: `712`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002b38`
- `0x180008390`
- `0x18000ae70`
- `0x18000f114`
- `0x180015fb0`
- `0x180016640`
- `0x1800281ac`
- `0x18002cba0`
- `0x18003a3d0`
- `0x180040cc0`
- `0x180048668`
- `0x180048c40`
- `0x180048d20`
- `0x18004b104`
- `0x180059235`
- `0x180059270`

## string_xrefs

- `0x18003a650`: `Failed to resolve database path`
- `0x18003a4dc`: `Failed to open database "%ls"`
- `0x18003a508`: `Failed to find msi package by guid id`
- `0x18003a44c`: `ApphelpFixMsiPackage`
- `0x18003a4e5`: `ApphelpFixMsiPackage`
- `0x18003a640`: `ApphelpFixMsiPackage`
- `0x18003a65d`: `ApphelpFixMsiPackage`

## pseudocode

```c
__int64 __fastcall ApphelpFixMsiPackage(int a1, __int128 *a2, const wchar_t *a3, const wchar_t *a4, char a5)
{
  char v5; // al
  unsigned int fixed; // esi
  __int64 inited; // rax
  void *v11; // rdi
  unsigned int MsiPackageByID; // r14d
  unsigned int CustomActionForPackage; // r15d
  __int128 v14; // xmm0
  unsigned int FirstTagRef; // r14d
  unsigned int v16; // esi
  int NamedLayer; // eax
  int v18; // eax
  const wchar_t *v19; // r14
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v22; // [rsp+38h] [rbp-C8h]
  _DWORD v23[43]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v24; // [rsp+ECh] [rbp-14h]
  __int128 v25; // [rsp+F0h] [rbp-10h]
  _BYTE v26[528]; // [rsp+210h] [rbp+110h] BYREF

  v5 = gdwInfrastructureFlags;
  v22 = a3;
  if ( gdwInfrastructureFlags >= 0 )
    v5 = CheckAppcompatInfrastructureFlags();
  if ( (v5 & 1) != 0 )
  {
    return 1;
  }
  else
  {
    fixed = 0;
    inited = SdbInitDatabase(0, 0);
    v11 = (void *)inited;
    if ( inited )
    {
      *(_WORD *)(inited + 584) = 0x7FFF;
      if ( (unsigned int)SdbResolveDatabaseEx(inited, a1, (unsigned int)&v21, 0, (__int64)v26, 260) - 1 > 0x103 )
      {
        AslLogCallPrintf(1, "ApphelpFixMsiPackage", 1299, "Failed to resolve database path");
      }
      else
      {
        v21 = 0x10000000;
        if ( (unsigned int)SdbpOpenLocalDatabaseEx((_DWORD)v11, (unsigned int)v26, 268435458, 0, (__int64)&v21) )
        {
          MsiPackageByID = SdbFindMsiPackageByID(v11, a2);
          if ( MsiPackageByID )
          {
            if ( (unsigned int)SdbGetEntryFlags(a2, &a5) && (a5 & 1) != 0 )
            {
              AslLogCallPrintf(1, "ApphelpFixMsiPackage", 1322, "Shims for this package are disabled");
            }
            else
            {
              CustomActionForPackage = SdbFindCustomActionForPackage(v11, MsiPackageByID, a4);
              if ( CustomActionForPackage )
              {
                memset_0(v23, 0, 0x1C8u);
                v14 = *a2;
                v23[0] = CustomActionForPackage;
                v23[42] = 1;
                v25 = v14;
                FirstTagRef = SdbFindFirstTagRef(v11, CustomActionForPackage, 28683);
                if ( FirstTagRef )
                {
                  v16 = v24;
                  do
                  {
                    if ( v16 >= 8 )
                      break;
                    NamedLayer = SdbGetNamedLayer(v11, FirstTagRef);
                    if ( NamedLayer )
                    {
                      v23[v16 + 32] = NamedLayer;
                      v16 = ++v24;
                    }
                    FirstTagRef = SdbFindNextTagRef(v11, CustomActionForPackage, FirstTagRef);
                  }
                  while ( FirstTagRef );
                }
                v18 = SdbFindFirstTagRef(v11, CustomActionForPackage, 4104);
                v19 = v22;
                fixed = ApphelpFixExe(v11, v22, v23, v18 == 0, 0);
                if ( !fixed )
                  AslLogCallPrintf(
                    1,
                    "ApphelpFixMsiPackage",
                    1369,
                    "Custom action \"%ls\" failed to shim \"%ls\"",
                    a4,
                    v19);
              }
              else
              {
                AslLogCallPrintf(3, "ApphelpFixMsiPackage", 1328, "No custom action for package found: \"%ls\"", a4);
              }
            }
          }
          else
          {
            AslLogCallPrintf(1, "ApphelpFixMsiPackage", 1317, "Failed to find msi package by guid id");
          }
        }
        else
        {
          AslLogCallPrintf(1, "ApphelpFixMsiPackage", 1308, "Failed to open database \"%ls\"", v26);
        }
      }
      SdbReleaseDatabase(v11);
    }
    else
    {
      AslLogCallPrintf(1, "ApphelpFixMsiPackage", 1276, "Failed to initialize database");
    }
  }
  return fixed;
}

```

## disassembly

```asm
0x18003a3d0  push    rbp
0x18003a3d2  push    rbx
0x18003a3d3  push    rsi
0x18003a3d4  push    rdi
0x18003a3d5  push    r12
0x18003a3d7  push    r13
0x18003a3d9  push    r14
0x18003a3db  push    r15
0x18003a3dd  lea     rbp, [rsp-338h]
0x18003a3e5  sub     rsp, 438h
0x18003a3ec  mov     rax, cs:__security_cookie
0x18003a3f3  xor     rax, rsp
0x18003a3f6  mov     [rbp+370h+var_50], rax
0x18003a3fd  mov     eax, cs:gdwInfrastructureFlags
0x18003a403  mov     r13, r9
0x18003a406  mov     [rsp+470h+var_438], r8
0x18003a40b  mov     r12, rdx
0x18003a40e  mov     r14, rcx
0x18003a411  test    eax, eax
0x18003a413  js      short loc_18003A41A
0x18003a415  call    CheckAppcompatInfrastructureFlags
0x18003a41a  mov     ebx, 1
0x18003a41f  and     eax, ebx
0x18003a421  test    eax, eax
0x18003a423  jz      short loc_18003A42C
0x18003a425  mov     esi, ebx
0x18003a427  jmp     loc_18003A673
0x18003a42c  xor     edx, edx
0x18003a42e  xor     ecx, ecx
0x18003a430  xor     esi, esi
0x18003a432  call    SdbInitDatabase
0x18003a437  mov     rdi, rax
0x18003a43a  test    rax, rax
0x18003a43d  jnz     short loc_18003A45F
0x18003a43f  lea     r9, aFailedToInitia_10; "Failed to initialize database"
0x18003a446  mov     r8d, 4FCh
0x18003a44c  lea     rdx, aApphelpfixmsip_1; "ApphelpFixMsiPackage"
0x18003a453  mov     ecx, ebx
0x18003a455  call    AslLogCallPrintf
0x18003a45a  jmp     loc_18003A673
0x18003a45f  mov     word ptr [rax+248h], 7FFFh
0x18003a468  lea     r8, [rsp+470h+var_440]
0x18003a46d  lea     rax, [rbp+370h+var_260]
0x18003a474  mov     dword ptr [rsp+470h+var_448], 104h
0x18003a47c  xor     r9d, r9d
0x18003a47f  mov     [rsp+470h+var_450], rax
0x18003a484  mov     rdx, r14
0x18003a487  mov     rcx, rdi
0x18003a48a  call    SdbResolveDatabaseEx
0x18003a48f  dec     eax
0x18003a491  cmp     eax, 103h
0x18003a496  ja      loc_18003A650
0x18003a49c  lea     rax, [rsp+470h+var_440]
0x18003a4a1  mov     [rsp+470h+var_440], 10000000h
0x18003a4a9  xor     r9d, r9d
0x18003a4ac  mov     [rsp+470h+var_450], rax
0x18003a4b1  mov     r8d, 10000002h
0x18003a4b7  lea     rdx, [rbp+370h+var_260]
0x18003a4be  mov     rcx, rdi
0x18003a4c1  call    SdbpOpenLocalDatabaseEx
0x18003a4c6  test    eax, eax
0x18003a4c8  jnz     short loc_18003A4F6
0x18003a4ca  lea     rax, [rbp+370h+var_260]
0x18003a4d1  mov     r8d, 51Ch
0x18003a4d7  mov     [rsp+470h+var_450], rax
0x18003a4dc  lea     r9, aFailedToOpenDa_0; "Failed to open database \"%ls\""
0x18003a4e3  mov     ecx, ebx
0x18003a4e5  lea     rdx, aApphelpfixmsip_1; "ApphelpFixMsiPackage"
0x18003a4ec  call    AslLogCallPrintf
0x18003a4f1  jmp     loc_18003A66B
0x18003a4f6  mov     rdx, r12
0x18003a4f9  mov     rcx, rdi
0x18003a4fc  call    SdbFindMsiPackageByID
0x18003a501  mov     r14d, eax
0x18003a504  test    eax, eax
0x18003a506  jnz     short loc_18003A51A
0x18003a508  lea     r9, aFailedToFindMs; "Failed to find msi package by guid id"
0x18003a50f  mov     r8d, 525h
0x18003a515  jmp     loc_18003A65D
0x18003a51a  lea     rdx, [rbp+370h+arg_20]
0x18003a521  mov     rcx, r12
0x18003a524  call    SdbGetEntryFlags
0x18003a529  test    eax, eax
0x18003a52b  jz      short loc_18003A547
0x18003a52d  test    [rbp+370h+arg_20], bl
0x18003a533  jz      short loc_18003A547
0x18003a535  lea     r9, aShimsForThisPa; "Shims for this package are disabled"
0x18003a53c  mov     r8d, 52Ah
0x18003a542  jmp     loc_18003A65D
0x18003a547  mov     r8, r13
0x18003a54a  mov     edx, r14d
0x18003a54d  mov     rcx, rdi
0x18003a550  call    SdbFindCustomActionForPackage
0x18003a555  mov     r15d, eax
0x18003a558  test    eax, eax
0x18003a55a  jnz     short loc_18003A576
0x18003a55c  mov     [rsp+470h+var_450], r13
0x18003a561  lea     r9, aNoCustomAction; "No custom action for package found: \"%"...
0x18003a568  mov     r8d, 530h
0x18003a56e  lea     ecx, [rax+3]
0x18003a571  jmp     loc_18003A4E5
0x18003a576  xor     edx, edx; Val
0x18003a578  lea     rcx, [rsp+470h+var_430]; void *
0x18003a57d  mov     r8d, 1C8h; Size
0x18003a583  call    memset_0
0x18003a588  movups  xmm0, xmmword ptr [r12]
0x18003a58d  mov     r8d, 700Bh
0x18003a593  mov     [rsp+470h+var_430], r15d
0x18003a598  mov     edx, r15d
0x18003a59b  mov     [rbp+370h+var_388], ebx
0x18003a59e  mov     rcx, rdi
0x18003a5a1  movdqu  [rbp+370h+var_380], xmm0
0x18003a5a6  call    SdbFindFirstTagRef
0x18003a5ab  mov     r14d, eax
0x18003a5ae  test    eax, eax
0x18003a5b0  jz      short loc_18003A5EC
0x18003a5b2  mov     esi, [rbp+370h+var_384]
0x18003a5b5  cmp     esi, 8
0x18003a5b8  jnb     short loc_18003A5EC
0x18003a5ba  mov     edx, r14d
0x18003a5bd  mov     rcx, rdi
0x18003a5c0  call    SdbGetNamedLayer
0x18003a5c5  test    eax, eax
0x18003a5c7  jz      short loc_18003A5D7
0x18003a5c9  mov     ecx, esi
0x18003a5cb  mov     [rbp+rcx*4+370h+var_3B0], eax
0x18003a5cf  mov     esi, [rbp+370h+var_384]
0x18003a5d2  add     esi, ebx
0x18003a5d4  mov     [rbp+370h+var_384], esi
0x18003a5d7  mov     r8d, r14d
0x18003a5da  mov     edx, r15d
0x18003a5dd  mov     rcx, rdi
0x18003a5e0  call    SdbFindNextTagRef
0x18003a5e5  mov     r14d, eax
0x18003a5e8  test    eax, eax
0x18003a5ea  jnz     short loc_18003A5B5
0x18003a5ec  mov     r8d, 1008h
0x18003a5f2  mov     edx, r15d
0x18003a5f5  mov     rcx, rdi
0x18003a5f8  call    SdbFindFirstTagRef
0x18003a5fd  mov     r14, [rsp+470h+var_438]
0x18003a602  lea     r8, [rsp+470h+var_430]
0x18003a607  xor     r9d, r9d
0x18003a60a  mov     dword ptr [rsp+470h+var_450], 0
0x18003a612  test    eax, eax
0x18003a614  mov     rdx, r14
0x18003a617  mov     rcx, rdi
0x18003a61a  setz    r9b
0x18003a61e  call    ApphelpFixExe
0x18003a623  mov     esi, eax
0x18003a625  test    eax, eax
0x18003a627  jnz     short loc_18003A66B
0x18003a629  mov     [rsp+470h+var_448], r14
0x18003a62e  lea     r9, aCustomActionLs; "Custom action \"%ls\" failed to shim \""...
0x18003a635  mov     r8d, 559h
0x18003a63b  mov     [rsp+470h+var_450], r13
0x18003a640  lea     rdx, aApphelpfixmsip_1; "ApphelpFixMsiPackage"
0x18003a647  mov     ecx, ebx
0x18003a649  call    AslLogCallPrintf
0x18003a64e  jmp     short loc_18003A66B
0x18003a650  lea     r9, aFailedToResolv_4; "Failed to resolve database path"
0x18003a657  mov     r8d, 513h
0x18003a65d  lea     rdx, aApphelpfixmsip_1; "ApphelpFixMsiPackage"
0x18003a664  mov     ecx, ebx
0x18003a666  call    AslLogCallPrintf
0x18003a66b  mov     rcx, rdi; P
0x18003a66e  call    SdbReleaseDatabase
0x18003a673  mov     eax, esi
0x18003a675  mov     rcx, [rbp+370h+var_50]
0x18003a67c  xor     rcx, rsp; StackCookie
0x18003a67f  call    __security_check_cookie
0x18003a684  add     rsp, 438h
0x18003a68b  pop     r15
0x18003a68d  pop     r14
0x18003a68f  pop     r13
0x18003a691  pop     r12
0x18003a693  pop     rdi
0x18003a694  pop     rsi
0x18003a695  pop     rbx
0x18003a696  pop     rbp
0x18003a697  retn
```
