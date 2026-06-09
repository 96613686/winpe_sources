# GetGlobalCountersName(CWxString *)

- ea: `0x1800b0f30`
- end: `0x1800b1146`
- name: `?GetGlobalCountersName@@YAJPEAVCWxString@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(struct CWxString *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b26b8`

## callees

- `0x18001eaec`
- `0x18002482c`
- `0x1800701d0`
- `0x1800b0f30`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e1790`
- `0x1801e1b00`
- `0x1801e3c24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b0fc8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b0fc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b0fb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b0fb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b10e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b10e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b111d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b111d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b1015`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b1015`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b1051`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b1051`

## string_xrefs

- `0x1800b109b`: `Local\windows_webcache_counters_{9B6AB5B3-91BC-4097-835C-EA2DEC95E9CC}_`

## pseudocode

```c
__int64 __fastcall GetGlobalCountersName(struct CWxString *this)
{
  HANDLE CurrentProcess; // rax
  __int64 v3; // rcx
  int v4; // eax
  signed int v5; // ebx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  int LastError; // eax
  const unsigned __int16 *v10; // r8
  _WORD *v11; // rcx
  LPWSTR StringSid; // [rsp+38h] [rbp-31h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-21h] BYREF
  PSID TokenInformation[12]; // [rsp+50h] [rbp-19h] BYREF

  TokenHandle = 0;
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  StringSid = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF_q(1038, 10, &WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, this);
  if ( this )
    CWxString::Empty(this);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
    {
      if ( ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
      {
        v10 = StringSid;
        if ( *((_DWORD *)this + 2) )
        {
          v11 = *(_WORD **)this;
          *((_DWORD *)this + 2) = 0;
          *v11 = 0;
        }
        v5 = CWxString::Append(this, L"Local\\windows_webcache_counters_{9B6AB5B3-91BC-4097-835C-EA2DEC95E9CC}_", v10);
        if ( v5 >= 0 && (BYTE1(xmmword_180266B60) & 0x40) != 0 )
          WPP_SF_S(1038, 11, &WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, *(_QWORD *)this);
      }
      else
      {
        LastError = WxGetLastError(v8);
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 >= 0 )
          v5 = -2147418113;
      }
    }
    else
    {
      v7 = WxGetLastError(v6);
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147418113;
    }
  }
  else
  {
    v4 = WxGetLastError(v3);
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147418113;
  }
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF_d(1038, 12, &WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, (unsigned int)v5);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800b0f30  mov     [rsp-8+arg_8], rbx
0x1800b0f35  mov     [rsp-8+arg_10], rdi
0x1800b0f3a  push    rbp
0x1800b0f3b  lea     rbp, [rsp-57h]
0x1800b0f40  sub     rsp, 0C0h
0x1800b0f47  mov     rax, cs:__security_cookie
0x1800b0f4e  xor     rax, rsp
0x1800b0f51  mov     [rbp+57h+var_10], rax
0x1800b0f55  mov     rdi, rcx
0x1800b0f58  mov     [rbp+57h+var_8C], 0
0x1800b0f5f  mov     ebx, 58h ; 'X'
0x1800b0f64  mov     [rbp+57h+TokenHandle], 0
0x1800b0f6c  mov     r8d, ebx; Size
0x1800b0f6f  lea     rcx, [rbp+57h+TokenInformation]; void *
0x1800b0f73  xor     edx, edx; Val
0x1800b0f75  call    memset_0
0x1800b0f7a  mov     [rbp+57h+var_80], 0
0x1800b0f81  mov     [rbp+57h+StringSid], 0
0x1800b0f89  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b0f90  jz      short loc_1800B0FA9
0x1800b0f92  lea     edx, [rbx-4Eh]
0x1800b0f95  mov     ecx, 40Eh
0x1800b0f9a  mov     r9, rdi
0x1800b0f9d  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1800b0fa4  call    WPP_SF_q
0x1800b0fa9  test    rdi, rdi
0x1800b0fac  jz      short loc_1800B0FB6
0x1800b0fae  mov     rcx, rdi; this
0x1800b0fb1  call    ?Empty@CWxString@@QEAAXXZ; CWxString::Empty(void)
0x1800b0fb6  call    cs:__imp_GetCurrentProcess
0x1800b0fbc  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800b0fc0  mov     edx, 20008h; DesiredAccess
0x1800b0fc5  mov     rcx, rax; ProcessHandle
0x1800b0fc8  call    cs:__imp_OpenProcessToken
0x1800b0fce  test    eax, eax
0x1800b0fd0  jnz     short loc_1800B0FFC
0x1800b0fd2  call    WxGetLastError
0x1800b0fd7  mov     ebx, eax
0x1800b0fd9  test    eax, eax
0x1800b0fdb  jle     short loc_1800B0FE6
0x1800b0fdd  movzx   ebx, ax
0x1800b0fe0  or      ebx, 80070000h
0x1800b0fe6  test    ebx, ebx
0x1800b0fe8  mov     [rbp+57h+var_8C], 44h ; 'D'
0x1800b0fef  mov     eax, 8000FFFFh
0x1800b0ff4  cmovns  ebx, eax
0x1800b0ff7  jmp     loc_1800B10DB
0x1800b0ffc  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800b1000  lea     rax, [rbp+57h+var_80]
0x1800b1004  mov     r9d, ebx; TokenInformationLength
0x1800b1007  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x1800b100c  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800b1010  mov     edx, 1; TokenInformationClass
0x1800b1015  call    cs:__imp_GetTokenInformation
0x1800b101b  test    eax, eax
0x1800b101d  jnz     short loc_1800B1049
0x1800b101f  call    WxGetLastError
0x1800b1024  mov     ebx, eax
0x1800b1026  test    eax, eax
0x1800b1028  jle     short loc_1800B1033
0x1800b102a  movzx   ebx, ax
0x1800b102d  or      ebx, 80070000h
0x1800b1033  test    ebx, ebx
0x1800b1035  mov     [rbp+57h+var_8C], 45h ; 'E'
0x1800b103c  mov     eax, 8000FFFFh
0x1800b1041  cmovns  ebx, eax
0x1800b1044  jmp     loc_1800B10DB
0x1800b1049  mov     rcx, [rbp+57h+TokenInformation]; Sid
0x1800b104d  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800b1051  call    cs:__imp_ConvertSidToStringSidW
0x1800b1057  test    eax, eax
0x1800b1059  jnz     short loc_1800B1082
0x1800b105b  call    WxGetLastError
0x1800b1060  mov     ebx, eax
0x1800b1062  test    eax, eax
0x1800b1064  jle     short loc_1800B106F
0x1800b1066  movzx   ebx, ax
0x1800b1069  or      ebx, 80070000h
0x1800b106f  test    ebx, ebx
0x1800b1071  mov     [rbp+57h+var_8C], 47h ; 'G'
0x1800b1078  mov     eax, 8000FFFFh
0x1800b107d  cmovns  ebx, eax
0x1800b1080  jmp     short loc_1800B10DB
0x1800b1082  cmp     dword ptr [rdi+8], 0
0x1800b1086  mov     r8, [rbp+57h+StringSid]; unsigned __int16 *
0x1800b108a  jz      short loc_1800B109B
0x1800b108c  mov     rcx, [rdi]
0x1800b108f  xor     eax, eax
0x1800b1091  mov     dword ptr [rdi+8], 0
0x1800b1098  mov     [rcx], ax
0x1800b109b  lea     rdx, aLocalWindowsWe_0; "Local\\windows_webcache_counters_{9B6AB"...
0x1800b10a2  mov     rcx, rdi; this
0x1800b10a5  call    ?Append@CWxString@@QEAAJPEBG0@Z; CWxString::Append(ushort const *,ushort const *)
0x1800b10aa  mov     ebx, eax
0x1800b10ac  test    eax, eax
0x1800b10ae  jns     short loc_1800B10B9
0x1800b10b0  mov     [rbp+57h+var_8C], 49h ; 'I'
0x1800b10b7  jmp     short loc_1800B10DB
0x1800b10b9  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b10c0  jz      short loc_1800B10DB
0x1800b10c2  mov     r9, [rdi]
0x1800b10c5  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1800b10cc  mov     edx, 0Bh
0x1800b10d1  mov     ecx, 40Eh
0x1800b10d6  call    WPP_SF_S
0x1800b10db  mov     rcx, [rbp+57h+StringSid]; hMem
0x1800b10df  test    rcx, rcx
0x1800b10e2  jz      short loc_1800B10F2
0x1800b10e4  call    cs:__imp_LocalFree
0x1800b10ea  mov     [rbp+57h+StringSid], 0
0x1800b10f2  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b10f9  jz      short loc_1800B1114
0x1800b10fb  mov     edx, 0Ch
0x1800b1100  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1800b1107  mov     ecx, 40Eh
0x1800b110c  mov     r9d, ebx
0x1800b110f  call    WPP_SF_d
0x1800b1114  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800b1118  test    rcx, rcx
0x1800b111b  jz      short loc_1800B1123
0x1800b111d  call    cs:__imp_CloseHandle
0x1800b1123  mov     eax, ebx
0x1800b1125  mov     rcx, [rbp+57h+var_10]
0x1800b1129  xor     rcx, rsp; StackCookie
0x1800b112c  call    __security_check_cookie
0x1800b1131  lea     r11, [rsp+0C0h+var_s0]
0x1800b1139  mov     rbx, [r11+18h]
0x1800b113d  mov     rdi, [r11+20h]
0x1800b1141  mov     rsp, r11
0x1800b1144  pop     rbp
0x1800b1145  retn
```
