# CHTTPFilePathHelper::CreateContentIdMapping(ulong,uchar *,ushort const *,ulong,SmartPointer<CPubCacheFileName> *)

- ea: `0x180016738`
- end: `0x18001694e`
- name: `?CreateContentIdMapping@CHTTPFilePathHelper@@AEAAKKPEAEPEBGKPEAV?$SmartPointer@VCPubCacheFileName@@@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(__int64, int, int, const WCHAR *, int, CPubCacheFileName **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x180016960`

## callees

- `0x1800024f0`
- `0x180004374`
- `0x180008290`
- `0x18000cfc0`
- `0x18000ecf4`
- `0x180016738`
- `0x1801383d8`
- `0x180138b4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001689e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800168bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001689e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800168bc`
- `KERNEL32!CreateHardLinkW` at `0x180016894`
- `KERNEL32!CreateHardLinkW` at `0x1800168b2`
- `KERNEL32!CreateHardLinkW` at `0x180016894`
- `KERNEL32!CreateHardLinkW` at `0x1800168b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHTTPFilePathHelper::CreateContentIdMapping(
        __int64 a1,
        int a2,
        int a3,
        const WCHAR *a4,
        int a5,
        CPubCacheFileName **a6)
{
  unsigned int v10; // ebp
  __int64 v11; // r9
  WCHAR *v12; // rbx
  unsigned int v13; // eax
  __int64 v14; // rdx
  CPubCacheFileName *v15; // rdi
  unsigned int PublicationFilePath; // eax
  int v17; // esi
  DWORD LastError; // eax
  CPubCacheFileName **v19; // rsi
  LPCWSTR lpFileName; // [rsp+40h] [rbp-48h] BYREF
  CPubCacheFileName *v22; // [rsp+90h] [rbp+8h] BYREF

  v10 = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 44, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids);
  }
  v11 = *(_QWORD *)(a1 + 80);
  v12 = 0;
  lpFileName = 0;
  v22 = 0;
  v13 = CPubCacheFileName::Create((int)a1 + 64, a2, a3, v11, a5);
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 45, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids, v13);
    }
    goto LABEL_29;
  }
  v14 = *(_QWORD *)(a1 + 72);
  v15 = v22;
  PublicationFilePath = CPubCacheFileName::GeneratePublicationFilePath(
                          v22,
                          *(const unsigned __int16 **)(v14 + 16),
                          (unsigned __int16 **)&lpFileName);
  v17 = PublicationFilePath;
  if ( PublicationFilePath )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        46,
        WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids,
        PublicationFilePath);
    }
    if ( v17 > 0 )
      v10 = (unsigned __int16)v17 | 0x80070000;
    else
      v10 = v17;
    goto LABEL_29;
  }
  operator delete(0);
  v12 = (WCHAR *)lpFileName;
  if ( CreateHardLinkW(lpFileName, a4, 0) )
    goto LABEL_28;
  LastError = GetLastError();
  if ( LastError == 2 )
  {
    if ( !CreateHardLinkW(a4, v12, 0) )
    {
      LastError = GetLastError();
      goto LABEL_22;
    }
LABEL_28:
    v19 = a6;
    SmartPointer<CRepubJetSessionContext>::Release(a6);
    *v19 = v15;
    v22 = 0;
    goto LABEL_29;
  }
LABEL_22:
  if ( LastError == 183 || !LastError )
    goto LABEL_28;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      47,
      (unsigned int)WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids,
      (_DWORD)v12,
      (__int64)a4,
      LastError);
  }
LABEL_29:
  SmartPointer<CRepubJetSessionContext>::Release(&v22);
  operator delete(v12);
  return v10;
}

```

## disassembly

