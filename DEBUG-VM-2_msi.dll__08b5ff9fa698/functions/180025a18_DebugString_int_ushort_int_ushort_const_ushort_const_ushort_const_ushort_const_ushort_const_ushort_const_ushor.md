# DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)

- ea: `0x180025a18`
- end: `0x180025f57`
- name: `?DebugString@@YAXHGHPEBG000000KPEAX@Z`
- size: `1343`
- prototype: `void(int, unsigned __int16, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void *)`
- caller_count: `665`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180001700`
- `0x1800028b0`
- `0x1800074c4`
- `0x180007f20`
- `0x18000c0cc`
- `0x18000cfa0`
- `0x18000d758`
- `0x18000e424`
- `0x18000f290`
- `0x1800117c0`
- `0x180013264`
- `0x18001354c`
- `0x180013ecc`
- `0x180013fe4`
- `0x180014848`
- `0x180015ac0`
- `0x18001ab38`
- `0x18001b230`
- `0x18001cab0`
- `0x18001cca0`
- `0x18001d960`
- `0x18001db00`
- `0x18001df20`
- `0x18001e0bc`
- `0x18001e2d8`
- `0x18001e5d0`
- `0x18001f190`
- `0x18001f700`
- `0x18001fd10`
- `0x180021030`
- `0x1800227d0`
- `0x180024f9c`
- `0x1800252a8`
- `0x180027b54`
- `0x180028670`
- `0x180028a90`
- `0x180029718`
- `0x18002b35c`
- `0x18002d00c`
- `0x18002dcd8`
- `0x18002de5c`
- `0x18002e3ec`
- `0x180030568`
- `0x180032374`
- `0x180033f6c`
- `0x180035ac0`
- `0x180037278`
- `0x180037558`
- `0x180038534`
- `0x1800387cc`

## callees

- `0x180022120`
- `0x180025a18`
- `0x18003cd20`
- `0x180090e50`
- `0x18009dadc`
- `0x1800c3fb8`
- `0x1800c41c8`
- `0x18011c130`
- `0x180145e58`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180025af3`
- `KERNEL32!GetCurrentThreadId` at `0x180025af3`
- `KERNEL32!FormatMessageW` at `0x180025dea`
- `KERNEL32!FormatMessageW` at `0x180025e44`
- `KERNEL32!FormatMessageW` at `0x180025dea`
- `KERNEL32!FormatMessageW` at `0x180025e44`
- `KERNEL32!GetLastError` at `0x180025df4`
- `KERNEL32!GetLastError` at `0x180025df4`
- `KERNEL32!OutputDebugStringW` at `0x180025ef1`
- `KERNEL32!OutputDebugStringW` at `0x180025efe`
- `KERNEL32!OutputDebugStringW` at `0x180025ef1`
- `KERNEL32!OutputDebugStringW` at `0x180025efe`
- `KERNEL32!GlobalFree` at `0x180025ca3`
- `KERNEL32!GlobalFree` at `0x180025ca3`
- `KERNEL32!GetCurrentProcessId` at `0x180025d0e`
- `KERNEL32!GetCurrentProcessId` at `0x180025d0e`
- `KERNEL32!GetLocalTime` at `0x180025b13`
- `KERNEL32!GetLocalTime` at `0x180025b13`

## string_xrefs

- `0x180025b2b`: `MSI (a)`
- `0x180025b3a`: `MSI (c)`
- `0x180025b19`: `MSI (s)`

## pseudocode

