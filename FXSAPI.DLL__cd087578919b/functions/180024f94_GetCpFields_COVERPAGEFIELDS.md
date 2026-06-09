# GetCpFields(_COVERPAGEFIELDS *)

- ea: `0x180024f94`
- end: `0x1800250fb`
- name: `?GetCpFields@@YAHPEAU_COVERPAGEFIELDS@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(struct _COVERPAGEFIELDS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800254e0`

## callees

- `0x180024ed0`
- `0x180024f94`
- `0x18003d4ca`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800250de`
- `ADVAPI32!RegCloseKey` at `0x1800250de`
- `ADVAPI32!RegOpenKeyExW` at `0x180024fcc`
- `ADVAPI32!RegOpenKeyExW` at `0x180024fcc`

## string_xrefs

- `0x180025022`: `Company`

## pseudocode

```c
__int64 __fastcall GetCpFields(struct _COVERPAGEFIELDS *a1)
{
  HKEY v3; // rcx
  unsigned __int16 *CpField; // rax
  HKEY v5; // rcx
  unsigned __int16 *v6; // rax
  HKEY v7; // rcx
  unsigned __int16 *v8; // rax
  HKEY v9; // rcx
  unsigned __int16 *v10; // rax
  HKEY v11; // rcx
  unsigned __int16 *v12; // rax
  HKEY v13; // rcx
  unsigned __int16 *v14; // rax
  HKEY v15; // rcx
  unsigned __int16 *v16; // rax
  HKEY v17; // rcx
  unsigned __int16 *v18; // rax
  HKEY v19; // rcx
  unsigned __int16 *v20; // rax
  HKEY v21; // rcx
  unsigned __int16 *v22; // rax
  HKEY v23; // rcx
  HKEY hKey; // [rsp+48h] [rbp+18h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Fax\\UserInfo", 0, 0x2000000u, &hKey) )
    return 0;
  memset_0((char *)a1 + 4, 0, 0xECu);
  v3 = hKey;
  *(_DWORD *)a1 = 240;
  CpField = GetCpField(v3, L"FullName");
  v5 = hKey;
  *((_QWORD *)a1 + 14) = CpField;
  v6 = GetCpField(v5, L"FaxNumber");
  v7 = hKey;
  *((_QWORD *)a1 + 15) = v6;
  v8 = GetCpField(v7, L"Company");
  v9 = hKey;
  *((_QWORD *)a1 + 16) = v8;
  v10 = GetCpField(v9, L"Address");
  v11 = hKey;
  *((_QWORD *)a1 + 17) = v10;
  v12 = GetCpField(v11, L"Title");
  v13 = hKey;
  *((_QWORD *)a1 + 18) = v12;
  v14 = GetCpField(v13, L"Department");
  v15 = hKey;
  *((_QWORD *)a1 + 19) = v14;
  v16 = GetCpField(v15, L"Office");
  v17 = hKey;
  *((_QWORD *)a1 + 20) = v16;
  v18 = GetCpField(v17, L"HomePhone");
  v19 = hKey;
  *((_QWORD *)a1 + 21) = v18;
  v20 = GetCpField(v19, L"OfficePhone");
  v21 = hKey;
  *((_QWORD *)a1 + 22) = v20;
  v22 = GetCpField(v21, L"Mailbox");
  v23 = hKey;
  *((_QWORD *)a1 + 23) = v22;
  RegCloseKey(v23);
  return 1;
}

