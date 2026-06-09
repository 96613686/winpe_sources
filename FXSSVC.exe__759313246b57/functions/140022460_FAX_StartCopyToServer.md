# FAX_StartCopyToServer

- ea: `0x140022460`
- end: `0x140022b30`
- name: `FAX_StartCopyToServer`
- size: `1744`
- prototype: `__int64 __fastcall(void *, wchar_t *String1, unsigned __int16 *, _QWORD *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config`

## callees

- `0x140002c73`
- `0x140004b70`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004f64`
- `0x140004fe4`
- `0x140022460`
- `0x14002de70`
- `0x140047d20`
- `0x140048284`
- `0x14006998c`
- `0x14006e124`
- `0x1400720c8`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x14002264e`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14002264e`
- `KERNEL32!GetLastError` at `0x1400225e5`
- `KERNEL32!GetLastError` at `0x14002265e`
- `KERNEL32!GetLastError` at `0x14002276c`
- `KERNEL32!GetLastError` at `0x1400227f0`
- `KERNEL32!GetLastError` at `0x140022888`
- `KERNEL32!GetLastError` at `0x140022a11`
- `KERNEL32!GetLastError` at `0x140022a69`
- `KERNEL32!GetLastError` at `0x1400225e5`
- `KERNEL32!GetLastError` at `0x14002265e`
- `KERNEL32!GetLastError` at `0x14002276c`
- `KERNEL32!GetLastError` at `0x1400227f0`
- `KERNEL32!GetLastError` at `0x140022888`
- `KERNEL32!GetLastError` at `0x140022a11`
- `KERNEL32!GetLastError` at `0x140022a69`
- `KERNEL32!CloseHandle` at `0x140022a01`
- `KERNEL32!CloseHandle` at `0x140022a01`
- `KERNEL32!LocalFree` at `0x140022ab5`
- `KERNEL32!LocalFree` at `0x140022ab5`
- `KERNEL32!DeleteFileW` at `0x140022a59`
- `KERNEL32!DeleteFileW` at `0x140022a59`
- `msvcrt!wcsrchr` at `0x140022856`
- `msvcrt!wcsrchr` at `0x140022856`
- `msvcrt!_wcsicmp` at `0x1400225a8`
- `msvcrt!_wcsicmp` at `0x1400225c2`
- `msvcrt!_wcsicmp` at `0x1400225a8`
- `msvcrt!_wcsicmp` at `0x1400225c2`

## pseudocode

```c
__int64 __fastcall FAX_StartCopyToServer(void *a1, wchar_t *String1, unsigned __int16 *a3, _QWORD *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  void *ClientUserSID; // rax
  DWORD LastError; // eax
  __int64 File; // r14
  DWORD v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  unsigned int v17; // edi
  int v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  wchar_t *v21; // rdi
  DWORD v22; // eax
  unsigned __int16 *v23; // rax
  __int64 v24; // rdx
  unsigned __int64 v25; // r9
  __int64 v26; // rdx
  _WORD *v27; // rax
  int v28; // eax
  __int64 v29; // r11
  DWORD v30; // eax
  char v31; // al
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v36[264]; // [rsp+270h] [rbp+170h] BYREF

  StringSid = 0;
  memset_0(Str, 0, 0x208u);
  v33 = 0;
  LODWORD(lpMem) = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 494, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  v8 = FaxSvcAccessCheck(0x2000000u, &v33, (unsigned int *)&lpMem, 1);
  v9 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 495, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v8);
    }
    return v9;
  }
  if ( ((unsigned __int8)lpMem & 7) == 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 496, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    }
    return 5;
  }
  if ( String1 && (!_wcsicmp(String1, L"cov") || !_wcsicmp(String1, L"tif")) )
  {
    ClientUserSID = GetClientUserSID();
    lpMem = ClientUserSID;
    if ( !ClientUserSID )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 498, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, LastError);
      }
      if ( v9 == 8 || v9 == 14 )
        return 7001;
      return v9;
    }
    File = -1;
    if ( !ConvertSidToStringSidW(ClientUserSID, &StringSid) )
    {
      v14 = GetLastError();
      v9 = v14;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 499, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v14);
      }
      goto LABEL_33;
    }
    v15 = StringCchPrintfW(v36, 0x104u, L"%s%s", StringSid, L"$");
    v17 = v15;
    if ( v15 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          500,
          &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
          (unsigned int)v15);
      }
      v18 = v17 & 0x1FFF0000;
