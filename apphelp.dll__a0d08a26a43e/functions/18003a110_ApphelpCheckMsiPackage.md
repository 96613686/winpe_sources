# ApphelpCheckMsiPackage

- ea: `0x18003a110`
- end: `0x18003a3c4`
- name: `ApphelpCheckMsiPackage`
- size: `692`
- prototype: `__int64 __fastcall(__int128 *, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002b38`
- `0x18000f114`
- `0x180015fb0`
- `0x180016640`
- `0x1800281ac`
- `0x18003a110`
- `0x180043680`
- `0x1800443a0`
- `0x1800446e0`
- `0x1800450c0`
- `0x180048668`
- `0x180048d20`
- `0x18004b104`
- `0x180059175`
- `0x1800591b0`

## string_xrefs

- `0x18003a1a2`: `ApphelpCheckMsiPackage`
- `0x18003a230`: `ApphelpCheckMsiPackage`
- `0x18003a2e8`: `ApphelpCheckMsiPackage`
- `0x18003a37b`: `ApphelpCheckMsiPackage`
- `0x18003a36e`: `Failed to resolve database path`
- `0x18003a224`: `Failed to open database "%ls"`
- `0x18003a252`: `Failed to find msi package by guid id`

## pseudocode

```c
__int64 __fastcall ApphelpCheckMsiPackage(__int128 *a1, __int64 a2, __int64 a3, int a4)
{
  char v4; // al
  int v5; // r14d
  unsigned int v8; // ebx
  __int64 inited; // rax
  void *v10; // rdi
  unsigned int MsiPackageByID; // eax
  void *v12; // r15
  int v13; // eax
  unsigned int v14; // esi
  int v15; // r12d
  __int128 v16; // xmm0
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v19; // [rsp+34h] [rbp-CCh] BYREF
  int v20; // [rsp+38h] [rbp-C8h] BYREF
  int v21; // [rsp+3Ch] [rbp-C4h] BYREF
  int v22; // [rsp+40h] [rbp-C0h]
  _BYTE v23[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+70h] [rbp-90h] BYREF
  __int128 v26; // [rsp+74h] [rbp-8Ch]
  int v27; // [rsp+84h] [rbp-7Ch]
  wchar_t v28[264]; // [rsp+B0h] [rbp-50h] BYREF

  v4 = gdwInfrastructureFlags;
  v5 = 0;
  v22 = a4;
  v19 = 0;
  v20 = 0;
  v18 = 0;
  if ( gdwInfrastructureFlags >= 0 )
    v4 = CheckAppcompatInfrastructureFlags();
  v8 = 1;
  if ( (v4 & 1) == 0 )
  {
    inited = SdbInitDatabase(2147614720LL, 0);
    v10 = (void *)inited;
    if ( inited )
    {
      *(_WORD *)(inited + 584) = 0x7FFF;
      if ( (unsigned int)SdbResolveDatabaseEx(inited, (_DWORD)a1, (unsigned int)&v19, 0, (__int64)v28, 260) - 1 > 0x103 )
      {
        AslLogCallPrintf(1, "ApphelpCheckMsiPackage", 1121, "Failed to resolve database path");
      }
      else
      {
        v21 = 0x10000000;
        if ( (unsigned int)SdbpOpenLocalDatabaseEx((_DWORD)v10, (unsigned int)v28, 268435458, 0, (__int64)&v21) )
        {
          MsiPackageByID = SdbFindMsiPackageByID(v10, a2);
          if ( MsiPackageByID )
          {
            v12 = (void *)SdbOpenApphelpInformationByID(v10, MsiPackageByID, v19);
            if ( v12 )
            {
              v13 = -(int)SdbGetEntryFlags(a2, &v20);
              if ( ((unsigned __int8)v20 & (unsigned __int8)-(v13 != 0) & 2) == 0 )
              {
                v14 = ((v20 & (unsigned int)-(v13 != 0)) >> 2) & 1;
                SdbQueryApphelpInformation(v12, 5, &v18);
                v15 = v18;
                if ( v18 == 1 || v18 == 2 || (unsigned int)(v18 - 3) < 2 )
                {
                  LOBYTE(v5) = v18 == 2;
                  v18 = v5;
                  if ( !(v22 | v14) )
                  {
                    memset_0(v23, 0, 0x58u);
                    v16 = *a1;
                    v24 = v15;
                    v26 = v16;
                    SdbQueryApphelpInformation(v12, 12, &v25);
                    if ( v25 )
                    {
                      v27 = 1;
                      SdbShowApphelpDialog(v23, 0x7FFF, 0, &v18);
                      v5 = v18;
                    }
                  }
                }
                else
                {
                  AslLogCallPrintf(1, "ApphelpCheckMsiPackage", 1218, "Unhandled severity flag 0x%x", v18);
                }
              }
              SdbCloseApphelpInformation(v12);
            }
          }
          else
          {
            AslLogCallPrintf(1, "ApphelpCheckMsiPackage", 1139, "Failed to find msi package by guid id");
          }
        }
        else
        {
          AslLogCallPrintf(1, "ApphelpCheckMsiPackage", 1130, "Failed to open database \"%ls\"", v28);
        }
      }
      SdbReleaseDatabase(v10);
      if ( v5 )
        return 0;
    }
    else
    {
      AslLogCallPrintf(1, "ApphelpCheckMsiPackage", 1105, "Failed to initialize database");
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18003a110  mov     [rsp-8+arg_10], rbx
0x18003a115  push    rbp
0x18003a116  push    rsi
0x18003a117  push    rdi
0x18003a118  push    r12
0x18003a11a  push    r13
0x18003a11c  push    r14
0x18003a11e  push    r15
0x18003a120  lea     rbp, [rsp-1D0h]
0x18003a128  sub     rsp, 2D0h
0x18003a12f  mov     rax, cs:__security_cookie
0x18003a136  xor     rax, rsp
0x18003a139  mov     [rbp+200h+var_40], rax
0x18003a140  mov     eax, cs:gdwInfrastructureFlags
0x18003a146  xor     r14d, r14d
0x18003a149  mov     [rsp+300h+var_2C0], r9d
0x18003a14e  mov     rsi, rdx
0x18003a151  mov     [rsp+300h+var_2CC], 0
0x18003a159  mov     r13, rcx
0x18003a15c  mov     [rsp+300h+var_2C8], 0
0x18003a164  mov     [rsp+300h+var_2D0], r14d
0x18003a169  test    eax, eax
0x18003a16b  js      short loc_18003A172
0x18003a16d  call    CheckAppcompatInfrastructureFlags
0x18003a172  mov     ebx, 1
0x18003a177  and     eax, ebx
0x18003a179  test    eax, eax
0x18003a17b  jnz     loc_18003A398
0x18003a181  xor     edx, edx
0x18003a183  mov     ecx, 80020000h
0x18003a188  call    SdbInitDatabase
0x18003a18d  mov     rdi, rax
0x18003a190  test    rax, rax
0x18003a193  jnz     short loc_18003A1B5
0x18003a195  lea     r9, aFailedToInitia_10; "Failed to initialize database"
0x18003a19c  mov     r8d, 451h
0x18003a1a2  lea     rdx, aApphelpcheckms_0; "ApphelpCheckMsiPackage"
0x18003a1a9  mov     ecx, ebx
0x18003a1ab  call    AslLogCallPrintf
0x18003a1b0  jmp     loc_18003A398
0x18003a1b5  mov     word ptr [rax+248h], 7FFFh
0x18003a1be  lea     r8, [rsp+300h+var_2CC]
0x18003a1c3  lea     rax, [rbp+200h+var_250]
0x18003a1c7  mov     [rsp+300h+var_2D8], 104h
0x18003a1cf  xor     r9d, r9d
0x18003a1d2  mov     [rsp+300h+var_2E0], rax
0x18003a1d7  mov     rdx, r13
0x18003a1da  mov     rcx, rdi
0x18003a1dd  call    SdbResolveDatabaseEx
0x18003a1e2  dec     eax
0x18003a1e4  cmp     eax, 103h
0x18003a1e9  ja      loc_18003A36E
0x18003a1ef  lea     rax, [rsp+300h+var_2C4]
0x18003a1f4  mov     [rsp+300h+var_2C4], 10000000h
0x18003a1fc  xor     r9d, r9d
0x18003a1ff  mov     [rsp+300h+var_2E0], rax
0x18003a204  mov     r8d, 10000002h
0x18003a20a  lea     rdx, [rbp+200h+var_250]
0x18003a20e  mov     rcx, rdi
0x18003a211  call    SdbpOpenLocalDatabaseEx
0x18003a216  test    eax, eax
0x18003a218  jnz     short loc_18003A243
0x18003a21a  lea     rax, [rbp+200h+var_250]
0x18003a21e  mov     r8d, 46Ah
0x18003a224  lea     r9, aFailedToOpenDa_0; "Failed to open database \"%ls\""
0x18003a22b  mov     [rsp+300h+var_2E0], rax
0x18003a230  lea     rdx, aApphelpcheckms_0; "ApphelpCheckMsiPackage"
0x18003a237  mov     ecx, ebx
0x18003a239  call    AslLogCallPrintf
0x18003a23e  jmp     loc_18003A389
0x18003a243  mov     rdx, rsi
0x18003a246  mov     rcx, rdi
0x18003a249  call    SdbFindMsiPackageByID
0x18003a24e  test    eax, eax
0x18003a250  jnz     short loc_18003A264
0x18003a252  lea     r9, aFailedToFindMs; "Failed to find msi package by guid id"
0x18003a259  mov     r8d, 473h
0x18003a25f  jmp     loc_18003A37B
0x18003a264  mov     r8d, [rsp+300h+var_2CC]
0x18003a269  mov     edx, eax
0x18003a26b  mov     rcx, rdi
0x18003a26e  call    SdbOpenApphelpInformationByID
0x18003a273  mov     r15, rax
0x18003a276  test    rax, rax
0x18003a279  jz      loc_18003A389
0x18003a27f  lea     rdx, [rsp+300h+var_2C8]
0x18003a284  mov     rcx, rsi
0x18003a287  call    SdbGetEntryFlags
0x18003a28c  neg     eax
0x18003a28e  sbb     esi, esi
0x18003a290  and     esi, [rsp+300h+var_2C8]
0x18003a294  test    sil, 2
0x18003a298  jnz     loc_18003A364
0x18003a29e  mov     r9d, 4
0x18003a2a4  shr     esi, 2
0x18003a2a7  lea     r8, [rsp+300h+var_2D0]
0x18003a2ac  mov     rcx, r15
0x18003a2af  and     esi, ebx
0x18003a2b1  lea     edx, [r9+1]
0x18003a2b5  call    SdbQueryApphelpInformation
0x18003a2ba  mov     r12d, [rsp+300h+var_2D0]
0x18003a2bf  mov     eax, r12d
0x18003a2c2  sub     eax, 1
0x18003a2c5  jz      short loc_18003A2F8
0x18003a2c7  sub     eax, 1
0x18003a2ca  jz      short loc_18003A2F8
0x18003a2cc  sub     eax, 1
0x18003a2cf  jz      short loc_18003A2F8
0x18003a2d1  cmp     eax, 1
0x18003a2d4  jz      short loc_18003A2F8
0x18003a2d6  lea     r9, aUnhandledSever; "Unhandled severity flag 0x%x"
0x18003a2dd  mov     dword ptr [rsp+300h+var_2E0], r12d
0x18003a2e2  mov     r8d, 4C2h
0x18003a2e8  lea     rdx, aApphelpcheckms_0; "ApphelpCheckMsiPackage"
0x18003a2ef  mov     ecx, ebx
0x18003a2f1  call    AslLogCallPrintf
0x18003a2f6  jmp     short loc_18003A364
0x18003a2f8  cmp     r12d, 2
0x18003a2fc  setz    r14b
0x18003a300  or      esi, [rsp+300h+var_2C0]
0x18003a304  mov     [rsp+300h+var_2D0], r14d
0x18003a309  jnz     short loc_18003A364
0x18003a30b  xor     edx, edx; Val
0x18003a30d  lea     r8d, [rsi+58h]; Size
0x18003a311  lea     rcx, [rsp+300h+var_2B0]; void *
0x18003a316  call    memset_0
0x18003a31b  movups  xmm0, xmmword ptr [r13+0]
0x18003a320  lea     r9d, [rsi+4]
0x18003a324  mov     [rsp+300h+var_2AC], r12d
0x18003a329  lea     r8, [rsp+300h+var_290]
0x18003a32e  mov     rcx, r15
0x18003a331  lea     edx, [rsi+0Ch]
0x18003a334  movdqu  [rsp+300h+var_28C], xmm0
0x18003a33a  call    SdbQueryApphelpInformation
0x18003a33f  cmp     [rsp+300h+var_290], esi
0x18003a343  jz      short loc_18003A364
0x18003a345  mov     edx, 7FFFh
0x18003a34a  mov     [rbp+200h+var_27C], ebx
0x18003a34d  lea     r9, [rsp+300h+var_2D0]
0x18003a352  xor     r8d, r8d
0x18003a355  lea     rcx, [rsp+300h+var_2B0]
0x18003a35a  call    SdbShowApphelpDialog
0x18003a35f  mov     r14d, [rsp+300h+var_2D0]
0x18003a364  mov     rcx, r15; void *
0x18003a367  call    SdbCloseApphelpInformation
0x18003a36c  jmp     short loc_18003A389
0x18003a36e  lea     r9, aFailedToResolv_4; "Failed to resolve database path"
0x18003a375  mov     r8d, 461h
0x18003a37b  lea     rdx, aApphelpcheckms_0; "ApphelpCheckMsiPackage"
0x18003a382  mov     ecx, ebx
0x18003a384  call    AslLogCallPrintf
0x18003a389  mov     rcx, rdi; P
0x18003a38c  call    SdbReleaseDatabase
0x18003a391  test    r14d, r14d
0x18003a394  jz      short loc_18003A398
0x18003a396  xor     ebx, ebx
0x18003a398  mov     eax, ebx
0x18003a39a  mov     rcx, [rbp+200h+var_40]
0x18003a3a1  xor     rcx, rsp; StackCookie
0x18003a3a4  call    __security_check_cookie
0x18003a3a9  mov     rbx, [rsp+300h+arg_10]
0x18003a3b1  add     rsp, 2D0h
0x18003a3b8  pop     r15
0x18003a3ba  pop     r14
0x18003a3bc  pop     r13
0x18003a3be  pop     r12
0x18003a3c0  pop     rdi
0x18003a3c1  pop     rsi
0x18003a3c2  pop     rbp
0x18003a3c3  retn
```
