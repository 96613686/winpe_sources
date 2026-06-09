# __CodeAuthzpCompareCodeAuthzLevelWithToken

- ea: `0x180010910`
- end: `0x1800115e9`
- name: `__CodeAuthzpCompareCodeAuthzLevelWithToken`
- size: `3289`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f840`
- `0x180010780`

## callees

- `0x180010910`
- `0x1800115f0`
- `0x1800117d0`
- `0x180011dd0`
- `0x180021be0`
- `0x180072036`
- `0x18007204e`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtClose` at `0x18001149d`
- `ntdll!NtClose` at `0x18001149d`
- `ntdll!NtOpenThreadToken` at `0x1800114d1`
- `ntdll!NtOpenThreadToken` at `0x1800114d1`
- `ntdll!NtOpenProcessToken` at `0x1800114f7`
- `ntdll!NtOpenProcessToken` at `0x1800114f7`
- `ntdll!RtlEqualSid` at `0x180010c60`
- `ntdll!RtlEqualSid` at `0x180010ca2`
- `ntdll!RtlEqualSid` at `0x180010c60`
- `ntdll!RtlEqualSid` at `0x180010ca2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180010c07`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180010c07`
- `ntdll!RtlFreeSid` at `0x180010d5b`
- `ntdll!RtlFreeSid` at `0x180010d5b`
- `ntdll!RtlFreeHeap` at `0x180010d3a`
- `ntdll!RtlFreeHeap` at `0x180010d82`
- `ntdll!RtlFreeHeap` at `0x180010da5`
- `ntdll!RtlFreeHeap` at `0x180010dcc`
- `ntdll!RtlFreeHeap` at `0x180010def`
- `ntdll!RtlFreeHeap` at `0x180010e15`
- `ntdll!RtlFreeHeap` at `0x180010e38`
- `ntdll!RtlFreeHeap` at `0x180010e5e`
- `ntdll!RtlFreeHeap` at `0x18001104b`
- `ntdll!RtlFreeHeap` at `0x18001110c`
- `ntdll!RtlFreeHeap` at `0x180011186`
- `ntdll!RtlFreeHeap` at `0x1800111fc`
- `ntdll!RtlFreeHeap` at `0x1800112bb`
- `ntdll!RtlFreeHeap` at `0x1800113c3`
- `ntdll!RtlFreeHeap` at `0x180011402`
- `ntdll!RtlFreeHeap` at `0x18001142f`
- `ntdll!RtlFreeHeap` at `0x18001145d`
- `ntdll!RtlFreeHeap` at `0x180010d3a`
- `ntdll!RtlFreeHeap` at `0x180010d82`
- `ntdll!RtlFreeHeap` at `0x180010da5`
- `ntdll!RtlFreeHeap` at `0x180010dcc`
- `ntdll!RtlFreeHeap` at `0x180010def`
- `ntdll!RtlFreeHeap` at `0x180010e15`
- `ntdll!RtlFreeHeap` at `0x180010e38`
- `ntdll!RtlFreeHeap` at `0x180010e5e`
- `ntdll!RtlFreeHeap` at `0x18001104b`
- `ntdll!RtlFreeHeap` at `0x18001110c`
- `ntdll!RtlFreeHeap` at `0x180011186`
- `ntdll!RtlFreeHeap` at `0x1800111fc`
- `ntdll!RtlFreeHeap` at `0x1800112bb`
- `ntdll!RtlFreeHeap` at `0x1800113c3`
- `ntdll!RtlFreeHeap` at `0x180011402`
- `ntdll!RtlFreeHeap` at `0x18001142f`
- `ntdll!RtlFreeHeap` at `0x18001145d`
- `ntdll!NtQueryInformationToken` at `0x180010a3d`
- `ntdll!NtQueryInformationToken` at `0x180010add`
- `ntdll!NtQueryInformationToken` at `0x180010baf`
- `ntdll!NtQueryInformationToken` at `0x180010f25`
- `ntdll!NtQueryInformationToken` at `0x180010fd2`
- `ntdll!NtQueryInformationToken` at `0x1800110a1`
- `ntdll!NtQueryInformationToken` at `0x180011162`
- `ntdll!NtQueryInformationToken` at `0x1800111d9`
- `ntdll!NtQueryInformationToken` at `0x180011252`
- `ntdll!NtQueryInformationToken` at `0x180011311`
- `ntdll!NtQueryInformationToken` at `0x180010a3d`
- `ntdll!NtQueryInformationToken` at `0x180010add`
- `ntdll!NtQueryInformationToken` at `0x180010baf`
- `ntdll!NtQueryInformationToken` at `0x180010f25`
- `ntdll!NtQueryInformationToken` at `0x180010fd2`
- `ntdll!NtQueryInformationToken` at `0x1800110a1`
- `ntdll!NtQueryInformationToken` at `0x180011162`
- `ntdll!NtQueryInformationToken` at `0x1800111d9`
- `ntdll!NtQueryInformationToken` at `0x180011252`
- `ntdll!NtQueryInformationToken` at `0x180011311`
- `ntdll!RtlAllocateHeap` at `0x180010a05`
- `ntdll!RtlAllocateHeap` at `0x180010aa6`
- `ntdll!RtlAllocateHeap` at `0x180010b78`
- `ntdll!RtlAllocateHeap` at `0x180010eea`
- `ntdll!RtlAllocateHeap` at `0x180010f96`
- `ntdll!RtlAllocateHeap` at `0x18001106b`
- `ntdll!RtlAllocateHeap` at `0x18001112c`
- `ntdll!RtlAllocateHeap` at `0x1800111a6`
- `ntdll!RtlAllocateHeap` at `0x18001121c`
- `ntdll!RtlAllocateHeap` at `0x1800112db`
- `ntdll!RtlAllocateHeap` at `0x180010a05`
- `ntdll!RtlAllocateHeap` at `0x180010aa6`
- `ntdll!RtlAllocateHeap` at `0x180010b78`
- `ntdll!RtlAllocateHeap` at `0x180010eea`
- `ntdll!RtlAllocateHeap` at `0x180010f96`
- `ntdll!RtlAllocateHeap` at `0x18001106b`
- `ntdll!RtlAllocateHeap` at `0x18001112c`
- `ntdll!RtlAllocateHeap` at `0x1800111a6`
- `ntdll!RtlAllocateHeap` at `0x18001121c`
- `ntdll!RtlAllocateHeap` at `0x1800112db`

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
0x180010910  push    rbp
0x180010912  push    rbx
0x180010913  push    rdi
0x180010914  push    r12
0x180010916  push    r14
0x180010918  push    r15
0x18001091a  lea     rbp, [rsp-8]
0x18001091f  sub     rsp, 108h
0x180010926  mov     rax, cs:__security_cookie
0x18001092d  xor     rax, rsp
0x180010930  mov     [rbp+30h+var_38], rax
0x180010934  xor     ebx, ebx
0x180010936  mov     [rbp+30h+var_70], r9
0x18001093a  mov     [rbp+30h+var_50], rdx
0x18001093e  mov     r15, r9
0x180010941  mov     [rbp+30h+var_48], rcx
0x180010945  mov     r14, rdx
0x180010948  mov     [rsp+130h+TokenHandle], r8
0x18001094d  mov     r12d, ebx
0x180010950  mov     dword ptr [rbp+30h+IdentifierAuthority.Value], 0
0x180010957  mov     word ptr [rbp+30h+IdentifierAuthority.Value+4], 500h
0x18001095d  mov     [rbp+30h+Sid1], rbx
0x180010961  mov     [rsp+130h+var_CC], ebx
0x180010965  mov     [rbp+30h+var_60], rbx
0x180010969  mov     dword ptr [rbp+30h+var_88], ebx
0x18001096c  mov     [rbp+30h+var_B0], rbx
0x180010970  mov     [rbp+30h+var_58], rbx
0x180010974  test    rdx, rdx
0x180010977  jz      loc_18001148A
0x18001097d  test    r9, r9
0x180010980  jz      loc_1800114AE
0x180010986  mov     [r9], ebx
0x180010989  test    r8, r8
0x18001098c  jz      loc_1800114B5
0x180010992  mov     dil, 1
0x180010995  mov     [rsp+130h+var_CF], dil
0x18001099a  mov     rcx, [rsp+130h+TokenHandle]
0x18001099f  call    IsSystemProcessOrService
0x1800109a4  test    eax, eax
0x1800109a6  jnz     loc_1800113A5
0x1800109ac  cmp     [r14+0Ch], r12d
0x1800109b0  jnz     loc_180010D1C
0x1800109b6  mov     [rsp+130h+arg_0], rsi
0x1800109be  mov     rsi, rbx
0x1800109c1  mov     [rsp+130h+var_30], r13
0x1800109c9  mov     r13, rbx
0x1800109cc  mov     [rbp+30h+P], rbx
0x1800109d0  mov     rbx, [rsp+130h+TokenHandle]
0x1800109d5  mov     [rsp+130h+var_D0], r12b
0x1800109da  cmp     [r14+38h], r12d
0x1800109de  jnz     loc_180010F70
0x1800109e4  xor     r10d, r10d
0x1800109e7  mov     [rbp+30h+var_A8], r10
0x1800109eb  test    rbx, rbx
0x1800109ee  jz      short loc_180010A60
0x1800109f0  mov     rcx, gs:60h
0x1800109f9  xor     edx, edx; Flags
0x1800109fb  mov     r8d, 80h; Size
0x180010a01  mov     rcx, [rcx+30h]; HeapHandle
0x180010a05  call    cs:__imp_RtlAllocateHeap
0x180010a0c  nop     dword ptr [rax+rax+00h]
0x180010a11  mov     [rbp+30h+var_A8], rax
0x180010a15  mov     r10, rax
0x180010a18  test    rax, rax
0x180010a1b  jz      short loc_180010A60
0x180010a1d  lea     rax, [rsp+130h+var_BC]
0x180010a22  mov     [rsp+130h+var_BC], r12d
0x180010a27  mov     r9d, 80h; TokenInformationLength
0x180010a2d  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x180010a32  mov     r8, r10; TokenInformation
0x180010a35  mov     edx, 3; TokenInformationClass
0x180010a3a  mov     rcx, rbx; TokenHandle
0x180010a3d  call    cs:__imp_NtQueryInformationToken
0x180010a44  nop     dword ptr [rax+rax+00h]
0x180010a49  cmp     eax, 0C0000023h
0x180010a4e  jz      loc_180011173
0x180010a54  test    eax, eax
0x180010a56  js      loc_180011575
0x180010a5c  mov     r10, [rbp+30h+var_A8]
0x180010a60  test    r10, r10
0x180010a63  jz      loc_1800113CF
0x180010a69  xor     edi, edi
0x180010a6b  mov     [rbp+30h+var_98], rdi
0x180010a6f  mov     edx, edi
0x180010a71  mov     [rsp+130h+var_CE], dil
0x180010a76  cmp     edx, [r14+40h]
0x180010a7a  jb      loc_18001157E
0x180010a80  mov     rbx, [rsp+130h+TokenHandle]
0x180010a85  mov     rsi, rdi
0x180010a88  mov     [rbp+30h+var_A0], rdi
0x180010a8c  test    rbx, rbx
0x180010a8f  jz      short loc_180010AFC
0x180010a91  mov     rcx, gs:60h
0x180010a9a  xor     edx, edx; Flags
0x180010a9c  mov     r8d, 80h; Size
0x180010aa2  mov     rcx, [rcx+30h]; HeapHandle
0x180010aa6  call    cs:__imp_RtlAllocateHeap
0x180010aad  nop     dword ptr [rax+rax+00h]
0x180010ab2  mov     [rbp+30h+var_A0], rax
0x180010ab6  mov     rsi, rax
0x180010ab9  test    rax, rax
0x180010abc  jz      short loc_180010AFC
0x180010abe  lea     rax, [rsp+130h+TokenInformationLength]
0x180010ac3  mov     [rsp+130h+TokenInformationLength], edi
0x180010ac7  mov     r9d, 80h; TokenInformationLength
0x180010acd  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x180010ad2  mov     r8, rsi; TokenInformation
0x180010ad5  mov     edx, 1; TokenInformationClass
0x180010ada  mov     rcx, rbx; TokenHandle
0x180010add  call    cs:__imp_NtQueryInformationToken
0x180010ae4  nop     dword ptr [rax+rax+00h]
0x180010ae9  cmp     eax, 0C0000023h
0x180010aee  jz      loc_180011039
0x180010af4  test    eax, eax
0x180010af6  js      loc_180010D28
0x180010afc  test    rsi, rsi
0x180010aff  jz      loc_180010D49
0x180010b05  mov     r8d, [r14+2Ch]
0x180010b09  cmp     [r14+24h], r12d
0x180010b0d  jz      loc_1800110B2
0x180010b13  mov     r9, [r14+30h]
0x180010b17  lea     rax, [rbp+30h+var_60]
0x180010b1b  mov     rdx, [rsi]; Sid1
0x180010b1e  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x180010b23  mov     qword ptr [rsp+130h+SubAuthority5], rax; __int64
0x180010b28  lea     rax, [rsp+130h+var_CC]
0x180010b2d  mov     qword ptr [rsp+130h+SubAuthority4], rax; __int64
0x180010b32  mov     qword ptr [rsp+130h+SubAuthority3], rdi; __int64
0x180010b37  mov     dword ptr [rsp+130h+ReturnLength], edi; int
0x180010b3b  call    CodeAuthzpInvertAndAddSids
0x180010b40  test    al, al
0x180010b42  jz      loc_1800115BF
0x180010b48  mov     r12d, [rsp+130h+var_CC]
0x180010b4d  mov     [rsp+130h+var_D0], 1
0x180010b52  mov     rbx, [rsp+130h+TokenHandle]
0x180010b57  mov     r13, rdi
0x180010b5a  mov     [rbp+30h+var_78], rdi
0x180010b5e  test    rbx, rbx
0x180010b61  jz      short loc_180010BCE
0x180010b63  mov     rcx, gs:60h
0x180010b6c  xor     edx, edx; Flags
0x180010b6e  mov     r8d, 80h; Size
0x180010b74  mov     rcx, [rcx+30h]; HeapHandle
0x180010b78  call    cs:__imp_RtlAllocateHeap
0x180010b7f  nop     dword ptr [rax+rax+00h]
0x180010b84  mov     [rbp+30h+var_78], rax
0x180010b88  mov     r13, rax
0x180010b8b  test    rax, rax
0x180010b8e  jz      short loc_180010BCE
0x180010b90  lea     rax, [rsp+130h+var_B4]
0x180010b95  mov     [rsp+130h+var_B4], edi
0x180010b99  mov     r9d, 80h; TokenInformationLength
0x180010b9f  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x180010ba4  mov     r8, r13; TokenInformation
0x180010ba7  mov     edx, 2; TokenInformationClass
0x180010bac  mov     rcx, rbx; TokenHandle
0x180010baf  call    cs:__imp_NtQueryInformationToken
0x180010bb6  nop     dword ptr [rax+rax+00h]
0x180010bbb  cmp     eax, 0C0000023h
0x180010bc0  jz      loc_1800110FA
0x180010bc6  test    eax, eax
0x180010bc8  js      loc_18001141D
0x180010bce  test    r13, r13
0x180010bd1  jz      loc_18001143E
0x180010bd7  lea     rax, [rbp+30h+Sid1]
0x180010bdb  xor     r9d, r9d; SubAuthority1
0x180010bde  mov     [rsp+130h+Sid], rax; Sid
0x180010be3  lea     rcx, [rbp+30h+IdentifierAuthority]; IdentifierAuthority
0x180010be7  mov     [rsp+130h+SubAuthority7], edi; SubAuthority7
0x180010beb  mov     r8d, 0Ah; SubAuthority0
0x180010bf1  mov     [rsp+130h+SubAuthority6], edi; SubAuthority6
0x180010bf5  mov     dl, 1; SubAuthorityCount
0x180010bf7  mov     [rsp+130h+SubAuthority5], edi; SubAuthority5
0x180010bfb  mov     [rsp+130h+SubAuthority4], edi; SubAuthority4
0x180010bff  mov     [rsp+130h+SubAuthority3], edi; SubAuthority3
0x180010c03  mov     dword ptr [rsp+130h+ReturnLength], edi; SubAuthority2
0x180010c07  call    cs:__imp_RtlAllocateAndInitializeSid
0x180010c0e  nop     dword ptr [rax+rax+00h]
0x180010c13  mov     ebx, eax
0x180010c15  test    eax, eax
0x180010c17  js      loc_180010D00
0x180010c1d  mov     edx, edi
0x180010c1f  mov     [rbp+30h+var_8C], edx
0x180010c22  cmp     edx, r12d
0x180010c25  jnb     loc_180010EA8
0x180010c2b  lea     rdi, [r13+8]
0x180010c2f  test    rdi, rdi
0x180010c32  jz      loc_180010D15
0x180010c38  mov     rax, [rbp+30h+var_60]
0x180010c3c  mov     r15, [rsi]
0x180010c3f  mov     r14, [rbp+30h+Sid1]
0x180010c43  mov     r13d, [r13+0]
0x180010c47  mov     ecx, edx
0x180010c49  add     rcx, rcx
0x180010c4c  mov     r12, [rax+rcx*8]
0x180010c50  test    r15, r15
0x180010c53  jz      short loc_180010C72
0x180010c55  test    r14, r14
0x180010c58  jz      short loc_180010C72
0x180010c5a  mov     rdx, r12; Sid2
0x180010c5d  mov     rcx, r14; Sid1
0x180010c60  call    cs:__imp_RtlEqualSid
0x180010c67  nop     dword ptr [rax+rax+00h]
0x180010c6c  test    al, al
0x180010c6e  cmovnz  r12, r15
0x180010c72  movzx   eax, byte ptr [r12+1]
0x180010c78  xor     esi, esi
0x180010c7a  lea     ecx, ds:8[rax*4]
0x180010c81  mov     [rbp+30h+var_90], ecx
0x180010c84  cmp     esi, r13d
0x180010c87  jnb     short loc_180010D05
0x180010c89  test    byte ptr [rdi+8], 4
0x180010c8d  jz      short loc_180010CCF
0x180010c8f  mov     rbx, [rdi]
0x180010c92  test    r14, r14
0x180010c95  jz      short loc_180010CB7
0x180010c97  test    r15, r15
0x180010c9a  jz      short loc_180010CB7
0x180010c9c  mov     rdx, rbx; Sid2
0x180010c9f  mov     rcx, r14; Sid1
0x180010ca2  call    cs:__imp_RtlEqualSid
0x180010ca9  nop     dword ptr [rax+rax+00h]
0x180010cae  mov     ecx, [rbp+30h+var_90]
0x180010cb1  test    al, al
0x180010cb3  cmovnz  rbx, r15
0x180010cb7  movzx   eax, byte ptr [rbx]
0x180010cba  cmp     [r12], al
0x180010cbe  jnz     short loc_180010CCF
0x180010cc0  movzx   eax, byte ptr [rbx+1]
0x180010cc4  lea     eax, ds:8[rax*4]
0x180010ccb  cmp     ecx, eax
0x180010ccd  jz      short loc_180010CDA
0x180010ccf  mov     ecx, [rbp+30h+var_90]
0x180010cd2  add     rdi, 10h
0x180010cd6  inc     esi
0x180010cd8  jmp     short loc_180010C84
0x180010cda  mov     r8d, ecx; Size
0x180010cdd  mov     rdx, rbx; Buf2
0x180010ce0  mov     rcx, r12; Buf1
0x180010ce3  call    memcmp_0
0x180010ce8  test    eax, eax
0x180010cea  jnz     short loc_180010CCF
0x180010cec  mov     rax, [rbp+30h+var_70]
0x180010cf0  xor     ebx, ebx
0x180010cf2  mov     r13, [rbp+30h+var_78]
0x180010cf6  mov     rsi, [rbp+30h+var_A0]
0x180010cfa  mov     dword ptr [rax], 0FFFFFFFFh
0x180010d00  xor     r12b, r12b
0x180010d03  jmp     short loc_180010D4E
0x180010d05  mov     edx, [rbp+30h+var_8C]
0x180010d08  mov     r12d, [rsp+130h+var_CC]
0x180010d0d  mov     r13, [rbp+30h+var_78]
0x180010d11  mov     rsi, [rbp+30h+var_A0]
0x180010d15  inc     edx
0x180010d17  jmp     loc_180010C1F
0x180010d1c  mov     dword ptr [r15], 0FFFFFFFFh
0x180010d23  jmp     loc_180010E7F
0x180010d28  mov     rcx, gs:60h
0x180010d31  mov     r8, rsi; P
0x180010d34  xor     edx, edx; Flags
0x180010d36  mov     rcx, [rcx+30h]; HeapHandle
0x180010d3a  call    cs:__imp_RtlFreeHeap
0x180010d41  nop     dword ptr [rax+rax+00h]
0x180010d46  mov     rsi, rdi
0x180010d49  mov     ebx, 0C0000001h
0x180010d4e  mov     r14, [rbp+30h+var_B0]
0x180010d52  mov     rcx, [rbp+30h+Sid1]; Sid
0x180010d56  test    rcx, rcx
0x180010d59  jz      short loc_180010D67
0x180010d5b  call    cs:__imp_RtlFreeSid
0x180010d62  nop     dword ptr [rax+rax+00h]
0x180010d67  mov     rax, [rbp+30h+P]
0x180010d6b  test    rax, rax
0x180010d6e  jz      short loc_180010D8E
0x180010d70  mov     rcx, gs:60h
0x180010d79  mov     r8, rax; P
0x180010d7c  xor     edx, edx; Flags
0x180010d7e  mov     rcx, [rcx+30h]; HeapHandle
0x180010d82  call    cs:__imp_RtlFreeHeap
0x180010d89  nop     dword ptr [rax+rax+00h]
0x180010d8e  test    r13, r13
0x180010d91  jz      short loc_180010DB1
0x180010d93  mov     rcx, gs:60h
0x180010d9c  mov     r8, r13; P
0x180010d9f  xor     edx, edx; Flags
0x180010da1  mov     rcx, [rcx+30h]; HeapHandle
0x180010da5  call    cs:__imp_RtlFreeHeap
0x180010dac  nop     dword ptr [rax+rax+00h]
0x180010db1  mov     rax, [rbp+30h+var_A8]
0x180010db5  test    rax, rax
0x180010db8  jz      short loc_180010DD8
0x180010dba  mov     rcx, gs:60h
0x180010dc3  mov     r8, rax; P
0x180010dc6  xor     edx, edx; Flags
0x180010dc8  mov     rcx, [rcx+30h]; HeapHandle
0x180010dcc  call    cs:__imp_RtlFreeHeap
0x180010dd3  nop     dword ptr [rax+rax+00h]
0x180010dd8  test    rsi, rsi
0x180010ddb  jz      short loc_180010DFB
0x180010ddd  mov     rcx, gs:60h
  ... truncated ...
```