```

## disassembly

```asm
0x180024f94  mov     [rsp-8+arg_0], rbx
0x180024f99  push    rbp
0x180024f9a  mov     rbp, rsp
0x180024f9d  sub     rsp, 30h
0x180024fa1  mov     rbx, rcx
0x180024fa4  mov     [rbp+hKey], 0
0x180024fac  lea     rax, [rbp+hKey]
0x180024fb0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180024fb7  mov     r9d, 2000000h; samDesired
0x180024fbd  mov     [rsp+30h+phkResult], rax; phkResult
0x180024fc2  xor     r8d, r8d; ulOptions
0x180024fc5  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Fax\\UserInfo"
0x180024fcc  call    cs:__imp_RegOpenKeyExW
0x180024fd3  nop     dword ptr [rax+rax+00h]
0x180024fd8  test    eax, eax
0x180024fda  jz      short loc_180024FE3
0x180024fdc  xor     eax, eax
0x180024fde  jmp     loc_1800250EF
0x180024fe3  lea     rcx, [rbx+4]; void *
0x180024fe7  xor     edx, edx; Val
0x180024fe9  mov     r8d, 0ECh; Size
0x180024fef  call    memset_0
0x180024ff4  mov     rcx, [rbp+hKey]; hKey
0x180024ff8  lea     rdx, ValueName; "FullName"
0x180024fff  mov     dword ptr [rbx], 0F0h
0x180025005  call    ?GetCpField@@YAPEAGPEAUHKEY__@@PEBG@Z; GetCpField(HKEY__ *,ushort const *)
0x18002500a  mov     rcx, [rbp+hKey]; hKey
0x18002500e  lea     rdx, aFaxnumber; "FaxNumber"
0x180025015  mov     [rbx+70h], rax
0x180025019  call    ?GetCpField@@YAPEAGPEAUHKEY__@@PEBG@Z; GetCpField(HKEY__ *,ushort const *)
0x18002501e  mov     rcx, [rbp+hKey]; hKey
0x180025022  lea     rdx, aCompany; "Company"
0x180025029  mov     [rbx+78h], rax
0x18002502d  call    ?GetCpField@@YAPEAGPEAUHKEY__@@PEBG@Z; GetCpField(HKEY__ *,ushort const *)
0x180025032  mov     rcx, [rbp+hKey]; hKey
0x180025036  lea     rdx, aAddress; "Address"
0x18002503d  mov     [rbx+80h], rax
0x180025044  call    ?GetCpField@@YAPEAGPEAUHKEY__@@PEBG@Z; GetCpField(HKEY__ *,ushort const *)
0x180025049  mov     rcx, [rbp+hKey]; hKey
0x18002504d  lea     rdx, aTitle; "Title"
0x180025054  mov     [rbx+88h], rax
0x18002505b  call    ?GetCpField@@YAPEAGPEAUHKEY__@@PEBG@Z; GetCpField(HKEY__ *,ushort const *)
0x180025060  mov     rcx, [rbp+hKey]; hKey
0x180025064  lea     rdx, aDepartment; "Department"
0x18002506b  mov     [rbx+90h], rax
0x180025072  call    ?GetCpField@@YAPEAGPEAUHKEY__@@PEBG@Z; GetCpField(HKEY__ *,ushort const *)
0x180025077  mov     rcx, [rbp+hKey]; hKey
0x18002507b  lea     rdx, aOffice; "Office"
0x180025082  mov     [rbx+98h], rax
0x180025089  call    ?GetCpField@@YAPEAGPEAUHKEY__@@PEBG@Z; GetCpField(HKEY__ *,ushort const *)
0x18002508e  mov     rcx, [rbp+hKey]; hKey
0x180025092  lea     rdx, aHomephone; "HomePhone"
0x180025099  mov     [rbx+0A0h], rax
0x1800250a0  call    ?GetCpField@@YAPEAGPEAUHKEY__@@PEBG@Z; GetCpField(HKEY__ *,ushort const *)
0x1800250a5  mov     rcx, [rbp+hKey]; hKey
0x1800250a9  lea     rdx, aOfficephone; "OfficePhone"
0x1800250b0  mov     [rbx+0A8h], rax
0x1800250b7  call    ?GetCpField@@YAPEAGPEAUHKEY__@@PEBG@Z; GetCpField(HKEY__ *,ushort const *)
0x1800250bc  mov     rcx, [rbp+hKey]; hKey
0x1800250c0  lea     rdx, aMailbox; "Mailbox"
0x1800250c7  mov     [rbx+0B0h], rax
0x1800250ce  call    ?GetCpField@@YAPEAGPEAUHKEY__@@PEBG@Z; GetCpField(HKEY__ *,ushort const *)
0x1800250d3  mov     rcx, [rbp+hKey]; hKey
0x1800250d7  mov     [rbx+0B8h], rax
0x1800250de  call    cs:__imp_RegCloseKey
0x1800250e5  nop     dword ptr [rax+rax+00h]
0x1800250ea  mov     eax, 1
0x1800250ef  mov     rbx, [rsp+30h+arg_0]
0x1800250f4  add     rsp, 30h
0x1800250f8  pop     rbp
0x1800250f9  retn
```
