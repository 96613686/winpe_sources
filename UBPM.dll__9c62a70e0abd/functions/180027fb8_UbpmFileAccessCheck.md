# UbpmFileAccessCheck

- ea: `0x180027fb8`
- end: `0x1800281f1`
- name: `UbpmFileAccessCheck`
- size: `569`
- prototype: `__int64 __fastcall(HANDLE ClientToken)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013c90`
- `0x18001eaf4`

## callees

- `0x1800150c0`
- `0x180027fb8`
- `0x1800351ec`
- `0x180040260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180028048`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800280ff`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180028048`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800280ff`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800281a6`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800281a6`
- `ntdll!RtlFreeHeap` at `0x1800281e0`
- `ntdll!RtlFreeHeap` at `0x1800281e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002810f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002810f`

## pseudocode

```c
__int64 __fastcall UbpmFileAccessCheck(HANDLE ClientToken, __int64 a2)
{
  DWORD LastError; // ebx
  void *v6; // rdi
  DWORD v7; // r8d
  DWORD nLengthNeeded; // [rsp+40h] [rbp-40h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp-3Ch] BYREF
  DWORD GrantedAccess; // [rsp+48h] [rbp-38h] BYREF
  DWORD PrivilegeSetLength; // [rsp+4Ch] [rbp-34h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+50h] [rbp-30h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-20h] BYREF

  LastError = 0;
  PrivilegeSetLength = 20;
  nLengthNeeded = 0;
  AccessStatus = 0;
  GrantedAccess = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GenericMapping = 0;
  if ( a2 )
  {
    if ( GetFileSecurityW(*(LPCWSTR *)a2, 7u, 0, 0, &nLengthNeeded) || (LastError = GetLastError(), LastError == 122) )
    {
      v6 = UbpmAlloc(nLengthNeeded);
      if ( v6 )
      {
        if ( GetFileSecurityW(*(LPCWSTR *)a2, 7u, v6, nLengthNeeded, &nLengthNeeded) )
        {
          v7 = *(_DWORD *)(a2 + 8);
          GenericMapping.GenericRead = 1179785;
          GenericMapping.GenericWrite = 1179926;
          GenericMapping.GenericExecute = 1179808;
          GenericMapping.GenericAll = 2032127;
          if ( !AccessCheck(
                  v6,
                  ClientToken,
                  v7,
                  &GenericMapping,
                  &PrivilegeSet,
                  &PrivilegeSetLength,
                  &GrantedAccess,
                  &AccessStatus)
            || !AccessStatus
            || (LastError = 0, (GrantedAccess & *(_DWORD *)(a2 + 8)) != *(_DWORD *)(a2 + 8)) )
          {
            LastError = 5;
          }
        }
        else
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              WPP_134408c016563692a0776b6ad2359b4f_Traceguids,
              LastError);
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, 0);
        return 0;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180027fb8  mov     [rsp-18h+arg_10], rbx
0x180027fbd  mov     [rsp-18h+arg_18], rsi
0x180027fc2  push    rbp
0x180027fc3  push    rdi
0x180027fc4  push    r14
0x180027fc6  mov     rbp, rsp
0x180027fc9  sub     rsp, 80h
0x180027fd0  mov     rax, cs:__security_cookie
0x180027fd7  xor     rax, rsp
0x180027fda  mov     [rbp+var_8], rax
0x180027fde  xor     ebx, ebx
0x180027fe0  mov     [rbp+var_34], 14h
0x180027fe7  xor     eax, eax
0x180027fe9  mov     [rbp+nLengthNeeded], ebx
0x180027fec  mov     [rbp+var_3C], ebx
0x180027fef  xorps   xmm0, xmm0
0x180027ff2  mov     [rbp+var_38], ebx
0x180027ff5  mov     rsi, rdx
0x180027ff8  mov     [rbp+PrivilegeSet.Privilege.Attributes], eax
0x180027ffb  mov     r14, rcx
0x180027ffe  movups  xmmword ptr [rbp+PrivilegeSet.PrivilegeCount], xmm0
0x180028002  movups  xmmword ptr [rbp+GenericMapping.GenericRead], xmm0
0x180028006  test    rdx, rdx
0x180028009  jnz     short loc_180028032
0x18002800b  mov     eax, ebx
0x18002800d  mov     rcx, [rbp+var_8]
0x180028011  xor     rcx, rsp; StackCookie
0x180028014  call    __security_check_cookie
0x180028019  lea     r11, [rsp+80h+var_s0]
0x180028021  mov     rbx, [r11+30h]
0x180028025  mov     rsi, [r11+38h]
0x180028029  mov     rsp, r11
0x18002802c  pop     r14
0x18002802e  pop     rdi
0x18002802f  pop     rbp
0x180028030  retn
0x180028032  mov     rcx, [rsi]; lpFileName
0x180028035  lea     rax, [rbp+nLengthNeeded]
0x180028039  xor     r9d, r9d; nLength
0x18002803c  mov     [rsp+80h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180028041  xor     r8d, r8d; pSecurityDescriptor
0x180028044  lea     edx, [r9+7]; RequestedInformation
0x180028048  call    cs:__imp_GetFileSecurityW
0x18002804f  nop     dword ptr [rax+rax+00h]
0x180028054  test    eax, eax
0x180028056  jnz     short loc_1800280A1
0x180028058  call    cs:__imp_GetLastError
0x18002805f  nop     dword ptr [rax+rax+00h]
0x180028064  mov     ebx, eax
0x180028066  cmp     eax, 7Ah ; 'z'
0x180028069  jz      short loc_1800280A1
0x18002806b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028072  lea     rax, WPP_GLOBAL_Control
0x180028079  cmp     rcx, rax
0x18002807c  jz      short loc_18002800B
0x18002807e  test    byte ptr [rcx+1Ch], 1
0x180028082  jz      short loc_18002800B
0x180028084  mov     rcx, [rcx+10h]
0x180028088  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x18002808f  mov     edx, 13h
0x180028094  mov     r9d, ebx
0x180028097  call    WPP_SF_d
0x18002809c  jmp     loc_18002800B
0x1800280a1  mov     ecx, [rbp+nLengthNeeded]; Size
0x1800280a4  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x1800280a9  mov     rdi, rax
0x1800280ac  test    rax, rax
0x1800280af  jnz     short loc_1800280E7
0x1800280b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280b8  lea     rax, WPP_GLOBAL_Control
0x1800280bf  cmp     rcx, rax
0x1800280c2  jz      short loc_1800280E0
0x1800280c4  test    byte ptr [rcx+1Ch], 1
0x1800280c8  jz      short loc_1800280E0
0x1800280ca  mov     rcx, [rcx+10h]
0x1800280ce  lea     edx, [rdi+14h]
0x1800280d1  xor     r9d, r9d
0x1800280d4  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x1800280db  call    WPP_SF_d
0x1800280e0  xor     ebx, ebx
0x1800280e2  jmp     loc_18002800B
0x1800280e7  mov     r9d, [rbp+nLengthNeeded]; nLength
0x1800280eb  lea     rax, [rbp+nLengthNeeded]
0x1800280ef  mov     rcx, [rsi]; lpFileName
0x1800280f2  mov     r8, rdi; pSecurityDescriptor
0x1800280f5  mov     edx, 7; RequestedInformation
0x1800280fa  mov     [rsp+80h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800280ff  call    cs:__imp_GetFileSecurityW
0x180028106  nop     dword ptr [rax+rax+00h]
0x18002810b  test    eax, eax
0x18002810d  jnz     short loc_180028158
0x18002810f  call    cs:__imp_GetLastError
0x180028116  nop     dword ptr [rax+rax+00h]
0x18002811b  mov     ebx, eax
0x18002811d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028124  lea     rax, WPP_GLOBAL_Control
0x18002812b  cmp     rcx, rax
0x18002812e  jz      loc_1800281CE
0x180028134  test    byte ptr [rcx+1Ch], 1
0x180028138  jz      loc_1800281CE
0x18002813e  mov     rcx, [rcx+10h]
0x180028142  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180028149  mov     edx, 15h
0x18002814e  mov     r9d, ebx
0x180028151  call    WPP_SF_d
0x180028156  jmp     short loc_1800281CE
0x180028158  mov     r8d, [rsi+8]; DesiredAccess
0x18002815c  lea     rax, [rbp+var_3C]
0x180028160  mov     [rsp+80h+AccessStatus], rax; AccessStatus
0x180028165  lea     r9, [rbp+GenericMapping]; GenericMapping
0x180028169  lea     rax, [rbp+var_38]
0x18002816d  mov     [rbp+GenericMapping.GenericRead], 120089h
0x180028174  mov     [rsp+80h+GrantedAccess], rax; GrantedAccess
0x180028179  mov     rdx, r14; ClientToken
0x18002817c  lea     rax, [rbp+var_34]
0x180028180  mov     [rbp+GenericMapping.GenericWrite], 120116h
0x180028187  mov     [rsp+80h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18002818c  mov     rcx, rdi; pSecurityDescriptor
0x18002818f  lea     rax, [rbp+PrivilegeSet]
0x180028193  mov     [rbp+GenericMapping.GenericExecute], 1200A0h
0x18002819a  mov     [rsp+80h+lpnLengthNeeded], rax; PrivilegeSet
0x18002819f  mov     [rbp+GenericMapping.GenericAll], 1F01FFh
0x1800281a6  call    cs:__imp_AccessCheck
0x1800281ad  nop     dword ptr [rax+rax+00h]
0x1800281b2  test    eax, eax
0x1800281b4  jz      short loc_1800281C9
0x1800281b6  cmp     [rbp+var_3C], 0
0x1800281ba  jz      short loc_1800281C9
0x1800281bc  mov     eax, [rsi+8]
0x1800281bf  xor     ebx, ebx
0x1800281c1  and     eax, [rbp+var_38]
0x1800281c4  cmp     eax, [rsi+8]
0x1800281c7  jz      short loc_1800281CE
0x1800281c9  mov     ebx, 5
0x1800281ce  mov     rcx, gs:60h
0x1800281d7  mov     r8, rdi; P
0x1800281da  xor     edx, edx; Flags
0x1800281dc  mov     rcx, [rcx+30h]; HeapHandle
0x1800281e0  call    cs:__imp_RtlFreeHeap
0x1800281e7  nop     dword ptr [rax+rax+00h]
0x1800281ec  jmp     loc_18002800B
```
