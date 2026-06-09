# GetUserSIDString(ushort *)

- ea: `0x1800c473c`
- end: `0x1800c491a`
- name: `?GetUserSIDString@@YAJPEAG@Z`
- size: `478`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c4990`
- `0x1800c5120`

## callees

- `0x18000c840`
- `0x18000d44c`
- `0x18001a608`
- `0x1800c473c`
- `0x1800c5674`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c47b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c482d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c47b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c482d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c48d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c48d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c48e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c48e5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c4801`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c4801`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c47a5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c47a5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c481d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c481d`

## string_xrefs

- `0x1800c48c1`: `GetUserSIDString`

## pseudocode

```c
__int64 __fastcall GetUserSIDString(unsigned __int16 *a1)
{
  int v2; // edx
  int v3; // ecx
  signed int LastError; // eax
  signed int v5; // ebx
  PSID v6; // rbx
  signed int v7; // eax
  int v8; // r9d
  int v9; // eax
  int v10; // edx
  int v11; // ecx
  DWORD ReturnLength; // [rsp+30h] [rbp-138h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-130h] BYREF
  PSID TokenInformation[34]; // [rsp+40h] [rbp-128h] BYREF

  StringSid = 0;
  memset_0(TokenInformation, 0, 0x104u);
  ReturnLength = 260;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenUser, TokenInformation, 0x104u, &ReturnLength) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
        McTemplateU0sqq_EventWriteTransfer(v3, v2, (unsigned int)"GetUserSIDString", 34, v5);
      goto LABEL_24;
    }
  }
  v6 = TokenInformation[0];
  if ( !TokenInformation[0] || !IsValidSid(TokenInformation[0]) )
  {
    v5 = -2147467259;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      goto LABEL_24;
    v8 = 37;
    goto LABEL_23;
  }
  if ( !ConvertSidToStringSidW(v6, &StringSid) )
  {
    v7 = GetLastError();
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    if ( v5 < 0 )
    {
      if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
        McTemplateU0sqq_EventWriteTransfer(v3, v2, (unsigned int)"GetUserSIDString", 39, v5);
      goto LABEL_24;
    }
  }
  if ( !StringSid )
  {
    v5 = -2147467259;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      goto LABEL_24;
    v8 = (_DWORD)StringSid + 40;
LABEL_23:
    McTemplateU0sqq_EventWriteTransfer(v3, v2, (unsigned int)"GetUserSIDString", v8, 5);
    goto LABEL_24;
  }
  v9 = StringCchCopyW(a1, 0x104u, StringSid);
  v5 = v9;
  if ( v9 < 0 && (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    McTemplateU0sqq_EventWriteTransfer(v11, v10, (unsigned int)"GetUserSIDString", 42, v9);
LABEL_24:
  CloseHandle((HANDLE)0xFFFFFFFFFFFFFFFCLL);
  LocalFree(StringSid);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800c473c  mov     [rsp+arg_8], rbx
0x1800c4741  mov     [rsp+arg_10], rdi
0x1800c4746  push    r14
0x1800c4748  sub     rsp, 160h
0x1800c474f  mov     rax, cs:__security_cookie
0x1800c4756  xor     rax, rsp
0x1800c4759  mov     [rsp+168h+var_18], rax
0x1800c4761  mov     rdi, rcx
0x1800c4764  mov     [rsp+168h+StringSid], 0
0x1800c476d  mov     r14d, 104h
0x1800c4773  lea     rcx, [rsp+168h+TokenInformation]; void *
0x1800c4778  mov     r8d, r14d; Size
0x1800c477b  xor     edx, edx; Val
0x1800c477d  call    memset_0
0x1800c4782  lea     rax, [rsp+168h+var_138]
0x1800c4787  mov     [rsp+168h+var_138], r14d
0x1800c478c  mov     r9d, r14d; TokenInformationLength
0x1800c478f  mov     [rsp+168h+ReturnLength], rax; ReturnLength
0x1800c4794  lea     r8, [rsp+168h+TokenInformation]; TokenInformation
0x1800c4799  mov     edx, 1; TokenInformationClass
0x1800c479e  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x1800c47a5  call    cs:__imp_GetTokenInformation
0x1800c47ac  nop     dword ptr [rax+rax+00h]
0x1800c47b1  test    eax, eax
0x1800c47b3  jnz     short loc_1800C47F0
0x1800c47b5  call    cs:__imp_GetLastError
0x1800c47bc  nop     dword ptr [rax+rax+00h]
0x1800c47c1  mov     ebx, eax
0x1800c47c3  test    eax, eax
0x1800c47c5  jle     short loc_1800C47D0
0x1800c47c7  movzx   ebx, ax
0x1800c47ca  or      ebx, 80070000h
0x1800c47d0  test    ebx, ebx
0x1800c47d2  jns     short loc_1800C47F0
0x1800c47d4  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800c47db  jz      loc_1800C48CD
0x1800c47e1  mov     dword ptr [rsp+168h+ReturnLength], ebx
0x1800c47e5  mov     r9d, 22h ; '"'
0x1800c47eb  jmp     loc_1800C48C1
0x1800c47f0  mov     rbx, [rsp+168h+TokenInformation]
0x1800c47f5  test    rbx, rbx
0x1800c47f8  jz      loc_1800C48A5
0x1800c47fe  mov     rcx, rbx; pSid
0x1800c4801  call    cs:__imp_IsValidSid
0x1800c4808  nop     dword ptr [rax+rax+00h]
0x1800c480d  test    eax, eax
0x1800c480f  jz      loc_1800C48A5
0x1800c4815  lea     rdx, [rsp+168h+StringSid]; StringSid
0x1800c481a  mov     rcx, rbx; Sid
0x1800c481d  call    cs:__imp_ConvertSidToStringSidW
0x1800c4824  nop     dword ptr [rax+rax+00h]
0x1800c4829  test    eax, eax
0x1800c482b  jnz     short loc_1800C4861
0x1800c482d  call    cs:__imp_GetLastError
0x1800c4834  nop     dword ptr [rax+rax+00h]
0x1800c4839  mov     ebx, eax
0x1800c483b  test    eax, eax
0x1800c483d  jle     short loc_1800C4848
0x1800c483f  movzx   ebx, ax
0x1800c4842  or      ebx, 80070000h
0x1800c4848  test    ebx, ebx
0x1800c484a  jns     short loc_1800C4861
0x1800c484c  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800c4853  jz      short loc_1800C48CD
0x1800c4855  mov     dword ptr [rsp+168h+ReturnLength], ebx
0x1800c4859  mov     r9d, 27h ; '''
0x1800c485f  jmp     short loc_1800C48C1
0x1800c4861  mov     r8, [rsp+168h+StringSid]; unsigned __int16 *
0x1800c4866  test    r8, r8
0x1800c4869  jnz     short loc_1800C487F
0x1800c486b  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800c4872  mov     ebx, 80004005h
0x1800c4877  jz      short loc_1800C48CD
0x1800c4879  lea     r9d, [r8+28h]
0x1800c487d  jmp     short loc_1800C48B9
0x1800c487f  mov     rdx, r14; unsigned __int64
0x1800c4882  mov     rcx, rdi; unsigned __int16 *
0x1800c4885  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c488a  mov     ebx, eax
0x1800c488c  test    eax, eax
0x1800c488e  jns     short loc_1800C48CD
0x1800c4890  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800c4897  jz      short loc_1800C48CD
0x1800c4899  mov     dword ptr [rsp+168h+ReturnLength], eax
0x1800c489d  mov     r9d, 2Ah ; '*'
0x1800c48a3  jmp     short loc_1800C48C1
0x1800c48a5  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800c48ac  mov     ebx, 80004005h
0x1800c48b1  jz      short loc_1800C48CD
0x1800c48b3  mov     r9d, 25h ; '%'
0x1800c48b9  mov     dword ptr [rsp+168h+ReturnLength], 80004005h
0x1800c48c1  lea     r8, aGetusersidstri; "GetUserSIDString"
0x1800c48c8  call    McTemplateU0sqq_EventWriteTransfer
0x1800c48cd  mov     rcx, 0FFFFFFFFFFFFFFFCh; hObject
0x1800c48d4  call    cs:__imp_CloseHandle
0x1800c48db  nop     dword ptr [rax+rax+00h]
0x1800c48e0  mov     rcx, [rsp+168h+StringSid]; hMem
0x1800c48e5  call    cs:__imp_LocalFree
0x1800c48ec  nop     dword ptr [rax+rax+00h]
0x1800c48f1  mov     eax, ebx
0x1800c48f3  mov     rcx, [rsp+168h+var_18]
0x1800c48fb  xor     rcx, rsp; StackCookie
0x1800c48fe  call    __security_check_cookie
0x1800c4903  lea     r11, [rsp+168h+var_8]
0x1800c490b  mov     rbx, [r11+18h]
0x1800c490f  mov     rdi, [r11+20h]
0x1800c4913  mov     rsp, r11
0x1800c4916  pop     r14
0x1800c4918  retn
```
