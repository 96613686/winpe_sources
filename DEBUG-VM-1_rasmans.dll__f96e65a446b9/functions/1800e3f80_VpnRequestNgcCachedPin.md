# VpnRequestNgcCachedPin

- ea: `0x1800e3f80`
- end: `0x1800e4417`
- name: `VpnRequestNgcCachedPin`
- size: `1175`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800584e0`

## callees

- `0x180005e34`
- `0x180005f1c`
- `0x1800a5770`
- `0x1800e1b9c`
- `0x1800e3f80`
- `0x1800e7206`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e4161`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e4161`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e4149`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e4149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e40ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e416b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e423a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e42c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e40ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e416b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e423a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e42c7`
- `RPCRT4!RpcImpersonateClient` at `0x1800e411f`
- `RPCRT4!RpcImpersonateClient` at `0x1800e411f`
- `RPCRT4!RpcRevertToSelf` at `0x1800e41b2`
- `RPCRT4!RpcRevertToSelf` at `0x1800e41ca`
- `RPCRT4!RpcRevertToSelf` at `0x1800e41b2`
- `RPCRT4!RpcRevertToSelf` at `0x1800e41ca`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800e40e3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800e40e3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e41a7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e41c2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e41a7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e41c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e3ff4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e404e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e3ff4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e404e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e4005`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e4060`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e4005`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e4060`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800e422e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800e42bb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800e422e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800e42bb`
- `ncrypt!NCryptGetProperty` at `0x1800e41f5`
- `ncrypt!NCryptGetProperty` at `0x1800e4357`
- `ncrypt!NCryptGetProperty` at `0x1800e41f5`
- `ncrypt!NCryptGetProperty` at `0x1800e4357`
- `ncrypt!NCryptSetProperty` at `0x1800e430c`
- `ncrypt!NCryptSetProperty` at `0x1800e430c`

## string_xrefs

- `0x1800e4305`: `PinCacheApplicationImage`
- `0x1800e41de`: `PinCacheApplicationTicket`
- `0x1800e4340`: `PinCacheApplicationTicket`
- `0x1800e4225`: `%windir%\System32\lsass.exe`
- `0x1800e42b1`: `%windir%\System32\lsass.exe`

## pseudocode

