# SetLocalFaxPrinterSharing

- ea: `0x1400716a8`
- end: `0x140071973`
- name: `SetLocalFaxPrinterSharing`
- size: `715`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400480f0`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140065d14`
- `0x140065dbc`
- `0x140070fc4`
- `0x1400716a8`
- `0x1400818b0`
- `0x140081970`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140071739`
- `KERNEL32!GetLastError` at `0x14007179f`
- `KERNEL32!GetLastError` at `0x140071805`
- `KERNEL32!GetLastError` at `0x140071851`
- `KERNEL32!GetLastError` at `0x1400718ad`
- `KERNEL32!GetLastError` at `0x1400718fa`
- `KERNEL32!GetLastError` at `0x140071739`
- `KERNEL32!GetLastError` at `0x14007179f`
- `KERNEL32!GetLastError` at `0x140071805`
- `KERNEL32!GetLastError` at `0x140071851`
- `KERNEL32!GetLastError` at `0x1400718ad`
- `KERNEL32!GetLastError` at `0x1400718fa`
- `WINSPOOL!SetPrinterW` at `0x1400718f0`
- `WINSPOOL!SetPrinterW` at `0x1400718f0`
- `WINSPOOL!OpenPrinterW` at `0x140071795`
- `WINSPOOL!OpenPrinterW` at `0x140071795`
- `WINSPOOL!GetPrinterW` at `0x1400717f7`
- `WINSPOOL!GetPrinterW` at `0x1400718a3`
- `WINSPOOL!GetPrinterW` at `0x1400717f7`
- `WINSPOOL!GetPrinterW` at `0x1400718a3`
- `WINSPOOL!ClosePrinter` at `0x140071938`
- `WINSPOOL!ClosePrinter` at `0x140071938`

## pseudocode

```c
__int64 __fastcall SetLocalFaxPrinterSharing(__int64 a1, unsigned int a2, unsigned int a3)
{
  DWORD LastError; // ebx
  CMapDeviceId *v4; // rcx
  __int64 v5; // rdx
  BYTE *v6; // rdi
  DWORD v7; // eax
  CMapDeviceId *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  int v11; // eax
  DWORD cbBuf; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE phPrinter; // [rsp+38h] [rbp-C8h] BYREF
  _PRINTER_DEFAULTSW pDefault; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pPrinterName[784]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE pPrinter[4096]; // [rsp+680h] [rbp+580h] BYREF

  phPrinter = 0;
  memset(&pDefault, 0, sizeof(pDefault));
  cbBuf = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
  }
  if ( !(unsigned int)GetFirstFaxPrinterName(pPrinterName, a2, a3) )
  {
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 54;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, LastError);
      return LastError;
    }
    return LastError;
  }
  pDefault.DesiredAccess = 983052;
  if ( OpenPrinterW(pPrinterName, &phPrinter, &pDefault) )
  {
    v6 = pPrinter;
    if ( GetPrinterW(phPrinter, 2u, pPrinter, 0x1000u, &cbBuf) )
      goto LABEL_32;
    v7 = GetLastError();
    LastError = v7;
    if ( v7 != 122 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      v9 = 56;
      goto LABEL_38;
    }
    v6 = (BYTE *)pMemAlloc(cbBuf);
    if ( !v6 )
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      v10 = cbBuf;
      v9 = 57;
      goto LABEL_39;
    }
    if ( GetPrinterW(phPrinter, 2u, v6, cbBuf, &cbBuf) )
    {
LABEL_32:
      v11 = *((_DWORD *)v6 + 26);
      LastError = 0;
      if ( (v11 & 8) == 0 )
        goto LABEL_40;
      *((_DWORD *)v6 + 26) = v11 & 0xFFFFFFF7;
      if ( SetPrinterW(phPrinter, 2u, v6, 0) )
        goto LABEL_40;
      v7 = GetLastError();
      LastError = v7;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      v9 = 59;
    }
    else
    {
      v7 = GetLastError();
      LastError = v7;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      v9 = 58;
    }
LABEL_38:
    v10 = v7;
LABEL_39:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v10);
LABEL_40:
    if ( phPrinter )
      ClosePrinter(phPrinter);
    if ( v6 != pPrinter )
      pMemFree(v6);
    return LastError;
  }
  LastError = GetLastError();
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = 55;
    goto LABEL_10;
  }
  return LastError;
}

