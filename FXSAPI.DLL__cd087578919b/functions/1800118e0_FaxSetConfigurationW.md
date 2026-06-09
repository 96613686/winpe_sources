# FaxSetConfigurationW

- ea: `0x1800118e0`
- end: `0x180011b4e`
- name: `FaxSetConfigurationW`
- size: `622`
- prototype: `BOOL __stdcall(HANDLE FaxHandle, const FAX_CONFIGURATIONW *FaxConfig)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x1800118e0`
- `0x180014368`
- `0x180033d10`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180011a26`
- `RPCRT4!NdrClientCall3` at `0x180011a26`
- `KERNEL32!SetLastError` at `0x18001194c`
- `KERNEL32!SetLastError` at `0x18001198d`
- `KERNEL32!SetLastError` at `0x180011a90`
- `KERNEL32!SetLastError` at `0x180011ab0`
- `KERNEL32!SetLastError` at `0x180011b09`
- `KERNEL32!SetLastError` at `0x18001194c`
- `KERNEL32!SetLastError` at `0x18001198d`
- `KERNEL32!SetLastError` at `0x180011a90`
- `KERNEL32!SetLastError` at `0x180011ab0`
- `KERNEL32!SetLastError` at `0x180011b09`

## pseudocode

```c
BOOL __stdcall FaxSetConfigurationW(HANDLE FaxHandle, const FAX_CONFIGURATIONW *FaxConfig)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  DWORD Pointer; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
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
    v5 = 19;
LABEL_33:
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
    v5 = 20;
    goto LABEL_33;
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
    v5 = 21;
    goto LABEL_33;
  }
  if ( FaxConfig->StartCheapTime.Hour >= 0x18u
    || FaxConfig->StartCheapTime.Minute >= 0x3Cu
    || FaxConfig->StopCheapTime.Hour >= 0x18u
    || FaxConfig->StopCheapTime.Minute >= 0x3Cu )
  {
    SetLastError(0x57u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_dddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        FaxConfig->StopCheapTime.Hour,
        FaxConfig->StartCheapTime.Hour,
        FaxConfig->StartCheapTime.Minute,
        FaxConfig->StopCheapTime.Hour,
        FaxConfig->StopCheapTime.Minute);
    }
  }
  else
  {
    FaxConfig->SizeOfStruct = GetWin32StructSize(&fax_configuration_fields);
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x14u,
                              0,
                              **((_QWORD **)FaxHandle + 4),
                              FaxConfig).Pointer;
    FaxConfig->SizeOfStruct = 64;
    if ( !Pointer )
      return 1;
    SetLastError(Pointer);
  }
  return 0;
}

