# EncryptDecryptHelper::DoEncryption(_SecHandle *,Packet *,Packet * *,char const *,bool,char const *,ulong,AuthenticationProcessed,bool *)

- ea: `0x18004e188`
- end: `0x18004e7dc`
- name: `?DoEncryption@EncryptDecryptHelper@@QEAAKPEAU_SecHandle@@PEAVPacket@@PEAPEAV3@PEBD_N3KW4AuthenticationProcessed@@PEA_N@Z`
- size: `1620`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD, _QWORD)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004a9b0`
- `0x18008bbe0`

## callees

- `0x180005d10`
- `0x180033c90`
- `0x18004a900`
- `0x18004d280`
- `0x18004e0d0`
- `0x18004e188`
- `0x18005c09c`
- `0x18005d800`
- `0x180071cdc`
- `0x1800e43f4`
- `0x1801123a8`
- `0x18011a6d4`
- `0x1801ba1b0`

## import_xrefs

- `msvcrt!_scprintf` at `0x18004e257`
- `msvcrt!_scprintf` at `0x18004e257`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e2d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e33c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e471`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e2d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e33c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e471`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18004e4cd`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18004e4ef`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18004e4cd`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18004e4ef`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004e52b`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004e52b`
- `SspiCli!QueryContextAttributesW` at `0x18004e23a`
- `SspiCli!QueryContextAttributesW` at `0x18004e23a`

## string_xrefs

- `0x18004e6e4`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18004e710`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18004e7ae`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18004e24d`: `OriginalContent: type=application/soap+xml;charset=%s;Length=%lu\n`

## pseudocode

