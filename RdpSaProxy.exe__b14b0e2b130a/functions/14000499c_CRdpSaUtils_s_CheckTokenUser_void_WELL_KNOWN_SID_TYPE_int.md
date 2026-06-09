# CRdpSaUtils::s_CheckTokenUser(void *,WELL_KNOWN_SID_TYPE,int *)

- ea: `0x14000499c`
- end: `0x140004c03`
- name: `?s_CheckTokenUser@CRdpSaUtils@@SAJPEAXW4WELL_KNOWN_SID_TYPE@@PEAH@Z`
- size: `615`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, WELL_KNOWN_SID_TYPE WellKnownSidType, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400035d8`

## callees

- `0x140002738`
- `0x1400027cc`
- `0x14000499c`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x1400049d8`
- `ADVAPI32!GetTokenInformation` at `0x140004ad8`
- `ADVAPI32!GetTokenInformation` at `0x1400049d8`
- `ADVAPI32!GetTokenInformation` at `0x140004ad8`
- `ADVAPI32!EqualSid` at `0x140004bd3`
- `ADVAPI32!EqualSid` at `0x140004bd3`
- `ADVAPI32!CreateWellKnownSid` at `0x140004b7f`
- `ADVAPI32!CreateWellKnownSid` at `0x140004b7f`
- `KERNEL32!LocalFree` at `0x140004bdf`
- `KERNEL32!LocalFree` at `0x140004be8`
- `KERNEL32!LocalFree` at `0x140004bdf`
- `KERNEL32!LocalFree` at `0x140004be8`
- `KERNEL32!LocalAlloc` at `0x140004a5d`
- `KERNEL32!LocalAlloc` at `0x140004b2d`
- `KERNEL32!LocalAlloc` at `0x140004a5d`
- `KERNEL32!LocalAlloc` at `0x140004b2d`
- `KERNEL32!GetLastError` at `0x1400049de`
- `KERNEL32!GetLastError` at `0x1400049eb`
- `KERNEL32!GetLastError` at `0x140004ae2`
- `KERNEL32!GetLastError` at `0x140004b89`
- `KERNEL32!GetLastError` at `0x1400049de`
- `KERNEL32!GetLastError` at `0x1400049eb`
- `KERNEL32!GetLastError` at `0x140004ae2`
- `KERNEL32!GetLastError` at `0x140004b89`

## pseudocode

