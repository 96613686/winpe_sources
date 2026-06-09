# StartList::GetUserValue(ushort *,uint,ATL::CRegKey &)

- ea: `0x14000e3e8`
- end: `0x14000e52f`
- name: `?GetUserValue@StartList@@AEAAJPEAGIAEAVCRegKey@ATL@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(StartList *this, unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ee8c`

## callees

- `0x140007708`
- `0x14000e3e8`
- `0x1400111c0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000e42e`
- `ADVAPI32!RegOpenKeyExW` at `0x14000e42e`
- `ADVAPI32!RegCloseKey` at `0x14000e446`
- `ADVAPI32!RegCloseKey` at `0x14000e446`

## string_xrefs

- `0x14000e46e`: `Configuration`
- `0x14000e40f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall StartList::GetUserValue(StartList *this, unsigned __int16 *a2, unsigned int a3, HKEY *a4)
{
  LSTATUS v6; // ebx
  __int64 v7; // r8
  unsigned int v8; // eax
  __int64 v9; // r8
  HKEY v11; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v12; // [rsp+50h] [rbp+18h] BYREF

  v12 = a3;
  *a2 = 0;
  v11 = 0;
  v6 = RegOpenKeyExW(HKEY_CURRENT_USER, StartList::_accessibilityKeyString, 0, 0x20019u, &v11);
  if ( v6 )
    goto LABEL_17;
  if ( *a4 )
    v6 = RegCloseKey(*a4);
  *a4 = v11;
  if ( v6 )
  {
LABEL_17:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, v7, (unsigned int)v6);
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
    return (unsigned int)v6;
  }
  else
  {
    v12 = 1024;
    v8 = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)a4, L"Configuration", a2, &v12);
    if ( v8 == 2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, v9, v8);
      return 2147942402LL;
    }
    else
    {
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, v9, v8);
        *a2 = 0;
      }
      return 0;
    }
  }
}

```

## disassembly

```asm
0x14000e3e8  mov     r11, rsp
0x14000e3eb  mov     [r11+10h], rbx
0x14000e3ef  mov     [r11+20h], rsi
0x14000e3f3  mov     [r11+18h], r8d
0x14000e3f7  mov     [r11+8], rcx
0x14000e3fb  push    rdi
0x14000e3fc  sub     rsp, 30h
0x14000e400  xor     eax, eax
0x14000e402  mov     rdi, r9
0x14000e405  mov     [rdx], ax
0x14000e408  mov     rsi, rdx
0x14000e40b  mov     [r11+8], rax
0x14000e40f  lea     rdx, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000e416  lea     rax, [r11+8]
0x14000e41a  mov     r9d, 20019h; samDesired
0x14000e420  xor     r8d, r8d; ulOptions
0x14000e423  mov     [r11-18h], rax
0x14000e427  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000e42e  call    cs:__imp_RegOpenKeyExW
0x14000e434  mov     ebx, eax
0x14000e436  test    eax, eax
0x14000e438  jnz     loc_14000E4E6
0x14000e43e  mov     rcx, [rdi]; hKey
0x14000e441  test    rcx, rcx
0x14000e444  jz      short loc_14000E44E
0x14000e446  call    cs:__imp_RegCloseKey
0x14000e44c  mov     ebx, eax
0x14000e44e  mov     rax, [rsp+38h+arg_0]
0x14000e453  mov     [rdi], rax
0x14000e456  test    ebx, ebx
0x14000e458  jnz     loc_14000E4E6
0x14000e45e  lea     r9, [rsp+38h+arg_10]; unsigned int *
0x14000e463  mov     [rsp+38h+arg_10], 400h
0x14000e46b  mov     r8, rsi; unsigned __int16 *
0x14000e46e  lea     rdx, aConfiguration; "Configuration"
0x14000e475  mov     rcx, rdi; this
0x14000e478  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14000e47d  mov     r9d, eax
0x14000e480  cmp     eax, 2
0x14000e483  jnz     short loc_14000E4B1
0x14000e485  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e48c  lea     rax, WPP_GLOBAL_Control
0x14000e493  cmp     rcx, rax
0x14000e496  jz      short loc_14000E4AA
0x14000e498  test    byte ptr [rcx+1Ch], 8
0x14000e49c  jz      short loc_14000E4AA
0x14000e49e  mov     rcx, [rcx+10h]
0x14000e4a2  lea     edx, [rbx+25h]
0x14000e4a5  call    WPP_SF_d
0x14000e4aa  mov     eax, 80070002h
0x14000e4af  jmp     short loc_14000E51F
0x14000e4b1  test    r9d, r9d
0x14000e4b4  jz      short loc_14000E4E2
0x14000e4b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e4bd  lea     rax, WPP_GLOBAL_Control
0x14000e4c4  cmp     rcx, rax
0x14000e4c7  jz      short loc_14000E4DD
0x14000e4c9  test    byte ptr [rcx+1Ch], 8
0x14000e4cd  jz      short loc_14000E4DD
0x14000e4cf  mov     rcx, [rcx+10h]
0x14000e4d3  mov     edx, 26h ; '&'
0x14000e4d8  call    WPP_SF_d
0x14000e4dd  xor     eax, eax
0x14000e4df  mov     [rsi], ax
0x14000e4e2  xor     eax, eax
0x14000e4e4  jmp     short loc_14000E51F
0x14000e4e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e4ed  lea     rax, WPP_GLOBAL_Control
0x14000e4f4  cmp     rcx, rax
0x14000e4f7  jz      short loc_14000E510
0x14000e4f9  test    byte ptr [rcx+1Ch], 8
0x14000e4fd  jz      short loc_14000E510
0x14000e4ff  mov     rcx, [rcx+10h]
0x14000e503  mov     edx, 24h ; '$'
0x14000e508  mov     r9d, ebx
0x14000e50b  call    WPP_SF_d
0x14000e510  test    ebx, ebx
0x14000e512  jle     short loc_14000E51D
0x14000e514  movzx   ebx, bx
0x14000e517  or      ebx, 80070000h
0x14000e51d  mov     eax, ebx
0x14000e51f  mov     rbx, [rsp+38h+arg_8]
0x14000e524  mov     rsi, [rsp+38h+arg_18]
0x14000e529  add     rsp, 30h
0x14000e52d  pop     rdi
0x14000e52e  retn
```
