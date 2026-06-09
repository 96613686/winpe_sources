# EncryptReceiptsPassword(void)

- ea: `0x1400240e0`
- end: `0x1400242ba`
- name: `?EncryptReceiptsPassword@@YAXXZ`
- size: `474`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400246b0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400240e0`
- `0x14006998c`
- `0x140074f18`
- `0x14008249c`
- `0x140084004`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140024271`
- `ADVAPI32!RegCloseKey` at `0x140024271`
- `ADVAPI32!RegDeleteValueW` at `0x14002422e`
- `ADVAPI32!RegDeleteValueW` at `0x14002422e`
- `KERNEL32!GetLastError` at `0x14002416c`
- `KERNEL32!GetLastError` at `0x1400241f9`
- `KERNEL32!GetLastError` at `0x14002416c`
- `KERNEL32!GetLastError` at `0x1400241f9`

## pseudocode

```c
void EncryptReceiptsPassword(void)
{
  HKEY v0; // rdi
  DWORD LastError; // eax
  _WORD *RegistrySecureString; // rbx
  DWORD v3; // eax
  unsigned int v4; // eax
  __int64 v5; // rax
  __int64 v6; // rcx
  _BYTE *i; // rax
  __int64 v8; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
  }
  LODWORD(v8) = 0;
  v0 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Receipts", 0, 0x2001Fu);
  if ( !v0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, LastError);
    }
    return;
  }
  RegistrySecureString = (_WORD *)GetRegistrySecureString(v0, (__int64)&v8);
  if ( (_DWORD)v8 != 1 )
  {
    if ( !(_DWORD)v8 )
    {
LABEL_17:
      v4 = RegDeleteValueW(v0, L"Password");
      if ( v4
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v4);
      }
      goto LABEL_22;
    }
    if ( !(unsigned int)SetRegistrySecureString(v0) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v3 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v3);
      }
      goto LABEL_17;
    }
  }
LABEL_22:
  RegCloseKey(v0);
  if ( RegistrySecureString )
  {
    v5 = -1;
    do
      ++v5;
    while ( RegistrySecureString[v5] );
    v6 = 2 * v5;
    for ( i = RegistrySecureString; v6; --v6 )
      *i++ = 0;
    pMemFree(RegistrySecureString);
  }
}

```

## disassembly

