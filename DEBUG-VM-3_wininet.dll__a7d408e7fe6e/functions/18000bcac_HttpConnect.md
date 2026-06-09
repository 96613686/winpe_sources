# HttpConnect

- ea: `0x18000bcac`
- end: `0x18000c68b`
- name: `HttpConnect`
- size: `2527`
- prototype: ``
- caller_count: `5`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ccce4`
- `0x1800d9d20`
- `0x1800ea2e0`
- `0x1800feb00`
- `0x180181514`

## callees

- `0x180007e48`
- `0x180009cf0`
- `0x18000baa0`
- `0x18000bcac`
- `0x18000c694`
- `0x18000c940`
- `0x180011930`
- `0x180019d20`
- `0x18002ac10`
- `0x180050b80`
- `0x180064060`
- `0x1800641c0`
- `0x180064560`
- `0x18006625c`
- `0x1800672d0`
- `0x18007ad20`
- `0x18008a970`
- `0x1800f3618`
- `0x18010e674`
- `0x1801145e8`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e1790`
- `0x1801e5e10`
- `0x1801e76e4`
- `0x1801e78b8`
- `0x1801e802c`
- `0x1801ea104`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bfd9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bfd9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c3b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c3b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000be39`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c310`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000be39`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c310`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000be41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c318`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000be41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c318`
- `ntdll!EtwEventActivityIdControl` at `0x18000be61`
- `ntdll!EtwEventActivityIdControl` at `0x18000be61`
- `ntdll!RtlNtStatusToDosError` at `0x18000c66c`
- `ntdll!RtlNtStatusToDosError` at `0x18000c66c`

## pseudocode

