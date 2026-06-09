# FaxSetConfigurationA

- ea: `0x180011640`
- end: `0x1800118cd`
- name: `FaxSetConfigurationA`
- size: `653`
- prototype: `BOOL __stdcall(HANDLE FaxHandle, const FAX_CONFIGURATIONA *FaxConfig)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180011640`
- `0x18002bb58`
- `0x18002bc50`
- `0x180033d10`
- `0x18003d4ca`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800117f6`
- `RPCRT4!NdrClientCall3` at `0x1800117f6`
- `KERNEL32!SetLastError` at `0x1800116bf`
- `KERNEL32!SetLastError` at `0x180011700`
- `KERNEL32!SetLastError` at `0x18001186b`
- `KERNEL32!SetLastError` at `0x180011885`
- `KERNEL32!SetLastError` at `0x1800116bf`
- `KERNEL32!SetLastError` at `0x180011700`
- `KERNEL32!SetLastError` at `0x18001186b`
- `KERNEL32!SetLastError` at `0x180011885`

## pseudocode

```c
BOOL __stdcall FaxSetConfigurationA(HANDLE FaxHandle, const FAX_CONFIGURATIONA *FaxConfig)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  const CHAR *ArchiveDirectory; // rcx
  DWORD Pointer; // ebx
  DWORD SizeOfStruct; // edi
  _OWORD v10[3]; // [rsp+40h] [rbp-68h] BYREF
  LPVOID lpMem[7]; // [rsp+70h] [rbp-38h]

  memset_0(v10, 0, 0x40u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !FaxHandle || !*(_DWORD *)FaxHandle || *((_DWORD *)FaxHandle + 4) )
  {
    SetLastError(6u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 25;
LABEL_34:
    WPP_SF_(v4[2], v5, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( !FaxConfig )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 26;
    goto LABEL_34;
  }
  if ( FaxConfig->SizeOfStruct != 64 )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 27;
    goto LABEL_34;
  }
  v10[0] = *(_OWORD *)&FaxConfig->SizeOfStruct;
  v10[1] = *(_OWORD *)&FaxConfig->Branding;
  v10[2] = *(_OWORD *)&FaxConfig->StartCheapTime.Hour;
  *(_OWORD *)lpMem = *(_OWORD *)&FaxConfig->ArchiveDirectory;
  ArchiveDirectory = FaxConfig->ArchiveDirectory;
  if ( !ArchiveDirectory || (lpMem[0] = AnsiStringToUnicodeString(ArchiveDirectory)) != 0 )
  {
    lpMem[1] = 0;
    SizeOfStruct = FaxConfig->SizeOfStruct;
    FaxConfig->SizeOfStruct = GetWin32StructSize(&fax_configuration_fields);
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x14u,
                              0,
                              **((_QWORD **)FaxHandle + 4),
                              v10).Pointer;
    FaxConfig->SizeOfStruct = SizeOfStruct;
  }
  else
  {
    Pointer = 14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    }
  }
  if ( lpMem[0] )
    pMemFree(lpMem[0]);
  if ( !Pointer )
    return 1;
  SetLastError(Pointer);
  return 0;
}

