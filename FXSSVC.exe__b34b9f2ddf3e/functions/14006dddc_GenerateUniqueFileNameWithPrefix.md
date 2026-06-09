# GenerateUniqueFileNameWithPrefix

- ea: `0x14006dddc`
- end: `0x14006e159`
- name: `GenerateUniqueFileNameWithPrefix`
- size: `893`
- prototype: `unsigned __int64 __fastcall(__int64, const wchar_t *, const WCHAR *, const wchar_t *, unsigned __int16 *lpFileName)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140021530`
- `0x14002dee0`
- `0x14002eb78`
- `0x14004f56c`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x14006a3a4`
- `0x14006dddc`
- `0x14006ee34`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x14006de73`
- `KERNEL32!GetTempPath2W` at `0x14006de73`
- `KERNEL32!GetLastError` at `0x14006dea1`
- `KERNEL32!GetLastError` at `0x14006dfc4`
- `KERNEL32!GetLastError` at `0x14006e01d`
- `KERNEL32!GetLastError` at `0x14006e072`
- `KERNEL32!GetLastError` at `0x14006dea1`
- `KERNEL32!GetLastError` at `0x14006dfc4`
- `KERNEL32!GetLastError` at `0x14006e01d`
- `KERNEL32!GetLastError` at `0x14006e072`
- `KERNEL32!SetLastError` at `0x14006e127`
- `KERNEL32!SetLastError` at `0x14006e127`
- `KERNEL32!CloseHandle` at `0x14006e0e1`
- `KERNEL32!CloseHandle` at `0x14006e0e1`
- `KERNEL32!GetSystemTime` at `0x14006df2f`
- `KERNEL32!GetSystemTime` at `0x14006df2f`
- `KERNEL32!SystemTimeToFileTime` at `0x14006df3f`
- `KERNEL32!SystemTimeToFileTime` at `0x14006df3f`
- `msvcrt!wcsrchr` at `0x14006ded6`
- `msvcrt!wcsrchr` at `0x14006ded6`
- `msvcrt!_wcsnset` at `0x14006def2`
- `msvcrt!_wcsnset` at `0x14006def2`

## pseudocode

```c
unsigned __int64 __fastcall GenerateUniqueFileNameWithPrefix(
        __int64 a1,
        const wchar_t *a2,
        const WCHAR *a3,
        const wchar_t *a4,
        unsigned __int16 *lpFileName)
{
  DWORD LastError; // eax
  wchar_t *v9; // rax
  const wchar_t *v10; // r12
  const WCHAR *v11; // r13
  int v12; // edi
  unsigned __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // r9
  unsigned __int16 v16; // si
  void *File; // rax
  DWORD v18; // eax
  int v19; // r8d
  DWORD v20; // eax
  char v21; // al
  DWORD v22; // ecx
  struct _FILETIME FileTime; // [rsp+40h] [rbp-C0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v26[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+78h] [rbp-88h]
  _BYTE v28[1040]; // [rsp+80h] [rbp-80h] BYREF

  memset(v26, 0, sizeof(v26));
  v27 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
  }
  if ( !a2 )
  {
    if ( !(unsigned int)GetTempPath2W(520, v28) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, LastError);
      }
      return 0;
    }
    a2 = (const wchar_t *)v28;
  }
  v9 = wcsrchr(a2, 0x5Cu);
  if ( v9 && !v9[1] )
    _wcsnset(v9, 0, 1u);
  v10 = L"tif";
  v11 = &Class;
  if ( a4 )
    v10 = a4;
  v12 = 0;
  if ( a3 )
    v11 = a3;
  v13 = 0;
  while ( 1 )
  {
    FileTime = 0;
    SystemTime = 0;
    if ( !v12 )
    {
      GetSystemTime(&SystemTime);
      if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v20 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v20);
        }
        return 0;
      }
      v13 = *(unsigned __int64 *)&FileTime >> 8;
    }
    v14 = StringCchPrintfW(lpFileName, 0x104u, L"%s\\%s%s%I64X.%s", a2, v11, v26, v13, v10);
    v16 = v14;
    if ( v14 < 0 )
      break;
    File = (void *)InternalSafeCreateFile(lpFileName, 0x40000000u, 0, v15, 1u, 128);
    if ( File != (void *)-1LL )
    {
      CloseHandle(File);
      return v13;
    }
    v18 = GetLastError();
    if ( v18 != 183 && v18 != 80 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
          (_DWORD)lpFileName,
          v21);
      }
      return 0;
    }
    ++v13;
    if ( (unsigned int)++v12 >= 0x100 )
    {
      if ( v12 == 256 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_diS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned int)&WPP_GLOBAL_Control,
            v19,
            256,
            v13,
            (__int64)lpFileName);
        }
        v22 = 4;
        goto LABEL_50;
      }
      return v13;
    }
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
      (unsigned __int16)v14);
  }
  v22 = v16;
LABEL_50:
  SetLastError(v22);
  return 0;
}

```

