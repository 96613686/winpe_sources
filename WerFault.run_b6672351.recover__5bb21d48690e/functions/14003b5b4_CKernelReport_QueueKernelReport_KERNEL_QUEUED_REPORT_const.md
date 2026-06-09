# CKernelReport::QueueKernelReport(KERNEL_QUEUED_REPORT const *)

- ea: `0x14003b5b4`
- end: `0x14003b77b`
- name: `?QueueKernelReport@CKernelReport@@AEAAJPEBUKERNEL_QUEUED_REPORT@@@Z`
- size: `455`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this, const struct KERNEL_QUEUED_REPORT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140038274`
- `0x14003be5c`

## callees

- `0x14000551c`
- `0x1400372dc`
- `0x140038bd8`
- `0x14003b5b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14003b690`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14003b690`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003b761`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003b761`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14003b724`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14003b724`

## string_xrefs

- `0x14003b741`: `RegSetValueEx failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    v7 = 517;
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
    v7 = 523;
    goto LABEL_3;
  }
  v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  v5 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    v6 = "RegQueryInfoKey failed";
    v7 = 551;
    goto LABEL_3;
  }
  if ( cValues < 0x40 )
  {
    v9 = RegSetValueExW(hKey, *(LPCWSTR *)a2, 0, 3u, (const BYTE *)a2 + 32, 0x1Cu);
    v5 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      v6 = "RegSetValueEx failed";
      v7 = 575;
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
      (void *)0x22F,
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
0x14003b5b4  mov     rax, rsp
0x14003b5b7  mov     [rax+10h], rbx
0x14003b5bb  mov     [rax+8], rcx
0x14003b5bf  push    rdi
0x14003b5c0  sub     rsp, 60h
0x14003b5c4  mov     rdi, rdx
0x14003b5c7  mov     qword ptr [rax+18h], 0
0x14003b5cf  mov     dword ptr [rax+8], 0
0x14003b5d6  lea     rcx, [rax+18h]
0x14003b5da  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003b5df  mov     rdx, rax; HKEY *
0x14003b5e2  call    ?EnsureKernelQueueRegkeyExists@CKernelReport@@AEAAJPEAPEAUHKEY__@@@Z; CKernelReport::EnsureKernelQueueRegkeyExists(HKEY__ * *)
0x14003b5e7  mov     ebx, eax
0x14003b5e9  test    eax, eax
0x14003b5eb  jns     short loc_14003B61F
0x14003b5ed  lea     rax, aEnsurekernelqu_0; "EnsureKernelQueueRegkeyExists failed"
0x14003b5f4  mov     edx, 205h; void *
0x14003b5f9  mov     [rsp+68h+lpcbMaxSubKeyLen], rax; int
0x14003b5fe  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003b605  lea     r9, aCkernelreportQ; "CKernelReport::QueueKernelReport"
0x14003b60c  mov     dword ptr [rsp+68h+lpcSubKeys], ebx; wil::details *
0x14003b610  mov     rcx, [rsp+68h]; this
0x14003b615  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003b61a  jmp     loc_14003B754
0x14003b61f  mov     rcx, [rsp+68h+hKey]; hKey
0x14003b627  test    rcx, rcx
0x14003b62a  jnz     short loc_14003B63F
0x14003b62c  mov     ebx, 80070006h
0x14003b631  lea     rax, aEnsurekernelqu; "EnsureKernelQueueRegkeyExists returned "...
0x14003b638  mov     edx, 20Bh
0x14003b63d  jmp     short loc_14003B5F9
0x14003b63f  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x14003b648  mov     [rsp+68h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x14003b651  mov     [rsp+68h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x14003b65a  mov     [rsp+68h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x14003b663  lea     rax, [rsp+68h+cValues]
0x14003b668  mov     [rsp+68h+lpcValues], rax; lpcValues
0x14003b66d  mov     [rsp+68h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x14003b676  mov     [rsp+68h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x14003b67f  mov     [rsp+68h+lpcSubKeys], 0; lpcSubKeys
0x14003b688  xor     r9d, r9d; lpReserved
0x14003b68b  xor     r8d, r8d; lpcchClass
0x14003b68e  xor     edx, edx; lpClass
0x14003b690  call    cs:__imp_RegQueryInfoKeyW
0x14003b697  nop     dword ptr [rax+rax+00h]
0x14003b69c  mov     ebx, eax
0x14003b69e  test    eax, eax
0x14003b6a0  jz      short loc_14003B6BE
0x14003b6a2  jle     short loc_14003B6AD
0x14003b6a4  movzx   ebx, ax
0x14003b6a7  or      ebx, 80070000h
0x14003b6ad  lea     rax, aRegqueryinfoke_1; "RegQueryInfoKey failed"
0x14003b6b4  mov     edx, 227h
0x14003b6b9  jmp     loc_14003B5F9
0x14003b6be  mov     eax, [rsp+68h+cValues]
0x14003b6c2  cmp     eax, 40h ; '@'
0x14003b6c5  jb      short loc_14003B6FF
0x14003b6c7  mov     ebx, 80070503h
0x14003b6cc  mov     rcx, [rsp+68h]; this
0x14003b6d1  mov     dword ptr [rsp+68h+lpcbMaxClassLen], eax; char *
0x14003b6d5  lea     rax, aTooManyKernelF; "Too many kernel faults in the queue: %u"
0x14003b6dc  mov     [rsp+68h+lpcbMaxSubKeyLen], rax; int
0x14003b6e1  mov     dword ptr [rsp+68h+lpcSubKeys], ebx; wil::details *
0x14003b6e5  lea     r9, aCkernelreportQ; "CKernelReport::QueueKernelReport"
0x14003b6ec  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003b6f3  mov     edx, 22Fh; void *
0x14003b6f8  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003b6fd  jmp     short loc_14003B754
0x14003b6ff  lea     rax, [rdi+20h]
0x14003b703  mov     dword ptr [rsp+68h+lpcbMaxSubKeyLen], 1Ch; cbData
0x14003b70b  mov     [rsp+68h+lpcSubKeys], rax; lpData
0x14003b710  mov     r9d, 3; dwType
0x14003b716  xor     r8d, r8d; Reserved
0x14003b719  mov     rdx, [rdi]; lpValueName
0x14003b71c  mov     rcx, [rsp+68h+hKey]; hKey
0x14003b724  call    cs:__imp_RegSetValueExW
0x14003b72b  nop     dword ptr [rax+rax+00h]
0x14003b730  mov     ebx, eax
0x14003b732  test    eax, eax
0x14003b734  jz      short loc_14003B752
0x14003b736  jle     short loc_14003B741
0x14003b738  movzx   ebx, ax
0x14003b73b  or      ebx, 80070000h
0x14003b741  lea     rax, aRegsetvalueexF; "RegSetValueEx failed"
0x14003b748  mov     edx, 23Fh
0x14003b74d  jmp     loc_14003B5F9
0x14003b752  xor     ebx, ebx
0x14003b754  mov     rcx, [rsp+68h+hKey]; hKey
0x14003b75c  test    rcx, rcx
0x14003b75f  jz      short loc_14003B76D
0x14003b761  call    cs:__imp_RegCloseKey
0x14003b768  nop     dword ptr [rax+rax+00h]
0x14003b76d  mov     eax, ebx
0x14003b76f  mov     rbx, [rsp+68h+arg_8]
0x14003b774  add     rsp, 60h
0x14003b778  pop     rdi
0x14003b779  retn
```