```c
void __fastcall DebugString(
        int a1,
        unsigned __int16 a2,
        DWORD a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        const unsigned __int16 *a10,
        unsigned int a11,
        void *a12)
{
  const unsigned __int16 *v13; // rdi
  const unsigned __int16 *v15; // r15
  int v16; // eax
  int CurrentThreadId; // esi
  __int128 *v18; // r10
  int v19; // r9d
  _OWORD *v20; // rcx
  int v21; // ebx
  unsigned __int8 v22; // al
  char v23; // di
  HINSTANCE MsgDll; // rbx
  DWORD v25; // r15d
  int v26; // eax
  unsigned __int16 v27[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v28; // [rsp+64h] [rbp-9Ch]
  DWORD dwMessageId; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v30; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v31; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v32; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v33; // [rsp+88h] [rbp-78h]
  unsigned int v34; // [rsp+90h] [rbp-70h] BYREF
  void *v35; // [rsp+98h] [rbp-68h]
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  HGLOBAL hMem; // [rsp+B0h] [rbp-50h] BYREF
  int v38; // [rsp+B8h] [rbp-48h]
  char v39; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v40[224]; // [rsp+100h] [rbp+0h] BYREF
  va_list Arguments[7]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v42; // [rsp+2F8h] [rbp+1F8h] BYREF
  __int128 v43; // [rsp+308h] [rbp+208h] BYREF
  __int128 v44; // [rsp+318h] [rbp+218h] BYREF
  unsigned __int16 v45[8]; // [rsp+330h] [rbp+230h] BYREF
  __int128 v46; // [rsp+340h] [rbp+240h]
  __int128 v47; // [rsp+350h] [rbp+250h]
  __int128 v48; // [rsp+360h] [rbp+260h]

  v13 = a6;
  v15 = a7;
  v33 = a8;
  v32 = a9;
  v35 = a12;
  v16 = g_dmDiagnosticMode;
  dwMessageId = a3;
  v28 = a2;
  v30 = a6;
  v31 = a7;
  if ( g_dmDiagnosticMode == -1 )
  {
    SetDiagnosticMode();
    v16 = g_dmDiagnosticMode;
  }
  if ( ((v16 | 0x10) & a1) == 0 )
    return;
  if ( (dword_18030B358 & 1) == 0 )
  {
    dword_18030B358 |= 1u;
    dword_18030B35C = (unsigned __int8)GetCurrentProcessId();
  }
  *(_DWORD *)v27 = (unsigned __int8)GetCurrentThreadId();
  CurrentThreadId = (unsigned __int8)MsiGetCurrentThreadId();
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v18 = 0;
  v43 = *(_OWORD *)L"MSI (s)";
  v42 = *(_OWORD *)L"MSI (a)";
  v44 = *(_OWORD *)L"MSI (c)";
  if ( g_scServerContext )
  {
    if ( g_scServerContext == 1 || g_scServerContext == 2 )
    {
      v18 = &v43;
    }
    else if ( g_scServerContext == 3 )
    {
      v18 = &v42;
    }
  }
  else
  {
    v18 = &v44;
  }
  v19 = 58;
  if ( *(_DWORD *)v27 != CurrentThreadId )
    v19 = 33;
  if ( (int)StringCchPrintfW(
              v45,
              0x21u,
              L"%s (%.2X%c%.2X) [%02u:%02u:%02u:%03u]: ",
              v18,
              dword_18030B35C,
              v19,
              CurrentThreadId,
              SystemTime.wHour,
              SystemTime.wMinute,
              SystemTime.wSecond,
              SystemTime.wMilliseconds) < 0 )
    return;
  v38 = 256;
  hMem = &v39;
  if ( (a1 & 0x10) != 0 )
  {
    Arguments[4] = (va_list)v33;
    Arguments[5] = (va_list)v32;
    Arguments[3] = (va_list)a7;
    Arguments[2] = (va_list)a6;
    Arguments[0] = (va_list)a4;
    Arguments[1] = (va_list)a5;
    v23 = 0;
    Arguments[6] = (va_list)a10;
    v34 = (_WORD)dword_180306E9C == 0;
    v27[0] = dword_180306E9C;
    while ( MsiSwitchLanguage(&v34, v27) )
    {
      MsgDll = GetMsgDll(v27[0]);
      if ( MsgDll )
      {
        v25 = v27[0];
        if ( !FormatMessageW(0x2800u, MsgDll, dwMessageId, v27[0], (LPWSTR)hMem + 32, v38 - 32, Arguments) )
        {
          if ( GetLastError() == 122
            && (unsigned __int8)CAPITempBuffer<unsigned short,256>::SetSize(&hMem, 1100)
            && FormatMessageW(0x2800u, MsgDll, dwMessageId, v25, (LPWSTR)hMem + 32, v38 - 32, Arguments) )
          {
            v23 = 1;
          }
          if ( !v23 )
            continue;
        }
      }
      goto LABEL_41;
    }
    *((_WORD *)hMem + 32) = 0;
LABEL_41:
    v15 = v31;
    v13 = v30;
  }
  else if ( (unsigned int)StringCchPrintfW(v40, 0xE0u, a4, a5, a6, a7, v33, v32, a10) == -2147024774 )
  {
    if ( (unsigned __int8)CAPITempBuffer<unsigned short,256>::SetSize(&hMem, 1100) )
    {
      v26 = StringCchPrintfW((unsigned __int16 *)hMem + 32, v38 - 32, a4, a5, a6, a7, v33, v32, a10);
      if ( v26 < 0 && v26 != -2147024774 )
        goto LABEL_23;
    }
  }
  v20 = hMem;
  if ( !hMem || v38 < 32 )
  {
    if ( v38 > 256 )
      goto LABEL_25;
    return;
  }
  v21 = g_dmDiagnosticMode;
  v22 = g_dmDiagnosticMode;
  *(_OWORD *)hMem = *(_OWORD *)v45;
  v20[1] = v46;
  v20[2] = v47;
  v20[3] = v48;
  if ( ((unsigned __int8)a1 & v22 & 3) != 0 )
  {
    OutputDebugStringW((LPCWSTR)hMem);
    OutputDebugStringW(L"\r\n");
    v21 = g_dmDiagnosticMode;
  }
  if ( ((unsigned __int8)a1 & (unsigned __int8)v21 & 0xC) != 0 )
  {
    g_dmDiagnosticMode = 0;
    WriteLog((const unsigned __int16 *)hMem);
    g_dmDiagnosticMode = v21;
  }
  if ( (a1 & 0x10) != 0 )
    ReportToEventLogW(v28, dwMessageId, a4, a5, v13, v15, v33, v32, a11, v35);
LABEL_23:
  if ( v38 > 256 )
  {
    v20 = hMem;
LABEL_25:
    GlobalFree(v20);
  }
}

```