```c
ULONG __fastcall HttpConnect(
        __int64 a1,
        _BYTE *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 *a9)
{
  __int64 v9; // rsi
  __int64 v10; // r13
  unsigned __int16 v11; // bx
  __int64 v12; // r12
  __int64 v14; // r15
  signed int v15; // r14d
  int v16; // edi
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int64 ThreadInfo; // r15
  struct _GUID *v20; // rax
  __int64 v21; // rcx
  struct _GUID *v22; // rax
  __int64 v23; // rcx
  signed __int32 v24; // esi
  DWORD TickCount; // ebx
  DWORD CurrentProcessId; // eax
  int v27; // eax
  bool v28; // sf
  __int64 v29; // rdi
  signed int v30; // eax
  int v31; // edx
  int v32; // ecx
  int v33; // r8d
  __int64 v34; // rbx
  void *v35; // r8
  __int64 v36; // rsi
  bool v37; // sf
  __int64 v38; // rbx
  int IsValid; // eax
  int v40; // r8d
  int v41; // r14d
  __int64 v42; // rdi
  INTERNET_CONNECT_HANDLE_OBJECT *v43; // rax
  INTERNET_CONNECT_HANDLE_OBJECT *v44; // rbx
  INTERNET_CONNECT_HANDLE_OBJECT *v45; // rax
  HANDLE_OBJECT *v46; // rbx
  int v47; // edi
  int v48; // eax
  __int64 v49; // rbx
  __int64 v50; // rdi
  struct _GUID *v51; // rax
  __int64 v52; // rdx
  struct _GUID *v53; // rbx
  __int64 v54; // rcx
  struct _GUID *v55; // rax
  __int64 v56; // r11
  __int64 v57; // r10
  __int64 v58; // r8
  ULONG result; // eax
  signed __int32 v60; // esi
  DWORD v61; // ebx
  DWORD v62; // eax
  unsigned int v63; // eax
  unsigned int v64; // eax
  int v65; // [rsp+20h] [rbp-E0h]
  __int64 v66; // [rsp+68h] [rbp-98h] BYREF
  HANDLE_OBJECT *v67; // [rsp+70h] [rbp-90h] BYREF
  __int64 v68; // [rsp+78h] [rbp-88h] BYREF
  _BYTE *v69; // [rsp+80h] [rbp-80h] BYREF
  int v70; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v71; // [rsp+90h] [rbp-70h] BYREF
  __int64 v72; // [rsp+98h] [rbp-68h] BYREF
  __int64 v73; // [rsp+A0h] [rbp-60h] BYREF
  struct _GUID v74; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v75; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID v76; // [rsp+D0h] [rbp-30h] BYREF
  int v77; // [rsp+E0h] [rbp-20h]
  char v78[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 *v79; // [rsp+100h] [rbp+0h]
  __int64 v80; // [rsp+108h] [rbp+8h]
  __int64 *v81; // [rsp+110h] [rbp+10h]
  __int64 v82; // [rsp+118h] [rbp+18h]
  int *v83; // [rsp+120h] [rbp+20h]
  __int64 v84; // [rsp+128h] [rbp+28h]
  __int64 v85; // [rsp+130h] [rbp+30h]
  int v86; // [rsp+138h] [rbp+38h]
  int v87; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v88; // [rsp+140h] [rbp+40h]
  __int64 v89; // [rsp+148h] [rbp+48h]
  unsigned __int16 *v90; // [rsp+150h] [rbp+50h]
  __int64 v91; // [rsp+158h] [rbp+58h]
  const CHAR *v92; // [rsp+160h] [rbp+60h]
  int v93; // [rsp+168h] [rbp+68h]
  int v94; // [rsp+16Ch] [rbp+6Ch]
  __int64 *v95; // [rsp+170h] [rbp+70h]
  __int64 v96; // [rsp+178h] [rbp+78h]
  _UNKNOWN *retaddr; // [rsp+1D8h] [rbp+D8h]

  v9 = a1;
  v10 = a5;
  v11 = a3;
  v73 = a1;
  v70 = (unsigned __int16)a3;
  v69 = a2;
  v12 = a4;
  v77 = 0;
  HIDWORD(v66) = 0;
  v14 = 0;
  v68 = 0;
  v67 = 0;
  v76 = 0;
  v72 = 0;
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_qsdssDPl(1025, 50, a7, a1, (__int64)a2, a3, a4, a5, a6, a7, a8);
  if ( !GlobalDataInitialized )
  {
    v15 = -2147012724;
    HIDWORD(v66) = 2763;
    goto LABEL_5;
  }
  ThreadInfo = InternetGetThreadInfo(0, a2, a3);
  if ( !ThreadInfo )
  {
    v15 = -2147012892;
    HIDWORD(v66) = 2766;
    goto LABEL_97;
  }
  if ( !a2 || !*a2 )
  {
    v15 = -2147024809;
    HIDWORD(v66) = 2768;
LABEL_97:
    v14 = 0;
    goto LABEL_5;
  }
  a6 &= ~0x20000000u;
  *a9 = 0;
  v20 = &v76;
  v21 = 16;
  do
  {
    LOBYTE(v20->Data1) = 0;
    v20 = (struct _GUID *)((char *)v20 + 1);
    --v21;
  }
  while ( v21 );
  v77 = 0;
  v22 = &v76;
  v75 = 0;
  v23 = 16;
  v74 = 0;
  do
  {
    LOBYTE(v22->Data1) = 0;
    v22 = (struct _GUID *)((char *)v22 + 1);
    --v23;
  }
  while ( v23 );
  WxEtwGetActivityId(&v74);
  v24 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
  TickCount = GetTickCount();
  CurrentProcessId = GetCurrentProcessId();
  v75.Data1 = (unsigned int)retaddr;
  *(_DWORD *)&v75.Data4[4] = CurrentProcessId;
  *(_DWORD *)&v75.Data2 = v24;
  *(_DWORD *)v75.Data4 = TickCount;
  HIDWORD(v66) = 0;
  v27 = EtwEventActivityIdControl(2, &v75);
  v28 = v27 < 0;
  if ( v27 > 0 )
    v28 = 1;
  if ( v28 )
    HIDWORD(v66) = 144;
  WxEtwTransferActivityId(&v75, &v74);
  v77 = 1;
  v76 = v74;
  if ( (unsigned int)InternetProxySettingsChanged() )
    ChangeGlobalSettings(1);
  v29 = v73;
  v30 = MapHandleToAddress(v73, &v68, 0);
  v34 = v68;
  v15 = v30;
  if ( v68 )
  {
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_qqqqq(
        1025,
        43,
        (unsigned int)&WPP_269ea9d0988239ed4fc21e863914335a_Traceguids,
        ThreadInfo,
        *(_QWORD *)(ThreadInfo + 48),
        v29,
        *(_QWORD *)(ThreadInfo + 56),
        v68);
    *(_QWORD *)(ThreadInfo + 48) = v29;
    *(_QWORD *)(ThreadInfo + 56) = v34;
    if ( (BYTE1(xmmword_180266B60) & 0x20) != 0 )
    {
      *(_QWORD *)v74.Data4 = 1;
      *(_QWORD *)&v74.Data1 = word_180222338;
      WPP_SF_qd_COUNTEDSTRING_dD(v32, v31, v33, ThreadInfo, v65, (__int64)&v74, 0, 0);
    }
    v35 = *(void **)(ThreadInfo + 24);
    if ( v35 )
      HeapFree(g_hWxProcessHeap, 0, v35);
    *(_QWORD *)(ThreadInfo + 24) = 0;
    *(_DWORD *)(ThreadInfo + 32) = 0;
    *(_DWORD *)(ThreadInfo + 20) = 0;
    if ( (BYTE1(xmmword_180266B60) & 0x20) != 0 )
      WPP_SF_d(1037, 41, &WPP_269ea9d0988239ed4fc21e863914335a_Traceguids, 0);
    v36 = a7;
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_qPP(1025, 42, &WPP_269ea9d0988239ed4fc21e863914335a_Traceguids, ThreadInfo);
    *(_QWORD *)(ThreadInfo + 40) = a7;
  }
  else
  {
    v36 = a7;
  }
  v37 = v15 < 0;
  if ( v15 > 0 )
  {
    v15 = (unsigned __int16)v15 | 0x80070000;
    v37 = v15 < 0;
  }
  if ( v37 )
  {
    HIDWORD(v66) = 2805;
LABEL_89:
    v11 = v70;
    v9 = v73;
    v14 = v72;
    goto LABEL_5;
  }
  v38 = v68;
  IsValid = HANDLE_OBJECT::IsValid(v68, 1952804425);
  v15 = IsValid;
  if ( IsValid )
  {
    if ( IsValid > 0 )
      v15 = (unsigned __int16)IsValid | 0x80070000;
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v15 = 0;
  }
  if ( v15 < 0 )
  {
    HIDWORD(v66) = 2810;
    goto LABEL_89;
  }
  v41 = v70;
  if ( !(_WORD)v70 )
  {
    v41 = 80;
    if ( (a6 & 0x800000) != 0 )
      v41 = 443;
  }
  v70 = v41;
  if ( v12 )
    v12 &= -(__int64)(*(_BYTE *)v12 != 0);
  if ( a5 )
    v10 = -(__int64)(*(_BYTE *)a5 != 0) & a5;
  v42 = v68;
  HIDWORD(v66) = 0;
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_qsdsslDPq((unsigned int)&v67, a6, v40, v68, (__int64)v69, v41, v12, v10, 3, a6, v36, (__int64)&v67);
  v67 = 0;
  v43 = (INTERNET_CONNECT_HANDLE_OBJECT *)HeapAlloc(g_hWxProcessHeap, 0, 0x3E8u);
  v44 = v43;
  if ( v43
    && (memset_0(v43, 0, 0x3E8u),
        v45 = INTERNET_CONNECT_HANDLE_OBJECT::INTERNET_CONNECT_HANDLE_OBJECT(v44),
        (v46 = v45) != 0) )
  {
    v47 = (*(__int64 (__fastcall **)(INTERNET_CONNECT_HANDLE_OBJECT *, __int64, _BYTE *, _QWORD, __int64, __int64, int, int, __int64))(*(_QWORD *)v45 + 200LL))(
            v45,
            v42,
            v69,
            (unsigned __int16)v41,
            v12,
            v10,
            3,
            a6,
            v36);
    if ( v47 < 0 )
    {
      HIDWORD(v66) = 848;
      HANDLE_OBJECT::Invalidate(v46);
      HANDLE_OBJECT::Dereference(v46);
    }
    else
    {
      v67 = v46;
    }
  }
  else
  {
    v47 = -2147024882;
    HIDWORD(v66) = 837;
  }
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
  {
    v63 = WX_WIN32_FROM_HR((unsigned int)v47);
    WPP_SF_d(1032, 21, &WPP_ebf5ebc2fb2b37980c6e0149dcb01477_Traceguids, v63);
  }
  v48 = WX_WIN32_FROM_HR((unsigned int)v47);
  v15 = v48;
  if ( v48 > 0 )
    v15 = (unsigned __int16)v48 | 0x80070000;
  if ( v15 >= 0 )
  {
    v49 = (__int64)v67;
    v50 = *((_QWORD *)v67 + 16);
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_qqqqq(
        1025,
        43,
        (unsigned int)&WPP_269ea9d0988239ed4fc21e863914335a_Traceguids,
        ThreadInfo,
        *(_QWORD *)(ThreadInfo + 48),
        v50,
        *(_QWORD *)(ThreadInfo + 56),
        (__int64)v67);
    *(_QWORD *)(ThreadInfo + 48) = v50;
    *(_QWORD *)(ThreadInfo + 56) = v49;
    EtwEndActivityId(&v76);
    v51 = &v76;
    v52 = 16;
    v53 = (struct _GUID *)((char *)v67 + 164);
    v54 = 16;
    do
    {
      LOBYTE(v51->Data1) = 0;
      v51 = (struct _GUID *)((char *)v51 + 1);
      --v54;
    }
    while ( v54 );
    v77 = 0;
    v55 = &v76;
    v75 = 0;
    v74 = 0;
    do
    {
      LOBYTE(v55->Data1) = 0;
      v55 = (struct _GUID *)((char *)v55 + 1);
      --v52;
    }
    while ( v52 );
    WxEtwGetActivityId(&v74);
    if ( !v53 )
    {
      v60 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
      v61 = GetTickCount();
      v62 = GetCurrentProcessId();
      *(_DWORD *)v75.Data4 = v61;
      v53 = &v75;
      *(_DWORD *)&v75.Data4[4] = v62;
      v75.Data1 = (unsigned int)retaddr;
      *(_DWORD *)&v75.Data2 = v60;
    }
    WxEtwSetActivityId(v53);
    WxEtwTransferActivityId(v53, &v74);
    v16 = a6;
    v9 = v73;
    v77 = 1;
    v76 = v74;
    if ( (a6 & 0x1000000) == 0 )
      FlushExistingConnectObjects(v73);
    v11 = v70;
    v14 = v72;
    goto LABEL_6;
  }
  v11 = v70;
  v9 = v73;
  v14 = v72;
  HIDWORD(v66) = 2834;
LABEL_5:
  v16 = a6;
LABEL_6:
  if ( v67 )
  {
    if ( v15 < 0 )
      InternetCloseHandle(*((_QWORD *)v67 + 16));
    else
      v14 = *((_QWORD *)v67 + 16);
    if ( v67 )
    {
      if ( a8 && v15 >= 0 )
        goto LABEL_69;
      if ( !(unsigned int)DereferenceObject(v67) )
      {
        if ( v15 < 0 )
          goto LABEL_8;
        v15 = -2147012879;
      }
    }
  }
  if ( v15 >= 0 )
  {
LABEL_69:
    if ( (Microsoft_Windows_WinINetEnableBits & 1) != 0 )
    {
      LODWORD(v72) = v16;
      v71 = 4;
      LODWORD(v73) = v11;
      LOWORD(v70) = inetstrlenUShortA(v69);
      v79 = (__int64 *)&v69;
      v86 = (unsigned __int16)v70;
      v81 = &v66;
      v66 = v9;
      v83 = &v70;
      v88 = &v73;
      v90 = &v71;
      v92 = "HTTP";
      v93 = v71;
      v95 = &v72;
      v69 = (_BYTE *)v14;
      v80 = 8;
      v82 = 8;
      v84 = 2;
      v85 = v56;
      v87 = 0;
      v89 = v57;
      v91 = 2;
      v94 = 0;
      v96 = v57;
      McGenEventWrite_EventWriteTransfer(&WININET_Context, "g", v58, (unsigned int)(v57 + 5), v78);
    }
    *a9 = v14;
    goto LABEL_72;
  }
LABEL_8:
  if ( (Microsoft_Windows_WinINetEnableBits & 4) != 0 )
  {
    v17 = WX_WIN32_FROM_HR((unsigned int)v15);
    McTemplateU0pq_EventWriteTransfer(v18, &WININET_HANDLE_CREATE_FAILED, v9, v17);
  }
LABEL_72:
  if ( v68 )
    DereferenceObject(v68);
  if ( (xmmword_180266B60 & 2) != 0 )
  {
    v64 = WX_WIN32_FROM_HR((unsigned int)v15);
    WPP_SF_d(1025, 51, &WPP_15fca7e08d66386e86c8ae4515ac1814_Traceguids, v64);
  }
  EtwEndActivityId(&v76);
  if ( (v15 & 0x1FFF0000) == 0xC0000 )
    return (unsigned __int16)v15;
  if ( v15 >= 0 )
    return 0;
  if ( (v15 & 0x1FFF0000) == 0x70000 )
  {
    result = (unsigned __int16)v15;
    if ( !(_WORD)v15 )
      return 317;
  }
  else
  {
    if ( (v15 & 0x10000000) == 0 )
      return v15;
    result = RtlNtStatusToDosError(v15 & 0xEFFFFFFF);
    if ( !result || result == 317 )
      return v15;
  }
  return result;
}

```

