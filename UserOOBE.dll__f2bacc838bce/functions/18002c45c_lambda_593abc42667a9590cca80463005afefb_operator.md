# _lambda_593abc42667a9590cca80463005afefb_::operator()

- ea: `0x18002c45c`
- end: `0x18002c4f0`
- name: `_lambda_593abc42667a9590cca80463005afefb_::operator()`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c41c`
- `0x18002c4f8`

## callees

- `0x18002d18c`
- `0x180047bd0`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002c499`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002c4b0`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002c4c7`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002c4de`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002c499`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002c4b0`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002c4c7`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002c4de`

## pseudocode

```c
__int64 __fastcall lambda_593abc42667a9590cca80463005afefb_::operator()(_BYTE **a1)
{
  const wchar_t *v1; // rdx

  v1 = L"Clearing Auto-logon values due to failure.";
  if ( !**a1 )
    v1 = L"Clearing Auto-logon values per request";
  UnattendLogW(0, v1);
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"AutoAdminLogon");
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"SystemAutoLogon");
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"DefaultUserName");
  SHDeleteValueW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
    L"IsConnectedAutoLogon");
  return SetAutologonPassword(0);
}

```

## disassembly

```asm
0x18002c45c  push    rbx
0x18002c45e  sub     rsp, 20h
0x18002c462  mov     rax, [rcx]
0x18002c465  lea     rdx, aClearingAutoLo; "Clearing Auto-logon values due to failu"...
0x18002c46c  lea     rcx, aClearingAutoLo_0; "Clearing Auto-logon values per request"
0x18002c473  cmp     byte ptr [rax], 0
0x18002c476  cmovz   rdx, rcx
0x18002c47a  xor     ecx, ecx
0x18002c47c  call    UnattendLogW
0x18002c481  mov     rbx, 0FFFFFFFF80000002h
0x18002c488  lea     r8, aAutoadminlogon; "AutoAdminLogon"
0x18002c48f  mov     rcx, rbx; hkey
0x18002c492  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002c499  call    cs:__imp_SHDeleteValueW
0x18002c49f  lea     r8, aSystemautologo; "SystemAutoLogon"
0x18002c4a6  mov     rcx, rbx; hkey
0x18002c4a9  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002c4b0  call    cs:__imp_SHDeleteValueW
0x18002c4b6  lea     r8, aDefaultusernam; "DefaultUserName"
0x18002c4bd  mov     rcx, rbx; hkey
0x18002c4c0  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002c4c7  call    cs:__imp_SHDeleteValueW
0x18002c4cd  lea     r8, aIsconnectedaut; "IsConnectedAutoLogon"
0x18002c4d4  mov     rcx, rbx; hkey
0x18002c4d7  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002c4de  call    cs:__imp_SHDeleteValueW
0x18002c4e4  xor     ecx, ecx; SourceString
0x18002c4e6  add     rsp, 20h
0x18002c4ea  pop     rbx
0x18002c4eb  jmp     _SetAutologonPassword
```
