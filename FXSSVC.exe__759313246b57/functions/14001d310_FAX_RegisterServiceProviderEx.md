# FAX_RegisterServiceProviderEx

- ea: `0x14001d310`
- end: `0x14001d77f`
- name: `FAX_RegisterServiceProviderEx`
- size: `1135`
- prototype: `__int64 __fastcall(__int64, OLECHAR *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *lpString2, int, int)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callees

- `0x140003450`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004f64`
- `0x140004fe4`
- `0x14001d310`
- `0x140047d20`
- `0x14006998c`
- `0x14006a574`
- `0x14006a9f0`
- `0x14006e124`
- `0x140080d28`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001d59c`
- `KERNEL32!GetLastError` at `0x14001d626`
- `KERNEL32!GetLastError` at `0x14001d59c`
- `KERNEL32!GetLastError` at `0x14001d626`
- `KERNEL32!lstrcmpiW` at `0x14001d4fb`
- `KERNEL32!lstrcmpiW` at `0x14001d4fb`
- `KERNEL32!CloseHandle` at `0x14001d720`
- `KERNEL32!CloseHandle` at `0x14001d720`

## pseudocode

```c
__int64 __fastcall FAX_RegisterServiceProviderEx(
        __int64 a1,
        OLECHAR *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *lpString2,
        int a6,
        int a7)
{
  unsigned int valid; // ebx
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
  WCHAR *v24; // rdi
  void *File; // rsi
  int v26[18]; // [rsp+40h] [rbp-48h] BYREF

  v26[0] = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 381, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  valid = FaxSvcAccessCheck(0x40u, v26, 0, 1);
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
  if ( !v26[0] )
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
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 385, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
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
        v24 = (WCHAR *)v23;
        if ( v23 )
        {
          File = (void *)InternalSafeCreateFile(v23, 0x80000000, 1u, 3u, 128);
          if ( File == (void *)-1LL )
          {
            valid = GetLastError();
            if ( valid == 2 )
            {
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= (unsigned __int8)valid )
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
          pMemFree(v24);
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
0x14001d310  push    rbx
0x14001d312  push    rbp
0x14001d313  push    rsi
0x14001d314  push    rdi
0x14001d315  push    r12
0x14001d317  push    r13
0x14001d319  push    r15
0x14001d31b  sub     rsp, 50h
0x14001d31f  xor     esi, esi
0x14001d321  mov     rbp, r9
0x14001d324  mov     [rsp+88h+var_48], esi
0x14001d328  mov     r12, r8
0x14001d32b  mov     r15, rdx
0x14001d32e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d335  lea     rdi, WPP_GLOBAL_Control
0x14001d33c  mov     r13b, 4
0x14001d33f  cmp     rcx, rdi
0x14001d342  jz      short loc_14001D365
0x14001d344  test    [rcx+1Ch], r13b
0x14001d348  jz      short loc_14001D365
0x14001d34a  cmp     byte ptr [rcx+19h], 5
0x14001d34e  jb      short loc_14001D365
0x14001d350  mov     rcx, [rcx+10h]
0x14001d354  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d35b  mov     edx, 17Dh
0x14001d360  call    WPP_SF_
0x14001d365  mov     r9d, 1; int
0x14001d36b  lea     rdx, [rsp+88h+var_48]; int *
0x14001d370  xor     r8d, r8d; unsigned int *
0x14001d373  lea     ecx, [r9+3Fh]; unsigned int
0x14001d377  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14001d37c  mov     ebx, eax
0x14001d37e  test    eax, eax
0x14001d380  jz      short loc_14001D3B9
0x14001d382  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d389  cmp     rcx, rdi
0x14001d38c  jz      short loc_14001D3B2
0x14001d38e  test    [rcx+1Ch], r13b
0x14001d392  jz      short loc_14001D3B2
0x14001d394  cmp     byte ptr [rcx+19h], 2
0x14001d398  jb      short loc_14001D3B2
0x14001d39a  mov     edx, 17Eh
0x14001d39f  mov     rcx, [rcx+10h]
0x14001d3a3  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d3aa  mov     r9d, ebx
0x14001d3ad  call    WPP_SF_d
0x14001d3b2  mov     eax, ebx
0x14001d3b4  jmp     loc_14001D76F
0x14001d3b9  cmp     [rsp+88h+var_48], esi
0x14001d3bd  jnz     short loc_14001D3F6
0x14001d3bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d3c6  cmp     rcx, rdi
0x14001d3c9  jz      short loc_14001D3EC
0x14001d3cb  test    [rcx+1Ch], r13b
0x14001d3cf  jz      short loc_14001D3EC
0x14001d3d1  cmp     byte ptr [rcx+19h], 2
0x14001d3d5  jb      short loc_14001D3EC
0x14001d3d7  mov     rcx, [rcx+10h]
0x14001d3db  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d3e2  mov     edx, 17Fh
0x14001d3e7  call    WPP_SF_
0x14001d3ec  mov     eax, 5
0x14001d3f1  jmp     loc_14001D76F
0x14001d3f6  mov     ecx, 102h
0x14001d3fb  test    r12, r12
0x14001d3fe  jz      short loc_14001D416
0x14001d400  mov     edx, ecx
0x14001d402  mov     rax, r12
0x14001d405  cmp     [rax], si
0x14001d408  jz      short loc_14001D416
0x14001d40a  add     rax, 2
0x14001d40e  sub     rdx, 1
0x14001d412  jnz     short loc_14001D405
0x14001d414  jmp     short loc_14001D453
0x14001d416  test    rbp, rbp
0x14001d419  jz      short loc_14001D432
0x14001d41b  mov     rdx, rcx
0x14001d41e  mov     rax, rbp
0x14001d421  cmp     [rax], si
0x14001d424  jz      short loc_14001D432
0x14001d426  add     rax, 2
0x14001d42a  sub     rdx, 1
0x14001d42e  jnz     short loc_14001D421
0x14001d430  jmp     short loc_14001D453
0x14001d432  cmp     [rsp+88h+lpString2], rsi
0x14001d43a  jz      short loc_14001D45D
0x14001d43c  mov     rax, [rsp+88h+lpString2]
0x14001d444  cmp     [rax], si
0x14001d447  jz      short loc_14001D45D
0x14001d449  add     rax, 2
0x14001d44d  sub     rcx, 1
0x14001d451  jnz     short loc_14001D444
0x14001d453  mov     eax, 6Fh ; 'o'
0x14001d458  jmp     loc_14001D76F
0x14001d45d  mov     rcx, r15; lpsz
0x14001d460  call    IsValidGUID
0x14001d465  mov     ebx, eax
0x14001d467  test    eax, eax
0x14001d469  jz      short loc_14001D499
0x14001d46b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d472  cmp     rcx, rdi
0x14001d475  jz      loc_14001D3B2
0x14001d47b  test    [rcx+1Ch], r13b
0x14001d47f  jz      loc_14001D3B2
0x14001d485  cmp     byte ptr [rcx+19h], 2
0x14001d489  jb      loc_14001D3B2
0x14001d48f  mov     edx, 180h
0x14001d494  jmp     loc_14001D39F
0x14001d499  mov     r9d, [rsp+88h+arg_28]
0x14001d4a1  mov     eax, [rsp+88h+arg_30]
0x14001d4a8  cmp     r9d, 10000h
0x14001d4af  jnz     loc_14001D739
0x14001d4b5  test    eax, eax
0x14001d4b7  jnz     loc_14001D739
0x14001d4bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d4c4  cmp     rcx, rdi
0x14001d4c7  jz      short loc_14001D4E8
0x14001d4c9  test    [rcx+1Ch], r13b
0x14001d4cd  jz      short loc_14001D4E8
0x14001d4cf  cmp     byte ptr [rcx+19h], 5
0x14001d4d3  jb      short loc_14001D4E8
0x14001d4d5  mov     rcx, [rcx+10h]
0x14001d4d9  lea     edx, [rax+3Ch]
0x14001d4dc  lea     r8, WPP_200271385d87382553faba38592a1280_Traceguids
0x14001d4e3  call    WPP_SF_
0x14001d4e8  mov     rbx, cs:?g_DeviceProvidersListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_DeviceProvidersListHead
0x14001d4ef  jmp     short loc_14001D50E
0x14001d4f1  lea     rdx, [rbx+658h]; lpString2
0x14001d4f8  mov     rcx, r15; lpString1
0x14001d4fb  call    cs:__imp_lstrcmpiW
0x14001d502  nop     dword ptr [rax+rax+00h]
0x14001d507  test    eax, eax
0x14001d509  jz      short loc_14001D568
0x14001d50b  mov     rbx, [rbx]
0x14001d50e  lea     rax, ?g_DeviceProvidersListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_DeviceProvidersListHead
0x14001d515  cmp     rbx, rax
0x14001d518  jnz     short loc_14001D4F1
0x14001d51a  mov     rcx, [rsp+88h+lpString2]; lpString2
0x14001d522  xor     edx, edx; int
0x14001d524  call    ?FindDeviceProvider@@YAPEAU_DEVICE_PROVIDER@@PEBGH@Z; FindDeviceProvider(ushort const *,int)
0x14001d529  test    rax, rax
0x14001d52c  jz      short loc_14001D58C
0x14001d52e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d535  cmp     rcx, rdi
0x14001d538  jz      short loc_14001D55E
0x14001d53a  test    [rcx+1Ch], r13b
0x14001d53e  jz      short loc_14001D55E
0x14001d540  cmp     byte ptr [rcx+19h], 2
0x14001d544  jb      short loc_14001D55E
0x14001d546  mov     edx, 183h
0x14001d54b  mov     rcx, [rcx+10h]
0x14001d54f  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d556  mov     r9, r15
0x14001d559  call    WPP_SF_S
0x14001d55e  mov     eax, 0B7h
0x14001d563  jmp     loc_14001D76F
0x14001d568  test    rbx, rbx
0x14001d56b  jz      short loc_14001D51A
0x14001d56d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d574  cmp     rcx, rdi
0x14001d577  jz      short loc_14001D55E
0x14001d579  test    [rcx+1Ch], r13b
0x14001d57d  jz      short loc_14001D55E
0x14001d57f  cmp     byte ptr [rcx+19h], 2
0x14001d583  jb      short loc_14001D55E
0x14001d585  mov     edx, 182h
0x14001d58a  jmp     short loc_14001D54B
0x14001d58c  mov     rcx, rbp; unsigned __int16 *
0x14001d58f  call    ExpandEnvironmentString
0x14001d594  mov     rdi, rax
0x14001d597  test    rax, rax
0x14001d59a  jnz     short loc_14001D5F6
0x14001d59c  call    cs:__imp_GetLastError
0x14001d5a3  nop     dword ptr [rax+rax+00h]
0x14001d5a8  mov     ebx, eax
0x14001d5aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d5b1  lea     rax, WPP_GLOBAL_Control
0x14001d5b8  cmp     rcx, rax
0x14001d5bb  jz      loc_14001D3B2
0x14001d5c1  test    [rcx+1Ch], r13b
0x14001d5c5  jz      loc_14001D3B2
0x14001d5cb  cmp     byte ptr [rcx+19h], 2
0x14001d5cf  jb      loc_14001D3B2
0x14001d5d5  mov     rcx, [rcx+10h]
0x14001d5d9  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d5e0  mov     edx, 184h
0x14001d5e5  mov     [rsp+88h+var_68], ebx
0x14001d5e9  mov     r9, rbp
0x14001d5ec  call    WPP_SF_Sd
0x14001d5f1  jmp     loc_14001D3B2
0x14001d5f6  mov     [rsp+88h+var_60], 80h; int
0x14001d5fe  mov     edx, 80000000h; dwDesiredAccess
0x14001d603  mov     r8d, 1; dwShareMode
0x14001d609  mov     [rsp+88h+var_68], 3; DWORD
0x14001d611  mov     rcx, rdi; lpFileName
0x14001d614  call    InternalSafeCreateFile
0x14001d619  mov     rsi, rax
0x14001d61c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001d620  jnz     loc_14001D6C2
0x14001d626  call    cs:__imp_GetLastError
0x14001d62d  nop     dword ptr [rax+rax+00h]
0x14001d632  mov     ebx, eax
0x14001d634  cmp     eax, 2
0x14001d637  jnz     short loc_14001D679
0x14001d639  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d640  lea     rax, WPP_GLOBAL_Control
0x14001d647  cmp     rcx, rax
0x14001d64a  jz      short loc_14001D66F
0x14001d64c  test    [rcx+1Ch], r13b
0x14001d650  jz      short loc_14001D66F
0x14001d652  cmp     [rcx+19h], bl
0x14001d655  jb      short loc_14001D66F
0x14001d657  mov     rcx, [rcx+10h]
0x14001d65b  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d662  mov     edx, 185h
0x14001d667  mov     r9, rbp
0x14001d66a  call    WPP_SF_S
0x14001d66f  mov     ebx, 57h ; 'W'
0x14001d674  jmp     loc_14001D72C
0x14001d679  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d680  lea     rax, WPP_GLOBAL_Control
0x14001d687  cmp     rcx, rax
0x14001d68a  jz      loc_14001D72C
0x14001d690  test    [rcx+1Ch], r13b
0x14001d694  jz      loc_14001D72C
0x14001d69a  cmp     byte ptr [rcx+19h], 2
0x14001d69e  jb      loc_14001D72C
0x14001d6a4  mov     rcx, [rcx+10h]
0x14001d6a8  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d6af  mov     edx, 186h
0x14001d6b4  mov     [rsp+88h+var_68], ebx
0x14001d6b8  mov     r9, rbp
0x14001d6bb  call    WPP_SF_Sd
0x14001d6c0  jmp     short loc_14001D72C
0x14001d6c2  mov     r9, [rsp+88h+lpString2]; unsigned __int16 *
0x14001d6ca  mov     r8, rbp; unsigned __int16 *
0x14001d6cd  mov     rdx, r12; unsigned __int16 *
0x14001d6d0  mov     [rsp+88h+var_68], 10000h; int
0x14001d6d8  mov     rcx, r15; unsigned __int16 *
0x14001d6db  call    AddNewProviderToRegistry
0x14001d6e0  mov     ebx, eax
0x14001d6e2  test    eax, eax
0x14001d6e4  jz      short loc_14001D71D
0x14001d6e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d6ed  lea     rax, WPP_GLOBAL_Control
0x14001d6f4  cmp     rcx, rax
0x14001d6f7  jz      short loc_14001D71D
0x14001d6f9  test    [rcx+1Ch], r13b
0x14001d6fd  jz      short loc_14001D71D
0x14001d6ff  cmp     byte ptr [rcx+19h], 2
0x14001d703  jb      short loc_14001D71D
0x14001d705  mov     rcx, [rcx+10h]
0x14001d709  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d710  mov     edx, 187h
0x14001d715  mov     r9d, ebx
0x14001d718  call    WPP_SF_d
0x14001d71d  mov     rcx, rsi; hObject
0x14001d720  call    cs:__imp_CloseHandle
0x14001d727  nop     dword ptr [rax+rax+00h]
0x14001d72c  mov     rcx, rdi; lpMem
0x14001d72f  call    pMemFree
0x14001d734  jmp     loc_14001D3B2
0x14001d739  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d740  cmp     rcx, rdi
0x14001d743  jz      short loc_14001D76A
0x14001d745  test    [rcx+1Ch], r13b
0x14001d749  jz      short loc_14001D76A
0x14001d74b  cmp     byte ptr [rcx+19h], 2
0x14001d74f  jb      short loc_14001D76A
0x14001d751  mov     rcx, [rcx+10h]
0x14001d755  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d75c  mov     edx, 181h
0x14001d761  mov     [rsp+88h+var_68], eax
0x14001d765  call    WPP_SF_dd
0x14001d76a  mov     eax, 57h ; 'W'
0x14001d76f  add     rsp, 50h
0x14001d773  pop     r15
0x14001d775  pop     r13
0x14001d777  pop     r12
0x14001d779  pop     rdi
0x14001d77a  pop     rsi
0x14001d77b  pop     rbp
0x14001d77c  pop     rbx
0x14001d77d  retn
```
