# BdeCfgDetectWinREVolumeName(unsigned __int64,ushort *)

- ea: `0x180007210`
- end: `0x180007439`
- name: `?BdeCfgDetectWinREVolumeName@@YAJ_KPEAG@Z`
- size: `553`
- prototype: `signed int __fastcall(unsigned __int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x180002460`
- `0x180002814`
- `0x180003240`
- `0x180004b00`

## callees

- `0x180007210`
- `0x180008e4c`
- `0x18001358e`
- `0x1800135c0`
- `0x180013650`

## import_xrefs

- `msvcrt!wcschr` at `0x18000733c`
- `msvcrt!wcschr` at `0x18000736b`
- `msvcrt!wcschr` at `0x18000733c`
- `msvcrt!wcschr` at `0x18000736b`
- `msvcrt!_wcsnicmp` at `0x1800072e4`
- `msvcrt!_wcsnicmp` at `0x18000730c`
- `msvcrt!_wcsnicmp` at `0x180007328`
- `msvcrt!_wcsnicmp` at `0x18000735a`
- `msvcrt!_wcsnicmp` at `0x1800072e4`
- `msvcrt!_wcsnicmp` at `0x18000730c`
- `msvcrt!_wcsnicmp` at `0x180007328`
- `msvcrt!_wcsnicmp` at `0x18000735a`
- `KERNEL32!GetLastError` at `0x1800072a0`
- `KERNEL32!GetLastError` at `0x1800072a0`
- `ReAgent!WinReGetConfig` at `0x180007292`
- `ReAgent!WinReGetConfig` at `0x180007292`

## pseudocode

