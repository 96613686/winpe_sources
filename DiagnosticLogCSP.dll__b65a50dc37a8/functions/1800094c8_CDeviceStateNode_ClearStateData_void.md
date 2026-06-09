# CDeviceStateNode::ClearStateData(void)

- ea: `0x1800094c8`
- end: `0x18000960f`
- name: `?ClearStateData@CDeviceStateNode@@KAJXZ`
- size: `327`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800097e0`

## callees

- `0x180001108`
- `0x180001b90`
- `0x1800094c8`
- `0x180010a30`
- `0x180010a7c`
- `0x180011930`
- `0x180011ad8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180009504`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180009504`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800095e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800095e0`

## string_xrefs

- `0x180009534`: `MdmConfiguration`
- `0x18000955a`: `MdmConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CDeviceStateNode::ClearStateData(void)
{
  char IsStateSeparationEnabled; // al
  const WCHAR *v1; // rcx
  int v2; // ebx
  int v3; // eax
  int v5; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey[3]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR v7[1032]; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+860h] [rbp+760h] BYREF
  int *v9; // [rsp+880h] [rbp+780h]
  __int64 v10; // [rsp+888h] [rbp+788h]

  v7[0] = 0;
  memset(hKey, 0, sizeof(hKey));
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v1 = L"OSData\\SOFTWARE\\Microsoft\\DiagnosticLogCSP\\DeviceStateData";
  if ( !IsStateSeparationEnabled )
    v1 = L"SOFTWARE\\Microsoft\\DiagnosticLogCSP\\DeviceStateData";
  v2 = CRegUtils::OpenKey(v1, hKey);
  if ( v2 >= 0 )
  {
    v3 = ATL::CRegKey::RecurseDeleteKey(hKey, L"MdmConfiguration");
    v2 = v3;
    if ( !v3 )
      goto LABEL_8;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_8:
      v2 = CLogFileMgr::Initialize(v7, 2, L"MdmConfiguration");
      if ( v2 >= 0 )
        v2 = CLogFileMgr::Delete(v7);
    }
  }
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v5 = v2;
    v9 = &v5;
    v10 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18004AE90, (unsigned __int8 *)&unk_180040C70, 0, 0, 3u, &v8);
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800094c8  mov     [rsp-8+arg_0], rbx
0x1800094cd  push    rbp
0x1800094ce  lea     rbp, [rsp-7A0h]
0x1800094d6  sub     rsp, 8A0h
0x1800094dd  mov     rax, cs:__security_cookie
0x1800094e4  xor     rax, rsp
0x1800094e7  mov     [rbp+7A0h+var_10], rax
0x1800094ee  xor     eax, eax
0x1800094f0  mov     [rsp+8A0h+var_850], ax
0x1800094f5  mov     [rsp+8A0h+hKey], rax
0x1800094fa  mov     [rsp+8A0h+var_860], rax
0x1800094ff  mov     [rsp+8A0h+var_858], rax
0x180009504  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000950b  nop     dword ptr [rax+rax+00h]
0x180009510  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\DiagnosticLogCSP\\"...
0x180009517  lea     rcx, aOsdataSoftware; "OSData\\SOFTWARE\\Microsoft\\Diagnostic"...
0x18000951e  test    al, al
0x180009520  cmovz   rcx, rdx; lpSubKey
0x180009524  lea     rdx, [rsp+8A0h+hKey]; struct ATL::CRegKey *
0x180009529  call    ?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@@Z; CRegUtils::OpenKey(ushort const *,ATL::CRegKey &)
0x18000952e  mov     ebx, eax
0x180009530  test    eax, eax
0x180009532  js      short loc_180009582
0x180009534  lea     rdx, aMdmconfigurati; "MdmConfiguration"
0x18000953b  lea     rcx, [rsp+8A0h+hKey]; this
0x180009540  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180009545  mov     ebx, eax
0x180009547  test    eax, eax
0x180009549  jz      short loc_18000955A
0x18000954b  jle     short loc_180009556
0x18000954d  movzx   ebx, ax
0x180009550  or      ebx, 80070000h
0x180009556  test    ebx, ebx
0x180009558  js      short loc_180009582
0x18000955a  lea     r8, aMdmconfigurati; "MdmConfiguration"
0x180009561  mov     edx, 2
0x180009566  lea     rcx, [rsp+8A0h+var_850]
0x18000956b  call    ?Initialize@CLogFileMgr@@QEAAJW4LogFileType@@PEBG@Z; CLogFileMgr::Initialize(LogFileType,ushort const *)
0x180009570  mov     ebx, eax
0x180009572  test    eax, eax
0x180009574  js      short loc_180009582
0x180009576  lea     rcx, [rsp+8A0h+var_850]; this
0x18000957b  call    ?Delete@CLogFileMgr@@QEAAJXZ; CLogFileMgr::Delete(void)
0x180009580  mov     ebx, eax
0x180009582  mov     eax, cs:dword_18004AE90
0x180009588  cmp     eax, 5
0x18000958b  jbe     short loc_1800095D6
0x18000958d  mov     [rsp+8A0h+var_870], ebx
0x180009591  lea     rax, [rsp+8A0h+var_870]
0x180009596  mov     [rbp+7A0h+var_20], rax
0x18000959d  mov     [rbp+7A0h+var_18], 4
0x1800095a8  lea     rax, [rbp+7A0h+var_40]
0x1800095af  mov     [rsp+8A0h+var_878], rax
0x1800095b4  mov     [rsp+8A0h+var_880], 3
0x1800095bc  xor     r9d, r9d
0x1800095bf  xor     r8d, r8d
0x1800095c2  lea     rdx, unk_180040C70
0x1800095c9  lea     rcx, dword_18004AE90
0x1800095d0  call    _tlgWriteTransfer_EventWriteTransfer
0x1800095d5  nop
0x1800095d6  mov     rcx, [rsp+8A0h+hKey]; hKey
0x1800095db  test    rcx, rcx
0x1800095de  jz      short loc_1800095EC
0x1800095e0  call    cs:__imp_RegCloseKey
0x1800095e7  nop     dword ptr [rax+rax+00h]
0x1800095ec  mov     eax, ebx
0x1800095ee  mov     rcx, [rbp+7A0h+var_10]
0x1800095f5  xor     rcx, rsp; StackCookie
0x1800095f8  call    __security_check_cookie
0x1800095fd  mov     rbx, [rsp+8A0h+arg_0]
0x180009605  add     rsp, 8A0h
0x18000960c  pop     rbp
0x18000960d  retn
```