```

## disassembly

```asm
0x180011640  push    rbx
0x180011642  push    rsi
0x180011643  push    rdi
0x180011644  push    r14
0x180011646  sub     rsp, 88h
0x18001164d  mov     rsi, rdx
0x180011650  mov     rbx, rcx
0x180011653  xor     edx, edx; Val
0x180011655  lea     r8d, [rdx+40h]; Size
0x180011659  lea     rcx, [rsp+0A8h+var_68]; void *
0x18001165e  call    memset_0
0x180011663  lea     r14, WPP_GLOBAL_Control
0x18001166a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011671  mov     edi, 1000h
0x180011676  cmp     rcx, r14
0x180011679  jz      short loc_18001169B
0x18001167b  test    [rcx+1Ch], edi
0x18001167e  jz      short loc_18001169B
0x180011680  cmp     byte ptr [rcx+19h], 5
0x180011684  jb      short loc_18001169B
0x180011686  mov     edx, 18h
0x18001168b  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180011692  mov     rcx, [rcx+10h]
0x180011696  call    WPP_SF_
0x18001169b  test    rbx, rbx
0x18001169e  jz      loc_180011880
0x1800116a4  cmp     dword ptr [rbx], 0
0x1800116a7  jz      loc_180011880
0x1800116ad  cmp     dword ptr [rbx+10h], 0
0x1800116b1  jnz     loc_180011880
0x1800116b7  test    rsi, rsi
0x1800116ba  jnz     short loc_1800116F6
0x1800116bc  lea     ecx, [rsi+57h]; dwErrCode
0x1800116bf  call    cs:__imp_SetLastError
0x1800116c6  nop     dword ptr [rax+rax+00h]
0x1800116cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116d2  cmp     rcx, r14
0x1800116d5  jz      loc_1800118BD
0x1800116db  test    [rcx+1Ch], edi
0x1800116de  jz      loc_1800118BD
0x1800116e4  cmp     byte ptr [rcx+19h], 2
0x1800116e8  jb      loc_1800118BD
0x1800116ee  lea     edx, [rsi+1Ah]
0x1800116f1  jmp     loc_1800118AD
0x1800116f6  cmp     dword ptr [rsi], 40h ; '@'
0x1800116f9  jz      short loc_180011739
0x1800116fb  mov     ecx, 57h ; 'W'; dwErrCode
0x180011700  call    cs:__imp_SetLastError
0x180011707  nop     dword ptr [rax+rax+00h]
0x18001170c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011713  cmp     rcx, r14
0x180011716  jz      loc_1800118BD
0x18001171c  test    [rcx+1Ch], edi
0x18001171f  jz      loc_1800118BD
0x180011725  cmp     byte ptr [rcx+19h], 2
0x180011729  jb      loc_1800118BD
0x18001172f  mov     edx, 1Bh
0x180011734  jmp     loc_1800118AD
0x180011739  movups  xmm0, xmmword ptr [rsi]
0x18001173c  movaps  [rsp+0A8h+var_68], xmm0
0x180011741  movups  xmm1, xmmword ptr [rsi+10h]
0x180011745  movaps  [rsp+0A8h+var_58], xmm1
0x18001174a  movups  xmm0, xmmword ptr [rsi+20h]
0x18001174e  movaps  [rsp+0A8h+var_48], xmm0
0x180011753  movups  xmm1, xmmword ptr [rsi+30h]
0x180011757  movaps  xmmword ptr [rsp+0A8h+lpMem], xmm1
0x18001175c  mov     rcx, [rsi+30h]; lpMultiByteStr
0x180011760  test    rcx, rcx
0x180011763  jz      short loc_1800117B2
0x180011765  call    AnsiStringToUnicodeString
0x18001176a  mov     [rsp+0A8h+lpMem], rax
0x18001176f  test    rax, rax
0x180011772  jnz     short loc_1800117B2
0x180011774  lea     ebx, [rax+0Eh]
0x180011777  mov     rcx, cs:WPP_GLOBAL_Control
0x18001177e  cmp     rcx, r14
0x180011781  jz      loc_180011856
0x180011787  test    [rcx+1Ch], edi
0x18001178a  jz      loc_180011856
0x180011790  cmp     byte ptr [rcx+19h], 2
0x180011794  jb      loc_180011856
0x18001179a  lea     edx, [rax+1Ch]
0x18001179d  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x1800117a4  mov     rcx, [rcx+10h]
0x1800117a8  call    WPP_SF_
0x1800117ad  jmp     loc_180011856
0x1800117b2  mov     [rsp+0A8h+lpMem+8], 0
0x1800117bb  mov     edi, [rsi]
0x1800117bd  lea     rcx, ?fax_configuration_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_configuration_fields
0x1800117c4  call    GetWin32StructSize
0x1800117c9  mov     [rsi], eax
0x1800117cb  mov     rax, [rbx+20h]
0x1800117cf  mov     [rsp+0A8h+arg_0], 0
0x1800117db  lea     rcx, [rsp+0A8h+var_68]
0x1800117e0  mov     [rsp+0A8h+var_88], rcx
0x1800117e5  mov     r9, [rax]
0x1800117e8  xor     r8d, r8d; pReturnValue
0x1800117eb  lea     edx, [r8+14h]; nProcNum
0x1800117ef  lea     rcx, pProxyInfo; pProxyInfo
0x1800117f6  call    cs:__imp_NdrClientCall3
0x1800117fd  nop     dword ptr [rax+rax+00h]
0x180011802  mov     rbx, rax
0x180011805  mov     [rsp+0A8h+arg_0], rax
0x18001180d  mov     [rsp+0A8h+var_78], eax
0x180011811  mov     [rsi], edi
0x180011813  jmp     short loc_180011856
0x180011815  mov     ebx, eax
0x180011817  mov     [rsp+0A8h+var_78], eax
0x18001181b  lea     rdx, WPP_GLOBAL_Control
0x180011822  mov     rcx, cs:WPP_GLOBAL_Control
0x180011829  cmp     rcx, rdx
0x18001182c  jz      short loc_180011856
0x18001182e  test    dword ptr [rcx+1Ch], 1000h
0x180011835  jz      short loc_180011856
0x180011837  cmp     byte ptr [rcx+19h], 2
0x18001183b  jb      short loc_180011856
0x18001183d  mov     edx, 1Dh
0x180011842  mov     r9d, eax
0x180011845  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18001184c  mov     rcx, [rcx+10h]
0x180011850  call    WPP_SF_d
0x180011855  nop
0x180011856  mov     rcx, [rsp+0A8h+lpMem]; lpMem
0x18001185b  test    rcx, rcx
0x18001185e  jz      short loc_180011865
0x180011860  call    pMemFree
0x180011865  test    ebx, ebx
0x180011867  jz      short loc_180011879
0x180011869  mov     ecx, ebx; dwErrCode
0x18001186b  call    cs:__imp_SetLastError
0x180011872  nop     dword ptr [rax+rax+00h]
0x180011877  jmp     short loc_1800118BD
0x180011879  mov     eax, 1
0x18001187e  jmp     short loc_1800118BF
0x180011880  mov     ecx, 6; dwErrCode
0x180011885  call    cs:__imp_SetLastError
0x18001188c  nop     dword ptr [rax+rax+00h]
0x180011891  mov     rcx, cs:WPP_GLOBAL_Control
0x180011898  cmp     rcx, r14
0x18001189b  jz      short loc_1800118BD
0x18001189d  test    [rcx+1Ch], edi
0x1800118a0  jz      short loc_1800118BD
0x1800118a2  cmp     byte ptr [rcx+19h], 2
0x1800118a6  jb      short loc_1800118BD
0x1800118a8  mov     edx, 19h
0x1800118ad  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x1800118b4  mov     rcx, [rcx+10h]
0x1800118b8  call    WPP_SF_
0x1800118bd  xor     eax, eax
0x1800118bf  add     rsp, 88h
0x1800118c6  pop     r14
0x1800118c8  pop     rdi
0x1800118c9  pop     rsi
0x1800118ca  pop     rbx
0x1800118cb  retn
```
