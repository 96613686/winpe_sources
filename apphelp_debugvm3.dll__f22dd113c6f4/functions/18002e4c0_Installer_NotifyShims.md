# Installer_NotifyShims

- ea: `0x18002e4c0`
- end: `0x18002e58a`
- name: `Installer_NotifyShims`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000f114`
- `0x18002e4c0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e500`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e500`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e54e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e54e`

## string_xrefs

- `0x18002e538`: `Installer_NotifyShims`
- `0x18002e561`: `Installer_NotifyShims`
- `0x18002e52b`: `Windows hook set in installer.`
- `0x18002e57b`: `User32 is not loaded in this installer.`

## pseudocode

```c
void __fastcall Installer_NotifyShims(int a1)
{
  int v1; // ecx
  __int64 (__fastcall *v2)(__int64, __int64 (__fastcall *)(), _QWORD, _QWORD); // rbx
  DWORD CurrentThreadId; // eax
  DWORD LastError; // eax

  v1 = a1 - 1;
  if ( !v1 || v1 == 99 )
  {
    if ( *(_QWORD *)(InsApiHooks + 264) && *(_QWORD *)(InsApiHooks + 312) )
    {
      v2 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(), _QWORD, _QWORD))(InsApiHooks + 264);
      CurrentThreadId = GetCurrentThreadId();
      InsWindowHook = v2(12, Insp_WindowHook, 0, CurrentThreadId);
      if ( InsWindowHook )
      {
        AslLogCallPrintf(3, "Installer_NotifyShims", 1164, "Windows hook set in installer.");
      }
      else
      {
        LastError = GetLastError();
        AslLogCallPrintf(1, "Installer_NotifyShims", 1156, "Failed to set windows hook[%d]", LastError);
      }
    }
    else
    {
      AslLogCallPrintf(3, "Installer_NotifyShims", 1147, "User32 is not loaded in this installer.");
    }
  }
}

```

## disassembly

```asm
0x18002e4c0  push    rbx
0x18002e4c2  sub     rsp, 30h
0x18002e4c6  sub     ecx, 1
0x18002e4c9  jz      short loc_18002E4D6
0x18002e4cb  cmp     ecx, 63h ; 'c'
0x18002e4ce  jz      short loc_18002E4D6
0x18002e4d0  add     rsp, 30h
0x18002e4d4  pop     rbx
0x18002e4d5  retn
0x18002e4d6  mov     rbx, cs:InsApiHooks
0x18002e4dd  cmp     qword ptr [rbx+108h], 0
0x18002e4e5  jz      loc_18002E57B
0x18002e4eb  cmp     qword ptr [rbx+138h], 0
0x18002e4f3  jz      loc_18002E57B
0x18002e4f9  mov     rbx, [rbx+108h]
0x18002e500  call    cs:__imp_GetCurrentThreadId
0x18002e506  xor     r8d, r8d
0x18002e509  lea     rdx, Insp_WindowHook
0x18002e510  mov     r9d, eax
0x18002e513  mov     rax, rbx
0x18002e516  lea     ecx, [r8+0Ch]
0x18002e51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e51f  mov     cs:InsWindowHook, rax
0x18002e526  test    rax, rax
0x18002e529  jz      short loc_18002E54E
0x18002e52b  lea     r9, aWindowsHookSet; "Windows hook set in installer."
0x18002e532  mov     r8d, 48Ch
0x18002e538  lea     rdx, aInstallerNotif; "Installer_NotifyShims"
0x18002e53f  mov     ecx, 3
0x18002e544  add     rsp, 30h
0x18002e548  pop     rbx
0x18002e549  jmp     AslLogCallPrintf
0x18002e54e  call    cs:__imp_GetLastError
0x18002e554  lea     r9, aFailedToSetWin; "Failed to set windows hook[%d]"
0x18002e55b  mov     r8d, 484h
0x18002e561  lea     rdx, aInstallerNotif; "Installer_NotifyShims"
0x18002e568  mov     [rsp+38h+var_18], eax
0x18002e56c  mov     ecx, 1
0x18002e571  call    AslLogCallPrintf
0x18002e576  jmp     loc_18002E4D0
0x18002e57b  lea     r9, aUser32IsNotLoa; "User32 is not loaded in this installer."
0x18002e582  mov     r8d, 47Bh
0x18002e588  jmp     short loc_18002E538
```
