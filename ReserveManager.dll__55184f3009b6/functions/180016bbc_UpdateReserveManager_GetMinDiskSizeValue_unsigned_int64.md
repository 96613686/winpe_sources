# UpdateReserveManager::GetMinDiskSizeValue(unsigned __int64 *)

- ea: `0x180016bbc`
- end: `0x180016ca3`
- name: `?GetMinDiskSizeValue@UpdateReserveManager@@AEAAJPEA_K@Z`
- size: `231`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012bf0`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180016bbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016c1d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016c1d`

## string_xrefs

- `0x180016c32`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180016c3e`: `UpdateReserveManager::GetMinDiskSizeValue`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::GetMinDiskSizeValue(UpdateReserveManager *this, unsigned __int64 *a2)
{
  HKEY v2; // rcx
  int ValueW; // ebx
  _QWORD v6[4]; // [rsp+40h] [rbp-48h] BYREF
  DWORD v7; // [rsp+60h] [rbp-28h] BYREF
  unsigned __int64 v8; // [rsp+68h] [rbp-20h] BYREF

  v2 = (HKEY)*((_QWORD *)this + 13);
  v8 = 0;
  v7 = 8;
  ValueW = RegGetValueW(v2, L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"MinDiskSize", 0x40u, 0, &v8, &v7);
  if ( ValueW )
  {
    v6[2] = 3590;
    v6[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v6[1] = "UpdateReserveManager::GetMinDiskSizeValue";
    v6[3] = "::RegGetValueW(m_SoftwareKey, L\"Microsoft\\\\Windows\\\\CurrentVersion\\\\ReserveManager\", L\"MinDiskSize\""
            ", 0x00000040, nullptr, &MinDiskSize, &ULongLongDataMax)";
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    RtlReportErrorOrigination(v6, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)ValueW);
    return (unsigned int)ValueW;
  }
  else
  {
    *a2 = v8;
    return 0;
  }
}

```

## disassembly

```asm
0x180016bbc  mov     r11, rsp
0x180016bbf  mov     [r11+18h], rbx
0x180016bc3  push    rdi
0x180016bc4  sub     rsp, 80h
0x180016bcb  mov     rax, cs:__security_cookie
0x180016bd2  xor     rax, rsp
0x180016bd5  mov     [rsp+88h+var_18], rax
0x180016bda  mov     rcx, [rcx+68h]; hkey
0x180016bde  lea     rax, [r11-28h]
0x180016be2  mov     [r11-58h], rax
0x180016be6  lea     r8, aMindisksize; "MinDiskSize"
0x180016bed  lea     rax, [r11-20h]
0x180016bf1  mov     qword ptr [r11-20h], 0
0x180016bf9  mov     rdi, rdx
0x180016bfc  mov     [r11-60h], rax
0x180016c00  mov     r9d, 40h ; '@'; dwFlags
0x180016c06  mov     qword ptr [r11-68h], 0
0x180016c0e  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180016c15  mov     [rsp+88h+var_28], 8
0x180016c1d  call    cs:__imp_RegGetValueW
0x180016c23  mov     ebx, eax
0x180016c25  test    eax, eax
0x180016c27  jz      short loc_180016C7B
0x180016c29  mov     [rsp+88h+var_38], 0E06h
0x180016c32  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180016c39  mov     [rsp+88h+var_48], rax
0x180016c3e  lea     rax, aUpdatereservem_24; "UpdateReserveManager::GetMinDiskSizeVal"...
0x180016c45  mov     [rsp+88h+var_40], rax
0x180016c4a  lea     rax, aReggetvaluewMS_2; "::RegGetValueW(m_SoftwareKey, L\"Micros"...
0x180016c51  mov     [rsp+88h+var_30], rax
0x180016c56  test    ebx, ebx
0x180016c58  jle     short loc_180016C63
0x180016c5a  movzx   ebx, bx
0x180016c5d  or      ebx, 80070000h
0x180016c63  mov     r8d, ebx
0x180016c66  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180016c6d  lea     rcx, [rsp+88h+var_48]
0x180016c72  call    RtlReportErrorOrigination
0x180016c77  mov     eax, ebx
0x180016c79  jmp     short loc_180016C85
0x180016c7b  mov     rax, [rsp+88h+var_20]
0x180016c80  mov     [rdi], rax
0x180016c83  xor     eax, eax
0x180016c85  mov     rcx, [rsp+88h+var_18]
0x180016c8a  xor     rcx, rsp; StackCookie
0x180016c8d  call    __security_check_cookie
0x180016c92  mov     rbx, [rsp+88h+arg_10]
0x180016c9a  add     rsp, 80h
0x180016ca1  pop     rdi
0x180016ca2  retn
```
