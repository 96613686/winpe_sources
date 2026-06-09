# SipcSignalFactory::CreateClientEvents(SipcPrivateNamespace const &,void * *,void * *)

- ea: `0x180027040`
- end: `0x18002720d`
- name: `?CreateClientEvents@SipcSignalFactory@@SAJAEBVSipcPrivateNamespace@@PEAPEAX1@Z`
- size: `461`
- prototype: `__int64 __fastcall(const struct SipcPrivateNamespace *, void **, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180026d6c`
- `0x18002a900`

## callees

- `0x180027040`
- `0x18004c8e0`

## import_xrefs

- `ntdll!swprintf_s` at `0x180027120`
- `ntdll!swprintf_s` at `0x180027173`
- `ntdll!swprintf_s` at `0x180027120`
- `ntdll!swprintf_s` at `0x180027173`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002713b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002718d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002713b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002718d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800271c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800271c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002719e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002719e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800270d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800271e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800270d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800271e4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180027094`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180027094`

## pseudocode

```c
__int64 __fastcall SipcSignalFactory::CreateClientEvents(const struct SipcPrivateNamespace *a1, void **a2, void **a3)
{
  signed int LastError; // eax
  unsigned int v7; // edi
  HANDLE v9; // rbx
  HANDLE v10; // rax
  signed int v11; // eax
  PSECURITY_DESCRIPTOR v12; // rcx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-D0h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[56]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Name[56]; // [rsp+C0h] [rbp-40h] BYREF

  *a2 = 0;
  *a3 = 0;
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;WD)", 1u, &SecurityDescriptor, 0)
    || (EventAttributes.lpSecurityDescriptor = SecurityDescriptor,
        *(_QWORD *)&EventAttributes.nLength = 24,
        *(_QWORD *)&EventAttributes.bInheritHandle = 0,
        swprintf_s(Buffer, 0x33u, L"%s\\%s", (char *)a1 + 8, L"ClientSignal"),
        (v9 = CreateEventW(&EventAttributes, 0, 0, Buffer)) == 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = -2147418113;
    if ( LastError < 0 )
      v7 = LastError;
    goto LABEL_6;
  }
  swprintf_s(Name, 0x33u, L"%s\\%s", (char *)a1 + 8, L"ServerSignal");
  v10 = CreateEventW(&EventAttributes, 0, 0, Name);
  if ( !v10 )
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    v7 = -2147418113;
    if ( v11 < 0 )
      v7 = v11;
    CloseHandle(v9);
LABEL_6:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return v7;
  }
  v12 = SecurityDescriptor;
  *a2 = v9;
  *a3 = v10;
  if ( v12 )
    LocalFree(v12);
  return 0;
}

```

## disassembly