```

## disassembly

```asm
0x1800118e0  push    rbx
0x1800118e2  push    rsi
0x1800118e3  push    rdi
0x1800118e4  push    r14
0x1800118e6  sub     rsp, 58h
0x1800118ea  mov     rdi, rdx
0x1800118ed  mov     rsi, rcx
0x1800118f0  lea     r14, WPP_GLOBAL_Control
0x1800118f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118fe  mov     ebx, 1000h
0x180011903  cmp     rcx, r14
0x180011906  jz      short loc_180011928
0x180011908  test    [rcx+1Ch], ebx
0x18001190b  jz      short loc_180011928
0x18001190d  cmp     byte ptr [rcx+19h], 5
0x180011911  jb      short loc_180011928
0x180011913  mov     edx, 12h
0x180011918  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18001191f  mov     rcx, [rcx+10h]
0x180011923  call    WPP_SF_
0x180011928  test    rsi, rsi
0x18001192b  jz      loc_180011B04
0x180011931  cmp     dword ptr [rsi], 0
0x180011934  jz      loc_180011B04
0x18001193a  cmp     dword ptr [rsi+10h], 0
0x18001193e  jnz     loc_180011B04
0x180011944  test    rdi, rdi
0x180011947  jnz     short loc_180011983
0x180011949  lea     ecx, [rdi+57h]; dwErrCode
0x18001194c  call    cs:__imp_SetLastError
0x180011953  nop     dword ptr [rax+rax+00h]
0x180011958  mov     rcx, cs:WPP_GLOBAL_Control
0x18001195f  cmp     rcx, r14
0x180011962  jz      loc_180011B41
0x180011968  test    [rcx+1Ch], ebx
0x18001196b  jz      loc_180011B41
0x180011971  cmp     byte ptr [rcx+19h], 2
0x180011975  jb      loc_180011B41
0x18001197b  lea     edx, [rdi+14h]
0x18001197e  jmp     loc_180011B31
0x180011983  cmp     dword ptr [rdi], 40h ; '@'
0x180011986  jz      short loc_1800119C6
0x180011988  mov     ecx, 57h ; 'W'; dwErrCode
0x18001198d  call    cs:__imp_SetLastError
0x180011994  nop     dword ptr [rax+rax+00h]
0x180011999  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119a0  cmp     rcx, r14
0x1800119a3  jz      loc_180011B41
0x1800119a9  test    [rcx+1Ch], ebx
0x1800119ac  jz      loc_180011B41
0x1800119b2  cmp     byte ptr [rcx+19h], 2
0x1800119b6  jb      loc_180011B41
0x1800119bc  mov     edx, 15h
0x1800119c1  jmp     loc_180011B31
0x1800119c6  cmp     word ptr [rdi+20h], 18h
0x1800119cb  jnb     loc_180011AAB
0x1800119d1  cmp     word ptr [rdi+22h], 3Ch ; '<'
0x1800119d6  jnb     loc_180011AAB
0x1800119dc  cmp     word ptr [rdi+24h], 18h
0x1800119e1  jnb     loc_180011AAB
0x1800119e7  cmp     word ptr [rdi+26h], 3Ch ; '<'
0x1800119ec  jnb     loc_180011AAB
0x1800119f2  lea     rcx, ?fax_configuration_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_configuration_fields
0x1800119f9  call    GetWin32StructSize
0x1800119fe  mov     [rdi], eax
0x180011a00  mov     rax, [rsi+20h]
0x180011a04  mov     [rsp+78h+arg_0], 0
0x180011a10  mov     [rsp+78h+var_58], rdi
0x180011a15  mov     r9, [rax]
0x180011a18  xor     r8d, r8d; pReturnValue
0x180011a1b  lea     edx, [r8+14h]; nProcNum
0x180011a1f  lea     rcx, pProxyInfo; pProxyInfo
0x180011a26  call    cs:__imp_NdrClientCall3
0x180011a2d  nop     dword ptr [rax+rax+00h]
0x180011a32  mov     rbx, rax
0x180011a35  mov     [rsp+78h+arg_0], rax
0x180011a3d  mov     [rsp+78h+var_38], eax
0x180011a41  mov     dword ptr [rdi], 40h ; '@'
0x180011a47  jmp     short loc_180011A8A
0x180011a49  mov     ebx, eax
0x180011a4b  mov     [rsp+78h+var_38], eax
0x180011a4f  lea     rdx, WPP_GLOBAL_Control
0x180011a56  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a5d  cmp     rcx, rdx
0x180011a60  jz      short loc_180011A8A
0x180011a62  test    dword ptr [rcx+1Ch], 1000h
0x180011a69  jz      short loc_180011A8A
0x180011a6b  cmp     byte ptr [rcx+19h], 2
0x180011a6f  jb      short loc_180011A8A
0x180011a71  mov     edx, 17h
0x180011a76  mov     r9d, eax
0x180011a79  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180011a80  mov     rcx, [rcx+10h]
0x180011a84  call    WPP_SF_d
0x180011a89  nop
0x180011a8a  test    ebx, ebx
0x180011a8c  jz      short loc_180011AA1
0x180011a8e  mov     ecx, ebx; dwErrCode
0x180011a90  call    cs:__imp_SetLastError
0x180011a97  nop     dword ptr [rax+rax+00h]
0x180011a9c  jmp     loc_180011B41
0x180011aa1  mov     eax, 1
0x180011aa6  jmp     loc_180011B43
0x180011aab  mov     ecx, 57h ; 'W'; dwErrCode
0x180011ab0  call    cs:__imp_SetLastError
0x180011ab7  nop     dword ptr [rax+rax+00h]
0x180011abc  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ac3  cmp     rcx, r14
0x180011ac6  jz      short loc_180011B41
0x180011ac8  test    [rcx+1Ch], ebx
0x180011acb  jz      short loc_180011B41
0x180011acd  cmp     byte ptr [rcx+19h], 2
0x180011ad1  jb      short loc_180011B41
0x180011ad3  movzx   eax, word ptr [rdi+26h]
0x180011ad7  movzx   r8d, word ptr [rdi+24h]
0x180011adc  movzx   r10d, word ptr [rdi+22h]
0x180011ae1  movzx   r9d, word ptr [rdi+20h]
0x180011ae6  mov     edx, 16h
0x180011aeb  mov     [rsp+78h+var_48], eax
0x180011aef  mov     [rsp+78h+var_50], r8d
0x180011af4  mov     dword ptr [rsp+78h+var_58], r10d
0x180011af9  mov     rcx, [rcx+10h]
0x180011afd  call    WPP_SF_dddd
0x180011b02  jmp     short loc_180011B41
0x180011b04  mov     ecx, 6; dwErrCode
0x180011b09  call    cs:__imp_SetLastError
0x180011b10  nop     dword ptr [rax+rax+00h]
0x180011b15  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b1c  cmp     rcx, r14
0x180011b1f  jz      short loc_180011B41
0x180011b21  test    [rcx+1Ch], ebx
0x180011b24  jz      short loc_180011B41
0x180011b26  cmp     byte ptr [rcx+19h], 2
0x180011b2a  jb      short loc_180011B41
0x180011b2c  mov     edx, 13h
0x180011b31  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180011b38  mov     rcx, [rcx+10h]
0x180011b3c  call    WPP_SF_
0x180011b41  xor     eax, eax
0x180011b43  add     rsp, 58h
0x180011b47  pop     r14
0x180011b49  pop     rdi
0x180011b4a  pop     rsi
0x180011b4b  pop     rbx
0x180011b4c  retn
```
