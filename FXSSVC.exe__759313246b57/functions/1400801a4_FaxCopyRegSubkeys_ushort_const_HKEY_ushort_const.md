# FaxCopyRegSubkeys(ushort const *,HKEY__ *,ushort const *)

- ea: `0x1400801a4`
- end: `0x14008030e`
- name: `?FaxCopyRegSubkeys@@YAKPEBGPEAUHKEY__@@0@Z`
- size: `362`
- prototype: `unsigned int(const unsigned __int16 *, HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140082be8`
- `0x140083acc`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140074f18`
- `0x1400801a4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400802ae`
- `ADVAPI32!RegCloseKey` at `0x1400802ae`
- `KERNEL32!GetLastError` at `0x14008020e`
- `KERNEL32!GetLastError` at `0x1400802d6`
- `KERNEL32!GetLastError` at `0x14008020e`
- `KERNEL32!GetLastError` at `0x1400802d6`
- `SHLWAPI!SHCopyKeyW` at `0x140080269`
- `SHLWAPI!SHCopyKeyW` at `0x140080269`

## pseudocode

```c
__int64 __fastcall FaxCopyRegSubkeys(const unsigned __int16 *a1, HKEY a2, const unsigned __int16 *a3)
{
  HKEY v5; // rax
  HKEY v6; // rdi
  DWORD v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // eax
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v5 = OpenRegistryKey(HKEY_LOCAL_MACHINE, a1, 1, 0x20006u);
  v6 = v5;
  if ( v5 )
  {
    v9 = SHCopyKeyW(HKEY_LOCAL_MACHINE, a3, v5, 0);
    v8 = v9;
    if ( v9
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v9);
    }
    if ( RegCloseKey(v6)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
    }
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v7);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1400801a4  push    rbx
0x1400801a6  push    rsi
0x1400801a7  push    rdi
0x1400801a8  push    r14
0x1400801aa  sub     rsp, 28h
0x1400801ae  mov     rsi, r8
0x1400801b1  mov     rbx, rcx
0x1400801b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400801bb  lea     r14, WPP_GLOBAL_Control
0x1400801c2  cmp     rcx, r14
0x1400801c5  jz      short loc_1400801E8
0x1400801c7  test    byte ptr [rcx+1Ch], 2
0x1400801cb  jz      short loc_1400801E8
0x1400801cd  cmp     byte ptr [rcx+19h], 5
0x1400801d1  jb      short loc_1400801E8
0x1400801d3  mov     rcx, [rcx+10h]
0x1400801d7  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x1400801de  mov     edx, 80h
0x1400801e3  call    WPP_SF_
0x1400801e8  mov     rdx, rbx
0x1400801eb  mov     r9d, 20006h
0x1400801f1  mov     rbx, 0FFFFFFFF80000002h
0x1400801f8  mov     r8d, 1
0x1400801fe  mov     rcx, rbx
0x140080201  call    OpenRegistryKey
0x140080206  mov     rdi, rax
0x140080209  test    rax, rax
0x14008020c  jnz     short loc_14008025D
0x14008020e  call    cs:__imp_GetLastError
0x140080215  nop     dword ptr [rax+rax+00h]
0x14008021a  mov     ebx, eax
0x14008021c  mov     rcx, cs:WPP_GLOBAL_Control
0x140080223  cmp     rcx, r14
0x140080226  jz      loc_140080301
0x14008022c  test    byte ptr [rcx+1Ch], 2
0x140080230  jz      loc_140080301
0x140080236  cmp     byte ptr [rcx+19h], 2
0x14008023a  jb      loc_140080301
0x140080240  mov     rcx, [rcx+10h]
0x140080244  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14008024b  mov     edx, 81h
0x140080250  mov     r9d, eax
0x140080253  call    WPP_SF_d
0x140080258  jmp     loc_140080301
0x14008025d  xor     r9d, r9d; fReserved
0x140080260  mov     r8, rdi; hkeyDest
0x140080263  mov     rdx, rsi; pszSrcSubKey
0x140080266  mov     rcx, rbx; hkeySrc
0x140080269  call    cs:__imp_SHCopyKeyW
0x140080270  nop     dword ptr [rax+rax+00h]
0x140080275  mov     ebx, eax
0x140080277  test    eax, eax
0x140080279  jz      short loc_1400802AB
0x14008027b  mov     rcx, cs:WPP_GLOBAL_Control
0x140080282  cmp     rcx, r14
0x140080285  jz      short loc_1400802AB
0x140080287  test    byte ptr [rcx+1Ch], 2
0x14008028b  jz      short loc_1400802AB
0x14008028d  cmp     byte ptr [rcx+19h], 2
0x140080291  jb      short loc_1400802AB
0x140080293  mov     rcx, [rcx+10h]
0x140080297  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14008029e  mov     edx, 82h
0x1400802a3  mov     r9d, eax
0x1400802a6  call    WPP_SF_d
0x1400802ab  mov     rcx, rdi; hKey
0x1400802ae  call    cs:__imp_RegCloseKey
0x1400802b5  nop     dword ptr [rax+rax+00h]
0x1400802ba  test    eax, eax
0x1400802bc  jz      short loc_140080301
0x1400802be  mov     rax, cs:WPP_GLOBAL_Control
0x1400802c5  cmp     rax, r14
0x1400802c8  jz      short loc_140080301
0x1400802ca  test    byte ptr [rax+1Ch], 2
0x1400802ce  jz      short loc_140080301
0x1400802d0  cmp     byte ptr [rax+19h], 2
0x1400802d4  jb      short loc_140080301
0x1400802d6  call    cs:__imp_GetLastError
0x1400802dd  nop     dword ptr [rax+rax+00h]
0x1400802e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400802e9  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x1400802f0  mov     edx, 83h
0x1400802f5  mov     r9d, eax
0x1400802f8  mov     rcx, [rcx+10h]
0x1400802fc  call    WPP_SF_d
0x140080301  mov     eax, ebx
0x140080303  add     rsp, 28h
0x140080307  pop     r14
0x140080309  pop     rdi
0x14008030a  pop     rsi
0x14008030b  pop     rbx
0x14008030c  retn
```
