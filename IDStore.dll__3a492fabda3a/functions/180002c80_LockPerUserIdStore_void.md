# LockPerUserIdStore(void * *)

- ea: `0x180002c80`
- end: `0x180003289`
- name: `?LockPerUserIdStore@@YAJPEAPEAX@Z`
- size: `1545`
- prototype: `__int64 __fastcall(void **, __int64, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012b10`
- `0x180013430`
- `0x180013b40`

## callees

- `0x180002c80`
- `0x180003290`
- `0x180003560`
- `0x1800144b4`
- `0x1800191ac`
- `0x180019210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180002f46`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180002f46`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002f74`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002f74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002eef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002eef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800031c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003132`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000307f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000307f`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x180002d75`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x180002d75`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x180002d34`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x180002d34`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180002ee6`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180002ee6`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180002dcf`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180002dcf`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x180002d55`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x180002d55`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x180002dab`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x180002dab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002df0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002df0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ef8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800031cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ef8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800031cd`

## string_xrefs

- `0x180002cf1`: `CreateSecureObjectNamespace`

## pseudocode

```c
__int64 __fastcall LockPerUserIdStore(void **a1, __int64 a2, __int64 a3)
{
  HANDLE PrivateNamespaceW; // rsi
  WCHAR *v5; // r14
  void *v6; // rbx
  int CallerTokenUserSid; // eax
  __int64 v8; // r8
  signed int v9; // edi
  void *v10; // r12
  void *v11; // r15
  void *v12; // rdi
  const WCHAR *v13; // rbx
  CIdentityProfileHandler **v14; // rdx
  __int64 v15; // r8
  unsigned int i; // edi
  signed int LastError; // eax
  WCHAR *v18; // rax
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rdx
  WCHAR *v22; // r8
  WCHAR *v23; // rcx
  int v24; // r10d
  __int64 v25; // rax
  WCHAR *v26; // rcx
  const wchar_t *v27; // rdx
  WCHAR *v28; // r8
  WCHAR *v29; // rdx
  CIdentityProfileHandler *v30; // rcx
  int v31; // edx
  __int64 v32; // r8
  CIdentityProfileHandler *v33; // rcx
  HANDLE MutexW; // rax
  signed int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r9
  signed int v39; // eax
  signed int v40; // eax
  CIdentityProfileHandler *v41; // rcx
  __int64 v42; // rdx
  signed int v43; // eax
  _QWORD v44[2]; // [rsp+30h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+40h] BYREF
  HANDLE BoundaryDescriptor; // [rsp+88h] [rbp+48h] BYREF

  PrivateNamespaceW = 0;
  v5 = 0;
  pv = 0;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "LockPerUserIdStore");
  }
  v6 = *a1;
  CallerTokenUserSid = GetCallerTokenUserSid((struct _TOKEN_USER **)&pv, a2, a3);
  v9 = CallerTokenUserSid;
  if ( CallerTokenUserSid >= 0 )
  {
    v10 = pv;
    v11 = 0;
    if ( v6 )
      goto LABEL_56;
    v12 = *(void **)pv;
    v44[1] = "CreateSecureObjectNamespace";
    v44[0] = &pv;
    BoundaryDescriptor = 0;
    LODWORD(pv) = 0;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v8, "CreateSecureObjectNamespace");
    }
    BoundaryDescriptor = CreateBoundaryDescriptorW(L"IDSTORE_BOUNDARY", 0);
    v13 = L"IDSTORE_NS";
    if ( BoundaryDescriptor )
    {
      if ( AddSIDToBoundaryDescriptor(&BoundaryDescriptor, v12) )
      {
        for ( i = 0; i < 0x64; ++i )
        {
          PrivateNamespaceW = OpenPrivateNamespaceW(BoundaryDescriptor, L"IDSTORE_NS");
          if ( PrivateNamespaceW )
            goto LABEL_18;
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          LODWORD(pv) = LastError;
          if ( (unsigned int)(LastError + 2147024894) <= 1 )
          {
            PrivateNamespaceW = CreatePrivateNamespaceW(0, BoundaryDescriptor, L"IDSTORE_NS");
            if ( PrivateNamespaceW )
            {
LABEL_18:
              LODWORD(pv) = 0;
LABEL_19:
              v11 = PrivateNamespaceW;
              goto LABEL_20;
            }
            v39 = GetLastError();
            if ( v39 > 0 )
              v39 = (unsigned __int16)v39 | 0x80070000;
            LODWORD(pv) = v39;
          }
        }
        if ( (int)pv >= 0 )
          goto LABEL_19;
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            140,
            WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
            (unsigned int)pv);
        }
        goto LABEL_20;
      }
      v40 = GetLastError();
      if ( v40 > 0 )
        v40 = (unsigned __int16)v40 | 0x80070000;
      LODWORD(pv) = v40;
      v41 = WPP_GLOBAL_Control;
      v14 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_20:
        if ( BoundaryDescriptor )
          DeleteBoundaryDescriptor(BoundaryDescriptor);
        v9 = (int)pv;
        CLogBlock::~CLogBlock((CLogBlock *)v44, (__int64)v14, v15);
        if ( v9 < 0 )
        {
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v37 = 142;
LABEL_62:
            v38 = (unsigned int)v9;
LABEL_63:
            WPP_SF_d(*((_QWORD *)v30 + 2), v37, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v38);
          }
LABEL_45:
          if ( v11 )
            ClosePrivateNamespace(v11, 0);
          goto LABEL_47;
        }
        v18 = (WCHAR *)LocalAlloc(0, 0x6Cu);
        v5 = v18;
        if ( !v18 )
        {
          v9 = -2147024882;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v37 = 143;
            v38 = 2147942414LL;
            goto LABEL_63;
          }
          goto LABEL_45;
        }
        v19 = 2147483646;
        v20 = 2147483646;
        v21 = 54;
        v22 = v18;
        do
        {
          if ( !v20 )
            break;
          if ( !*v13 )
            break;
          *v22++ = *v13++;
          --v20;
          --v21;
        }
        while ( v21 );
        v23 = v22 - 1;
        v9 = -2147024774;
        if ( v21 )
          v23 = v22;
        v24 = -2147024774;
        if ( v21 )
          v24 = 0;
        *v23 = 0;
        if ( !v21 )
        {
          v9 = v24;
          goto LABEL_44;
        }
        v25 = 54;
        v26 = v5;
        do
        {
          if ( !*v26 )
            break;
          ++v26;
          --v25;
        }
        while ( v25 );
        if ( !v25 )
        {
          v9 = -2147024809;
          goto LABEL_44;
        }
        v27 = L"\\69884752-95BE-4032-8AF1-B300F0E2CB97-Mutex";
        v28 = &v5[54 - v25];
        do
        {
          if ( !v19 )
            break;
          if ( !*v27 )
            break;
          *v28++ = *v27++;
          --v19;
          --v25;
        }
        while ( v25 );
        v29 = v28 - 1;
        if ( v25 )
        {
          v29 = v28;
          v9 = 0;
        }
        *v29 = 0;
        if ( !v25 )
        {
LABEL_44:
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v37 = 144;
            goto LABEL_62;
          }
          goto LABEL_45;
        }
        MutexW = CreateMutexW(0, 0, v5);
        if ( !MutexW )
        {
          v43 = GetLastError();
          v9 = v43;
          if ( v43 > 0 )
            v9 = (unsigned __int16)v43 | 0x80070000;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
            goto LABEL_45;
          }
          v37 = 145;
          goto LABEL_62;
        }
        v6 = (void *)_InterlockedCompareExchange64((volatile signed __int64 *)a1, (signed __int64)MutexW, 0);
        if ( v6 )
          CloseHandle(MutexW);
        else
          v6 = MutexW;
LABEL_56:
        if ( WaitForSingleObject(v6, 0xFFFFFFFF) != -1 )
          goto LABEL_45;
        v36 = GetLastError();
        v9 = v36;
        if ( v36 > 0 )
          v9 = (unsigned __int16)v36 | 0x80070000;
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_45;
        }
        v37 = 146;
        goto LABEL_62;
      }
      v42 = 139;
    }
    else
    {
      v40 = GetLastError();
      if ( v40 > 0 )
        v40 = (unsigned __int16)v40 | 0x80070000;
      LODWORD(pv) = v40;
      v41 = WPP_GLOBAL_Control;
      v14 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_20;
      }
      v42 = 138;
    }
    WPP_SF_d(*((_QWORD *)v41 + 2), v42, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, (unsigned int)v40);
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      141,
      WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
      (unsigned int)CallerTokenUserSid);
    CoTaskMemFree(pv);
    LocalFree(0);
    goto LABEL_80;
  }
  v10 = pv;
LABEL_47:
  CoTaskMemFree(v10);
  LocalFree(v5);
  if ( v9 >= 0 )
  {
LABEL_48:
    v33 = WPP_GLOBAL_Control;
    goto LABEL_49;
  }
LABEL_80:
  v33 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
    return (unsigned int)v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_sL(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, v32, (unsigned int)"LockPerUserIdStore", v9);
    goto LABEL_48;
  }
LABEL_49:
  if ( v33 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v33 + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)v33 + 2), 12, v32, "LockPerUserIdStore");
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180002c80  push    rbp
0x180002c82  push    rbx
0x180002c83  push    rsi
0x180002c84  push    rdi
0x180002c85  push    r13
0x180002c87  push    r14
0x180002c89  push    r15
0x180002c8b  mov     rbp, rsp
0x180002c8e  sub     rsp, 40h
0x180002c92  xor     esi, esi
0x180002c94  mov     r13, rcx
0x180002c97  mov     r14d, esi
0x180002c9a  mov     [rbp+pv], rsi
0x180002c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ca5  lea     r15, WPP_GLOBAL_Control
0x180002cac  cmp     rcx, r15
0x180002caf  jz      short loc_180002CBE
0x180002cb1  test    dword ptr [rcx+1Ch], 400h
0x180002cb8  jnz     loc_180003185
0x180002cbe  mov     rbx, [r13+0]
0x180002cc2  lea     rcx, [rbp+pv]; struct _TOKEN_USER **
0x180002cc6  mov     [rsp+40h+arg_10], r12
0x180002cce  call    ?GetCallerTokenUserSid@@YAJPEAPEAU_TOKEN_USER@@@Z; GetCallerTokenUserSid(_TOKEN_USER * *)
0x180002cd3  mov     edi, eax
0x180002cd5  test    eax, eax
0x180002cd7  js      loc_18000308A
0x180002cdd  mov     r12, [rbp+pv]
0x180002ce1  mov     r15, rsi
0x180002ce4  test    rbx, rbx
0x180002ce7  jnz     loc_180002F6C
0x180002ced  mov     rdi, [r12]
0x180002cf1  lea     r9, aCreatesecureob; "CreateSecureObjectNamespace"
0x180002cf8  lea     rax, [rbp+pv]
0x180002cfc  mov     [rbp+var_8], r9
0x180002d00  mov     [rbp+var_10], rax
0x180002d04  mov     [rbp+BoundaryDescriptor], rsi
0x180002d08  mov     dword ptr [rbp+pv], esi
0x180002d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d12  lea     rax, WPP_GLOBAL_Control
0x180002d19  cmp     rcx, rax
0x180002d1c  jz      short loc_180002D2B
0x180002d1e  test    dword ptr [rcx+1Ch], 400h
0x180002d25  jnz     loc_1800031D8
0x180002d2b  xor     edx, edx; Flags
0x180002d2d  lea     rcx, Name; "IDSTORE_BOUNDARY"
0x180002d34  call    cs:__imp_CreateBoundaryDescriptorW
0x180002d3a  mov     [rbp+BoundaryDescriptor], rax
0x180002d3e  lea     rbx, AliasPrefix; "IDSTORE_NS"
0x180002d45  test    rax, rax
0x180002d48  jz      loc_180003043
0x180002d4e  mov     rdx, rdi; RequiredSid
0x180002d51  lea     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x180002d55  call    cs:__imp_AddSIDToBoundaryDescriptor
0x180002d5b  test    eax, eax
0x180002d5d  jz      loc_180003132
0x180002d63  xor     edi, edi
0x180002d65  cmp     edi, 64h ; 'd'
0x180002d68  jnb     loc_180002FEE
0x180002d6e  mov     rcx, [rbp+BoundaryDescriptor]; lpBoundaryDescriptor
0x180002d72  mov     rdx, rbx; lpAliasPrefix
0x180002d75  call    cs:__imp_OpenPrivateNamespaceW
0x180002d7b  mov     rsi, rax
0x180002d7e  test    rax, rax
0x180002d81  jnz     short loc_180002DBD
0x180002d83  call    cs:__imp_GetLastError
0x180002d89  test    eax, eax
0x180002d8b  jg      loc_180003036
0x180002d91  mov     dword ptr [rbp+pv], eax
0x180002d94  add     eax, 7FF8FFFEh
0x180002d99  cmp     eax, 1
0x180002d9c  ja      loc_180002FE7
0x180002da2  mov     rdx, [rbp+BoundaryDescriptor]; lpBoundaryDescriptor
0x180002da6  mov     r8, rbx; lpAliasPrefix
0x180002da9  xor     ecx, ecx; lpPrivateNamespaceAttributes
0x180002dab  call    cs:__imp_CreatePrivateNamespaceW
0x180002db1  mov     rsi, rax
0x180002db4  test    rax, rax
0x180002db7  jz      loc_180002FD6
0x180002dbd  mov     dword ptr [rbp+pv], r14d
0x180002dc1  mov     r15, rsi
0x180002dc4  xor     esi, esi
0x180002dc6  mov     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x180002dca  test    rcx, rcx
0x180002dcd  jz      short loc_180002DD5
0x180002dcf  call    cs:__imp_DeleteBoundaryDescriptor
0x180002dd5  mov     edi, dword ptr [rbp+pv]
0x180002dd8  lea     rcx, [rbp+var_10]; this
0x180002ddc  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x180002de1  test    edi, edi
0x180002de3  js      loc_1800031EB
0x180002de9  mov     edx, 6Ch ; 'l'; uBytes
0x180002dee  xor     ecx, ecx; uFlags
0x180002df0  call    cs:__imp_LocalAlloc
0x180002df6  mov     r14, rax
0x180002df9  test    rax, rax
0x180002dfc  jz      loc_180003216
0x180002e02  mov     r9d, 7FFFFFFEh
0x180002e08  mov     r11d, 36h ; '6'
0x180002e0e  mov     ecx, r9d
0x180002e11  mov     edx, r11d
0x180002e14  mov     r8, rax
0x180002e17  test    rcx, rcx
0x180002e1a  jz      short loc_180002E39
0x180002e1c  movzx   eax, word ptr [rbx]
0x180002e1f  test    ax, ax
0x180002e22  jz      short loc_180002E39
0x180002e24  mov     [r8], ax
0x180002e28  add     rbx, 2
0x180002e2c  add     r8, 2
0x180002e30  dec     rcx
0x180002e33  sub     rdx, 1
0x180002e37  jnz     short loc_180002E17
0x180002e39  test    rdx, rdx
0x180002e3c  lea     rcx, [r8-2]
0x180002e40  mov     edi, 8007007Ah
0x180002e45  cmovnz  rcx, r8
0x180002e49  mov     r10d, edi
0x180002e4c  cmovnz  r10d, esi
0x180002e50  mov     [rcx], si
0x180002e53  jz      loc_180003253
0x180002e59  mov     rax, r11
0x180002e5c  mov     rcx, r14
0x180002e5f  nop
0x180002e60  cmp     word ptr [rcx], 0
0x180002e64  jz      short loc_180002E70
0x180002e66  add     rcx, 2
0x180002e6a  sub     rax, 1
0x180002e6e  jnz     short loc_180002E60
0x180002e70  test    rax, rax
0x180002e73  mov     edx, 80070057h
0x180002e78  cmovnz  edx, esi
0x180002e7b  jz      loc_18000324C
0x180002e81  sub     r11, rax
0x180002e84  lea     rdx, a6988475295be40; "\\69884752-95BE-4032-8AF1-B300F0E2CB97-"...
0x180002e8b  lea     r8, [r14+r11*2]
0x180002e8f  nop
0x180002e90  test    r9, r9
0x180002e93  jz      short loc_180002EB2
0x180002e95  movzx   ecx, word ptr [rdx]
0x180002e98  test    cx, cx
0x180002e9b  jz      short loc_180002EB2
0x180002e9d  mov     [r8], cx
0x180002ea1  add     rdx, 2
0x180002ea5  add     r8, 2
0x180002ea9  dec     r9
0x180002eac  sub     rax, 1
0x180002eb0  jnz     short loc_180002E90
0x180002eb2  test    rax, rax
0x180002eb5  lea     rdx, [r8-2]
0x180002eb9  cmovnz  rdx, r8
0x180002ebd  cmovnz  edi, esi
0x180002ec0  mov     [rdx], si
0x180002ec3  jnz     short loc_180002F3F
0x180002ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ecc  lea     rax, WPP_GLOBAL_Control
0x180002ed3  cmp     rcx, rax
0x180002ed6  jnz     loc_18000325B
0x180002edc  test    r15, r15
0x180002edf  jz      short loc_180002EEC
0x180002ee1  xor     edx, edx; Flags
0x180002ee3  mov     rcx, r15; Handle
0x180002ee6  call    cs:__imp_ClosePrivateNamespace
0x180002eec  mov     rcx, r12; pv
0x180002eef  call    cs:__imp_CoTaskMemFree
0x180002ef5  mov     rcx, r14; hMem
0x180002ef8  call    cs:__imp_LocalFree
0x180002efe  lea     r15, WPP_GLOBAL_Control
0x180002f05  test    edi, edi
0x180002f07  js      loc_1800030A3
0x180002f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f14  cmp     rcx, r15
0x180002f17  jz      short loc_180002F26
0x180002f19  test    dword ptr [rcx+1Ch], 400h
0x180002f20  jnz     loc_18000326F
0x180002f26  mov     r12, [rsp+40h+arg_10]
0x180002f2e  mov     eax, edi
0x180002f30  add     rsp, 40h
0x180002f34  pop     r15
0x180002f36  pop     r14
0x180002f38  pop     r13
0x180002f3a  pop     rdi
0x180002f3b  pop     rsi
0x180002f3c  pop     rbx
0x180002f3d  pop     rbp
0x180002f3e  retn
0x180002f3f  mov     r8, r14; lpName
0x180002f42  xor     edx, edx; bInitialOwner
0x180002f44  xor     ecx, ecx; lpMutexAttributes
0x180002f46  call    cs:__imp_CreateMutexW
0x180002f4c  mov     rcx, rax; hObject
0x180002f4f  test    rax, rax
0x180002f52  jz      loc_1800030E3
0x180002f58  xor     eax, eax
0x180002f5a  lock cmpxchg [r13+0], rcx
0x180002f60  mov     rbx, rax
0x180002f63  jnz     loc_18000307F
0x180002f69  mov     rbx, rcx
0x180002f6c  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180002f71  mov     rcx, rbx; hHandle
0x180002f74  call    cs:__imp_WaitForSingleObject
0x180002f7a  cmp     eax, 0FFFFFFFFh
0x180002f7d  jnz     loc_180002EDC
0x180002f83  call    cs:__imp_GetLastError
0x180002f89  mov     edi, eax
0x180002f8b  test    eax, eax
0x180002f8d  jle     short loc_180002F98
0x180002f8f  movzx   edi, ax
0x180002f92  or      edi, 80070000h
0x180002f98  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f9f  lea     rax, WPP_GLOBAL_Control
0x180002fa6  cmp     rcx, rax
0x180002fa9  jz      loc_180002EDC
0x180002faf  test    byte ptr [rcx+1Ch], 4
0x180002fb3  jz      loc_180002EDC
0x180002fb9  mov     edx, 92h
0x180002fbe  mov     r9d, edi
0x180002fc1  mov     rcx, [rcx+10h]
0x180002fc5  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x180002fcc  call    WPP_SF_d
0x180002fd1  jmp     loc_180002EDC
0x180002fd6  call    cs:__imp_GetLastError
0x180002fdc  test    eax, eax
0x180002fde  jg      loc_1800030D6
0x180002fe4  mov     dword ptr [rbp+pv], eax
0x180002fe7  inc     edi
0x180002fe9  jmp     loc_180002D65
0x180002fee  mov     r9d, dword ptr [rbp+pv]
0x180002ff2  test    r9d, r9d
0x180002ff5  jns     loc_180002DC1
0x180002ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003002  lea     rax, WPP_GLOBAL_Control
0x180003009  cmp     rcx, rax
0x18000300c  jz      loc_180002DC4
0x180003012  test    byte ptr [rcx+1Ch], 4
0x180003016  jz      loc_180002DC4
0x18000301c  mov     rcx, [rcx+10h]
0x180003020  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x180003027  mov     edx, 8Ch
0x18000302c  call    WPP_SF_d
0x180003031  jmp     loc_180002DC4
0x180003036  movzx   eax, ax
0x180003039  or      eax, 80070000h
0x18000303e  jmp     loc_180002D91
0x180003043  call    cs:__imp_GetLastError
0x180003049  test    eax, eax
0x18000304b  jg      loc_18000311A
0x180003051  mov     dword ptr [rbp+pv], eax
0x180003054  mov     rcx, cs:WPP_GLOBAL_Control
0x18000305b  lea     rdx, WPP_GLOBAL_Control
0x180003062  cmp     rcx, rdx
0x180003065  jz      loc_180002DC6
0x18000306b  test    byte ptr [rcx+1Ch], 4
0x18000306f  jz      loc_180002DC6
0x180003075  mov     edx, 8Ah
0x18000307a  jmp     loc_18000316D
0x18000307f  call    cs:__imp_CloseHandle
0x180003085  jmp     loc_180002F6C
0x18000308a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003091  cmp     rcx, r15
0x180003094  jnz     loc_18000319F
0x18000309a  mov     r12, [rbp+pv]
0x18000309e  jmp     loc_180002EEC
0x1800030a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030aa  cmp     rcx, r15
0x1800030ad  jz      loc_180002F26
0x1800030b3  test    byte ptr [rcx+1Ch], 4
0x1800030b7  jz      loc_180002F14
0x1800030bd  mov     rcx, [rcx+10h]
0x1800030c1  lea     r9, aLockperuserids; "LockPerUserIdStore"
0x1800030c8  mov     [rsp+40h+var_20], edi
0x1800030cc  call    WPP_SF_sL
0x1800030d1  jmp     loc_180002F0D
0x1800030d6  movzx   eax, ax
0x1800030d9  or      eax, 80070000h
0x1800030de  jmp     loc_180002FE4
0x1800030e3  call    cs:__imp_GetLastError
0x1800030e9  mov     edi, eax
0x1800030eb  test    eax, eax
0x1800030ed  jg      short loc_180003127
0x1800030ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030f6  lea     rax, WPP_GLOBAL_Control
0x1800030fd  cmp     rcx, rax
0x180003100  jz      loc_180002EDC
0x180003106  test    byte ptr [rcx+1Ch], 4
0x18000310a  jz      loc_180002EDC
0x180003110  mov     edx, 91h
0x180003115  jmp     loc_180002FBE
0x18000311a  movzx   eax, ax
0x18000311d  or      eax, 80070000h
0x180003122  jmp     loc_180003051
0x180003127  movzx   edi, ax
0x18000312a  or      edi, 80070000h
0x180003130  jmp     short loc_1800030EF
0x180003132  call    cs:__imp_GetLastError
0x180003138  test    eax, eax
0x18000313a  jle     short loc_180003144
0x18000313c  movzx   eax, ax
0x18000313f  or      eax, 80070000h
0x180003144  mov     dword ptr [rbp+pv], eax
0x180003147  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
