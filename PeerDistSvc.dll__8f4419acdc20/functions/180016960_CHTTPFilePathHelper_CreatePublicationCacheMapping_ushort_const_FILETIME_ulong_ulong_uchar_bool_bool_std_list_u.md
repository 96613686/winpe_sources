# CHTTPFilePathHelper::CreatePublicationCacheMapping(ushort const *,_FILETIME,ulong,ulong,uchar *,bool,bool,std::list<ushort const *,std::allocator<ushort const *>> *)

- ea: `0x180016960`
- end: `0x180016e16`
- name: `?CreatePublicationCacheMapping@CHTTPFilePathHelper@@UEAAKPEBGU_FILETIME@@KKPEAE_N3PEAV?$list@PEBGV?$allocator@PEBG@std@@@std@@@Z`
- size: `1206`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, int, __int64, char, char, __int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, reparse_path`

## callees

- `0x1800024f0`
- `0x180004374`
- `0x18000cf48`
- `0x18000cfc0`
- `0x18000e330`
- `0x18000ecf4`
- `0x18000fac0`
- `0x180011be0`
- `0x180011db0`
- `0x180015d38`
- `0x180016738`
- `0x180016960`
- `0x180016ed0`
- `0x18001703c`
- `0x180017bbc`
- `0x180018340`
- `0x18001844c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c33`
- `KERNEL32!CreateHardLinkW` at `0x180016c29`
- `KERNEL32!CreateHardLinkW` at `0x180016c29`

## pseudocode

```c
__int64 __fastcall CHTTPFilePathHelper::CreatePublicationCacheMapping(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        int a5,
        __int64 a6,
        char a7,
        char a8,
        __int64 a9)
{
  WCHAR *v13; // r14
  CPubCacheFileName *v15; // rdi
  DWORD PublicationCachePathHelper; // eax
  DWORD v17; // r12d
  CHostedCacheMsgEncoding *v18; // rcx
  int v19; // edx
  char v20; // r10
  CHostedCacheMsgEncoding *v21; // rcx
  _QWORD *v22; // rax
  _QWORD *v23; // rsi
  __int64 v24; // rbx
  DWORD v25; // eax
  WCHAR *v26; // rbx
  __int64 v27; // rcx
  DWORD LastError; // eax
  WCHAR *v29; // rcx
  const wchar_t *v30; // r9
  const wchar_t *v31; // r8
  const wchar_t *v32; // rax
  __int64 v33; // rcx
  LPCWSTR lpFileName; // [rsp+30h] [rbp-40h] BYREF
  CPubCacheFileName *v35; // [rsp+38h] [rbp-38h] BYREF
  __int64 v36; // [rsp+40h] [rbp-30h] BYREF
  _QWORD *v37; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v38[2]; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v39[16]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v40; // [rsp+B8h] [rbp+48h] BYREF
  int v41; // [rsp+C8h] [rbp+58h]

  v41 = a4;
  v13 = 0;
  if ( !a2 )
    return 87;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 52, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids, a2);
  }
  v36 = 0;
  v15 = 0;
  v35 = 0;
  lpFileName = 0;
  std::list<unsigned short const *>::list<unsigned short const *>(v38);
  v37 = v38;
  LockSentry<ReadersWriterLock,1>::LockSentry<ReadersWriterLock,1>(v39, a1 + 8);
  if ( *(_QWORD *)(a1 + 72) )
  {
    PublicationCachePathHelper = CHTTPFilePathHelper::CreatePublicationCachePathHelper(
                                   a1,
                                   a2,
                                   a3,
                                   a4,
                                   (unsigned __int16 **)&lpFileName,
                                   (__int64)&v36);
    v17 = PublicationCachePathHelper;
    if ( PublicationCachePathHelper )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_68;
      }
      v19 = 54;
    }
    else
    {
      operator delete(0);
      v13 = (WCHAR *)lpFileName;
      if ( a6 )
      {
        PublicationCachePathHelper = CHTTPFilePathHelper::CreateContentIdMapping(a1, a5, a6, lpFileName, a4, &v35);
        v17 = PublicationCachePathHelper;
        if ( PublicationCachePathHelper )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            goto LABEL_68;
          }
          v19 = 55;
          goto LABEL_18;
        }
        v15 = v35;
      }
      v20 = *(_BYTE *)(a1 + 56);
      if ( !v20 || a8 || a7 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
        {
          v30 = L"Y";
          v31 = L"Y";
          if ( !a7 )
            v31 = (const wchar_t *)L"N";
          v32 = L"Y";
          if ( !a8 )
            v32 = (const wchar_t *)L"N";
          if ( !v20 )
            v30 = (const wchar_t *)L"N";
          WPP_SF_SSS(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            56,
            (unsigned int)WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids,
            (_DWORD)v30,
            (__int64)v32,
            (__int64)v31);
        }
LABEL_64:
        if ( a9 )
        {
          v17 = CHTTPFilePathHelper::PushPublicationCacheMapping(v21, v36 + 48, a9);
          if ( !v17 )
          {
            if ( v15 )
              v17 = CHTTPFilePathHelper::PushPublicationCacheMapping(v33, (char *)v15 + 48, a9);
          }
        }
        goto LABEL_68;
      }
      PublicationCachePathHelper = CHTTPFilePathHelper::GenerateContentFileMapping(a1, a2, v38);
      v17 = PublicationCachePathHelper;
      if ( !PublicationCachePathHelper )
      {
        v22 = (_QWORD *)v38[0];
        v23 = *(_QWORD **)v38[0];
        while ( 1 )
        {
          if ( v23 == v22 )
            goto LABEL_64;
          v24 = v23[2];
          v40 = 0;
          v25 = CHTTPFilePathHelper::CreatePublicationCachePathHelper(
                  a1,
                  v24,
                  a3,
                  v41,
                  (unsigned __int16 **)&lpFileName,
                  (__int64)&v40);
          v17 = v25;
          if ( v25 )
            break;
          operator delete(0);
          v26 = (WCHAR *)lpFileName;
          if ( !CreateHardLinkW(lpFileName, v13, 0) )
          {
            LastError = GetLastError();
            v17 = LastError;
            if ( LastError != 183 )
            {
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) )
              {
                WPP_SF_SSD(
                  *((_QWORD *)WPP_GLOBAL_Control + 12),
                  59,
                  (unsigned int)WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids,
                  (_DWORD)v26,
                  (__int64)v13,
                  LastError);
              }
LABEL_47:
              SmartPointer<CRepubJetSessionContext>::Release(&v40);
              v29 = v26;
LABEL_53:
              operator delete(v29);
              goto LABEL_68;
            }
            v17 = 0;
          }
          if ( a9 )
          {
            v17 = CHTTPFilePathHelper::PushPublicationCacheMapping(v27, v40 + 48, a9);
            if ( v17 )
              goto LABEL_47;
          }
          SmartPointer<CRepubJetSessionContext>::Release(&v40);
          operator delete(v26);
          v23 = (_QWORD *)*v23;
          v22 = (_QWORD *)v38[0];
        }
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            58,
            (unsigned int)WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids,
            v24,
            v25);
        }
        SmartPointer<CRepubJetSessionContext>::Release(&v40);
        v29 = 0;
        goto LABEL_53;
      }
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_68;
      }
      v19 = 57;
    }