```

## disassembly

```asm
0x1400716a8  push    rbp
0x1400716aa  push    rbx
0x1400716ab  push    rsi
0x1400716ac  push    rdi
0x1400716ad  push    r14
0x1400716af  push    r15
0x1400716b1  lea     rbp, [rsp-1598h]
0x1400716b9  mov     eax, 1698h
0x1400716be  call    _alloca_probe
0x1400716c3  sub     rsp, rax
0x1400716c6  mov     rax, cs:__security_cookie
0x1400716cd  xor     rax, rsp
0x1400716d0  mov     [rbp+15C0h+var_40], rax
0x1400716d7  xor     eax, eax
0x1400716d9  mov     [rsp+16C0h+phPrinter], 0
0x1400716e2  xorps   xmm0, xmm0
0x1400716e5  mov     qword ptr [rsp+16C0h+pDefault.DesiredAccess], rax
0x1400716ea  movups  xmmword ptr [rsp+16C0h+pDefault.pDatatype], xmm0
0x1400716ef  mov     [rsp+16C0h+cbBuf], eax
0x1400716f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400716fa  lea     r14, WPP_GLOBAL_Control
0x140071701  lea     r15, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x140071708  lea     esi, [rax+2]
0x14007170b  cmp     rcx, r14
0x14007170e  jz      short loc_14007172B
0x140071710  test    [rcx+1Ch], sil
0x140071714  jz      short loc_14007172B
0x140071716  cmp     byte ptr [rcx+19h], 5
0x14007171a  jb      short loc_14007172B
0x14007171c  mov     rcx, [rcx+10h]
0x140071720  lea     edx, [rax+35h]
0x140071723  mov     r8, r15
0x140071726  call    WPP_SF_
0x14007172b  lea     rcx, [rsp+16C0h+pPrinterName]; unsigned __int16 *
0x140071730  call    ?GetFirstFaxPrinterName@@YAHPEAGKK@Z; GetFirstFaxPrinterName(ushort *,ulong,ulong)
0x140071735  test    eax, eax
0x140071737  jnz     short loc_14007177E
0x140071739  call    cs:__imp_GetLastError
0x14007173f  mov     ebx, eax
0x140071741  mov     rcx, cs:WPP_GLOBAL_Control
0x140071748  cmp     rcx, r14
0x14007174b  jz      loc_140071952
0x140071751  test    [rcx+1Ch], sil
0x140071755  jz      loc_140071952
0x14007175b  cmp     [rcx+19h], sil
0x14007175f  jb      loc_140071952
0x140071765  mov     edx, 36h ; '6'
0x14007176a  mov     rcx, [rcx+10h]
0x14007176e  mov     r9d, ebx
0x140071771  mov     r8, r15
0x140071774  call    WPP_SF_d
0x140071779  jmp     loc_140071952
0x14007177e  lea     r8, [rsp+16C0h+pDefault]; pDefault
0x140071783  mov     [rsp+16C0h+pDefault.DesiredAccess], 0F000Ch
0x14007178b  lea     rdx, [rsp+16C0h+phPrinter]; phPrinter
0x140071790  lea     rcx, [rsp+16C0h+pPrinterName]; pPrinterName
0x140071795  call    cs:__imp_OpenPrinterW
0x14007179b  test    eax, eax
0x14007179d  jnz     short loc_1400717D2
0x14007179f  call    cs:__imp_GetLastError
0x1400717a5  mov     ebx, eax
0x1400717a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400717ae  cmp     rcx, r14
0x1400717b1  jz      loc_140071952
0x1400717b7  test    [rcx+1Ch], sil
0x1400717bb  jz      loc_140071952
0x1400717c1  cmp     [rcx+19h], sil
0x1400717c5  jb      loc_140071952
0x1400717cb  mov     edx, 37h ; '7'
0x1400717d0  jmp     short loc_14007176A
0x1400717d2  mov     rcx, [rsp+16C0h+phPrinter]; hPrinter
0x1400717d7  lea     rax, [rsp+16C0h+cbBuf]
0x1400717dc  mov     r9d, 1000h; cbBuf
0x1400717e2  mov     [rsp+16C0h+pcbNeeded], rax; pcbNeeded
0x1400717e7  lea     r8, [rbp+15C0h+pPrinter]; pPrinter
0x1400717ee  mov     edx, esi; Level
0x1400717f0  lea     rdi, [rbp+15C0h+pPrinter]
0x1400717f7  call    cs:__imp_GetPrinterW
0x1400717fd  test    eax, eax
0x1400717ff  jnz     loc_1400718D4
0x140071805  call    cs:__imp_GetLastError
0x14007180b  mov     ebx, eax
0x14007180d  cmp     eax, 7Ah ; 'z'
0x140071810  jz      short loc_140071840
0x140071812  mov     rcx, cs:WPP_GLOBAL_Control
0x140071819  cmp     rcx, r14
0x14007181c  jz      loc_14007192E
0x140071822  test    [rcx+1Ch], sil
0x140071826  jz      loc_14007192E
0x14007182c  cmp     [rcx+19h], sil
0x140071830  jb      loc_14007192E
0x140071836  mov     edx, 38h ; '8'
0x14007183b  jmp     loc_14007191F
0x140071840  mov     ecx, [rsp+16C0h+cbBuf]; dwBytes
0x140071844  call    pMemAlloc
0x140071849  mov     rdi, rax
0x14007184c  test    rax, rax
0x14007184f  jnz     short loc_14007188A
0x140071851  call    cs:__imp_GetLastError
0x140071857  mov     ebx, eax
0x140071859  mov     rcx, cs:WPP_GLOBAL_Control
0x140071860  cmp     rcx, r14
0x140071863  jz      loc_14007192E
0x140071869  test    [rcx+1Ch], sil
0x14007186d  jz      loc_14007192E
0x140071873  cmp     [rcx+19h], sil
0x140071877  jb      loc_14007192E
0x14007187d  mov     r9d, [rsp+16C0h+cbBuf]
0x140071882  lea     edx, [rdi+39h]
0x140071885  jmp     loc_140071922
0x14007188a  mov     r9d, [rsp+16C0h+cbBuf]; cbBuf
0x14007188f  lea     rax, [rsp+16C0h+cbBuf]
0x140071894  mov     rcx, [rsp+16C0h+phPrinter]; hPrinter
0x140071899  mov     r8, rdi; pPrinter
0x14007189c  mov     edx, esi; Level
0x14007189e  mov     [rsp+16C0h+pcbNeeded], rax; pcbNeeded
0x1400718a3  call    cs:__imp_GetPrinterW
0x1400718a9  test    eax, eax
0x1400718ab  jnz     short loc_1400718D4
0x1400718ad  call    cs:__imp_GetLastError
0x1400718b3  mov     ebx, eax
0x1400718b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400718bc  cmp     rcx, r14
0x1400718bf  jz      short loc_14007192E
0x1400718c1  test    [rcx+1Ch], sil
0x1400718c5  jz      short loc_14007192E
0x1400718c7  cmp     [rcx+19h], sil
0x1400718cb  jb      short loc_14007192E
0x1400718cd  mov     edx, 3Ah ; ':'
0x1400718d2  jmp     short loc_14007191F
0x1400718d4  mov     eax, [rdi+68h]
0x1400718d7  xor     ebx, ebx
0x1400718d9  test    al, 8
0x1400718db  jz      short loc_14007192E
0x1400718dd  and     eax, 0FFFFFFF7h
0x1400718e0  xor     r9d, r9d; Command
0x1400718e3  mov     [rdi+68h], eax
0x1400718e6  mov     r8, rdi; pPrinter
0x1400718e9  mov     rcx, [rsp+16C0h+phPrinter]; hPrinter
0x1400718ee  mov     edx, esi; Level
0x1400718f0  call    cs:__imp_SetPrinterW
0x1400718f6  test    eax, eax
0x1400718f8  jnz     short loc_14007192E
0x1400718fa  call    cs:__imp_GetLastError
0x140071900  mov     ebx, eax
0x140071902  mov     rcx, cs:WPP_GLOBAL_Control
0x140071909  cmp     rcx, r14
0x14007190c  jz      short loc_14007192E
0x14007190e  test    [rcx+1Ch], sil
0x140071912  jz      short loc_14007192E
0x140071914  cmp     [rcx+19h], sil
0x140071918  jb      short loc_14007192E
0x14007191a  mov     edx, 3Bh ; ';'
0x14007191f  mov     r9d, eax
0x140071922  mov     rcx, [rcx+10h]
0x140071926  mov     r8, r15
0x140071929  call    WPP_SF_d
0x14007192e  mov     rcx, [rsp+16C0h+phPrinter]; hPrinter
0x140071933  test    rcx, rcx
0x140071936  jz      short loc_14007193E
0x140071938  call    cs:__imp_ClosePrinter
0x14007193e  lea     rax, [rbp+15C0h+pPrinter]
0x140071945  cmp     rdi, rax
0x140071948  jz      short loc_140071952
0x14007194a  mov     rcx, rdi; lpMem
0x14007194d  call    pMemFree
0x140071952  mov     eax, ebx
0x140071954  mov     rcx, [rbp+15C0h+var_40]
0x14007195b  xor     rcx, rsp; StackCookie
0x14007195e  call    __security_check_cookie
0x140071963  add     rsp, 1698h
0x14007196a  pop     r15
0x14007196c  pop     r14
0x14007196e  pop     rdi
0x14007196f  pop     rsi
0x140071970  pop     rbx
0x140071971  pop     rbp
0x140071972  retn
```