## disassembly

```asm
0x180025a18  mov     [rsp-8+arg_0], rbx
0x180025a1d  push    rbp
0x180025a1e  push    rsi
0x180025a1f  push    rdi
0x180025a20  push    r12
0x180025a22  push    r13
0x180025a24  push    r14
0x180025a26  push    r15
0x180025a28  lea     rbp, [rsp-290h]
0x180025a30  sub     rsp, 390h
0x180025a37  mov     rax, cs:__security_cookie
0x180025a3e  xor     rax, rsp
0x180025a41  mov     [rbp+2C0h+var_40], rax
0x180025a48  mov     rax, [rbp+2C0h+arg_38]
0x180025a4f  mov     r12, r9
0x180025a52  mov     rdi, [rbp+2C0h+arg_28]
0x180025a59  mov     r14d, ecx
0x180025a5c  mov     r15, [rbp+2C0h+arg_30]
0x180025a63  mov     r13, [rbp+2C0h+arg_20]
0x180025a6a  mov     rbx, [rbp+2C0h+arg_48]
0x180025a71  mov     [rbp+2C0h+var_338], rax
0x180025a75  mov     rax, [rbp+2C0h+arg_40]
0x180025a7c  mov     [rbp+2C0h+var_340], rax
0x180025a80  mov     rax, [rbp+2C0h+arg_58]
0x180025a87  mov     [rbp+2C0h+var_328], rax
0x180025a8b  mov     eax, cs:?g_dmDiagnosticMode@@3HA; int g_dmDiagnosticMode
0x180025a91  mov     [rsp+3C0h+dwMessageId], r8d
0x180025a96  mov     [rsp+3C0h+var_35C], dx
0x180025a9b  mov     [rsp+3C0h+var_350], rdi
0x180025aa0  mov     [rsp+3C0h+var_348], r15
0x180025aa5  cmp     eax, 0FFFFFFFFh
0x180025aa8  jz      loc_180025CE7
0x180025aae  or      eax, 10h
0x180025ab1  test    r14d, eax
0x180025ab4  jnz     short loc_180025AE0
0x180025ab6  mov     rcx, [rbp+2C0h+var_40]
0x180025abd  xor     rcx, rsp; StackCookie
0x180025ac0  call    __security_check_cookie
0x180025ac5  mov     rbx, [rsp+3C0h+arg_0]
0x180025acd  add     rsp, 390h
0x180025ad4  pop     r15
0x180025ad6  pop     r14
0x180025ad8  pop     r13
0x180025ada  pop     r12
0x180025adc  pop     rdi
0x180025add  pop     rsi
0x180025ade  pop     rbp
0x180025adf  retn
0x180025ae0  mov     eax, cs:dword_18030B358
0x180025ae6  mov     ecx, 1
0x180025aeb  test    cl, al
0x180025aed  jz      loc_180025D06
0x180025af3  call    cs:__imp_GetCurrentThreadId
0x180025af9  movzx   eax, al
0x180025afc  mov     dword ptr [rsp+3C0h+var_360], eax
0x180025b00  call    ?MsiGetCurrentThreadId@@YA?AUUniqueThreadID@@XZ; MsiGetCurrentThreadId(void)
0x180025b05  xorps   xmm0, xmm0
0x180025b08  movzx   esi, al
0x180025b0b  lea     rcx, [rbp+2C0h+SystemTime]; lpSystemTime
0x180025b0f  movups  xmmword ptr [rbp+2C0h+SystemTime.wYear], xmm0
0x180025b13  call    cs:__imp_GetLocalTime
0x180025b19  movups  xmm0, xmmword ptr cs:aMsiS; "MSI (s)"
0x180025b20  mov     ecx, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x180025b26  xor     edx, edx
0x180025b28  mov     r10d, edx
0x180025b2b  movups  xmm1, xmmword ptr cs:aMsiA; "MSI (a)"
0x180025b32  movdqu  [rbp+2C0h+var_B8], xmm0
0x180025b3a  movups  xmm0, xmmword ptr cs:aMsiC; "MSI (c)"
0x180025b41  movdqu  [rbp+2C0h+var_C8], xmm1
0x180025b49  movdqu  [rbp+2C0h+var_A8], xmm0
0x180025b51  test    ecx, ecx
0x180025b53  jz      loc_180025D22
0x180025b59  sub     ecx, 1
0x180025b5c  jnz     loc_180025CC9
0x180025b62  lea     r10, [rbp+2C0h+var_B8]
0x180025b69  movzx   eax, [rbp+2C0h+SystemTime.wMilliseconds]
0x180025b6d  mov     r9d, 3Ah ; ':'
0x180025b73  movzx   ecx, [rbp+2C0h+SystemTime.wSecond]
0x180025b77  movzx   edx, [rbp+2C0h+SystemTime.wMinute]
0x180025b7b  movzx   r8d, [rbp+2C0h+SystemTime.wHour]
0x180025b80  cmp     dword ptr [rsp+3C0h+var_360], esi
0x180025b84  lea     r11d, [r9-19h]
0x180025b88  mov     [rsp+3C0h+var_370], eax
0x180025b8c  mov     eax, cs:dword_18030B35C
0x180025b92  cmovnz  r9d, r11d
0x180025b96  mov     dword ptr [rsp+3C0h+var_378], ecx
0x180025b9a  lea     rcx, [rbp+2C0h+var_90]; unsigned __int16 *
0x180025ba1  mov     [rsp+3C0h+var_380], edx
0x180025ba5  mov     edx, r11d; unsigned __int64
0x180025ba8  mov     dword ptr [rsp+3C0h+var_388], r8d
0x180025bad  lea     r8, aS2xC2x02u02u02_0; "%s (%.2X%c%.2X) [%02u:%02u:%02u:%03u]: "
0x180025bb4  mov     dword ptr [rsp+3C0h+Arguments], esi
0x180025bb8  mov     [rsp+3C0h+nSize], r9d
0x180025bbd  mov     r9, r10
0x180025bc0  mov     dword ptr [rsp+3C0h+lpBuffer], eax
0x180025bc4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025bc9  test    eax, eax
0x180025bcb  js      loc_180025AB6
0x180025bd1  mov     esi, r14d
0x180025bd4  mov     [rbp+2C0h+var_308], 100h
0x180025bdb  lea     rax, [rbp+2C0h+var_300]
0x180025bdf  mov     [rbp+2C0h+hMem], rax
0x180025be3  and     esi, 10h
0x180025be6  jnz     loc_180025D2E
0x180025bec  mov     rax, [rbp+2C0h+var_340]
0x180025bf0  lea     rcx, [rbp+2C0h+var_2C0]; unsigned __int16 *
0x180025bf4  mov     qword ptr [rsp+3C0h+var_380], rbx
0x180025bf9  mov     r9, r13
0x180025bfc  mov     [rsp+3C0h+var_388], rax
0x180025c01  mov     r8, r12; unsigned __int16 *
0x180025c04  mov     rax, [rbp+2C0h+var_338]
0x180025c08  mov     edx, 0E0h; unsigned __int64
0x180025c0d  mov     [rsp+3C0h+Arguments], rax
0x180025c12  mov     qword ptr [rsp+3C0h+nSize], r15
0x180025c17  mov     [rsp+3C0h+lpBuffer], rdi
0x180025c1c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025c21  cmp     eax, 8007007Ah
0x180025c26  jz      loc_180025E82
0x180025c2c  mov     rcx, [rbp+2C0h+hMem]
0x180025c30  test    rcx, rcx
0x180025c33  jz      loc_180025CF7
0x180025c39  cmp     [rbp+2C0h+var_308], 20h ; ' '
0x180025c3d  jl      loc_180025CF7
0x180025c43  movaps  xmm0, xmmword ptr [rbp+2C0h+var_90]
0x180025c4a  mov     ebx, cs:?g_dmDiagnosticMode@@3HA; int g_dmDiagnosticMode
0x180025c50  mov     eax, ebx
0x180025c52  movups  xmmword ptr [rcx], xmm0
0x180025c55  and     eax, r14d
0x180025c58  movaps  xmm1, [rbp+2C0h+var_80]
0x180025c5f  movups  xmmword ptr [rcx+10h], xmm1
0x180025c63  movaps  xmm0, [rbp+2C0h+var_70]
0x180025c6a  movups  xmmword ptr [rcx+20h], xmm0
0x180025c6e  movaps  xmm1, [rbp+2C0h+var_60]
0x180025c75  movups  xmmword ptr [rcx+30h], xmm1
0x180025c79  test    al, 3
0x180025c7b  jnz     loc_180025EED
0x180025c81  mov     eax, ebx
0x180025c83  and     eax, r14d
0x180025c86  test    al, 0Ch
0x180025c88  jnz     short loc_180025CAE
0x180025c8a  test    esi, esi
0x180025c8c  jnz     loc_180025F0F
0x180025c92  cmp     [rbp+2C0h+var_308], 100h
0x180025c99  jle     loc_180025AB6
0x180025c9f  mov     rcx, [rbp+2C0h+hMem]; hMem
0x180025ca3  call    cs:__imp_GlobalFree
0x180025ca9  jmp     loc_180025AB6
0x180025cae  mov     rcx, [rbp+2C0h+hMem]; Src
0x180025cb2  mov     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x180025cbc  call    ?WriteLog@@YA_NPEBG@Z; WriteLog(ushort const *)
0x180025cc1  mov     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x180025cc7  jmp     short loc_180025C8A
0x180025cc9  sub     ecx, 1
0x180025ccc  jz      loc_180025B62
0x180025cd2  cmp     ecx, 1
0x180025cd5  jnz     loc_180025B69
0x180025cdb  lea     r10, [rbp+2C0h+var_C8]
0x180025ce2  jmp     loc_180025B69
0x180025ce7  call    ?SetDiagnosticMode@@YAXXZ; SetDiagnosticMode(void)
0x180025cec  mov     eax, cs:?g_dmDiagnosticMode@@3HA; int g_dmDiagnosticMode
0x180025cf2  jmp     loc_180025AAE
0x180025cf7  cmp     [rbp+2C0h+var_308], 100h
0x180025cfe  jle     loc_180025AB6
0x180025d04  jmp     short loc_180025CA3
0x180025d06  or      eax, ecx
0x180025d08  mov     cs:dword_18030B358, eax
0x180025d0e  call    cs:__imp_GetCurrentProcessId
0x180025d14  movzx   ecx, al
0x180025d17  mov     cs:dword_18030B35C, ecx
0x180025d1d  jmp     loc_180025AF3
0x180025d22  lea     r10, [rbp+2C0h+var_A8]
0x180025d29  jmp     loc_180025B69
0x180025d2e  mov     rax, [rbp+2C0h+var_338]
0x180025d32  mov     [rbp+2C0h+var_E0], rax
0x180025d39  mov     rax, [rbp+2C0h+var_340]
0x180025d3d  mov     [rbp+2C0h+var_D8], rax
0x180025d44  movzx   eax, word ptr cs:dword_180306E9C
0x180025d4b  mov     [rbp+2C0h+var_E8], r15
0x180025d52  xor     r15d, r15d
0x180025d55  mov     ecx, r15d
0x180025d58  mov     [rbp+2C0h+var_F0], rdi
0x180025d5f  test    ax, ax
0x180025d62  mov     [rbp+2C0h+var_100], r12
0x180025d69  mov     [rbp+2C0h+var_F8], r13
0x180025d70  mov     dil, r15b
0x180025d73  setz    cl
0x180025d76  mov     [rbp+2C0h+var_D0], rbx
0x180025d7d  mov     [rbp+2C0h+var_330], ecx
0x180025d80  mov     [rsp+3C0h+var_360], ax
0x180025d85  lea     rdx, [rsp+3C0h+var_360]; unsigned __int16 *
0x180025d8a  lea     rcx, [rbp+2C0h+var_330]; unsigned int *
0x180025d8e  call    ?MsiSwitchLanguage@@YA_NAEAIAEAG@Z; MsiSwitchLanguage(uint &,ushort &)
0x180025d93  test    al, al
0x180025d95  jz      loc_180025E77
0x180025d9b  movzx   ecx, [rsp+3C0h+var_360]; unsigned __int16
0x180025da0  call    ?GetMsgDll@@YAPEAUHINSTANCE__@@G@Z; GetMsgDll(ushort)
0x180025da5  mov     rbx, rax
0x180025da8  test    rax, rax
0x180025dab  jz      loc_180025E68
0x180025db1  mov     edx, [rbp+2C0h+var_308]
0x180025db4  lea     rax, [rbp+2C0h+var_100]
0x180025dbb  mov     rcx, [rbp+2C0h+hMem]
0x180025dbf  add     edx, 0FFFFFFE0h
0x180025dc2  movzx   r15d, [rsp+3C0h+var_360]
0x180025dc8  add     rcx, 40h ; '@'
0x180025dcc  mov     r8d, [rsp+3C0h+dwMessageId]; dwMessageId
0x180025dd1  mov     r9d, r15d; dwLanguageId
0x180025dd4  mov     [rsp+3C0h+Arguments], rax; Arguments
0x180025dd9  mov     [rsp+3C0h+nSize], edx; nSize
0x180025ddd  mov     rdx, rbx; lpSource
0x180025de0  mov     [rsp+3C0h+lpBuffer], rcx; lpBuffer
0x180025de5  mov     ecx, 2800h; dwFlags
0x180025dea  call    cs:__imp_FormatMessageW
0x180025df0  test    eax, eax
0x180025df2  jnz     short loc_180025E68
0x180025df4  call    cs:__imp_GetLastError
0x180025dfa  cmp     eax, 7Ah ; 'z'
0x180025dfd  jnz     short loc_180025E5C
0x180025dff  mov     edx, 44Ch
0x180025e04  lea     rcx, [rbp+2C0h+hMem]
0x180025e08  call    ?SetSize@?$CAPITempBuffer@G$0BAA@@@QEAA_NH_N@Z; CAPITempBuffer<ushort,256>::SetSize(int,bool)
0x180025e0d  test    al, al
0x180025e0f  jz      short loc_180025E5C
0x180025e11  mov     ecx, [rbp+2C0h+var_308]
0x180025e14  lea     rdx, [rbp+2C0h+var_100]
0x180025e1b  mov     rax, [rbp+2C0h+hMem]
0x180025e1f  add     ecx, 0FFFFFFE0h
0x180025e22  mov     r8d, [rsp+3C0h+dwMessageId]; dwMessageId
0x180025e27  add     rax, 40h ; '@'
0x180025e2b  mov     [rsp+3C0h+Arguments], rdx; Arguments
0x180025e30  mov     r9d, r15d; dwLanguageId
0x180025e33  mov     [rsp+3C0h+nSize], ecx; nSize
0x180025e37  mov     rdx, rbx; lpSource
0x180025e3a  mov     ecx, 2800h; dwFlags
0x180025e3f  mov     [rsp+3C0h+lpBuffer], rax; lpBuffer
0x180025e44  call    cs:__imp_FormatMessageW
0x180025e4a  xor     r15d, r15d
0x180025e4d  movzx   edi, dil
0x180025e51  test    eax, eax
0x180025e53  lea     eax, [r15+1]
0x180025e57  cmovnz  edi, eax
0x180025e5a  jmp     short loc_180025E5F
0x180025e5c  xor     r15d, r15d
0x180025e5f  test    dil, dil
0x180025e62  jz      loc_180025D85
0x180025e68  mov     r15, [rsp+3C0h+var_348]
0x180025e6d  mov     rdi, [rsp+3C0h+var_350]
0x180025e72  jmp     loc_180025C2C
0x180025e77  mov     rax, [rbp+2C0h+hMem]
0x180025e7b  mov     [rax+40h], r15w
0x180025e80  jmp     short loc_180025E68
0x180025e82  mov     edx, 44Ch
0x180025e87  lea     rcx, [rbp+2C0h+hMem]
0x180025e8b  call    ?SetSize@?$CAPITempBuffer@G$0BAA@@@QEAA_NH_N@Z; CAPITempBuffer<ushort,256>::SetSize(int,bool)
0x180025e90  test    al, al
0x180025e92  jz      loc_180025C2C
0x180025e98  mov     eax, [rbp+2C0h+var_308]
0x180025e9b  mov     r9, r13
0x180025e9e  mov     rcx, [rbp+2C0h+hMem]
0x180025ea2  add     eax, 0FFFFFFE0h
0x180025ea5  mov     qword ptr [rsp+3C0h+var_380], rbx
0x180025eaa  add     rcx, 40h ; '@'; unsigned __int16 *
0x180025eae  movsxd  rdx, eax; unsigned __int64
0x180025eb1  mov     r8, r12; unsigned __int16 *
0x180025eb4  mov     rax, [rbp+2C0h+var_340]
0x180025eb8  mov     [rsp+3C0h+var_388], rax
0x180025ebd  mov     rax, [rbp+2C0h+var_338]
0x180025ec1  mov     [rsp+3C0h+Arguments], rax
0x180025ec6  mov     qword ptr [rsp+3C0h+nSize], r15
0x180025ecb  mov     [rsp+3C0h+lpBuffer], rdi
0x180025ed0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025ed5  test    eax, eax
0x180025ed7  jns     loc_180025C2C
0x180025edd  cmp     eax, 8007007Ah
0x180025ee2  jz      loc_180025C2C
0x180025ee8  jmp     loc_180025C92
0x180025eed  mov     rcx, [rbp+2C0h+hMem]; lpOutputString
0x180025ef1  call    cs:__imp_OutputDebugStringW
0x180025ef7  lea     rcx, asc_180273FD8; "\r\n"
0x180025efe  call    cs:__imp_OutputDebugStringW
0x180025f04  mov     ebx, cs:?g_dmDiagnosticMode@@3HA; int g_dmDiagnosticMode
0x180025f0a  jmp     loc_180025C81
0x180025f0f  mov     rax, [rbp+2C0h+var_328]
0x180025f13  mov     r9, r13; unsigned __int16 *
0x180025f16  mov     edx, [rsp+3C0h+dwMessageId]; int
0x180025f1a  mov     r8, r12; unsigned __int16 *
0x180025f1d  movzx   ecx, [rsp+3C0h+var_35C]; unsigned __int16
0x180025f22  mov     [rsp+3C0h+var_378], rax; void *
0x180025f27  mov     eax, [rbp+2C0h+arg_50]
0x180025f2d  mov     [rsp+3C0h+var_380], eax; unsigned int
0x180025f31  mov     rax, [rbp+2C0h+var_340]
0x180025f35  mov     [rsp+3C0h+var_388], rax; unsigned __int16 *
0x180025f3a  mov     rax, [rbp+2C0h+var_338]
0x180025f3e  mov     [rsp+3C0h+Arguments], rax; unsigned __int16 *
0x180025f43  mov     qword ptr [rsp+3C0h+nSize], r15; unsigned __int16 *
0x180025f48  mov     [rsp+3C0h+lpBuffer], rdi; unsigned __int16 *
0x180025f4d  call    ?ReportToEventLogW@@YAXGHPEBG00000KPEAX@Z; ReportToEventLogW(ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180025f52  jmp     loc_180025C92
```
