# CDbOperationManager::InitializeDB(int,ulong,int,int *)

- ea: `0x1800e9a58`
- end: `0x1800ea062`
- name: `?InitializeDB@CDbOperationManager@@AEAAJHKHPEAH@Z`
- size: `1546`
- prototype: `__int64 __usercall@<rax>(CDbOperationManager *__hidden this@<rcx>, int@<edx>, unsigned int@<r8d>, int@<r9d>, int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800e93ec`
- `0x1800ea5f8`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x18001133c`
- `0x18001137c`
- `0x18002dad0`
- `0x180041984`
- `0x1800d6154`
- `0x1800d73ec`
- `0x1800e9360`
- `0x1800e9a58`
- `0x1800ea068`
- `0x1800ea298`
- `0x1800ea510`
- `0x1800eb080`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1800e9bc8`
- `KERNEL32!GetFileAttributesW` at `0x1800e9bc8`
- `KERNEL32!CreateFileW` at `0x1800e9b28`
- `KERNEL32!CreateFileW` at `0x1800e9b28`
- `KERNEL32!CloseHandle` at `0x1800e9b37`
- `KERNEL32!CloseHandle` at `0x1800e9b37`
- `KERNEL32!GetLastError` at `0x1800e9b79`
- `KERNEL32!GetLastError` at `0x1800e9b79`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800e9c2f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800e9c2f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800e9c10`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800e9c10`
- `ESENT!JetGetDatabaseFileInfoW` at `0x1800e9ef4`
- `ESENT!JetGetDatabaseFileInfoW` at `0x1800e9ef4`
- `ESENT!JetAttachDatabase2W` at `0x1800e9e3a`
- `ESENT!JetAttachDatabase2W` at `0x1800e9e3a`
- `ESENT!JetBeginSessionW` at `0x1800e9d12`
- `ESENT!JetBeginSessionW` at `0x1800e9d12`
- `ESENT!JetCreateInstance2W` at `0x1800e9c4c`
- `ESENT!JetCreateInstance2W` at `0x1800e9c4c`

## pseudocode