LABEL_18:
    WPP_SF_Sd(
      *((_QWORD *)v18 + 12),
      v19,
      (unsigned int)WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids,
      a2,
      PublicationCachePathHelper);
LABEL_68:
    LockSentry<ReadersWriterLock,1>::Unlock(v39);
    CHTTPFilePathHelper::CHTTPFileMappingListScopeGuard::~CHTTPFileMappingListScopeGuard((CHTTPFilePathHelper::CHTTPFileMappingListScopeGuard *)&v37);
    std::list<unsigned short const *>::~list<unsigned short const *>(v38);
    SmartPointer<CRepubJetSessionContext>::Release(&v35);
    SmartPointer<CRepubJetSessionContext>::Release(&v36);
    operator delete(v13);
    return v17;
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 53, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids);
  }
  LockSentry<ReadersWriterLock,1>::Unlock(v39);
  CHTTPFilePathHelper::CHTTPFileMappingListScopeGuard::~CHTTPFileMappingListScopeGuard((CHTTPFilePathHelper::CHTTPFileMappingListScopeGuard *)&v37);
  std::list<unsigned short const *>::~list<unsigned short const *>(v38);
  SmartPointer<CRepubJetSessionContext>::Release(&v35);
  SmartPointer<CRepubJetSessionContext>::Release(&v36);
  operator delete(0);
  return 4054;
}

