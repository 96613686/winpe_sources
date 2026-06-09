# IsRpcClientPrivilegedUser

- ea: `0x1800018d0`
- end: `0x180001ce2`
- name: `IsRpcClientPrivilegedUser`
- size: `1042`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800013d0`

## callees

- `0x1800018d0`
- `0x180008ff0`
- `0x180009130`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800019ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800019ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800019d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800019d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001935`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001935`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001986`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001986`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001b11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001b11`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180001a79`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180001a79`
- `RPCRT4!RpcImpersonateClient` at `0x180001a12`
- `RPCRT4!RpcImpersonateClient` at `0x180001a12`
- `RPCRT4!RpcRevertToSelf` at `0x180001ac9`
- `RPCRT4!RpcRevertToSelf` at `0x180001ac9`

## pseudocode

```c
__int64 __fastcall IsRpcClientPrivilegedUser(PBOOL IsMember)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  unsigned int v4; // esi
  int v5; // r14d
  int v7; // ebp
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *v10; // rdx
  DWORD v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdx
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    {
      WPP_SF_(v2[2], 72, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v3 = 0;
  if ( *(_QWORD *)&g_pSecurity )
  {
    v4 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&g_pSecurity + 368LL));
    v5 = 1;
LABEL_9:
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_10;
  }
  v4 = 5023;
  v5 = 0;
  if ( v2 == &WPP_GLOBAL_Control )
    goto LABEL_13;
  if ( (*((_BYTE *)v2 + 28) & 4) != 0 )
  {
    WPP_SF_L(v2[2], 73, WPP_fd6184a389643c6486807174a58ed414_Traceguids, 5023);
    goto LABEL_9;
  }
LABEL_10:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
  {
    WPP_SF_L(v2[2], 74, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v4);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_13:
  if ( v4 )
  {
    if ( v2 == &WPP_GLOBAL_Control )
      goto LABEL_15;
    if ( (*((_BYTE *)v2 + 28) & 4) != 0 )
    {
      WPP_SF_L(v2[2], 120, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v4);
      goto LABEL_51;
    }
    goto LABEL_52;
  }
  v7 = 0;
  TokenHandle = 0;
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_(v2[2], 115, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v4 = 0;
    CloseHandle(TokenHandle);
    goto LABEL_31;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError != 1008 && LastError )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_35;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_32;
    v14 = 116;
    goto LABEL_65;
  }
  LastError = RpcImpersonateClient(0);
  v4 = LastError;
  if ( !LastError )
  {
    v7 = 1;
LABEL_31:
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_32;
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_35;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v14 = 117;
LABEL_65:
    WPP_SF_L(v2[2], v14, WPP_fd6184a389643c6486807174a58ed414_Traceguids, LastError);
    goto LABEL_31;
  }
LABEL_32:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
  {
    WPP_SF_L(v2[2], 118, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v4);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_35:
  if ( !v4 )
  {
    while ( !*IsMember && v3 < 0xA && v3 <= *(_DWORD *)(*(_QWORD *)&g_pSecurity + 360LL) )
    {
      v10 = *(void **)(*(_QWORD *)&g_pSecurity + 8LL * v3);
      if ( v10 )
      {
        if ( *(_DWORD *)(*(_QWORD *)&g_pSecurity + 4LL * v3 + 80) )
        {
          if ( !CheckTokenMembership(0, v10, IsMember) )
          {
            v11 = GetLastError();
            v4 = v11;
            if ( v11 )
            {
              v2 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                v12 = 122;
                v13 = v11;
                goto LABEL_47;
              }
              goto LABEL_49;
            }
          }
        }
      }
      ++v3;
    }
    goto LABEL_48;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 )
  {
    v12 = 121;
    v13 = v4;
LABEL_47:
    WPP_SF_L(v2[2], v12, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v13);
LABEL_48:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_49:
  if ( v7 )
  {
    RpcRevertToSelf();
LABEL_51:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_52:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
  {
    WPP_SF_(v2[2], 75, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_15:
  if ( v5 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&g_pSecurity + 368LL));
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v2 + 28) & 8) != 0 )
    {
      WPP_SF_L(v2[2], 76, WPP_fd6184a389643c6486807174a58ed414_Traceguids, 0);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      WPP_SF_L(v2[2], 123, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x1800018d0  push    rsi
0x1800018d2  push    r15
0x1800018d4  sub     rsp, 28h
0x1800018d8  mov     [rsp+38h+arg_18], rdi
0x1800018dd  mov     rdi, rcx
0x1800018e0  mov     [rsp+38h+var_18], r14
0x1800018e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018ec  lea     r15, WPP_GLOBAL_Control
0x1800018f3  cmp     rcx, r15
0x1800018f6  jz      short loc_180001911
0x1800018f8  test    byte ptr [rcx+1Ch], 8
0x1800018fc  jnz     loc_180001B40
0x180001902  cmp     rcx, r15
0x180001905  jz      short loc_180001911
0x180001907  test    byte ptr [rcx+1Ch], 8
0x18000190b  jnz     loc_180001B61
0x180001911  mov     [rsp+38h+arg_0], rbx
0x180001916  xor     ebx, ebx
0x180001918  cmp     cs:g_pSecurity, rbx
0x18000191f  jz      loc_180001B82
0x180001925  mov     rcx, cs:g_pSecurity
0x18000192c  mov     esi, ebx
0x18000192e  add     rcx, 170h; lpCriticalSection
0x180001935  call    cs:__imp_EnterCriticalSection
0x18000193b  mov     r14d, 1
0x180001941  mov     rcx, cs:WPP_GLOBAL_Control
0x180001948  cmp     rcx, r15
0x18000194b  jz      short loc_180001957
0x18000194d  test    byte ptr [rcx+1Ch], 8
0x180001951  jnz     loc_180001B1C
0x180001957  test    esi, esi
0x180001959  jz      short loc_1800019BB
0x18000195b  cmp     rcx, r15
0x18000195e  jnz     loc_180001BBA
0x180001964  mov     rdi, [rsp+38h+arg_18]
0x180001969  test    r14d, r14d
0x18000196c  mov     r14, [rsp+38h+var_18]
0x180001971  mov     rbx, [rsp+38h+arg_0]
0x180001976  jz      short loc_180001993
0x180001978  mov     rcx, cs:g_pSecurity
0x18000197f  add     rcx, 170h; lpCriticalSection
0x180001986  call    cs:__imp_LeaveCriticalSection
0x18000198c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001993  cmp     rcx, r15
0x180001996  jz      short loc_1800019B1
0x180001998  test    byte ptr [rcx+1Ch], 8
0x18000199c  jnz     loc_180001CA1
0x1800019a2  cmp     rcx, r15
0x1800019a5  jz      short loc_1800019B1
0x1800019a7  test    byte ptr [rcx+1Ch], 8
0x1800019ab  jnz     loc_180001CC5
0x1800019b1  mov     eax, esi
0x1800019b3  add     rsp, 28h
0x1800019b7  pop     r15
0x1800019b9  pop     rsi
0x1800019ba  retn
0x1800019bb  mov     [rsp+38h+arg_10], rbp
0x1800019c0  mov     ebp, ebx
0x1800019c2  mov     [rsp+38h+TokenHandle], rbx
0x1800019c7  cmp     rcx, r15
0x1800019ca  jz      short loc_1800019D6
0x1800019cc  test    byte ptr [rcx+1Ch], 8
0x1800019d0  jnz     loc_180001BE1
0x1800019d6  call    cs:__imp_GetCurrentThread
0x1800019dc  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800019e1  mov     edx, 8; DesiredAccess
0x1800019e6  mov     rcx, rax; ThreadHandle
0x1800019e9  mov     r8d, 1; OpenAsSelf
0x1800019ef  call    cs:__imp_OpenThreadToken
0x1800019f5  test    eax, eax
0x1800019f7  jnz     loc_180001B0A
0x1800019fd  call    cs:__imp_GetLastError
0x180001a03  mov     esi, eax
0x180001a05  cmp     eax, 3F0h
0x180001a0a  jnz     loc_180001BFB
0x180001a10  xor     ecx, ecx; BindingHandle
0x180001a12  call    cs:__imp_RpcImpersonateClient
0x180001a18  mov     esi, eax
0x180001a1a  test    eax, eax
0x180001a1c  jnz     loc_180001C41
0x180001a22  mov     ebp, 1
0x180001a27  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a2e  cmp     rcx, r15
0x180001a31  jz      short loc_180001A3D
0x180001a33  test    byte ptr [rcx+1Ch], 8
0x180001a37  jnz     loc_180001C5D
0x180001a3d  test    esi, esi
0x180001a3f  jnz     loc_180001C81
0x180001a45  cmp     dword ptr [rdi], 0
0x180001a48  jnz     short loc_180001AB9
0x180001a4a  cmp     ebx, 0Ah
0x180001a4d  jnb     short loc_180001AB9
0x180001a4f  mov     rax, cs:g_pSecurity
0x180001a56  cmp     ebx, [rax+168h]
0x180001a5c  ja      short loc_180001AB9
0x180001a5e  mov     ecx, ebx
0x180001a60  mov     rdx, [rax+rcx*8]; SidToCheck
0x180001a64  test    rdx, rdx
0x180001a67  jz      short loc_180001A70
0x180001a69  cmp     dword ptr [rax+rcx*4+50h], 0
0x180001a6e  jnz     short loc_180001A74
0x180001a70  inc     ebx
0x180001a72  jmp     short loc_180001A45
0x180001a74  mov     r8, rdi; IsMember
0x180001a77  xor     ecx, ecx; TokenHandle
0x180001a79  call    cs:__imp_CheckTokenMembership
0x180001a7f  test    eax, eax
0x180001a81  jnz     short loc_180001A70
0x180001a83  call    cs:__imp_GetLastError
0x180001a89  mov     esi, eax
0x180001a8b  test    eax, eax
0x180001a8d  jz      short loc_180001A70
0x180001a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a96  cmp     rcx, r15
0x180001a99  jz      short loc_180001AC0
0x180001a9b  test    byte ptr [rcx+1Ch], 4
0x180001a9f  jz      short loc_180001AC0
0x180001aa1  mov     edx, 7Ah ; 'z'
0x180001aa6  mov     r9d, eax
0x180001aa9  mov     rcx, [rcx+10h]
0x180001aad  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001ab4  call    WPP_SF_L
0x180001ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ac0  test    ebp, ebp
0x180001ac2  mov     rbp, [rsp+38h+arg_10]
0x180001ac7  jz      short loc_180001AD6
0x180001ac9  call    cs:__imp_RpcRevertToSelf
0x180001acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ad6  cmp     rcx, r15
0x180001ad9  jz      loc_180001964
0x180001adf  test    byte ptr [rcx+1Ch], 8
0x180001ae3  jz      loc_180001964
0x180001ae9  mov     rcx, [rcx+10h]
0x180001aed  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001af4  mov     edx, 4Bh ; 'K'
0x180001af9  call    WPP_SF_
0x180001afe  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b05  jmp     loc_180001964
0x180001b0a  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180001b0f  mov     esi, ebx
0x180001b11  call    cs:__imp_CloseHandle
0x180001b17  jmp     loc_180001A27
0x180001b1c  mov     rcx, [rcx+10h]
0x180001b20  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001b27  mov     edx, 4Ah ; 'J'
0x180001b2c  mov     r9d, esi
0x180001b2f  call    WPP_SF_L
0x180001b34  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b3b  jmp     loc_180001957
0x180001b40  mov     rcx, [rcx+10h]
0x180001b44  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001b4b  mov     edx, 77h ; 'w'
0x180001b50  call    WPP_SF_
0x180001b55  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b5c  jmp     loc_180001902
0x180001b61  mov     rcx, [rcx+10h]
0x180001b65  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001b6c  mov     edx, 48h ; 'H'
0x180001b71  call    WPP_SF_
0x180001b76  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b7d  jmp     loc_180001911
0x180001b82  mov     esi, 139Fh
0x180001b87  mov     r14d, ebx
0x180001b8a  cmp     rcx, r15
0x180001b8d  jz      loc_180001957
0x180001b93  test    byte ptr [rcx+1Ch], 4
0x180001b97  jz      loc_180001948
0x180001b9d  mov     rcx, [rcx+10h]
0x180001ba1  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001ba8  mov     edx, 49h ; 'I'
0x180001bad  mov     r9d, esi
0x180001bb0  call    WPP_SF_L
0x180001bb5  jmp     loc_180001941
0x180001bba  test    byte ptr [rcx+1Ch], 4
0x180001bbe  jz      loc_180001AD6
0x180001bc4  mov     rcx, [rcx+10h]
0x180001bc8  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001bcf  mov     edx, 78h ; 'x'
0x180001bd4  mov     r9d, esi
0x180001bd7  call    WPP_SF_L
0x180001bdc  jmp     loc_180001ACF
0x180001be1  mov     rcx, [rcx+10h]
0x180001be5  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001bec  mov     edx, 73h ; 's'
0x180001bf1  call    WPP_SF_
0x180001bf6  jmp     loc_1800019D6
0x180001bfb  test    eax, eax
0x180001bfd  jz      loc_180001A10
0x180001c03  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c0a  cmp     rcx, r15
0x180001c0d  jz      loc_180001A3D
0x180001c13  test    byte ptr [rcx+1Ch], 4
0x180001c17  jz      loc_180001A2E
0x180001c1d  mov     edx, 74h ; 't'
0x180001c22  jmp     short loc_180001C29
0x180001c24  mov     edx, 75h ; 'u'
0x180001c29  mov     rcx, [rcx+10h]
0x180001c2d  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001c34  mov     r9d, eax
0x180001c37  call    WPP_SF_L
0x180001c3c  jmp     loc_180001A27
0x180001c41  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c48  cmp     rcx, r15
0x180001c4b  jz      loc_180001A3D
0x180001c51  test    byte ptr [rcx+1Ch], 4
0x180001c55  jz      loc_180001A2E
0x180001c5b  jmp     short loc_180001C24
0x180001c5d  mov     rcx, [rcx+10h]
0x180001c61  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001c68  mov     edx, 76h ; 'v'
0x180001c6d  mov     r9d, esi
0x180001c70  call    WPP_SF_L
0x180001c75  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c7c  jmp     loc_180001A3D
0x180001c81  cmp     rcx, r15
0x180001c84  jz      loc_180001AC0
0x180001c8a  test    byte ptr [rcx+1Ch], 4
0x180001c8e  jz      loc_180001AC0
0x180001c94  mov     edx, 79h ; 'y'
0x180001c99  mov     r9d, esi
0x180001c9c  jmp     loc_180001AA9
0x180001ca1  mov     rcx, [rcx+10h]
0x180001ca5  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001cac  mov     edx, 4Ch ; 'L'
0x180001cb1  xor     r9d, r9d
0x180001cb4  call    WPP_SF_L
0x180001cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180001cc0  jmp     loc_1800019A2
0x180001cc5  mov     rcx, [rcx+10h]
0x180001cc9  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001cd0  mov     edx, 7Bh ; '{'
0x180001cd5  mov     r9d, esi
0x180001cd8  call    WPP_SF_L
0x180001cdd  jmp     loc_1800019B1
```
