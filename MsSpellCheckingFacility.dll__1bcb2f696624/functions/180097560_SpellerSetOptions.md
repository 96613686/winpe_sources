# SpellerSetOptions

- ea: `0x180097560`
- end: `0x18009781a`
- name: `SpellerSetOptions`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180093a10`

## callees

- `0x180052284`
- `0x180096864`
- `0x180097560`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800977d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800977d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180097781`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180097781`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800977cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800977cb`

## pseudocode

```c
__int64 __fastcall SpellerSetOptions(__int64 a1, int a2, int a3)
{
  __int64 v4; // rbx
  unsigned int v5; // edi
  int v6; // edx
  bool v7; // r11
  int v8; // r10d
  bool v9; // cl
  int v10; // r9d
  bool v11; // si
  unsigned int v12; // eax
  LSTATUS v13; // esi
  DWORD Type; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF
  CNLException *v16; // [rsp+40h] [rbp-28h] BYREF
  int Data; // [rsp+70h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+20h] BYREF

  if ( !a1 )
    return 8454146;
  v4 = a1 + 488;
  v5 = 0;
  if ( !a2 )
  {
    *(_BYTE *)(a1 + 1032) = (a3 & 0x40) != 0;
    *(_BYTE *)(a1 + 1029) = a3 & 1;
    *(_BYTE *)(a1 + 1028) = (a3 & 4) != 0;
    *(_BYTE *)(a1 + 1031) = (a3 & 0x20000) != 0;
    *(_BYTE *)(a1 + 1027) = (a3 & 2) != 0;
    *(_BYTE *)(a1 + 1030) = (a3 & 0x4000) != 0;
    *(_BYTE *)(a1 + 1088) = (a3 & 0x8000) != 0;
    *(_BYTE *)(a1 + 497) = (a3 & 0x10) != 0;
    v6 = a3 & 0x10000000;
    v7 = (a3 & 0x10000000) != 0;
    *(_BYTE *)(a1 + 1056) = v7;
    v8 = a3 & 0x20000000;
    v9 = (a3 & 0x20000000) != 0;
    *(_BYTE *)(v4 + 569) = v9;
    v10 = a3 & 0x40000000;
    v11 = (a3 & 0x40000000) != 0;
    *(_BYTE *)(v4 + 570) = v11;
    v12 = a3 & 0xF0000000;
    if ( (a3 & 0xF0000000) != 0 )
    {
      if ( v12 == 0x10000000 )
      {
        *(_WORD *)(v4 + 573) = 256;
LABEL_14:
        *(_BYTE *)(v4 + 572) = 0;
        goto LABEL_17;
      }
      if ( v12 != 0x20000000 )
      {
        if ( v12 != 805306368 )
          goto LABEL_17;
        *(_WORD *)(v4 + 573) = 257;
        goto LABEL_14;
      }
      *(_WORD *)(v4 + 572) = 1;
    }
    else
    {
      *(_WORD *)(v4 + 572) = 256;
    }
    *(_BYTE *)(v4 + 574) = 0;
LABEL_17:
    *(_BYTE *)(v4 + 538) = v9;
    *(_BYTE *)(v4 + 2) = v11;
    *(_BYTE *)v4 = v7;
    *(_BYTE *)(v4 + 1) = v9;
    if ( v6 && v8 )
      *(_DWORD *)(v4 + 552) = 0;
    else
      *(_DWORD *)(v4 + 552) = 2 - (v6 != 0);
    if ( v10 && a3 < 0 )
      *(_DWORD *)(v4 + 556) = 0;
    else
      *(_DWORD *)(v4 + 556) = 2 - (v10 != 0);
    if ( v6 && v8 )
      *(_DWORD *)(v4 + 564) = 0;
    else
      *(_DWORD *)(v4 + 564) = 2 - (v6 != 0);
    if ( (*(_WORD *)(v4 + 16) & 0x3FF) == 0x16 )
    {
      try
      {
        SetPortugueseReform((struct Speller::CSpellerDataStorage *)v4, a3);
      }
      catch ( CNLException *v16 )
      {
        return 2;
      }
      catch ( _com_error )
      {
        return 2;
      }
    }
    Speller::CSpellerDataStorage::SetupDialectMask((Speller::CSpellerDataStorage *)v4);
    if ( (*(_WORD *)(v4 + 16) & 0x3FF) == 1 )
    {
      hKey = 0;
      if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SOFTWARE\\MICROSOFT\\Natural Language\\TraceOutput", 0, 1u, &hKey) )
      {
        Data = 0;
        Type = 0;
        cbData = 4;
        v13 = RegQueryValueExA(hKey, "Dogfood", 0, &Type, (LPBYTE)&Data, &cbData);
        RegCloseKey(hKey);
        if ( !v13 )
        {
          if ( Data )
          {
            *(_BYTE *)(v4 + 570) = 1;
            Speller::CSpellerDataStorage::SetupDialectMask((Speller::CSpellerDataStorage *)v4);
          }
        }
      }
    }
    return v5;
  }
  if ( a2 == 3 )
    *(_DWORD *)(a1 + 1092) = a3;
  else
    return 5;
  return v5;
}

```