```c
__int64 __fastcall EncryptDecryptHelper::DoEncryption(
        _BYTE *a1,
        struct _SecHandle *a2,
        __int64 a3,
        Packet **a4,
        char *a5,
        bool a6,
        EncryptDecryptHelper *a7,
        unsigned int a8,
        int a9,
        _BYTE *a10)
{
  unsigned int v12; // esi
  unsigned int v13; // ebx
  SECURITY_STATUS v14; // edi
  unsigned int v15; // ecx
  unsigned int v16; // edx
  unsigned int v17; // ebx
  const unsigned __int16 *v18; // r8
  __int64 v19; // rdx
  CHeap *v21; // rcx
  void *Handle; // rax
  CHeap *v23; // rcx
  __int64 v24; // rdi
  const void *v25; // r15
  CHeap *v26; // rcx
  void *v27; // rax
  LPVOID v28; // r14
  void *v29; // rcx
  unsigned __int8 *v30; // rsi
  unsigned int v31; // r14d
  const CHAR *v32; // r15
  unsigned int v33; // edi
  _BYTE *v34; // r13
  _BYTE *v35; // rcx
  unsigned int v36; // edi
  unsigned int v37; // esi
  Packet *v38; // rdi
  const void *v39; // r15
  CHeap *v40; // rcx
  CHeap *v41; // rcx
  void *v42; // rax
  void *v43; // rax
  void *v44; // rax
  void *Heap; // rax
  __int64 v46; // r14
  PSLIST_ENTRY v47; // rax
  unsigned int v48; // eax
  char v49; // r13
  unsigned int TotalEncryptedSizeInternalSsl; // eax
  bool v51; // zf
  unsigned int v52; // [rsp+60h] [rbp-51h] BYREF
  SIZE_T dwBytes; // [rsp+64h] [rbp-4Dh] BYREF
  unsigned int v54; // [rsp+6Ch] [rbp-45h]
  _BYTE *v55; // [rsp+70h] [rbp-41h]
  _BYTE *v56; // [rsp+78h] [rbp-39h]
  EncryptDecryptHelper *v57; // [rsp+80h] [rbp-31h]
  char *v58; // [rsp+88h] [rbp-29h]
  struct _SecHandle *v59; // [rsp+90h] [rbp-21h]
  __int128 pBuffer; // [rsp+98h] [rbp-19h] BYREF

  v55 = a1;
  v57 = a7;
  v59 = a2;
  v58 = a5;
  v56 = a10;
  if ( !a2 )
  {
    v18 = L"4869";
    v19 = 4869;
    goto LABEL_14;
  }
  if ( !a5 )
  {
    v18 = L"4870";
    v19 = 4870;
    goto LABEL_14;
  }
  if ( !a7 )
  {
    v18 = L"4871";
    v19 = 4871;
LABEL_14:
    v17 = 1359;
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", v19, v18, 0x54Fu, 0);
    return v17;
  }
  if ( !a10 )
  {
    v18 = L"4872";
    v19 = 4872;
    goto LABEL_14;
  }
  v12 = 0;
  v52 = 0;
  if ( *(_QWORD *)(a3 + 40) )
    v13 = *(_DWORD *)(a3 + 48);
  else
    v13 = 0;
  if ( a9 >= 3 )
  {
    v18 = L"4844";
    v19 = 4844;
    goto LABEL_14;
  }
  if ( a9 == 2 )
  {
    TotalEncryptedSizeInternalSsl = EncryptDecryptHelper::GetTotalEncryptedSizeInternalSsl(
                                      a7,
                                      a2,
                                      v13,
                                      a5,
                                      a6,
                                      a8,
                                      0x12u,
                                      &v52);
    v12 = v52;
    v17 = TotalEncryptedSizeInternalSsl;
  }
  else
  {
    pBuffer = 0;
    v14 = QueryContextAttributesW(a2, 0, &pBuffer);
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          124,
          &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids,
          (unsigned int)v14);
      v17 = SecurityStatusToWin32(v14);
    }
    else
    {
      v12 = -1;
      v15 = _scprintf("OriginalContent: type=application/soap+xml;charset=%s;Length=%lu\r\n", a5, v13) + a8 + 135;
      v16 = v15 + HIDWORD(pBuffer);
      if ( v15 + HIDWORD(pBuffer) >= v15 )
      {
        if ( v16 + v13 >= v16 )
          v12 = v16 + v13;
        v17 = v16 + v13 < v16 ? 0x216 : 0;
      }
      else
      {
        v17 = 534;
      }
    }
  }
  if ( v17 )
    return v17;
  *a4 = 0;
  v46 = *(_QWORD *)(a3 + 24);
  v47 = InterlockedPopEntrySList((PSLIST_HEADER)(v46 + 16));
  v23 = (CHeap *)&v47[-1];
  v24 = (unsigned __int64)&v47[-1] & -(__int64)(v47 != 0);
  if ( v24 )
  {
    *a4 = (Packet *)v24;
    goto LABEL_20;
  }
  if ( CHeap::GetHandle(v23) )
  {
    Handle = CHeap::GetHandle(v21);
    v24 = (__int64)HeapAlloc(Handle, 0, 0x40u);
    if ( v24 )
    {
      *(_QWORD *)(v24 + 32) = 0;
      *(_QWORD *)v24 = &Packet::`vftable';
      *(_QWORD *)(v24 + 40) = 0;
      *(_DWORD *)(v24 + 48) = 0;
      *(_QWORD *)(v24 + 24) = v46;
      _InterlockedIncrement((volatile signed __int32 *)(v46 + 32));
      goto LABEL_19;
    }
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
  }
  v24 = 0;
LABEL_19:
  *a4 = (Packet *)v24;
  if ( !v24 )
    return 14;
LABEL_20:
  v25 = *(const void **)(v24 + 32);
  if ( v25 )
  {
    Heap = WSManMemory::GetHeap();
    if ( HeapSize(Heap, 0, v25) >= v12 )
    {
      v28 = *(LPVOID *)(v24 + 32);
      goto LABEL_26;
    }
  }
  if ( !CHeap::GetHandle(v23) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
    goto LABEL_75;
  }
  v27 = CHeap::GetHandle(v26);
  v28 = HeapAlloc(v27, 0, v12);
  if ( !v28 )
  {
LABEL_75:
    Packet::Recycle(*a4);
    *a4 = 0;
    return 14;
  }
  v29 = *(void **)(v24 + 32);
  if ( v29 )
    WSManMemory::Free(v29, 0);
  *(_QWORD *)(v24 + 32) = v28;
