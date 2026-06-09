# GetServerConfig(ldap *,ushort const *,int,_KDS_CONFIGURATION * *)

- ea: `0x180007060`
- end: `0x180007133`
- name: `?GetServerConfig@@YAJPEAUldap@@PEBGHPEAPEAU_KDS_CONFIGURATION@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(LDAP *ld, PWSTR base, int, struct _KDS_CONFIGURATION **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004a00`

## callees

- `0x180006d90`
- `0x180006fb0`
- `0x180007060`
- `0x18000713c`
- `0x18001a450`

## string_xrefs

- `0x180007098`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdssrvconfig.cxx`
- `0x1800070fb`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdssrvconfig.cxx`

## pseudocode

```c
__int64 __fastcall GetServerConfig(LDAP *ld, PWSTR base, int a3, struct _KDS_CONFIGURATION **a4)
{
  signed int DefaultServerConfig; // eax
  signed int v9; // ebx
  struct _KDS_CONFIGURATION *v10; // rdi
  signed int ServerConfigFromAD; // eax
  struct _KDS_CONFIGURATION *lpMem; // [rsp+20h] [rbp-48h] BYREF

  lpMem = 0;
  DefaultServerConfig = GetDefaultServerConfig(&lpMem);
  v9 = DefaultServerConfig;
  if ( DefaultServerConfig >= 0 )
  {
    v10 = lpMem;
    ServerConfigFromAD = GetServerConfigFromAD(ld, base, (unsigned int *)lpMem);
    v9 = ServerConfigFromAD;
    if ( ServerConfigFromAD == -2147024864 || ServerConfigFromAD == -2147024880 || ServerConfigFromAD == -2147024802 )
      v9 = 0;
    if ( !a3 || *((_DWORD *)v10 + 18) )
    {
      if ( v9 >= 0 )
      {
        *a4 = v10;
        v10 = 0;
      }
      else
      {
        SidKeyDebugTraceError(v9, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdssrvconfig.cxx", 0x2B6u);
      }
    }
    else
    {
      v9 = -2146893819;
    }
  }
  else
  {
    SidKeyDebugTraceError(
      DefaultServerConfig,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdssrvconfig.cxx",
      0x29Cu);
    v10 = lpMem;
  }
  if ( v10 )
    FreeServerConfig(v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007060  push    rbx
0x180007062  push    rbp
0x180007063  push    rsi
0x180007064  push    rdi
0x180007065  push    r14
0x180007067  push    r15
0x180007069  sub     rsp, 38h
0x18000706d  mov     r15, rcx
0x180007070  mov     [rsp+68h+lpMem], 0
0x180007079  lea     rcx, [rsp+68h+lpMem]; struct _KDS_CONFIGURATION **
0x18000707e  mov     r14, r9
0x180007081  mov     esi, r8d
0x180007084  mov     rbp, rdx
0x180007087  call    ?GetDefaultServerConfig@@YAJPEAPEAU_KDS_CONFIGURATION@@@Z; GetDefaultServerConfig(_KDS_CONFIGURATION * *)
0x18000708c  mov     ebx, eax
0x18000708e  test    eax, eax
0x180007090  jns     short loc_1800070B4
0x180007092  mov     r9d, 29Ch; unsigned int
0x180007098  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000709f  lea     rdx, aHr; "hr"
0x1800070a6  mov     ecx, eax; unsigned int
0x1800070a8  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800070ad  mov     rdi, [rsp+68h+lpMem]
0x1800070b2  jmp     short loc_180007117
0x1800070b4  mov     rdi, [rsp+68h+lpMem]
0x1800070b9  mov     rdx, rbp; base
0x1800070bc  mov     r8, rdi; unsigned int *
0x1800070bf  mov     rcx, r15; ld
0x1800070c2  call    GetServerConfigFromAD
0x1800070c7  mov     ebx, eax
0x1800070c9  cmp     eax, 80070020h
0x1800070ce  jz      short loc_1800070DE
0x1800070d0  cmp     eax, 80070010h
0x1800070d5  jz      short loc_1800070DE
0x1800070d7  cmp     eax, 8007005Eh
0x1800070dc  jnz     short loc_1800070E0
0x1800070de  xor     ebx, ebx
0x1800070e0  test    esi, esi
0x1800070e2  jz      short loc_1800070F1
0x1800070e4  cmp     dword ptr [rdi+48h], 0
0x1800070e8  jnz     short loc_1800070F1
0x1800070ea  mov     ebx, 80090005h
0x1800070ef  jmp     short loc_180007117
0x1800070f1  test    ebx, ebx
0x1800070f3  jns     short loc_180007112
0x1800070f5  mov     r9d, 2B6h; unsigned int
0x1800070fb  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180007102  lea     rdx, aHr; "hr"
0x180007109  mov     ecx, ebx; unsigned int
0x18000710b  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180007110  jmp     short loc_180007117
0x180007112  mov     [r14], rdi
0x180007115  xor     edi, edi
0x180007117  test    rdi, rdi
0x18000711a  jz      short loc_180007124
0x18000711c  mov     rcx, rdi; lpMem
0x18000711f  call    ?FreeServerConfig@@YAXPEAU_KDS_CONFIGURATION@@@Z; FreeServerConfig(_KDS_CONFIGURATION *)
0x180007124  mov     eax, ebx
0x180007126  add     rsp, 38h
0x18000712a  pop     r15
0x18000712c  pop     r14
0x18000712e  pop     rdi
0x18000712f  pop     rsi
0x180007130  pop     rbp
0x180007131  pop     rbx
0x180007132  retn
```
