# CSystemHive::Unload(void)

- ea: `0x180049110`
- end: `0x180049275`
- name: `?Unload@CSystemHive@@QEAAJXZ`
- size: `357`
- prototype: `__int64 __fastcall(CSystemHive *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18004acc8`
- `0x18004d2a8`

## callees

- `0x180009e04`
- `0x18003e794`
- `0x180049110`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180049147`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180049147`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800491e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049208`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800491e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049208`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800491f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049216`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800491f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049160`
- `WDSCORE!CurrentIP` at `0x180049168`
- `WDSCORE!CurrentIP` at `0x180049168`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800491d2`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800491d2`

## string_xrefs

- `0x180049258`: `SeBackupPrivilege`
- `0x18004923c`: `SeRestorePrivilege`

## pseudocode

```c
__int64 __fastcall CSystemHive::Unload(CSystemHive *this)
{
  void *v3; // rbx
  LSTATUS KeyW; // eax
  unsigned int v5; // ebp
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  void *v9; // rbx
  HANDLE v10; // rax
  HANDLE ProcessHeap; // rax

  if ( !*((_BYTE *)this + 16) )
    return 1;
  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    if ( HeapFree(ProcessHeap, 0, v3) )
      *((_QWORD *)this + 4) = 0;
    v5 = 1;
    goto LABEL_14;
  }
  KeyW = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"ba3ad4be-851e-4bf3-9bc9-43b1cc0acae9");
  v5 = KeyW;
  if ( KeyW > 0 )
    v5 = (unsigned __int16)KeyW | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
    v9 = (void *)*((_QWORD *)this + 3);
    if ( v9 )
    {
      v10 = GetProcessHeap();
      if ( HeapFree(v10, 0, v9) )
        *((_QWORD *)this + 3) = 0;
    }
LABEL_14:
    if ( *((_DWORD *)this + 3) == 1 && !*((_DWORD *)this + 1) )
      EnablePrivilegeEx(L"SeRestorePrivilege", 0, 0);
    if ( *((_DWORD *)this + 2) == 1 && !*(_DWORD *)this )
      EnablePrivilegeEx(L"SeBackupPrivilege", 0, 0);
    *((_BYTE *)this + 16) = 0;
    return v5;
  }
  LastError = GetLastError();
  v7 = CurrentIP();
  v8 = ConstructPartialMsgW(
         0x2000000,
         "CSystemHive::Unload: Failed to unload system hive %s; hr = 0x%x",
         *((const char **)this + 3),
         v5);
  WdsSetupLogMessageW(
    v8,
    0,
    L"D",
    0,
    2921,
    L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
    L"CSystemHive::Unload",
    v7,
    LastError,
    0,
    0);
  return v5;
}

```

## disassembly

```asm
0x180049110  push    rbx
0x180049112  push    rbp
0x180049113  push    rsi
0x180049114  push    rdi
0x180049115  sub     rsp, 68h
0x180049119  cmp     byte ptr [rcx+10h], 0
0x18004911d  mov     rsi, rcx
0x180049120  jnz     short loc_18004912C
0x180049122  mov     eax, 1
0x180049127  jmp     loc_18004926C
0x18004912c  mov     rbx, [rcx+20h]
0x180049130  test    rbx, rbx
0x180049133  jnz     loc_180049208
0x180049139  lea     rdx, ?STR_LOAD_NAME@CSystemHive@@1QBGB; "ba3ad4be-851e-4bf3-9bc9-43b1cc0acae9"
0x180049140  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180049147  call    cs:__imp_RegUnLoadKeyW
0x18004914d  mov     ebp, eax
0x18004914f  test    eax, eax
0x180049151  jle     short loc_18004915C
0x180049153  movzx   ebp, ax
0x180049156  or      ebp, 80070000h
0x18004915c  test    ebp, ebp
0x18004915e  jns     short loc_1800491DD
0x180049160  call    cs:__imp_GetLastError
0x180049166  mov     edi, eax
0x180049168  call    cs:__imp_CurrentIP
0x18004916e  mov     r8, [rsi+18h]
0x180049172  lea     rdx, aCsystemhiveUnl; "CSystemHive::Unload: Failed to unload s"...
0x180049179  mov     r9d, ebp
0x18004917c  mov     ecx, 2000000h; unsigned int
0x180049181  mov     rbx, rax
0x180049184  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180049189  mov     [rsp+88h+var_38], 0
0x180049191  lea     rcx, aCsystemhiveUnl_0; "CSystemHive::Unload"
0x180049198  mov     [rsp+88h+var_40], 0
0x1800491a1  lea     r8, aD; "D"
0x1800491a8  mov     [rsp+88h+var_48], edi
0x1800491ac  xor     r9d, r9d
0x1800491af  mov     [rsp+88h+var_50], rbx
0x1800491b4  xor     edx, edx
0x1800491b6  mov     [rsp+88h+var_58], rcx
0x1800491bb  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x1800491c2  mov     [rsp+88h+var_60], rcx
0x1800491c7  mov     rcx, rax
0x1800491ca  mov     [rsp+88h+var_68], 0B69h
0x1800491d2  call    cs:__imp_WdsSetupLogMessageW
0x1800491d8  jmp     loc_18004926A
0x1800491dd  mov     rbx, [rsi+18h]
0x1800491e1  test    rbx, rbx
0x1800491e4  jz      short loc_18004922D
0x1800491e6  call    cs:__imp_GetProcessHeap
0x1800491ec  mov     r8, rbx; lpMem
0x1800491ef  xor     edx, edx; dwFlags
0x1800491f1  mov     rcx, rax; hHeap
0x1800491f4  call    cs:__imp_HeapFree
0x1800491fa  test    eax, eax
0x1800491fc  jz      short loc_18004922D
0x1800491fe  mov     qword ptr [rsi+18h], 0
0x180049206  jmp     short loc_18004922D
0x180049208  call    cs:__imp_GetProcessHeap
0x18004920e  mov     r8, rbx; lpMem
0x180049211  xor     edx, edx; dwFlags
0x180049213  mov     rcx, rax; hHeap
0x180049216  call    cs:__imp_HeapFree
0x18004921c  test    eax, eax
0x18004921e  jz      short loc_180049228
0x180049220  mov     qword ptr [rsi+20h], 0
0x180049228  mov     ebp, 1
0x18004922d  cmp     dword ptr [rsi+0Ch], 1
0x180049231  jnz     short loc_18004924A
0x180049233  cmp     dword ptr [rsi+4], 0
0x180049237  jnz     short loc_18004924A
0x180049239  xor     r8d, r8d
0x18004923c  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x180049243  xor     edx, edx
0x180049245  call    EnablePrivilegeEx
0x18004924a  cmp     dword ptr [rsi+8], 1
0x18004924e  jnz     short loc_180049266
0x180049250  cmp     dword ptr [rsi], 0
0x180049253  jnz     short loc_180049266
0x180049255  xor     r8d, r8d
0x180049258  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18004925f  xor     edx, edx
0x180049261  call    EnablePrivilegeEx
0x180049266  mov     byte ptr [rsi+10h], 0
0x18004926a  mov     eax, ebp
0x18004926c  add     rsp, 68h
0x180049270  pop     rdi
0x180049271  pop     rsi
0x180049272  pop     rbp
0x180049273  pop     rbx
0x180049274  retn
```
