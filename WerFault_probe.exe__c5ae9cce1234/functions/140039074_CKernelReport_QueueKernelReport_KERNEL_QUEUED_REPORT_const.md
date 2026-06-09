# CKernelReport::QueueKernelReport(KERNEL_QUEUED_REPORT const *)

- ea: `0x140039074`
- end: `0x140039228`
- name: `?QueueKernelReport@CKernelReport@@AEAAJPEBUKERNEL_QUEUED_REPORT@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this, const struct KERNEL_QUEUED_REPORT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140035d20`
- `0x140039820`

## callees

- `0x140005468`
- `0x140034d9c`
- `0x140036634`
- `0x140039074`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140039150`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140039150`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140039215`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140039215`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400391de`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400391de`

## string_xrefs

- `0x1400391f5`: `RegSetValueEx failed`

## pseudocode

```c
__int64 __fastcall CKernelReport::QueueKernelReport(CKernelReport *this, const struct KERNEL_QUEUED_REPORT *a2)
{
  HKEY *v3; // rax
  CKernelReport *v4; // rcx
  signed int v5; // ebx
  const char *v6; // rax
  __int64 v7; // rdx
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  wil::details *lpcSubKeys; // [rsp+20h] [rbp-48h]
  const char *lpcbMaxClassLen; // [rsp+30h] [rbp-38h]
  wil::details::in1diag4 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD cValues; // [rsp+70h] [rbp+8h] BYREF
  int v15; // [rsp+74h] [rbp+Ch]
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  v15 = HIDWORD(this);
  hKey = 0;
  cValues = 0;
  v3 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v5 = CKernelReport::EnsureKernelQueueRegkeyExists(v4, v3);
  if ( v5 < 0 )
  {
    v6 = "EnsureKernelQueueRegkeyExists failed";
    v7 = 516;
LABEL_3:
    LODWORD(lpcSubKeys) = v5;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::QueueKernelReport",
      lpcSubKeys,
      (int)v6,
      lpcbMaxClassLen);
    goto LABEL_17;
  }
  if ( !hKey )
  {
    v5 = -2147024890;
    v6 = "EnsureKernelQueueRegkeyExists returned a NULL key handle, failing";
    v7 = 522;
    goto LABEL_3;
  }
  v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  v5 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    v6 = "RegQueryInfoKey failed";
    v7 = 550;
    goto LABEL_3;
  }
  if ( cValues < 0x40 )
  {
    v9 = RegSetValueExW(hKey, *(LPCWSTR *)a2, 0, 3u, (const BYTE *)a2 + 32, 0x24u);
    v5 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      v6 = "RegSetValueEx failed";
      v7 = 574;
      goto LABEL_3;
    }
    v5 = 0;
  }
  else
  {
    v5 = -2147023613;
    LODWORD(lpcbMaxClassLen) = cValues;
    LODWORD(lpcSubKeys) = -2147023613;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x22E,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::QueueKernelReport",
      lpcSubKeys,
      (int)"Too many kernel faults in the queue: %u",
      lpcbMaxClassLen);
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140039074  mov     rax, rsp
0x140039077  mov     [rax+10h], rbx
0x14003907b  mov     [rax+8], rcx
0x14003907f  push    rdi
0x140039080  sub     rsp, 60h
0x140039084  mov     rdi, rdx
0x140039087  mov     qword ptr [rax+18h], 0
0x14003908f  mov     dword ptr [rax+8], 0
0x140039096  lea     rcx, [rax+18h]
0x14003909a  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003909f  mov     rdx, rax; HKEY *
0x1400390a2  call    ?EnsureKernelQueueRegkeyExists@CKernelReport@@AEAAJPEAPEAUHKEY__@@@Z; CKernelReport::EnsureKernelQueueRegkeyExists(HKEY__ * *)
0x1400390a7  mov     ebx, eax
0x1400390a9  test    eax, eax
0x1400390ab  jns     short loc_1400390DF
0x1400390ad  lea     rax, aEnsurekernelqu_0; "EnsureKernelQueueRegkeyExists failed"
0x1400390b4  mov     edx, 204h; void *
0x1400390b9  mov     [rsp+68h+lpcbMaxSubKeyLen], rax; int
0x1400390be  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x1400390c5  lea     r9, aCkernelreportQ; "CKernelReport::QueueKernelReport"
0x1400390cc  mov     dword ptr [rsp+68h+lpcSubKeys], ebx; wil::details *
0x1400390d0  mov     rcx, [rsp+68h]; this
0x1400390d5  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400390da  jmp     loc_140039208
0x1400390df  mov     rcx, [rsp+68h+hKey]; hKey
0x1400390e7  test    rcx, rcx
0x1400390ea  jnz     short loc_1400390FF
0x1400390ec  mov     ebx, 80070006h
0x1400390f1  lea     rax, aEnsurekernelqu; "EnsureKernelQueueRegkeyExists returned "...
0x1400390f8  mov     edx, 20Ah
0x1400390fd  jmp     short loc_1400390B9
0x1400390ff  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140039108  mov     [rsp+68h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x140039111  mov     [rsp+68h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x14003911a  mov     [rsp+68h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x140039123  lea     rax, [rsp+68h+cValues]
0x140039128  mov     [rsp+68h+lpcValues], rax; lpcValues
0x14003912d  mov     [rsp+68h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x140039136  mov     [rsp+68h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x14003913f  mov     [rsp+68h+lpcSubKeys], 0; lpcSubKeys
0x140039148  xor     r9d, r9d; lpReserved
0x14003914b  xor     r8d, r8d; lpcchClass
0x14003914e  xor     edx, edx; lpClass
0x140039150  call    cs:__imp_RegQueryInfoKeyW
0x140039156  mov     ebx, eax
0x140039158  test    eax, eax
0x14003915a  jz      short loc_140039178
0x14003915c  jle     short loc_140039167
0x14003915e  movzx   ebx, ax
0x140039161  or      ebx, 80070000h
0x140039167  lea     rax, aRegqueryinfoke_1; "RegQueryInfoKey failed"
0x14003916e  mov     edx, 226h
0x140039173  jmp     loc_1400390B9
0x140039178  mov     eax, [rsp+68h+cValues]
0x14003917c  cmp     eax, 40h ; '@'
0x14003917f  jb      short loc_1400391B9
0x140039181  mov     ebx, 80070503h
0x140039186  mov     rcx, [rsp+68h]; this
0x14003918b  mov     dword ptr [rsp+68h+lpcbMaxClassLen], eax; char *
0x14003918f  lea     rax, aTooManyKernelF; "Too many kernel faults in the queue: %u"
0x140039196  mov     [rsp+68h+lpcbMaxSubKeyLen], rax; int
0x14003919b  mov     dword ptr [rsp+68h+lpcSubKeys], ebx; wil::details *
0x14003919f  lea     r9, aCkernelreportQ; "CKernelReport::QueueKernelReport"
0x1400391a6  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x1400391ad  mov     edx, 22Eh; void *
0x1400391b2  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400391b7  jmp     short loc_140039208
0x1400391b9  lea     rax, [rdi+20h]
0x1400391bd  mov     dword ptr [rsp+68h+lpcbMaxSubKeyLen], 24h ; '$'; cbData
0x1400391c5  mov     [rsp+68h+lpcSubKeys], rax; lpData
0x1400391ca  mov     r9d, 3; dwType
0x1400391d0  xor     r8d, r8d; Reserved
0x1400391d3  mov     rdx, [rdi]; lpValueName
0x1400391d6  mov     rcx, [rsp+68h+hKey]; hKey
0x1400391de  call    cs:__imp_RegSetValueExW
0x1400391e4  mov     ebx, eax
0x1400391e6  test    eax, eax
0x1400391e8  jz      short loc_140039206
0x1400391ea  jle     short loc_1400391F5
0x1400391ec  movzx   ebx, ax
0x1400391ef  or      ebx, 80070000h
0x1400391f5  lea     rax, aRegsetvalueexF; "RegSetValueEx failed"
0x1400391fc  mov     edx, 23Eh
0x140039201  jmp     loc_1400390B9
0x140039206  xor     ebx, ebx
0x140039208  mov     rcx, [rsp+68h+hKey]; hKey
0x140039210  test    rcx, rcx
0x140039213  jz      short loc_14003921B
0x140039215  call    cs:__imp_RegCloseKey
0x14003921b  mov     eax, ebx
0x14003921d  mov     rbx, [rsp+68h+arg_8]
0x140039222  add     rsp, 60h
0x140039226  pop     rdi
0x140039227  retn
```