LABEL_26:
  *(_QWORD *)(v24 + 40) = v28;
  *(_DWORD *)(v24 + 48) = v12;
  v30 = *(unsigned __int8 **)(a3 + 40);
  *(_QWORD *)&pBuffer = v30;
  if ( v30 )
  {
    v31 = *(_DWORD *)(a3 + 48);
  }
  else
  {
    v30 = (unsigned __int8 *)Buf1;
    v31 = 0;
    *(_QWORD *)&pBuffer = Buf1;
  }
  v32 = (const CHAR *)*((_QWORD *)*a4 + 5);
  if ( v32 )
  {
    v33 = *((_DWORD *)*a4 + 12);
  }
  else
  {
    v33 = 0;
    v32 = Buf1;
  }
  v52 = v33;
  LODWORD(dwBytes) = 0;
  v34 = v55;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids, v55);
  v35 = v56;
  *v56 = 0;
  if ( a9 == 2 && (a6 || v31 > 0x4000) )
  {
    *v35 = 1;
    for ( dwBytes = 0; ; v32 += HIDWORD(dwBytes) )
    {
      if ( v31 >= 0x4000 )
      {
        v51 = v31 == 0x4000;
        v31 -= 0x4000;
        v54 = 0x4000;
        v48 = 0x4000;
        v49 = v51;
      }
      else
      {
        v48 = v31;
        v49 = 1;
        v54 = v31;
      }
      v36 = EncryptDecryptHelper::DoPartEncryption(
              v55,
              v59,
              v48,
              v30,
              v58,
              v57,
              a8,
              2,
              v49,
              v33,
              v32,
              (char *)&dwBytes + 4);
      if ( v36 )
        break;
      v37 = HIDWORD(dwBytes) + dwBytes;
      LODWORD(dwBytes) = HIDWORD(dwBytes) + dwBytes;
      if ( v49 )
        goto LABEL_36;
      v33 = v52 - HIDWORD(dwBytes);
      v30 = (unsigned __int8 *)(v54 + (_QWORD)pBuffer);
      v52 -= HIDWORD(dwBytes);
      *(_QWORD *)&pBuffer = v30;
    }
    goto LABEL_83;
  }
  v36 = EncryptDecryptHelper::DoPartEncryption(v34, v59, v31, v30, v58, v57, a8, a9, 1, v33, v32, &dwBytes);
  if ( v36 )
  {
LABEL_83:
    Packet::Recycle(*a4);
    *a4 = 0;
    return v36;
  }
  v37 = dwBytes;
LABEL_36:
  v38 = *a4;
  v39 = (const void *)*((_QWORD *)*a4 + 4);
  if ( v39 )
  {
    v44 = WSManMemory::GetHeap();
    if ( HeapSize(v44, 0, v39) >= v37 )
    {
      v43 = (void *)*((_QWORD *)v38 + 4);
      goto LABEL_42;
    }
  }
  v40 = (CHeap *)*((_QWORD *)v38 + 4);
  if ( v40 )
  {
    v43 = WSManMemory::ReAlloc(v40, v37);
  }
  else if ( CHeap::GetHandle(0) )
  {
    v42 = CHeap::GetHandle(v41);
    v43 = HeapAlloc(v42, 0, v37);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
    v43 = 0;
  }
  if ( !v43 )
  {
    v36 = 14;
    goto LABEL_83;
  }
  *((_QWORD *)v38 + 4) = v43;
LABEL_42:
  *((_QWORD *)v38 + 5) = v43;
  *((_DWORD *)v38 + 12) = v37;
  return 0;
}