```asm
0x180016738  push    rbx
0x18001673a  push    rbp
0x18001673b  push    rsi
0x18001673c  push    rdi
0x18001673d  push    r14
0x18001673f  push    r15
0x180016741  sub     rsp, 58h
0x180016745  mov     r14, r9
0x180016748  mov     rsi, r8
0x18001674b  mov     r15d, edx
0x18001674e  mov     rdi, rcx
0x180016751  xor     ebp, ebp
0x180016753  mov     rcx, cs:WPP_GLOBAL_Control
0x18001675a  lea     rax, WPP_GLOBAL_Control
0x180016761  cmp     rcx, rax
0x180016764  jz      short loc_180016788
0x180016766  test    dword ptr [rcx+6Ch], 800h
0x18001676d  jz      short loc_180016788
0x18001676f  cmp     byte ptr [rcx+69h], 4
0x180016773  jb      short loc_180016788
0x180016775  mov     rcx, [rcx+60h]
0x180016779  lea     edx, [rbp+2Ch]
0x18001677c  lea     r8, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids
0x180016783  call    WPP_SF_
0x180016788  mov     r9, [rdi+50h]
0x18001678c  lea     rax, [rsp+88h+arg_0]
0x180016794  mov     [rsp+88h+var_50], rax
0x180016799  lea     rcx, [rdi+40h]
0x18001679d  mov     eax, [rsp+88h+arg_20]
0x1800167a4  xor     ebx, ebx
0x1800167a6  mov     r8, rsi
0x1800167a9  mov     dword ptr [rsp+88h+var_68], eax
0x1800167ad  mov     edx, r15d
0x1800167b0  mov     [rsp+88h+lpFileName], rbp
0x1800167b5  mov     [rsp+88h+arg_0], rbx
0x1800167bd  call    ?Create@CPubCacheFileName@@SAKAEAV?$SmartPointer@VIHashAlg@@@@KPEAEPEAGKK1PEAV?$SmartPointer@VCPubCacheFileName@@@@@Z; CPubCacheFileName::Create(SmartPointer<IHashAlg> &,ulong,uchar *,ushort *,ulong,ulong,uchar *,SmartPointer<CPubCacheFileName> *)
0x1800167c2  test    eax, eax
0x1800167c4  jz      short loc_18001680C
0x1800167c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167cd  lea     rdx, WPP_GLOBAL_Control
0x1800167d4  cmp     rcx, rdx
0x1800167d7  jz      loc_18001692A
0x1800167dd  test    byte ptr [rcx+6Ch], 4
0x1800167e1  jz      loc_18001692A
0x1800167e7  cmp     byte ptr [rcx+69h], 1
0x1800167eb  jb      loc_18001692A
0x1800167f1  mov     rcx, [rcx+60h]
0x1800167f5  lea     edx, [rbx+2Dh]
0x1800167f8  mov     r9d, eax
0x1800167fb  lea     r8, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids
0x180016802  call    WPP_SF_d
0x180016807  jmp     loc_18001692A
0x18001680c  mov     rdx, [rdi+48h]
0x180016810  lea     r8, [rsp+88h+lpFileName]; unsigned __int16 **
0x180016815  mov     rdi, [rsp+88h+arg_0]
0x18001681d  mov     rcx, rdi; this
0x180016820  mov     rdx, [rdx+10h]; unsigned __int16 *
0x180016824  call    ?GeneratePublicationFilePath@CPubCacheFileName@@QEAAKPEBGPEAPEAG@Z; CPubCacheFileName::GeneratePublicationFilePath(ushort const *,ushort * *)
0x180016829  mov     esi, eax
0x18001682b  test    eax, eax
0x18001682d  jz      short loc_18001687F
0x18001682f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016836  lea     rdx, WPP_GLOBAL_Control
0x18001683d  cmp     rcx, rdx
0x180016840  jz      short loc_180016866
0x180016842  test    byte ptr [rcx+6Ch], 4
0x180016846  jz      short loc_180016866
0x180016848  cmp     byte ptr [rcx+69h], 1
0x18001684c  jb      short loc_180016866
0x18001684e  mov     rcx, [rcx+60h]
0x180016852  lea     r8, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids
0x180016859  mov     edx, 2Eh ; '.'
0x18001685e  mov     r9d, eax
0x180016861  call    WPP_SF_d
0x180016866  test    esi, esi
0x180016868  jg      short loc_180016871
0x18001686a  mov     ebp, esi
0x18001686c  jmp     loc_18001692A
0x180016871  movzx   ebp, si
0x180016874  or      ebp, 80070000h
0x18001687a  jmp     loc_18001692A
0x18001687f  xor     ecx, ecx; Block
0x180016881  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016886  mov     rbx, [rsp+88h+lpFileName]
0x18001688b  xor     r8d, r8d; lpSecurityAttributes
0x18001688e  mov     rcx, rbx; lpFileName
0x180016891  mov     rdx, r14; lpExistingFileName
0x180016894  call    cs:__imp_CreateHardLinkW
0x18001689a  test    eax, eax
0x18001689c  jnz     short loc_18001690F
0x18001689e  call    cs:__imp_GetLastError
0x1800168a4  cmp     eax, 2
0x1800168a7  jnz     short loc_1800168C2
0x1800168a9  xor     r8d, r8d; lpSecurityAttributes
0x1800168ac  mov     rdx, rbx; lpExistingFileName
0x1800168af  mov     rcx, r14; lpFileName
0x1800168b2  call    cs:__imp_CreateHardLinkW
0x1800168b8  test    eax, eax
0x1800168ba  jnz     short loc_18001690F
0x1800168bc  call    cs:__imp_GetLastError
0x1800168c2  cmp     eax, 0B7h
0x1800168c7  jz      short loc_18001690F
0x1800168c9  test    eax, eax
0x1800168cb  jz      short loc_18001690F
0x1800168cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168d4  lea     rdx, WPP_GLOBAL_Control
0x1800168db  cmp     rcx, rdx
0x1800168de  jz      short loc_18001692A
0x1800168e0  test    byte ptr [rcx+6Ch], 4
0x1800168e4  jz      short loc_18001692A
0x1800168e6  cmp     byte ptr [rcx+69h], 1
0x1800168ea  jb      short loc_18001692A
0x1800168ec  mov     rcx, [rcx+60h]
0x1800168f0  lea     r8, WPP_dc3c53ed60a53432ddf31060f441d36e_Traceguids
0x1800168f7  mov     [rsp+88h+var_60], eax
0x1800168fb  mov     edx, 2Fh ; '/'
0x180016900  mov     r9, rbx
0x180016903  mov     [rsp+88h+var_68], r14
0x180016908  call    WPP_SF_SSD
0x18001690d  jmp     short loc_18001692A
0x18001690f  mov     rsi, [rsp+88h+arg_28]
0x180016917  mov     rcx, rsi
0x18001691a  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x18001691f  mov     [rsi], rdi
0x180016922  mov     [rsp+88h+arg_0], rbp
0x18001692a  lea     rcx, [rsp+88h+arg_0]
0x180016932  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180016937  mov     rcx, rbx; Block
0x18001693a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001693f  mov     eax, ebp
0x180016941  add     rsp, 58h
0x180016945  pop     r15
0x180016947  pop     r14
0x180016949  pop     rdi
0x18001694a  pop     rsi
0x18001694b  pop     rbp
0x18001694c  pop     rbx
0x18001694d  retn
```