```c
__int64 __fastcall VpnRequestNgcCachedPin(__int64 a1, NCRYPT_HANDLE a2, void *a3, _QWORD *a4, NCRYPT_HANDLE **a5)
{
  HANDLE ProcessHeap; // rax
  LPVOID v10; // r13
  unsigned int v11; // ebx
  SECURITY_STATUS Property; // esi
  void *v13; // r15
  HANDLE v14; // rax
  NCRYPT_HANDLE *v15; // r14
  DWORD LastError; // edi
  struct _LIST_ENTRY *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  HANDLE CurrentThread; // rax
  struct _LIST_ENTRY *v21; // rcx
  __int64 v22; // rdx
  DWORD v23; // ebx
  DWORD v24; // ebp
  size_t v25; // rbx
  void *v26; // rax
  DWORD v27; // ebx
  DWORD cbOutput; // [rsp+30h] [rbp-58h] BYREF
  DWORD pcbResult[21]; // [rsp+34h] [rbp-54h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 37, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, a3);
  }
  cbOutput = 0;
  pcbResult[0] = 0;
  *a4 = 0;
  *a5 = 0;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 8u, 0x70u);
  if ( v10 )
  {
    Property = 0;
    v13 = 0;
    v14 = GetProcessHeap();
    v15 = (NCRYPT_HANDLE *)HeapAlloc(v14, 8u, 0x70u);
    if ( !v15 )
    {
      LastError = 14;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
LABEL_53:
        v11 = LastError;
        *a4 = v10;
        if ( v15 )
          *a5 = v15;
        if ( Property < 0 && !LastError )
        {
          v11 = (unsigned __int16)Property;
          if ( (Property & 0x1FFF0000) != 0x70000 )
            v11 = 13;
        }
        if ( v13 )
          MprCommonFree(v13);
        goto LABEL_61;
      }
      v18 = 39;
      goto LABEL_11;
    }
    memset_0(v10, 0, 0x70u);
    cbOutput = 90;
    *((_QWORD *)v10 + 12) = a1;
    memset_0(v15, 0, 0x70u);
    pcbResult[0] = 90;
    v15[12] = a2;
    if ( a3 )
    {
      LastError = 0;
      if ( !ImpersonateLoggedOnUser(a3) )
      {
        LastError = GetLastError();
        if ( LastError )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            goto LABEL_53;
          v18 = 40;
          goto LABEL_18;
        }
      }
    }
    else
    {
      LastError = RpcImpersonateClient(0);
      if ( LastError )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_53;
        v18 = 41;
        goto LABEL_18;
      }
    }
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, (PHANDLE)v10 + 13) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 42, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, LastError);
        if ( a3 )
          RevertToSelf();
        else
          RpcRevertToSelf();
        goto LABEL_53;
      }
    }
    if ( a3 )
      RevertToSelf();
    else
      RpcRevertToSelf();
    Property = NCryptGetProperty(
                 *((_QWORD *)v10 + 12),
                 L"PinCacheApplicationTicket",
                 (PBYTE)v10,
                 cbOutput,
                 &cbOutput,
                 0x40u);
    if ( Property < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_53;
      v22 = 43;
LABEL_52:
      WPP_SF_d(v21[1].Flink, v22, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, (unsigned int)Property);
      goto LABEL_53;
    }
    v23 = ExpandEnvironmentStringsW(L"%windir%\\System32\\lsass.exe", 0, 0);
    if ( v23 || (LastError = GetLastError()) == 0 )
    {
      v24 = v23 + 1;
      v25 = 2LL * (v23 + 1);
      v26 = (void *)VpnAlloc(v25);
      v13 = v26;
      if ( !v26 )
      {
        LastError = 14;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_53;
        v18 = 45;
LABEL_11:
        v19 = 14;
LABEL_12:
        WPP_SF_d(v17[1].Flink, v18, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, v19);
        goto LABEL_53;
      }
      memset_0(v26, 0, v25);
      v27 = ExpandEnvironmentStringsW(L"%windir%\\System32\\lsass.exe", (LPWSTR)v13, v24);
      if ( v27 || (LastError = GetLastError()) == 0 )
      {
        Property = NCryptSetProperty(v15[12], L"PinCacheApplicationImage", (PBYTE)v13, 2 * v27, 0);
        if ( Property >= 0 )
        {
          Property = NCryptGetProperty(
                       v15[12],
                       L"PinCacheApplicationTicket",
                       (PBYTE)v15,
                       pcbResult[0],
                       pcbResult,
                       0x40u);
          if ( Property >= 0 )
            goto LABEL_53;
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            goto LABEL_53;
          v22 = 48;
        }
        else
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            goto LABEL_53;
          v22 = 47;
        }
        goto LABEL_52;
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_53;
      v18 = 46;
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_53;
      v18 = 44;
    }
LABEL_18:
    v19 = LastError;
    goto LABEL_12;
  }
  v11 = 14;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v11;
  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 38, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, 14);
LABEL_61:
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 49, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x1800e3f80  mov     [rsp+arg_18], r9
0x1800e3f85  push    rbx
0x1800e3f86  push    rbp
0x1800e3f87  push    rsi
0x1800e3f88  push    rdi
0x1800e3f89  push    r12
0x1800e3f8b  push    r13
0x1800e3f8d  push    r14
0x1800e3f8f  push    r15
0x1800e3f91  sub     rsp, 48h
0x1800e3f95  mov     rsi, r9
0x1800e3f98  mov     rbp, r8
0x1800e3f9b  mov     rbx, rdx
0x1800e3f9e  mov     rdi, rcx
0x1800e3fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3fa8  lea     rax, WPP_GLOBAL_Control
0x1800e3faf  cmp     rcx, rax
0x1800e3fb2  jz      short loc_1800E3FD8
0x1800e3fb4  test    byte ptr [rcx+1Ch], 80h
0x1800e3fb8  jz      short loc_1800E3FD8
0x1800e3fba  cmp     byte ptr [rcx+19h], 6
0x1800e3fbe  jb      short loc_1800E3FD8
0x1800e3fc0  mov     rcx, [rcx+10h]
0x1800e3fc4  mov     r9, r8
0x1800e3fc7  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e3fce  mov     edx, 25h ; '%'
0x1800e3fd3  call    WPP_SF_q
0x1800e3fd8  mov     r12, [rsp+88h+arg_20]
0x1800e3fe0  xor     r14d, r14d
0x1800e3fe3  mov     [rsp+88h+cbOutput], r14d
0x1800e3fe8  mov     [rsp+88h+var_54], r14d
0x1800e3fed  mov     [rsi], r14
0x1800e3ff0  mov     [r12], r14
0x1800e3ff4  call    cs:__imp_GetProcessHeap
0x1800e3ffa  mov     rcx, rax; hHeap
0x1800e3ffd  lea     edx, [r14+8]; dwFlags
0x1800e4001  lea     r8d, [r14+70h]; dwBytes
0x1800e4005  call    cs:__imp_HeapAlloc
0x1800e400b  mov     r13, rax
0x1800e400e  test    rax, rax
0x1800e4011  jnz     short loc_1800E4048
0x1800e4013  lea     ebx, [rax+0Eh]
0x1800e4016  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e401d  lea     rax, WPP_GLOBAL_Control
0x1800e4024  cmp     rcx, rax
0x1800e4027  jz      loc_1800E4404
0x1800e402d  mov     rcx, [rcx+10h]
0x1800e4031  lea     edx, [rbx+18h]
0x1800e4034  mov     r9d, ebx
0x1800e4037  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e403e  call    WPP_SF_d
0x1800e4043  jmp     loc_1800E43CD
0x1800e4048  mov     esi, r14d
0x1800e404b  mov     r15, r14
0x1800e404e  call    cs:__imp_GetProcessHeap
0x1800e4054  mov     edx, 8; dwFlags
0x1800e4059  mov     rcx, rax; hHeap
0x1800e405c  lea     r8d, [rdx+68h]; dwBytes
0x1800e4060  call    cs:__imp_HeapAlloc
0x1800e4066  mov     r14, rax
0x1800e4069  test    rax, rax
0x1800e406c  jnz     short loc_1800E40A5
0x1800e406e  lea     ebx, [rax+0Eh]
0x1800e4071  mov     edi, ebx
0x1800e4073  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e407a  lea     rax, WPP_GLOBAL_Control
0x1800e4081  cmp     rcx, rax
0x1800e4084  jz      loc_1800E438E
0x1800e408a  lea     edx, [rbx+19h]
0x1800e408d  mov     r9d, ebx
0x1800e4090  mov     rcx, [rcx+10h]
0x1800e4094  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e409b  call    WPP_SF_d
0x1800e40a0  jmp     loc_1800E438E
0x1800e40a5  xor     edx, edx; Val
0x1800e40a7  mov     rcx, r13; void *
0x1800e40aa  lea     r8d, [rdx+70h]; Size
0x1800e40ae  call    memset_0
0x1800e40b3  xor     edx, edx; Val
0x1800e40b5  mov     [rsp+88h+cbOutput], 5Ah ; 'Z'
0x1800e40bd  mov     rcx, r14; void *
0x1800e40c0  mov     [r13+60h], rdi
0x1800e40c4  lea     r8d, [rdx+70h]; Size
0x1800e40c8  call    memset_0
0x1800e40cd  mov     [rsp+88h+var_54], 5Ah ; 'Z'
0x1800e40d5  mov     [r14+60h], rbx
0x1800e40d9  test    rbp, rbp
0x1800e40dc  jz      short loc_1800E411D
0x1800e40de  mov     rcx, rbp; hToken
0x1800e40e1  xor     edi, edi
0x1800e40e3  call    cs:__imp_ImpersonateLoggedOnUser
0x1800e40e9  test    eax, eax
0x1800e40eb  jnz     short loc_1800E4149
0x1800e40ed  call    cs:__imp_GetLastError
0x1800e40f3  mov     edi, eax
0x1800e40f5  test    eax, eax
0x1800e40f7  jz      short loc_1800E4149
0x1800e40f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4100  lea     rax, WPP_GLOBAL_Control
0x1800e4107  cmp     rcx, rax
0x1800e410a  jz      loc_1800E438E
0x1800e4110  mov     edx, 28h ; '('
0x1800e4115  mov     r9d, edi
0x1800e4118  jmp     loc_1800E4090
0x1800e411d  xor     ecx, ecx; BindingHandle
0x1800e411f  call    cs:__imp_RpcImpersonateClient
0x1800e4125  mov     edi, eax
0x1800e4127  test    eax, eax
0x1800e4129  jz      short loc_1800E4149
0x1800e412b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4132  lea     rax, WPP_GLOBAL_Control
0x1800e4139  cmp     rcx, rax
0x1800e413c  jz      loc_1800E438E
0x1800e4142  mov     edx, 29h ; ')'
0x1800e4147  jmp     short loc_1800E4115
0x1800e4149  call    cs:__imp_GetCurrentThread
0x1800e414f  lea     r9, [r13+68h]; TokenHandle
0x1800e4153  mov     edx, 0F01FFh; DesiredAccess
0x1800e4158  mov     rcx, rax; ThreadHandle
0x1800e415b  mov     r8d, 1; OpenAsSelf
0x1800e4161  call    cs:__imp_OpenThreadToken
0x1800e4167  test    eax, eax
0x1800e4169  jnz     short loc_1800E41BD
0x1800e416b  call    cs:__imp_GetLastError
0x1800e4171  mov     edi, eax
0x1800e4173  test    eax, eax
0x1800e4175  jz      short loc_1800E41BD
0x1800e4177  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e417e  lea     rax, WPP_GLOBAL_Control
0x1800e4185  cmp     rcx, rax
0x1800e4188  jz      short loc_1800E41A2
0x1800e418a  mov     rcx, [rcx+10h]
0x1800e418e  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e4195  mov     edx, 2Ah ; '*'
0x1800e419a  mov     r9d, edi
0x1800e419d  call    WPP_SF_d
0x1800e41a2  test    rbp, rbp
0x1800e41a5  jz      short loc_1800E41B2
0x1800e41a7  call    cs:__imp_RevertToSelf
0x1800e41ad  jmp     loc_1800E438E
0x1800e41b2  call    cs:__imp_RpcRevertToSelf
0x1800e41b8  jmp     loc_1800E438E
0x1800e41bd  test    rbp, rbp
0x1800e41c0  jz      short loc_1800E41CA
0x1800e41c2  call    cs:__imp_RevertToSelf
0x1800e41c8  jmp     short loc_1800E41D0
0x1800e41ca  call    cs:__imp_RpcRevertToSelf
0x1800e41d0  mov     r9d, [rsp+88h+cbOutput]; cbOutput
0x1800e41d5  lea     rax, [rsp+88h+cbOutput]
0x1800e41da  mov     rcx, [r13+60h]; hObject
0x1800e41de  lea     rdx, aPincacheapplic_0; "PinCacheApplicationTicket"
0x1800e41e5  mov     [rsp+88h+dwFlags], 40h ; '@'; dwFlags
0x1800e41ed  mov     r8, r13; pbOutput
0x1800e41f0  mov     [rsp+88h+pcbResult], rax; pcbResult
0x1800e41f5  call    cs:__imp_NCryptGetProperty
0x1800e41fb  mov     esi, eax
0x1800e41fd  test    eax, eax
0x1800e41ff  jns     short loc_1800E4222
0x1800e4201  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4208  lea     rax, WPP_GLOBAL_Control
0x1800e420f  cmp     rcx, rax
0x1800e4212  jz      loc_1800E438E
0x1800e4218  mov     edx, 2Bh ; '+'
0x1800e421d  jmp     loc_1800E437B
0x1800e4222  xor     r8d, r8d; nSize
0x1800e4225  lea     rcx, aWindirSystem32; "%windir%\\System32\\lsass.exe"
0x1800e422c  xor     edx, edx; lpDst
0x1800e422e  call    cs:__imp_ExpandEnvironmentStringsW
0x1800e4234  mov     ebx, eax
0x1800e4236  test    eax, eax
0x1800e4238  jnz     short loc_1800E4265
0x1800e423a  call    cs:__imp_GetLastError
0x1800e4240  mov     edi, eax
0x1800e4242  test    eax, eax
0x1800e4244  jz      short loc_1800E4265
0x1800e4246  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e424d  lea     rax, WPP_GLOBAL_Control
0x1800e4254  cmp     rcx, rax
0x1800e4257  jz      loc_1800E438E
0x1800e425d  lea     edx, [rbx+2Ch]
0x1800e4260  jmp     loc_1800E4115
0x1800e4265  lea     ebp, [rbx+1]
0x1800e4268  mov     ebx, ebp
0x1800e426a  add     rbx, rbx
0x1800e426d  mov     rcx, rbx
0x1800e4270  call    VpnAlloc
0x1800e4275  mov     r15, rax
0x1800e4278  test    rax, rax
0x1800e427b  jnz     short loc_1800E42A1
0x1800e427d  lea     ebx, [rax+0Eh]
0x1800e4280  mov     edi, ebx
0x1800e4282  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4289  lea     rax, WPP_GLOBAL_Control
0x1800e4290  cmp     rcx, rax
0x1800e4293  jz      loc_1800E438E
0x1800e4299  lea     edx, [rbx+1Fh]
0x1800e429c  jmp     loc_1800E408D
0x1800e42a1  mov     r8, rbx; Size
0x1800e42a4  xor     edx, edx; Val
0x1800e42a6  mov     rcx, r15; void *
0x1800e42a9  call    memset_0
0x1800e42ae  mov     r8d, ebp; nSize
0x1800e42b1  lea     rcx, aWindirSystem32; "%windir%\\System32\\lsass.exe"
0x1800e42b8  mov     rdx, r15; lpDst
0x1800e42bb  call    cs:__imp_ExpandEnvironmentStringsW
0x1800e42c1  mov     ebx, eax
0x1800e42c3  test    eax, eax
0x1800e42c5  jnz     short loc_1800E42F2
0x1800e42c7  call    cs:__imp_GetLastError
0x1800e42cd  mov     edi, eax
0x1800e42cf  test    eax, eax
0x1800e42d1  jz      short loc_1800E42F2
0x1800e42d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e42da  lea     rax, WPP_GLOBAL_Control
0x1800e42e1  cmp     rcx, rax
0x1800e42e4  jz      loc_1800E438E
0x1800e42ea  lea     edx, [rbx+2Eh]
0x1800e42ed  jmp     loc_1800E4115
0x1800e42f2  mov     rcx, [r14+60h]; hObject
0x1800e42f6  lea     r9d, [rbx+rbx]; cbInput
0x1800e42fa  mov     r8, r15; pbInput
0x1800e42fd  mov     dword ptr [rsp+88h+pcbResult], 0; dwFlags
0x1800e4305  lea     rdx, aPincacheapplic; "PinCacheApplicationImage"
0x1800e430c  call    cs:__imp_NCryptSetProperty
0x1800e4312  mov     esi, eax
0x1800e4314  test    eax, eax
0x1800e4316  jns     short loc_1800E4332
0x1800e4318  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e431f  lea     rax, WPP_GLOBAL_Control
0x1800e4326  cmp     rcx, rax
0x1800e4329  jz      short loc_1800E438E
0x1800e432b  mov     edx, 2Fh ; '/'
0x1800e4330  jmp     short loc_1800E437B
0x1800e4332  mov     r9d, [rsp+88h+var_54]; cbOutput
0x1800e4337  lea     rax, [rsp+88h+var_54]
0x1800e433c  mov     rcx, [r14+60h]; hObject
0x1800e4340  lea     rdx, aPincacheapplic_0; "PinCacheApplicationTicket"
0x1800e4347  mov     [rsp+88h+dwFlags], 40h ; '@'; dwFlags
0x1800e434f  mov     r8, r14; pbOutput
0x1800e4352  mov     [rsp+88h+pcbResult], rax; pcbResult
0x1800e4357  call    cs:__imp_NCryptGetProperty
0x1800e435d  mov     esi, eax
0x1800e435f  test    eax, eax
0x1800e4361  jns     short loc_1800E438E
0x1800e4363  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e436a  lea     rax, WPP_GLOBAL_Control
0x1800e4371  cmp     rcx, rax
0x1800e4374  jz      short loc_1800E438E
0x1800e4376  mov     edx, 30h ; '0'
0x1800e437b  mov     rcx, [rcx+10h]
0x1800e437f  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e4386  mov     r9d, esi
0x1800e4389  call    WPP_SF_d
0x1800e438e  mov     rax, [rsp+88h+arg_18]
0x1800e4396  mov     ebx, edi
0x1800e4398  mov     [rax], r13
0x1800e439b  test    r14, r14
0x1800e439e  jz      short loc_1800E43A4
0x1800e43a0  mov     [r12], r14
0x1800e43a4  test    esi, esi
0x1800e43a6  jns     short loc_1800E43C0
0x1800e43a8  test    edi, edi
0x1800e43aa  jnz     short loc_1800E43C0
0x1800e43ac  mov     eax, esi
0x1800e43ae  movzx   ebx, si
0x1800e43b1  and     eax, 1FFF0000h
0x1800e43b6  cmp     eax, 70000h
0x1800e43bb  jz      short loc_1800E43C0
0x1800e43bd  lea     ebx, [rdi+0Dh]
0x1800e43c0  test    r15, r15
0x1800e43c3  jz      short loc_1800E43CD
0x1800e43c5  mov     rcx, r15; lpMem
0x1800e43c8  call    MprCommonFree
0x1800e43cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e43d4  lea     rax, WPP_GLOBAL_Control
0x1800e43db  cmp     rcx, rax
0x1800e43de  jz      short loc_1800E4404
0x1800e43e0  test    byte ptr [rcx+1Ch], 80h
0x1800e43e4  jz      short loc_1800E4404
0x1800e43e6  cmp     byte ptr [rcx+19h], 6
0x1800e43ea  jb      short loc_1800E4404
0x1800e43ec  mov     rcx, [rcx+10h]
0x1800e43f0  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e43f7  mov     edx, 31h ; '1'
0x1800e43fc  mov     r9d, ebx
0x1800e43ff  call    WPP_SF_d
0x1800e4404  mov     eax, ebx
0x1800e4406  add     rsp, 48h
0x1800e440a  pop     r15
0x1800e440c  pop     r14
0x1800e440e  pop     r13
0x1800e4410  pop     r12
0x1800e4412  pop     rdi
0x1800e4413  pop     rsi
0x1800e4414  pop     rbp
0x1800e4415  pop     rbx
0x1800e4416  retn
```
