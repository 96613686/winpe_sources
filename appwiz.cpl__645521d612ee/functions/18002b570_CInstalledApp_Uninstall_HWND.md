# CInstalledApp::Uninstall(HWND__ *)

- ea: `0x18002b570`
- end: `0x18002b645`
- name: `?Uninstall@CInstalledApp@@UEAAJPEAUHWND__@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(CInstalledApp *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18002b570`
- `0x18002bdd8`
- `0x18002bf28`
- `0x18002c2e4`
- `0x18002c528`
- `0x18002c9c4`
- `0x18002cb1c`
- `0x18004fb80`

## import_xrefs

- `KERNEL32!SetTermsrvAppInstallMode` at `0x18002b5eb`
- `KERNEL32!SetTermsrvAppInstallMode` at `0x18002b630`
- `KERNEL32!SetTermsrvAppInstallMode` at `0x18002b5eb`
- `KERNEL32!SetTermsrvAppInstallMode` at `0x18002b630`
- `KERNEL32!TermsrvAppInstallMode` at `0x18002b5df`
- `KERNEL32!TermsrvAppInstallMode` at `0x18002b5df`

## pseudocode

```c
__int64 __fastcall CInstalledApp::Uninstall(CInstalledApp *this, HWND a2)
{
  unsigned int v5; // edi
  unsigned int TSInstallMode; // ebp
  unsigned int v7; // r14d
  int updated; // eax

  if ( !(unsigned int)CInstalledApp::_IsAppFastUserSwitchingCompliant(this)
    && (unsigned int)_ShowMultiUserWarning(a2) != 1 )
  {
    return 2147500037LL;
  }
  v5 = -2147467259;
  TSInstallMode = 1;
  v7 = 0;
  if ( (unsigned int)IsTerminalServicesRunning() )
  {
    TSInstallMode = _QueryTSInstallMode((LPCWSTR)((char *)this
                                                + (-(__int64)((*((_DWORD *)this + 5) & 2) != 0) & 0xFFFFFFFFFFFFFFA4uLL)
                                                + 4288));
    if ( !TSInstallMode )
    {
      v7 = TermsrvAppInstallMode();
      SetTermsrvAppInstallMode(1);
    }
  }
  if ( *((_DWORD *)this + 5) == 1 )
  {
    updated = CInstalledApp::_LegacyUninstall(this, a2);
LABEL_13:
    v5 = updated;
    goto LABEL_14;
  }
  if ( *((_DWORD *)this + 5) == 2 )
  {
    if ( *((_WORD *)this + 2666) )
      updated = CInstalledApp::_DarwinUpdateUninstall(this, a2);
    else
      updated = CInstalledApp::_DarwinAppUninstall(this, a2);
    goto LABEL_13;
  }
LABEL_14:
  if ( !TSInstallMode )
    SetTermsrvAppInstallMode(v7);
  return v5;
}

```

## disassembly

```asm
0x18002b570  push    rbx
0x18002b572  push    rbp
0x18002b573  push    rsi
0x18002b574  push    rdi
0x18002b575  push    r14
0x18002b577  push    r15
0x18002b579  sub     rsp, 28h
0x18002b57d  mov     rsi, rdx
0x18002b580  mov     rbx, rcx
0x18002b583  call    ?_IsAppFastUserSwitchingCompliant@CInstalledApp@@AEAAHXZ; CInstalledApp::_IsAppFastUserSwitchingCompliant(void)
0x18002b588  xor     r15d, r15d
0x18002b58b  test    eax, eax
0x18002b58d  jnz     short loc_18002B5A6
0x18002b58f  mov     rcx, rsi; HWND
0x18002b592  call    ?_ShowMultiUserWarning@@YAHPEAUHWND__@@@Z; _ShowMultiUserWarning(HWND__ *)
0x18002b597  cmp     eax, 1
0x18002b59a  jz      short loc_18002B5A6
0x18002b59c  mov     eax, 80004005h
0x18002b5a1  jmp     loc_18002B638
0x18002b5a6  mov     edi, 80004005h
0x18002b5ab  mov     ebp, 1
0x18002b5b0  mov     r14d, r15d
0x18002b5b3  call    IsTerminalServicesRunning
0x18002b5b8  test    eax, eax
0x18002b5ba  jz      short loc_18002B5F1
0x18002b5bc  mov     eax, [rbx+14h]
0x18002b5bf  and     al, 2
0x18002b5c1  neg     al
0x18002b5c3  sbb     rcx, rcx
0x18002b5c6  and     rcx, 0FFFFFFFFFFFFFFA4h
0x18002b5ca  add     rcx, 10C0h
0x18002b5d1  add     rcx, rbx; pszValue
0x18002b5d4  call    ?_QueryTSInstallMode@@YAKPEBG@Z; _QueryTSInstallMode(ushort const *)
0x18002b5d9  mov     ebp, eax
0x18002b5db  test    eax, eax
0x18002b5dd  jnz     short loc_18002B5F1
0x18002b5df  call    cs:__imp_TermsrvAppInstallMode
0x18002b5e5  lea     ecx, [rbp+1]
0x18002b5e8  mov     r14d, eax
0x18002b5eb  call    cs:__imp_SetTermsrvAppInstallMode
0x18002b5f1  mov     edx, [rbx+14h]
0x18002b5f4  sub     edx, 1
0x18002b5f7  jz      short loc_18002B61C
0x18002b5f9  cmp     edx, 1
0x18002b5fc  jnz     short loc_18002B629
0x18002b5fe  mov     rdx, rsi; HWND
0x18002b601  mov     rcx, rbx; this
0x18002b604  cmp     [rbx+14D4h], r15w
0x18002b60c  jz      short loc_18002B615
0x18002b60e  call    ?_DarwinUpdateUninstall@CInstalledApp@@AEAAJPEAUHWND__@@@Z; CInstalledApp::_DarwinUpdateUninstall(HWND__ *)
0x18002b613  jmp     short loc_18002B627
0x18002b615  call    ?_DarwinAppUninstall@CInstalledApp@@AEAAJPEAUHWND__@@@Z; CInstalledApp::_DarwinAppUninstall(HWND__ *)
0x18002b61a  jmp     short loc_18002B627
0x18002b61c  mov     rdx, rsi; HWND
0x18002b61f  mov     rcx, rbx; this
0x18002b622  call    ?_LegacyUninstall@CInstalledApp@@AEAAJPEAUHWND__@@@Z; CInstalledApp::_LegacyUninstall(HWND__ *)
0x18002b627  mov     edi, eax
0x18002b629  test    ebp, ebp
0x18002b62b  jnz     short loc_18002B636
0x18002b62d  mov     ecx, r14d
0x18002b630  call    cs:__imp_SetTermsrvAppInstallMode
0x18002b636  mov     eax, edi
0x18002b638  add     rsp, 28h
0x18002b63c  pop     r15
0x18002b63e  pop     r14
0x18002b640  pop     rdi
0x18002b641  pop     rsi
0x18002b642  pop     rbp
0x18002b643  pop     rbx
0x18002b644  retn
```