```asm
0x180027040  push    rbp
0x180027042  push    rbx
0x180027043  push    rsi
0x180027044  push    rdi
0x180027045  push    r14
0x180027047  lea     rbp, [rsp-40h]
0x18002704c  sub     rsp, 140h
0x180027053  mov     rax, cs:__security_cookie
0x18002705a  xor     rax, rsp
0x18002705d  mov     [rbp+60h+var_30], rax
0x180027061  mov     qword ptr [rdx], 0
0x180027068  xor     r9d, r9d; SecurityDescriptorSize
0x18002706b  mov     rsi, r8
0x18002706e  mov     qword ptr [r8], 0
0x180027075  mov     rdi, rdx
0x180027078  mov     [rsp+160h+SecurityDescriptor], 0
0x180027081  mov     r14, rcx
0x180027084  lea     r8, [rsp+160h+SecurityDescriptor]; SecurityDescriptor
0x180027089  lea     edx, [r9+1]; StringSDRevision
0x18002708d  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;WD)"
0x180027094  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002709b  nop     dword ptr [rax+rax+00h]
0x1800270a0  test    eax, eax
0x1800270a2  jnz     short loc_1800270E3
0x1800270a4  call    cs:__imp_GetLastError
0x1800270ab  nop     dword ptr [rax+rax+00h]
0x1800270b0  test    eax, eax
0x1800270b2  jle     short loc_1800270BC
0x1800270b4  movzx   eax, ax
0x1800270b7  or      eax, 80070000h
0x1800270bc  test    eax, eax
0x1800270be  mov     edi, 8000FFFFh
0x1800270c3  cmovs   edi, eax
0x1800270c6  mov     rcx, [rsp+160h+SecurityDescriptor]; hMem
0x1800270cb  test    rcx, rcx
0x1800270ce  jz      short loc_1800270DC
0x1800270d0  call    cs:__imp_LocalFree
0x1800270d7  nop     dword ptr [rax+rax+00h]
0x1800270dc  mov     eax, edi
0x1800270de  jmp     loc_1800271F2
0x1800270e3  mov     rax, [rsp+160h+SecurityDescriptor]
0x1800270e8  lea     r9, [r14+8]
0x1800270ec  mov     [rsp+160h+EventAttributes.lpSecurityDescriptor], rax
0x1800270f1  lea     r8, aSS; "%s\\%s"
0x1800270f8  lea     rax, ?ClientSignalName@SipcSignalFactory@@0QBGB; "ClientSignal"
0x1800270ff  mov     qword ptr [rsp+160h+EventAttributes.nLength], 18h
0x180027108  mov     edx, 33h ; '3'; BufferCount
0x18002710d  mov     [rsp+160h+var_140], rax
0x180027112  lea     rcx, [rsp+160h+Buffer]; Buffer
0x180027117  mov     qword ptr [rsp+160h+EventAttributes.bInheritHandle], 0
0x180027120  call    cs:__imp_swprintf_s
0x180027127  nop     dword ptr [rax+rax+00h]
0x18002712c  lea     r9, [rsp+160h+Buffer]; lpName
0x180027131  xor     r8d, r8d; bInitialState
0x180027134  xor     edx, edx; bManualReset
0x180027136  lea     rcx, [rsp+160h+EventAttributes]; lpEventAttributes
0x18002713b  call    cs:__imp_CreateEventW
0x180027142  nop     dword ptr [rax+rax+00h]
0x180027147  mov     rbx, rax
0x18002714a  test    rax, rax
0x18002714d  jz      loc_1800270A4
0x180027153  lea     rax, ?ServerSignalName@SipcSignalFactory@@0QBGB; "ServerSignal"
0x18002715a  mov     edx, 33h ; '3'; BufferCount
0x18002715f  lea     r9, [r14+8]
0x180027163  mov     [rsp+160h+var_140], rax
0x180027168  lea     r8, aSS; "%s\\%s"
0x18002716f  lea     rcx, [rbp+60h+Name]; Buffer
0x180027173  call    cs:__imp_swprintf_s
0x18002717a  nop     dword ptr [rax+rax+00h]
0x18002717f  lea     r9, [rbp+60h+Name]; lpName
0x180027183  xor     r8d, r8d; bInitialState
0x180027186  xor     edx, edx; bManualReset
0x180027188  lea     rcx, [rsp+160h+EventAttributes]; lpEventAttributes
0x18002718d  call    cs:__imp_CreateEventW
0x180027194  nop     dword ptr [rax+rax+00h]
0x180027199  test    rax, rax
0x18002719c  jnz     short loc_1800271D4
0x18002719e  call    cs:__imp_GetLastError
0x1800271a5  nop     dword ptr [rax+rax+00h]
0x1800271aa  test    eax, eax
0x1800271ac  jle     short loc_1800271B6
0x1800271ae  movzx   eax, ax
0x1800271b1  or      eax, 80070000h
0x1800271b6  test    eax, eax
0x1800271b8  mov     edi, 8000FFFFh
0x1800271bd  mov     rcx, rbx; hObject
0x1800271c0  cmovs   edi, eax
0x1800271c3  call    cs:__imp_CloseHandle
0x1800271ca  nop     dword ptr [rax+rax+00h]
0x1800271cf  jmp     loc_1800270C6
0x1800271d4  mov     rcx, [rsp+160h+SecurityDescriptor]; hMem
0x1800271d9  mov     [rdi], rbx
0x1800271dc  mov     [rsi], rax
0x1800271df  test    rcx, rcx
0x1800271e2  jz      short loc_1800271F0
0x1800271e4  call    cs:__imp_LocalFree
0x1800271eb  nop     dword ptr [rax+rax+00h]
0x1800271f0  xor     eax, eax
0x1800271f2  mov     rcx, [rbp+60h+var_30]
0x1800271f6  xor     rcx, rsp; StackCookie
0x1800271f9  call    __security_check_cookie
0x1800271fe  add     rsp, 140h
0x180027205  pop     r14
0x180027207  pop     rdi
0x180027208  pop     rsi
0x180027209  pop     rbx
0x18002720a  pop     rbp
0x18002720b  retn
```