```c
__int64 __fastcall CRdpSaUtils::s_CheckTokenUser(HANDLE TokenHandle, WELL_KNOWN_SID_TYPE WellKnownSidType, int *a3)
{
  void *v3; // rsi
  PSID *v7; // rdi
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rdx
  HLOCAL v13; // rax
  SIZE_T ReturnLength[5]; // [rsp+30h] [rbp-28h] BYREF
  SIZE_T uBytes; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  ReturnLength[0] = 68;
  LODWORD(uBytes) = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&uBytes);
  if ( GetLastError() == 122 )
  {
    v7 = (PSID *)LocalAlloc(0x40u, (unsigned int)uBytes);
    if ( v7 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenUser, v7, uBytes, (PDWORD)ReturnLength + 1) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_7;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 22;
        goto LABEL_6;
      }
      v13 = LocalAlloc(0x40u, LODWORD(ReturnLength[0]));
      v3 = v13;
      if ( v13 )
      {
        if ( CreateWellKnownSid(WellKnownSidType, 0, v13, (DWORD *)ReturnLength) )
        {
          LastError = 0;
          *a3 = EqualSid(*v7, v3);
          goto LABEL_35;
        }
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_7;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 24;
        goto LABEL_6;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_18:
        LastError = -2147024882;
        goto LABEL_35;
      }
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 23;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_18;
      }
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 21;
    }
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      WPP_65fbe6aa894c3c63a1856e9127b0f4a0_Traceguids,
      v11,
      -2147024882);
    goto LABEL_18;
  }
  v7 = 0;
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_7;
  }
  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
  v10 = 20;
LABEL_6:
  WPP_SF_Dd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v10,
    WPP_65fbe6aa894c3c63a1856e9127b0f4a0_Traceguids,
    CurrentThreadActivityIdPrefix,
    LastError);
LABEL_7:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError >= 0 )
    LastError = -2147467259;
LABEL_35:
  LocalFree(v7);
  LocalFree(v3);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14000499c  mov     rax, rsp
0x14000499f  mov     [rax+8], rbx
0x1400049a3  mov     [rax+10h], rbp
0x1400049a7  push    rsi
0x1400049a8  push    rdi
0x1400049a9  push    r14
0x1400049ab  sub     rsp, 40h
0x1400049af  xor     esi, esi
0x1400049b1  mov     dword ptr [rax-28h], 44h ; 'D'
0x1400049b8  mov     [rax+20h], esi
0x1400049bb  mov     r14, r8
0x1400049be  mov     [rax-24h], esi
0x1400049c1  lea     rax, [rax+20h]
0x1400049c5  mov     ebp, edx
0x1400049c7  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1400049cc  lea     edx, [rsi+1]; TokenInformationClass
0x1400049cf  xor     r9d, r9d; TokenInformationLength
0x1400049d2  xor     r8d, r8d; TokenInformation
0x1400049d5  mov     rbx, rcx
0x1400049d8  call    cs:__imp_GetTokenInformation
0x1400049de  call    cs:__imp_GetLastError
0x1400049e4  cmp     eax, 7Ah ; 'z'
0x1400049e7  jz      short loc_140004A54
0x1400049e9  xor     edi, edi
0x1400049eb  call    cs:__imp_GetLastError
0x1400049f1  mov     ebx, eax
0x1400049f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400049fa  lea     rax, WPP_GLOBAL_Control
0x140004a01  cmp     rcx, rax
0x140004a04  jz      short loc_140004A38
0x140004a06  test    byte ptr [rcx+1Ch], 8
0x140004a0a  jz      short loc_140004A38
0x140004a0c  cmp     byte ptr [rcx+19h], 2
0x140004a10  jb      short loc_140004A38
0x140004a12  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004a17  lea     edx, [rsi+14h]
0x140004a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a21  lea     r8, WPP_65fbe6aa894c3c63a1856e9127b0f4a0_Traceguids
0x140004a28  mov     r9d, eax
0x140004a2b  mov     dword ptr [rsp+58h+ReturnLength], ebx
0x140004a2f  mov     rcx, [rcx+10h]
0x140004a33  call    WPP_SF_Dd
0x140004a38  test    ebx, ebx
0x140004a3a  jle     short loc_140004A45
0x140004a3c  movzx   ebx, bx
0x140004a3f  or      ebx, 80070000h
0x140004a45  test    ebx, ebx
0x140004a47  mov     eax, 80004005h
0x140004a4c  cmovns  ebx, eax
0x140004a4f  jmp     loc_140004BDC
0x140004a54  mov     edx, dword ptr [rsp+58h+uBytes]; uBytes
0x140004a58  mov     ecx, 40h ; '@'; uFlags
0x140004a5d  call    cs:__imp_LocalAlloc
0x140004a63  mov     rdi, rax
0x140004a66  test    rax, rax
0x140004a69  jnz     short loc_140004ABE
0x140004a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a72  lea     rax, WPP_GLOBAL_Control
0x140004a79  cmp     rcx, rax
0x140004a7c  jz      short loc_140004AB4
0x140004a7e  test    byte ptr [rcx+1Ch], 8
0x140004a82  jz      short loc_140004AB4
0x140004a84  cmp     byte ptr [rcx+19h], 2
0x140004a88  jb      short loc_140004AB4
0x140004a8a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004a8f  lea     edx, [rdi+15h]
0x140004a92  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a99  lea     r8, WPP_65fbe6aa894c3c63a1856e9127b0f4a0_Traceguids
0x140004aa0  mov     r9d, eax
0x140004aa3  mov     dword ptr [rsp+58h+ReturnLength], 8007000Eh
0x140004aab  mov     rcx, [rcx+10h]
0x140004aaf  call    WPP_SF_Dd
0x140004ab4  mov     ebx, 8007000Eh
0x140004ab9  jmp     loc_140004BDC
0x140004abe  mov     r9d, dword ptr [rsp+58h+uBytes]; TokenInformationLength
0x140004ac3  lea     rax, [rsp+58h+var_28+4]
0x140004ac8  mov     r8, rdi; TokenInformation
0x140004acb  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x140004ad0  mov     edx, 1; TokenInformationClass
0x140004ad5  mov     rcx, rbx; TokenHandle
0x140004ad8  call    cs:__imp_GetTokenInformation
0x140004ade  test    eax, eax
0x140004ae0  jnz     short loc_140004B24
0x140004ae2  call    cs:__imp_GetLastError
0x140004ae8  mov     ebx, eax
0x140004aea  mov     rcx, cs:WPP_GLOBAL_Control
0x140004af1  lea     rax, WPP_GLOBAL_Control
0x140004af8  cmp     rcx, rax
0x140004afb  jz      loc_140004A38
0x140004b01  test    byte ptr [rcx+1Ch], 8
0x140004b05  jz      loc_140004A38
0x140004b0b  cmp     byte ptr [rcx+19h], 2
0x140004b0f  jb      loc_140004A38
0x140004b15  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004b1a  mov     edx, 16h
0x140004b1f  jmp     loc_140004A1A
0x140004b24  mov     edx, dword ptr [rsp+58h+var_28]; uBytes
0x140004b28  mov     ecx, 40h ; '@'; uFlags
0x140004b2d  call    cs:__imp_LocalAlloc
0x140004b33  mov     rsi, rax
0x140004b36  test    rax, rax
0x140004b39  jnz     short loc_140004B73
0x140004b3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b42  lea     rax, WPP_GLOBAL_Control
0x140004b49  cmp     rcx, rax
0x140004b4c  jz      loc_140004AB4
0x140004b52  test    byte ptr [rcx+1Ch], 8
0x140004b56  jz      loc_140004AB4
0x140004b5c  cmp     byte ptr [rcx+19h], 2
0x140004b60  jb      loc_140004AB4
0x140004b66  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004b6b  lea     edx, [rsi+17h]
0x140004b6e  jmp     loc_140004A92
0x140004b73  lea     r9, [rsp+58h+var_28]; cbSid
0x140004b78  mov     r8, rsi; pSid
0x140004b7b  xor     edx, edx; DomainSid
0x140004b7d  mov     ecx, ebp; WellKnownSidType
0x140004b7f  call    cs:__imp_CreateWellKnownSid
0x140004b85  test    eax, eax
0x140004b87  jnz     short loc_140004BCB
0x140004b89  call    cs:__imp_GetLastError
0x140004b8f  mov     ebx, eax
0x140004b91  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b98  lea     rax, WPP_GLOBAL_Control
0x140004b9f  cmp     rcx, rax
0x140004ba2  jz      loc_140004A38
0x140004ba8  test    byte ptr [rcx+1Ch], 8
0x140004bac  jz      loc_140004A38
0x140004bb2  cmp     byte ptr [rcx+19h], 2
0x140004bb6  jb      loc_140004A38
0x140004bbc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004bc1  mov     edx, 18h
0x140004bc6  jmp     loc_140004A1A
0x140004bcb  mov     rcx, [rdi]; pSid1
0x140004bce  xor     ebx, ebx
0x140004bd0  mov     rdx, rsi; pSid2
0x140004bd3  call    cs:__imp_EqualSid
0x140004bd9  mov     [r14], eax
0x140004bdc  mov     rcx, rdi; hMem
0x140004bdf  call    cs:__imp_LocalFree
0x140004be5  mov     rcx, rsi; hMem
0x140004be8  call    cs:__imp_LocalFree
0x140004bee  mov     rbp, [rsp+58h+arg_8]
0x140004bf3  mov     eax, ebx
0x140004bf5  mov     rbx, [rsp+58h+arg_0]
0x140004bfa  add     rsp, 40h
0x140004bfe  pop     r14
0x140004c00  pop     rdi
0x140004c01  pop     rsi
0x140004c02  retn
```
