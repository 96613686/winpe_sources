# CCertManager::CreateCertUpdateEvent(void)

- ea: `0x1800135a0`
- end: `0x1800136a4`
- name: `?CreateCertUpdateEvent@CCertManager@@AEAAJXZ`
- size: `260`
- prototype: `__int64 __fastcall(CCertManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002a298`

## callees

- `0x180003f30`
- `0x1800135a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800135ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001362c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800135ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001362c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013655`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013655`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001361f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001361f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013691`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013691`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800135e2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800135e2`

## string_xrefs

- `0x18001360e`: `Local\TS Certificate Update Event`
- `0x180013673`: `CCertManager::CreateCertUpdateEvent`
- `0x180013605`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed: 0x%x in %s`
- `0x18001366c`: `CreateEvent(TS_CERT_UPDATE_EVENT) failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCertManager::CreateCertUpdateEvent(CCertManager *this)
{
  signed int LastError; // eax
  signed int v3; // ebx
  signed int v4; // eax
  void *v5; // rcx
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+20h] [rbp-28h] BYREF
  ULONG v8; // [rsp+58h] [rbp+10h] BYREF

  *(_QWORD *)&EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  v8 = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:SYG:SYD:(A;;GA;;;SY)(A;;0x0002;;;S-1-5-80-446051430-1559341753-4161941529-1950928533-810483104)",
          1u,
          &EventAttributes.lpSecurityDescriptor,
          &v8) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 < 0 )
    {
      _DbgPrintMessage(
        8,
        "ConvertStringSecurityDescriptorToSecurityDescriptor failed: 0x%x in %s",
        (unsigned int)v3,
        "CCertManager::CreateCertUpdateEvent");
      goto LABEL_13;
    }
  }
  *((_QWORD *)this + 200) = CreateEventW(&EventAttributes, 0, 0, L"Local\\TS Certificate Update Event");
  v4 = GetLastError();
  v3 = v4;
  if ( v4 > 0 )
    v3 = (unsigned __int16)v4 | 0x80070000;
  v5 = (void *)*((_QWORD *)this + 200);
  if ( v5 && v3 == -2147024713 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 200) = 0;
  }
  else if ( v3 >= 0 )
  {
    goto LABEL_13;
  }
  _DbgPrintMessage(
    8,
    "CreateEvent(TS_CERT_UPDATE_EVENT) failed: 0x%x in %s",
    (unsigned int)v3,
    "CCertManager::CreateCertUpdateEvent");
LABEL_13:
  if ( EventAttributes.lpSecurityDescriptor )
    LocalFree(EventAttributes.lpSecurityDescriptor);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800135a0  mov     rax, rsp
0x1800135a3  mov     [rax+8], rbx
0x1800135a7  push    rdi
0x1800135a8  sub     rsp, 40h
0x1800135ac  mov     rdi, rcx
0x1800135af  mov     qword ptr [rax-28h], 18h
0x1800135b7  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;;GA;;;SY)(A;;0x0002;;;S-1-"...
0x1800135be  mov     qword ptr [rax-20h], 0
0x1800135c6  lea     r9, [rax+10h]; SecurityDescriptorSize
0x1800135ca  mov     qword ptr [rax-18h], 0
0x1800135d2  lea     r8, [rax-20h]; SecurityDescriptor
0x1800135d6  mov     dword ptr [rax+10h], 0
0x1800135dd  mov     edx, 1; StringSDRevision
0x1800135e2  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800135e8  test    eax, eax
0x1800135ea  jnz     short loc_18001360E
0x1800135ec  call    cs:__imp_GetLastError
0x1800135f2  mov     ebx, eax
0x1800135f4  test    eax, eax
0x1800135f6  jle     short loc_180013601
0x1800135f8  movzx   ebx, ax
0x1800135fb  or      ebx, 80070000h
0x180013601  test    ebx, ebx
0x180013603  jns     short loc_18001360E
0x180013605  lea     rdx, aConvertstrings_6; "ConvertStringSecurityDescriptorToSecuri"...
0x18001360c  jmp     short loc_180013673
0x18001360e  lea     r9, Name; "Local\\TS Certificate Update Event"
0x180013615  xor     r8d, r8d; bInitialState
0x180013618  xor     edx, edx; bManualReset
0x18001361a  lea     rcx, [rsp+48h+EventAttributes]; lpEventAttributes
0x18001361f  call    cs:__imp_CreateEventW
0x180013625  mov     [rdi+640h], rax
0x18001362c  call    cs:__imp_GetLastError
0x180013632  mov     ebx, eax
0x180013634  test    eax, eax
0x180013636  jle     short loc_180013641
0x180013638  movzx   ebx, ax
0x18001363b  or      ebx, 80070000h
0x180013641  mov     rcx, [rdi+640h]; hObject
0x180013648  test    rcx, rcx
0x18001364b  jz      short loc_180013668
0x18001364d  cmp     ebx, 800700B7h
0x180013653  jnz     short loc_180013668
0x180013655  call    cs:__imp_CloseHandle
0x18001365b  mov     qword ptr [rdi+640h], 0
0x180013666  jmp     short loc_18001366C
0x180013668  test    ebx, ebx
0x18001366a  jns     short loc_180013687
0x18001366c  lea     rdx, aCreateeventTsC; "CreateEvent(TS_CERT_UPDATE_EVENT) faile"...
0x180013673  lea     r9, aCcertmanagerCr; "CCertManager::CreateCertUpdateEvent"
0x18001367a  mov     r8d, ebx
0x18001367d  mov     ecx, 8; int
0x180013682  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013687  mov     rcx, [rsp+48h+EventAttributes.lpSecurityDescriptor]; hMem
0x18001368c  test    rcx, rcx
0x18001368f  jz      short loc_180013697
0x180013691  call    cs:__imp_LocalFree
0x180013697  mov     eax, ebx
0x180013699  mov     rbx, [rsp+48h+arg_0]
0x18001369e  add     rsp, 40h
0x1800136a2  pop     rdi
0x1800136a3  retn
```