LABEL_42:
      if ( v18 == 458752 )
        v9 = (unsigned __int16)v17;
      else
        v9 = v17;
      goto LABEL_33;
    }
    if ( GenerateUniqueFileNameWithPrefix(v16, *((_QWORD *)g_pFaxConfig + 12), v36, String1, Str) )
    {
      File = InternalSafeCreateFile(Str, 0x40000000u, 1u, 2u, 128);
      if ( File == -1 )
      {
        v20 = GetLastError();
        v9 = v20;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            502,
            (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            (unsigned int)Str,
            v20);
        }
      }
      else
      {
        v21 = wcsrchr(Str, 0x24u);
        if ( CreateNewCopyHandle(a1, (void *)File, 1, Str, 0) )
        {
          if ( !a3 )
            goto LABEL_80;
          v23 = a3;
          v24 = 0x7FFFFFFF;
          do
          {
            if ( !*v23 )
              break;
            ++v23;
            --v24;
          }
          while ( v24 );
          v25 = (0x7FFFFFFF - v24) & -(__int64)(v24 != 0);
          if ( !v24 || v21 == (wchar_t *)-2LL )
            goto LABEL_80;
          v26 = 0x7FFFFFFF;
          v27 = v21 + 1;
          do
          {
            if ( !*v27 )
              break;
            ++v27;
            --v26;
          }
          while ( v26 );
          if ( !v26 || v25 < ((0x7FFFFFFF - v26) & (unsigned __int64)-(__int64)(v26 != 0)) )
          {
LABEL_80:
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 504, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
            }
            v9 = 111;
            goto LABEL_83;
          }
          v28 = StringCchCopyW(a3, v25 + 1, v21 + 1);
          v17 = v28;
          if ( v28 >= 0 )
          {
            *a4 = v29;
            goto LABEL_94;
          }
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              505,
              &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
              (unsigned int)v28);
          }
          v18 = v17 & 0x1FFF0000;
          goto LABEL_42;
        }
        v22 = GetLastError();
        v9 = v22;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 503, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v22);
        }
      }
    }
    else
    {
      v19 = GetLastError();
      v9 = v19;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 501, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v19);
      }
    }
LABEL_33:
    if ( v9 )
    {
      if ( File == -1 )
      {
LABEL_88:
        if ( Str[0] )
        {
          if ( !DeleteFileW(Str) )
          {
            v31 = GetLastError();
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                507,
                (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                (unsigned int)Str,
                v31);
            }
          }
        }
        goto LABEL_94;
      }
LABEL_83:
      if ( CloseHandle((HANDLE)File) )
      {
        v30 = GetLastError();
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 506, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v30);
        }
      }
      goto LABEL_88;
    }
LABEL_94:
    if ( StringSid )
      LocalFree(StringSid);
    pMemFree(lpMem);
    return v9;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 497, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, String1);
  }
  return 87;
}