## disassembly

```asm
0x14006dddc  mov     [rsp-8+arg_0], rbx
0x14006dde1  push    rbp
0x14006dde2  push    rsi
0x14006dde3  push    rdi
0x14006dde4  push    r12
0x14006dde6  push    r13
0x14006dde8  push    r14
0x14006ddea  push    r15
0x14006ddec  lea     rbp, [rsp-3A0h]
0x14006ddf4  sub     rsp, 4A0h
0x14006ddfb  mov     rax, cs:__security_cookie
0x14006de02  xor     rax, rsp
0x14006de05  mov     [rbp+3D0h+var_40], rax
0x14006de0c  mov     r15, [rbp+3D0h+lpFileName]
0x14006de13  xorps   xmm0, xmm0
0x14006de16  xor     eax, eax
0x14006de18  mov     rdi, r9
0x14006de1b  movups  [rsp+4D0h+var_478], xmm0
0x14006de20  mov     [rsp+4D0h+var_458], rax
0x14006de25  mov     rbx, r8
0x14006de28  movups  [rsp+4D0h+var_468], xmm0
0x14006de2d  mov     r14, rdx
0x14006de30  mov     rcx, cs:WPP_GLOBAL_Control
0x14006de37  lea     r13, WPP_GLOBAL_Control
0x14006de3e  mov     sil, 2
0x14006de41  cmp     rcx, r13
0x14006de44  jz      short loc_14006DE65
0x14006de46  test    [rcx+1Ch], sil
0x14006de4a  jz      short loc_14006DE65
0x14006de4c  cmp     byte ptr [rcx+19h], 5
0x14006de50  jb      short loc_14006DE65
0x14006de52  mov     rcx, [rcx+10h]
0x14006de56  lea     edx, [rax+11h]
0x14006de59  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006de60  call    WPP_SF_
0x14006de65  test    r14, r14
0x14006de68  jnz     short loc_14006DECE
0x14006de6a  lea     rdx, [rbp+3D0h+var_450]
0x14006de6e  mov     ecx, 208h
0x14006de73  call    cs:__imp_GetTempPath2W
0x14006de79  test    eax, eax
0x14006de7b  jnz     short loc_14006DECA
0x14006de7d  mov     rax, cs:WPP_GLOBAL_Control
0x14006de84  cmp     rax, r13
0x14006de87  jz      loc_14006E12D
0x14006de8d  test    [rax+1Ch], sil
0x14006de91  jz      loc_14006E12D
0x14006de97  cmp     [rax+19h], sil
0x14006de9b  jb      loc_14006E12D
0x14006dea1  call    cs:__imp_GetLastError
0x14006dea7  mov     rcx, cs:WPP_GLOBAL_Control
0x14006deae  lea     edx, [r14+12h]
0x14006deb2  mov     r9d, eax
0x14006deb5  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006debc  mov     rcx, [rcx+10h]
0x14006dec0  call    WPP_SF_d
0x14006dec5  jmp     loc_14006E12D
0x14006deca  lea     r14, [rbp+3D0h+var_450]
0x14006dece  mov     edx, 5Ch ; '\'; Ch
0x14006ded3  mov     rcx, r14; Str
0x14006ded6  call    cs:__imp_wcsrchr
0x14006dedc  xor     esi, esi
0x14006dede  test    rax, rax
0x14006dee1  jz      short loc_14006DEF8
0x14006dee3  cmp     [rax+2], si
0x14006dee7  jnz     short loc_14006DEF8
0x14006dee9  xor     edx, edx; Value
0x14006deeb  lea     r8d, [rsi+1]; MaxCount
0x14006deef  mov     rcx, rax; String
0x14006def2  call    cs:__imp__wcsnset
0x14006def8  test    rdi, rdi
0x14006defb  lea     r12, aTif; "tif"
0x14006df02  lea     r13, Class
0x14006df09  cmovnz  r12, rdi
0x14006df0d  test    rbx, rbx
0x14006df10  mov     edi, esi
0x14006df12  cmovnz  r13, rbx
0x14006df16  mov     rbx, rsi
0x14006df19  mov     qword ptr [rsp+4D0h+FileTime.dwLowDateTime], rsi
0x14006df1e  xorps   xmm0, xmm0
0x14006df21  movups  xmmword ptr [rsp+4D0h+SystemTime.wYear], xmm0
0x14006df26  test    edi, edi
0x14006df28  jnz     short loc_14006DF60
0x14006df2a  lea     rcx, [rsp+4D0h+SystemTime]; lpSystemTime
0x14006df2f  call    cs:__imp_GetSystemTime
0x14006df35  lea     rdx, [rsp+4D0h+FileTime]; lpFileTime
0x14006df3a  lea     rcx, [rsp+4D0h+SystemTime]; lpSystemTime
0x14006df3f  call    cs:__imp_SystemTimeToFileTime
0x14006df45  test    eax, eax
0x14006df47  jz      loc_14006DFEF
0x14006df4d  mov     ebx, [rsp+4D0h+FileTime.dwHighDateTime]
0x14006df51  mov     eax, [rsp+4D0h+FileTime.dwLowDateTime]
0x14006df55  shl     rbx, 20h
0x14006df59  or      rbx, rax
0x14006df5c  shr     rbx, 8
0x14006df60  mov     [rsp+4D0h+var_498], r12
0x14006df65  lea     rax, [rsp+4D0h+var_478]
0x14006df6a  mov     [rsp+4D0h+var_4A0], rbx
0x14006df6f  lea     r8, aSSSI64xS; "%s\\%s%s%I64X.%s"
0x14006df76  mov     qword ptr [rsp+4D0h+var_4A8], rax
0x14006df7b  mov     r9, r14
0x14006df7e  mov     edx, 104h; unsigned __int64
0x14006df83  mov     qword ptr [rsp+4D0h+var_4B0], r13
0x14006df88  mov     rcx, r15; unsigned __int16 *
0x14006df8b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14006df90  mov     esi, eax
0x14006df92  test    eax, eax
0x14006df94  js      loc_14006E0EC
0x14006df9a  mov     [rsp+4D0h+var_4A8], 80h; int
0x14006dfa2  xor     r8d, r8d; dwShareMode
0x14006dfa5  mov     edx, 40000000h; dwDesiredAccess
0x14006dfaa  mov     [rsp+4D0h+var_4B0], 1; DWORD
0x14006dfb2  mov     rcx, r15; lpFileName
0x14006dfb5  call    InternalSafeCreateFile
0x14006dfba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006dfbe  jnz     loc_14006E0DE
0x14006dfc4  call    cs:__imp_GetLastError
0x14006dfca  cmp     eax, 0B7h
0x14006dfcf  jz      short loc_14006DFD6
0x14006dfd1  cmp     eax, 50h ; 'P'
0x14006dfd4  jnz     short loc_14006E047
0x14006dfd6  inc     rbx
0x14006dfd9  inc     edi
0x14006dfdb  mov     eax, 100h
0x14006dfe0  cmp     edi, eax
0x14006dfe2  jnb     loc_14006E0A0
0x14006dfe8  xor     esi, esi
0x14006dfea  jmp     loc_14006DF19
0x14006dfef  mov     rax, cs:WPP_GLOBAL_Control
0x14006dff6  lea     rdx, WPP_GLOBAL_Control
0x14006dffd  cmp     rax, rdx
0x14006e000  jz      loc_14006E12D
0x14006e006  mov     sil, 2
0x14006e009  test    [rax+1Ch], sil
0x14006e00d  jz      loc_14006E12D
0x14006e013  cmp     [rax+19h], sil
0x14006e017  jb      loc_14006E12D
0x14006e01d  call    cs:__imp_GetLastError
0x14006e023  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e02a  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006e031  mov     edx, 14h
0x14006e036  mov     r9d, eax
0x14006e039  mov     rcx, [rcx+10h]
0x14006e03d  call    WPP_SF_d
0x14006e042  jmp     loc_14006E12D
0x14006e047  mov     rax, cs:WPP_GLOBAL_Control
0x14006e04e  lea     rdx, WPP_GLOBAL_Control
0x14006e055  cmp     rax, rdx
0x14006e058  jz      loc_14006E12D
0x14006e05e  test    byte ptr [rax+1Ch], 2
0x14006e062  jz      loc_14006E12D
0x14006e068  cmp     byte ptr [rax+19h], 2
0x14006e06c  jb      loc_14006E12D
0x14006e072  call    cs:__imp_GetLastError
0x14006e078  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e07f  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006e086  mov     edx, 16h
0x14006e08b  mov     [rsp+4D0h+var_4B0], eax
0x14006e08f  mov     r9, r15
0x14006e092  mov     rcx, [rcx+10h]
0x14006e096  call    WPP_SF_Sd
0x14006e09b  jmp     loc_14006E12D
0x14006e0a0  jnz     short loc_14006E0E7
0x14006e0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e0a9  lea     rdx, WPP_GLOBAL_Control
0x14006e0b0  cmp     rcx, rdx
0x14006e0b3  jz      short loc_14006E0D7
0x14006e0b5  test    byte ptr [rcx+1Ch], 2
0x14006e0b9  jz      short loc_14006E0D7
0x14006e0bb  cmp     byte ptr [rcx+19h], 2
0x14006e0bf  jb      short loc_14006E0D7
0x14006e0c1  mov     rcx, [rcx+10h]
0x14006e0c5  mov     r9d, eax
0x14006e0c8  mov     qword ptr [rsp+4D0h+var_4A8], r15
0x14006e0cd  mov     qword ptr [rsp+4D0h+var_4B0], rbx
0x14006e0d2  call    WPP_SF_diS
0x14006e0d7  mov     ecx, 4
0x14006e0dc  jmp     short loc_14006E127
0x14006e0de  mov     rcx, rax; hObject
0x14006e0e1  call    cs:__imp_CloseHandle
0x14006e0e7  mov     rax, rbx
0x14006e0ea  jmp     short loc_14006E12F
0x14006e0ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e0f3  lea     rdx, WPP_GLOBAL_Control
0x14006e0fa  cmp     rcx, rdx
0x14006e0fd  jz      short loc_14006E124
0x14006e0ff  test    byte ptr [rcx+1Ch], 2
0x14006e103  jz      short loc_14006E124
0x14006e105  cmp     byte ptr [rcx+19h], 2
0x14006e109  jb      short loc_14006E124
0x14006e10b  mov     rcx, [rcx+10h]
0x14006e10f  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006e116  movzx   r9d, si
0x14006e11a  mov     edx, 15h
0x14006e11f  call    WPP_SF_d
0x14006e124  movzx   ecx, si; dwErrCode
0x14006e127  call    cs:__imp_SetLastError
0x14006e12d  xor     eax, eax
0x14006e12f  mov     rcx, [rbp+3D0h+var_40]
0x14006e136  xor     rcx, rsp; StackCookie
0x14006e139  call    __security_check_cookie
0x14006e13e  mov     rbx, [rsp+4D0h+arg_0]
0x14006e146  add     rsp, 4A0h
0x14006e14d  pop     r15
0x14006e14f  pop     r14
0x14006e151  pop     r13
0x14006e153  pop     r12
0x14006e155  pop     rdi
0x14006e156  pop     rsi
0x14006e157  pop     rbp
0x14006e158  retn
```
