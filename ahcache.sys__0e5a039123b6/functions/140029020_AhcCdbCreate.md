# AhcCdbCreate

- ea: `0x140029020`
- end: `0x14002931a`
- name: `AhcCdbCreate`
- size: `762`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x14002a3dc`

## callees

- `0x140007e40`
- `0x14002642c`
- `0x1400275a0`
- `0x140027790`
- `0x140029020`
- `0x140029320`
- `0x140029f2c`
- `0x140032d64`
- `0x14003e364`
- `0x140043274`
- `0x140045d44`
- `0x14005498c`
- `0x140054c34`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x140029208`
- `ntoskrnl!_wcsicmp` at `0x140029208`

## string_xrefs

- `0x14002902f`: `AhcCdbCreate`
- `0x1400290b4`: `Failed to create cdb lock [%x]`
- `0x140029112`: `Failed to create cdb store [%x]`
- `0x1400291ac`: `SdbGetPathSystemSdbAlloc failed`
- `0x1400292a4`: `Failed to get trusted installer sid [%x]`

## pseudocode

```c
__int64 __fastcall AhcCdbCreate(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  unsigned int v4; // ebx
  int ProcessWowInfo; // eax
  __int64 v6; // r8
  const char *v7; // r9
  __int64 v8; // rbx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 i; // r14
  __int64 v14; // rax
  __int64 v16; // [rsp+20h] [rbp-58h]
  __int64 v17; // [rsp+88h] [rbp+10h] BYREF

  LOWORD(v17) = 0;
  AslLogCallPrintf(3, "AhcCdbCreate", 354, "Enter.");
  v3 = AslAlloc(v2, 328, 1);
  if ( !v3 )
  {
    AslLogCallPrintf(1, "AhcCdbCreate", 363, "Failed to allocate memory for cdb");
    return (unsigned int)-1073741801;
  }
  *(_OWORD *)(v3 + 16) = 0;
  *(_DWORD *)(v3 + 32) = 0;
  ProcessWowInfo = AhcLockCreate(v3);
  v4 = ProcessWowInfo;
  if ( ProcessWowInfo < 0 )
  {
    v6 = 377;
    v7 = "Failed to create cdb lock [%x]";
LABEL_25:
    LODWORD(v16) = ProcessWowInfo;
    AslLogCallPrintf(1, "AhcCdbCreate", v6, v7, v16);
    AhcCdbDelete(v3);
    return v4;
  }
  ProcessWowInfo = AhcStoreCreate(
                     (int)v3 + 8,
                     0,
                     (int)v3 + 16,
                     (unsigned int)AhcpCdbEntryAlloc,
                     (__int64)AhcpCdbEntryFree,
                     (__int64)AhcpCdbEntryCopy,
                     (__int64)AhcpCdbEntrySave,
                     (__int64)AhcpCdbEntryLoad);
  v4 = ProcessWowInfo;
  if ( ProcessWowInfo < 0 )
  {
    v6 = 395;
    v7 = "Failed to create cdb store [%x]";
    goto LABEL_25;
  }
  ProcessWowInfo = AslEnvGetProcessWowInfo(&v17, 0);
  v4 = ProcessWowInfo;
  if ( ProcessWowInfo < 0 )
  {
    v6 = 405;
    v7 = "AslEnvGetProcessWowInfo failed to determine processor info [%x]";
    goto LABEL_25;
  }
  v8 = 0;
  do
  {
    v9 = AslEnvVerifyGuestProcessorSupport(&v17, *((unsigned __int16 *)&qword_14001E2C8 + v8));
    if ( v9 >= 0 )
    {
      if ( (unsigned int)SdbGetPathSystemSdbAlloc(
                           v3 + 8 * (*(unsigned int *)(v3 + 320) + 6LL),
                           v10,
                           (char *)&qword_14001E2C8 + 2 * v8) )
      {
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          v14 = *(unsigned int *)(v3 + 320);
          if ( (unsigned int)i >= (unsigned int)v14 )
            break;
          if ( !_wcsicmp(*(const wchar_t **)(v3 + 8 * i + 48), *(const wchar_t **)(v3 + 8 * v14 + 48)) )
          {
            AslLogCallPrintf(
              3,
              "AhcCdbCreate",
              445,
              "Ignore duplicate sdb: %ws",
              *(_QWORD *)(v3 + 8LL * *(unsigned int *)(v3 + 320) + 48));
            v12 = *(_QWORD *)(v3 + 8LL * *(unsigned int *)(v3 + 320) + 48);
            goto LABEL_15;
          }
        }
        AslLogCallPrintf(
          3,
          "AhcCdbCreate",
          457,
          "sdb file is: %ws",
          *(_QWORD *)(v3 + 8LL * *(unsigned int *)(v3 + 320) + 48));
        ++*(_DWORD *)(v3 + 320);
      }
      else
      {
        AslLogCallPrintf(1, "AhcCdbCreate", 426, "SdbGetPathSystemSdbAlloc failed");
        v12 = *(_QWORD *)(v3 + 8LL * *(unsigned int *)(v3 + 320) + 48);
        if ( v12 )
        {
LABEL_15:
          AslFree(v11, v12);
          *(_QWORD *)(v3 + 8LL * *(unsigned int *)(v3 + 320) + 48) = 0;
        }
      }
    }
    else if ( v9 != -1073741637 )
    {
      AslLogCallPrintf(1, "AhcCdbCreate", 418, "AslEnvVerifyGuestProcessorSupport failed for architecture index %d", v8);
    }
    v8 = (unsigned int)(v8 + 1);
  }
  while ( (unsigned int)v8 < 4 );
  ProcessWowInfo = AhcGetTrustedInstallerSid(v3 + 40);
  v4 = ProcessWowInfo;
  if ( ProcessWowInfo < 0 )
  {
    v6 = 468;
    v7 = "Failed to get trusted installer sid [%x]";
    goto LABEL_25;
  }
  v17 = 240;
  if ( (int)AhcpCdbLoadFileTimeFromRegistry(v3 + 80, &v17, a1 + 128) < 0 || v17 != 240 )
    memset((void *)(v3 + 80), 0, 0xF0u);
  *(_QWORD *)(a1 + 32) = v3;
  return 0;
}

```

