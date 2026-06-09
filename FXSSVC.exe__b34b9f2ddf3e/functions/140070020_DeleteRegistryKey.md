# DeleteRegistryKey

- ea: `0x140070020`
- end: `0x140070218`
- name: `DeleteRegistryKey`
- size: `504`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000cac8`
- `0x140021fb0`
- `0x14006fb00`
- `0x14006fc98`
- `0x140070020`
- `0x140070220`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140070020`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007016b`
- `ADVAPI32!RegCloseKey` at `0x1400701e1`
- `ADVAPI32!RegCloseKey` at `0x14007016b`
- `ADVAPI32!RegCloseKey` at `0x1400701e1`
- `ADVAPI32!RegOpenKeyExW` at `0x1400700b2`
- `ADVAPI32!RegOpenKeyExW` at `0x1400700b2`
- `ADVAPI32!RegEnumKeyExW` at `0x140070153`
- `ADVAPI32!RegEnumKeyExW` at `0x140070153`
- `ADVAPI32!RegDeleteKeyW` at `0x140070177`
- `ADVAPI32!RegDeleteKeyW` at `0x140070177`
- `KERNEL32!SetLastError` at `0x1400701e9`
- `KERNEL32!SetLastError` at `0x1400701e9`

## pseudocode

```c
__int64 __fastcall DeleteRegistryKey(HKEY a1, const WCHAR *a2)
{
  unsigned int v4; // ebx
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  cchName = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids);
  }
  v4 = RegOpenKeyExW(a1, a2, 0, 0x3001Fu, &hKey);
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 11;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids, v4);
    }
  }
  else
  {
    while ( 1 )
    {
      cchName = 260;
      v7 = RegEnumKeyExW(hKey, 0, SubKey, &cchName, 0, 0, 0, 0);
      v4 = v7;
      if ( v7 )
        break;
      if ( !(unsigned int)DeleteRegistryKey(hKey, SubKey) )
        return 0;
    }
    if ( v7 == 259 )
    {
      RegCloseKey(hKey);
      v4 = RegDeleteKeyW(a1, a2);
      if ( !v4 )
        return 1;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 13;
        goto LABEL_10;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids, v7);
      }
      RegCloseKey(hKey);
    }
  }
  SetLastError(v4);
  return 0;
}

