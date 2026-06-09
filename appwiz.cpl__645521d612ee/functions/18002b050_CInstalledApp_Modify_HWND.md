# CInstalledApp::Modify(HWND__ *)

- ea: `0x18002b050`
- end: `0x18002b14e`
- name: `?Modify@CInstalledApp@@UEAAJPEAUHWND__@@@Z`
- size: `254`
- prototype: `int(CInstalledApp *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18002b050`
- `0x18002b890`
- `0x18002c2e4`
- `0x18002c9c4`
- `0x18002cb1c`
- `0x18004fad4`

## import_xrefs

- `KERNEL32!SetTermsrvAppInstallMode` at `0x18002b0b8`
- `KERNEL32!SetTermsrvAppInstallMode` at `0x18002b13b`
- `KERNEL32!SetTermsrvAppInstallMode` at `0x18002b0b8`
- `KERNEL32!SetTermsrvAppInstallMode` at `0x18002b13b`
- `KERNEL32!TermsrvAppInstallMode` at `0x18002b0ac`
- `KERNEL32!TermsrvAppInstallMode` at `0x18002b0ac`
- `msi!__imp_MsiConfigureProductW` at `0x18002b103`
- `msi!__imp_MsiConfigureProductW` at `0x18002b103`
- `msi!__imp_MsiSetInternalUI` at `0x18002b0ee`
- `msi!__imp_MsiSetInternalUI` at `0x18002b10f`
- `msi!__imp_MsiSetInternalUI` at `0x18002b0ee`
- `msi!__imp_MsiSetInternalUI` at `0x18002b10f`

## pseudocode

