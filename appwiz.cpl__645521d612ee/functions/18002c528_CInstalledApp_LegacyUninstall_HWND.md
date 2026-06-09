# CInstalledApp::_LegacyUninstall(HWND__ *)

- ea: `0x18002c528`
- end: `0x18002c5b4`
- name: `?_LegacyUninstall@CInstalledApp@@AEAAJPEAUHWND__@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(CInstalledApp *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18002b570`

## callees

- `0x18002b890`
- `0x18002c528`
- `0x18005317c`
- `0x180053a84`
- `0x180053cf0`

## import_xrefs

- `KERNEL32!SetTermsrvAppInstallMode` at `0x18002c572`
- `KERNEL32!SetTermsrvAppInstallMode` at `0x18002c59b`
- `KERNEL32!SetTermsrvAppInstallMode` at `0x18002c572`
- `KERNEL32!SetTermsrvAppInstallMode` at `0x18002c59b`
- `KERNEL32!TermsrvAppInstallMode` at `0x18002c561`
- `KERNEL32!TermsrvAppInstallMode` at `0x18002c561`

## pseudocode

```c
__int64 __fastcall CInstalledApp::_LegacyUninstall(CInstalledApp *this, HWND a2)
{
  CAppScriptManager *inited; // rdi
  unsigned int AppModifyProcess; // ebp
  int v6; // esi
  unsigned int v7; // edx
  __int64 *i; // rbx

  inited = (CAppScriptManager *)ScriptManagerInitScripts();
  AppModifyProcess = -2147467259;
  if ( (*((_BYTE *)this + 24) & 2) != 0 )
    AppModifyProcess = CInstalledApp::_CreateAppModifyProcess(this, a2, 0);
  if ( inited )
  {
    v6 = 0;
    if ( !(unsigned int)TermsrvAppInstallMode() || (v6 = 1, (unsigned int)SetTermsrvAppInstallMode(0)) )
    {
      for ( i = *(__int64 **)inited; ; CAppScript::RunScriptIfApplicable((CAppScript *)i[2]) )
      {
        i = (__int64 *)*i;
        if ( i == *(__int64 **)inited )
          break;
      }
      if ( v6 )
        SetTermsrvAppInstallMode(1);
    }
    CAppScriptManager::`scalar deleting destructor'(inited, v7);
  }
  return AppModifyProcess;
}

```

## disassembly

```asm
0x18002c528  push    rbx
0x18002c52a  push    rbp
0x18002c52b  push    rsi
0x18002c52c  push    rdi
0x18002c52d  sub     rsp, 28h
0x18002c531  mov     rsi, rdx
0x18002c534  mov     rbx, rcx
0x18002c537  call    ScriptManagerInitScripts
0x18002c53c  test    byte ptr [rbx+18h], 2
0x18002c540  mov     rdi, rax
0x18002c543  mov     ebp, 80004005h
0x18002c548  jz      short loc_18002C55A
0x18002c54a  xor     r8d, r8d; unsigned int
0x18002c54d  mov     rdx, rsi; HWND
0x18002c550  mov     rcx, rbx; this
0x18002c553  call    ?_CreateAppModifyProcess@CInstalledApp@@AEAAJPEAUHWND__@@K@Z; CInstalledApp::_CreateAppModifyProcess(HWND__ *,ulong)
0x18002c558  mov     ebp, eax
0x18002c55a  test    rdi, rdi
0x18002c55d  jz      short loc_18002C5A9
0x18002c55f  xor     esi, esi
0x18002c561  call    cs:__imp_TermsrvAppInstallMode
0x18002c567  test    eax, eax
0x18002c569  jz      short loc_18002C57C
0x18002c56b  xor     ecx, ecx
0x18002c56d  mov     esi, 1
0x18002c572  call    cs:__imp_SetTermsrvAppInstallMode
0x18002c578  test    eax, eax
0x18002c57a  jz      short loc_18002C5A1
0x18002c57c  mov     rbx, [rdi]
0x18002c57f  mov     rbx, [rbx]
0x18002c582  cmp     rbx, [rdi]
0x18002c585  jz      short loc_18002C592
0x18002c587  mov     rcx, [rbx+10h]; this
0x18002c58b  call    ?RunScriptIfApplicable@CAppScript@@QEAAHXZ; CAppScript::RunScriptIfApplicable(void)
0x18002c590  jmp     short loc_18002C57F
0x18002c592  test    esi, esi
0x18002c594  jz      short loc_18002C5A1
0x18002c596  mov     ecx, 1
0x18002c59b  call    cs:__imp_SetTermsrvAppInstallMode
0x18002c5a1  mov     rcx, rdi; this
0x18002c5a4  call    ??_GCAppScriptManager@@QEAAPEAXI@Z; CAppScriptManager::`scalar deleting destructor'(uint)
0x18002c5a9  mov     eax, ebp
0x18002c5ab  add     rsp, 28h
0x18002c5af  pop     rdi
0x18002c5b0  pop     rsi
0x18002c5b1  pop     rbp
0x18002c5b2  pop     rbx
0x18002c5b3  retn
```