```c
signed int __fastcall BdeCfgDetectWinREVolumeName(unsigned __int64 a1, unsigned __int16 *a2)
{
  signed int result; // eax
  wchar_t *v5; // rax
  wchar_t *v6; // rbx
  wchar_t *v7; // rcx
  unsigned __int64 v8; // rcx
  unsigned int v9; // edx
  wchar_t *v10; // rdx
  __int64 v11; // r9
  WCHAR *v12; // r10
  WCHAR *v13; // rcx
  __int64 v14; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v15[156]; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t String1[14]; // [rsp+298h] [rbp+198h] BYREF
  wchar_t v17[7]; // [rsp+2B4h] [rbp+1B4h] BYREF
  wchar_t v18[9]; // [rsp+2C2h] [rbp+1C2h] BYREF
  wchar_t Str[1526]; // [rsp+2D4h] [rbp+1D4h] BYREF
  WCHAR SourceString[264]; // [rsp+EC0h] [rbp+DC0h] BYREF

  memset_0(SourceString, 0, 0x208u);
  memset_0(v15, 0, 0xE98u);
  if ( !a2 )
    return -2147467261;
  v14 = 3744;
  if ( (unsigned int)WinReGetConfig(0, &v14) )
  {
    if ( !v15[0] )
    {
      *a2 = 0;
      return 1;
    }
    if ( _wcsnicmp(String1, L"\\\\?\\GLOBALROOT", 0xEu) )
      return -1063256037;
    if ( _wcsnicmp(v17, L"\\Device", 7u) )
      return -1063256037;
    if ( _wcsnicmp(v18, L"\\Harddisk", 9u) )
      return -1063256037;
    v5 = wcschr(Str, 0x5Cu);
    v6 = v5;
    if ( !v5 )
      return -1063256037;
    if ( _wcsnicmp(v5, L"\\Partition", 0xAu) )
      return -1063256037;
    v7 = wcschr(v6 + 10, 0x5Cu);
    if ( !v7 )
      return -1063256037;
    v8 = v7 - v17;
    if ( v8 > 0x7FFFFFFE )
      return -2147024809;
    v10 = v17;
    v11 = 260;
    v12 = SourceString;
    do
    {
      if ( !v8 )
        break;
      if ( !*v10 )
        break;
      *v12++ = *v10++;
      --v8;
      --v11;
    }
    while ( v11 );
    v13 = v12 - 1;
    v9 = v11 == 0 ? 0x8007007A : 0;
    if ( v11 )
      v13 = v12;
    *v13 = 0;
    if ( v11 )
      return BdeCfgpGetVolumeNameFromSymbolicLink(SourceString, a1, a2);
    return v9;
  }
  else
  {
    *a2 = 0;
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180007210  mov     [rsp-8+arg_10], rbx
0x180007215  mov     [rsp-8+arg_18], rsi
0x18000721a  push    rbp
0x18000721b  push    rdi
0x18000721c  push    r14
0x18000721e  lea     rbp, [rsp-0FE0h]
0x180007226  mov     eax, 10E0h
0x18000722b  call    _alloca_probe
0x180007230  sub     rsp, rax
0x180007233  mov     rax, cs:__security_cookie
0x18000723a  xor     rax, rsp
0x18000723d  mov     [rbp+0FF0h+var_20], rax
0x180007244  mov     rdi, rdx
0x180007247  mov     rsi, rcx
0x18000724a  xor     edx, edx; Val
0x18000724c  lea     rcx, [rbp+0FF0h+SourceString]; void *
0x180007253  mov     r8d, 208h; Size
0x180007259  call    memset_0
0x18000725e  xor     edx, edx; Val
0x180007260  lea     rcx, [rsp+10F0h+var_10C8]; void *
0x180007265  mov     r8d, 0E98h; Size
0x18000726b  call    memset_0
0x180007270  xor     r14d, r14d
0x180007273  test    rdi, rdi
0x180007276  jnz     short loc_180007282
0x180007278  mov     eax, 80004003h
0x18000727d  jmp     loc_18000739A
0x180007282  lea     rdx, [rsp+10F0h+var_10D0]
0x180007287  mov     [rsp+10F0h+var_10D0], 0EA0h
0x180007290  xor     ecx, ecx
0x180007292  call    cs:__imp_WinReGetConfig
0x180007298  test    eax, eax
0x18000729a  jnz     short loc_1800072BB
0x18000729c  mov     [rdi], r14w
0x1800072a0  call    cs:__imp_GetLastError
0x1800072a6  test    eax, eax
0x1800072a8  jle     loc_18000739A
0x1800072ae  movzx   eax, ax
0x1800072b1  or      eax, 80070000h
0x1800072b6  jmp     loc_18000739A
0x1800072bb  cmp     [rsp+10F0h+var_10C8], r14d
0x1800072c0  jnz     short loc_1800072D0
0x1800072c2  mov     [rdi], r14w
0x1800072c6  mov     eax, 1
0x1800072cb  jmp     loc_18000739A
0x1800072d0  mov     r8d, 0Eh; MaxCount
0x1800072d6  lea     rdx, aGlobalroot; "\\\\?\\GLOBALROOT"
0x1800072dd  lea     rcx, [rbp+0FF0h+String1]; String1
0x1800072e4  call    cs:__imp__wcsnicmp
0x1800072ea  test    eax, eax
0x1800072ec  jz      short loc_1800072F8
0x1800072ee  mov     eax, 0C0A0001Bh
0x1800072f3  jmp     loc_18000739A
0x1800072f8  mov     r8d, 7; MaxCount
0x1800072fe  lea     rdx, aDevice_0; "\\Device"
0x180007305  lea     rcx, [rbp+0FF0h+var_E3C]; String1
0x18000730c  call    cs:__imp__wcsnicmp
0x180007312  test    eax, eax
0x180007314  jnz     short loc_1800072EE
0x180007316  lea     r8d, [rax+9]; MaxCount
0x18000731a  lea     rdx, aHarddisk; "\\Harddisk"
0x180007321  lea     rcx, [rbp+0FF0h+var_E2E]; String1
0x180007328  call    cs:__imp__wcsnicmp
0x18000732e  test    eax, eax
0x180007330  jnz     short loc_1800072EE
0x180007332  lea     edx, [rax+5Ch]; Ch
0x180007335  lea     rcx, [rbp+0FF0h+Str]; Str
0x18000733c  call    cs:__imp_wcschr
0x180007342  mov     rbx, rax
0x180007345  test    rax, rax
0x180007348  jz      short loc_1800072EE
0x18000734a  mov     r8d, 0Ah; MaxCount
0x180007350  lea     rdx, aPartition; "\\Partition"
0x180007357  mov     rcx, rax; String1
0x18000735a  call    cs:__imp__wcsnicmp
0x180007360  test    eax, eax
0x180007362  jnz     short loc_1800072EE
0x180007364  lea     edx, [rax+5Ch]; Ch
0x180007367  lea     rcx, [rbx+14h]; Str
0x18000736b  call    cs:__imp_wcschr
0x180007371  mov     rcx, rax
0x180007374  test    rax, rax
0x180007377  jz      loc_1800072EE
0x18000737d  lea     rax, [rbp+0FF0h+var_E3C]
0x180007384  sub     rcx, rax
0x180007387  sar     rcx, 1
0x18000738a  cmp     rcx, 7FFFFFFEh
0x180007391  jbe     short loc_1800073C1
0x180007393  mov     edx, 80070057h
0x180007398  mov     eax, edx
0x18000739a  mov     rcx, [rbp+0FF0h+var_20]
0x1800073a1  xor     rcx, rsp; StackCookie
0x1800073a4  call    __security_check_cookie
0x1800073a9  lea     r11, [rsp+10F0h+var_10]
0x1800073b1  mov     rbx, [r11+30h]
0x1800073b5  mov     rsi, [r11+38h]
0x1800073b9  mov     rsp, r11
0x1800073bc  pop     r14
0x1800073be  pop     rdi
0x1800073bf  pop     rbp
0x1800073c0  retn
0x1800073c1  lea     rdx, [rbp+0FF0h+var_E3C]
0x1800073c8  mov     r9d, 104h
0x1800073ce  lea     r10, [rbp+0FF0h+SourceString]
0x1800073d5  mov     eax, 1
0x1800073da  test    rcx, rcx
0x1800073dd  jz      short loc_1800073FD
0x1800073df  movzx   r8d, word ptr [rdx]
0x1800073e3  test    r8w, r8w
0x1800073e7  jz      short loc_1800073FD
0x1800073e9  mov     [r10], r8w
0x1800073ed  add     rdx, 2
0x1800073f1  add     r10, 2
0x1800073f5  sub     rcx, rax
0x1800073f8  sub     r9, rax
0x1800073fb  jnz     short loc_1800073DA
0x1800073fd  mov     rax, r9
0x180007400  lea     rcx, [r10-2]
0x180007404  neg     rax
0x180007407  sbb     edx, edx
0x180007409  not     edx
0x18000740b  and     edx, 8007007Ah
0x180007411  test    r9, r9
0x180007414  cmovnz  rcx, r10
0x180007418  mov     [rcx], r14w
0x18000741c  jz      loc_180007398
0x180007422  mov     r8, rdi; unsigned __int16 *
0x180007425  lea     rcx, [rbp+0FF0h+SourceString]; SourceString
0x18000742c  mov     rdx, rsi; unsigned __int64
0x18000742f  call    ?BdeCfgpGetVolumeNameFromSymbolicLink@@YAJPEBG_KPEAG@Z; BdeCfgpGetVolumeNameFromSymbolicLink(ushort const *,unsigned __int64,ushort *)
0x180007434  jmp     loc_18000739A
```