```

## disassembly

```asm
0x180016960  mov     [rsp-38h+arg_0], rbx
0x180016965  mov     [rsp-38h+arg_18], r9d
0x18001696a  push    rbp
0x18001696b  push    rsi
0x18001696c  push    rdi
0x18001696d  push    r12
0x18001696f  push    r13
0x180016971  push    r14
0x180016973  push    r15
0x180016975  mov     rbp, rsp
0x180016978  sub     rsp, 70h
0x18001697c  mov     esi, r9d
0x18001697f  mov     r15, r8
0x180016982  mov     rbx, rdx
0x180016985  mov     r13, rcx
0x180016988  xor     r14d, r14d
0x18001698b  test    rdx, rdx
0x18001698e  jnz     short loc_180016998
0x180016990  lea     eax, [rdx+57h]
0x180016993  jmp     loc_180016DFE
0x180016998  lea     rax, WPP_GLOBAL_Control
0x18001699f  mov     r12b, 4
0x1800169a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169a9  cmp     rcx, rax
0x1800169ac  jz      short loc_1800169D2
0x1800169ae  test    [rcx+6Ch], r12b
0x1800169b2  jz      short loc_1800169D2
0x1800169b4  cmp     [rcx+69h], r12b
0x1800169b8  jb      short loc_1800169D2
0x1800169ba  mov     edx, 34h ; '4'
0x1800169bf  mov     r9, rbx
0x1800169c2  lea     r8, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids
0x1800169c9  mov     rcx, [rcx+60h]
0x1800169cd  call    WPP_SF_S
0x1800169d2  mov     [rbp+var_30], r14
0x1800169d6  mov     rdi, r14
0x1800169d9  mov     [rbp+var_38], r14
0x1800169dd  mov     [rbp+lpFileName], r14
0x1800169e1  lea     rcx, [rbp+var_20]
0x1800169e5  call    ??0?$list@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::list<ushort const *>::list<ushort const *>(void)
0x1800169ea  lea     rax, [rbp+var_20]
0x1800169ee  mov     [rbp+var_28], rax
0x1800169f2  lea     rdx, [r13+8]
0x1800169f6  lea     rcx, [rbp+var_10]
0x1800169fa  call    ??0?$LockSentry@VReadersWriterLock@@$00@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,1>::LockSentry<ReadersWriterLock,1>(ReadersWriterLock &)
0x1800169ff  cmp     [r13+48h], r14
0x180016a03  jnz     short loc_180016A77
0x180016a05  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a0c  lea     r9, WPP_GLOBAL_Control
0x180016a13  cmp     rcx, r9
0x180016a16  jz      short loc_180016A39
0x180016a18  test    [rcx+6Ch], r12b
0x180016a1c  jz      short loc_180016A39
0x180016a1e  cmp     byte ptr [rcx+69h], 1
0x180016a22  jb      short loc_180016A39
0x180016a24  mov     edx, 35h ; '5'
0x180016a29  lea     r8, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids
0x180016a30  mov     rcx, [rcx+60h]
0x180016a34  call    WPP_SF_
0x180016a39  lea     rcx, [rbp+var_10]
0x180016a3d  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$00@@QEAAXXZ; LockSentry<ReadersWriterLock,1>::Unlock(void)
0x180016a42  lea     rcx, [rbp+var_28]; this
0x180016a46  call    ??1CHTTPFileMappingListScopeGuard@CHTTPFilePathHelper@@QEAA@XZ; CHTTPFilePathHelper::CHTTPFileMappingListScopeGuard::~CHTTPFileMappingListScopeGuard(void)
0x180016a4b  lea     rcx, [rbp+var_20]
0x180016a4f  call    ??1?$list@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::list<ushort const *>::~list<ushort const *>(void)
0x180016a54  lea     rcx, [rbp+var_38]
0x180016a58  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180016a5d  lea     rcx, [rbp+var_30]
0x180016a61  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180016a66  xor     ecx, ecx; Block
0x180016a68  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016a6d  mov     eax, 0FD6h
0x180016a72  jmp     loc_180016DFE
0x180016a77  lea     rax, [rbp+var_30]
0x180016a7b  mov     [rsp+70h+var_48], rax; __int64
0x180016a80  lea     rax, [rbp+lpFileName]
0x180016a84  mov     [rsp+70h+var_50], rax; unsigned __int16 **
0x180016a89  mov     r9d, esi; int
0x180016a8c  mov     r8, r15; int
0x180016a8f  mov     rdx, rbx; int
0x180016a92  mov     rcx, r13; int
0x180016a95  call    ?CreatePublicationCachePathHelper@CHTTPFilePathHelper@@AEAAKPEBGU_FILETIME@@KPEAPEAGPEAV?$SmartPointer@VCPubCacheFileName@@@@@Z; CHTTPFilePathHelper::CreatePublicationCachePathHelper(ushort const *,_FILETIME,ulong,ushort * *,SmartPointer<CPubCacheFileName> *)
0x180016a9a  mov     r12d, eax
0x180016a9d  test    eax, eax
0x180016a9f  jz      short loc_180016AED
0x180016aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180016aa8  lea     r9, WPP_GLOBAL_Control
0x180016aaf  cmp     rcx, r9
0x180016ab2  jz      loc_180016DC6
0x180016ab8  test    byte ptr [rcx+6Ch], 4
0x180016abc  jz      loc_180016DC6
0x180016ac2  cmp     byte ptr [rcx+69h], 1
0x180016ac6  jb      loc_180016DC6
0x180016acc  mov     edx, 36h ; '6'
0x180016ad1  mov     dword ptr [rsp+70h+var_50], eax
0x180016ad5  mov     r9, rbx
0x180016ad8  lea     r8, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids
0x180016adf  mov     rcx, [rcx+60h]
0x180016ae3  call    WPP_SF_Sd
0x180016ae8  jmp     loc_180016DC6
0x180016aed  xor     ecx, ecx; Block
0x180016aef  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016af4  mov     r14, [rbp+lpFileName]
0x180016af8  mov     r8, [rbp+arg_28]
0x180016afc  test    r8, r8
0x180016aff  jz      short loc_180016B5C
0x180016b01  lea     rax, [rbp+var_38]
0x180016b05  mov     [rsp+70h+var_48], rax
0x180016b0a  mov     dword ptr [rsp+70h+var_50], esi
0x180016b0e  mov     r9, r14
0x180016b11  mov     edx, [rbp+arg_20]
0x180016b14  mov     rcx, r13
0x180016b17  call    ?CreateContentIdMapping@CHTTPFilePathHelper@@AEAAKKPEAEPEBGKPEAV?$SmartPointer@VCPubCacheFileName@@@@@Z; CHTTPFilePathHelper::CreateContentIdMapping(ulong,uchar *,ushort const *,ulong,SmartPointer<CPubCacheFileName> *)
0x180016b1c  mov     r12d, eax
0x180016b1f  test    eax, eax
0x180016b21  jz      short loc_180016B58
0x180016b23  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b2a  lea     r9, WPP_GLOBAL_Control
0x180016b31  cmp     rcx, r9
0x180016b34  jz      loc_180016DC6
0x180016b3a  test    byte ptr [rcx+6Ch], 4
0x180016b3e  jz      loc_180016DC6
0x180016b44  cmp     byte ptr [rcx+69h], 1
0x180016b48  jb      loc_180016DC6
0x180016b4e  mov     edx, 37h ; '7'
0x180016b53  jmp     loc_180016AD1
0x180016b58  mov     rdi, [rbp+var_38]
0x180016b5c  mov     r10b, [r13+38h]
0x180016b60  mov     dl, [rbp+arg_38]
0x180016b63  mov     al, [rbp+arg_30]
0x180016b66  test    r10b, r10b
0x180016b69  jz      loc_180016D24
0x180016b6f  test    dl, dl
0x180016b71  jnz     loc_180016D24
0x180016b77  test    al, al
0x180016b79  jnz     loc_180016D24
0x180016b7f  lea     r8, [rbp+var_20]
0x180016b83  mov     rdx, rbx
0x180016b86  mov     rcx, r13
0x180016b89  call    ?GenerateContentFileMapping@CHTTPFilePathHelper@@AEAAKPEBGAEAV?$list@PEBGV?$allocator@PEBG@std@@@std@@@Z; CHTTPFilePathHelper::GenerateContentFileMapping(ushort const *,std::list<ushort const *> &)
0x180016b8e  mov     r12d, eax
0x180016b91  test    eax, eax
0x180016b93  jz      short loc_180016BCA
0x180016b95  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b9c  lea     r9, WPP_GLOBAL_Control
0x180016ba3  cmp     rcx, r9
0x180016ba6  jz      loc_180016DC6
0x180016bac  test    byte ptr [rcx+6Ch], 4
0x180016bb0  jz      loc_180016DC6
0x180016bb6  cmp     byte ptr [rcx+69h], 1
0x180016bba  jb      loc_180016DC6
0x180016bc0  mov     edx, 39h ; '9'
0x180016bc5  jmp     loc_180016AD1
0x180016bca  mov     rax, [rbp+var_20]
0x180016bce  mov     rsi, [rax]
0x180016bd1  cmp     rsi, rax
0x180016bd4  jz      loc_180016D89
0x180016bda  mov     rbx, [rsi+10h]
0x180016bde  mov     [rbp+arg_8], 0
0x180016be6  lea     rax, [rbp+arg_8]
0x180016bea  mov     [rsp+70h+var_48], rax; __int64
0x180016bef  lea     rax, [rbp+lpFileName]
0x180016bf3  mov     [rsp+70h+var_50], rax; unsigned __int16 **
0x180016bf8  mov     r9d, [rbp+arg_18]; int
0x180016bfc  mov     r8, r15; int
0x180016bff  mov     rdx, rbx; int
0x180016c02  mov     rcx, r13; int
0x180016c05  call    ?CreatePublicationCachePathHelper@CHTTPFilePathHelper@@AEAAKPEBGU_FILETIME@@KPEAPEAGPEAV?$SmartPointer@VCPubCacheFileName@@@@@Z; CHTTPFilePathHelper::CreatePublicationCachePathHelper(ushort const *,_FILETIME,ulong,ushort * *,SmartPointer<CPubCacheFileName> *)
0x180016c0a  mov     r12d, eax
0x180016c0d  test    eax, eax
0x180016c0f  jnz     loc_180016CD4
0x180016c15  xor     ecx, ecx; Block
0x180016c17  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016c1c  mov     rbx, [rbp+lpFileName]
0x180016c20  xor     r8d, r8d; lpSecurityAttributes
0x180016c23  mov     rdx, r14; lpExistingFileName
0x180016c26  mov     rcx, rbx; lpFileName
0x180016c29  call    cs:__imp_CreateHardLinkW
0x180016c2f  test    eax, eax
0x180016c31  jnz     short loc_180016C46
0x180016c33  call    cs:__imp_GetLastError
0x180016c39  mov     r12d, eax
0x180016c3c  cmp     eax, 0B7h
0x180016c41  jnz     short loc_180016C86
0x180016c43  xor     r12d, r12d
0x180016c46  mov     rax, [rbp+arg_40]
0x180016c4d  test    rax, rax
0x180016c50  jz      short loc_180016C69
0x180016c52  mov     rdx, [rbp+arg_8]
0x180016c56  add     rdx, 30h ; '0'
0x180016c5a  mov     r8, rax
0x180016c5d  call    ?PushPublicationCacheMapping@CHTTPFilePathHelper@@AEAAKPEBGPEAV?$list@PEBGV?$allocator@PEBG@std@@@std@@@Z; CHTTPFilePathHelper::PushPublicationCacheMapping(ushort const *,std::list<ushort const *> *)
0x180016c62  mov     r12d, eax
0x180016c65  test    eax, eax
0x180016c67  jnz     short loc_180016CC6
0x180016c69  lea     rcx, [rbp+arg_8]
0x180016c6d  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180016c72  mov     rcx, rbx; Block
0x180016c75  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016c7a  mov     rsi, [rsi]
0x180016c7d  mov     rax, [rbp+var_20]
0x180016c81  jmp     loc_180016BD1
0x180016c86  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c8d  lea     r9, WPP_GLOBAL_Control
0x180016c94  cmp     rcx, r9
0x180016c97  jz      short loc_180016CC6
0x180016c99  test    byte ptr [rcx+6Ch], 4
0x180016c9d  jz      short loc_180016CC6
0x180016c9f  cmp     byte ptr [rcx+69h], 1
0x180016ca3  jb      short loc_180016CC6
0x180016ca5  mov     edx, 3Bh ; ';'
0x180016caa  mov     dword ptr [rsp+70h+var_48], eax
0x180016cae  mov     [rsp+70h+var_50], r14
0x180016cb3  mov     r9, rbx
0x180016cb6  lea     r8, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids
0x180016cbd  mov     rcx, [rcx+60h]
0x180016cc1  call    WPP_SF_SSD
0x180016cc6  lea     rcx, [rbp+arg_8]
0x180016cca  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180016ccf  mov     rcx, rbx
0x180016cd2  jmp     short loc_180016D1A
0x180016cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cdb  lea     r9, WPP_GLOBAL_Control
0x180016ce2  cmp     rcx, r9
0x180016ce5  jz      short loc_180016D0F
0x180016ce7  test    byte ptr [rcx+6Ch], 4
0x180016ceb  jz      short loc_180016D0F
0x180016ced  cmp     byte ptr [rcx+69h], 1
0x180016cf1  jb      short loc_180016D0F
0x180016cf3  mov     edx, 3Ah ; ':'
0x180016cf8  mov     dword ptr [rsp+70h+var_50], eax
0x180016cfc  mov     r9, rbx
0x180016cff  lea     r8, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids
0x180016d06  mov     rcx, [rcx+60h]
0x180016d0a  call    WPP_SF_Sd
0x180016d0f  lea     rcx, [rbp+arg_8]
0x180016d13  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180016d18  xor     ecx, ecx; Block
0x180016d1a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016d1f  jmp     loc_180016DC6
0x180016d24  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d2b  lea     r9, WPP_GLOBAL_Control
0x180016d32  cmp     rcx, r9
0x180016d35  jz      short loc_180016D89
0x180016d37  test    byte ptr [rcx+6Ch], 4
0x180016d3b  jz      short loc_180016D89
0x180016d3d  cmp     byte ptr [rcx+69h], 4
0x180016d41  jb      short loc_180016D89
0x180016d43  lea     r11, aN; "N"
0x180016d4a  lea     r9, aY; "Y"
0x180016d51  mov     r8, r9
0x180016d54  test    al, al
0x180016d56  cmovz   r8, r11
0x180016d5a  mov     rax, r9
0x180016d5d  test    dl, dl
0x180016d5f  cmovz   rax, r11
0x180016d63  test    r10b, r10b
0x180016d66  cmovz   r9, r11
0x180016d6a  mov     edx, 38h ; '8'
0x180016d6f  mov     [rsp+70h+var_48], r8
0x180016d74  mov     [rsp+70h+var_50], rax
0x180016d79  lea     r8, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids
0x180016d80  mov     rcx, [rcx+60h]
0x180016d84  call    WPP_SF_SSS
0x180016d89  cmp     [rbp+arg_40], 0
0x180016d91  jz      short loc_180016DC6
0x180016d93  mov     rdx, [rbp+var_30]
0x180016d97  add     rdx, 30h ; '0'
0x180016d9b  mov     r8, [rbp+arg_40]
0x180016da2  call    ?PushPublicationCacheMapping@CHTTPFilePathHelper@@AEAAKPEBGPEAV?$list@PEBGV?$allocator@PEBG@std@@@std@@@Z; CHTTPFilePathHelper::PushPublicationCacheMapping(ushort const *,std::list<ushort const *> *)
0x180016da7  mov     r12d, eax
0x180016daa  test    eax, eax
0x180016dac  jnz     short loc_180016DC6
0x180016dae  test    rdi, rdi
0x180016db1  jz      short loc_180016DC6
0x180016db3  lea     rdx, [rdi+30h]
0x180016db7  mov     r8, [rbp+arg_40]
0x180016dbe  call    ?PushPublicationCacheMapping@CHTTPFilePathHelper@@AEAAKPEBGPEAV?$list@PEBGV?$allocator@PEBG@std@@@std@@@Z; CHTTPFilePathHelper::PushPublicationCacheMapping(ushort const *,std::list<ushort const *> *)
0x180016dc3  mov     r12d, eax
0x180016dc6  lea     rcx, [rbp+var_10]
0x180016dca  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$00@@QEAAXXZ; LockSentry<ReadersWriterLock,1>::Unlock(void)
0x180016dcf  lea     rcx, [rbp+var_28]; this
0x180016dd3  call    ??1CHTTPFileMappingListScopeGuard@CHTTPFilePathHelper@@QEAA@XZ; CHTTPFilePathHelper::CHTTPFileMappingListScopeGuard::~CHTTPFileMappingListScopeGuard(void)
0x180016dd8  lea     rcx, [rbp+var_20]
0x180016ddc  call    ??1?$list@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::list<ushort const *>::~list<ushort const *>(void)
0x180016de1  lea     rcx, [rbp+var_38]
0x180016de5  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180016dea  lea     rcx, [rbp+var_30]
0x180016dee  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180016df3  mov     rcx, r14; Block
0x180016df6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016dfb  mov     eax, r12d
0x180016dfe  mov     rbx, [rsp+70h+arg_0]
0x180016e06  add     rsp, 70h
0x180016e0a  pop     r15
0x180016e0c  pop     r14
0x180016e0e  pop     r13
0x180016e10  pop     r12
0x180016e12  pop     rdi
0x180016e13  pop     rsi
  ... truncated ...
```
