# GetUserSidFromToken(void *,void * *)

- ea: `0x18000867c`
- end: `0x180008829`
- name: `?GetUserSidFromToken@@YAJPEAXPEAPEAX@Z`
- size: `429`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180008484`

## callees

- `0x180002068`
- `0x18000867c`
- `0x18000a290`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800087f3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008809`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800087f3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008809`
- `ADVAPI32!GetTokenInformation` at `0x1800086bc`
- `ADVAPI32!GetTokenInformation` at `0x180008769`
- `ADVAPI32!GetTokenInformation` at `0x1800086bc`
- `ADVAPI32!GetTokenInformation` at `0x180008769`
- `ADVAPI32!GetLengthSid` at `0x180008799`
- `ADVAPI32!GetLengthSid` at `0x180008799`
- `ADVAPI32!CopySid` at `0x1800087c5`
- `ADVAPI32!CopySid` at `0x1800087c5`
- `KERNEL32!GetLastError` at `0x180008702`
- `KERNEL32!GetLastError` at `0x180008713`
- `KERNEL32!GetLastError` at `0x180008779`
- `KERNEL32!GetLastError` at `0x1800087d5`
- `KERNEL32!GetLastError` at `0x180008702`
- `KERNEL32!GetLastError` at `0x180008713`
- `KERNEL32!GetLastError` at `0x180008779`
- `KERNEL32!GetLastError` at `0x1800087d5`

## pseudocode

```c
__int64 __fastcall GetUserSidFromToken(HANDLE TokenHandle, void **a2)
{
  unsigned int v4; // ebx
  signed int v5; // eax
  PSID *v6; // rdi
  signed int v7; // eax
  DWORD LengthSid; // ebx
  void *v9; // rax
  void *v10; // rsi
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF

  if ( !TokenHandle || !a2 )
    return 2147942487LL;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids);
    return (unsigned int)-2147418113;
  }
  else if ( GetLastError() == 122 )
  {
    v6 = (PSID *)operator new[](TokenInformationLength);
    if ( v6 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
      {
        LengthSid = GetLengthSid(*v6);
        v9 = operator new[](LengthSid);
        v10 = v9;
        if ( v9 )
        {
          if ( CopySid(LengthSid, v9, *v6) )
          {
            v4 = 0;
            *a2 = v10;
          }
          else
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
            operator delete[](v10);
          }
        }
        else
        {
          v4 = -2147024882;
        }
      }
      else
      {
        v7 = GetLastError();
        v4 = v7;
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
      }
      operator delete[](v6);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v5 = GetLastError();
    v4 = v5;
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x18000867c  push    rbx
0x18000867e  push    rsi
0x18000867f  push    rdi
0x180008680  push    r14
0x180008682  sub     rsp, 38h
0x180008686  mov     r14, rdx
0x180008689  mov     rbx, rcx
0x18000868c  test    rcx, rcx
0x18000868f  jz      loc_180008819
0x180008695  test    rdx, rdx
0x180008698  jz      loc_180008819
0x18000869e  xor     r9d, r9d; TokenInformationLength
0x1800086a1  mov     [rsp+58h+TokenInformationLength], 0
0x1800086a9  lea     rax, [rsp+58h+TokenInformationLength]
0x1800086ae  xor     r8d, r8d; TokenInformation
0x1800086b1  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800086b6  lea     esi, [r9+1]
0x1800086ba  mov     edx, esi; TokenInformationClass
0x1800086bc  call    cs:__imp_GetTokenInformation
0x1800086c3  nop     dword ptr [rax+rax+00h]
0x1800086c8  test    eax, eax
0x1800086ca  jz      short loc_180008702
0x1800086cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086d3  lea     rax, WPP_GLOBAL_Control
0x1800086da  cmp     rcx, rax
0x1800086dd  jz      short loc_1800086F8
0x1800086df  test    byte ptr [rcx+1Ch], 4
0x1800086e3  jz      short loc_1800086F8
0x1800086e5  mov     rcx, [rcx+10h]
0x1800086e9  lea     edx, [rsi+5Bh]
0x1800086ec  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x1800086f3  call    WPP_SF_
0x1800086f8  mov     ebx, 8000FFFFh
0x1800086fd  jmp     loc_180008815
0x180008702  call    cs:__imp_GetLastError
0x180008709  nop     dword ptr [rax+rax+00h]
0x18000870e  cmp     eax, 7Ah ; 'z'
0x180008711  jz      short loc_180008737
0x180008713  call    cs:__imp_GetLastError
0x18000871a  nop     dword ptr [rax+rax+00h]
0x18000871f  mov     ebx, eax
0x180008721  test    eax, eax
0x180008723  jle     loc_180008815
0x180008729  movzx   ebx, ax
0x18000872c  or      ebx, 80070000h
0x180008732  jmp     loc_180008815
0x180008737  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x18000873b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008740  mov     rdi, rax
0x180008743  test    rax, rax
0x180008746  jnz     short loc_180008752
0x180008748  mov     ebx, 8007000Eh
0x18000874d  jmp     loc_180008815
0x180008752  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180008757  lea     rax, [rsp+58h+TokenInformationLength]
0x18000875c  mov     r8, rdi; TokenInformation
0x18000875f  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180008764  mov     edx, esi; TokenInformationClass
0x180008766  mov     rcx, rbx; TokenHandle
0x180008769  call    cs:__imp_GetTokenInformation
0x180008770  nop     dword ptr [rax+rax+00h]
0x180008775  test    eax, eax
0x180008777  jnz     short loc_180008796
0x180008779  call    cs:__imp_GetLastError
0x180008780  nop     dword ptr [rax+rax+00h]
0x180008785  mov     ebx, eax
0x180008787  test    eax, eax
0x180008789  jle     short loc_180008806
0x18000878b  movzx   ebx, ax
0x18000878e  or      ebx, 80070000h
0x180008794  jmp     short loc_180008806
0x180008796  mov     rcx, [rdi]; pSid
0x180008799  call    cs:__imp_GetLengthSid
0x1800087a0  nop     dword ptr [rax+rax+00h]
0x1800087a5  mov     ecx, eax; unsigned __int64
0x1800087a7  mov     ebx, eax
0x1800087a9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800087ae  mov     rsi, rax
0x1800087b1  test    rax, rax
0x1800087b4  jnz     short loc_1800087BD
0x1800087b6  mov     ebx, 8007000Eh
0x1800087bb  jmp     short loc_180008806
0x1800087bd  mov     r8, [rdi]; pSourceSid
0x1800087c0  mov     rdx, rsi; pDestinationSid
0x1800087c3  mov     ecx, ebx; nDestinationSidLength
0x1800087c5  call    cs:__imp_CopySid
0x1800087cc  nop     dword ptr [rax+rax+00h]
0x1800087d1  test    eax, eax
0x1800087d3  jnz     short loc_180008801
0x1800087d5  call    cs:__imp_GetLastError
0x1800087dc  nop     dword ptr [rax+rax+00h]
0x1800087e1  mov     ebx, eax
0x1800087e3  test    eax, eax
0x1800087e5  jle     short loc_1800087F0
0x1800087e7  movzx   ebx, ax
0x1800087ea  or      ebx, 80070000h
0x1800087f0  mov     rcx, rsi
0x1800087f3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800087fa  nop     dword ptr [rax+rax+00h]
0x1800087ff  jmp     short loc_180008806
0x180008801  xor     ebx, ebx
0x180008803  mov     [r14], rsi
0x180008806  mov     rcx, rdi
0x180008809  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008810  nop     dword ptr [rax+rax+00h]
0x180008815  mov     eax, ebx
0x180008817  jmp     short loc_18000881E
0x180008819  mov     eax, 80070057h
0x18000881e  add     rsp, 38h
0x180008822  pop     r14
0x180008824  pop     rdi
0x180008825  pop     rsi
0x180008826  pop     rbx
0x180008827  retn
```
