# ApphelpFixMsiPackageExe

- ea: `0x18003a6a0`
- end: `0x18003a933`
- name: `ApphelpFixMsiPackageExe`
- size: `659`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002be0`
- `0x180008390`
- `0x18000ae70`
- `0x18000f114`
- `0x180015fb0`
- `0x180016640`
- `0x1800281ac`
- `0x18003a6a0`
- `0x180046a30`
- `0x180048668`
- `0x180048c40`
- `0x180048d20`
- `0x18004b104`
- `0x180059235`
- `0x180059270`

## string_xrefs

- `0x18003a8ea`: `Failed to resolve database path`
- `0x18003a7c1`: `Failed to open database "%ls"`
- `0x18003a7f1`: `Failed to find msi package by guid id`
- `0x18003a73f`: `ApphelpFixMsiPackageExe`
- `0x18003a7c8`: `ApphelpFixMsiPackageExe`
- `0x18003a8f7`: `ApphelpFixMsiPackageExe`

## pseudocode

```c
__int64 __fastcall ApphelpFixMsiPackageExe(int a1, __int128 *a2, __int64 a3, wchar_t *a4, int *a5)
{
  unsigned int v5; // r14d
  char v9; // al
  void *inited; // rdi
  unsigned int MsiPackageByID; // esi
  unsigned int CustomActionForPackage; // r12d
  __int64 v13; // rsi
  int NextTagRef; // eax
  int v15; // eax
  int v16; // eax
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h]
  wchar_t *Buffer; // [rsp+50h] [rbp-B0h]
  int v22[43]; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+10Ch] [rbp+Ch]
  __int128 v24; // [rsp+110h] [rbp+10h]
  _BYTE v25[528]; // [rsp+230h] [rbp+130h] BYREF

  v5 = 0;
  Buffer = a4;
  v20 = a3;
  v18 = 0;
  if ( a4 )
    *a4 = 0;
  v9 = gdwInfrastructureFlags;
  if ( gdwInfrastructureFlags >= 0 )
    v9 = CheckAppcompatInfrastructureFlags();
  if ( (v9 & 1) == 0 )
  {
    inited = (void *)SdbInitDatabaseEx(2147614720LL, 0, 0x7FFF);
    if ( inited )
    {
      if ( (unsigned int)SdbResolveDatabaseEx((_DWORD)inited, a1, (unsigned int)&v19, 0, (__int64)v25, 260) - 1 > 0x103 )
      {
        AslLogCallPrintf(1, "ApphelpFixMsiPackageExe", 1429, "Failed to resolve database path");
      }
      else
      {
        v19 = 0x10000000;
        if ( (unsigned int)SdbpOpenLocalDatabaseEx((_DWORD)inited, (unsigned int)v25, 268435458, 0, (__int64)&v19) )
        {
          MsiPackageByID = SdbFindMsiPackageByID(inited, a2);
          if ( MsiPackageByID )
          {
            if ( (unsigned int)SdbGetEntryFlags(a2, &v18) && (v18 & 1) != 0 )
            {
              AslLogCallPrintf(1, "ApphelpFixMsiPackageExe", 1452, "Shims for this package are disabled");
            }
            else
            {
              CustomActionForPackage = SdbFindCustomActionForPackage(inited, MsiPackageByID, a3);
              if ( CustomActionForPackage )
              {
                memset_0(v22, 0, 0x1C8u);
                v13 = 0;
                v24 = *a2;
                do
                {
                  if ( (_DWORD)v13 )
                    NextTagRef = SdbFindNextTagRef(inited, CustomActionForPackage, v5);
                  else
                    NextTagRef = SdbFindFirstTagRef(inited, CustomActionForPackage, 28683);
                  v5 = NextTagRef;
                  if ( !NextTagRef )
                    break;
                  v22[v13 + 32] = NextTagRef;
                  v13 = (unsigned int)(v13 + 1);
                  ++v23;
                }
                while ( (int)v13 < 8 );
                v15 = 0;
                if ( a5 )
                  v15 = *a5;
                v16 = SdbBuildCompatEnvVariables((int)inited, (int)v22, 0, 0, Buffer, v15, 0);
                if ( a5 )
                  *a5 = v16;
                v5 = 1;
              }
              else
              {
                AslLogCallPrintf(1, "ApphelpFixMsiPackageExe", 1458, "Failed to find custom action \"%ls\"", v20);
              }
            }
          }
          else
          {
            AslLogCallPrintf(1, "ApphelpFixMsiPackageExe", 1447, "Failed to find msi package by guid id");
          }
        }
        else
        {
          AslLogCallPrintf(1, "ApphelpFixMsiPackageExe", 1438, "Failed to open database \"%ls\"", v25);
        }
      }
      SdbReleaseDatabase(inited);
    }
    else
    {
      AslLogCallPrintf(1, "ApphelpFixMsiPackageExe", 1415, "Failed to initialize database");
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18003a6a0  push    rbp
0x18003a6a2  push    rbx
0x18003a6a3  push    rsi
0x18003a6a4  push    rdi
0x18003a6a5  push    r12
0x18003a6a7  push    r13
0x18003a6a9  push    r14
0x18003a6ab  push    r15
0x18003a6ad  lea     rbp, [rsp-358h]
0x18003a6b5  sub     rsp, 458h
0x18003a6bc  mov     rax, cs:__security_cookie
0x18003a6c3  xor     rax, rsp
0x18003a6c6  mov     [rbp+390h+var_50], rax
0x18003a6cd  mov     r15, [rbp+390h+arg_20]
0x18003a6d4  xor     r14d, r14d
0x18003a6d7  mov     [rsp+490h+var_440], r9
0x18003a6dc  mov     r12, r8
0x18003a6df  mov     [rsp+490h+var_448], r8
0x18003a6e4  mov     r13, rdx
0x18003a6e7  mov     [rsp+490h+var_450], r14d
0x18003a6ec  mov     rsi, rcx
0x18003a6ef  test    r9, r9
0x18003a6f2  jz      short loc_18003A6FA
0x18003a6f4  xor     eax, eax
0x18003a6f6  mov     [r9], ax
0x18003a6fa  mov     eax, cs:gdwInfrastructureFlags
0x18003a700  test    eax, eax
0x18003a702  js      short loc_18003A709
0x18003a704  call    CheckAppcompatInfrastructureFlags
0x18003a709  mov     ebx, 1
0x18003a70e  and     eax, ebx
0x18003a710  test    eax, eax
0x18003a712  jnz     loc_18003A90D
0x18003a718  xor     edx, edx
0x18003a71a  mov     ecx, 80020000h
0x18003a71f  mov     r8d, 7FFFh
0x18003a725  call    SdbInitDatabaseEx
0x18003a72a  mov     rdi, rax
0x18003a72d  test    rax, rax
0x18003a730  jnz     short loc_18003A752
0x18003a732  lea     r9, aFailedToInitia_10; "Failed to initialize database"
0x18003a739  mov     r8d, 587h
0x18003a73f  lea     rdx, aApphelpfixmsip_2; "ApphelpFixMsiPackageExe"
0x18003a746  mov     ecx, ebx
0x18003a748  call    AslLogCallPrintf
0x18003a74d  jmp     loc_18003A90D
0x18003a752  lea     rax, [rbp+390h+var_260]
0x18003a759  mov     [rsp+490h+var_468], 104h
0x18003a761  xor     r9d, r9d
0x18003a764  mov     [rsp+490h+Buffer], rax
0x18003a769  lea     r8, [rsp+490h+var_44C]
0x18003a76e  mov     rdx, rsi
0x18003a771  mov     rcx, rdi
0x18003a774  call    SdbResolveDatabaseEx
0x18003a779  dec     eax
0x18003a77b  cmp     eax, 103h
0x18003a780  ja      loc_18003A8EA
0x18003a786  lea     rax, [rsp+490h+var_44C]
0x18003a78b  mov     [rsp+490h+var_44C], 10000000h
0x18003a793  xor     r9d, r9d
0x18003a796  mov     [rsp+490h+Buffer], rax
0x18003a79b  mov     r8d, 10000002h
0x18003a7a1  lea     rdx, [rbp+390h+var_260]
0x18003a7a8  mov     rcx, rdi
0x18003a7ab  call    SdbpOpenLocalDatabaseEx
0x18003a7b0  test    eax, eax
0x18003a7b2  jnz     short loc_18003A7E0
0x18003a7b4  lea     rax, [rbp+390h+var_260]
0x18003a7bb  mov     r8d, 59Eh
0x18003a7c1  lea     r9, aFailedToOpenDa_0; "Failed to open database \"%ls\""
0x18003a7c8  lea     rdx, aApphelpfixmsip_2; "ApphelpFixMsiPackageExe"
0x18003a7cf  mov     [rsp+490h+Buffer], rax
0x18003a7d4  mov     ecx, ebx
0x18003a7d6  call    AslLogCallPrintf
0x18003a7db  jmp     loc_18003A905
0x18003a7e0  mov     rdx, r13
0x18003a7e3  mov     rcx, rdi
0x18003a7e6  call    SdbFindMsiPackageByID
0x18003a7eb  mov     esi, eax
0x18003a7ed  test    eax, eax
0x18003a7ef  jnz     short loc_18003A803
0x18003a7f1  lea     r9, aFailedToFindMs; "Failed to find msi package by guid id"
0x18003a7f8  mov     r8d, 5A7h
0x18003a7fe  jmp     loc_18003A8F7
0x18003a803  lea     rdx, [rsp+490h+var_450]
0x18003a808  mov     rcx, r13
0x18003a80b  call    SdbGetEntryFlags
0x18003a810  test    eax, eax
0x18003a812  jz      short loc_18003A82C
0x18003a814  test    byte ptr [rsp+490h+var_450], bl
0x18003a818  jz      short loc_18003A82C
0x18003a81a  lea     r9, aShimsForThisPa; "Shims for this package are disabled"
0x18003a821  mov     r8d, 5ACh
0x18003a827  jmp     loc_18003A8F7
0x18003a82c  mov     r8, r12
0x18003a82f  mov     edx, esi
0x18003a831  mov     rcx, rdi
0x18003a834  call    SdbFindCustomActionForPackage
0x18003a839  mov     r12d, eax
0x18003a83c  test    eax, eax
0x18003a83e  jnz     short loc_18003A857
0x18003a840  mov     rax, [rsp+490h+var_448]
0x18003a845  lea     r9, aFailedToFindCu; "Failed to find custom action \"%ls\""
0x18003a84c  mov     r8d, 5B2h
0x18003a852  jmp     loc_18003A7C8
0x18003a857  xor     edx, edx; Val
0x18003a859  lea     rcx, [rsp+490h+var_430]; void *
0x18003a85e  mov     r8d, 1C8h; Size
0x18003a864  call    memset_0
0x18003a869  movups  xmm0, xmmword ptr [r13+0]
0x18003a86e  xor     esi, esi
0x18003a870  movdqu  [rbp+390h+var_380], xmm0
0x18003a875  mov     edx, r12d
0x18003a878  mov     rcx, rdi
0x18003a87b  test    esi, esi
0x18003a87d  jnz     short loc_18003A88C
0x18003a87f  mov     r8d, 700Bh
0x18003a885  call    SdbFindFirstTagRef
0x18003a88a  jmp     short loc_18003A894
0x18003a88c  mov     r8d, r14d
0x18003a88f  call    SdbFindNextTagRef
0x18003a894  mov     r14d, eax
0x18003a897  test    eax, eax
0x18003a899  jz      short loc_18003A8A9
0x18003a89b  mov     [rbp+rsi*4+390h+var_3B0], eax
0x18003a89f  add     esi, ebx
0x18003a8a1  add     [rbp+390h+var_384], ebx
0x18003a8a4  cmp     esi, 8
0x18003a8a7  jl      short loc_18003A875
0x18003a8a9  xor     eax, eax
0x18003a8ab  test    r15, r15
0x18003a8ae  jz      short loc_18003A8B3
0x18003a8b0  mov     eax, [r15]
0x18003a8b3  mov     [rsp+490h+var_460], 0; __int64
0x18003a8bc  lea     rdx, [rsp+490h+var_430]; int
0x18003a8c1  mov     [rsp+490h+var_468], eax; int
0x18003a8c5  xor     r9d, r9d; int
0x18003a8c8  mov     rax, [rsp+490h+var_440]
0x18003a8cd  xor     r8d, r8d; int
0x18003a8d0  mov     rcx, rdi; int
0x18003a8d3  mov     [rsp+490h+Buffer], rax; Buffer
0x18003a8d8  call    SdbBuildCompatEnvVariables
0x18003a8dd  test    r15, r15
0x18003a8e0  jz      short loc_18003A8E5
0x18003a8e2  mov     [r15], eax
0x18003a8e5  mov     r14d, ebx
0x18003a8e8  jmp     short loc_18003A905
0x18003a8ea  lea     r9, aFailedToResolv_4; "Failed to resolve database path"
0x18003a8f1  mov     r8d, 595h
0x18003a8f7  lea     rdx, aApphelpfixmsip_2; "ApphelpFixMsiPackageExe"
0x18003a8fe  mov     ecx, ebx
0x18003a900  call    AslLogCallPrintf
0x18003a905  mov     rcx, rdi; P
0x18003a908  call    SdbReleaseDatabase
0x18003a90d  mov     eax, r14d
0x18003a910  mov     rcx, [rbp+390h+var_50]
0x18003a917  xor     rcx, rsp; StackCookie
0x18003a91a  call    __security_check_cookie
0x18003a91f  add     rsp, 458h
0x18003a926  pop     r15
0x18003a928  pop     r14
0x18003a92a  pop     r13
0x18003a92c  pop     r12
0x18003a92e  pop     rdi
0x18003a92f  pop     rsi
0x18003a930  pop     rbx
0x18003a931  pop     rbp
0x18003a932  retn
```