## disassembly

```asm
0x180097560  mov     [rsp+arg_8], rbx
0x180097565  mov     [rsp+arg_10], rsi
0x18009756a  push    rdi
0x18009756b  push    r14
0x18009756d  push    r15
0x18009756f  sub     rsp, 50h
0x180097573  xor     r14d, r14d
0x180097576  test    rcx, rcx
0x180097579  jnz     short loc_180097585
0x18009757b  mov     eax, 810002h
0x180097580  jmp     loc_180097803
0x180097585  lea     rbx, [rcx+1E8h]
0x18009758c  mov     edi, r14d
0x18009758f  test    edx, edx
0x180097591  jz      short loc_1800975AE
0x180097593  cmp     edx, 3
0x180097596  jz      short loc_1800975A2
0x180097598  mov     edi, 5
0x18009759d  jmp     loc_1800977F8
0x1800975a2  mov     [rbx+25Ch], r8d
0x1800975a9  jmp     loc_1800977F8
0x1800975ae  mov     eax, r8d
0x1800975b1  shr     eax, 6
0x1800975b4  mov     r15d, 1
0x1800975ba  and     al, r15b
0x1800975bd  mov     [rbx+220h], al
0x1800975c3  mov     al, r8b
0x1800975c6  and     al, r15b
0x1800975c9  mov     [rbx+21Dh], al
0x1800975cf  mov     eax, r8d
0x1800975d2  shr     eax, 2
0x1800975d5  and     al, r15b
0x1800975d8  mov     [rbx+21Ch], al
0x1800975de  mov     eax, r8d
0x1800975e1  shr     eax, 11h
0x1800975e4  and     al, r15b
0x1800975e7  mov     [rbx+21Fh], al
0x1800975ed  mov     eax, r8d
0x1800975f0  shr     eax, 1
0x1800975f2  and     al, r15b
0x1800975f5  mov     [rbx+21Bh], al
0x1800975fb  mov     eax, r8d
0x1800975fe  shr     eax, 0Eh
0x180097601  and     al, r15b
0x180097604  mov     [rbx+21Eh], al
0x18009760a  mov     eax, r8d
0x18009760d  shr     eax, 0Fh
0x180097610  and     al, r15b
0x180097613  mov     [rbx+258h], al
0x180097619  mov     eax, r8d
0x18009761c  shr     eax, 4
0x18009761f  and     al, r15b
0x180097622  mov     [rbx+9], al
0x180097625  mov     edx, r8d
0x180097628  and     edx, 10000000h
0x18009762e  setnz   r11b
0x180097632  mov     [rbx+238h], r11b
0x180097639  mov     r10d, r8d
0x18009763c  and     r10d, 20000000h
0x180097643  setnz   cl
0x180097646  mov     [rbx+239h], cl
0x18009764c  mov     r9d, r8d
0x18009764f  and     r9d, 40000000h
0x180097656  setnz   sil
0x18009765a  mov     [rbx+23Ah], sil
0x180097661  mov     eax, r8d
0x180097664  and     eax, 0F0000000h
0x180097669  jz      short loc_1800976A7
0x18009766b  cmp     eax, 10000000h
0x180097670  jz      short loc_180097695
0x180097672  cmp     eax, 20000000h
0x180097677  jz      short loc_18009768B
0x180097679  cmp     eax, 30000000h
0x18009767e  jnz     short loc_1800976B7
0x180097680  mov     word ptr [rbx+23Dh], 101h
0x180097689  jmp     short loc_18009769E
0x18009768b  mov     [rbx+23Ch], r15w
0x180097693  jmp     short loc_1800976B0
0x180097695  mov     word ptr [rbx+23Dh], 100h
0x18009769e  mov     [rbx+23Ch], r14b
0x1800976a5  jmp     short loc_1800976B7
0x1800976a7  mov     word ptr [rbx+23Ch], 100h
0x1800976b0  mov     [rbx+23Eh], r14b
0x1800976b7  mov     [rbx+21Ah], cl
0x1800976bd  mov     [rbx+2], sil
0x1800976c1  mov     [rbx], r11b
0x1800976c4  mov     [rbx+1], cl
0x1800976c7  test    edx, edx
0x1800976c9  jz      short loc_1800976D9
0x1800976cb  test    r10d, r10d
0x1800976ce  jz      short loc_1800976D9
0x1800976d0  mov     [rbx+228h], r14d
0x1800976d7  jmp     short loc_1800976E8
0x1800976d9  mov     eax, edx
0x1800976db  neg     eax
0x1800976dd  sbb     ecx, ecx
0x1800976df  add     ecx, 2
0x1800976e2  mov     [rbx+228h], ecx
0x1800976e8  test    r9d, r9d
0x1800976eb  jz      short loc_1800976FB
0x1800976ed  test    r8d, r8d
0x1800976f0  jns     short loc_1800976FB
0x1800976f2  mov     [rbx+22Ch], r14d
0x1800976f9  jmp     short loc_180097709
0x1800976fb  neg     r9d
0x1800976fe  sbb     eax, eax
0x180097700  add     eax, 2
0x180097703  mov     [rbx+22Ch], eax
0x180097709  test    edx, edx
0x18009770b  jz      short loc_18009771B
0x18009770d  test    r10d, r10d
0x180097710  jz      short loc_18009771B
0x180097712  mov     [rbx+234h], r14d
0x180097719  jmp     short loc_180097728
0x18009771b  neg     edx
0x18009771d  sbb     eax, eax
0x18009771f  add     eax, 2
0x180097722  mov     [rbx+234h], eax
0x180097728  movzx   eax, word ptr [rbx+10h]
0x18009772c  mov     esi, 3FFh
0x180097731  and     ax, si
0x180097734  cmp     ax, 16h
0x180097738  jnz     short loc_180097745
0x18009773a  mov     edx, r8d; int
0x18009773d  mov     rcx, rbx; struct Speller::CSpellerDataStorage *
0x180097740  call    ?SetPortugueseReform@@YAXPEAVCSpellerDataStorage@Speller@@H@Z; SetPortugueseReform(Speller::CSpellerDataStorage *,int)
0x180097745  mov     rcx, rbx; this
0x180097748  call    ?SetupDialectMask@CSpellerDataStorage@Speller@@QEAAXXZ; Speller::CSpellerDataStorage::SetupDialectMask(void)
0x18009774d  movzx   eax, word ptr [rbx+10h]
0x180097751  and     ax, si
0x180097754  cmp     ax, r15w
0x180097758  jnz     loc_1800977F8
0x18009775e  mov     [rsp+68h+hKey], r14
0x180097763  lea     rax, [rsp+68h+hKey]
0x180097768  mov     [rsp+68h+phkResult], rax; phkResult
0x18009776d  mov     r9d, r15d; samDesired
0x180097770  xor     r8d, r8d; ulOptions
0x180097773  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\MICROSOFT\\Natural Language\\"...
0x18009777a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180097781  call    cs:__imp_RegOpenKeyExA
0x180097787  test    eax, eax
0x180097789  jnz     short loc_1800977F8
0x18009778b  mov     [rsp+68h+Data], r14d
0x180097790  mov     [rsp+68h+Type], r14d
0x180097795  mov     [rsp+68h+cbData], 4
0x1800977a0  lea     rax, [rsp+68h+cbData]
0x1800977a8  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800977ad  lea     rax, [rsp+68h+Data]
0x1800977b2  mov     [rsp+68h+phkResult], rax; lpData
0x1800977b7  lea     r9, [rsp+68h+Type]; lpType
0x1800977bc  xor     r8d, r8d; lpReserved
0x1800977bf  lea     rdx, aDogfood; "Dogfood"
0x1800977c6  mov     rcx, [rsp+68h+hKey]; hKey
0x1800977cb  call    cs:__imp_RegQueryValueExA
0x1800977d1  mov     esi, eax
0x1800977d3  mov     rcx, [rsp+68h+hKey]; hKey
0x1800977d8  call    cs:__imp_RegCloseKey
0x1800977de  test    esi, esi
0x1800977e0  jnz     short loc_1800977F8
0x1800977e2  cmp     [rsp+68h+Data], r14d
0x1800977e7  jz      short loc_1800977F8
0x1800977e9  mov     [rbx+23Ah], r15b
0x1800977f0  mov     rcx, rbx; this
0x1800977f3  call    ?SetupDialectMask@CSpellerDataStorage@Speller@@QEAAXXZ; Speller::CSpellerDataStorage::SetupDialectMask(void)
0x1800977f8  mov     eax, edi
0x1800977fa  jmp     short loc_180097803
0x1800977fc  jmp     short $+2
0x1800977fe  mov     eax, 2
0x180097803  lea     r11, [rsp+68h+var_18]
0x180097808  mov     rbx, [r11+28h]
0x18009780c  mov     rsi, [r11+30h]
0x180097810  mov     rsp, r11
0x180097813  pop     r15
0x180097815  pop     r14
0x180097817  pop     rdi
0x180097818  retn
```