```

## disassembly

```asm
0x18004e188  push    rbp
0x18004e18a  push    rbx
0x18004e18b  push    rsi
0x18004e18c  push    rdi
0x18004e18d  push    r12
0x18004e18f  push    r13
0x18004e191  push    r14
0x18004e193  push    r15
0x18004e195  lea     rbp, [rsp-7]
0x18004e19a  sub     rsp, 0B8h
0x18004e1a1  mov     rax, cs:__security_cookie
0x18004e1a8  xor     rax, rsp
0x18004e1ab  mov     [rbp+3Fh+var_48], rax
0x18004e1af  mov     r14, [rbp+3Fh+arg_20]
0x18004e1b3  xor     r15d, r15d
0x18004e1b6  mov     rax, [rbp+3Fh+arg_48]
0x18004e1bd  mov     r12, r9
0x18004e1c0  mov     [rbp+3Fh+var_80], rcx
0x18004e1c4  mov     r13, r8
0x18004e1c7  mov     rcx, [rbp+3Fh+arg_30]; this
0x18004e1cb  mov     r10, rdx
0x18004e1ce  mov     [rbp+3Fh+var_70], rcx
0x18004e1d2  mov     [rbp+3Fh+var_60], rdx
0x18004e1d6  mov     [rbp+3Fh+var_68], r14
0x18004e1da  mov     [rbp+3Fh+var_78], rax
0x18004e1de  test    rdx, rdx
0x18004e1e1  jz      loc_18004E624
0x18004e1e7  test    r14, r14
0x18004e1ea  jz      loc_18004E635
0x18004e1f0  test    rcx, rcx
0x18004e1f3  jz      loc_18004E28B
0x18004e1f9  test    rax, rax
0x18004e1fc  jz      loc_18004E646
0x18004e202  mov     esi, r15d
0x18004e205  mov     [rbp+3Fh+var_90], r15d
0x18004e209  cmp     [r8+28h], r15
0x18004e20d  jnz     short loc_18004E285
0x18004e20f  mov     ebx, r15d
0x18004e212  mov     eax, [rbp+3Fh+arg_40]
0x18004e218  cmp     eax, 3
0x18004e21b  jge     loc_18004E552
0x18004e221  cmp     eax, 2
0x18004e224  jz      loc_18004E657
0x18004e22a  xorps   xmm0, xmm0
0x18004e22d  lea     r8, [rbp+3Fh+pBuffer]; pBuffer
0x18004e231  xor     edx, edx; ulAttribute
0x18004e233  mov     rcx, r10; phContext
0x18004e236  movups  [rbp+3Fh+pBuffer], xmm0
0x18004e23a  call    cs:__imp_QueryContextAttributesW
0x18004e240  mov     edi, eax
0x18004e242  test    eax, eax
0x18004e244  js      loc_18004E68E
0x18004e24a  mov     r8d, ebx
0x18004e24d  lea     rcx, aOriginalconten_0; "OriginalContent: type=application/soap+"...
0x18004e254  mov     rdx, r14
0x18004e257  call    cs:__imp__scprintf
0x18004e25d  mov     ecx, [rbp+3Fh+arg_38]
0x18004e263  or      esi, 0FFFFFFFFh
0x18004e266  mov     edx, dword ptr [rbp+3Fh+pBuffer+0Ch]
0x18004e269  add     ecx, 87h
0x18004e26f  add     ecx, eax
0x18004e271  add     edx, ecx
0x18004e273  cmp     edx, ecx
0x18004e275  jnb     loc_18004E507
0x18004e27b  mov     ebx, 216h
0x18004e280  jmp     loc_18004E517
0x18004e285  mov     ebx, [r8+30h]
0x18004e289  jmp     short loc_18004E212
0x18004e28b  lea     r8, a4871; "4871"
0x18004e292  mov     edx, 1307h; unsigned int
0x18004e297  mov     ebx, 54Fh
0x18004e29c  mov     [rsp+0F0h+var_D0], r15; struct IRequestContext *
0x18004e2a1  mov     r9d, ebx; unsigned int
0x18004e2a4  lea     rcx, aOnecoreAdminWm_90; "onecore\\admin\\wmi\\wmx\\stdlib\\wsman"...
0x18004e2ab  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18004e2b0  mov     eax, ebx
0x18004e2b2  jmp     loc_18004E48F
0x18004e2b7  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18004e2bc  test    rax, rax
0x18004e2bf  jz      loc_18004E6D0
0x18004e2c5  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18004e2ca  xor     edx, edx; dwFlags
0x18004e2cc  mov     rcx, rax; hHeap
0x18004e2cf  lea     r8d, [rdx+40h]; dwBytes
0x18004e2d3  call    cs:__imp_HeapAlloc
0x18004e2d9  mov     rdi, rax
0x18004e2dc  test    rax, rax
0x18004e2df  jz      loc_18004E6F0
0x18004e2e5  lea     rax, ??_7Packet@@6B@; const Packet::`vftable'
0x18004e2ec  mov     [rdi+20h], r15
0x18004e2f0  mov     [rdi], rax
0x18004e2f3  mov     [rdi+28h], r15
0x18004e2f7  mov     [rdi+30h], r15d
0x18004e2fb  mov     [rdi+18h], r14
0x18004e2ff  lock inc dword ptr [r14+20h]
0x18004e304  mov     [r12], rdi
0x18004e308  test    rdi, rdi
0x18004e30b  jz      loc_18004E72D
0x18004e311  mov     r15, [rdi+20h]
0x18004e315  mov     r14d, esi
0x18004e318  test    r15, r15
0x18004e31b  jnz     loc_18004E4E2
0x18004e321  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18004e326  test    rax, rax
0x18004e329  jz      loc_18004E6F8
0x18004e32f  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18004e334  mov     r8, r14; dwBytes
0x18004e337  xor     edx, edx; dwFlags
0x18004e339  mov     rcx, rax; hHeap
0x18004e33c  call    cs:__imp_HeapAlloc
0x18004e342  mov     r14, rax
0x18004e345  test    rax, rax
0x18004e348  jz      loc_18004E71C
0x18004e34e  mov     rcx, [rdi+20h]; void *
0x18004e352  test    rcx, rcx
0x18004e355  jnz     loc_18004E737
0x18004e35b  mov     [rdi+20h], r14
0x18004e35f  mov     [rdi+28h], r14
0x18004e363  mov     [rdi+30h], esi
0x18004e366  mov     rsi, [r13+28h]
0x18004e36a  mov     qword ptr [rbp+3Fh+pBuffer], rsi
0x18004e36e  test    rsi, rsi
0x18004e371  jnz     loc_18004E4AF
0x18004e377  lea     rsi, Buf1
0x18004e37e  xor     r14d, r14d
0x18004e381  mov     qword ptr [rbp+3Fh+pBuffer], rsi
0x18004e385  mov     rdi, [r12]
0x18004e389  mov     r15, [rdi+28h]
0x18004e38d  test    r15, r15
0x18004e390  jnz     loc_18004E4B8
0x18004e396  xor     edi, edi
0x18004e398  lea     r15, Buf1
0x18004e39f  mov     [rbp+3Fh+var_90], edi
0x18004e3a2  mov     dword ptr [rbp+3Fh+dwBytes], 0
0x18004e3a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e3b0  lea     rax, WPP_GLOBAL_Control
0x18004e3b7  mov     r13, [rbp+3Fh+var_80]
0x18004e3bb  cmp     rcx, rax
0x18004e3be  jz      short loc_18004E3CD
0x18004e3c0  test    dword ptr [rcx+1Ch], 400h
0x18004e3c7  jnz     loc_18004E743
0x18004e3cd  mov     rcx, [rbp+3Fh+var_78]
0x18004e3d1  mov     eax, [rbp+3Fh+arg_40]
0x18004e3d7  mov     byte ptr [rcx], 0
0x18004e3da  cmp     eax, 2
0x18004e3dd  jz      loc_18004E563
0x18004e3e3  mov     rdx, [rbp+3Fh+var_60]
0x18004e3e7  lea     rcx, [rbp+3Fh+dwBytes]
0x18004e3eb  mov     [rsp+0F0h+var_98], rcx
0x18004e3f0  mov     r9, rsi
0x18004e3f3  mov     [rsp+0F0h+var_A0], r15
0x18004e3f8  mov     r8d, r14d
0x18004e3fb  mov     [rsp+0F0h+var_A8], edi
0x18004e3ff  mov     rcx, r13
0x18004e402  mov     [rsp+0F0h+var_B0], 1
0x18004e407  mov     dword ptr [rsp+0F0h+var_B8], eax
0x18004e40b  mov     eax, [rbp+3Fh+arg_38]
0x18004e411  mov     [rsp+0F0h+var_C0], eax
0x18004e415  mov     rax, [rbp+3Fh+var_70]
0x18004e419  mov     qword ptr [rsp+0F0h+var_C8], rax
0x18004e41e  mov     rax, [rbp+3Fh+var_68]
0x18004e422  mov     [rsp+0F0h+var_D0], rax
0x18004e427  call    ?DoPartEncryption@EncryptDecryptHelper@@AEAAKPEAU_SecHandle@@KPEAEPEBD2KW4AuthenticationProcessed@@_NKPEADPEAK@Z; EncryptDecryptHelper::DoPartEncryption(_SecHandle *,ulong,uchar *,char const *,char const *,ulong,AuthenticationProcessed,bool,ulong,char *,ulong *)
0x18004e42c  mov     edi, eax
0x18004e42e  test    eax, eax
0x18004e430  jnz     loc_18004E7C6
0x18004e436  mov     esi, dword ptr [rbp+3Fh+dwBytes]
0x18004e439  mov     rdi, [r12]
0x18004e43d  mov     r14d, esi
0x18004e440  mov     r15, [rdi+20h]
0x18004e444  test    r15, r15
0x18004e447  jnz     short loc_18004E4C0
0x18004e449  mov     rcx, [rdi+20h]; this
0x18004e44d  test    rcx, rcx
0x18004e450  jnz     loc_18004E783
0x18004e456  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18004e45b  test    rax, rax
0x18004e45e  jz      loc_18004E796
0x18004e464  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18004e469  mov     r8, r14; dwBytes
0x18004e46c  xor     edx, edx; dwFlags
0x18004e46e  mov     rcx, rax; hHeap
0x18004e471  call    cs:__imp_HeapAlloc
0x18004e477  test    rax, rax
0x18004e47a  jz      loc_18004E7C1
0x18004e480  mov     [rdi+20h], rax
0x18004e484  mov     [rdi+28h], rax
0x18004e488  mov     [rdi+30h], esi
0x18004e48b  xor     edi, edi
0x18004e48d  mov     eax, edi
0x18004e48f  mov     rcx, [rbp+3Fh+var_48]
0x18004e493  xor     rcx, rsp; StackCookie
0x18004e496  call    __security_check_cookie
0x18004e49b  add     rsp, 0B8h
0x18004e4a2  pop     r15
0x18004e4a4  pop     r14
0x18004e4a6  pop     r13
0x18004e4a8  pop     r12
0x18004e4aa  pop     rdi
0x18004e4ab  pop     rsi
0x18004e4ac  pop     rbx
0x18004e4ad  pop     rbp
0x18004e4ae  retn
0x18004e4af  mov     r14d, [r13+30h]
0x18004e4b3  jmp     loc_18004E385
0x18004e4b8  mov     edi, [rdi+30h]
0x18004e4bb  jmp     loc_18004E39F
0x18004e4c0  call    ?GetHeap@WSManMemory@@SAPEAXXZ; WSManMemory::GetHeap(void)
0x18004e4c5  mov     r8, r15; lpMem
0x18004e4c8  xor     edx, edx; dwFlags
0x18004e4ca  mov     rcx, rax; hHeap
0x18004e4cd  call    cs:__imp_HeapSize
0x18004e4d3  cmp     rax, r14
0x18004e4d6  jb      loc_18004E449
0x18004e4dc  mov     rax, [rdi+20h]
0x18004e4e0  jmp     short loc_18004E484
0x18004e4e2  call    ?GetHeap@WSManMemory@@SAPEAXXZ; WSManMemory::GetHeap(void)
0x18004e4e7  mov     r8, r15; lpMem
0x18004e4ea  xor     edx, edx; dwFlags
0x18004e4ec  mov     rcx, rax; hHeap
0x18004e4ef  call    cs:__imp_HeapSize
0x18004e4f5  cmp     rax, r14
0x18004e4f8  jb      loc_18004E321
0x18004e4fe  mov     r14, [rdi+20h]
0x18004e502  jmp     loc_18004E35F
0x18004e507  lea     eax, [rdx+rbx]
0x18004e50a  cmp     eax, edx
0x18004e50c  cmovnb  esi, eax
0x18004e50f  sbb     ebx, ebx
0x18004e511  and     ebx, 216h
0x18004e517  test    ebx, ebx
0x18004e519  jnz     loc_18004E2B0
0x18004e51f  mov     [r12], r15
0x18004e523  mov     r14, [r13+18h]
0x18004e527  lea     rcx, [r14+10h]; ListHead
0x18004e52b  call    cs:__imp_InterlockedPopEntrySList
0x18004e531  mov     ebx, 54Fh
0x18004e536  lea     rcx, [rax-10h]; this
0x18004e53a  neg     rax
0x18004e53d  sbb     rdi, rdi
0x18004e540  and     rdi, rcx
0x18004e543  jz      loc_18004E2B7
0x18004e549  mov     [r12], rdi
0x18004e54d  jmp     loc_18004E311
0x18004e552  lea     r8, a4844; "4844"
0x18004e559  mov     edx, 12ECh
0x18004e55e  jmp     loc_18004E297
0x18004e563  cmp     [rbp+3Fh+arg_28], 0
0x18004e567  mov     edx, 4000h
0x18004e56c  jz      loc_18004E760
0x18004e572  mov     byte ptr [rcx], 1
0x18004e575  mov     dword ptr [rbp+3Fh+dwBytes], 0
0x18004e57c  mov     dword ptr [rbp+3Fh+dwBytes+4], 0
0x18004e583  cmp     r14d, edx
0x18004e586  jnb     loc_18004E76E
0x18004e58c  mov     eax, r14d
0x18004e58f  mov     r13b, 1
0x18004e592  mov     [rbp+3Fh+var_84], eax
0x18004e595  mov     rdx, [rbp+3Fh+var_60]
0x18004e599  lea     rcx, [rbp+3Fh+dwBytes+4]
0x18004e59d  mov     [rsp+0F0h+var_98], rcx
0x18004e5a2  mov     r9, rsi
0x18004e5a5  mov     ecx, [rbp+3Fh+arg_38]
0x18004e5ab  mov     r8d, eax
0x18004e5ae  mov     [rsp+0F0h+var_A0], r15
0x18004e5b3  mov     [rsp+0F0h+var_A8], edi
0x18004e5b7  mov     [rsp+0F0h+var_B0], r13b
0x18004e5bc  mov     dword ptr [rsp+0F0h+var_B8], 2
0x18004e5c4  mov     [rsp+0F0h+var_C0], ecx
0x18004e5c8  mov     rcx, [rbp+3Fh+var_70]
0x18004e5cc  mov     qword ptr [rsp+0F0h+var_C8], rcx
0x18004e5d1  mov     rcx, [rbp+3Fh+var_68]
0x18004e5d5  mov     [rsp+0F0h+var_D0], rcx
0x18004e5da  mov     rcx, [rbp+3Fh+var_80]
0x18004e5de  call    ?DoPartEncryption@EncryptDecryptHelper@@AEAAKPEAU_SecHandle@@KPEAEPEBD2KW4AuthenticationProcessed@@_NKPEADPEAK@Z; EncryptDecryptHelper::DoPartEncryption(_SecHandle *,ulong,uchar *,char const *,char const *,ulong,AuthenticationProcessed,bool,ulong,char *,ulong *)
0x18004e5e3  mov     edi, eax
0x18004e5e5  test    eax, eax
0x18004e5e7  jnz     loc_18004E7C6
0x18004e5ed  mov     esi, dword ptr [rbp+3Fh+dwBytes]
0x18004e5f0  mov     ecx, dword ptr [rbp+3Fh+dwBytes+4]
0x18004e5f3  add     esi, ecx
0x18004e5f5  mov     dword ptr [rbp+3Fh+dwBytes], esi
0x18004e5f8  test    r13b, r13b
0x18004e5fb  jnz     loc_18004E439
0x18004e601  mov     rsi, qword ptr [rbp+3Fh+pBuffer]
0x18004e605  mov     edx, 4000h
0x18004e60a  mov     edi, [rbp+3Fh+var_90]
0x18004e60d  mov     eax, [rbp+3Fh+var_84]
0x18004e610  sub     edi, ecx
0x18004e612  add     rsi, rax
0x18004e615  mov     [rbp+3Fh+var_90], edi
0x18004e618  mov     qword ptr [rbp+3Fh+pBuffer], rsi
0x18004e61c  add     r15, rcx
0x18004e61f  jmp     loc_18004E583
0x18004e624  lea     r8, a4869; "4869"
0x18004e62b  mov     edx, 1305h
0x18004e630  jmp     loc_18004E297
0x18004e635  lea     r8, a4870; "4870"
0x18004e63c  mov     edx, 1306h
0x18004e641  jmp     loc_18004E297
  ... truncated ...
```
