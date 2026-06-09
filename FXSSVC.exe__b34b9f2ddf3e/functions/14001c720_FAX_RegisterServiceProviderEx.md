# FAX_RegisterServiceProviderEx

- ea: `0x14001c720`
- end: `0x14001cb76`
- name: `FAX_RegisterServiceProviderEx`
- size: `1110`
- prototype: `__int64 __fastcall(__int64, OLECHAR *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *lpString2, unsigned int, int)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callees

- `0x1400033ec`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004df0`
- `0x140004e68`
- `0x14001c720`
- `0x1400452ac`
- `0x140065dbc`
- `0x140066868`
- `0x140066c9c`
- `0x14006a3a4`
- `0x14007bc44`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001c9a6`
- `KERNEL32!GetLastError` at `0x14001ca2a`
- `KERNEL32!GetLastError` at `0x14001c9a6`
- `KERNEL32!GetLastError` at `0x14001ca2a`
- `KERNEL32!lstrcmpiW` at `0x14001c90b`
- `KERNEL32!lstrcmpiW` at `0x14001c90b`
- `KERNEL32!CloseHandle` at `0x14001cb1e`
- `KERNEL32!CloseHandle` at `0x14001cb1e`

## pseudocode

```c
__int64 __fastcall FAX_RegisterServiceProviderEx(
        __int64 a1,
        OLECHAR *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *lpString2,
        unsigned int a6,
        int a7)
{
  DWORD valid; // ebx
  CMapDeviceId *v11; // rcx
  __int64 v12; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned __int16 *v16; // rax
  __int64 v17; // rdx
  unsigned __int16 *i; // rax
  unsigned __int16 *j; // rax
  struct _DEVICE_PROVIDER *k; // rbx
  CMapDeviceId *v21; // rcx
  __int64 v22; // rdx
  const WCHAR *v23; // rax
  __int64 v24; // r9
  WCHAR *v25; // rdi
  void *File; // rsi
  int v27[18]; // [rsp+40h] [rbp-48h] BYREF

  v27[0] = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 381, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  valid = FaxSvcAccessCheck(0x40u, v27, 0, 1);
  if ( valid )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return valid;
    }
    v12 = 382;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, valid);
    return valid;
  }
  if ( !v27[0] )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 383, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    }
    return 5;
  }
  v14 = 258;
  if ( !a3 )
  {
LABEL_23:
    if ( a4 )
    {
      v17 = 258;
      for ( i = a4; *i; ++i )
      {
        if ( !--v17 )
          return 111;
      }
    }
    if ( lpString2 )
    {
      for ( j = lpString2; *j; ++j )
      {
        if ( !--v14 )
          return 111;
      }
    }
    valid = IsValidGUID(a2);
    if ( valid )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return valid;
      }
      v12 = 384;
      goto LABEL_10;
    }
    if ( a6 != 0x10000 || a7 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 385, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, a6, a7);
      }
      return 87;
    }
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)(a7 + 60),
        &WPP_200271385d87382553faba38592a1280_Traceguids);
    }
    for ( k = g_DeviceProvidersListHead; ; k = *(struct _DEVICE_PROVIDER **)k )
    {
      if ( k == (struct _DEVICE_PROVIDER *)&g_DeviceProvidersListHead )
        goto LABEL_48;
      if ( !lstrcmpiW(a2, (LPCWSTR)k + 812) )
        break;
    }
    if ( k )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 183;
      }
      v22 = 386;
    }
    else
    {
LABEL_48:
      if ( !FindDeviceProvider(lpString2, 0) )
      {
        v23 = (const WCHAR *)ExpandEnvironmentString(a4);
        v25 = (WCHAR *)v23;
        if ( v23 )
        {
          File = (void *)InternalSafeCreateFile(v23, 0x80000000, 1u, v24, 3u, 128);
          if ( File == (void *)-1LL )
          {
            valid = GetLastError();
            if ( valid == 2 )
            {
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 389, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, a4);
              }
              valid = 87;
            }
            else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                390,
                (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                (_DWORD)a4,
                valid);
            }
          }
          else
          {
            valid = AddNewProviderToRegistry(a2, a3, a4, lpString2, 0x10000);
            if ( valid
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                391,
                &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                valid);
            }
            CloseHandle(File);
          }
          pMemFree(v25);
        }
        else
        {
          valid = GetLastError();
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              388,
              (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
              (_DWORD)a4,
              valid);
          }
        }
        return valid;
      }
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 183;
      }
      v22 = 387;
    }
    WPP_SF_S(*((_QWORD *)v21 + 2), v22, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, a2);
    return 183;
  }
  v15 = 258;
  v16 = a3;
  do
  {
    if ( !*v16 )
      goto LABEL_23;
    ++v16;
    --v15;
  }
  while ( v15 );
  return 111;
}