## disassembly

```asm
0x18000bcac  push    rbp
0x18000bcae  push    rbx
0x18000bcaf  push    rsi
0x18000bcb0  push    rdi
0x18000bcb1  push    r12
0x18000bcb3  push    r13
0x18000bcb5  push    r14
0x18000bcb7  push    r15
0x18000bcb9  lea     rbp, [rsp-98h]
0x18000bcc1  sub     rsp, 198h
0x18000bcc8  mov     rax, cs:__security_cookie
0x18000bccf  xor     rax, rsp
0x18000bcd2  mov     [rbp+0D0h+var_50], rax
0x18000bcd9  mov     rax, [rbp+0D0h+arg_40]
0x18000bce0  mov     rsi, rcx
0x18000bce3  mov     r13, [rbp+0D0h+arg_20]
0x18000bcea  movzx   ebx, r8w
0x18000bcee  mov     [rbp+0D0h+var_130], rcx
0x18000bcf2  xorps   xmm0, xmm0
0x18000bcf5  xor     ecx, ecx
0x18000bcf7  mov     [rsp+1D0h+var_170], rax
0x18000bcfc  xor     eax, eax
0x18000bcfe  mov     [rbp+0D0h+var_148], ebx
0x18000bd01  mov     [rbp+0D0h+var_150], rdx
0x18000bd05  mov     r12, r9
0x18000bd08  mov     [rbp+0D0h+var_F0], eax
0x18000bd0b  mov     r14, rdx
0x18000bd0e  mov     dword ptr [rsp+1D0h+var_168+4], ecx
0x18000bd12  mov     r15d, ecx
0x18000bd15  mov     [rsp+1D0h+var_158], rcx
0x18000bd1a  mov     [rsp+1D0h+var_160], rcx
0x18000bd1f  movups  [rbp+0D0h+var_100], xmm0
0x18000bd23  mov     [rbp+0D0h+var_138], rcx
0x18000bd27  test    byte ptr cs:xmmword_180266B60, 2
0x18000bd2e  mov     edi, [rbp+0D0h+arg_28]
0x18000bd34  jnz     loc_18000C348
0x18000bd3a  cmp     cs:GlobalDataInitialized, ecx
0x18000bd40  jnz     short loc_18000BDA7
0x18000bd42  mov     r14d, 80072F8Ch
0x18000bd48  mov     dword ptr [rsp+1D0h+var_168+4], 0ACBh
0x18000bd50  xor     r12d, r12d
0x18000bd53  lea     r13d, [r12+1]
0x18000bd58  mov     edi, [rbp+0D0h+arg_28]
0x18000bd5e  mov     rax, [rsp+1D0h+var_160]
0x18000bd63  test    rax, rax
0x18000bd66  jnz     loc_18000C2AD
0x18000bd6c  test    r14d, r14d
0x18000bd6f  jns     loc_18000C161
0x18000bd75  mov     r10d, 4
0x18000bd7b  test    byte ptr cs:Microsoft_Windows_WinINetEnableBits, r10b
0x18000bd82  jz      loc_18000C243
0x18000bd88  mov     ecx, r14d
0x18000bd8b  call    WX_WIN32_FROM_HR
0x18000bd90  mov     r9d, eax
0x18000bd93  lea     rdx, WININET_HANDLE_CREATE_FAILED
0x18000bd9a  mov     r8, rsi
0x18000bd9d  call    McTemplateU0pq_EventWriteTransfer
0x18000bda2  jmp     loc_18000C243
0x18000bda7  call    InternetGetThreadInfo
0x18000bdac  mov     r15, rax
0x18000bdaf  xor     eax, eax
0x18000bdb1  test    r15, r15
0x18000bdb4  jz      loc_18000C4B1
0x18000bdba  test    r14, r14
0x18000bdbd  jz      loc_18000C3F4
0x18000bdc3  cmp     [r14], al
0x18000bdc6  jz      loc_18000C3F4
0x18000bdcc  mov     rax, [rsp+1D0h+var_170]
0x18000bdd1  btr     edi, 1Dh
0x18000bdd5  xor     r14d, r14d
0x18000bdd8  mov     [rbp+0D0h+arg_28], edi
0x18000bdde  mov     [rax], r14
0x18000bde1  lea     rax, [rbp+0D0h+var_100]
0x18000bde5  lea     edx, [r14+10h]
0x18000bde9  mov     ecx, edx
0x18000bdeb  lea     ebx, [rdx-0Fh]
0x18000bdee  mov     [rax], r14b
0x18000bdf1  add     rax, rbx
0x18000bdf4  sub     rcx, rbx
0x18000bdf7  jnz     short loc_18000BDEE
0x18000bdf9  xorps   xmm0, xmm0
0x18000bdfc  mov     [rbp+0D0h+var_F0], r14d
0x18000be00  xorps   xmm1, xmm1
0x18000be03  lea     rax, [rbp+0D0h+var_100]
0x18000be07  movups  xmmword ptr [rbp+0D0h+var_110.Data1], xmm0
0x18000be0b  mov     rcx, rdx
0x18000be0e  movups  xmmword ptr [rbp+0D0h+var_120.Data1], xmm1
0x18000be12  mov     [rax], r14b
0x18000be15  add     rax, rbx
0x18000be18  sub     rcx, rbx
0x18000be1b  jnz     short loc_18000BE12
0x18000be1d  lea     rcx, [rbp+0D0h+var_120]; struct _GUID *
0x18000be21  call    ?WxEtwGetActivityId@@YAXPEAU_GUID@@@Z; WxEtwGetActivityId(_GUID *)
0x18000be26  mov     rdi, [rbp+0D8h]
0x18000be2d  mov     esi, ebx
0x18000be2f  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x18000be37  add     esi, ebx
0x18000be39  call    cs:__imp_GetTickCount
0x18000be3f  mov     ebx, eax
0x18000be41  call    cs:__imp_GetCurrentProcessId
0x18000be47  mov     [rbp+0D0h+var_110.Data1], edi
0x18000be4a  lea     rdx, [rbp+0D0h+var_110]
0x18000be4e  mov     dword ptr [rbp+0D0h+var_110.Data4+4], eax
0x18000be51  mov     ecx, 2
0x18000be56  mov     dword ptr [rbp+0D0h+var_110.Data2], esi
0x18000be59  mov     dword ptr [rbp+0D0h+var_110.Data4], ebx
0x18000be5c  mov     dword ptr [rsp+1D0h+var_168+4], r14d
0x18000be61  call    cs:__imp_EtwEventActivityIdControl
0x18000be67  test    eax, eax
0x18000be69  jle     short loc_18000BE75
0x18000be6b  movzx   eax, ax
0x18000be6e  or      eax, 80070000h
0x18000be73  test    eax, eax
0x18000be75  js      loc_18000C4C4
0x18000be7b  lea     rdx, [rbp+0D0h+var_120]; struct _GUID *
0x18000be7f  lea     rcx, [rbp+0D0h+var_110]; struct _GUID *
0x18000be83  call    ?WxEtwTransferActivityId@@YAXPEBU_GUID@@0@Z; WxEtwTransferActivityId(_GUID const *,_GUID const *)
0x18000be88  movups  xmm0, xmmword ptr [rbp+0D0h+var_120.Data1]
0x18000be8c  mov     esi, 1
0x18000be91  mov     [rbp+0D0h+var_F0], esi
0x18000be94  movdqu  [rbp+0D0h+var_100], xmm0
0x18000be99  call    InternetProxySettingsChanged
0x18000be9e  test    eax, eax
0x18000bea0  jz      short loc_18000BEA9
0x18000bea2  mov     ecx, esi
0x18000bea4  call    ChangeGlobalSettings
0x18000bea9  mov     rdi, [rbp+0D0h+var_130]
0x18000bead  lea     rdx, [rsp+1D0h+var_158]
0x18000beb2  mov     rcx, rdi
0x18000beb5  xor     r8d, r8d
0x18000beb8  call    MapHandleToAddress
0x18000bebd  mov     rbx, [rsp+1D0h+var_158]
0x18000bec2  mov     r14d, eax
0x18000bec5  test    rbx, rbx
0x18000bec8  jz      loc_18000C3DD
0x18000bece  test    byte ptr cs:xmmword_180266B60, 2
0x18000bed5  jnz     loc_18000C4D1
0x18000bedb  mov     [r15+30h], rdi
0x18000bedf  mov     [r15+38h], rbx
0x18000bee3  xor     edi, edi
0x18000bee5  test    byte ptr cs:xmmword_180266B60+1, 20h
0x18000beec  jnz     loc_18000C45E
0x18000bef2  mov     r8, [r15+18h]; lpMem
0x18000bef6  test    r8, r8
0x18000bef9  jnz     loc_18000C3AB
0x18000beff  mov     [r15+18h], rdi
0x18000bf03  mov     [r15+20h], edi
0x18000bf07  mov     [r15+14h], edi
0x18000bf0b  test    byte ptr cs:xmmword_180266B60+1, 20h
0x18000bf12  jnz     loc_18000C440
0x18000bf18  test    byte ptr cs:xmmword_180266B60, 2
0x18000bf1f  mov     rsi, [rbp+0D0h+arg_30]
0x18000bf26  jnz     loc_18000C50B
0x18000bf2c  mov     [r15+28h], rsi
0x18000bf30  test    r14d, r14d
0x18000bf33  jle     short loc_18000BF43
0x18000bf35  movzx   r14d, r14w
0x18000bf39  or      r14d, 80070000h
0x18000bf40  test    r14d, r14d
0x18000bf43  js      loc_18000C393
0x18000bf49  mov     rbx, [rsp+1D0h+var_158]
0x18000bf4e  mov     edx, 74656E49h
0x18000bf53  mov     rcx, rbx
0x18000bf56  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18000bf5b  mov     r14d, eax
0x18000bf5e  test    eax, eax
0x18000bf60  jnz     loc_18000C49B
0x18000bf66  mov     rax, [rbx]
0x18000bf69  mov     rcx, rbx
0x18000bf6c  mov     rax, [rax+10h]
0x18000bf70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf75  mov     r14d, edi
0x18000bf78  test    r14d, r14d
0x18000bf7b  js      loc_18000C433
0x18000bf81  mov     r14d, [rbp+0D0h+var_148]
0x18000bf85  mov     edx, [rbp+0D0h+arg_28]
0x18000bf8b  test    r14w, r14w
0x18000bf8f  jz      loc_18000C537
0x18000bf95  mov     [rbp+0D0h+var_148], r14d
0x18000bf99  test    r12, r12
0x18000bf9c  jnz     loc_18000C40A
0x18000bfa2  test    r13, r13
0x18000bfa5  jnz     loc_18000C552
0x18000bfab  mov     rdi, [rsp+1D0h+var_158]
0x18000bfb0  xor     ebx, ebx
0x18000bfb2  mov     dword ptr [rsp+1D0h+var_168+4], ebx
0x18000bfb6  lea     eax, [rbx+1]
0x18000bfb9  test    byte ptr cs:xmmword_180266B60+1, al
0x18000bfbf  jnz     loc_18000C563
0x18000bfc5  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18000bfcc  xor     edx, edx; dwFlags
0x18000bfce  mov     r8d, 3E8h; dwBytes
0x18000bfd4  mov     [rsp+1D0h+var_160], rbx
0x18000bfd9  call    cs:__imp_HeapAlloc
0x18000bfdf  mov     rbx, rax
0x18000bfe2  test    rax, rax
0x18000bfe5  jz      loc_18000C333
0x18000bfeb  xor     edx, edx; Val
0x18000bfed  mov     r8d, 3E8h; Size
0x18000bff3  mov     rcx, rax; void *
0x18000bff6  call    memset_0
0x18000bffb  mov     rcx, rbx; this
0x18000bffe  call    ??0INTERNET_CONNECT_HANDLE_OBJECT@@IEAA@XZ; INTERNET_CONNECT_HANDLE_OBJECT::INTERNET_CONNECT_HANDLE_OBJECT(void)
0x18000c003  mov     rbx, rax
0x18000c006  test    rax, rax
0x18000c009  jz      loc_18000C333
0x18000c00f  mov     rcx, [rax]
0x18000c012  movzx   r9d, r14w
0x18000c016  mov     r8, [rbp+0D0h+var_150]
0x18000c01a  mov     rdx, rdi
0x18000c01d  mov     [rsp+1D0h+var_190], rsi
0x18000c022  mov     rax, [rcx+0C8h]
0x18000c029  mov     ecx, [rbp+0D0h+arg_28]
0x18000c02f  mov     dword ptr [rsp+1D0h+var_198], ecx
0x18000c033  mov     rcx, rbx
0x18000c036  mov     dword ptr [rsp+1D0h+var_1A0], 3
0x18000c03e  mov     [rsp+1D0h+var_1A8], r13
0x18000c043  mov     [rsp+1D0h+var_1B0], r12
0x18000c048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c04d  xor     r12d, r12d
0x18000c050  mov     edi, eax
0x18000c052  test    eax, eax
0x18000c054  js      loc_18000C5A6
0x18000c05a  mov     [rsp+1D0h+var_160], rbx
0x18000c05f  mov     r13d, 1
0x18000c065  test    byte ptr cs:xmmword_180266B60+1, r13b
0x18000c06c  jnz     loc_18000C5C3
0x18000c072  mov     ecx, edi
0x18000c074  call    WX_WIN32_FROM_HR
0x18000c079  mov     r14d, eax
0x18000c07c  test    eax, eax
0x18000c07e  jle     short loc_18000C08B
0x18000c080  movzx   r14d, ax
0x18000c084  or      r14d, 80070000h
0x18000c08b  test    r14d, r14d
0x18000c08e  js      loc_18000C41B
0x18000c094  mov     rbx, [rsp+1D0h+var_160]
0x18000c099  mov     rdi, [rbx+80h]
0x18000c0a0  test    byte ptr cs:xmmword_180266B60, 2
0x18000c0a7  jnz     loc_18000C5E8
0x18000c0ad  lea     rcx, [rbp+0D0h+var_100]
0x18000c0b1  mov     [r15+30h], rdi
0x18000c0b5  mov     [r15+38h], rbx
0x18000c0b9  call    EtwEndActivityId
0x18000c0be  mov     rbx, [rsp+1D0h+var_160]
0x18000c0c3  lea     rax, [rbp+0D0h+var_100]
0x18000c0c7  mov     edx, 10h
0x18000c0cc  add     rbx, 0A4h
0x18000c0d3  mov     ecx, edx
0x18000c0d5  mov     [rax], r12b
0x18000c0d8  add     rax, r13
0x18000c0db  sub     rcx, r13
0x18000c0de  jnz     short loc_18000C0D5
0x18000c0e0  xorps   xmm0, xmm0
0x18000c0e3  mov     [rbp+0D0h+var_F0], r12d
0x18000c0e7  xorps   xmm1, xmm1
0x18000c0ea  lea     rax, [rbp+0D0h+var_100]
0x18000c0ee  movups  xmmword ptr [rbp+0D0h+var_110.Data1], xmm0
0x18000c0f2  movups  xmmword ptr [rbp+0D0h+var_120.Data1], xmm1
0x18000c0f6  mov     [rax], r12b
0x18000c0f9  add     rax, r13
0x18000c0fc  sub     rdx, r13
0x18000c0ff  jnz     short loc_18000C0F6
0x18000c101  lea     rcx, [rbp+0D0h+var_120]; struct _GUID *
0x18000c105  call    ?WxEtwGetActivityId@@YAXPEAU_GUID@@@Z; WxEtwGetActivityId(_GUID *)
0x18000c10a  test    rbx, rbx
0x18000c10d  jz      loc_18000C2FB
0x18000c113  mov     rcx, rbx; struct _GUID *
0x18000c116  call    ?WxEtwSetActivityId@@YAXPEBU_GUID@@@Z; WxEtwSetActivityId(_GUID const *)
0x18000c11b  lea     rdx, [rbp+0D0h+var_120]; struct _GUID *
0x18000c11f  mov     rcx, rbx; struct _GUID *
0x18000c122  call    ?WxEtwTransferActivityId@@YAXPEBU_GUID@@0@Z; WxEtwTransferActivityId(_GUID const *,_GUID const *)
0x18000c127  movups  xmm0, xmmword ptr [rbp+0D0h+var_120.Data1]
0x18000c12b  mov     edi, [rbp+0D0h+arg_28]
0x18000c131  mov     rsi, [rbp+0D0h+var_130]
0x18000c135  mov     [rbp+0D0h+var_F0], r13d
0x18000c139  movdqu  [rbp+0D0h+var_100], xmm0
0x18000c13e  bt      edi, 18h
0x18000c142  jb      short loc_18000C14C
0x18000c144  mov     rcx, rsi
0x18000c147  call    FlushExistingConnectObjects
0x18000c14c  mov     ebx, [rbp+0D0h+var_148]
0x18000c14f  mov     r15, [rbp+0D0h+var_138]
0x18000c153  jmp     loc_18000BD5E
0x18000c158  test    r14d, r14d
0x18000c15b  js      loc_18000C2D5
0x18000c161  test    byte ptr cs:Microsoft_Windows_WinINetEnableBits, r13b
0x18000c168  jz      loc_18000C23B
0x18000c16e  mov     r11, [rbp+0D0h+var_150]
0x18000c172  mov     r10d, 4
0x18000c178  movzx   eax, bx
0x18000c17b  mov     rcx, r11
0x18000c17e  mov     dword ptr [rbp+0D0h+var_138], edi
0x18000c181  mov     [rbp+0D0h+var_140], r10w
0x18000c186  mov     dword ptr [rbp+0D0h+var_130], eax
0x18000c189  call    inetstrlenUShortA
0x18000c18e  movzx   r9d, ax
0x18000c192  lea     rdx, WININET_CONNECT_HANDLE_CREATED; "g"
0x18000c199  lea     rax, [rbp+0D0h+var_150]
0x18000c19d  mov     word ptr [rbp+0D0h+var_148], r9w
  ... truncated ...
```