```c
__int64 __fastcall CDbOperationManager::InitializeDB(CDbOperationManager *this, int a2, int a3, int a4, int *a5)
{
  int v10; // eax
  HRESULT Database; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  DWORD FileAttributesW; // eax
  JET_ERR Instance2W; // eax
  int v16; // eax
  _QWORD *v17; // rcx
  int v18; // edx
  int v19; // eax
  _QWORD *v20; // rcx
  int v21; // edx
  JET_ERR v22; // eax
  unsigned int v23; // r8d
  _QWORD *v24; // rcx
  int v25; // edx
  JET_ERR v26; // eax
  unsigned int v27; // r8d
  unsigned int v28; // r8d
  JET_ERR DatabaseFileInfoW; // eax
  int v30[2]; // [rsp+40h] [rbp-148h] BYREF
  int v31; // [rsp+48h] [rbp-140h]
  GUID pguid; // [rsp+50h] [rbp-138h] BYREF
  _BYTE pvResult[36]; // [rsp+60h] [rbp-128h] BYREF
  int v34; // [rsp+84h] [rbp-104h]

  v31 = a2;
  *(_QWORD *)v30 = a5;
  *a5 = 0;
  if ( a3 == 1 )
    return 2147942487LL;
  if ( a3 == 2 )
  {
    v10 = CMetaStoreUtils::DeleteFilesInDirectory(*((const unsigned __int16 **)this + 10), 0);
    Database = v10;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
          *((_QWORD *)this + 10),
          v10);
      return (unsigned int)Database;
    }
  }
  FileW = CreateFileW(*((LPCWSTR *)this + 11), 0xC0000000, 0, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
        (unsigned int)LastError);
    if ( a2 )
    {
      FileAttributesW = GetFileAttributesW(*((LPCWSTR *)this + 9));
      if ( FileAttributesW == -1 || (FileAttributesW & 0x10) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
            *((_QWORD *)this + 9));
        v31 = 0;
      }
    }
    pguid = 0;
    Database = CoCreateGuid(&pguid);
    if ( Database < 0 )
      return (unsigned int)Database;
    Database = StringFromCLSID(&pguid, (LPOLESTR *)this + 19);
    if ( Database < 0 )
      return (unsigned int)Database;
    Instance2W = JetCreateInstance2W((JET_INSTANCE *)this + 15, *((JET_PCWSTR *)this + 19), 0, 0);
    v16 = ResultFromJetError(Instance2W);
    Database = v16;
    if ( v16 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)Database;
      v18 = 30;
LABEL_35:
      WPP_SF_Sd(v17[2], v18, (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids, *((_QWORD *)this + 9), v16);
      return (unsigned int)Database;
    }
    v16 = CDbOperationManager::SetEseInstanceParameters(
            this,
            *((const unsigned __int16 **)this + 10),
            a4,
            *((const unsigned __int16 **)this + 12));
    Database = v16;
    if ( v16 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)Database;
      v18 = 31;
      goto LABEL_35;
    }
    v19 = CDbOperationManager::InitializeEseInstance(this, *((const unsigned __int16 **)this + 9));
    Database = v19;
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_46;
      v21 = 32;
LABEL_45:
      WPP_SF_Sd(v20[2], v21, (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids, *((_QWORD *)this + 9), v19);
LABEL_46:
      v30[0] = 0;
LABEL_47:
      if ( Database == (unsigned int)ResultFromJetError(-1083) || Database == (unsigned int)ResultFromJetError(-1084) )
      {
        return (unsigned int)-2147024864;
      }
      else if ( (unsigned int)CDbOperationManager::IsFatalJetError(this, Database, v30) )
      {
        if ( v30[0] )
        {
          if ( !*((_DWORD *)this + 10) )
          {
            *((_DWORD *)this + 10) = 1;
            *((_DWORD *)this + 13) = Database;
          }
          return (unsigned int)-2147216759;
        }
        else if ( v31 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              38,
              (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
              *((_QWORD *)this + 10),
              Database);
          *((_DWORD *)this + 13) = Database;
          Database = 0;
          *((_DWORD *)this + 11) = 0;
        }
      }
      return (unsigned int)Database;
    }
    v22 = JetBeginSessionW(*((_QWORD *)this + 15), (JET_SESID *)this + 16, 0, 0);
    v19 = ResultFromJetError(v22);
    Database = v19;
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_46;
      v21 = 33;
      goto LABEL_45;
    }
    if ( a3 == 2 )
    {
      Database = CJetSession::CreateDatabase(
                   (CDbOperationManager *)((char *)this + 128),
                   *((const unsigned __int16 **)this + 9),
                   v23,
                   0x200u,
                   (CDbOperationManager *)((char *)this + 136));
      if ( Database >= 0 )
        goto LABEL_60;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_60;
      v25 = 34;
LABEL_59:
      WPP_SF_Sd(
        v24[2],
        v25,
        (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
        *((_QWORD *)this + 9),
        Database);
LABEL_60:
      **(_DWORD **)v30 = Database >= 0;
      goto LABEL_85;
    }
    if ( (unsigned int)(a3 - 3) <= 1 )
    {
      v26 = JetAttachDatabase2W(*((_QWORD *)this + 16), *((JET_PCWSTR *)this + 9), 0, 0);
      Database = ResultFromJetError(v26);
      if ( Database == (unsigned int)ResultFromJetError(-1811) )
      {
        Database = -2147024894;
      }
      else if ( Database == (unsigned int)ResultFromJetError(-1217) )
      {
        Database = -2147024893;
      }
      else if ( Database == (unsigned int)ResultFromJetError(-1215) )
      {
        Database = -2147024864;
      }
      else if ( Database >= 0 )
      {
        Database = CJetSession::OpenDatabase(
                     (CDbOperationManager *)((char *)this + 128),
                     *((const unsigned __int16 **)this + 9),
                     v27,
                     (CDbOperationManager *)((char *)this + 136));
        goto LABEL_85;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
          *((_QWORD *)this + 9),
          Database);
      if ( Database == (unsigned int)ResultFromJetError(-550) )
      {
        memset_0(pvResult, 0, 0xD8u);
        DatabaseFileInfoW = JetGetDatabaseFileInfoW(*((JET_PCWSTR *)this + 9), pvResult, 0xD8u, 0xEu);
        if ( (int)ResultFromJetError(DatabaseFileInfoW) >= 0 && v34 == 1 )
        {
          if ( (Microsoft_Windows_SyncShareEnableBits & 1) != 0 )
            McTemplateU0zd_EventWriteTransfer(
              ECSServerEvents_Context,
              ECSSVC_EVENT_SYNC_DB_CORRUPTION_DETECTED,
              *((_QWORD *)this + 9),
              (unsigned int)Database);
          Database = -2147216759;
        }
      }
      else if ( Database == -2147024894 && a3 == 4 )
      {
        Database = CJetSession::CreateDatabase(
                     (CDbOperationManager *)((char *)this + 128),
                     *((const unsigned __int16 **)this + 9),
                     v28,
                     0,
                     (CDbOperationManager *)((char *)this + 136));
        if ( Database >= 0 )
          goto LABEL_60;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_60;
        v25 = 36;
        goto LABEL_59;
      }
    }
LABEL_85:
    v30[0] = 0;
    if ( Database >= 0 )
    {
      ++*((_QWORD *)this + 8);
      *(_QWORD *)((char *)this + 44) = 0;
      *((_DWORD *)this + 13) = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
          *((_QWORD *)this + 9),
          *((_DWORD *)this + 16));
      return (unsigned int)Database;
    }
    goto LABEL_47;
  }
  CloseHandle(FileW);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
      *((_QWORD *)this + 11));
  return 2147750537LL;
}

```

