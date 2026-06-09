# CWbemBackupRestore::CWbemBackupRestore(HINSTANCE__ *)

- ea: `0x1800041e8`
- end: `0x180004343`
- name: `??0CWbemBackupRestore@@QEAA@PEAUHINSTANCE__@@@Z`
- size: `347`
- prototype: `CWbemBackupRestore *__fastcall(CWbemBackupRestore *__hidden this, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800052a0`

## callees

- `0x1800041e8`
- `0x180004fd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000430c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000430c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000427b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000427b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800042b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800042b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CWbemBackupRestore *__fastcall CWbemBackupRestore::CWbemBackupRestore(CWbemBackupRestore *this, HINSTANCE a2)
{
  LSTATUS v3; // edi
  struct _LIST_ENTRY *v4; // rcx
  int v6; // eax
  LPCRITICAL_SECTION Type; // [rsp+50h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+28h] BYREF
  int v9; // [rsp+5Ch] [rbp+2Ch]
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  v9 = HIDWORD(a2);
  *(_QWORD *)this = &CWbemBackupRestore::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = g_hInstance;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 900000;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 22) = 0;
  Data = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\CIMOM", 0, 0x20019u, &hKey);
  if ( !v3 )
  {
    cbData = 4;
    LODWORD(Type) = 0;
    v3 = RegQueryValueExW(hKey, L"PauseResumeTimeOut", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData);
    if ( !v3 && (_DWORD)Type != 4 )
      v3 = 1804;
    RegCloseKey(hKey);
  }
  if ( !v3 )
  {
    v6 = 30000;
    if ( Data > 0x7530 )
      v6 = Data;
    *((_DWORD *)this + 12) = v6;
  }
  CInCritSec::CInCritSec((CInCritSec *)&Type, &CWbemBackupRestore::s_CritSec);
  v4 = off_180032040;
  if ( off_180032040->Flink != &CWbemBackupRestore::s_ListHead )
    __fastfail(3u);
  *((_QWORD *)this + 9) = &CWbemBackupRestore::s_ListHead;
  *((_QWORD *)this + 10) = v4;
  v4->Flink = (struct _LIST_ENTRY *)((char *)this + 72);
  off_180032040 = (struct _LIST_ENTRY *)((char *)this + 72);
  LeaveCriticalSection(Type);
  return this;
}

```

## disassembly

```asm
0x1800041e8  mov     qword ptr [rsp-18h+Data], rdx
0x1800041ed  push    rbp
0x1800041ee  push    rbx
0x1800041ef  push    rdi
0x1800041f0  mov     rbp, rsp
0x1800041f3  sub     rsp, 30h
0x1800041f7  mov     rbx, rcx
0x1800041fa  lea     rax, ??_7CWbemBackupRestore@@6B@; const CWbemBackupRestore::`vftable'
0x180004201  mov     [rcx], rax
0x180004204  mov     dword ptr [rcx+8], 0
0x18000420b  mov     qword ptr [rcx+10h], 0
0x180004213  mov     qword ptr [rcx+18h], 0
0x18000421b  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x180004222  mov     [rcx+20h], rax
0x180004226  mov     qword ptr [rcx+28h], 0
0x18000422e  mov     dword ptr [rcx+30h], 0DBBA0h
0x180004235  mov     qword ptr [rcx+38h], 0
0x18000423d  mov     qword ptr [rcx+40h], 0
0x180004245  mov     dword ptr [rcx+58h], 0
0x18000424c  mov     [rbp+Data], 0
0x180004253  mov     [rbp+hKey], 0
0x18000425b  lea     rax, [rbp+hKey]
0x18000425f  mov     [rsp+30h+phkResult], rax; phkResult
0x180004264  mov     r9d, 20019h; samDesired
0x18000426a  xor     r8d, r8d; ulOptions
0x18000426d  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x180004274  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000427b  call    cs:__imp_RegOpenKeyExW
0x180004281  mov     edi, eax
0x180004283  test    eax, eax
0x180004285  jnz     short loc_1800042CB
0x180004287  mov     [rbp+cbData], 4
0x18000428e  mov     dword ptr [rbp+Type], eax
0x180004291  lea     rax, [rbp+cbData]
0x180004295  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000429a  lea     rax, [rbp+Data]
0x18000429e  mov     [rsp+30h+phkResult], rax; lpData
0x1800042a3  lea     r9, [rbp+Type]; lpType
0x1800042a7  xor     r8d, r8d; lpReserved
0x1800042aa  lea     rdx, ValueName; "PauseResumeTimeOut"
0x1800042b1  mov     rcx, [rbp+hKey]; hKey
0x1800042b5  call    cs:__imp_RegQueryValueExW
0x1800042bb  mov     edi, eax
0x1800042bd  test    eax, eax
0x1800042bf  jz      short loc_18000431D
0x1800042c1  mov     rcx, [rbp+hKey]; hKey
0x1800042c5  call    cs:__imp_RegCloseKey
0x1800042cb  test    edi, edi
0x1800042cd  jz      short loc_18000432B
0x1800042cf  lea     rdx, ?s_CritSec@CWbemBackupRestore@@1VCStaticCritSec@@A; struct _RTL_CRITICAL_SECTION *
0x1800042d6  lea     rcx, [rbp+Type]; this
0x1800042da  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x1800042df  nop
0x1800042e0  mov     rcx, cs:off_180032040
0x1800042e7  lea     rdx, ?s_ListHead@CWbemBackupRestore@@1U_LIST_ENTRY@@A; _LIST_ENTRY CWbemBackupRestore::s_ListHead
0x1800042ee  cmp     [rcx], rdx
0x1800042f1  jnz     short loc_18000433C
0x1800042f3  lea     rax, [rbx+48h]
0x1800042f7  mov     [rax], rdx
0x1800042fa  mov     [rax+8], rcx
0x1800042fe  mov     [rcx], rax
0x180004301  mov     cs:off_180032040, rax
0x180004308  mov     rcx, [rbp+Type]; lpCriticalSection
0x18000430c  call    cs:__imp_LeaveCriticalSection
0x180004312  mov     rax, rbx
0x180004315  add     rsp, 30h
0x180004319  pop     rdi
0x18000431a  pop     rbx
0x18000431b  pop     rbp
0x18000431c  retn
0x18000431d  mov     eax, 70Ch
0x180004322  cmp     dword ptr [rbp+Type], 4
0x180004326  cmovnz  edi, eax
0x180004329  jmp     short loc_1800042C1
0x18000432b  mov     eax, 7530h
0x180004330  cmp     [rbp+Data], eax
0x180004333  cmova   eax, [rbp+Data]
0x180004337  mov     [rbx+30h], eax
0x18000433a  jmp     short loc_1800042CF
0x18000433c  mov     ecx, 3
0x180004341  int     29h; Win8: RtlFailFast(ecx)
```
