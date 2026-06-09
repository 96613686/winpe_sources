# FAX_StartCopyToServer

- ea: `0x140021530`
- end: `0x140021bab`
- name: `FAX_StartCopyToServer`
- size: `1659`
- prototype: `__int64 __fastcall(void *, wchar_t *String1, unsigned __int16 *, _QWORD *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config`

## callees

- `0x140002c43`
- `0x140004a30`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004df0`
- `0x140004e68`
- `0x140021530`
- `0x14002c92c`
- `0x1400452ac`
- `0x140045798`
- `0x140065dbc`
- `0x14006a3a4`
- `0x14006dddc`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x14002170c`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14002170c`
- `KERNEL32!GetLastError` at `0x1400216a9`
- `KERNEL32!GetLastError` at `0x140021716`
- `KERNEL32!GetLastError` at `0x14002181e`
- `KERNEL32!GetLastError` at `0x14002189c`
- `KERNEL32!GetLastError` at `0x140021928`
- `KERNEL32!GetLastError` at `0x140021aa5`
- `KERNEL32!GetLastError` at `0x140021af1`
- `KERNEL32!GetLastError` at `0x1400216a9`
- `KERNEL32!GetLastError` at `0x140021716`
- `KERNEL32!GetLastError` at `0x14002181e`
- `KERNEL32!GetLastError` at `0x14002189c`
- `KERNEL32!GetLastError` at `0x140021928`
- `KERNEL32!GetLastError` at `0x140021aa5`
- `KERNEL32!GetLastError` at `0x140021af1`
- `KERNEL32!CloseHandle` at `0x140021a9b`
- `KERNEL32!CloseHandle` at `0x140021a9b`
- `KERNEL32!LocalFree` at `0x140021b37`
- `KERNEL32!LocalFree` at `0x140021b37`
- `KERNEL32!DeleteFileW` at `0x140021ae7`
- `KERNEL32!DeleteFileW` at `0x140021ae7`
- `msvcrt!wcsrchr` at `0x1400218fc`
- `msvcrt!wcsrchr` at `0x1400218fc`
- `msvcrt!_wcsicmp` at `0x140021678`
- `msvcrt!_wcsicmp` at `0x14002168c`
- `msvcrt!_wcsicmp` at `0x140021678`
- `msvcrt!_wcsicmp` at `0x14002168c`

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
  unsigned __int64 v28; // rax
  int v29; // eax
  __int64 v30; // r11
  DWORD v31; // eax
  char v32; // al
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v37[264]; // [rsp+270h] [rbp+170h] BYREF

  StringSid = 0;
  memset_0(Str, 0, 0x208u);
  v34 = 0;
  LODWORD(lpMem) = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 494, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  v8 = FaxSvcAccessCheck(0x2000000u, &v34, (unsigned int *)&lpMem, 1);
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
    v15 = StringCchPrintfW(v37, 0x104u, L"%s%s", StringSid, L"$");
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
    if ( !GenerateUniqueFileNameWithPrefix(v16, *((_QWORD *)g_pFaxConfig + 12), v37, String1, Str) )
    {
      v19 = GetLastError();
      v9 = v19;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 501, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v19);
      }
      goto LABEL_33;
    }
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
      goto LABEL_33;
    }
    v21 = wcsrchr(Str, 0x24u);
    if ( !CreateNewCopyHandle(a1, (void *)File, 1, Str, 0) )
    {
      v22 = GetLastError();
      v9 = v22;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 503, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v22);
      }
LABEL_33:
      if ( v9 )
      {
        if ( File == -1 )
        {
LABEL_90:
          if ( Str[0] )
          {
            if ( !DeleteFileW(Str) )
            {
              v32 = GetLastError();
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  507,
                  (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                  (unsigned int)Str,
                  v32);
              }
            }
          }
          goto LABEL_96;
        }
LABEL_85:
        if ( CloseHandle((HANDLE)File) )
        {
          v31 = GetLastError();
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 506, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v31);
          }
        }
        goto LABEL_90;
      }
LABEL_96:
      if ( StringSid )
        LocalFree(StringSid);
      pMemFree(lpMem);
      return v9;
    }
    if ( !a3 )
      goto LABEL_78;
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
    if ( v24 )
    {
      if ( v21 != (wchar_t *)-2LL )
      {
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
        v28 = (0x7FFFFFFF - v26) & -(__int64)(v26 != 0);
        if ( v26 )
        {
          if ( v25 >= v28 )
          {
            v29 = StringCchCopyW(a3, v25 + 1, v21 + 1);
            v17 = v29;
            if ( v29 >= 0 )
            {
              *a4 = v30;
              goto LABEL_96;
            }
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                505,
                &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                (unsigned int)v29);
            }
            v18 = v17 & 0x1FFF0000;
            goto LABEL_42;
          }
LABEL_80:
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              504,
              &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
              (unsigned int)(v25 + 1),
              v28 + 1);
          }
          v9 = 111;
          goto LABEL_85;
        }
      }
    }
    else
    {
LABEL_78:
      LODWORD(v25) = 0;
    }
    LODWORD(v28) = 0;
    goto LABEL_80;
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
0x140021530  push    rbp
0x140021532  push    rbx
0x140021533  push    rsi
0x140021534  push    rdi
0x140021535  push    r12
0x140021537  push    r13
0x140021539  push    r14
0x14002153b  push    r15
0x14002153d  lea     rbp, [rsp-398h]
0x140021545  sub     rsp, 498h
0x14002154c  mov     rax, cs:__security_cookie
0x140021553  xor     rax, rsp
0x140021556  mov     [rbp+3D0h+var_50], rax
0x14002155d  mov     r12, r8
0x140021560  mov     rsi, rdx
0x140021563  mov     r15, rcx
0x140021566  xor     edi, edi
0x140021568  xor     edx, edx; Val
0x14002156a  mov     [rsp+4D0h+StringSid], rdi
0x14002156f  mov     r8d, 208h; Size
0x140021575  lea     rcx, [rsp+4D0h+Str]; void *
0x14002157a  mov     r13, r9
0x14002157d  call    memset_0
0x140021582  mov     [rsp+4D0h+var_488], edi
0x140021586  mov     dword ptr [rsp+4D0h+lpMem], edi
0x14002158a  mov     rcx, cs:WPP_GLOBAL_Control
0x140021591  lea     rax, WPP_GLOBAL_Control
0x140021598  mov     r14b, 4
0x14002159b  cmp     rcx, rax
0x14002159e  jz      short loc_1400215C1
0x1400215a0  test    [rcx+1Ch], r14b
0x1400215a4  jz      short loc_1400215C1
0x1400215a6  cmp     byte ptr [rcx+19h], 5
0x1400215aa  jb      short loc_1400215C1
0x1400215ac  mov     rcx, [rcx+10h]
0x1400215b0  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400215b7  mov     edx, 1EEh
0x1400215bc  call    WPP_SF_
0x1400215c1  mov     r9d, 1; int
0x1400215c7  lea     r8, [rsp+4D0h+lpMem]; unsigned int *
0x1400215cc  lea     rdx, [rsp+4D0h+var_488]; int *
0x1400215d1  mov     ecx, 2000000h; unsigned int
0x1400215d6  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x1400215db  mov     ebx, eax
0x1400215dd  test    eax, eax
0x1400215df  jz      short loc_14002161F
0x1400215e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400215e8  lea     r15, WPP_GLOBAL_Control
0x1400215ef  cmp     rcx, r15
0x1400215f2  jz      short loc_140021618
0x1400215f4  test    [rcx+1Ch], r14b
0x1400215f8  jz      short loc_140021618
0x1400215fa  cmp     byte ptr [rcx+19h], 2
0x1400215fe  jb      short loc_140021618
0x140021600  mov     rcx, [rcx+10h]
0x140021604  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14002160b  mov     edx, 1EFh
0x140021610  mov     r9d, eax
0x140021613  call    WPP_SF_d
0x140021618  mov     eax, ebx
0x14002161a  jmp     loc_140021B88
0x14002161f  mov     eax, dword ptr [rsp+4D0h+lpMem]
0x140021623  test    al, 7
0x140021625  jnz     short loc_140021665
0x140021627  mov     rcx, cs:WPP_GLOBAL_Control
0x14002162e  lea     r15, WPP_GLOBAL_Control
0x140021635  cmp     rcx, r15
0x140021638  jz      short loc_14002165B
0x14002163a  test    [rcx+1Ch], r14b
0x14002163e  jz      short loc_14002165B
0x140021640  cmp     byte ptr [rcx+19h], 2
0x140021644  jb      short loc_14002165B
0x140021646  mov     rcx, [rcx+10h]
0x14002164a  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021651  mov     edx, 1F0h
0x140021656  call    WPP_SF_
0x14002165b  mov     eax, 5
0x140021660  jmp     loc_140021B88
0x140021665  test    rsi, rsi
0x140021668  jz      loc_140021B4C
0x14002166e  lea     rdx, aCov_0; "cov"
0x140021675  mov     rcx, rsi; String1
0x140021678  call    cs:__imp__wcsicmp
0x14002167e  test    eax, eax
0x140021680  jz      short loc_14002169A
0x140021682  lea     rdx, aTif; "tif"
0x140021689  mov     rcx, rsi; String1
0x14002168c  call    cs:__imp__wcsicmp
0x140021692  test    eax, eax
0x140021694  jnz     loc_140021B4C
0x14002169a  call    ?GetClientUserSID@@YAPEAXXZ; GetClientUserSID(void)
0x14002169f  mov     [rsp+4D0h+lpMem], rax
0x1400216a4  test    rax, rax
0x1400216a7  jnz     short loc_140021700
0x1400216a9  call    cs:__imp_GetLastError
0x1400216af  mov     ebx, eax
0x1400216b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400216b8  lea     r15, WPP_GLOBAL_Control
0x1400216bf  cmp     rcx, r15
0x1400216c2  jz      short loc_1400216E8
0x1400216c4  test    [rcx+1Ch], r14b
0x1400216c8  jz      short loc_1400216E8
0x1400216ca  cmp     byte ptr [rcx+19h], 2
0x1400216ce  jb      short loc_1400216E8
0x1400216d0  mov     rcx, [rcx+10h]
0x1400216d4  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400216db  mov     edx, 1F2h
0x1400216e0  mov     r9d, eax
0x1400216e3  call    WPP_SF_d
0x1400216e8  cmp     ebx, 8
0x1400216eb  jz      short loc_1400216F6
0x1400216ed  cmp     ebx, 0Eh
0x1400216f0  jnz     loc_140021618
0x1400216f6  mov     ebx, 1B59h
0x1400216fb  jmp     loc_140021618
0x140021700  lea     rdx, [rsp+4D0h+StringSid]; StringSid
0x140021705  mov     rcx, rax; Sid
0x140021708  or      r14, 0FFFFFFFFFFFFFFFFh
0x14002170c  call    cs:__imp_ConvertSidToStringSidW
0x140021712  test    eax, eax
0x140021714  jnz     short loc_14002176E
0x140021716  call    cs:__imp_GetLastError
0x14002171c  mov     ebx, eax
0x14002171e  mov     rcx, cs:WPP_GLOBAL_Control
0x140021725  lea     r15, WPP_GLOBAL_Control
0x14002172c  cmp     rcx, r15
0x14002172f  jz      short loc_140021755
0x140021731  test    byte ptr [rcx+1Ch], 4
0x140021735  jz      short loc_140021755
0x140021737  cmp     byte ptr [rcx+19h], 2
0x14002173b  jb      short loc_140021755
0x14002173d  mov     rcx, [rcx+10h]
0x140021741  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021748  mov     edx, 1F3h
0x14002174d  mov     r9d, eax
0x140021750  call    WPP_SF_d
0x140021755  xor     esi, esi
0x140021757  test    ebx, ebx
0x140021759  jz      loc_140021B2D
0x14002175f  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140021763  jz      loc_140021ADB
0x140021769  jmp     loc_140021A98
0x14002176e  mov     r9, [rsp+4D0h+StringSid]
0x140021773  lea     rax, asc_14008C690; "$"
0x14002177a  lea     r8, aSS_1; "%s%s"
0x140021781  mov     qword ptr [rsp+4D0h+var_4B0], rax
0x140021786  mov     edx, 104h; unsigned __int64
0x14002178b  lea     rcx, [rbp+3D0h+var_260]; unsigned __int16 *
0x140021792  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140021797  mov     edi, eax
0x140021799  test    eax, eax
0x14002179b  jns     short loc_1400217F3
0x14002179d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400217a4  lea     r15, WPP_GLOBAL_Control
0x1400217ab  cmp     rcx, r15
0x1400217ae  jz      short loc_1400217D4
0x1400217b0  test    byte ptr [rcx+1Ch], 4
0x1400217b4  jz      short loc_1400217D4
0x1400217b6  cmp     byte ptr [rcx+19h], 2
0x1400217ba  jb      short loc_1400217D4
0x1400217bc  mov     rcx, [rcx+10h]
0x1400217c0  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400217c7  mov     edx, 1F4h
0x1400217cc  mov     r9d, eax
0x1400217cf  call    WPP_SF_d
0x1400217d4  mov     eax, edi
0x1400217d6  and     eax, 1FFF0000h
0x1400217db  xor     esi, esi
0x1400217dd  cmp     eax, 70000h
0x1400217e2  jnz     short loc_1400217EC
0x1400217e4  movzx   ebx, di
0x1400217e7  jmp     loc_140021757
0x1400217ec  mov     ebx, edi
0x1400217ee  jmp     loc_140021757
0x1400217f3  mov     rdx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400217fa  lea     rax, [rsp+4D0h+Str]
0x1400217ff  mov     r9, rsi
0x140021802  mov     qword ptr [rsp+4D0h+var_4B0], rax
0x140021807  lea     r8, [rbp+3D0h+var_260]
0x14002180e  mov     rdx, [rdx+60h]
0x140021812  call    GenerateUniqueFileNameWithPrefix
0x140021817  xor     esi, esi
0x140021819  test    rax, rax
0x14002181c  jnz     short loc_14002186E
0x14002181e  call    cs:__imp_GetLastError
0x140021824  mov     ebx, eax
0x140021826  mov     rcx, cs:WPP_GLOBAL_Control
0x14002182d  lea     r15, WPP_GLOBAL_Control
0x140021834  cmp     rcx, r15
0x140021837  jz      loc_140021757
0x14002183d  test    byte ptr [rcx+1Ch], 4
0x140021841  jz      loc_140021757
0x140021847  cmp     byte ptr [rcx+19h], 2
0x14002184b  jb      loc_140021757
0x140021851  mov     rcx, [rcx+10h]
0x140021855  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14002185c  mov     edx, 1F5h
0x140021861  mov     r9d, eax
0x140021864  call    WPP_SF_d
0x140021869  jmp     loc_140021757
0x14002186e  mov     [rsp+4D0h+var_4A8], 80h; int
0x140021876  lea     rcx, [rsp+4D0h+Str]; lpFileName
0x14002187b  mov     edx, 40000000h; dwDesiredAccess
0x140021880  mov     [rsp+4D0h+var_4B0], 2; DWORD
0x140021888  mov     r8d, 1; dwShareMode
0x14002188e  call    InternalSafeCreateFile
0x140021893  mov     r14, rax
0x140021896  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002189a  jnz     short loc_1400218F2
0x14002189c  call    cs:__imp_GetLastError
0x1400218a2  mov     ebx, eax
0x1400218a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400218ab  lea     r15, WPP_GLOBAL_Control
0x1400218b2  cmp     rcx, r15
0x1400218b5  jz      loc_140021757
0x1400218bb  test    byte ptr [rcx+1Ch], 4
0x1400218bf  jz      loc_140021757
0x1400218c5  cmp     byte ptr [rcx+19h], 2
0x1400218c9  jb      loc_140021757
0x1400218cf  mov     rcx, [rcx+10h]
0x1400218d3  lea     r9, [rsp+4D0h+Str]
0x1400218d8  mov     edx, 1F6h
0x1400218dd  mov     [rsp+4D0h+var_4B0], eax
0x1400218e1  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400218e8  call    WPP_SF_Sd
0x1400218ed  jmp     loc_140021757
0x1400218f2  mov     edx, 24h ; '$'; Ch
0x1400218f7  lea     rcx, [rsp+4D0h+Str]; Str
0x1400218fc  call    cs:__imp_wcsrchr
0x140021902  lea     r9, [rsp+4D0h+Str]; unsigned __int16 *
0x140021907  mov     qword ptr [rsp+4D0h+var_4B0], rsi; struct _JOB_QUEUE *
0x14002190c  mov     r8d, 1; int
0x140021912  mov     rdx, r14; void *
0x140021915  mov     rcx, r15; void *
0x140021918  mov     rdi, rax
0x14002191b  call    ?CreateNewCopyHandle@@YAPEAU_HANDLE_ENTRY@@PEAX0HPEBGPEAU_JOB_QUEUE@@@Z; CreateNewCopyHandle(void *,void *,int,ushort const *,_JOB_QUEUE *)
0x140021920  mov     r11, rax
0x140021923  test    rax, rax
0x140021926  jnz     short loc_140021978
0x140021928  call    cs:__imp_GetLastError
0x14002192e  mov     ebx, eax
0x140021930  mov     rcx, cs:WPP_GLOBAL_Control
0x140021937  lea     r15, WPP_GLOBAL_Control
0x14002193e  cmp     rcx, r15
0x140021941  jz      loc_140021757
0x140021947  test    byte ptr [rcx+1Ch], 4
0x14002194b  jz      loc_140021757
0x140021951  cmp     byte ptr [rcx+19h], 2
0x140021955  jb      loc_140021757
0x14002195b  mov     rcx, [rcx+10h]
0x14002195f  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021966  mov     edx, 1F7h
0x14002196b  mov     r9d, eax
0x14002196e  call    WPP_SF_d
0x140021973  jmp     loc_140021757
0x140021978  test    r12, r12
0x14002197b  jz      loc_140021A50
0x140021981  mov     r10d, 7FFFFFFFh
0x140021987  mov     rax, r12
0x14002198a  mov     edx, r10d
0x14002198d  cmp     [rax], si
0x140021990  jz      short loc_14002199C
0x140021992  add     rax, 2
0x140021996  sub     rdx, 1
0x14002199a  jnz     short loc_14002198D
0x14002199c  mov     rcx, r10
0x14002199f  mov     rax, rdx
0x1400219a2  sub     rcx, rdx
0x1400219a5  neg     rax
0x1400219a8  sbb     r9, r9
0x1400219ab  and     r9, rcx
0x1400219ae  test    rdx, rdx
0x1400219b1  jz      loc_140021A50
0x1400219b7  lea     r8, [rdi+2]; unsigned __int16 *
0x1400219bb  test    r8, r8
0x1400219be  jz      loc_140021A53
0x1400219c4  mov     rdx, r10
0x1400219c7  mov     rax, r8
0x1400219ca  cmp     [rax], si
0x1400219cd  jz      short loc_1400219D9
0x1400219cf  add     rax, 2
0x1400219d3  sub     rdx, 1
0x1400219d7  jnz     short loc_1400219CA
0x1400219d9  sub     r10, rdx
0x1400219dc  mov     rax, rdx
0x1400219df  neg     rax
0x1400219e2  sbb     rax, rax
0x1400219e5  and     rax, r10
0x1400219e8  test    rdx, rdx
0x1400219eb  jz      short loc_140021A53
0x1400219ed  cmp     r9, rax
0x1400219f0  jb      short loc_140021A56
0x1400219f2  lea     rdx, [r9+1]; unsigned __int64
0x1400219f6  mov     rcx, r12; unsigned __int16 *
0x1400219f9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400219fe  mov     edi, eax
0x140021a00  test    eax, eax
0x140021a02  jns     short loc_140021A47
0x140021a04  mov     rcx, cs:WPP_GLOBAL_Control
0x140021a0b  lea     r15, WPP_GLOBAL_Control
  ... truncated ...
```
