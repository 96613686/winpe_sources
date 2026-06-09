# MSCryptDsaFinalizeKeyPair

- ea: `0x1800698a0`
- end: `0x1800699db`
- name: `MSCryptDsaFinalizeKeyPair`
- size: `315`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18001bf34`
- `0x18005196c`
- `0x180056cf0`
- `0x1800693ac`
- `0x1800698a0`
- `0x180071418`
- `0x180071edc`

## string_xrefs

- `0x1800699ba`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptDsaFinalizeKeyPair(__int64 a1, int a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rdx
  int v8; // ecx
  __int64 SymCryptDlgroupHashAlgorithm; // r9
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rax
  __int64 v14; // [rsp+30h] [rbp+8h] BYREF

  v14 = 0;
  if ( !a1 || a2 && a2 != 24 )
  {
    v4 = 1259;
    goto LABEL_24;
  }
  v2 = ValidateDSAKey(a1, 0, &v14);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 1266;
LABEL_6:
    v5 = (unsigned int)v2;
LABEL_25:
    DebugTraceError(v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v4);
    return v3;
  }
  v6 = v14;
  if ( (*(_BYTE *)(v14 + 28) & 1) != 0 )
  {
    v3 = -1073741816;
    v4 = 1274;
    v5 = 3221225480LL;
    goto LABEL_25;
  }
  v7 = 2;
  if ( (*(_BYTE *)(v14 + 28) & 2) != 0 )
  {
    if ( !*(_QWORD *)(v14 + 32) || (*(_BYTE *)(v14 + 28) & 4) != 0 )
    {
      v4 = 1287;
LABEL_24:
      v5 = 3221225485LL;
      v3 = -1073741811;
      goto LABEL_25;
    }
  }
  else
  {
    v8 = *(_DWORD *)(v14 + 20);
    SymCryptDlgroupHashAlgorithm = 0;
    if ( v8 )
    {
      if ( v8 == 1 )
        SymCryptDlgroupHashAlgorithm = GetSymCryptDlgroupHashAlgorithm(*(unsigned int *)(v14 + 24), 2);
      else
        v10 = 0;
    }
    else
    {
      v10 = 1;
    }
    v11 = SymCryptDlgroupGenerate(SymCryptDlgroupHashAlgorithm, v10, *(_QWORD *)(v6 + 32));
    if ( v11 )
    {
      v2 = SymcryptErrorCodeToNtStatus(v11);
      v3 = v2;
      v4 = 1306;
      goto LABEL_6;
    }
  }
  v12 = SymCryptDlkeyAllocate(*(_QWORD *)(v6 + 32), v7);
  *(_QWORD *)(v6 + 40) = v12;
  if ( !v12 )
  {
    v3 = -1073741801;
    v4 = 1315;
    v5 = 3221225495LL;
    goto LABEL_25;
  }
  SymCryptDlkeyGenerate(4096, v12);
  *(_DWORD *)(v6 + 28) |= 1u;
  return v3;
}

```

## disassembly

```asm
0x1800698a0  mov     [rsp+arg_8], rbx
0x1800698a5  push    rdi
0x1800698a6  sub     rsp, 20h
0x1800698aa  mov     [rsp+28h+arg_0], 0
0x1800698b3  test    rcx, rcx
0x1800698b6  jz      loc_1800699AA
0x1800698bc  test    edx, edx
0x1800698be  jz      short loc_1800698C9
0x1800698c0  cmp     edx, 18h
0x1800698c3  jnz     loc_1800699AA
0x1800698c9  lea     r8, [rsp+28h+arg_0]
0x1800698ce  xor     edx, edx
0x1800698d0  call    ValidateDSAKey
0x1800698d5  mov     ebx, eax
0x1800698d7  test    eax, eax
0x1800698d9  jns     short loc_1800698E8
0x1800698db  mov     r9d, 4F2h
0x1800698e1  mov     ecx, eax
0x1800698e3  jmp     loc_1800699BA
0x1800698e8  mov     rdi, [rsp+28h+arg_0]
0x1800698ed  test    byte ptr [rdi+1Ch], 1
0x1800698f1  jz      short loc_180069908
0x1800698f3  mov     ebx, 0C0000008h
0x1800698f8  mov     r9d, 4FAh
0x1800698fe  mov     ecx, 0C0000008h
0x180069903  jmp     loc_1800699BA
0x180069908  mov     edx, 2
0x18006990d  test    [rdi+1Ch], dl
0x180069910  jz      short loc_18006992A
0x180069912  cmp     qword ptr [rdi+20h], 0
0x180069917  jz      short loc_18006991F
0x180069919  test    byte ptr [rdi+1Ch], 4
0x18006991d  jz      short loc_180069973
0x18006991f  mov     r9d, 507h
0x180069925  jmp     loc_1800699B0
0x18006992a  mov     ecx, [rdi+14h]
0x18006992d  xor     r9d, r9d
0x180069930  test    ecx, ecx
0x180069932  jz      short loc_18006994A
0x180069934  cmp     ecx, 1
0x180069937  jz      short loc_18006993D
0x180069939  xor     edx, edx
0x18006993b  jmp     short loc_18006994F
0x18006993d  mov     ecx, [rdi+18h]
0x180069940  call    GetSymCryptDlgroupHashAlgorithm
0x180069945  mov     r9, rax
0x180069948  jmp     short loc_18006994F
0x18006994a  mov     edx, 1
0x18006994f  mov     r8, [rdi+20h]
0x180069953  mov     rcx, r9
0x180069956  call    SymCryptDlgroupGenerate
0x18006995b  test    eax, eax
0x18006995d  jz      short loc_180069973
0x18006995f  mov     ecx, eax
0x180069961  call    SymcryptErrorCodeToNtStatus
0x180069966  mov     ebx, eax
0x180069968  mov     r9d, 51Ah
0x18006996e  jmp     loc_1800698E1
0x180069973  mov     rcx, [rdi+20h]
0x180069977  call    SymCryptDlkeyAllocate
0x18006997c  mov     [rdi+28h], rax
0x180069980  test    rax, rax
0x180069983  jnz     short loc_180069997
0x180069985  mov     ebx, 0C0000017h
0x18006998a  mov     r9d, 523h
0x180069990  mov     ecx, 0C0000017h
0x180069995  jmp     short loc_1800699BA
0x180069997  mov     rdx, rax
0x18006999a  mov     ecx, 1000h
0x18006999f  call    SymCryptDlkeyGenerate
0x1800699a4  or      dword ptr [rdi+1Ch], 1
0x1800699a8  jmp     short loc_1800699CD
0x1800699aa  mov     r9d, 4EBh
0x1800699b0  mov     ecx, 0C000000Dh
0x1800699b5  mov     ebx, 0C000000Dh
0x1800699ba  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800699c1  lea     rdx, aStatus; "Status"
0x1800699c8  call    DebugTraceError
0x1800699cd  mov     eax, ebx
0x1800699cf  mov     rbx, [rsp+28h+arg_8]
0x1800699d4  add     rsp, 20h
0x1800699d8  pop     rdi
0x1800699d9  retn
```
