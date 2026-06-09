# GenerateUniqueFileNameWithPrefix

- ea: `0x1400720c8`
- end: `0x140072488`
- name: `GenerateUniqueFileNameWithPrefix`
- size: `960`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140022460`
- `0x14002f530`
- `0x140030254`
- `0x140052838`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x14006e124`
- `0x1400720c8`
- `0x140073230`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x14007215f`
- `KERNEL32!GetTempPath2W` at `0x14007215f`
- `KERNEL32!GetLastError` at `0x140072193`
- `KERNEL32!GetLastError` at `0x1400722d4`
- `KERNEL32!GetLastError` at `0x140072333`
- `KERNEL32!GetLastError` at `0x14007238e`
- `KERNEL32!GetLastError` at `0x140072193`
- `KERNEL32!GetLastError` at `0x1400722d4`
- `KERNEL32!GetLastError` at `0x140072333`
- `KERNEL32!GetLastError` at `0x14007238e`
- `KERNEL32!SetLastError` at `0x14007244f`
- `KERNEL32!SetLastError` at `0x14007244f`
- `KERNEL32!CloseHandle` at `0x140072403`
- `KERNEL32!CloseHandle` at `0x140072403`
- `KERNEL32!GetSystemTime` at `0x140072233`
- `KERNEL32!GetSystemTime` at `0x140072233`
- `KERNEL32!SystemTimeToFileTime` at `0x140072249`
- `KERNEL32!SystemTimeToFileTime` at `0x140072249`
- `msvcrt!wcsrchr` at `0x1400721ce`
- `msvcrt!wcsrchr` at `0x1400721ce`
- `msvcrt!_wcsnset` at `0x1400721f0`
- `msvcrt!_wcsnset` at `0x1400721f0`

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
0x1400720c8  mov     [rsp-8+arg_0], rbx
0x1400720cd  push    rbp
0x1400720ce  push    rsi
0x1400720cf  push    rdi
0x1400720d0  push    r12
0x1400720d2  push    r13
0x1400720d4  push    r14
0x1400720d6  push    r15
0x1400720d8  lea     rbp, [rsp-3A0h]
0x1400720e0  sub     rsp, 4A0h
0x1400720e7  mov     rax, cs:__security_cookie
0x1400720ee  xor     rax, rsp
0x1400720f1  mov     [rbp+3D0h+var_40], rax
0x1400720f8  mov     r15, [rbp+3D0h+lpFileName]
0x1400720ff  xorps   xmm0, xmm0
0x140072102  xor     eax, eax
0x140072104  mov     rdi, r9
0x140072107  movups  [rsp+4D0h+var_478], xmm0
0x14007210c  mov     [rsp+4D0h+var_458], rax
0x140072111  mov     rbx, r8
0x140072114  movups  [rsp+4D0h+var_468], xmm0
0x140072119  mov     r14, rdx
0x14007211c  mov     rcx, cs:WPP_GLOBAL_Control
0x140072123  lea     r13, WPP_GLOBAL_Control
0x14007212a  mov     sil, 2
0x14007212d  cmp     rcx, r13
0x140072130  jz      short loc_140072151
0x140072132  test    [rcx+1Ch], sil
0x140072136  jz      short loc_140072151
0x140072138  cmp     byte ptr [rcx+19h], 5
0x14007213c  jb      short loc_140072151
0x14007213e  mov     rcx, [rcx+10h]
0x140072142  lea     edx, [rax+11h]
0x140072145  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14007214c  call    WPP_SF_
0x140072151  test    r14, r14
0x140072154  jnz     short loc_1400721C6
0x140072156  lea     rdx, [rbp+3D0h+var_450]
0x14007215a  mov     ecx, 208h
0x14007215f  call    cs:__imp_GetTempPath2W
0x140072166  nop     dword ptr [rax+rax+00h]
0x14007216b  test    eax, eax
0x14007216d  jnz     short loc_1400721C2
0x14007216f  mov     rax, cs:WPP_GLOBAL_Control
0x140072176  cmp     rax, r13
0x140072179  jz      loc_14007245B
0x14007217f  test    [rax+1Ch], sil
0x140072183  jz      loc_14007245B
0x140072189  cmp     [rax+19h], sil
0x14007218d  jb      loc_14007245B
0x140072193  call    cs:__imp_GetLastError
0x14007219a  nop     dword ptr [rax+rax+00h]
0x14007219f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400721a6  lea     edx, [r14+12h]
0x1400721aa  mov     r9d, eax
0x1400721ad  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x1400721b4  mov     rcx, [rcx+10h]
0x1400721b8  call    WPP_SF_d
0x1400721bd  jmp     loc_14007245B
0x1400721c2  lea     r14, [rbp+3D0h+var_450]
0x1400721c6  mov     edx, 5Ch ; '\'; Ch
0x1400721cb  mov     rcx, r14; Str
0x1400721ce  call    cs:__imp_wcsrchr
0x1400721d5  nop     dword ptr [rax+rax+00h]
0x1400721da  xor     esi, esi
0x1400721dc  test    rax, rax
0x1400721df  jz      short loc_1400721FC
0x1400721e1  cmp     [rax+2], si
0x1400721e5  jnz     short loc_1400721FC
0x1400721e7  xor     edx, edx; Value
0x1400721e9  lea     r8d, [rsi+1]; MaxCount
0x1400721ed  mov     rcx, rax; String
0x1400721f0  call    cs:__imp__wcsnset
0x1400721f7  nop     dword ptr [rax+rax+00h]
0x1400721fc  test    rdi, rdi
0x1400721ff  lea     r12, aTif; "tif"
0x140072206  lea     r13, Class
0x14007220d  cmovnz  r12, rdi
0x140072211  test    rbx, rbx
0x140072214  mov     edi, esi
0x140072216  cmovnz  r13, rbx
0x14007221a  mov     rbx, rsi
0x14007221d  mov     qword ptr [rsp+4D0h+FileTime.dwLowDateTime], rsi
0x140072222  xorps   xmm0, xmm0
0x140072225  movups  xmmword ptr [rsp+4D0h+SystemTime.wYear], xmm0
0x14007222a  test    edi, edi
0x14007222c  jnz     short loc_140072270
0x14007222e  lea     rcx, [rsp+4D0h+SystemTime]; lpSystemTime
0x140072233  call    cs:__imp_GetSystemTime
0x14007223a  nop     dword ptr [rax+rax+00h]
0x14007223f  lea     rdx, [rsp+4D0h+FileTime]; lpFileTime
0x140072244  lea     rcx, [rsp+4D0h+SystemTime]; lpSystemTime
0x140072249  call    cs:__imp_SystemTimeToFileTime
0x140072250  nop     dword ptr [rax+rax+00h]
0x140072255  test    eax, eax
0x140072257  jz      loc_140072305
0x14007225d  mov     ebx, [rsp+4D0h+FileTime.dwHighDateTime]
0x140072261  mov     eax, [rsp+4D0h+FileTime.dwLowDateTime]
0x140072265  shl     rbx, 20h
0x140072269  or      rbx, rax
0x14007226c  shr     rbx, 8
0x140072270  mov     [rsp+4D0h+var_498], r12
0x140072275  lea     rax, [rsp+4D0h+var_478]
0x14007227a  mov     [rsp+4D0h+var_4A0], rbx
0x14007227f  lea     r8, aSSSI64xS; "%s\\%s%s%I64X.%s"
0x140072286  mov     qword ptr [rsp+4D0h+var_4A8], rax
0x14007228b  mov     r9, r14
0x14007228e  mov     edx, 104h; unsigned __int64
0x140072293  mov     qword ptr [rsp+4D0h+var_4B0], r13
0x140072298  mov     rcx, r15; unsigned __int16 *
0x14007229b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400722a0  mov     esi, eax
0x1400722a2  test    eax, eax
0x1400722a4  js      loc_140072414
0x1400722aa  mov     [rsp+4D0h+var_4A8], 80h; int
0x1400722b2  xor     r8d, r8d; dwShareMode
0x1400722b5  mov     edx, 40000000h; dwDesiredAccess
0x1400722ba  mov     [rsp+4D0h+var_4B0], 1; DWORD
0x1400722c2  mov     rcx, r15; lpFileName
0x1400722c5  call    InternalSafeCreateFile
0x1400722ca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400722ce  jnz     loc_140072400
0x1400722d4  call    cs:__imp_GetLastError
0x1400722db  nop     dword ptr [rax+rax+00h]
0x1400722e0  cmp     eax, 0B7h
0x1400722e5  jz      short loc_1400722EC
0x1400722e7  cmp     eax, 50h ; 'P'
0x1400722ea  jnz     short loc_140072363
0x1400722ec  inc     rbx
0x1400722ef  inc     edi
0x1400722f1  mov     eax, 100h
0x1400722f6  cmp     edi, eax
0x1400722f8  jnb     loc_1400723C2
0x1400722fe  xor     esi, esi
0x140072300  jmp     loc_14007221D
0x140072305  mov     rax, cs:WPP_GLOBAL_Control
0x14007230c  lea     rdx, WPP_GLOBAL_Control
0x140072313  cmp     rax, rdx
0x140072316  jz      loc_14007245B
0x14007231c  mov     sil, 2
0x14007231f  test    [rax+1Ch], sil
0x140072323  jz      loc_14007245B
0x140072329  cmp     [rax+19h], sil
0x14007232d  jb      loc_14007245B
0x140072333  call    cs:__imp_GetLastError
0x14007233a  nop     dword ptr [rax+rax+00h]
0x14007233f  mov     rcx, cs:WPP_GLOBAL_Control
0x140072346  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14007234d  mov     edx, 14h
0x140072352  mov     r9d, eax
0x140072355  mov     rcx, [rcx+10h]
0x140072359  call    WPP_SF_d
0x14007235e  jmp     loc_14007245B
0x140072363  mov     rax, cs:WPP_GLOBAL_Control
0x14007236a  lea     rdx, WPP_GLOBAL_Control
0x140072371  cmp     rax, rdx
0x140072374  jz      loc_14007245B
0x14007237a  test    byte ptr [rax+1Ch], 2
0x14007237e  jz      loc_14007245B
0x140072384  cmp     byte ptr [rax+19h], 2
0x140072388  jb      loc_14007245B
0x14007238e  call    cs:__imp_GetLastError
0x140072395  nop     dword ptr [rax+rax+00h]
0x14007239a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400723a1  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x1400723a8  mov     edx, 16h
0x1400723ad  mov     [rsp+4D0h+var_4B0], eax
0x1400723b1  mov     r9, r15
0x1400723b4  mov     rcx, [rcx+10h]
0x1400723b8  call    WPP_SF_Sd
0x1400723bd  jmp     loc_14007245B
0x1400723c2  jnz     short loc_14007240F
0x1400723c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400723cb  lea     rdx, WPP_GLOBAL_Control
0x1400723d2  cmp     rcx, rdx
0x1400723d5  jz      short loc_1400723F9
0x1400723d7  test    byte ptr [rcx+1Ch], 2
0x1400723db  jz      short loc_1400723F9
0x1400723dd  cmp     byte ptr [rcx+19h], 2
0x1400723e1  jb      short loc_1400723F9
0x1400723e3  mov     rcx, [rcx+10h]
0x1400723e7  mov     r9d, eax
0x1400723ea  mov     qword ptr [rsp+4D0h+var_4A8], r15
0x1400723ef  mov     qword ptr [rsp+4D0h+var_4B0], rbx
0x1400723f4  call    WPP_SF_diS
0x1400723f9  mov     ecx, 4
0x1400723fe  jmp     short loc_14007244F
0x140072400  mov     rcx, rax; hObject
0x140072403  call    cs:__imp_CloseHandle
0x14007240a  nop     dword ptr [rax+rax+00h]
0x14007240f  mov     rax, rbx
0x140072412  jmp     short loc_14007245D
0x140072414  mov     rcx, cs:WPP_GLOBAL_Control
0x14007241b  lea     rdx, WPP_GLOBAL_Control
0x140072422  cmp     rcx, rdx
0x140072425  jz      short loc_14007244C
0x140072427  test    byte ptr [rcx+1Ch], 2
0x14007242b  jz      short loc_14007244C
0x14007242d  cmp     byte ptr [rcx+19h], 2
0x140072431  jb      short loc_14007244C
0x140072433  mov     rcx, [rcx+10h]
0x140072437  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14007243e  movzx   r9d, si
0x140072442  mov     edx, 15h
0x140072447  call    WPP_SF_d
0x14007244c  movzx   ecx, si; dwErrCode
0x14007244f  call    cs:__imp_SetLastError
0x140072456  nop     dword ptr [rax+rax+00h]
0x14007245b  xor     eax, eax
0x14007245d  mov     rcx, [rbp+3D0h+var_40]
0x140072464  xor     rcx, rsp; StackCookie
0x140072467  call    __security_check_cookie
0x14007246c  mov     rbx, [rsp+4D0h+arg_0]
0x140072474  add     rsp, 4A0h
0x14007247b  pop     r15
0x14007247d  pop     r14
0x14007247f  pop     r13
0x140072481  pop     r12
0x140072483  pop     rdi
0x140072484  pop     rsi
0x140072485  pop     rbp
0x140072486  retn
```