```c
__int64 __fastcall CInstalledApp::Modify(WCHAR *this, HWND a2)
{
  signed int v5; // ebx
  unsigned int v6; // ebp
  unsigned int TSInstallMode; // r14d
  INSTALLUILEVEL v8; // ebx
  signed int v9; // edi

  if ( !(unsigned int)CInstalledApp::_IsAppFastUserSwitchingCompliant((CInstalledApp *)this)
    && (unsigned int)_ShowMultiUserWarning(a2) != 1 )
  {
    return 2147500037LL;
  }
  v5 = -2147467259;
  v6 = 0;
  TSInstallMode = _QueryTSInstallMode((WCHAR *)((char *)this
                                              + (-(__int64)((*((_DWORD *)this + 5) & 2) != 0) & 0xFFFFFFFFFFFFFFA4uLL)
                                              + 4288));
  if ( !TSInstallMode )
  {
    v6 = TermsrvAppInstallMode();
    SetTermsrvAppInstallMode(1);
  }
  if ( (this[12] & 4) != 0 )
  {
    if ( (this[10] & 1) != 0 && (int)CInstalledApp::_CreateAppModifyProcess((CInstalledApp *)this, a2, 1) >= 0 )
    {
      v5 = 0;
    }
    else if ( (this[10] & 2) != 0 )
    {
      v8 = MsiSetInternalUI(INSTALLUILEVEL_FULL, 0);
      v9 = MsiConfigureProductW(this + 2098, 0, INSTALLSTATE_DEFAULT);
      MsiSetInternalUI(v8, 0);
      v5 = v9 > 0 ? (unsigned __int16)v9 | 0x80070000 : v9;
      if ( v5 < 0 )
        _ARPErrorMessageBox(a2, v9);
    }
  }
  if ( !TSInstallMode )
    SetTermsrvAppInstallMode(v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002b050  push    rbx
0x18002b052  push    rbp
0x18002b053  push    rsi
0x18002b054  push    rdi
0x18002b055  push    r14
0x18002b057  sub     rsp, 20h
0x18002b05b  mov     rsi, rdx
0x18002b05e  mov     rdi, rcx
0x18002b061  call    ?_IsAppFastUserSwitchingCompliant@CInstalledApp@@AEAAHXZ; CInstalledApp::_IsAppFastUserSwitchingCompliant(void)
0x18002b066  test    eax, eax
0x18002b068  jnz     short loc_18002B081
0x18002b06a  mov     rcx, rsi; HWND
0x18002b06d  call    ?_ShowMultiUserWarning@@YAHPEAUHWND__@@@Z; _ShowMultiUserWarning(HWND__ *)
0x18002b072  cmp     eax, 1
0x18002b075  jz      short loc_18002B081
0x18002b077  mov     eax, 80004005h
0x18002b07c  jmp     loc_18002B143
0x18002b081  mov     eax, [rdi+14h]
0x18002b084  mov     ebx, 80004005h
0x18002b089  and     al, 2
0x18002b08b  neg     al
0x18002b08d  sbb     rcx, rcx
0x18002b090  and     rcx, 0FFFFFFFFFFFFFFA4h
0x18002b094  add     rcx, 10C0h
0x18002b09b  add     rcx, rdi; pszValue
0x18002b09e  call    ?_QueryTSInstallMode@@YAKPEBG@Z; _QueryTSInstallMode(ushort const *)
0x18002b0a3  xor     ebp, ebp
0x18002b0a5  mov     r14d, eax
0x18002b0a8  test    eax, eax
0x18002b0aa  jnz     short loc_18002B0BE
0x18002b0ac  call    cs:__imp_TermsrvAppInstallMode
0x18002b0b2  lea     ecx, [r14+1]
0x18002b0b6  mov     ebp, eax
0x18002b0b8  call    cs:__imp_SetTermsrvAppInstallMode
0x18002b0be  test    byte ptr [rdi+18h], 4
0x18002b0c2  jz      short loc_18002B134
0x18002b0c4  test    byte ptr [rdi+14h], 1
0x18002b0c8  jz      short loc_18002B0E3
0x18002b0ca  mov     r8d, 1; unsigned int
0x18002b0d0  mov     rdx, rsi; HWND
0x18002b0d3  mov     rcx, rdi; this
0x18002b0d6  call    ?_CreateAppModifyProcess@CInstalledApp@@AEAAJPEAUHWND__@@K@Z; CInstalledApp::_CreateAppModifyProcess(HWND__ *,ulong)
0x18002b0db  test    eax, eax
0x18002b0dd  js      short loc_18002B0E3
0x18002b0df  xor     ebx, ebx
0x18002b0e1  jmp     short loc_18002B134
0x18002b0e3  test    byte ptr [rdi+14h], 2
0x18002b0e7  jz      short loc_18002B134
0x18002b0e9  xor     edx, edx; phWnd
0x18002b0eb  lea     ecx, [rdx+5]; dwUILevel
0x18002b0ee  call    cs:__imp_MsiSetInternalUI
0x18002b0f4  xor     edx, edx; iInstallLevel
0x18002b0f6  lea     rcx, [rdi+1064h]; szProduct
0x18002b0fd  mov     ebx, eax
0x18002b0ff  lea     r8d, [rdx+5]; eInstallState
0x18002b103  call    cs:__imp_MsiConfigureProductW
0x18002b109  xor     edx, edx; phWnd
0x18002b10b  mov     ecx, ebx; dwUILevel
0x18002b10d  mov     edi, eax
0x18002b10f  call    cs:__imp_MsiSetInternalUI
0x18002b115  test    edi, edi
0x18002b117  jg      short loc_18002B11D
0x18002b119  mov     ebx, edi
0x18002b11b  jmp     short loc_18002B126
0x18002b11d  movzx   ebx, di
0x18002b120  or      ebx, 80070000h
0x18002b126  test    ebx, ebx
0x18002b128  jns     short loc_18002B134
0x18002b12a  mov     edx, edi; dwMessageId
0x18002b12c  mov     rcx, rsi; hWnd
0x18002b12f  call    ?_ARPErrorMessageBox@@YAXPEAUHWND__@@K@Z; _ARPErrorMessageBox(HWND__ *,ulong)
0x18002b134  test    r14d, r14d
0x18002b137  jnz     short loc_18002B141
0x18002b139  mov     ecx, ebp
0x18002b13b  call    cs:__imp_SetTermsrvAppInstallMode
0x18002b141  mov     eax, ebx
0x18002b143  add     rsp, 20h
0x18002b147  pop     r14
0x18002b149  pop     rdi
0x18002b14a  pop     rsi
0x18002b14b  pop     rbp
0x18002b14c  pop     rbx
0x18002b14d  retn
```
