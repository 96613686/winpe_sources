# __CodeAuthzpCompareCodeAuthzLevelWithToken

- ea: `0x18000b340`
- end: `0x18000bf10`
- name: `__CodeAuthzpCompareCodeAuthzLevelWithToken`
- size: `3024`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a3b0`
- `0x18000b1d0`

## callees

- `0x18000b340`
- `0x18000bf20`
- `0x18000c0d0`
- `0x18000c650`
- `0x180022a00`
- `0x180065036`
- `0x18006504e`
- `0x180065090`

## import_xrefs

- `ntdll!NtClose` at `0x18000bdd6`
- `ntdll!NtClose` at `0x18000bdd6`
- `ntdll!NtOpenThreadToken` at `0x18000be04`
- `ntdll!NtOpenThreadToken` at `0x18000be04`
- `ntdll!NtOpenProcessToken` at `0x18000be24`
- `ntdll!NtOpenProcessToken` at `0x18000be24`
- `ntdll!RtlEqualSid` at `0x18000b666`
- `ntdll!RtlEqualSid` at `0x18000b6a2`
- `ntdll!RtlEqualSid` at `0x18000b666`
- `ntdll!RtlEqualSid` at `0x18000b6a2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000b613`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000b613`
- `ntdll!RtlFreeSid` at `0x18000b74f`
- `ntdll!RtlFreeSid` at `0x18000b74f`
- `ntdll!RtlFreeHeap` at `0x18000b734`
- `ntdll!RtlFreeHeap` at `0x18000b770`
- `ntdll!RtlFreeHeap` at `0x18000b78d`
- `ntdll!RtlFreeHeap` at `0x18000b7ae`
- `ntdll!RtlFreeHeap` at `0x18000b7cb`
- `ntdll!RtlFreeHeap` at `0x18000b7eb`
- `ntdll!RtlFreeHeap` at `0x18000b808`
- `ntdll!RtlFreeHeap` at `0x18000b828`
- `ntdll!RtlFreeHeap` at `0x18000b9f6`
- `ntdll!RtlFreeHeap` at `0x18000baa5`
- `ntdll!RtlFreeHeap` at `0x18000bb0d`
- `ntdll!RtlFreeHeap` at `0x18000bb71`
- `ntdll!RtlFreeHeap` at `0x18000bc1e`
- `ntdll!RtlFreeHeap` at `0x18000bd14`
- `ntdll!RtlFreeHeap` at `0x18000bd4d`
- `ntdll!RtlFreeHeap` at `0x18000bd74`
- `ntdll!RtlFreeHeap` at `0x18000bd9c`
- `ntdll!RtlFreeHeap` at `0x18000b734`
- `ntdll!RtlFreeHeap` at `0x18000b770`
- `ntdll!RtlFreeHeap` at `0x18000b78d`
- `ntdll!RtlFreeHeap` at `0x18000b7ae`
- `ntdll!RtlFreeHeap` at `0x18000b7cb`
- `ntdll!RtlFreeHeap` at `0x18000b7eb`
- `ntdll!RtlFreeHeap` at `0x18000b808`
- `ntdll!RtlFreeHeap` at `0x18000b828`
- `ntdll!RtlFreeHeap` at `0x18000b9f6`
- `ntdll!RtlFreeHeap` at `0x18000baa5`
- `ntdll!RtlFreeHeap` at `0x18000bb0d`
- `ntdll!RtlFreeHeap` at `0x18000bb71`
- `ntdll!RtlFreeHeap` at `0x18000bc1e`
- `ntdll!RtlFreeHeap` at `0x18000bd14`
- `ntdll!RtlFreeHeap` at `0x18000bd4d`
- `ntdll!RtlFreeHeap` at `0x18000bd74`
- `ntdll!RtlFreeHeap` at `0x18000bd9c`
- `ntdll!NtQueryInformationToken` at `0x18000b467`
- `ntdll!NtQueryInformationToken` at `0x18000b4fb`
- `ntdll!NtQueryInformationToken` at `0x18000b5c1`
- `ntdll!NtQueryInformationToken` at `0x18000b8e2`
- `ntdll!NtQueryInformationToken` at `0x18000b983`
- `ntdll!NtQueryInformationToken` at `0x18000ba40`
- `ntdll!NtQueryInformationToken` at `0x18000baef`
- `ntdll!NtQueryInformationToken` at `0x18000bb54`
- `ntdll!NtQueryInformationToken` at `0x18000bbbb`
- `ntdll!NtQueryInformationToken` at `0x18000bc68`
- `ntdll!NtQueryInformationToken` at `0x18000b467`
- `ntdll!NtQueryInformationToken` at `0x18000b4fb`
- `ntdll!NtQueryInformationToken` at `0x18000b5c1`
- `ntdll!NtQueryInformationToken` at `0x18000b8e2`
- `ntdll!NtQueryInformationToken` at `0x18000b983`
- `ntdll!NtQueryInformationToken` at `0x18000ba40`
- `ntdll!NtQueryInformationToken` at `0x18000baef`
- `ntdll!NtQueryInformationToken` at `0x18000bb54`
- `ntdll!NtQueryInformationToken` at `0x18000bbbb`
- `ntdll!NtQueryInformationToken` at `0x18000bc68`
- `ntdll!RtlAllocateHeap` at `0x18000b435`
- `ntdll!RtlAllocateHeap` at `0x18000b4ca`
- `ntdll!RtlAllocateHeap` at `0x18000b590`
- `ntdll!RtlAllocateHeap` at `0x18000b8ad`
- `ntdll!RtlAllocateHeap` at `0x18000b94d`
- `ntdll!RtlAllocateHeap` at `0x18000ba10`
- `ntdll!RtlAllocateHeap` at `0x18000babf`
- `ntdll!RtlAllocateHeap` at `0x18000bb27`
- `ntdll!RtlAllocateHeap` at `0x18000bb8b`
- `ntdll!RtlAllocateHeap` at `0x18000bc38`
- `ntdll!RtlAllocateHeap` at `0x18000b435`
- `ntdll!RtlAllocateHeap` at `0x18000b4ca`
- `ntdll!RtlAllocateHeap` at `0x18000b590`
- `ntdll!RtlAllocateHeap` at `0x18000b8ad`
- `ntdll!RtlAllocateHeap` at `0x18000b94d`
- `ntdll!RtlAllocateHeap` at `0x18000ba10`
- `ntdll!RtlAllocateHeap` at `0x18000babf`
- `ntdll!RtlAllocateHeap` at `0x18000bb27`
- `ntdll!RtlAllocateHeap` at `0x18000bb8b`
- `ntdll!RtlAllocateHeap` at `0x18000bc38`