## disassembly

```asm
0x1800e9a58  mov     [rsp+arg_8], rbx
0x1800e9a5d  push    rbp
0x1800e9a5e  push    rsi
0x1800e9a5f  push    rdi
0x1800e9a60  push    r12
0x1800e9a62  push    r13
0x1800e9a64  push    r14
0x1800e9a66  push    r15
0x1800e9a68  sub     rsp, 150h
0x1800e9a6f  mov     rax, cs:__security_cookie
0x1800e9a76  xor     rax, rsp
0x1800e9a79  mov     [rsp+188h+var_48], rax
0x1800e9a81  mov     rax, [rsp+188h+arg_20]
0x1800e9a89  xor     r12d, r12d
0x1800e9a8c  mov     [rsp+188h+var_140], edx
0x1800e9a90  mov     r13d, r9d
0x1800e9a93  mov     qword ptr [rsp+188h+var_148], rax
0x1800e9a98  mov     r15d, r8d
0x1800e9a9b  mov     r14d, edx
0x1800e9a9e  mov     rdi, rcx
0x1800e9aa1  mov     [rax], r12d
0x1800e9aa4  cmp     r8d, 1
0x1800e9aa8  jnz     short loc_1800E9AB4
0x1800e9aaa  mov     eax, 80070057h
0x1800e9aaf  jmp     loc_1800EA037
0x1800e9ab4  cmp     r15d, 2
0x1800e9ab8  jnz     short loc_1800E9B04
0x1800e9aba  mov     rcx, [rcx+50h]; unsigned __int16 *
0x1800e9abe  xor     edx, edx; int
0x1800e9ac0  call    ?DeleteFilesInDirectory@CMetaStoreUtils@@SAJPEBGH@Z; CMetaStoreUtils::DeleteFilesInDirectory(ushort const *,int)
0x1800e9ac5  mov     ebx, eax
0x1800e9ac7  test    eax, eax
0x1800e9ac9  jns     short loc_1800E9B04
0x1800e9acb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9ad2  lea     rsi, WPP_GLOBAL_Control
0x1800e9ad9  cmp     rcx, rsi
0x1800e9adc  jz      loc_1800EA035
0x1800e9ae2  test    byte ptr [rcx+1Ch], 1
0x1800e9ae6  jz      loc_1800EA035
0x1800e9aec  mov     r9, [rdi+50h]
0x1800e9af0  lea     edx, [r15+18h]
0x1800e9af4  mov     [rsp+188h+dwCreationDisposition], eax
0x1800e9af8  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e9aff  jmp     loc_1800E9CC5
0x1800e9b04  mov     rcx, [rdi+58h]; lpFileName
0x1800e9b08  xor     r9d, r9d; lpSecurityAttributes
0x1800e9b0b  mov     [rsp+188h+hTemplateFile], r12; hTemplateFile
0x1800e9b10  xor     r8d, r8d; dwShareMode
0x1800e9b13  mov     [rsp+188h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800e9b1b  mov     edx, 0C0000000h; dwDesiredAccess
0x1800e9b20  mov     [rsp+188h+dwCreationDisposition], 3; dwCreationDisposition
0x1800e9b28  call    cs:__imp_CreateFileW
0x1800e9b2e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e9b32  jz      short loc_1800E9B79
0x1800e9b34  mov     rcx, rax; hObject
0x1800e9b37  call    cs:__imp_CloseHandle
0x1800e9b3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9b44  lea     rsi, WPP_GLOBAL_Control
0x1800e9b4b  cmp     rcx, rsi
0x1800e9b4e  jz      short loc_1800E9B6F
0x1800e9b50  test    byte ptr [rcx+1Ch], 2
0x1800e9b54  jz      short loc_1800E9B6F
0x1800e9b56  mov     r9, [rdi+58h]
0x1800e9b5a  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e9b61  mov     rcx, [rcx+10h]
0x1800e9b65  mov     edx, 1Bh
0x1800e9b6a  call    WPP_SF_S
0x1800e9b6f  mov     eax, 80041289h
0x1800e9b74  jmp     loc_1800EA037
0x1800e9b79  call    cs:__imp_GetLastError
0x1800e9b7f  test    eax, eax
0x1800e9b81  jle     short loc_1800E9B8B
0x1800e9b83  movzx   eax, ax
0x1800e9b86  or      eax, 80070000h
0x1800e9b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9b92  lea     rsi, WPP_GLOBAL_Control
0x1800e9b99  lea     rbp, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e9ba0  cmp     rcx, rsi
0x1800e9ba3  jz      short loc_1800E9BBF
0x1800e9ba5  test    byte ptr [rcx+1Ch], 4
0x1800e9ba9  jz      short loc_1800E9BBF
0x1800e9bab  mov     rcx, [rcx+10h]
0x1800e9baf  mov     edx, 1Ch
0x1800e9bb4  mov     r9d, eax
0x1800e9bb7  mov     r8, rbp
0x1800e9bba  call    WPP_SF_d
0x1800e9bbf  test    r14d, r14d
0x1800e9bc2  jz      short loc_1800E9C03
0x1800e9bc4  mov     rcx, [rdi+48h]; lpFileName
0x1800e9bc8  call    cs:__imp_GetFileAttributesW
0x1800e9bce  cmp     eax, 0FFFFFFFFh
0x1800e9bd1  jz      short loc_1800E9BD7
0x1800e9bd3  test    al, 10h
0x1800e9bd5  jz      short loc_1800E9C03
0x1800e9bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9bde  cmp     rcx, rsi
0x1800e9be1  jz      short loc_1800E9BFE
0x1800e9be3  test    byte ptr [rcx+1Ch], 4
0x1800e9be7  jz      short loc_1800E9BFE
0x1800e9be9  mov     r9, [rdi+48h]
0x1800e9bed  mov     edx, 1Dh
0x1800e9bf2  mov     rcx, [rcx+10h]
0x1800e9bf6  mov     r8, rbp
0x1800e9bf9  call    WPP_SF_S
0x1800e9bfe  mov     [rsp+188h+var_140], r12d
0x1800e9c03  xorps   xmm0, xmm0
0x1800e9c06  lea     rcx, [rsp+188h+pguid]; pguid
0x1800e9c0b  movups  xmmword ptr [rsp+188h+pguid.Data1], xmm0
0x1800e9c10  call    cs:__imp_CoCreateGuid
0x1800e9c16  mov     ebx, eax
0x1800e9c18  test    eax, eax
0x1800e9c1a  js      loc_1800EA035
0x1800e9c20  lea     r14, [rdi+98h]
0x1800e9c27  mov     rdx, r14; lplpsz
0x1800e9c2a  lea     rcx, [rsp+188h+pguid]; rclsid
0x1800e9c2f  call    cs:__imp_StringFromCLSID
0x1800e9c35  mov     ebx, eax
0x1800e9c37  test    eax, eax
0x1800e9c39  js      loc_1800EA035
0x1800e9c3f  mov     rdx, [r14]; szInstanceName
0x1800e9c42  lea     rcx, [rdi+78h]; pinstance
0x1800e9c46  xor     r9d, r9d; grbit
0x1800e9c49  xor     r8d, r8d; szDisplayName
0x1800e9c4c  call    cs:__imp_JetCreateInstance2W
0x1800e9c52  mov     ecx, eax; int
0x1800e9c54  call    ?ResultFromJetError@@YAJJ@Z; ResultFromJetError(long)
0x1800e9c59  mov     ebx, eax
0x1800e9c5b  test    eax, eax
0x1800e9c5d  jns     short loc_1800E9C80
0x1800e9c5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9c66  cmp     rcx, rsi
0x1800e9c69  jz      loc_1800EA035
0x1800e9c6f  test    byte ptr [rcx+1Ch], 1
0x1800e9c73  jz      loc_1800EA035
0x1800e9c79  mov     edx, 1Eh
0x1800e9c7e  jmp     short loc_1800E9CBA
0x1800e9c80  mov     r9, [rdi+60h]; unsigned __int16 *
0x1800e9c84  mov     r8d, r13d; int
0x1800e9c87  mov     rdx, [rdi+50h]; unsigned __int16 *
0x1800e9c8b  mov     rcx, rdi; this
0x1800e9c8e  call    ?SetEseInstanceParameters@CDbOperationManager@@AEAAJPEBGH0@Z; CDbOperationManager::SetEseInstanceParameters(ushort const *,int,ushort const *)
0x1800e9c93  xor     r13d, r13d
0x1800e9c96  mov     ebx, eax
0x1800e9c98  test    eax, eax
0x1800e9c9a  jns     short loc_1800E9CD3
0x1800e9c9c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9ca3  cmp     rcx, rsi
0x1800e9ca6  jz      loc_1800EA035
0x1800e9cac  test    byte ptr [rcx+1Ch], 1
0x1800e9cb0  jz      loc_1800EA035
0x1800e9cb6  lea     edx, [r13+1Fh]
0x1800e9cba  mov     r9, [rdi+48h]
0x1800e9cbe  mov     r8, rbp
0x1800e9cc1  mov     [rsp+188h+dwCreationDisposition], eax
0x1800e9cc5  mov     rcx, [rcx+10h]
0x1800e9cc9  call    WPP_SF_Sd
0x1800e9cce  jmp     loc_1800EA035
0x1800e9cd3  mov     rdx, [rdi+48h]; unsigned __int16 *
0x1800e9cd7  mov     rcx, rdi; this
0x1800e9cda  call    ?InitializeEseInstance@CDbOperationManager@@AEAAJPEBG@Z; CDbOperationManager::InitializeEseInstance(ushort const *)
0x1800e9cdf  mov     ebx, eax
0x1800e9ce1  test    eax, eax
0x1800e9ce3  jns     short loc_1800E9CFE
0x1800e9ce5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9cec  cmp     rcx, rsi
0x1800e9cef  jz      short loc_1800E9D54
0x1800e9cf1  test    byte ptr [rcx+1Ch], 1
0x1800e9cf5  jz      short loc_1800E9D54
0x1800e9cf7  mov     edx, 20h ; ' '
0x1800e9cfc  jmp     short loc_1800E9D40
0x1800e9cfe  mov     rcx, [rdi+78h]; instance
0x1800e9d02  lea     r14, [rdi+80h]
0x1800e9d09  mov     rdx, r14; psesid
0x1800e9d0c  xor     r9d, r9d; szPassword
0x1800e9d0f  xor     r8d, r8d; szUserName
0x1800e9d12  call    cs:__imp_JetBeginSessionW
0x1800e9d18  mov     ecx, eax; int
0x1800e9d1a  call    ?ResultFromJetError@@YAJJ@Z; ResultFromJetError(long)
0x1800e9d1f  mov     ebx, eax
0x1800e9d21  test    eax, eax
0x1800e9d23  jns     loc_1800E9DB9
0x1800e9d29  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9d30  cmp     rcx, rsi
0x1800e9d33  jz      short loc_1800E9D54
0x1800e9d35  test    byte ptr [rcx+1Ch], 1
0x1800e9d39  jz      short loc_1800E9D54
0x1800e9d3b  mov     edx, 21h ; '!'
0x1800e9d40  mov     r9, [rdi+48h]
0x1800e9d44  mov     r8, rbp
0x1800e9d47  mov     rcx, [rcx+10h]
0x1800e9d4b  mov     [rsp+188h+dwCreationDisposition], eax
0x1800e9d4f  call    WPP_SF_Sd
0x1800e9d54  mov     [rsp+188h+var_148], r13d
0x1800e9d59  mov     ecx, 0FFFFFBC5h; int
0x1800e9d5e  call    ?ResultFromJetError@@YAJJ@Z; ResultFromJetError(long)
0x1800e9d63  cmp     ebx, eax
0x1800e9d65  jz      loc_1800EA030
0x1800e9d6b  mov     ecx, 0FFFFFBC4h; int
0x1800e9d70  call    ?ResultFromJetError@@YAJJ@Z; ResultFromJetError(long)
0x1800e9d75  cmp     ebx, eax
0x1800e9d77  jz      loc_1800EA030
0x1800e9d7d  lea     r8, [rsp+188h+var_148]; int *
0x1800e9d82  mov     edx, ebx; int
0x1800e9d84  mov     rcx, rdi; this
0x1800e9d87  call    ?IsFatalJetError@CDbOperationManager@@AEAAHJPEAH@Z; CDbOperationManager::IsFatalJetError(long,int *)
0x1800e9d8c  test    eax, eax
0x1800e9d8e  jz      loc_1800EA035
0x1800e9d94  cmp     [rsp+188h+var_148], r13d
0x1800e9d99  jz      loc_1800E9FF2
0x1800e9d9f  cmp     [rdi+28h], r13d
0x1800e9da3  jnz     short loc_1800E9DAF
0x1800e9da5  mov     dword ptr [rdi+28h], 1
0x1800e9dac  mov     [rdi+34h], ebx
0x1800e9daf  mov     ebx, 80041289h
0x1800e9db4  jmp     loc_1800EA035
0x1800e9db9  cmp     r15d, 2
0x1800e9dbd  jnz     short loc_1800E9E20
0x1800e9dbf  mov     rdx, [rdi+48h]; unsigned __int16 *
0x1800e9dc3  lea     rax, [rdi+88h]
0x1800e9dca  mov     r9d, 200h; unsigned int
0x1800e9dd0  mov     qword ptr [rsp+188h+dwCreationDisposition], rax; struct JET_DBINFO *
0x1800e9dd5  mov     rcx, r14; this
0x1800e9dd8  call    ?CreateDatabase@CJetSession@@QEAAJPEBGKKPEAUJET_DBINFO@@@Z; CJetSession::CreateDatabase(ushort const *,ulong,ulong,JET_DBINFO *)
0x1800e9ddd  mov     ebx, eax
0x1800e9ddf  test    eax, eax
0x1800e9de1  jns     short loc_1800E9E0D
0x1800e9de3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9dea  cmp     rcx, rsi
0x1800e9ded  jz      short loc_1800E9E0D
0x1800e9def  test    byte ptr [rcx+1Ch], 1
0x1800e9df3  jz      short loc_1800E9E0D
0x1800e9df5  lea     edx, [r15+20h]
0x1800e9df9  mov     r9, [rdi+48h]
0x1800e9dfd  mov     r8, rbp
0x1800e9e00  mov     rcx, [rcx+10h]
0x1800e9e04  mov     [rsp+188h+dwCreationDisposition], ebx
0x1800e9e08  call    WPP_SF_Sd
0x1800e9e0d  mov     rcx, qword ptr [rsp+188h+var_148]
0x1800e9e12  mov     eax, ebx
0x1800e9e14  not     eax
0x1800e9e16  shr     eax, 1Fh
0x1800e9e19  mov     [rcx], eax
0x1800e9e1b  jmp     loc_1800E9FA9
0x1800e9e20  lea     eax, [r15-3]
0x1800e9e24  cmp     eax, 1
0x1800e9e27  ja      loc_1800E9FA9
0x1800e9e2d  mov     rdx, [rdi+48h]; szFilename
0x1800e9e31  xor     r9d, r9d; grbit
0x1800e9e34  mov     rcx, [r14]; sesid
0x1800e9e37  xor     r8d, r8d; cpgDatabaseSizeMax
0x1800e9e3a  call    cs:__imp_JetAttachDatabase2W
0x1800e9e40  mov     ecx, eax; int
0x1800e9e42  call    ?ResultFromJetError@@YAJJ@Z; ResultFromJetError(long)
0x1800e9e47  mov     ecx, 0FFFFF8EDh; int
0x1800e9e4c  mov     ebx, eax
0x1800e9e4e  call    ?ResultFromJetError@@YAJJ@Z; ResultFromJetError(long)
0x1800e9e53  mov     r12d, 80070002h
0x1800e9e59  cmp     ebx, eax
0x1800e9e5b  jnz     short loc_1800E9E62
0x1800e9e5d  mov     ebx, r12d
0x1800e9e60  jmp     short loc_1800E9E94
0x1800e9e62  mov     ecx, 0FFFFFB3Fh; int
0x1800e9e67  call    ?ResultFromJetError@@YAJJ@Z; ResultFromJetError(long)
0x1800e9e6c  cmp     ebx, eax
0x1800e9e6e  jnz     short loc_1800E9E77
0x1800e9e70  mov     ebx, 80070003h
0x1800e9e75  jmp     short loc_1800E9E94
0x1800e9e77  mov     ecx, 0FFFFFB41h; int
0x1800e9e7c  call    ?ResultFromJetError@@YAJJ@Z; ResultFromJetError(long)
0x1800e9e81  cmp     ebx, eax
0x1800e9e83  jnz     short loc_1800E9E8C
0x1800e9e85  mov     ebx, 80070020h
0x1800e9e8a  jmp     short loc_1800E9E94
0x1800e9e8c  test    ebx, ebx
0x1800e9e8e  jns     loc_1800E9F94
0x1800e9e94  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9e9b  cmp     rcx, rsi
0x1800e9e9e  jz      short loc_1800E9EBF
0x1800e9ea0  test    byte ptr [rcx+1Ch], 1
0x1800e9ea4  jz      short loc_1800E9EBF
0x1800e9ea6  mov     r9, [rdi+48h]
0x1800e9eaa  mov     edx, 23h ; '#'
0x1800e9eaf  mov     rcx, [rcx+10h]
0x1800e9eb3  mov     r8, rbp
0x1800e9eb6  mov     [rsp+188h+dwCreationDisposition], ebx
0x1800e9eba  call    WPP_SF_Sd
0x1800e9ebf  mov     ecx, 0FFFFFDDAh; int
0x1800e9ec4  call    ?ResultFromJetError@@YAJJ@Z; ResultFromJetError(long)
0x1800e9ec9  cmp     ebx, eax
0x1800e9ecb  jnz     short loc_1800E9F41
0x1800e9ecd  mov     r14d, 0D8h
0x1800e9ed3  lea     rcx, [rsp+188h+pvResult]; void *
0x1800e9ed8  mov     r8d, r14d; Size
0x1800e9edb  xor     edx, edx; Val
0x1800e9edd  call    memset_0
0x1800e9ee2  mov     rcx, [rdi+48h]; szDatabaseName
0x1800e9ee6  lea     rdx, [rsp+188h+pvResult]; pvResult
0x1800e9eeb  mov     r9d, 0Eh; InfoLevel
0x1800e9ef1  mov     r8d, r14d; cbMax
0x1800e9ef4  call    cs:__imp_JetGetDatabaseFileInfoW
  ... truncated ...
```