```asm
0x1400240e0  push    rbx
0x1400240e2  push    rsi
0x1400240e3  push    rdi
0x1400240e4  push    r14
0x1400240e6  sub     rsp, 38h
0x1400240ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400240f1  lea     r14, WPP_GLOBAL_Control
0x1400240f8  cmp     rcx, r14
0x1400240fb  jz      short loc_14002411E
0x1400240fd  test    byte ptr [rcx+1Ch], 4
0x140024101  jz      short loc_14002411E
0x140024103  cmp     byte ptr [rcx+19h], 5
0x140024107  jb      short loc_14002411E
0x140024109  mov     rcx, [rcx+10h]
0x14002410d  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140024114  mov     edx, 2Bh ; '+'
0x140024119  call    WPP_SF_
0x14002411e  xor     esi, esi
0x140024120  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Fax\\Receipts"
0x140024127  mov     r9d, 2001Fh
0x14002412d  mov     dword ptr [rsp+58h+arg_0], esi
0x140024131  xor     r8d, r8d
0x140024134  mov     rcx, 0FFFFFFFF80000002h
0x14002413b  call    OpenRegistryKey
0x140024140  mov     rdi, rax
0x140024143  test    rax, rax
0x140024146  jnz     short loc_14002419A
0x140024148  mov     rax, cs:WPP_GLOBAL_Control
0x14002414f  cmp     rax, r14
0x140024152  jz      loc_1400242AF
0x140024158  test    byte ptr [rax+1Ch], 4
0x14002415c  jz      loc_1400242AF
0x140024162  cmp     byte ptr [rax+19h], 2
0x140024166  jb      loc_1400242AF
0x14002416c  call    cs:__imp_GetLastError
0x140024173  nop     dword ptr [rax+rax+00h]
0x140024178  mov     rcx, cs:WPP_GLOBAL_Control
0x14002417f  lea     edx, [rsi+2Ch]
0x140024182  mov     r9d, eax
0x140024185  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x14002418c  mov     rcx, [rcx+10h]
0x140024190  call    WPP_SF_d
0x140024195  jmp     loc_1400242AF
0x14002419a  lea     rax, [rsp+58h+arg_0]
0x14002419f  xor     r8d, r8d
0x1400241a2  mov     rcx, rdi; hKey
0x1400241a5  mov     [rsp+58h+var_38], rax; __int64
0x1400241aa  call    GetRegistrySecureString
0x1400241af  mov     rbx, rax
0x1400241b2  mov     eax, dword ptr [rsp+58h+arg_0]
0x1400241b6  cmp     eax, 1
0x1400241b9  jz      loc_14002426E
0x1400241bf  test    eax, eax
0x1400241c1  jz      short loc_140024224
0x1400241c3  test    rbx, rbx
0x1400241c6  lea     r8, Class
0x1400241cd  mov     rcx, rdi
0x1400241d0  cmovnz  r8, rbx
0x1400241d4  call    SetRegistrySecureString
0x1400241d9  test    eax, eax
0x1400241db  jnz     loc_14002426E
0x1400241e1  mov     rax, cs:WPP_GLOBAL_Control
0x1400241e8  cmp     rax, r14
0x1400241eb  jz      short loc_140024224
0x1400241ed  test    byte ptr [rax+1Ch], 4
0x1400241f1  jz      short loc_140024224
0x1400241f3  cmp     byte ptr [rax+19h], 2
0x1400241f7  jb      short loc_140024224
0x1400241f9  call    cs:__imp_GetLastError
0x140024200  nop     dword ptr [rax+rax+00h]
0x140024205  mov     rcx, cs:WPP_GLOBAL_Control
0x14002420c  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140024213  mov     edx, 2Dh ; '-'
0x140024218  mov     r9d, eax
0x14002421b  mov     rcx, [rcx+10h]
0x14002421f  call    WPP_SF_d
0x140024224  lea     rdx, aPassword; "Password"
0x14002422b  mov     rcx, rdi; hKey
0x14002422e  call    cs:__imp_RegDeleteValueW
0x140024235  nop     dword ptr [rax+rax+00h]
0x14002423a  test    eax, eax
0x14002423c  jz      short loc_14002426E
0x14002423e  mov     rcx, cs:WPP_GLOBAL_Control
0x140024245  cmp     rcx, r14
0x140024248  jz      short loc_14002426E
0x14002424a  test    byte ptr [rcx+1Ch], 4
0x14002424e  jz      short loc_14002426E
0x140024250  cmp     byte ptr [rcx+19h], 2
0x140024254  jb      short loc_14002426E
0x140024256  mov     rcx, [rcx+10h]
0x14002425a  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140024261  mov     edx, 2Eh ; '.'
0x140024266  mov     r9d, eax
0x140024269  call    WPP_SF_d
0x14002426e  mov     rcx, rdi; hKey
0x140024271  call    cs:__imp_RegCloseKey
0x140024278  nop     dword ptr [rax+rax+00h]
0x14002427d  test    rbx, rbx
0x140024280  jz      short loc_1400242AF
0x140024282  or      rax, 0FFFFFFFFFFFFFFFFh
0x140024286  inc     rax
0x140024289  cmp     [rbx+rax*2], si
0x14002428d  jnz     short loc_140024286
0x14002428f  lea     rcx, [rax+rax]
0x140024293  mov     rax, rbx
0x140024296  test    rcx, rcx
0x140024299  jz      short loc_1400242A7
0x14002429b  mov     [rax], sil
0x14002429e  inc     rax
0x1400242a1  sub     rcx, 1
0x1400242a5  jnz     short loc_14002429B
0x1400242a7  mov     rcx, rbx; lpMem
0x1400242aa  call    pMemFree
0x1400242af  add     rsp, 38h
0x1400242b3  pop     r14
0x1400242b5  pop     rdi
0x1400242b6  pop     rsi
0x1400242b7  pop     rbx
0x1400242b8  retn
```
