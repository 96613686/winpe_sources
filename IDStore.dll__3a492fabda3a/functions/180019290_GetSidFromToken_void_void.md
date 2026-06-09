# GetSidFromToken(void *,void * *)

- ea: `0x180019290`
- end: `0x1800193a0`
- name: `?GetSidFromToken@@YAKPEAXPEAPEAX@Z`
- size: `272`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800193a8`

## callees

- `0x18000fb96`
- `0x1800144b4`
- `0x180019290`
- `0x180019722`
- `0x180019750`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019349`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019349`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019358`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019358`
- `ntdll!RtlNtStatusToDosError` at `0x180019309`
- `ntdll!RtlNtStatusToDosError` at `0x180019309`
- `ntdll!NtQueryInformationToken` at `0x1800192fd`
- `ntdll!NtQueryInformationToken` at `0x1800192fd`

## pseudocode

```c
__int64 __fastcall GetSidFromToken(HANDLE TokenHandle, void **a2)
{
  ULONG v4; // ebx
  int InformationToken; // eax
  SIZE_T LengthSid; // rbx
  HLOCAL v7; // rax
  ULONG ReturnLength[4]; // [rsp+30h] [rbp-88h] BYREF
  const void *TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  ReturnLength[0] = 0;
  memset_0(TokenInformation, 0, 0x58u);
  if ( a2 )
  {
    *a2 = 0;
    InformationToken = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x58u, ReturnLength);
    if ( InformationToken >= 0 )
    {
      LengthSid = GetLengthSid((PSID)TokenInformation[0]);
      v7 = LocalAlloc(0x40u, LengthSid);
      *a2 = v7;
      if ( v7 )
      {
        memcpy_0(v7, TokenInformation[0], LengthSid);
        return 0;
      }
      else
      {
        return 8;
      }
    }
    else
    {
      v4 = RtlNtStatusToDosError(InformationToken);
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a8931f2c81c1305f250c9a1b52db8649_Traceguids, v4);
      }
    }
  }
  else
  {
    return 87;
  }
  return v4;
}

```

## disassembly

```asm
0x180019290  mov     [rsp+arg_10], rbx
0x180019295  push    rdi
0x180019296  sub     rsp, 0B0h
0x18001929d  mov     rax, cs:__security_cookie
0x1800192a4  xor     rax, rsp
0x1800192a7  mov     [rsp+0B8h+var_18], rax
0x1800192af  mov     rdi, rdx
0x1800192b2  mov     [rsp+0B8h+var_88], 0
0x1800192ba  xor     edx, edx; Val
0x1800192bc  mov     rbx, rcx
0x1800192bf  lea     rcx, [rsp+0B8h+TokenInformation]; void *
0x1800192c4  lea     r8d, [rdx+58h]; Size
0x1800192c8  call    memset_0
0x1800192cd  test    rdi, rdi
0x1800192d0  jnz     short loc_1800192DA
0x1800192d2  lea     ebx, [rdi+57h]
0x1800192d5  jmp     loc_18001937D
0x1800192da  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800192e0  mov     qword ptr [rdi], 0
0x1800192e7  lea     rax, [rsp+0B8h+var_88]
0x1800192ec  mov     rcx, rbx; TokenHandle
0x1800192ef  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x1800192f4  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x1800192f9  lea     edx, [r9-57h]; TokenInformationClass
0x1800192fd  call    cs:__imp_NtQueryInformationToken
0x180019303  test    eax, eax
0x180019305  jns     short loc_180019344
0x180019307  mov     ecx, eax; Status
0x180019309  call    cs:__imp_RtlNtStatusToDosError
0x18001930f  mov     ebx, eax
0x180019311  mov     rcx, cs:WPP_GLOBAL_Control
0x180019318  lea     rax, WPP_GLOBAL_Control
0x18001931f  cmp     rcx, rax
0x180019322  jz      short loc_18001937D
0x180019324  test    byte ptr [rcx+1Ch], 4
0x180019328  jz      short loc_18001937D
0x18001932a  mov     rcx, [rcx+10h]
0x18001932e  lea     r8, WPP_a8931f2c81c1305f250c9a1b52db8649_Traceguids
0x180019335  mov     edx, 0Ah
0x18001933a  mov     r9d, ebx
0x18001933d  call    WPP_SF_d
0x180019342  jmp     short loc_18001937D
0x180019344  mov     rcx, [rsp+0B8h+TokenInformation]; pSid
0x180019349  call    cs:__imp_GetLengthSid
0x18001934f  mov     edx, eax; uBytes
0x180019351  mov     ecx, 40h ; '@'; uFlags
0x180019356  mov     ebx, eax
0x180019358  call    cs:__imp_LocalAlloc
0x18001935e  mov     [rdi], rax
0x180019361  test    rax, rax
0x180019364  jnz     short loc_18001936B
0x180019366  lea     ebx, [rax+8]
0x180019369  jmp     short loc_18001937D
0x18001936b  mov     rdx, [rsp+0B8h+TokenInformation]; Src
0x180019370  mov     r8, rbx; Size
0x180019373  mov     rcx, rax; void *
0x180019376  call    memcpy_0
0x18001937b  xor     ebx, ebx
0x18001937d  mov     eax, ebx
0x18001937f  mov     rcx, [rsp+0B8h+var_18]
0x180019387  xor     rcx, rsp; StackCookie
0x18001938a  call    __security_check_cookie
0x18001938f  mov     rbx, [rsp+0B8h+arg_10]
0x180019397  add     rsp, 0B0h
0x18001939e  pop     rdi
0x18001939f  retn
```
