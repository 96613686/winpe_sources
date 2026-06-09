# _IsSsoAppContainer

- ea: `0x1400042fc`
- end: `0x1400044ba`
- name: `_IsSsoAppContainer`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003b70`

## callees

- `0x140002c98`
- `0x1400042fc`
- `0x140012f60`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140004467`
- `msvcrt!_wcsnicmp` at `0x140004467`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140004341`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140004341`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140004353`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140004353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000435d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400043de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000435d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400043de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004482`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004482`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400043d4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400043d4`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerLookupMoniker` at `0x140004421`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerLookupMoniker` at `0x140004421`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerFreeMemory` at `0x140004491`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerFreeMemory` at `0x140004491`

## pseudocode

```c
__int64 __fastcall IsSsoAppContainer(_DWORD *a1)
{
  HANDLE CurrentProcess; // rax
  signed int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-21h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-19h] BYREF
  _QWORD TokenInformation[10]; // [rsp+50h] [rbp-9h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 76;
  String1 = 0;
  *a1 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    if ( GetTokenInformation(
           TokenHandle,
           TokenAppContainerSid,
           TokenInformation,
           TokenInformationLength,
           &TokenInformationLength) )
    {
      v4 = AppContainerLookupMoniker(TokenInformation[0], &String1);
      if ( (v4 & 0x80000000) == 0 )
      {
        if ( !_wcsnicmp(String1, L"microsoft.windows.authhost.sso", 0x1Eu) )
          *a1 = 1;
        v4 = 0;
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          v6 = 25;
          goto LABEL_8;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        v6 = 24;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v6 = 23;
LABEL_8:
      WPP_SF_d(v5[7], v6, WPP_d672079daa5c3533fef55dc4d0763d25_Traceguids, v4);
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( String1 )
    AppContainerFreeMemory();
  return v4;
}

```

## disassembly

```asm
0x1400042fc  mov     [rsp-8+arg_8], rbx
0x140004301  mov     [rsp-8+arg_10], rdi
0x140004306  push    rbp
0x140004307  lea     rbp, [rsp-57h]
0x14000430c  sub     rsp, 0B0h
0x140004313  mov     rax, cs:__security_cookie
0x14000431a  xor     rax, rsp
0x14000431d  mov     [rbp+57h+var_10], rax
0x140004321  mov     rdi, rcx
0x140004324  mov     [rbp+57h+TokenHandle], 0
0x14000432c  mov     [rbp+57h+TokenInformationLength], 4Ch ; 'L'
0x140004333  mov     [rbp+57h+String1], 0
0x14000433b  mov     dword ptr [rcx], 0
0x140004341  call    cs:__imp_GetCurrentProcess
0x140004347  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x14000434b  mov     edx, 8; DesiredAccess
0x140004350  mov     rcx, rax; ProcessHandle
0x140004353  call    cs:__imp_OpenProcessToken
0x140004359  test    eax, eax
0x14000435b  jnz     short loc_1400043BA
0x14000435d  call    cs:__imp_GetLastError
0x140004363  mov     ebx, eax
0x140004365  test    eax, eax
0x140004367  jle     short loc_140004372
0x140004369  movzx   ebx, ax
0x14000436c  or      ebx, 80070000h
0x140004372  mov     rcx, cs:WPP_GLOBAL_Control
0x140004379  lea     rax, WPP_GLOBAL_Control
0x140004380  cmp     rcx, rax
0x140004383  jz      loc_140004479
0x140004389  test    byte ptr [rcx+44h], 10h
0x14000438d  jz      loc_140004479
0x140004393  cmp     byte ptr [rcx+41h], 2
0x140004397  jb      loc_140004479
0x14000439d  mov     edx, 17h
0x1400043a2  mov     rcx, [rcx+38h]
0x1400043a6  lea     r8, WPP_d672079daa5c3533fef55dc4d0763d25_Traceguids
0x1400043ad  mov     r9d, ebx
0x1400043b0  call    WPP_SF_d
0x1400043b5  jmp     loc_140004479
0x1400043ba  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1400043be  lea     rax, [rbp+57h+TokenInformationLength]
0x1400043c2  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1400043c6  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1400043ca  mov     edx, 1Fh; TokenInformationClass
0x1400043cf  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1400043d4  call    cs:__imp_GetTokenInformation
0x1400043da  test    eax, eax
0x1400043dc  jnz     short loc_140004419
0x1400043de  call    cs:__imp_GetLastError
0x1400043e4  mov     ebx, eax
0x1400043e6  test    eax, eax
0x1400043e8  jle     short loc_1400043F3
0x1400043ea  movzx   ebx, ax
0x1400043ed  or      ebx, 80070000h
0x1400043f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400043fa  lea     rax, WPP_GLOBAL_Control
0x140004401  cmp     rcx, rax
0x140004404  jz      short loc_140004479
0x140004406  test    byte ptr [rcx+44h], 10h
0x14000440a  jz      short loc_140004479
0x14000440c  cmp     byte ptr [rcx+41h], 2
0x140004410  jb      short loc_140004479
0x140004412  mov     edx, 18h
0x140004417  jmp     short loc_1400043A2
0x140004419  mov     rcx, [rbp+57h+TokenInformation]
0x14000441d  lea     rdx, [rbp+57h+String1]
0x140004421  call    cs:__imp_AppContainerLookupMoniker
0x140004427  mov     ebx, eax
0x140004429  test    eax, eax
0x14000442b  jns     short loc_140004456
0x14000442d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004434  lea     rax, WPP_GLOBAL_Control
0x14000443b  cmp     rcx, rax
0x14000443e  jz      short loc_140004479
0x140004440  test    byte ptr [rcx+44h], 10h
0x140004444  jz      short loc_140004479
0x140004446  cmp     byte ptr [rcx+41h], 2
0x14000444a  jb      short loc_140004479
0x14000444c  mov     edx, 19h
0x140004451  jmp     loc_1400043A2
0x140004456  mov     rcx, [rbp+57h+String1]; String1
0x14000445a  lea     rdx, aMicrosoftWindo_0; "microsoft.windows.authhost.sso"
0x140004461  mov     r8d, 1Eh; MaxCount
0x140004467  call    cs:__imp__wcsnicmp
0x14000446d  test    eax, eax
0x14000446f  jnz     short loc_140004477
0x140004471  mov     dword ptr [rdi], 1
0x140004477  xor     ebx, ebx
0x140004479  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x14000447d  test    rcx, rcx
0x140004480  jz      short loc_140004488
0x140004482  call    cs:__imp_CloseHandle
0x140004488  mov     rcx, [rbp+57h+String1]
0x14000448c  test    rcx, rcx
0x14000448f  jz      short loc_140004497
0x140004491  call    cs:__imp_AppContainerFreeMemory
0x140004497  mov     eax, ebx
0x140004499  mov     rcx, [rbp+57h+var_10]
0x14000449d  xor     rcx, rsp; StackCookie
0x1400044a0  call    __security_check_cookie
0x1400044a5  lea     r11, [rsp+0B0h+var_s0]
0x1400044ad  mov     rbx, [r11+18h]
0x1400044b1  mov     rdi, [r11+20h]
0x1400044b5  mov     rsp, r11
0x1400044b8  pop     rbp
0x1400044b9  retn
```
