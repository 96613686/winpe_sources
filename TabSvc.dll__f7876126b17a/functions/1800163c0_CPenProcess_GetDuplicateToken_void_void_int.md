# CPenProcess::GetDuplicateToken(void *,void * *,int)

- ea: `0x1800163c0`
- end: `0x180016613`
- name: `?GetDuplicateToken@CPenProcess@@AEAAHPEAXPEAPEAXH@Z`
- size: `595`
- prototype: `__int64 __fastcall(CPenProcess *this, void *, void **phNewToken, DWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180014d40`

## callees

- `0x180001f24`
- `0x180015630`
- `0x1800163c0`
- `0x18002b3a8`
- `0x18002b404`
- `0x18002d574`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800163f6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800163f6`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800164af`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800164af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001641d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001652e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001641d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001652e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165da`

## string_xrefs

- `0x18001642a`: `PENSERVICE_CPenProcess::GetDuplicateToken`
- `0x1800164e3`: `PENSERVICE_CPenProcess::GetDuplicateToken`
- `0x18001655d`: `PENSERVICE_CPenProcess::GetDuplicateToken`
- `0x18001659b`: `PENSERVICE_CPenProcess::GetDuplicateToken`

## pseudocode

```c
__int64 __fastcall CPenProcess::GetDuplicateToken(CPenProcess *this, void *a2, void **phNewToken, DWORD a4)
{
  char LastError; // al
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  char v11; // al
  DWORD v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  void *v16; // rdx
  int v17; // eax
  DWORD v19; // [rsp+30h] [rbp-18h] BYREF
  _DWORD v20[5]; // [rsp+34h] [rbp-14h] BYREF

  if ( !DuplicateTokenEx(a2, 0x18Bu, 0, SecurityImpersonation, TokenPrimary, phNewToken) )
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_sd(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        12,
        (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
        (unsigned int)"PENSERVICE_CPenProcess::GetDuplicateToken",
        LastError);
    }
    if ( (unsigned int)dword_1800411A8 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
      {
        v19 = a4;
        v20[0] = GetLastError();
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v8,
          (int)word_18003ABCA,
          v9,
          v10,
          (__int64)v20,
          (__int64)&v19);
      }
    }
    return 0;
  }
  if ( a4 && !SetTokenInformation(*phNewToken, TokenSessionId, (char *)this + 32, 4u) )
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
    {
      v11 = GetLastError();
      WPP_SF_sd(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        13,
        (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
        (unsigned int)"PENSERVICE_CPenProcess::GetDuplicateToken",
        v11);
    }
    if ( (unsigned int)dword_1800411A8 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
      return 0;
    v20[0] = a4;
    v12 = GetLastError();
    v16 = &unk_18003AD50;
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      14,
      WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
      "PENSERVICE_CPenProcess::GetDuplicateToken");
  v17 = LUASetUIAToken2(phNewToken);
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
      WPP_SF_sd(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        15,
        (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
        (unsigned int)"PENSERVICE_CPenProcess::GetDuplicateToken",
        v17);
    if ( (unsigned int)dword_1800411A8 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
      return 0;
    v20[0] = a4;
    v12 = GetLastError();
    v16 = &unk_18003ACF8;
LABEL_26:
    v19 = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v13,
      (int)v16,
      v14,
      v15,
      (__int64)&v19,
      (__int64)v20);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800163c0  push    rbp
0x1800163c2  push    rbx
0x1800163c3  push    rsi
0x1800163c4  push    rdi
0x1800163c5  mov     rbp, rsp
0x1800163c8  sub     rsp, 48h
0x1800163cc  mov     rax, rdx
0x1800163cf  mov     [rsp+48h+phNewToken], r8; phNewToken
0x1800163d4  mov     edi, r9d
0x1800163d7  mov     [rsp+48h+TokenType], 1; TokenType
0x1800163df  mov     rsi, r8
0x1800163e2  mov     rbx, rcx
0x1800163e5  mov     rcx, rax; hExistingToken
0x1800163e8  mov     r9d, 2; ImpersonationLevel
0x1800163ee  xor     r8d, r8d; lpTokenAttributes
0x1800163f1  mov     edx, 18Bh; dwDesiredAccess
0x1800163f6  call    cs:__imp_DuplicateTokenEx
0x1800163fc  test    eax, eax
0x1800163fe  jnz     loc_180016497
0x180016404  mov     rax, cs:WPP_GLOBAL_Control
0x18001640b  lea     rbx, WPP_GLOBAL_Control
0x180016412  cmp     rax, rbx
0x180016415  jz      short loc_18001644A
0x180016417  test    byte ptr [rax+1Ch], 4
0x18001641b  jz      short loc_18001644A
0x18001641d  call    cs:__imp_GetLastError
0x180016423  mov     rcx, cs:WPP_GLOBAL_Control
0x18001642a  lea     r9, aPenserviceCpen_7; "PENSERVICE_CPenProcess::GetDuplicateTok"...
0x180016431  mov     edx, 0Ch
0x180016436  mov     [rsp+48h+TokenType], eax
0x18001643a  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x180016441  mov     rcx, [rcx+10h]
0x180016445  call    WPP_SF_sd
0x18001644a  mov     eax, cs:dword_1800411A8
0x180016450  cmp     eax, 5
0x180016453  jbe     loc_180016601
0x180016459  mov     edx, 4000000h
0x18001645e  lea     rcx, dword_1800411A8
0x180016465  call    _tlgKeywordOn
0x18001646a  test    al, al
0x18001646c  jz      loc_180016601
0x180016472  mov     [rbp+var_18], edi
0x180016475  call    cs:__imp_GetLastError
0x18001647b  mov     [rbp+var_14], eax
0x18001647e  lea     rdx, word_18003ABCA
0x180016485  lea     rax, [rbp+var_18]
0x180016489  mov     [rsp+48h+phNewToken], rax
0x18001648e  lea     rax, [rbp+var_14]
0x180016492  jmp     loc_1800165F7
0x180016497  test    edi, edi
0x180016499  jz      loc_180016540
0x18001649f  mov     rcx, [rsi]; TokenHandle
0x1800164a2  lea     r8, [rbx+20h]; TokenInformation
0x1800164a6  mov     edx, 0Ch; TokenInformationClass
0x1800164ab  lea     r9d, [rdx-8]; TokenInformationLength
0x1800164af  call    cs:__imp_SetTokenInformation
0x1800164b5  test    eax, eax
0x1800164b7  jnz     loc_180016540
0x1800164bd  mov     rax, cs:WPP_GLOBAL_Control
0x1800164c4  lea     rbx, WPP_GLOBAL_Control
0x1800164cb  cmp     rax, rbx
0x1800164ce  jz      short loc_180016503
0x1800164d0  test    byte ptr [rax+1Ch], 4
0x1800164d4  jz      short loc_180016503
0x1800164d6  call    cs:__imp_GetLastError
0x1800164dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800164e3  lea     r9, aPenserviceCpen_7; "PENSERVICE_CPenProcess::GetDuplicateTok"...
0x1800164ea  mov     edx, 0Dh
0x1800164ef  mov     [rsp+48h+TokenType], eax
0x1800164f3  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x1800164fa  mov     rcx, [rcx+10h]
0x1800164fe  call    WPP_SF_sd
0x180016503  mov     eax, cs:dword_1800411A8
0x180016509  cmp     eax, 5
0x18001650c  jbe     loc_180016601
0x180016512  mov     edx, 4000000h
0x180016517  lea     rcx, dword_1800411A8
0x18001651e  call    _tlgKeywordOn
0x180016523  test    al, al
0x180016525  jz      loc_180016601
0x18001652b  mov     [rbp+var_14], edi
0x18001652e  call    cs:__imp_GetLastError
0x180016534  lea     rdx, unk_18003AD50
0x18001653b  jmp     loc_1800165E7
0x180016540  mov     rcx, cs:WPP_GLOBAL_Control
0x180016547  lea     rbx, WPP_GLOBAL_Control
0x18001654e  cmp     rcx, rbx
0x180016551  jz      short loc_180016575
0x180016553  test    byte ptr [rcx+1Ch], 10h
0x180016557  jz      short loc_180016575
0x180016559  mov     rcx, [rcx+10h]
0x18001655d  lea     r9, aPenserviceCpen_7; "PENSERVICE_CPenProcess::GetDuplicateTok"...
0x180016564  mov     edx, 0Eh
0x180016569  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x180016570  call    WPP_SF_s
0x180016575  mov     rcx, rsi
0x180016578  call    LUASetUIAToken2
0x18001657d  test    eax, eax
0x18001657f  jz      loc_180016605
0x180016585  mov     rcx, cs:WPP_GLOBAL_Control
0x18001658c  cmp     rcx, rbx
0x18001658f  jz      short loc_1800165B7
0x180016591  test    byte ptr [rcx+1Ch], 4
0x180016595  jz      short loc_1800165B7
0x180016597  mov     rcx, [rcx+10h]
0x18001659b  lea     r9, aPenserviceCpen_7; "PENSERVICE_CPenProcess::GetDuplicateTok"...
0x1800165a2  mov     edx, 0Fh
0x1800165a7  mov     [rsp+48h+TokenType], eax
0x1800165ab  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x1800165b2  call    WPP_SF_sd
0x1800165b7  mov     eax, cs:dword_1800411A8
0x1800165bd  cmp     eax, 5
0x1800165c0  jbe     short loc_180016601
0x1800165c2  mov     edx, 4000000h
0x1800165c7  lea     rcx, dword_1800411A8
0x1800165ce  call    _tlgKeywordOn
0x1800165d3  test    al, al
0x1800165d5  jz      short loc_180016601
0x1800165d7  mov     [rbp+var_14], edi
0x1800165da  call    cs:__imp_GetLastError
0x1800165e0  lea     rdx, unk_18003ACF8
0x1800165e7  mov     [rbp+var_18], eax
0x1800165ea  lea     rax, [rbp+var_14]
0x1800165ee  mov     [rsp+48h+phNewToken], rax
0x1800165f3  lea     rax, [rbp+var_18]
0x1800165f7  mov     qword ptr [rsp+48h+TokenType], rax
0x1800165fc  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016601  xor     eax, eax
0x180016603  jmp     short loc_18001660A
0x180016605  mov     eax, 1
0x18001660a  add     rsp, 48h
0x18001660e  pop     rdi
0x18001660f  pop     rsi
0x180016610  pop     rbx
0x180016611  pop     rbp
0x180016612  retn
```
