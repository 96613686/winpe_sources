# DeleteOutboundRuleKey

- ea: `0x1400813e4`
- end: `0x14008159a`
- name: `DeleteOutboundRuleKey`
- size: `438`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400658f0`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140074f18`
- `0x1400813e4`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140081566`
- `ADVAPI32!RegCloseKey` at `0x140081566`
- `ADVAPI32!RegDeleteKeyExW` at `0x140081521`
- `ADVAPI32!RegDeleteKeyExW` at `0x140081521`
- `KERNEL32!GetLastError` at `0x1400814d1`
- `KERNEL32!GetLastError` at `0x1400814d1`

## pseudocode

```c
__int64 __fastcall DeleteOutboundRuleKey(unsigned int a1, int a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  HKEY v6; // rax
  HKEY v7; // rdi
  DWORD LastError; // eax
  unsigned int v9; // eax
  WCHAR SubKey[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v4 = StringCchPrintfW(SubKey, 0x104u, L"%ld:%ld", a1, a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Outbound Routing\\Rules", 0, 0x10000u);
    v7 = v6;
    if ( v6 )
    {
      v9 = RegDeleteKeyExW(v6, SubKey, 0, 0);
      v5 = v9;
      if ( v9
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v9);
      }
      RegCloseKey(v7);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        102,
        &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
        (unsigned int)v4);
    }
    if ( (v5 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v5;
  }
  return v5;
}

```

## disassembly

```asm
0x1400813e4  mov     [rsp+arg_10], rbx
0x1400813e9  mov     [rsp+arg_18], rbp
0x1400813ee  push    rdi
0x1400813ef  sub     rsp, 250h
0x1400813f6  mov     rax, cs:__security_cookie
0x1400813fd  xor     rax, rsp
0x140081400  mov     [rsp+258h+var_18], rax
0x140081408  mov     edi, edx
0x14008140a  mov     ebx, ecx
0x14008140c  mov     rcx, cs:WPP_GLOBAL_Control
0x140081413  lea     rbp, WPP_GLOBAL_Control
0x14008141a  cmp     rcx, rbp
0x14008141d  jz      short loc_140081440
0x14008141f  test    byte ptr [rcx+1Ch], 2
0x140081423  jz      short loc_140081440
0x140081425  cmp     byte ptr [rcx+19h], 5
0x140081429  jb      short loc_140081440
0x14008142b  mov     rcx, [rcx+10h]
0x14008142f  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140081436  mov     edx, 65h ; 'e'
0x14008143b  call    WPP_SF_
0x140081440  mov     r9d, ebx
0x140081443  mov     [rsp+258h+var_238], edi
0x140081447  lea     r8, aLdLd; "%ld:%ld"
0x14008144e  mov     edx, 104h; unsigned __int64
0x140081453  lea     rcx, [rsp+258h+SubKey]; unsigned __int16 *
0x140081458  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14008145d  mov     ebx, eax
0x14008145f  test    eax, eax
0x140081461  jns     short loc_1400814AD
0x140081463  mov     rcx, cs:WPP_GLOBAL_Control
0x14008146a  cmp     rcx, rbp
0x14008146d  jz      short loc_140081493
0x14008146f  test    byte ptr [rcx+1Ch], 2
0x140081473  jz      short loc_140081493
0x140081475  cmp     byte ptr [rcx+19h], 2
0x140081479  jb      short loc_140081493
0x14008147b  mov     rcx, [rcx+10h]
0x14008147f  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140081486  mov     edx, 66h ; 'f'
0x14008148b  mov     r9d, eax
0x14008148e  call    WPP_SF_d
0x140081493  mov     eax, ebx
0x140081495  and     eax, 1FFF0000h
0x14008149a  cmp     eax, 70000h
0x14008149f  jnz     loc_140081572
0x1400814a5  movzx   ebx, bx
0x1400814a8  jmp     loc_140081572
0x1400814ad  mov     r9d, 10000h
0x1400814b3  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\Fax\\Outbound Rout"...
0x1400814ba  xor     r8d, r8d
0x1400814bd  mov     rcx, 0FFFFFFFF80000002h
0x1400814c4  call    OpenRegistryKey
0x1400814c9  mov     rdi, rax
0x1400814cc  test    rax, rax
0x1400814cf  jnz     short loc_140081513
0x1400814d1  call    cs:__imp_GetLastError
0x1400814d8  nop     dword ptr [rax+rax+00h]
0x1400814dd  mov     ebx, eax
0x1400814df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400814e6  cmp     rcx, rbp
0x1400814e9  jz      loc_140081572
0x1400814ef  test    byte ptr [rcx+1Ch], 2
0x1400814f3  jz      short loc_140081572
0x1400814f5  cmp     byte ptr [rcx+19h], 2
0x1400814f9  jb      short loc_140081572
0x1400814fb  mov     rcx, [rcx+10h]
0x1400814ff  lea     edx, [rdi+67h]
0x140081502  mov     r9d, eax
0x140081505  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14008150c  call    WPP_SF_d
0x140081511  jmp     short loc_140081572
0x140081513  xor     r9d, r9d; Reserved
0x140081516  lea     rdx, [rsp+258h+SubKey]; lpSubKey
0x14008151b  xor     r8d, r8d; samDesired
0x14008151e  mov     rcx, rdi; hKey
0x140081521  call    cs:__imp_RegDeleteKeyExW
0x140081528  nop     dword ptr [rax+rax+00h]
0x14008152d  mov     ebx, eax
0x14008152f  test    eax, eax
0x140081531  jz      short loc_140081563
0x140081533  mov     rcx, cs:WPP_GLOBAL_Control
0x14008153a  cmp     rcx, rbp
0x14008153d  jz      short loc_140081563
0x14008153f  test    byte ptr [rcx+1Ch], 2
0x140081543  jz      short loc_140081563
0x140081545  cmp     byte ptr [rcx+19h], 2
0x140081549  jb      short loc_140081563
0x14008154b  mov     rcx, [rcx+10h]
0x14008154f  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140081556  mov     edx, 68h ; 'h'
0x14008155b  mov     r9d, eax
0x14008155e  call    WPP_SF_d
0x140081563  mov     rcx, rdi; hKey
0x140081566  call    cs:__imp_RegCloseKey
0x14008156d  nop     dword ptr [rax+rax+00h]
0x140081572  mov     eax, ebx
0x140081574  mov     rcx, [rsp+258h+var_18]
0x14008157c  xor     rcx, rsp; StackCookie
0x14008157f  call    __security_check_cookie
0x140081584  lea     r11, [rsp+258h+var_8]
0x14008158c  mov     rbx, [r11+20h]
0x140081590  mov     rbp, [r11+28h]
0x140081594  mov     rsp, r11
0x140081597  pop     rdi
0x140081598  retn
```
