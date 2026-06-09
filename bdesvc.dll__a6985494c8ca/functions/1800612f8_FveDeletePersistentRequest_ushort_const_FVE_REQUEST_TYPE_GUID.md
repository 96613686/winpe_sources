# FveDeletePersistentRequest(ushort const *,_FVE_REQUEST_TYPE,_GUID)

- ea: `0x1800612f8`
- end: `0x180061623`
- name: `?FveDeletePersistentRequest@@YAJPEBGW4_FVE_REQUEST_TYPE@@U_GUID@@@Z`
- size: `811`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct _GUID *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180061230`
- `0x180065400`
- `0x180065bd8`

## callees

- `0x180001fe8`
- `0x180002e04`
- `0x180009f30`
- `0x180009f60`
- `0x18000b3d0`
- `0x18000be60`
- `0x180025ed4`
- `0x18002f28c`
- `0x180034070`
- `0x180034d28`
- `0x180060bb4`
- `0x1800612f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800614dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800614dd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800614c6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800614c6`

## string_xrefs

- `0x180061433`: `MakeSystemVolumeInformationPath`
- `0x18006147f`: `BuildPersistentRequestFilePath`
- `0x1800614d6`: `DeleteFileW`

## pseudocode

```c
__int64 __fastcall FveDeletePersistentRequest(const unsigned __int16 *a1, unsigned int a2, struct _GUID *a3)
{
  PVOID *v6; // rcx
  signed int v7; // ebx
  __int64 v8; // rdx
  unsigned int FolderName; // eax
  unsigned int v10; // r9d
  unsigned int SystemVolumeInformationPath; // eax
  unsigned int v12; // r9d
  unsigned int v13; // eax
  signed int LastError; // eax
  __int64 v15; // rcx
  struct _GUID v17; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[32]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v19[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v20[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR FileName[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(FileName, 0, 0x208u);
  memset_0(v20, 0, 0x208u);
  memset_0(v19, 0, 0x208u);
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    FolderName = FvePersistentRequest::GetFolderName(a2, v20);
    v7 = FolderName;
    if ( !FolderName )
      goto LABEL_27;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, FolderName);
    if ( v7 >= 0 )
    {
LABEL_27:
      SystemVolumeInformationPath = MakeSystemVolumeInformationPath(a1, v20, v19, v10);
      v7 = SystemVolumeInformationPath;
      if ( !SystemVolumeInformationPath )
        goto LABEL_40;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          157,
          &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
          SystemVolumeInformationPath);
      if ( v7 >= 0 )
      {
LABEL_40:
        v17 = *a3;
        v13 = FvePersistentRequest::BuildPersistentRequestFilePath(v19, &v17, FileName, v12);
        v7 = v13;
        if ( !v13 )
          goto LABEL_41;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v13);
        if ( v7 >= 0 )
        {
LABEL_41:
          if ( !DeleteFileW(FileName) )
          {
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
            v6 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              v8 = 159;
              goto LABEL_29;
            }
          }
        }
      }
    }
  }
  else
  {
    v7 = -2147024809;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 )
    {
      v8 = 155;
LABEL_29:
      WPP_SF_d(v6[2], v8, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, (unsigned int)v7);
    }
  }
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v18,
    &g_hBitLockerKeyRollProvider,
    &g_bitLockerKeyRollProviderInitLock,
    &g_bitLockerKeyRollProviderRefCount);
  if ( v7 < 0 && (unsigned int)dword_18009A3B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A3B8, 0x400000000000LL) )
  {
    *(_QWORD *)&v17.Data1 = v19;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v15,
      word_18008DF3A);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      160,
      &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
      (unsigned int)v7);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar((TelemetryProviderRegistrar *)v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800612f8  push    rbp
0x1800612fa  push    rbx
0x1800612fb  push    rsi
0x1800612fc  push    r12
0x1800612fe  push    r13
0x180061300  push    r14
0x180061302  push    r15
0x180061304  lea     rbp, [rsp-5E0h]
0x18006130c  sub     rsp, 6E0h
0x180061313  mov     rax, cs:__security_cookie
0x18006131a  xor     rax, rsp
0x18006131d  mov     [rbp+610h+var_40], rax
0x180061324  mov     r15, r8
0x180061327  mov     r12d, edx
0x18006132a  mov     r14, rcx
0x18006132d  mov     ebx, 208h
0x180061332  mov     r8d, ebx; Size
0x180061335  lea     rcx, [rbp+610h+FileName]; void *
0x18006133c  xor     edx, edx; Val
0x18006133e  call    memset_0
0x180061343  mov     r8d, ebx; Size
0x180061346  lea     rcx, [rbp+610h+var_460]; void *
0x18006134d  xor     edx, edx; Val
0x18006134f  call    memset_0
0x180061354  mov     r8d, ebx; Size
0x180061357  lea     rcx, [rbp+610h+var_670]; void *
0x18006135b  xor     edx, edx; Val
0x18006135d  call    memset_0
0x180061362  mov     rcx, cs:WPP_GLOBAL_Control
0x180061369  lea     r13, WPP_GLOBAL_Control
0x180061370  cmp     rcx, r13
0x180061373  jz      short loc_180061397
0x180061375  test    byte ptr [rcx+1Ch], 20h
0x180061379  jz      short loc_180061397
0x18006137b  mov     rcx, [rcx+10h]
0x18006137f  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180061386  mov     edx, 9Ah
0x18006138b  call    WPP_SF_
0x180061390  mov     rcx, cs:WPP_GLOBAL_Control
0x180061397  test    r14, r14
0x18006139a  jnz     short loc_1800613C5
0x18006139c  lea     rsi, aInvalidarg; "INVALIDARG"
0x1800613a3  mov     ebx, 80070057h
0x1800613a8  cmp     rcx, r13
0x1800613ab  jz      loc_180061522
0x1800613b1  test    byte ptr [rcx+1Ch], 40h
0x1800613b5  jz      loc_180061522
0x1800613bb  mov     edx, 9Bh
0x1800613c0  jmp     loc_18006150F
0x1800613c5  lea     rdx, [rbp+610h+var_460]
0x1800613cc  mov     ecx, r12d
0x1800613cf  call    ?GetFolderName@FvePersistentRequest@@SAJW4_FVE_REQUEST_TYPE@@PEAGK@Z; FvePersistentRequest::GetFolderName(_FVE_REQUEST_TYPE,ushort *,ulong)
0x1800613d4  mov     ebx, eax
0x1800613d6  test    eax, eax
0x1800613d8  jz      short loc_180061413
0x1800613da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800613e1  lea     rsi, aGetfoldername; "GetFolderName"
0x1800613e8  cmp     rcx, r13
0x1800613eb  jz      short loc_18006140B
0x1800613ed  test    byte ptr [rcx+1Ch], 40h
0x1800613f1  jz      short loc_18006140B
0x1800613f3  mov     rcx, [rcx+10h]
0x1800613f7  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800613fe  mov     edx, 9Ch
0x180061403  mov     r9d, eax
0x180061406  call    WPP_SF_d
0x18006140b  test    ebx, ebx
0x18006140d  js      loc_180061522
0x180061413  lea     r8, [rbp+610h+var_670]; unsigned __int16 *
0x180061417  mov     rcx, r14; unsigned __int16 *
0x18006141a  lea     rdx, [rbp+610h+var_460]; unsigned __int16 *
0x180061421  call    ?MakeSystemVolumeInformationPath@@YAJPEBG0PEAGK@Z; MakeSystemVolumeInformationPath(ushort const *,ushort const *,ushort *,ulong)
0x180061426  mov     ebx, eax
0x180061428  test    eax, eax
0x18006142a  jz      short loc_180061465
0x18006142c  mov     rcx, cs:WPP_GLOBAL_Control
0x180061433  lea     rsi, aMakesystemvolu; "MakeSystemVolumeInformationPath"
0x18006143a  cmp     rcx, r13
0x18006143d  jz      short loc_18006145D
0x18006143f  test    byte ptr [rcx+1Ch], 40h
0x180061443  jz      short loc_18006145D
0x180061445  mov     rcx, [rcx+10h]
0x180061449  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180061450  mov     edx, 9Dh
0x180061455  mov     r9d, eax
0x180061458  call    WPP_SF_d
0x18006145d  test    ebx, ebx
0x18006145f  js      loc_180061522
0x180061465  movups  xmm0, xmmword ptr [r15]
0x180061469  lea     r8, [rbp+610h+FileName]; unsigned __int16 *
0x180061470  lea     rdx, [rsp+710h+var_6A0]; struct _GUID
0x180061475  lea     rcx, [rbp+610h+var_670]; unsigned __int16 *
0x180061479  movdqu  xmmword ptr [rsp+710h+var_6A0.Data1], xmm0
0x18006147f  lea     rsi, aBuildpersisten; "BuildPersistentRequestFilePath"
0x180061486  call    ?BuildPersistentRequestFilePath@FvePersistentRequest@@SAJPEBGU_GUID@@PEAGK@Z; FvePersistentRequest::BuildPersistentRequestFilePath(ushort const *,_GUID,ushort *,ulong)
0x18006148b  mov     ebx, eax
0x18006148d  test    eax, eax
0x18006148f  jz      short loc_1800614BF
0x180061491  mov     rcx, cs:WPP_GLOBAL_Control
0x180061498  cmp     rcx, r13
0x18006149b  jz      short loc_1800614BB
0x18006149d  test    byte ptr [rcx+1Ch], 40h
0x1800614a1  jz      short loc_1800614BB
0x1800614a3  mov     rcx, [rcx+10h]
0x1800614a7  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800614ae  mov     edx, 9Eh
0x1800614b3  mov     r9d, eax
0x1800614b6  call    WPP_SF_d
0x1800614bb  test    ebx, ebx
0x1800614bd  js      short loc_180061522
0x1800614bf  lea     rcx, [rbp+610h+FileName]; lpFileName
0x1800614c6  call    cs:__imp_DeleteFileW
0x1800614cd  nop     dword ptr [rax+rax+00h]
0x1800614d2  test    eax, eax
0x1800614d4  jnz     short loc_180061522
0x1800614d6  lea     rsi, aDeletefilew; "DeleteFileW"
0x1800614dd  call    cs:__imp_GetLastError
0x1800614e4  nop     dword ptr [rax+rax+00h]
0x1800614e9  mov     ebx, eax
0x1800614eb  test    eax, eax
0x1800614ed  jle     short loc_1800614F8
0x1800614ef  movzx   ebx, ax
0x1800614f2  or      ebx, 80070000h
0x1800614f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800614ff  cmp     rcx, r13
0x180061502  jz      short loc_180061522
0x180061504  test    byte ptr [rcx+1Ch], 40h
0x180061508  jz      short loc_180061522
0x18006150a  mov     edx, 9Fh
0x18006150f  mov     rcx, [rcx+10h]
0x180061513  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x18006151a  mov     r9d, ebx
0x18006151d  call    WPP_SF_d
0x180061522  lea     r9, ?g_bitLockerKeyRollProviderRefCount@@3JC; volatile int *
0x180061529  lea     r8, ?g_bitLockerKeyRollProviderInitLock@@3U_RTL_SRWLOCK@@A; struct _RTL_SRWLOCK *
0x180061530  lea     rdx, g_hBitLockerKeyRollProvider; struct _tlgProvider_t **
0x180061537  lea     rcx, [rbp+610h+var_690]; this
0x18006153b  call    ??0TelemetryProviderRegistrar@@QEAA@PEBQEBU_tlgProvider_t@@PEAU_RTL_SRWLOCK@@PECJ@Z; TelemetryProviderRegistrar::TelemetryProviderRegistrar(_tlgProvider_t const * const *,_RTL_SRWLOCK *,long volatile *)
0x180061540  test    ebx, ebx
0x180061542  jns     loc_1800615CB
0x180061548  mov     eax, cs:dword_18009A3B8
0x18006154e  cmp     eax, 5
0x180061551  jbe     short loc_1800615CB
0x180061553  mov     rdx, 400000000000h
0x18006155d  lea     rcx, dword_18009A3B8
0x180061564  call    _tlgKeywordOn
0x180061569  test    al, al
0x18006156b  jz      short loc_1800615CB
0x18006156d  lea     rax, [rbp+610h+var_670]
0x180061571  mov     [rsp+710h+var_6B8], 1000000h
0x18006157a  mov     qword ptr [rsp+710h+var_6A0.Data1], rax
0x18006157f  lea     rdx, word_18008DF3A
0x180061586  lea     rax, [rsp+710h+var_6B8]
0x18006158b  mov     [rsp+710h+var_6B0], rsi
0x180061590  mov     [rsp+710h+var_6D0], rax
0x180061595  lea     rax, [rsp+710h+var_6B0]
0x18006159a  mov     [rsp+710h+var_6D8], rax
0x18006159f  lea     rax, [rsp+710h+var_6C0]
0x1800615a4  mov     [rsp+710h+var_6E0], rax
0x1800615a9  lea     rax, [rsp+710h+var_6A0]
0x1800615ae  mov     [rsp+710h+var_6E8], rax
0x1800615b3  lea     rax, [rsp+710h+var_6BC]
0x1800615b8  mov     [rsp+710h+var_6F0], rax
0x1800615bd  mov     [rsp+710h+var_6C0], r12d
0x1800615c2  mov     [rsp+710h+var_6BC], ebx
0x1800615c6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@34AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800615cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800615d2  cmp     rcx, r13
0x1800615d5  jz      short loc_1800615F5
0x1800615d7  test    byte ptr [rcx+1Ch], 20h
0x1800615db  jz      short loc_1800615F5
0x1800615dd  mov     rcx, [rcx+10h]
0x1800615e1  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800615e8  mov     edx, 0A0h
0x1800615ed  mov     r9d, ebx
0x1800615f0  call    WPP_SF_d
0x1800615f5  lea     rcx, [rbp+610h+var_690]; this
0x1800615f9  call    ??1TelemetryProviderRegistrar@@QEAA@XZ; TelemetryProviderRegistrar::~TelemetryProviderRegistrar(void)
0x1800615fe  mov     eax, ebx
0x180061600  mov     rcx, [rbp+610h+var_40]
0x180061607  xor     rcx, rsp; StackCookie
0x18006160a  call    __security_check_cookie
0x18006160f  add     rsp, 6E0h
0x180061616  pop     r15
0x180061618  pop     r14
0x18006161a  pop     r13
0x18006161c  pop     r12
0x18006161e  pop     rsi
0x18006161f  pop     rbx
0x180061620  pop     rbp
0x180061621  retn
```