## pseudocode

```c
__int64 __fastcall _CodeAuthzpCompareCodeAuthzLevelWithToken(__int64 a1, __int64 a2, void *a3, _DWORD *a4)
{
  NTSTATUS v4; // ebx
  __int64 v6; // r14
  ULONG v7; // r12d
  char v8; // di
  PSID *v9; // rsi
  unsigned int *v10; // r13
  HANDLE v11; // rbx
  unsigned int *v12; // r10
  NTSTATUS v13; // eax
  unsigned int v14; // edx
  HANDLE v15; // rbx
  NTSTATUS v16; // eax
  HANDLE v17; // rbx
  NTSTATUS v18; // eax
  ULONG m; // edx
  _DWORD *v20; // rdi
  _BYTE *v21; // r15
  PSID v22; // r14
  unsigned int v23; // r13d
  _BYTE *v24; // r12
  unsigned int v25; // esi
  unsigned int v26; // ecx
  _BYTE *v27; // rbx
  BOOLEAN v28; // al
  void *v29; // r14
  unsigned int v31; // edi
  HANDLE v32; // rbx
  unsigned int *v33; // r15
  NTSTATUS v34; // eax
  __int64 v35; // rsi
  unsigned int v36; // edi
  PVOID v37; // r14
  NTSTATUS v38; // eax
  unsigned int *v39; // r10
  __int64 v40; // r14
  unsigned int j; // ebx
  PVOID v42; // rax
  __int64 v43; // rcx
  char v44; // al
  unsigned int n; // ebx
  NTSTATUS v46; // eax
  __int64 k; // rdx
  unsigned int i; // r8d
  int SubAuthority3; // [rsp+28h] [rbp-D8h]
  char v50; // [rsp+60h] [rbp-A0h]
  char v51; // [rsp+61h] [rbp-9Fh]
  char v52; // [rsp+62h] [rbp-9Eh]
  ULONG v53; // [rsp+64h] [rbp-9Ch] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  ULONG v55; // [rsp+70h] [rbp-90h] BYREF
  ULONG ReturnLength; // [rsp+74h] [rbp-8Ch] BYREF
  ULONG TokenInformationLength; // [rsp+78h] [rbp-88h] BYREF
  ULONG v58; // [rsp+7Ch] [rbp-84h] BYREF
  PVOID v59; // [rsp+80h] [rbp-80h]
  PVOID Heap; // [rsp+88h] [rbp-78h]
  PSID *v61; // [rsp+90h] [rbp-70h]
  PVOID v62; // [rsp+98h] [rbp-68h]
  unsigned int v63; // [rsp+A0h] [rbp-60h]
  ULONG v64; // [rsp+A4h] [rbp-5Ch]
  __int64 v65; // [rsp+A8h] [rbp-58h] BYREF
  PVOID P; // [rsp+B0h] [rbp-50h]
  unsigned int *v67; // [rsp+B8h] [rbp-48h]
  _DWORD *v68; // [rsp+C0h] [rbp-40h]
  PSID Sid1; // [rsp+C8h] [rbp-38h] BYREF
  PVOID v70; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v71; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v72; // [rsp+E0h] [rbp-20h]
  __int64 v73; // [rsp+E8h] [rbp-18h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+F0h] [rbp-10h] BYREF

  v4 = 0;
  v68 = a4;
  v72 = a2;
  v73 = a1;
  v6 = a2;
  TokenHandle = a3;
  v7 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Sid1 = 0;
  v53 = 0;
  v70 = 0;
  LODWORD(v65) = 0;
  v59 = 0;
  v71 = 0;
  if ( !a2 )
  {
    v4 = -1073741585;
    goto LABEL_132;
  }
  if ( !a4 )
  {
    v4 = -1073741819;
    goto LABEL_132;
  }
  *a4 = 0;
  if ( a3 )
  {
    v8 = 1;
    v51 = 1;
    goto LABEL_5;
  }
  v8 = 0;
  v51 = 0;
  v46 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000Au, 1u, &TokenHandle);
  v4 = v46;
  if ( v46 != -1073741700 )
  {
    if ( v46 < 0 )
      goto LABEL_132;
LABEL_139:
    v4 = 0;
LABEL_5:
    if ( (unsigned int)IsSystemProcessOrService(TokenHandle) )
    {
      *a4 = 1;
      goto LABEL_73;
    }
    if ( *(_DWORD *)(v6 + 12) )
    {
      *a4 = -1;
      goto LABEL_73;
    }
    v9 = 0;
    v10 = 0;
    P = 0;
    v11 = TokenHandle;
    v50 = 0;
    if ( !*(_DWORD *)(v6 + 56) )
    {
      v12 = 0;
      Heap = 0;
      if ( !TokenHandle
        || (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x80u), (v12 = (unsigned int *)Heap) == 0) )
      {
LABEL_13:
        if ( v12 )
        {
          v62 = 0;
          v14 = 0;
          v52 = 0;
LABEL_15:
          if ( v14 < *(_DWORD *)(v6 + 64) )
          {
            for ( i = 0; ; ++i )
            {
              if ( i >= *v12 )
              {
                ++v14;
                goto LABEL_15;
              }
              if ( *(_QWORD *)&v12[3 * i + 1] == *(_QWORD *)(*(_QWORD *)(v6 + 72) + 12LL * v14) )
                break;
            }
            *a4 = -1;
            v4 = 0;
            goto LABEL_55;
          }
          goto LABEL_16;
        }
LABEL_120:
        v4 = -1073741823;
        goto LABEL_73;
      }
      ReturnLength = 0;
      v13 = NtQueryInformationToken(v11, TokenPrivileges, Heap, 0x80u, &ReturnLength);
      if ( v13 == -1073741789 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        v42 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ReturnLength);
        Heap = v42;
        if ( !v42 )
          goto LABEL_119;
        v13 = NtQueryInformationToken(v11, TokenPrivileges, v42, ReturnLength, &ReturnLength);
      }
      if ( v13 >= 0 )
      {
        v12 = (unsigned int *)Heap;
        goto LABEL_13;
      }
      v42 = Heap;
LABEL_119:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v42);
      goto LABEL_120;
    }
    if ( !TokenHandle )
    {
LABEL_125:
      v4 = -1073741823;
      goto LABEL_73;
    }
    v35 = *(_QWORD *)(v6 + 72);
    v36 = *(_DWORD *)(v6 + 64);
    v62 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x80u);
    v37 = v62;
    if ( !v62 )
    {
LABEL_124:
      v8 = v51;
      goto LABEL_125;
    }
    v55 = 0;
    v38 = NtQueryInformationToken(v11, TokenPrivileges, v62, 0x80u, &v55);
    if ( v38 == -1073741789 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v37);
      v62 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v55);
      v37 = v62;
      if ( !v62 )
      {
LABEL_123:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v37);
        goto LABEL_124;
      }
      v38 = NtQueryInformationToken(v11, TokenPrivileges, v62, v55, &v55);
    }
    if ( v38 >= 0 )
    {
      v39 = (unsigned int *)v62;
      v40 = 0;
      for ( j = *(_DWORD *)v62; (unsigned int)v40 < *v39; v40 = (unsigned int)(v40 + 1) )
      {
        for ( k = 0; (unsigned int)k < v36; k = (unsigned int)(k + 1) )
        {
          if ( *(_QWORD *)&v39[3 * v40 + 1] == *(_QWORD *)(v35 + 12 * k) )
          {
            memmove_0(
              &v39[3 * v40 + 1],
              &v39[2 * (unsigned int)(v40 + 1) + 1 + (unsigned int)(v40 + 1)],
              --*v39 - (unsigned int)v40);
            v39 = (unsigned int *)v62;
            LODWORD(v40) = v40 - 1;
            break;
          }
        }
        j = *v39;
      }
      memmove_0(v39, v39 + 1, 12LL * j);
      v52 = 1;
      Heap = 0;
      if ( j )
      {
        *a4 = -1;
        v4 = 0;
        v9 = 0;
        goto LABEL_55;
      }
      v6 = v72;
LABEL_16:
      v15 = TokenHandle;
      v9 = 0;
      v61 = 0;
      if ( !TokenHandle || (v61 = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x80u), (v9 = v61) == 0) )
      {
LABEL_20:
        if ( v9 )
        {
          if ( *(_DWORD *)(v6 + 36) )
          {
            if ( !(unsigned __int8)CodeAuthzpInvertAndAddSids(TokenHandle, *v9, 0, 0, (__int64)&v53, (__int64)&v70) )
            {
              v4 = -1073741823;
              goto LABEL_55;
            }
          }
          else
          {
            if ( !*(_DWORD *)(v6 + 44) || !*(_QWORD *)(v6 + 48) )
            {
              v50 = 0;
              goto LABEL_24;
            }
            if ( !(unsigned __int8)CodeAuthzpExpandWildcardList(TokenHandle, *v9, (__int64)&v53, (__int64)&v70) )
            {
              v4 = -1073741823;
              goto LABEL_55;
            }
          }
          v7 = v53;
          v50 = 1;
LABEL_24:
          v17 = TokenHandle;
          v10 = 0;
          v67 = 0;
          if ( !TokenHandle
            || (v67 = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x80u), (v10 = v67) == 0) )
          {
LABEL_28:
            if ( v10 )
            {
              v4 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0xAu, 0, 0, 0, 0, 0, 0, 0, &Sid1);
              if ( v4 >= 0 )
              {
                for ( m = 0; ; ++m )
                {
                  v64 = m;
                  if ( m >= v7 )
                    break;
                  v20 = v10 + 2;
                  if ( v10 != (unsigned int *)-8LL )
                  {
                    v21 = *v9;
                    v22 = Sid1;
                    v23 = *v10;
                    v24 = (_BYTE *)*((_QWORD *)v70 + 2 * m);
                    if ( *v9 && Sid1 && RtlEqualSid(Sid1, *((PSID *)v70 + 2 * m)) )
                      v24 = v21;
                    v25 = 0;
                    v26 = 4 * (unsigned __int8)v24[1] + 8;
                    v63 = v26;
                    while ( v25 < v23 )
                    {
                      if ( (v20[2] & 4) != 0 )
                      {
                        v27 = *(_BYTE **)v20;
                        if ( v22 )
                        {
                          if ( v21 )
                          {
                            v28 = RtlEqualSid(v22, *(PSID *)v20);
                            v26 = v63;
                            if ( v28 )
                              v27 = v21;
                          }
                        }
                        if ( *v24 == *v27 && v26 == 4 * (unsigned __int8)v27[1] + 8 && !memcmp_0(v24, v27, v26) )
                        {
                          v4 = 0;
                          v10 = v67;
                          v9 = v61;
                          *v68 = -1;
                          goto LABEL_49;
                        }
                      }
                      v26 = v63;
                      v20 += 4;
                      ++v25;
                    }
                    m = v64;
                    v7 = v53;
                    v10 = v67;
                    v9 = v61;
                  }
                }
                if ( *(_DWORD *)(v72 + 84) )
                {
                  v44 = CodeAuthzpInvertAndAddSids(
                          TokenHandle,
                          *v9,
                          *(_DWORD *)(v72 + 100),
                          *(_QWORD *)(v72 + 104),
                          (__int64)&v65,
                          (__int64)&v71);
                  v29 = (void *)v71;
                  if ( !v44 )
                  {
                    v4 = -1073741823;
                    LOBYTE(v7) = 0;
                    goto LABEL_56;
                  }
                  v31 = v65;
                  LOBYTE(v7) = 1;
                }
                else
                {
                  v31 = *(_DWORD *)(v72 + 100);
                  LOBYTE(v7) = 0;
                  v29 = *(void **)(v72 + 104);
                }
                v32 = TokenHandle;
                v33 = 0;
                P = 0;
                if ( !TokenHandle
                  || (P = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x80u), (v33 = (unsigned int *)P) == 0) )
                {
LABEL_81:
                  if ( v33 )
                  {
                    if ( *v33 )
                    {
                      for ( n = 0; n < *v33; ++n )
                      {
                        LOBYTE(SubAuthority3) = 0;
                        if ( !(unsigned __int8)CodeAuthzpSidInSidAndAttributes(
                                                 v29,
                                                 v31,
                                                 Sid1,
                                                 *v9,
                                                 *(_QWORD *)&v33[4 * n + 2],
                                                 SubAuthority3) )
                          goto LABEL_84;
                      }
                    }
                    else if ( v31 )
                    {
LABEL_84:
                      *v68 = -1;
LABEL_85:
                      v4 = 0;
                      goto LABEL_56;
                    }
                    v43 = v73;
                    *v68 = 1;
                    if ( v43
                      && (*(_DWORD *)(v43 + 552) & 0x1000) != 0
                      && *(_WORD *)(v43 + 32)
                      && (*(_DWORD *)(v43 + 16)
                       || *(_DWORD *)(v43 + 20)
                       || *(_DWORD *)(v43 + 24)
                       || *(_DWORD *)(v43 + 28)) )
                    {
                      v4 = 1073741874;
                      goto LABEL_56;
                    }
                    goto LABEL_85;
                  }
LABEL_129:
                  v4 = -1073741823;
                  goto LABEL_56;
                }
                v53 = 0;
                v34 = NtQueryInformationToken(v32, TokenRestrictedSids, P, 0x80u, &v53);
                if ( v34 == -1073741789 )
                {
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v33);
                  P = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v53);
                  v33 = (unsigned int *)P;
                  if ( !P )
                    goto LABEL_128;
                  v34 = NtQueryInformationToken(v32, TokenRestrictedSids, P, v53, &v53);
                }
                if ( v34 >= 0 )
                  goto LABEL_81;
LABEL_128:
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v33);
                P = 0;
                goto LABEL_129;
              }
LABEL_49:
              LOBYTE(v7) = 0;
LABEL_55:
              v29 = v59;
LABEL_56:
              if ( Sid1 )
                RtlFreeSid(Sid1);
              if ( P )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
              if ( v10 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
              if ( Heap )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
              if ( v9 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
              if ( v50 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v70);
              if ( (_BYTE)v7 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
              if ( v52 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v62);
              v8 = v51;
LABEL_73:
              if ( v8 )
                return (unsigned int)v4;
              goto LABEL_132;
            }
LABEL_127:
            v4 = -1073741823;
            LOBYTE(v7) = 0;
            goto LABEL_55;
          }
          v58 = 0;
          v18 = NtQueryInformationToken(v17, TokenGroups, v67, 0x80u, &v58);
          if ( v18 == -1073741789 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
            v67 = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v58);
            v10 = v67;
            if ( !v67 )
              goto LABEL_126;
            v18 = NtQueryInformationToken(v17, TokenGroups, v67, v58, &v58);
          }
          if ( v18 >= 0 )
            goto LABEL_28;
LABEL_126:
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
          v10 = 0;
          goto LABEL_127;
        }
LABEL_54:
        v4 = -1073741823;
        goto LABEL_55;
      }
      TokenInformationLength = 0;
      v16 = NtQueryInformationToken(v15, TokenUser, v61, 0x80u, &TokenInformationLength);
      if ( v16 == -1073741789 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
        v61 = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
        v9 = v61;
        if ( !v61 )
          goto LABEL_53;
        v16 = NtQueryInformationToken(v15, TokenUser, v61, TokenInformationLength, &TokenInformationLength);
      }
      if ( v16 >= 0 )
        goto LABEL_20;
LABEL_53:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
      v9 = 0;
      goto LABEL_54;
    }
    goto LABEL_123;
  }
  v4 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x2000Au, &TokenHandle);
  if ( v4 >= 0 )
    goto LABEL_139;
LABEL_132:
  if ( TokenHandle )
    NtClose(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b340  push    rbp
0x18000b342  push    rbx
0x18000b343  push    rdi
0x18000b344  push    r12
0x18000b346  push    r14
0x18000b348  push    r15
0x18000b34a  lea     rbp, [rsp-8]
0x18000b34f  sub     rsp, 108h
0x18000b356  mov     rax, cs:__security_cookie
0x18000b35d  xor     rax, rsp
0x18000b360  mov     [rbp+30h+var_38], rax
0x18000b364  xor     ebx, ebx
0x18000b366  mov     [rbp+30h+var_70], r9
0x18000b36a  mov     [rbp+30h+var_50], rdx
0x18000b36e  mov     r15, r9
0x18000b371  mov     [rbp+30h+var_48], rcx
0x18000b375  mov     r14, rdx
0x18000b378  mov     [rsp+130h+TokenHandle], r8
0x18000b37d  mov     r12d, ebx
0x18000b380  mov     dword ptr [rbp+30h+IdentifierAuthority.Value], 0
0x18000b387  mov     word ptr [rbp+30h+IdentifierAuthority.Value+4], 500h
0x18000b38d  mov     [rbp+30h+Sid1], rbx
0x18000b391  mov     [rsp+130h+var_CC], ebx
0x18000b395  mov     [rbp+30h+var_60], rbx
0x18000b399  mov     dword ptr [rbp+30h+var_88], ebx
0x18000b39c  mov     [rbp+30h+var_B0], rbx
0x18000b3a0  mov     [rbp+30h+var_58], rbx
0x18000b3a4  test    rdx, rdx
0x18000b3a7  jz      loc_18000BDC3
0x18000b3ad  test    r9, r9
0x18000b3b0  jz      loc_18000BDE1
0x18000b3b6  mov     [r9], ebx
0x18000b3b9  test    r8, r8
0x18000b3bc  jz      loc_18000BDE8
0x18000b3c2  mov     dil, 1
0x18000b3c5  mov     [rsp+130h+var_CF], dil
0x18000b3ca  mov     rcx, [rsp+130h+TokenHandle]
0x18000b3cf  call    IsSystemProcessOrService
0x18000b3d4  test    eax, eax
0x18000b3d6  jnz     loc_18000BCF6
0x18000b3dc  cmp     [r14+0Ch], r12d
0x18000b3e0  jnz     loc_18000B716
0x18000b3e6  mov     [rsp+130h+arg_0], rsi
0x18000b3ee  mov     rsi, rbx
0x18000b3f1  mov     [rsp+130h+var_30], r13
0x18000b3f9  mov     r13, rbx
0x18000b3fc  mov     [rbp+30h+P], rbx
0x18000b400  mov     rbx, [rsp+130h+TokenHandle]
0x18000b405  mov     [rsp+130h+var_D0], r12b
0x18000b40a  cmp     [r14+38h], r12d
0x18000b40e  jnz     loc_18000B927
0x18000b414  xor     r10d, r10d
0x18000b417  mov     [rbp+30h+var_A8], r10
0x18000b41b  test    rbx, rbx
0x18000b41e  jz      short loc_18000B484
0x18000b420  mov     rcx, gs:60h
0x18000b429  xor     edx, edx; Flags
0x18000b42b  mov     r8d, 80h; Size
0x18000b431  mov     rcx, [rcx+30h]; HeapHandle
0x18000b435  call    cs:__imp_RtlAllocateHeap
0x18000b43b  mov     [rbp+30h+var_A8], rax
0x18000b43f  mov     r10, rax
0x18000b442  test    rax, rax
0x18000b445  jz      short loc_18000B484
0x18000b447  lea     rax, [rsp+130h+var_BC]
0x18000b44c  mov     [rsp+130h+var_BC], r12d
0x18000b451  mov     r9d, 80h; TokenInformationLength
0x18000b457  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x18000b45c  mov     r8, r10; TokenInformation
0x18000b45f  mov     edx, 3; TokenInformationClass
0x18000b464  mov     rcx, rbx; TokenHandle
0x18000b467  call    cs:__imp_NtQueryInformationToken
0x18000b46d  cmp     eax, 0C0000023h
0x18000b472  jz      loc_18000BAFA
0x18000b478  test    eax, eax
0x18000b47a  js      loc_18000BE9C
0x18000b480  mov     r10, [rbp+30h+var_A8]
0x18000b484  test    r10, r10
0x18000b487  jz      loc_18000BD1A
0x18000b48d  xor     edi, edi
0x18000b48f  mov     [rbp+30h+var_98], rdi
0x18000b493  mov     edx, edi
0x18000b495  mov     [rsp+130h+var_CE], dil
0x18000b49a  cmp     edx, [r14+40h]
0x18000b49e  jb      loc_18000BEA5
0x18000b4a4  mov     rbx, [rsp+130h+TokenHandle]
0x18000b4a9  mov     rsi, rdi
0x18000b4ac  mov     [rbp+30h+var_A0], rdi
0x18000b4b0  test    rbx, rbx
0x18000b4b3  jz      short loc_18000B514
0x18000b4b5  mov     rcx, gs:60h
0x18000b4be  xor     edx, edx; Flags
0x18000b4c0  mov     r8d, 80h; Size
0x18000b4c6  mov     rcx, [rcx+30h]; HeapHandle
0x18000b4ca  call    cs:__imp_RtlAllocateHeap
0x18000b4d0  mov     [rbp+30h+var_A0], rax
0x18000b4d4  mov     rsi, rax
0x18000b4d7  test    rax, rax
0x18000b4da  jz      short loc_18000B514
0x18000b4dc  lea     rax, [rsp+130h+TokenInformationLength]
0x18000b4e1  mov     [rsp+130h+TokenInformationLength], edi
0x18000b4e5  mov     r9d, 80h; TokenInformationLength
0x18000b4eb  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x18000b4f0  mov     r8, rsi; TokenInformation
0x18000b4f3  mov     edx, 1; TokenInformationClass
0x18000b4f8  mov     rcx, rbx; TokenHandle
0x18000b4fb  call    cs:__imp_NtQueryInformationToken
0x18000b501  cmp     eax, 0C0000023h
0x18000b506  jz      loc_18000B9E4
0x18000b50c  test    eax, eax
0x18000b50e  js      loc_18000B722
0x18000b514  test    rsi, rsi
0x18000b517  jz      loc_18000B73D
0x18000b51d  mov     r8d, [r14+2Ch]
0x18000b521  cmp     [r14+24h], r12d
0x18000b525  jz      loc_18000BA4B
0x18000b52b  mov     r9, [r14+30h]
0x18000b52f  lea     rax, [rbp+30h+var_60]
0x18000b533  mov     rdx, [rsi]; Sid1
0x18000b536  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x18000b53b  mov     qword ptr [rsp+130h+SubAuthority5], rax; __int64
0x18000b540  lea     rax, [rsp+130h+var_CC]
0x18000b545  mov     qword ptr [rsp+130h+SubAuthority4], rax; __int64
0x18000b54a  mov     qword ptr [rsp+130h+SubAuthority3], rdi; __int64
0x18000b54f  mov     dword ptr [rsp+130h+ReturnLength], edi; int
0x18000b553  call    CodeAuthzpInvertAndAddSids
0x18000b558  test    al, al
0x18000b55a  jz      loc_18000BEE6
0x18000b560  mov     r12d, [rsp+130h+var_CC]
0x18000b565  mov     [rsp+130h+var_D0], 1
0x18000b56a  mov     rbx, [rsp+130h+TokenHandle]
0x18000b56f  mov     r13, rdi
0x18000b572  mov     [rbp+30h+var_78], rdi
0x18000b576  test    rbx, rbx
0x18000b579  jz      short loc_18000B5DA
0x18000b57b  mov     rcx, gs:60h
0x18000b584  xor     edx, edx; Flags
0x18000b586  mov     r8d, 80h; Size
0x18000b58c  mov     rcx, [rcx+30h]; HeapHandle
0x18000b590  call    cs:__imp_RtlAllocateHeap
0x18000b596  mov     [rbp+30h+var_78], rax
0x18000b59a  mov     r13, rax
0x18000b59d  test    rax, rax
0x18000b5a0  jz      short loc_18000B5DA
0x18000b5a2  lea     rax, [rsp+130h+var_B4]
0x18000b5a7  mov     [rsp+130h+var_B4], edi
0x18000b5ab  mov     r9d, 80h; TokenInformationLength
0x18000b5b1  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x18000b5b6  mov     r8, r13; TokenInformation
0x18000b5b9  mov     edx, 2; TokenInformationClass
0x18000b5be  mov     rcx, rbx; TokenHandle
0x18000b5c1  call    cs:__imp_NtQueryInformationToken
0x18000b5c7  cmp     eax, 0C0000023h
0x18000b5cc  jz      loc_18000BA93
0x18000b5d2  test    eax, eax
0x18000b5d4  js      loc_18000BD62
0x18000b5da  test    r13, r13
0x18000b5dd  jz      loc_18000BD7D
0x18000b5e3  lea     rax, [rbp+30h+Sid1]
0x18000b5e7  xor     r9d, r9d; SubAuthority1
0x18000b5ea  mov     [rsp+130h+Sid], rax; Sid
0x18000b5ef  lea     rcx, [rbp+30h+IdentifierAuthority]; IdentifierAuthority
0x18000b5f3  mov     [rsp+130h+SubAuthority7], edi; SubAuthority7
0x18000b5f7  mov     r8d, 0Ah; SubAuthority0
0x18000b5fd  mov     [rsp+130h+SubAuthority6], edi; SubAuthority6
0x18000b601  mov     dl, 1; SubAuthorityCount
0x18000b603  mov     [rsp+130h+SubAuthority5], edi; SubAuthority5
0x18000b607  mov     [rsp+130h+SubAuthority4], edi; SubAuthority4
0x18000b60b  mov     [rsp+130h+SubAuthority3], edi; SubAuthority3
0x18000b60f  mov     dword ptr [rsp+130h+ReturnLength], edi; SubAuthority2
0x18000b613  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000b619  mov     ebx, eax
0x18000b61b  test    eax, eax
0x18000b61d  js      loc_18000B6FA
0x18000b623  mov     edx, edi
0x18000b625  mov     [rbp+30h+var_8C], edx
0x18000b628  cmp     edx, r12d
0x18000b62b  jnb     loc_18000B86B
0x18000b631  lea     rdi, [r13+8]
0x18000b635  test    rdi, rdi
0x18000b638  jz      loc_18000B70F
0x18000b63e  mov     rax, [rbp+30h+var_60]
0x18000b642  mov     r15, [rsi]
0x18000b645  mov     r14, [rbp+30h+Sid1]
0x18000b649  mov     r13d, [r13+0]
0x18000b64d  mov     ecx, edx
0x18000b64f  add     rcx, rcx
0x18000b652  mov     r12, [rax+rcx*8]
0x18000b656  test    r15, r15
0x18000b659  jz      short loc_18000B672
0x18000b65b  test    r14, r14
0x18000b65e  jz      short loc_18000B672
0x18000b660  mov     rdx, r12; Sid2
0x18000b663  mov     rcx, r14; Sid1
0x18000b666  call    cs:__imp_RtlEqualSid
0x18000b66c  test    al, al
0x18000b66e  cmovnz  r12, r15
0x18000b672  movzx   eax, byte ptr [r12+1]
0x18000b678  xor     esi, esi
0x18000b67a  lea     ecx, ds:8[rax*4]
0x18000b681  mov     [rbp+30h+var_90], ecx
0x18000b684  cmp     esi, r13d
0x18000b687  jnb     short loc_18000B6FF
0x18000b689  test    byte ptr [rdi+8], 4
0x18000b68d  jz      short loc_18000B6C9
0x18000b68f  mov     rbx, [rdi]
0x18000b692  test    r14, r14
0x18000b695  jz      short loc_18000B6B1
0x18000b697  test    r15, r15
0x18000b69a  jz      short loc_18000B6B1
0x18000b69c  mov     rdx, rbx; Sid2
0x18000b69f  mov     rcx, r14; Sid1
0x18000b6a2  call    cs:__imp_RtlEqualSid
0x18000b6a8  mov     ecx, [rbp+30h+var_90]
0x18000b6ab  test    al, al
0x18000b6ad  cmovnz  rbx, r15
0x18000b6b1  movzx   eax, byte ptr [rbx]
0x18000b6b4  cmp     [r12], al
0x18000b6b8  jnz     short loc_18000B6C9
0x18000b6ba  movzx   eax, byte ptr [rbx+1]
0x18000b6be  lea     eax, ds:8[rax*4]
0x18000b6c5  cmp     ecx, eax
0x18000b6c7  jz      short loc_18000B6D4
0x18000b6c9  mov     ecx, [rbp+30h+var_90]
0x18000b6cc  add     rdi, 10h
0x18000b6d0  inc     esi
0x18000b6d2  jmp     short loc_18000B684
0x18000b6d4  mov     r8d, ecx; Size
0x18000b6d7  mov     rdx, rbx; Buf2
0x18000b6da  mov     rcx, r12; Buf1
0x18000b6dd  call    memcmp_0
0x18000b6e2  test    eax, eax
0x18000b6e4  jnz     short loc_18000B6C9
0x18000b6e6  mov     rax, [rbp+30h+var_70]
0x18000b6ea  xor     ebx, ebx
0x18000b6ec  mov     r13, [rbp+30h+var_78]
0x18000b6f0  mov     rsi, [rbp+30h+var_A0]
0x18000b6f4  mov     dword ptr [rax], 0FFFFFFFFh
0x18000b6fa  xor     r12b, r12b
0x18000b6fd  jmp     short loc_18000B742
0x18000b6ff  mov     edx, [rbp+30h+var_8C]
0x18000b702  mov     r12d, [rsp+130h+var_CC]
0x18000b707  mov     r13, [rbp+30h+var_78]
0x18000b70b  mov     rsi, [rbp+30h+var_A0]
0x18000b70f  inc     edx
0x18000b711  jmp     loc_18000B625
0x18000b716  mov     dword ptr [r15], 0FFFFFFFFh
0x18000b71d  jmp     loc_18000B843
0x18000b722  mov     rcx, gs:60h
0x18000b72b  mov     r8, rsi; P
0x18000b72e  xor     edx, edx; Flags
0x18000b730  mov     rcx, [rcx+30h]; HeapHandle
0x18000b734  call    cs:__imp_RtlFreeHeap
0x18000b73a  mov     rsi, rdi
0x18000b73d  mov     ebx, 0C0000001h
0x18000b742  mov     r14, [rbp+30h+var_B0]
0x18000b746  mov     rcx, [rbp+30h+Sid1]; Sid
0x18000b74a  test    rcx, rcx
0x18000b74d  jz      short loc_18000B755
0x18000b74f  call    cs:__imp_RtlFreeSid
0x18000b755  mov     rax, [rbp+30h+P]
0x18000b759  test    rax, rax
0x18000b75c  jz      short loc_18000B776
0x18000b75e  mov     rcx, gs:60h
0x18000b767  mov     r8, rax; P
0x18000b76a  xor     edx, edx; Flags
0x18000b76c  mov     rcx, [rcx+30h]; HeapHandle
0x18000b770  call    cs:__imp_RtlFreeHeap
0x18000b776  test    r13, r13
0x18000b779  jz      short loc_18000B793
0x18000b77b  mov     rcx, gs:60h
0x18000b784  mov     r8, r13; P
0x18000b787  xor     edx, edx; Flags
0x18000b789  mov     rcx, [rcx+30h]; HeapHandle
0x18000b78d  call    cs:__imp_RtlFreeHeap
0x18000b793  mov     rax, [rbp+30h+var_A8]
0x18000b797  test    rax, rax
0x18000b79a  jz      short loc_18000B7B4
0x18000b79c  mov     rcx, gs:60h
0x18000b7a5  mov     r8, rax; P
0x18000b7a8  xor     edx, edx; Flags
0x18000b7aa  mov     rcx, [rcx+30h]; HeapHandle
0x18000b7ae  call    cs:__imp_RtlFreeHeap
0x18000b7b4  test    rsi, rsi
0x18000b7b7  jz      short loc_18000B7D1
0x18000b7b9  mov     rcx, gs:60h
0x18000b7c2  mov     r8, rsi; P
0x18000b7c5  xor     edx, edx; Flags
0x18000b7c7  mov     rcx, [rcx+30h]; HeapHandle
0x18000b7cb  call    cs:__imp_RtlFreeHeap
0x18000b7d1  cmp     [rsp+130h+var_D0], 0
0x18000b7d6  jz      short loc_18000B7F1
0x18000b7d8  mov     rcx, gs:60h
0x18000b7e1  xor     edx, edx; Flags
0x18000b7e3  mov     r8, [rbp+30h+var_60]; P
0x18000b7e7  mov     rcx, [rcx+30h]; HeapHandle
0x18000b7eb  call    cs:__imp_RtlFreeHeap
0x18000b7f1  test    r12b, r12b
0x18000b7f4  jz      short loc_18000B80E
0x18000b7f6  mov     rcx, gs:60h
  ... truncated ...
```
