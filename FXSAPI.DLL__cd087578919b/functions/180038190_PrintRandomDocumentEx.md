# PrintRandomDocumentEx

- ea: `0x180038190`
- end: `0x1800386e7`
- name: `PrintRandomDocumentEx`
- size: `1367`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180016de4`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180021530`
- `0x1800308e0`
- `0x180035d78`
- `0x180036f80`
- `0x180038190`
- `0x1800386f0`
- `0x18003c0e8`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x180038289`
- `KERNEL32!GetTempPath2W` at `0x180038289`
- `KERNEL32!GetTempFileNameW` at `0x1800382c9`
- `KERNEL32!GetTempFileNameW` at `0x1800382c9`
- `KERNEL32!GetFullPathNameW` at `0x1800382eb`
- `KERNEL32!GetFullPathNameW` at `0x1800382eb`
- `KERNEL32!DeleteFileW` at `0x180038672`
- `KERNEL32!DeleteFileW` at `0x180038699`
- `KERNEL32!DeleteFileW` at `0x180038672`
- `KERNEL32!DeleteFileW` at `0x180038699`
- `KERNEL32!GetFileSize` at `0x1800383db`
- `KERNEL32!GetFileSize` at `0x1800383db`
- `KERNEL32!CopyFileW` at `0x180038623`
- `KERNEL32!CopyFileW` at `0x180038623`
- `KERNEL32!CloseHandle` at `0x1800383ed`
- `KERNEL32!CloseHandle` at `0x1800383ed`
- `KERNEL32!SetLastError` at `0x1800386ab`
- `KERNEL32!SetLastError` at `0x1800386ab`
- `KERNEL32!GetLastError` at `0x18003829e`
- `KERNEL32!GetLastError` at `0x18003837e`
- `KERNEL32!GetLastError` at `0x1800383ff`
- `KERNEL32!GetLastError` at `0x1800385d5`
- `KERNEL32!GetLastError` at `0x180038633`
- `KERNEL32!GetLastError` at `0x180038687`
- `KERNEL32!GetLastError` at `0x18003829e`
- `KERNEL32!GetLastError` at `0x18003837e`
- `KERNEL32!GetLastError` at `0x1800383ff`
- `KERNEL32!GetLastError` at `0x1800385d5`
- `KERNEL32!GetLastError` at `0x180038633`
- `KERNEL32!GetLastError` at `0x180038687`
- `GDI32!DeleteDC` at `0x1800385c1`
- `GDI32!DeleteDC` at `0x1800385c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PrintRandomDocumentEx(__int64 a1, const WCHAR *a2, const WCHAR *a3)
{
  __int64 v6; // rdi
  unsigned int v7; // esi
  unsigned int LastError; // ebx
  DWORD FullPathNameW; // eax
  bool v10; // zf
  char v11; // al
  void *File; // rax
  void *v13; // rdi
  DWORD FileSize; // r14d
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  _WORD *v17; // rdx
  __int64 v18; // rax
  WCHAR *v19; // rcx
  _WORD *v20; // rcx
  signed int v21; // edi
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+44h] [rbp-BCh] BYREF
  LPWSTR FilePart; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v26[20]; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v27; // [rsp+A0h] [rbp-60h]
  HDC hdc[2]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v29[2]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v31[528]; // [rsp+2F0h] [rbp+1F0h] BYREF
  WCHAR PathName[264]; // [rsp+500h] [rbp+400h] BYREF
  WCHAR TempFileName[264]; // [rsp+710h] [rbp+610h] BYREF

  v23 = 0;
  memset_0(Buffer, 0, 0x208u);
  memset_0(PathName, 0, 0x208u);
  memset_0(TempFileName, 0, 0x208u);
  memset_0(v31, 0, 0x208u);
  FilePart = 0;
  v26[1] = 0;
  memset_0(v26, 0, 0x54u);
  v24 = 0;
  memset(v29, 0, 28);
  *(_OWORD *)hdc = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
  }
  v6 = 260;
  v7 = 1;
  if ( !(unsigned int)GetTempPath2W(260, PathName) || !GetTempFileNameW(PathName, L"fax", 0, TempFileName) )
  {
    LastError = GetLastError();
    goto LABEL_67;
  }
  FullPathNameW = GetFullPathNameW(TempFileName, 0x104u, Buffer, &FilePart);
  if ( !FullPathNameW )
    goto LABEL_65;
  if ( FullPathNameW > 0x104 )
  {
    LastError = 111;
    goto LABEL_66;
  }
  LastError = 0;
  v10 = (unsigned int)ConvertTiffFileToValidFaxFormat(a2, Buffer, &v23) == 0;
  v11 = v23;
  if ( v10 )
  {
    if ( (v23 & 4) != 0 )
      goto LABEL_14;
    v11 = v23 | 4;
    v23 |= 4u;
  }
  if ( (v11 & 4) == 0 )
  {
    if ( (v11 & 2) == 0 )
    {
      if ( (v11 & 1) == 0 )
      {
        LastError = 13;
        DeleteFileW(a3);
        goto LABEL_66;
      }
      if ( CopyFileW(a2, a3, 0) )
        goto LABEL_66;
      LastError = GetLastError();
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_66;
      }
      v16 = 89;
      goto LABEL_26;
    }
    if ( !a1 )
    {
      LastError = 87;
      goto LABEL_66;
    }
    v10 = (v11 & 1) == 0;
    v17 = v31;
    v18 = 2147483646;
    if ( v10 )
    {
      v19 = Buffer;
      do
      {
        if ( !v18 )
          break;
        if ( !*v19 )
          break;
        *v17++ = *v19++;
        --v18;
        --v6;
      }
      while ( v6 );
    }
    else
    {
      do
      {
        if ( !v18 )
          break;
        if ( !*a2 )
          break;
        *v17++ = *a2++;
        --v18;
        --v6;
      }
      while ( v6 );
    }
    v20 = v17 - 1;
    if ( v6 )
      v20 = v17;
    v21 = v6 == 0 ? 0x8007007A : 0;
    *v20 = 0;
    if ( v21 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          87,
          WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids,
          (unsigned int)v21);
      }
      LastError = (unsigned __int16)v21;
      if ( (v21 & 0x1FFF0000) != 0x70000 )
        LastError = v21;
      goto LABEL_66;
    }
    memset_0(v26, 0, 0x58u);
    v26[0] = 88;
    v27 = a3;
    *(_OWORD *)hdc = 0;
    LODWORD(hdc[0]) = 48;
    memset(v29, 0, sizeof(v29));
    if ( (unsigned int)FaxStartPrintJob_InternalW(0, (unsigned int)v26, 0, (unsigned int)&v24, (__int64)hdc) )
    {
      LastError = (unsigned int)PrintTiffFile(a1, hdc[1], v31) == 0 ? 0x65B : 0;
      if ( DeleteDC(hdc[1]) )
        goto LABEL_66;
      LastError = GetLastError();
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_66;
      }
      v16 = 88;
      goto LABEL_26;
    }