```

## disassembly

```asm
0x140070020  mov     [rsp-8+arg_10], rbx
0x140070025  mov     [rsp-8+arg_18], rsi
0x14007002a  push    rbp
0x14007002b  push    rdi
0x14007002c  push    r12
0x14007002e  lea     rbp, [rsp-170h]
0x140070036  sub     rsp, 270h
0x14007003d  mov     rax, cs:__security_cookie
0x140070044  xor     rax, rsp
0x140070047  mov     [rbp+180h+var_20], rax
0x14007004e  mov     rsi, rdx
0x140070051  mov     [rsp+280h+hKey], 0
0x14007005a  mov     rdi, rcx
0x14007005d  mov     [rsp+280h+cchName], 0
0x140070065  mov     rcx, cs:WPP_GLOBAL_Control
0x14007006c  lea     r12, WPP_GLOBAL_Control
0x140070073  cmp     rcx, r12
0x140070076  jz      short loc_140070099
0x140070078  test    byte ptr [rcx+1Ch], 2
0x14007007c  jz      short loc_140070099
0x14007007e  cmp     byte ptr [rcx+19h], 5
0x140070082  jb      short loc_140070099
0x140070084  mov     rcx, [rcx+10h]
0x140070088  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x14007008f  mov     edx, 0Ah
0x140070094  call    WPP_SF_
0x140070099  lea     rax, [rsp+280h+hKey]
0x14007009e  mov     r9d, 3001Fh; samDesired
0x1400700a4  xor     r8d, r8d; ulOptions
0x1400700a7  mov     [rsp+280h+phkResult], rax; phkResult
0x1400700ac  mov     rdx, rsi; lpSubKey
0x1400700af  mov     rcx, rdi; hKey
0x1400700b2  call    cs:__imp_RegOpenKeyExW
0x1400700b8  mov     ebx, eax
0x1400700ba  test    eax, eax
0x1400700bc  jz      short loc_140070116
0x1400700be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400700c5  cmp     rcx, r12
0x1400700c8  jz      loc_1400701E7
0x1400700ce  test    byte ptr [rcx+1Ch], 2
0x1400700d2  jz      loc_1400701E7
0x1400700d8  cmp     byte ptr [rcx+19h], 2
0x1400700dc  jb      loc_1400701E7
0x1400700e2  mov     edx, 0Bh
0x1400700e7  mov     rcx, [rcx+10h]
0x1400700eb  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x1400700f2  mov     r9d, ebx
0x1400700f5  call    WPP_SF_d
0x1400700fa  jmp     loc_1400701E7
0x1400700ff  mov     rcx, [rsp+280h+hKey]
0x140070104  lea     rdx, [rsp+280h+SubKey]
0x140070109  call    DeleteRegistryKey
0x14007010e  test    eax, eax
0x140070110  jz      loc_1400701EF
0x140070116  mov     rcx, [rsp+280h+hKey]; hKey
0x14007011b  lea     r9, [rsp+280h+cchName]; lpcchName
0x140070120  mov     [rsp+280h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140070129  lea     r8, [rsp+280h+SubKey]; lpName
0x14007012e  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x140070137  xor     edx, edx; dwIndex
0x140070139  mov     [rsp+280h+lpClass], 0; lpClass
0x140070142  mov     [rsp+280h+phkResult], 0; lpReserved
0x14007014b  mov     [rsp+280h+cchName], 104h
0x140070153  call    cs:__imp_RegEnumKeyExW
0x140070159  mov     ebx, eax
0x14007015b  test    eax, eax
0x14007015d  jz      short loc_1400700FF
0x14007015f  cmp     eax, 103h
0x140070164  jnz     short loc_1400701AC
0x140070166  mov     rcx, [rsp+280h+hKey]; hKey
0x14007016b  call    cs:__imp_RegCloseKey
0x140070171  mov     rdx, rsi; lpSubKey
0x140070174  mov     rcx, rdi; hKey
0x140070177  call    cs:__imp_RegDeleteKeyW
0x14007017d  mov     ebx, eax
0x14007017f  test    eax, eax
0x140070181  jz      short loc_1400701A5
0x140070183  mov     rcx, cs:WPP_GLOBAL_Control
0x14007018a  cmp     rcx, r12
0x14007018d  jz      short loc_1400701E7
0x14007018f  test    byte ptr [rcx+1Ch], 2
0x140070193  jz      short loc_1400701E7
0x140070195  cmp     byte ptr [rcx+19h], 2
0x140070199  jb      short loc_1400701E7
0x14007019b  mov     edx, 0Dh
0x1400701a0  jmp     loc_1400700E7
0x1400701a5  mov     eax, 1
0x1400701aa  jmp     short loc_1400701F1
0x1400701ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400701b3  cmp     rcx, r12
0x1400701b6  jz      short loc_1400701DC
0x1400701b8  test    byte ptr [rcx+1Ch], 2
0x1400701bc  jz      short loc_1400701DC
0x1400701be  cmp     byte ptr [rcx+19h], 2
0x1400701c2  jb      short loc_1400701DC
0x1400701c4  mov     rcx, [rcx+10h]
0x1400701c8  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x1400701cf  mov     edx, 0Ch
0x1400701d4  mov     r9d, ebx
0x1400701d7  call    WPP_SF_d
0x1400701dc  mov     rcx, [rsp+280h+hKey]; hKey
0x1400701e1  call    cs:__imp_RegCloseKey
0x1400701e7  mov     ecx, ebx; dwErrCode
0x1400701e9  call    cs:__imp_SetLastError
0x1400701ef  xor     eax, eax
0x1400701f1  mov     rcx, [rbp+180h+var_20]
0x1400701f8  xor     rcx, rsp; StackCookie
0x1400701fb  call    __security_check_cookie
0x140070200  lea     r11, [rsp+280h+var_10]
0x140070208  mov     rbx, [r11+30h]
0x14007020c  mov     rsi, [r11+38h]
0x140070210  mov     rsp, r11
0x140070213  pop     r12
0x140070215  pop     rdi
0x140070216  pop     rbp
0x140070217  retn
```