```

## disassembly

```asm
0x14001c720  push    rbx
0x14001c722  push    rbp
0x14001c723  push    rsi
0x14001c724  push    rdi
0x14001c725  push    r12
0x14001c727  push    r13
0x14001c729  push    r15
0x14001c72b  sub     rsp, 50h
0x14001c72f  xor     esi, esi
0x14001c731  mov     rbp, r9
0x14001c734  mov     [rsp+88h+var_48], esi
0x14001c738  mov     r12, r8
0x14001c73b  mov     r15, rdx
0x14001c73e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c745  lea     rdi, WPP_GLOBAL_Control
0x14001c74c  mov     r13b, 4
0x14001c74f  cmp     rcx, rdi
0x14001c752  jz      short loc_14001C775
0x14001c754  test    [rcx+1Ch], r13b
0x14001c758  jz      short loc_14001C775
0x14001c75a  cmp     byte ptr [rcx+19h], 5
0x14001c75e  jb      short loc_14001C775
0x14001c760  mov     rcx, [rcx+10h]
0x14001c764  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001c76b  mov     edx, 17Dh
0x14001c770  call    WPP_SF_
0x14001c775  mov     r9d, 1; int
0x14001c77b  lea     rdx, [rsp+88h+var_48]; int *
0x14001c780  xor     r8d, r8d; unsigned int *
0x14001c783  lea     ecx, [r9+3Fh]; unsigned int
0x14001c787  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14001c78c  mov     ebx, eax
0x14001c78e  test    eax, eax
0x14001c790  jz      short loc_14001C7C9
0x14001c792  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c799  cmp     rcx, rdi
0x14001c79c  jz      short loc_14001C7C2
0x14001c79e  test    [rcx+1Ch], r13b
0x14001c7a2  jz      short loc_14001C7C2
0x14001c7a4  cmp     byte ptr [rcx+19h], 2
0x14001c7a8  jb      short loc_14001C7C2
0x14001c7aa  mov     edx, 17Eh
0x14001c7af  mov     rcx, [rcx+10h]
0x14001c7b3  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001c7ba  mov     r9d, ebx
0x14001c7bd  call    WPP_SF_d
0x14001c7c2  mov     eax, ebx
0x14001c7c4  jmp     loc_14001CB67
0x14001c7c9  cmp     [rsp+88h+var_48], esi
0x14001c7cd  jnz     short loc_14001C806
0x14001c7cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c7d6  cmp     rcx, rdi
0x14001c7d9  jz      short loc_14001C7FC
0x14001c7db  test    [rcx+1Ch], r13b
0x14001c7df  jz      short loc_14001C7FC
0x14001c7e1  cmp     byte ptr [rcx+19h], 2
0x14001c7e5  jb      short loc_14001C7FC
0x14001c7e7  mov     rcx, [rcx+10h]
0x14001c7eb  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001c7f2  mov     edx, 17Fh
0x14001c7f7  call    WPP_SF_
0x14001c7fc  mov     eax, 5
0x14001c801  jmp     loc_14001CB67
0x14001c806  mov     ecx, 102h
0x14001c80b  test    r12, r12
0x14001c80e  jz      short loc_14001C826
0x14001c810  mov     edx, ecx
0x14001c812  mov     rax, r12
0x14001c815  cmp     [rax], si
0x14001c818  jz      short loc_14001C826
0x14001c81a  add     rax, 2
0x14001c81e  sub     rdx, 1
0x14001c822  jnz     short loc_14001C815
0x14001c824  jmp     short loc_14001C863
0x14001c826  test    rbp, rbp
0x14001c829  jz      short loc_14001C842
0x14001c82b  mov     rdx, rcx
0x14001c82e  mov     rax, rbp
0x14001c831  cmp     [rax], si
0x14001c834  jz      short loc_14001C842
0x14001c836  add     rax, 2
0x14001c83a  sub     rdx, 1
0x14001c83e  jnz     short loc_14001C831
0x14001c840  jmp     short loc_14001C863
0x14001c842  cmp     [rsp+88h+lpString2], rsi
0x14001c84a  jz      short loc_14001C86D
0x14001c84c  mov     rax, [rsp+88h+lpString2]
0x14001c854  cmp     [rax], si
0x14001c857  jz      short loc_14001C86D
0x14001c859  add     rax, 2
0x14001c85d  sub     rcx, 1
0x14001c861  jnz     short loc_14001C854
0x14001c863  mov     eax, 6Fh ; 'o'
0x14001c868  jmp     loc_14001CB67
0x14001c86d  mov     rcx, r15; lpsz
0x14001c870  call    IsValidGUID
0x14001c875  mov     ebx, eax
0x14001c877  test    eax, eax
0x14001c879  jz      short loc_14001C8A9
0x14001c87b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c882  cmp     rcx, rdi
0x14001c885  jz      loc_14001C7C2
0x14001c88b  test    [rcx+1Ch], r13b
0x14001c88f  jz      loc_14001C7C2
0x14001c895  cmp     byte ptr [rcx+19h], 2
0x14001c899  jb      loc_14001C7C2
0x14001c89f  mov     edx, 180h
0x14001c8a4  jmp     loc_14001C7AF
0x14001c8a9  mov     r9d, [rsp+88h+arg_28]
0x14001c8b1  mov     eax, [rsp+88h+arg_30]
0x14001c8b8  cmp     r9d, 10000h
0x14001c8bf  jnz     loc_14001CB31
0x14001c8c5  test    eax, eax
0x14001c8c7  jnz     loc_14001CB31
0x14001c8cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c8d4  cmp     rcx, rdi
0x14001c8d7  jz      short loc_14001C8F8
0x14001c8d9  test    [rcx+1Ch], r13b
0x14001c8dd  jz      short loc_14001C8F8
0x14001c8df  cmp     byte ptr [rcx+19h], 5
0x14001c8e3  jb      short loc_14001C8F8
0x14001c8e5  mov     rcx, [rcx+10h]
0x14001c8e9  lea     edx, [rax+3Ch]
0x14001c8ec  lea     r8, WPP_200271385d87382553faba38592a1280_Traceguids
0x14001c8f3  call    WPP_SF_
0x14001c8f8  mov     rbx, cs:?g_DeviceProvidersListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_DeviceProvidersListHead
0x14001c8ff  jmp     short loc_14001C918
0x14001c901  lea     rdx, [rbx+658h]; lpString2
0x14001c908  mov     rcx, r15; lpString1
0x14001c90b  call    cs:__imp_lstrcmpiW
0x14001c911  test    eax, eax
0x14001c913  jz      short loc_14001C972
0x14001c915  mov     rbx, [rbx]
0x14001c918  lea     rax, ?g_DeviceProvidersListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_DeviceProvidersListHead
0x14001c91f  cmp     rbx, rax
0x14001c922  jnz     short loc_14001C901
0x14001c924  mov     rcx, [rsp+88h+lpString2]; lpString2
0x14001c92c  xor     edx, edx; int
0x14001c92e  call    ?FindDeviceProvider@@YAPEAU_DEVICE_PROVIDER@@PEBGH@Z; FindDeviceProvider(ushort const *,int)
0x14001c933  test    rax, rax
0x14001c936  jz      short loc_14001C996
0x14001c938  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c93f  cmp     rcx, rdi
0x14001c942  jz      short loc_14001C968
0x14001c944  test    [rcx+1Ch], r13b
0x14001c948  jz      short loc_14001C968
0x14001c94a  cmp     byte ptr [rcx+19h], 2
0x14001c94e  jb      short loc_14001C968
0x14001c950  mov     edx, 183h
0x14001c955  mov     rcx, [rcx+10h]
0x14001c959  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001c960  mov     r9, r15
0x14001c963  call    WPP_SF_S
0x14001c968  mov     eax, 0B7h
0x14001c96d  jmp     loc_14001CB67
0x14001c972  test    rbx, rbx
0x14001c975  jz      short loc_14001C924
0x14001c977  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c97e  cmp     rcx, rdi
0x14001c981  jz      short loc_14001C968
0x14001c983  test    [rcx+1Ch], r13b
0x14001c987  jz      short loc_14001C968
0x14001c989  cmp     byte ptr [rcx+19h], 2
0x14001c98d  jb      short loc_14001C968
0x14001c98f  mov     edx, 182h
0x14001c994  jmp     short loc_14001C955
0x14001c996  mov     rcx, rbp; unsigned __int16 *
0x14001c999  call    ExpandEnvironmentString
0x14001c99e  mov     rdi, rax
0x14001c9a1  test    rax, rax
0x14001c9a4  jnz     short loc_14001C9FA
0x14001c9a6  call    cs:__imp_GetLastError
0x14001c9ac  mov     ebx, eax
0x14001c9ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c9b5  lea     rax, WPP_GLOBAL_Control
0x14001c9bc  cmp     rcx, rax
0x14001c9bf  jz      loc_14001C7C2
0x14001c9c5  test    [rcx+1Ch], r13b
0x14001c9c9  jz      loc_14001C7C2
0x14001c9cf  cmp     byte ptr [rcx+19h], 2
0x14001c9d3  jb      loc_14001C7C2
0x14001c9d9  mov     rcx, [rcx+10h]
0x14001c9dd  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001c9e4  mov     edx, 184h
0x14001c9e9  mov     [rsp+88h+var_68], ebx
0x14001c9ed  mov     r9, rbp
0x14001c9f0  call    WPP_SF_Sd
0x14001c9f5  jmp     loc_14001C7C2
0x14001c9fa  mov     [rsp+88h+var_60], 80h; int
0x14001ca02  mov     edx, 80000000h; dwDesiredAccess
0x14001ca07  mov     r8d, 1; dwShareMode
0x14001ca0d  mov     [rsp+88h+var_68], 3; DWORD
0x14001ca15  mov     rcx, rdi; lpFileName
0x14001ca18  call    InternalSafeCreateFile
0x14001ca1d  mov     rsi, rax
0x14001ca20  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001ca24  jnz     loc_14001CAC0
0x14001ca2a  call    cs:__imp_GetLastError
0x14001ca30  mov     ebx, eax
0x14001ca32  cmp     eax, 2
0x14001ca35  jnz     short loc_14001CA77
0x14001ca37  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ca3e  lea     rax, WPP_GLOBAL_Control
0x14001ca45  cmp     rcx, rax
0x14001ca48  jz      short loc_14001CA6D
0x14001ca4a  test    [rcx+1Ch], r13b
0x14001ca4e  jz      short loc_14001CA6D
0x14001ca50  cmp     [rcx+19h], bl
0x14001ca53  jb      short loc_14001CA6D
0x14001ca55  mov     rcx, [rcx+10h]
0x14001ca59  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001ca60  mov     edx, 185h
0x14001ca65  mov     r9, rbp
0x14001ca68  call    WPP_SF_S
0x14001ca6d  mov     ebx, 57h ; 'W'
0x14001ca72  jmp     loc_14001CB24
0x14001ca77  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ca7e  lea     rax, WPP_GLOBAL_Control
0x14001ca85  cmp     rcx, rax
0x14001ca88  jz      loc_14001CB24
0x14001ca8e  test    [rcx+1Ch], r13b
0x14001ca92  jz      loc_14001CB24
0x14001ca98  cmp     byte ptr [rcx+19h], 2
0x14001ca9c  jb      loc_14001CB24
0x14001caa2  mov     rcx, [rcx+10h]
0x14001caa6  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001caad  mov     edx, 186h
0x14001cab2  mov     [rsp+88h+var_68], ebx
0x14001cab6  mov     r9, rbp
0x14001cab9  call    WPP_SF_Sd
0x14001cabe  jmp     short loc_14001CB24
0x14001cac0  mov     r9, [rsp+88h+lpString2]; unsigned __int16 *
0x14001cac8  mov     r8, rbp; unsigned __int16 *
0x14001cacb  mov     rdx, r12; unsigned __int16 *
0x14001cace  mov     [rsp+88h+var_68], 10000h; int
0x14001cad6  mov     rcx, r15; unsigned __int16 *
0x14001cad9  call    AddNewProviderToRegistry
0x14001cade  mov     ebx, eax
0x14001cae0  test    eax, eax
0x14001cae2  jz      short loc_14001CB1B
0x14001cae4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001caeb  lea     rax, WPP_GLOBAL_Control
0x14001caf2  cmp     rcx, rax
0x14001caf5  jz      short loc_14001CB1B
0x14001caf7  test    [rcx+1Ch], r13b
0x14001cafb  jz      short loc_14001CB1B
0x14001cafd  cmp     byte ptr [rcx+19h], 2
0x14001cb01  jb      short loc_14001CB1B
0x14001cb03  mov     rcx, [rcx+10h]
0x14001cb07  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001cb0e  mov     edx, 187h
0x14001cb13  mov     r9d, ebx
0x14001cb16  call    WPP_SF_d
0x14001cb1b  mov     rcx, rsi; hObject
0x14001cb1e  call    cs:__imp_CloseHandle
0x14001cb24  mov     rcx, rdi; lpMem
0x14001cb27  call    pMemFree
0x14001cb2c  jmp     loc_14001C7C2
0x14001cb31  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cb38  cmp     rcx, rdi
0x14001cb3b  jz      short loc_14001CB62
0x14001cb3d  test    [rcx+1Ch], r13b
0x14001cb41  jz      short loc_14001CB62
0x14001cb43  cmp     byte ptr [rcx+19h], 2
0x14001cb47  jb      short loc_14001CB62
0x14001cb49  mov     rcx, [rcx+10h]
0x14001cb4d  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001cb54  mov     edx, 181h
0x14001cb59  mov     [rsp+88h+var_68], eax
0x14001cb5d  call    WPP_SF_dd
0x14001cb62  mov     eax, 57h ; 'W'
0x14001cb67  add     rsp, 50h
0x14001cb6b  pop     r15
0x14001cb6d  pop     r13
0x14001cb6f  pop     r12
0x14001cb71  pop     rdi
0x14001cb72  pop     rsi
0x14001cb73  pop     rbp
0x14001cb74  pop     rbx
0x14001cb75  retn
```