## disassembly

```asm
0x140029020  push    rbx
0x140029022  push    rbp
0x140029023  push    rsi
0x140029024  push    rdi
0x140029025  push    r14
0x140029027  push    r15
0x140029029  sub     rsp, 48h
0x14002902d  xor     eax, eax
0x14002902f  lea     rbp, aAhccdbcreate; "AhcCdbCreate"
0x140029036  mov     r15, rcx
0x140029039  mov     word ptr [rsp+78h+arg_8], ax
0x140029041  lea     r9, aEnter; "Enter."
0x140029048  mov     r8d, 162h
0x14002904e  mov     rdx, rbp
0x140029051  lea     ecx, [rax+3]
0x140029054  call    AslLogCallPrintf
0x140029059  mov     esi, 1
0x14002905e  mov     edx, 148h
0x140029063  mov     r8d, esi
0x140029066  call    AslAlloc
0x14002906b  mov     rdi, rax
0x14002906e  test    rax, rax
0x140029071  jnz     short loc_140029094
0x140029073  lea     r9, aFailedToAlloca_16; "Failed to allocate memory for cdb"
0x14002907a  mov     r8d, 16Bh
0x140029080  mov     rdx, rbp
0x140029083  mov     ecx, esi
0x140029085  call    AslLogCallPrintf
0x14002908a  mov     ebx, 0C0000017h
0x14002908f  jmp     loc_14002930A
0x140029094  xorps   xmm0, xmm0
0x140029097  xor     eax, eax
0x140029099  movups  xmmword ptr [rdi+10h], xmm0
0x14002909d  mov     rcx, rdi
0x1400290a0  mov     [rdi+20h], eax
0x1400290a3  call    AhcLockCreate
0x1400290a8  mov     ebx, eax
0x1400290aa  test    eax, eax
0x1400290ac  jns     short loc_1400290C0
0x1400290ae  mov     r8d, 179h
0x1400290b4  lea     r9, aFailedToCreate_6; "Failed to create cdb lock [%x]"
0x1400290bb  jmp     loc_1400292AB
0x1400290c0  lea     rax, AhcpCdbEntryLoad
0x1400290c7  xor     edx, edx
0x1400290c9  mov     [rsp+78h+var_40], rax
0x1400290ce  lea     rcx, [rdi+8]
0x1400290d2  lea     rax, AhcpCdbEntrySave
0x1400290d9  mov     [rsp+78h+var_48], rax
0x1400290de  lea     r9, AhcpCdbEntryAlloc
0x1400290e5  lea     rax, AhcpCdbEntryCopy
0x1400290ec  mov     [rsp+78h+var_50], rax
0x1400290f1  lea     r8, [rdi+10h]
0x1400290f5  lea     rax, AhcpCdbEntryFree
0x1400290fc  mov     [rsp+78h+var_58], rax
0x140029101  call    AhcStoreCreate
0x140029106  mov     ebx, eax
0x140029108  test    eax, eax
0x14002910a  jns     short loc_14002911E
0x14002910c  mov     r8d, 18Bh
0x140029112  lea     r9, aFailedToCreate; "Failed to create cdb store [%x]"
0x140029119  jmp     loc_1400292AB
0x14002911e  xor     edx, edx
0x140029120  lea     rcx, [rsp+78h+arg_8]
0x140029128  call    AslEnvGetProcessWowInfo
0x14002912d  mov     ebx, eax
0x14002912f  test    eax, eax
0x140029131  jns     short loc_140029145
0x140029133  mov     r8d, 195h
0x140029139  lea     r9, aAslenvgetproce_0; "AslEnvGetProcessWowInfo failed to deter"...
0x140029140  jmp     loc_1400292AB
0x140029145  xor     ebx, ebx
0x140029147  lea     rcx, qword_14001E2C8
0x14002914e  lea     r14, [rcx+rbx*2]
0x140029152  movzx   edx, word ptr [r14]
0x140029156  lea     rcx, [rsp+78h+arg_8]
0x14002915e  call    AslEnvVerifyGuestProcessorSupport
0x140029163  test    eax, eax
0x140029165  jns     short loc_140029192
0x140029167  cmp     eax, 0C00000BBh
0x14002916c  jz      loc_140029284
0x140029172  lea     r9, aAslenvverifygu_0; "AslEnvVerifyGuestProcessorSupport faile"...
0x140029179  mov     dword ptr [rsp+78h+var_58], ebx
0x14002917d  mov     r8d, 1A2h
0x140029183  mov     rdx, rbp
0x140029186  mov     ecx, esi
0x140029188  call    AslLogCallPrintf
0x14002918d  jmp     loc_140029284
0x140029192  mov     eax, [rdi+140h]
0x140029198  mov     r8, r14
0x14002919b  add     rax, 6
0x14002919f  lea     rcx, [rdi+rax*8]
0x1400291a3  call    SdbGetPathSystemSdbAlloc
0x1400291a8  test    eax, eax
0x1400291aa  jnz     short loc_1400291F0
0x1400291ac  lea     r9, aSdbgetpathsyst_2; "SdbGetPathSystemSdbAlloc failed"
0x1400291b3  mov     r8d, 1AAh
0x1400291b9  mov     rdx, rbp
0x1400291bc  mov     ecx, esi
0x1400291be  call    AslLogCallPrintf
0x1400291c3  mov     eax, [rdi+140h]
0x1400291c9  mov     rdx, [rdi+rax*8+30h]
0x1400291ce  test    rdx, rdx
0x1400291d1  jz      loc_140029284
0x1400291d7  call    AslFree
0x1400291dc  mov     eax, [rdi+140h]
0x1400291e2  mov     qword ptr [rdi+rax*8+30h], 0
0x1400291eb  jmp     loc_140029284
0x1400291f0  xor     r14d, r14d
0x1400291f3  mov     eax, [rdi+140h]
0x1400291f9  cmp     r14d, eax
0x1400291fc  jnb     short loc_140029254
0x1400291fe  mov     rdx, [rdi+rax*8+30h]; Str2
0x140029203  mov     rcx, [rdi+r14*8+30h]; Str1
0x140029208  call    cs:__imp__wcsicmp
0x14002920f  nop     dword ptr [rax+rax+00h]
0x140029214  test    eax, eax
0x140029216  jz      short loc_14002921D
0x140029218  add     r14d, esi
0x14002921b  jmp     short loc_1400291F3
0x14002921d  mov     eax, [rdi+140h]
0x140029223  lea     r9, aIgnoreDuplicat; "Ignore duplicate sdb: %ws"
0x14002922a  mov     r8d, 1BDh
0x140029230  mov     rdx, rbp
0x140029233  mov     rcx, [rdi+rax*8+30h]
0x140029238  mov     [rsp+78h+var_58], rcx
0x14002923d  mov     ecx, 3
0x140029242  call    AslLogCallPrintf
0x140029247  mov     edx, [rdi+140h]
0x14002924d  mov     rdx, [rdi+rdx*8+30h]
0x140029252  jmp     short loc_1400291D7
0x140029254  mov     eax, [rdi+140h]
0x14002925a  lea     r9, aSdbFileIsWs; "sdb file is: %ws"
0x140029261  mov     r8d, 1C9h
0x140029267  mov     rdx, rbp
0x14002926a  mov     rcx, [rdi+rax*8+30h]
0x14002926f  mov     [rsp+78h+var_58], rcx
0x140029274  mov     ecx, 3
0x140029279  call    AslLogCallPrintf
0x14002927e  add     [rdi+140h], esi
0x140029284  add     ebx, esi
0x140029286  cmp     ebx, 4
0x140029289  jb      loc_140029147
0x14002928f  lea     rcx, [rdi+28h]
0x140029293  call    AhcGetTrustedInstallerSid
0x140029298  mov     ebx, eax
0x14002929a  test    eax, eax
0x14002929c  jns     short loc_1400292C3
0x14002929e  mov     r8d, 1D4h
0x1400292a4  lea     r9, aFailedToGetTru; "Failed to get trusted installer sid [%x"...
0x1400292ab  mov     rdx, rbp
0x1400292ae  mov     dword ptr [rsp+78h+var_58], eax
0x1400292b2  mov     ecx, esi
0x1400292b4  call    AslLogCallPrintf
0x1400292b9  mov     rcx, rdi
0x1400292bc  call    AhcCdbDelete
0x1400292c1  jmp     short loc_14002930A
0x1400292c3  mov     esi, 0F0h
0x1400292c8  lea     r8, [r15+80h]
0x1400292cf  lea     rdx, [rsp+78h+arg_8]
0x1400292d7  mov     [rsp+78h+arg_8], rsi
0x1400292df  lea     rcx, [rdi+50h]
0x1400292e3  call    AhcpCdbLoadFileTimeFromRegistry
0x1400292e8  test    eax, eax
0x1400292ea  js      short loc_1400292F6
0x1400292ec  cmp     [rsp+78h+arg_8], rsi
0x1400292f4  jz      short loc_140029304
0x1400292f6  mov     r8, rsi; Size
0x1400292f9  lea     rcx, [rdi+50h]; void *
0x1400292fd  xor     edx, edx; Val
0x1400292ff  call    memset
0x140029304  mov     [r15+20h], rdi
0x140029308  xor     ebx, ebx
0x14002930a  mov     eax, ebx
0x14002930c  add     rsp, 48h
0x140029310  pop     r15
0x140029312  pop     r14
0x140029314  pop     rdi
0x140029315  pop     rsi
0x140029316  pop     rbp
0x140029317  pop     rbx
0x140029318  retn
```