LABEL_65:
    LastError = GetLastError();
    goto LABEL_66;
  }
LABEL_14:
  if ( !a1 || !(unsigned int)PrintRandomDocument(a1, a2, a3) )
    goto LABEL_65;
  File = (void *)InternalSafeCreateFile(a3, 0x80000000, 1u, 3u, 128);
  v13 = File;
  if ( File == (void *)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        (unsigned int)WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids,
        (_DWORD)a3,
        LastError);
    }
    goto LABEL_66;
  }
  FileSize = GetFileSize(File, 0);
  CloseHandle(v13);
  if ( FileSize != -1 )
  {
    if ( !FileSize )
      LastError = 13;
    goto LABEL_66;
  }
  LastError = GetLastError();
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = 86;
LABEL_26:
    WPP_SF_d(v15[2], v16, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, LastError);
  }
LABEL_66:
  DeleteFileW(Buffer);
LABEL_67:
  if ( LastError )
  {
    SetLastError(LastError);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180038190  mov     [rsp-8+arg_18], rbx
0x180038195  push    rbp
0x180038196  push    rsi
0x180038197  push    rdi
0x180038198  push    r12
0x18003819a  push    r13
0x18003819c  push    r14
0x18003819e  push    r15
0x1800381a0  lea     rbp, [rsp-830h]
0x1800381a8  sub     rsp, 930h
0x1800381af  mov     rax, cs:__security_cookie
0x1800381b6  xor     rax, rsp
0x1800381b9  mov     [rbp+860h+var_40], rax
0x1800381c0  mov     r15, r8
0x1800381c3  mov     r14, rdx
0x1800381c6  mov     r12, rcx
0x1800381c9  mov     ebx, 208h
0x1800381ce  xor     r13d, r13d
0x1800381d1  lea     rcx, [rbp+860h+Buffer]; void *
0x1800381d5  mov     r8d, ebx; Size
0x1800381d8  mov     [rsp+960h+var_920], r13d
0x1800381dd  xor     edx, edx; Val
0x1800381df  call    memset_0
0x1800381e4  mov     r8d, ebx; Size
0x1800381e7  lea     rcx, [rbp+860h+PathName]; void *
0x1800381ee  xor     edx, edx; Val
0x1800381f0  call    memset_0
0x1800381f5  mov     r8d, ebx; Size
0x1800381f8  lea     rcx, [rbp+860h+TempFileName]; void *
0x1800381ff  xor     edx, edx; Val
0x180038201  call    memset_0
0x180038206  mov     r8d, ebx; Size
0x180038209  lea     rcx, [rbp+860h+var_670]; void *
0x180038210  xor     edx, edx; Val
0x180038212  call    memset_0
0x180038217  xor     eax, eax
0x180038219  mov     [rsp+960h+FilePart], r13
0x18003821e  xor     edx, edx; Val
0x180038220  mov     [rsp+960h+var_90C], eax
0x180038224  lea     rcx, [rsp+960h+var_910]; void *
0x180038229  lea     ebx, [rax+54h]
0x18003822c  mov     r8d, ebx; Size
0x18003822f  call    memset_0
0x180038234  xorps   xmm0, xmm0
0x180038237  mov     [rsp+960h+var_91C], r13d
0x18003823c  movups  [rbp+860h+var_8A0], xmm0
0x180038240  xor     eax, eax
0x180038242  movups  [rbp+860h+var_8A0+0Ch], xmm0
0x180038246  movups  xmmword ptr [rbp+860h+hdc], xmm0
0x18003824a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038251  lea     rax, WPP_GLOBAL_Control
0x180038258  cmp     rcx, rax
0x18003825b  jz      short loc_18003827B
0x18003825d  test    byte ptr [rcx+1Ch], 2
0x180038261  jz      short loc_18003827B
0x180038263  cmp     byte ptr [rcx+19h], 5
0x180038267  jb      short loc_18003827B
0x180038269  mov     rcx, [rcx+10h]
0x18003826d  lea     r8, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids
0x180038274  mov     edx, ebx
0x180038276  call    WPP_SF_
0x18003827b  mov     edi, 104h
0x180038280  lea     rdx, [rbp+860h+PathName]
0x180038287  mov     ecx, edi
0x180038289  call    cs:__imp_GetTempPath2W
0x180038290  nop     dword ptr [rax+rax+00h]
0x180038295  mov     esi, 1
0x18003829a  test    eax, eax
0x18003829c  jnz     short loc_1800382B1
0x18003829e  call    cs:__imp_GetLastError
0x1800382a5  nop     dword ptr [rax+rax+00h]
0x1800382aa  mov     ebx, eax
0x1800382ac  jmp     loc_1800386A5
0x1800382b1  lea     r9, [rbp+860h+TempFileName]; lpTempFileName
0x1800382b8  xor     r8d, r8d; uUnique
0x1800382bb  lea     rdx, PrefixString; "fax"
0x1800382c2  lea     rcx, [rbp+860h+PathName]; lpPathName
0x1800382c9  call    cs:__imp_GetTempFileNameW
0x1800382d0  nop     dword ptr [rax+rax+00h]
0x1800382d5  test    eax, eax
0x1800382d7  jz      short loc_18003829E
0x1800382d9  lea     r9, [rsp+960h+FilePart]; lpFilePart
0x1800382de  mov     edx, edi; nBufferLength
0x1800382e0  lea     r8, [rbp+860h+Buffer]; lpBuffer
0x1800382e4  lea     rcx, [rbp+860h+TempFileName]; lpFileName
0x1800382eb  call    cs:__imp_GetFullPathNameW
0x1800382f2  nop     dword ptr [rax+rax+00h]
0x1800382f7  test    eax, eax
0x1800382f9  jz      loc_180038687
0x1800382ff  cmp     eax, edi
0x180038301  ja      loc_180038680
0x180038307  lea     r8, [rsp+960h+var_920]
0x18003830c  mov     rcx, r14
0x18003830f  lea     rdx, [rbp+860h+Buffer]
0x180038313  mov     ebx, r13d
0x180038316  call    ConvertTiffFileToValidFaxFormat
0x18003831b  test    eax, eax
0x18003831d  mov     eax, [rsp+960h+var_920]
0x180038321  jnz     short loc_18003832E
0x180038323  test    al, 4
0x180038325  jnz     short loc_180038336
0x180038327  or      eax, 4
0x18003832a  mov     [rsp+960h+var_920], eax
0x18003832e  test    al, 4
0x180038330  jz      loc_180038467
0x180038336  test    r12, r12
0x180038339  jz      loc_180038687
0x18003833f  mov     r8, r15
0x180038342  mov     rdx, r14
0x180038345  mov     rcx, r12
0x180038348  call    PrintRandomDocument
0x18003834d  test    eax, eax
0x18003834f  jz      loc_180038687
0x180038355  mov     [rsp+960h+var_938], 80h; int
0x18003835d  mov     r8d, esi; dwShareMode
0x180038360  mov     edx, 80000000h; dwDesiredAccess
0x180038365  mov     [rsp+960h+var_940], 3; DWORD
0x18003836d  mov     rcx, r15; lpFileName
0x180038370  call    InternalSafeCreateFile
0x180038375  mov     rdi, rax
0x180038378  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003837c  jnz     short loc_1800383D6
0x18003837e  call    cs:__imp_GetLastError
0x180038385  nop     dword ptr [rax+rax+00h]
0x18003838a  mov     ebx, eax
0x18003838c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038393  lea     rax, WPP_GLOBAL_Control
0x18003839a  cmp     rcx, rax
0x18003839d  jz      loc_180038695
0x1800383a3  test    byte ptr [rcx+1Ch], 2
0x1800383a7  jz      loc_180038695
0x1800383ad  cmp     byte ptr [rcx+19h], 2
0x1800383b1  jb      loc_180038695
0x1800383b7  mov     rcx, [rcx+10h]
0x1800383bb  lea     edx, [rdi+56h]
0x1800383be  mov     r9, r15
0x1800383c1  mov     [rsp+960h+var_940], ebx
0x1800383c5  lea     r8, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids
0x1800383cc  call    WPP_SF_Sd
0x1800383d1  jmp     loc_180038695
0x1800383d6  xor     edx, edx; lpFileSizeHigh
0x1800383d8  mov     rcx, rdi; hFile
0x1800383db  call    cs:__imp_GetFileSize
0x1800383e2  nop     dword ptr [rax+rax+00h]
0x1800383e7  mov     rcx, rdi; hObject
0x1800383ea  mov     r14d, eax
0x1800383ed  call    cs:__imp_CloseHandle
0x1800383f4  nop     dword ptr [rax+rax+00h]
0x1800383f9  cmp     r14d, 0FFFFFFFFh
0x1800383fd  jnz     short loc_180038455
0x1800383ff  call    cs:__imp_GetLastError
0x180038406  nop     dword ptr [rax+rax+00h]
0x18003840b  mov     ebx, eax
0x18003840d  mov     rcx, cs:WPP_GLOBAL_Control
0x180038414  lea     rax, WPP_GLOBAL_Control
0x18003841b  cmp     rcx, rax
0x18003841e  jz      loc_180038695
0x180038424  test    byte ptr [rcx+1Ch], 2
0x180038428  jz      loc_180038695
0x18003842e  cmp     byte ptr [rcx+19h], 2
0x180038432  jb      loc_180038695
0x180038438  mov     edx, 56h ; 'V'
0x18003843d  mov     rcx, [rcx+10h]
0x180038441  lea     r8, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids
0x180038448  mov     r9d, ebx
0x18003844b  call    WPP_SF_d
0x180038450  jmp     loc_180038695
0x180038455  test    r14d, r14d
0x180038458  jnz     loc_180038695
0x18003845e  lea     ebx, [r14+0Dh]
0x180038462  jmp     loc_180038695
0x180038467  test    al, 2
0x180038469  jz      loc_180038615
0x18003846f  test    r12, r12
0x180038472  jnz     short loc_18003847E
0x180038474  lea     ebx, [r12+57h]
0x180038479  jmp     loc_180038695
0x18003847e  test    sil, al
0x180038481  lea     rdx, [rbp+860h+var_670]
0x180038488  mov     eax, 7FFFFFFEh
0x18003848d  jz      short loc_1800384B2
0x18003848f  test    rax, rax
0x180038492  jz      short loc_1800384D9
0x180038494  movzx   ecx, word ptr [r14]
0x180038498  test    cx, cx
0x18003849b  jz      short loc_1800384D9
0x18003849d  mov     [rdx], cx
0x1800384a0  add     r14, 2
0x1800384a4  add     rdx, 2
0x1800384a8  sub     rax, rsi
0x1800384ab  sub     rdi, rsi
0x1800384ae  jnz     short loc_18003848F
0x1800384b0  jmp     short loc_1800384D9
0x1800384b2  lea     rcx, [rbp+860h+Buffer]
0x1800384b6  test    rax, rax
0x1800384b9  jz      short loc_1800384D9
0x1800384bb  movzx   r8d, word ptr [rcx]
0x1800384bf  test    r8w, r8w
0x1800384c3  jz      short loc_1800384D9
0x1800384c5  mov     [rdx], r8w
0x1800384c9  add     rcx, 2
0x1800384cd  add     rdx, 2
0x1800384d1  sub     rax, rsi
0x1800384d4  sub     rdi, rsi
0x1800384d7  jnz     short loc_1800384B6
0x1800384d9  test    rdi, rdi
0x1800384dc  lea     rcx, [rdx-2]
0x1800384e0  cmovnz  rcx, rdx
0x1800384e4  neg     rdi
0x1800384e7  sbb     edi, edi
0x1800384e9  not     edi
0x1800384eb  and     edi, 8007007Ah
0x1800384f1  mov     [rcx], r13w
0x1800384f5  test    edi, edi
0x1800384f7  jns     short loc_180038547
0x1800384f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180038500  lea     rax, WPP_GLOBAL_Control
0x180038507  cmp     rcx, rax
0x18003850a  jz      short loc_180038530
0x18003850c  test    byte ptr [rcx+1Ch], 2
0x180038510  jz      short loc_180038530
0x180038512  cmp     byte ptr [rcx+19h], 2
0x180038516  jb      short loc_180038530
0x180038518  mov     rcx, [rcx+10h]
0x18003851c  lea     r8, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids
0x180038523  mov     edx, 57h ; 'W'
0x180038528  mov     r9d, edi
0x18003852b  call    WPP_SF_d
0x180038530  mov     eax, edi
0x180038532  movzx   ebx, di
0x180038535  and     eax, 1FFF0000h
0x18003853a  cmp     eax, 70000h
0x18003853f  cmovnz  ebx, edi
0x180038542  jmp     loc_180038695
0x180038547  mov     edi, 58h ; 'X'
0x18003854c  lea     rcx, [rsp+960h+var_910]; void *
0x180038551  mov     r8d, edi; Size
0x180038554  xor     edx, edx; Val
0x180038556  call    memset_0
0x18003855b  xorps   xmm0, xmm0
0x18003855e  mov     [rsp+960h+var_910], edi
0x180038562  lea     rax, [rbp+860h+hdc]
0x180038566  mov     [rbp+860h+var_8C0], r15
0x18003856a  movups  xmmword ptr [rbp+860h+hdc], xmm0
0x18003856e  xor     r8d, r8d
0x180038571  mov     dword ptr [rbp+860h+hdc], 30h ; '0'
0x180038578  lea     r9, [rsp+960h+var_91C]
0x18003857d  mov     qword ptr [rsp+960h+var_940], rax
0x180038582  lea     rdx, [rsp+960h+var_910]
0x180038587  xor     ecx, ecx
0x180038589  movups  [rbp+860h+var_8A0], xmm0
0x18003858d  movups  [rbp+860h+var_890], xmm0
0x180038591  call    FaxStartPrintJob_InternalW
0x180038596  test    eax, eax
0x180038598  jz      loc_180038687
0x18003859e  mov     rdx, [rbp+860h+hdc+8]
0x1800385a2  lea     r8, [rbp+860h+var_670]
0x1800385a9  mov     rcx, r12
0x1800385ac  call    PrintTiffFile
0x1800385b1  mov     rcx, [rbp+860h+hdc+8]; hdc
0x1800385b5  neg     eax
0x1800385b7  sbb     ebx, ebx
0x1800385b9  not     ebx
0x1800385bb  and     ebx, 65Bh
0x1800385c1  call    cs:__imp_DeleteDC
0x1800385c8  nop     dword ptr [rax+rax+00h]
0x1800385cd  test    eax, eax
0x1800385cf  jnz     loc_180038695
0x1800385d5  call    cs:__imp_GetLastError
0x1800385dc  nop     dword ptr [rax+rax+00h]
0x1800385e1  mov     ebx, eax
0x1800385e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800385ea  lea     rax, WPP_GLOBAL_Control
0x1800385f1  cmp     rcx, rax
0x1800385f4  jz      loc_180038695
0x1800385fa  test    byte ptr [rcx+1Ch], 2
0x1800385fe  jz      loc_180038695
0x180038604  cmp     byte ptr [rcx+19h], 2
0x180038608  jb      loc_180038695
0x18003860e  mov     edx, edi
0x180038610  jmp     loc_18003843D
0x180038615  test    sil, al
0x180038618  jz      short loc_18003866A
0x18003861a  xor     r8d, r8d; bFailIfExists
0x18003861d  mov     rdx, r15; lpNewFileName
0x180038620  mov     rcx, r14; lpExistingFileName
0x180038623  call    cs:__imp_CopyFileW
0x18003862a  nop     dword ptr [rax+rax+00h]
0x18003862f  test    eax, eax
0x180038631  jnz     short loc_180038695
0x180038633  call    cs:__imp_GetLastError
0x18003863a  nop     dword ptr [rax+rax+00h]
0x18003863f  mov     ebx, eax
0x180038641  mov     rcx, cs:WPP_GLOBAL_Control
0x180038648  lea     rax, WPP_GLOBAL_Control
0x18003864f  cmp     rcx, rax
0x180038652  jz      short loc_180038695
0x180038654  test    byte ptr [rcx+1Ch], 2
0x180038658  jz      short loc_180038695
0x18003865a  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