```

## disassembly

```asm
0x140022460  push    rbp
0x140022462  push    rbx
0x140022463  push    rsi
0x140022464  push    rdi
0x140022465  push    r12
0x140022467  push    r13
0x140022469  push    r14
0x14002246b  push    r15
0x14002246d  lea     rbp, [rsp-398h]
0x140022475  sub     rsp, 498h
0x14002247c  mov     rax, cs:__security_cookie
0x140022483  xor     rax, rsp
0x140022486  mov     [rbp+3D0h+var_50], rax
0x14002248d  mov     r12, r8
0x140022490  mov     rsi, rdx
0x140022493  mov     r15, rcx
0x140022496  xor     edi, edi
0x140022498  xor     edx, edx; Val
0x14002249a  mov     [rsp+4D0h+StringSid], rdi
0x14002249f  mov     r8d, 208h; Size
0x1400224a5  lea     rcx, [rsp+4D0h+Str]; void *
0x1400224aa  mov     r13, r9
0x1400224ad  call    memset_0
0x1400224b2  mov     [rsp+4D0h+var_488], edi
0x1400224b6  mov     dword ptr [rsp+4D0h+lpMem], edi
0x1400224ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400224c1  lea     rax, WPP_GLOBAL_Control
0x1400224c8  mov     r14b, 4
0x1400224cb  cmp     rcx, rax
0x1400224ce  jz      short loc_1400224F1
0x1400224d0  test    [rcx+1Ch], r14b
0x1400224d4  jz      short loc_1400224F1
0x1400224d6  cmp     byte ptr [rcx+19h], 5
0x1400224da  jb      short loc_1400224F1
0x1400224dc  mov     rcx, [rcx+10h]
0x1400224e0  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400224e7  mov     edx, 1EEh
0x1400224ec  call    WPP_SF_
0x1400224f1  mov     r9d, 1; int
0x1400224f7  lea     r8, [rsp+4D0h+lpMem]; unsigned int *
0x1400224fc  lea     rdx, [rsp+4D0h+var_488]; int *
0x140022501  mov     ecx, 2000000h; unsigned int
0x140022506  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14002250b  mov     ebx, eax
0x14002250d  test    eax, eax
0x14002250f  jz      short loc_14002254F
0x140022511  mov     rcx, cs:WPP_GLOBAL_Control
0x140022518  lea     r15, WPP_GLOBAL_Control
0x14002251f  cmp     rcx, r15
0x140022522  jz      short loc_140022548
0x140022524  test    [rcx+1Ch], r14b
0x140022528  jz      short loc_140022548
0x14002252a  cmp     byte ptr [rcx+19h], 2
0x14002252e  jb      short loc_140022548
0x140022530  mov     rcx, [rcx+10h]
0x140022534  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14002253b  mov     edx, 1EFh
0x140022540  mov     r9d, eax
0x140022543  call    WPP_SF_d
0x140022548  mov     eax, ebx
0x14002254a  jmp     loc_140022B0C
0x14002254f  mov     eax, dword ptr [rsp+4D0h+lpMem]
0x140022553  test    al, 7
0x140022555  jnz     short loc_140022595
0x140022557  mov     rcx, cs:WPP_GLOBAL_Control
0x14002255e  lea     r15, WPP_GLOBAL_Control
0x140022565  cmp     rcx, r15
0x140022568  jz      short loc_14002258B
0x14002256a  test    [rcx+1Ch], r14b
0x14002256e  jz      short loc_14002258B
0x140022570  cmp     byte ptr [rcx+19h], 2
0x140022574  jb      short loc_14002258B
0x140022576  mov     rcx, [rcx+10h]
0x14002257a  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140022581  mov     edx, 1F0h
0x140022586  call    WPP_SF_
0x14002258b  mov     eax, 5
0x140022590  jmp     loc_140022B0C
0x140022595  test    rsi, rsi
0x140022598  jz      loc_140022AD0
0x14002259e  lea     rdx, aCov_0; "cov"
0x1400225a5  mov     rcx, rsi; String1
0x1400225a8  call    cs:__imp__wcsicmp
0x1400225af  nop     dword ptr [rax+rax+00h]
0x1400225b4  test    eax, eax
0x1400225b6  jz      short loc_1400225D6
0x1400225b8  lea     rdx, aTif; "tif"
0x1400225bf  mov     rcx, rsi; String1
0x1400225c2  call    cs:__imp__wcsicmp
0x1400225c9  nop     dword ptr [rax+rax+00h]
0x1400225ce  test    eax, eax
0x1400225d0  jnz     loc_140022AD0
0x1400225d6  call    ?GetClientUserSID@@YAPEAXXZ; GetClientUserSID(void)
0x1400225db  mov     [rsp+4D0h+lpMem], rax
0x1400225e0  test    rax, rax
0x1400225e3  jnz     short loc_140022642
0x1400225e5  call    cs:__imp_GetLastError
0x1400225ec  nop     dword ptr [rax+rax+00h]
0x1400225f1  mov     ebx, eax
0x1400225f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400225fa  lea     r15, WPP_GLOBAL_Control
0x140022601  cmp     rcx, r15
0x140022604  jz      short loc_14002262A
0x140022606  test    [rcx+1Ch], r14b
0x14002260a  jz      short loc_14002262A
0x14002260c  cmp     byte ptr [rcx+19h], 2
0x140022610  jb      short loc_14002262A
0x140022612  mov     rcx, [rcx+10h]
0x140022616  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14002261d  mov     edx, 1F2h
0x140022622  mov     r9d, eax
0x140022625  call    WPP_SF_d
0x14002262a  cmp     ebx, 8
0x14002262d  jz      short loc_140022638
0x14002262f  cmp     ebx, 0Eh
0x140022632  jnz     loc_140022548
0x140022638  mov     ebx, 1B59h
0x14002263d  jmp     loc_140022548
0x140022642  lea     rdx, [rsp+4D0h+StringSid]; StringSid
0x140022647  mov     rcx, rax; Sid
0x14002264a  or      r14, 0FFFFFFFFFFFFFFFFh
0x14002264e  call    cs:__imp_ConvertSidToStringSidW
0x140022655  nop     dword ptr [rax+rax+00h]
0x14002265a  test    eax, eax
0x14002265c  jnz     short loc_1400226BC
0x14002265e  call    cs:__imp_GetLastError
0x140022665  nop     dword ptr [rax+rax+00h]
0x14002266a  mov     ebx, eax
0x14002266c  mov     rcx, cs:WPP_GLOBAL_Control
0x140022673  lea     r15, WPP_GLOBAL_Control
0x14002267a  cmp     rcx, r15
0x14002267d  jz      short loc_1400226A3
0x14002267f  test    byte ptr [rcx+1Ch], 4
0x140022683  jz      short loc_1400226A3
0x140022685  cmp     byte ptr [rcx+19h], 2
0x140022689  jb      short loc_1400226A3
0x14002268b  mov     rcx, [rcx+10h]
0x14002268f  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140022696  mov     edx, 1F3h
0x14002269b  mov     r9d, eax
0x14002269e  call    WPP_SF_d
0x1400226a3  xor     esi, esi
0x1400226a5  test    ebx, ebx
0x1400226a7  jz      loc_140022AAB
0x1400226ad  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1400226b1  jz      loc_140022A4D
0x1400226b7  jmp     loc_1400229FE
0x1400226bc  mov     r9, [rsp+4D0h+StringSid]
0x1400226c1  lea     rax, asc_1400926A0; "$"
0x1400226c8  lea     r8, aSS_1; "%s%s"
0x1400226cf  mov     qword ptr [rsp+4D0h+var_4B0], rax
0x1400226d4  mov     edx, 104h; unsigned __int64
0x1400226d9  lea     rcx, [rbp+3D0h+var_260]; unsigned __int16 *
0x1400226e0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400226e5  mov     edi, eax
0x1400226e7  test    eax, eax
0x1400226e9  jns     short loc_140022741
0x1400226eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400226f2  lea     r15, WPP_GLOBAL_Control
0x1400226f9  cmp     rcx, r15
0x1400226fc  jz      short loc_140022722
0x1400226fe  test    byte ptr [rcx+1Ch], 4
0x140022702  jz      short loc_140022722
0x140022704  cmp     byte ptr [rcx+19h], 2
0x140022708  jb      short loc_140022722
0x14002270a  mov     rcx, [rcx+10h]
0x14002270e  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140022715  mov     edx, 1F4h
0x14002271a  mov     r9d, eax
0x14002271d  call    WPP_SF_d
0x140022722  mov     eax, edi
0x140022724  and     eax, 1FFF0000h
0x140022729  xor     esi, esi
0x14002272b  cmp     eax, 70000h
0x140022730  jnz     short loc_14002273A
0x140022732  movzx   ebx, di
0x140022735  jmp     loc_1400226A5
0x14002273a  mov     ebx, edi
0x14002273c  jmp     loc_1400226A5
0x140022741  mov     rdx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140022748  lea     rax, [rsp+4D0h+Str]
0x14002274d  mov     r9, rsi
0x140022750  mov     qword ptr [rsp+4D0h+var_4B0], rax
0x140022755  lea     r8, [rbp+3D0h+var_260]
0x14002275c  mov     rdx, [rdx+60h]
0x140022760  call    GenerateUniqueFileNameWithPrefix
0x140022765  xor     esi, esi
0x140022767  test    rax, rax
0x14002276a  jnz     short loc_1400227C2
0x14002276c  call    cs:__imp_GetLastError
0x140022773  nop     dword ptr [rax+rax+00h]
0x140022778  mov     ebx, eax
0x14002277a  mov     rcx, cs:WPP_GLOBAL_Control
0x140022781  lea     r15, WPP_GLOBAL_Control
0x140022788  cmp     rcx, r15
0x14002278b  jz      loc_1400226A5
0x140022791  test    byte ptr [rcx+1Ch], 4
0x140022795  jz      loc_1400226A5
0x14002279b  cmp     byte ptr [rcx+19h], 2
0x14002279f  jb      loc_1400226A5
0x1400227a5  mov     rcx, [rcx+10h]
0x1400227a9  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400227b0  mov     edx, 1F5h
0x1400227b5  mov     r9d, eax
0x1400227b8  call    WPP_SF_d
0x1400227bd  jmp     loc_1400226A5
0x1400227c2  mov     [rsp+4D0h+var_4A8], 80h; int
0x1400227ca  lea     rcx, [rsp+4D0h+Str]; lpFileName
0x1400227cf  mov     edx, 40000000h; dwDesiredAccess
0x1400227d4  mov     [rsp+4D0h+var_4B0], 2; DWORD
0x1400227dc  mov     r8d, 1; dwShareMode
0x1400227e2  call    InternalSafeCreateFile
0x1400227e7  mov     r14, rax
0x1400227ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400227ee  jnz     short loc_14002284C
0x1400227f0  call    cs:__imp_GetLastError
0x1400227f7  nop     dword ptr [rax+rax+00h]
0x1400227fc  mov     ebx, eax
0x1400227fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140022805  lea     r15, WPP_GLOBAL_Control
0x14002280c  cmp     rcx, r15
0x14002280f  jz      loc_1400226A5
0x140022815  test    byte ptr [rcx+1Ch], 4
0x140022819  jz      loc_1400226A5
0x14002281f  cmp     byte ptr [rcx+19h], 2
0x140022823  jb      loc_1400226A5
0x140022829  mov     rcx, [rcx+10h]
0x14002282d  lea     r9, [rsp+4D0h+Str]
0x140022832  mov     edx, 1F6h
0x140022837  mov     [rsp+4D0h+var_4B0], eax
0x14002283b  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140022842  call    WPP_SF_Sd
0x140022847  jmp     loc_1400226A5
0x14002284c  mov     edx, 24h ; '$'; Ch
0x140022851  lea     rcx, [rsp+4D0h+Str]; Str
0x140022856  call    cs:__imp_wcsrchr
0x14002285d  nop     dword ptr [rax+rax+00h]
0x140022862  lea     r9, [rsp+4D0h+Str]; unsigned __int16 *
0x140022867  mov     qword ptr [rsp+4D0h+var_4B0], rsi; struct _JOB_QUEUE *
0x14002286c  mov     r8d, 1; int
0x140022872  mov     rdx, r14; void *
0x140022875  mov     rcx, r15; void *
0x140022878  mov     rdi, rax
0x14002287b  call    ?CreateNewCopyHandle@@YAPEAU_HANDLE_ENTRY@@PEAX0HPEBGPEAU_JOB_QUEUE@@@Z; CreateNewCopyHandle(void *,void *,int,ushort const *,_JOB_QUEUE *)
0x140022880  mov     r11, rax
0x140022883  test    rax, rax
0x140022886  jnz     short loc_1400228DE
0x140022888  call    cs:__imp_GetLastError
0x14002288f  nop     dword ptr [rax+rax+00h]
0x140022894  mov     ebx, eax
0x140022896  mov     rcx, cs:WPP_GLOBAL_Control
0x14002289d  lea     r15, WPP_GLOBAL_Control
0x1400228a4  cmp     rcx, r15
0x1400228a7  jz      loc_1400226A5
0x1400228ad  test    byte ptr [rcx+1Ch], 4
0x1400228b1  jz      loc_1400226A5
0x1400228b7  cmp     byte ptr [rcx+19h], 2
0x1400228bb  jb      loc_1400226A5
0x1400228c1  mov     rcx, [rcx+10h]
0x1400228c5  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400228cc  mov     edx, 1F7h
0x1400228d1  mov     r9d, eax
0x1400228d4  call    WPP_SF_d
0x1400228d9  jmp     loc_1400226A5
0x1400228de  test    r12, r12
0x1400228e1  jz      loc_1400229B6
0x1400228e7  mov     r10d, 7FFFFFFFh
0x1400228ed  mov     rax, r12
0x1400228f0  mov     edx, r10d
0x1400228f3  cmp     [rax], si
0x1400228f6  jz      short loc_140022902
0x1400228f8  add     rax, 2
0x1400228fc  sub     rdx, 1
0x140022900  jnz     short loc_1400228F3
0x140022902  mov     rcx, r10
0x140022905  mov     rax, rdx
0x140022908  sub     rcx, rdx
0x14002290b  neg     rax
0x14002290e  sbb     r9, r9
0x140022911  and     r9, rcx
0x140022914  test    rdx, rdx
0x140022917  jz      loc_1400229B6
0x14002291d  lea     r8, [rdi+2]; unsigned __int16 *
0x140022921  test    r8, r8
0x140022924  jz      loc_1400229B9
0x14002292a  mov     rdx, r10
0x14002292d  mov     rax, r8
0x140022930  cmp     [rax], si
0x140022933  jz      short loc_14002293F
0x140022935  add     rax, 2
0x140022939  sub     rdx, 1
0x14002293d  jnz     short loc_140022930
0x14002293f  sub     r10, rdx
0x140022942  mov     rax, rdx
0x140022945  neg     rax
0x140022948  sbb     rax, rax
0x14002294b  and     rax, r10
0x14002294e  test    rdx, rdx
0x140022951  jz      short loc_1400229B9
0x140022953  cmp     r9, rax
  ... truncated ...
```
