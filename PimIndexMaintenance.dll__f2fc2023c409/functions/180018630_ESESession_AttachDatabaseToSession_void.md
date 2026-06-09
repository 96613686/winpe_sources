# ESESession::_AttachDatabaseToSession(void)

- ea: `0x180018630`
- end: `0x18001876f`
- name: `?_AttachDatabaseToSession@ESESession@@AEAAJXZ`
- size: `319`
- prototype: `__int64 __fastcall(ESESession *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018e18`

## callees

- `0x180002da8`
- `0x180010638`
- `0x18001134c`
- `0x180016860`
- `0x1800177b8`
- `0x180017d74`
- `0x180018630`
- `0x180020fe4`

## import_xrefs

- `ESENT!JetCreateDatabaseW` at `0x18001871c`
- `ESENT!JetCreateDatabaseW` at `0x18001871c`
- `UserDataPlatformHelperUtil!DefaultMakeHresultFromJetError` at `0x18001868e`
- `UserDataPlatformHelperUtil!DefaultMakeHresultFromJetError` at `0x1800186a1`
- `UserDataPlatformHelperUtil!DefaultMakeHresultFromJetError` at `0x18001868e`
- `UserDataPlatformHelperUtil!DefaultMakeHresultFromJetError` at `0x1800186a1`

## string_xrefs

- `0x1800186d5`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::_AttachDatabaseToSession(ESESession *this)
{
  int HresultFromJetError; // eax
  ESEDataSource *v3; // rcx
  int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  const unsigned __int16 *DatabasePath; // rax
  ESEDataSource *v8; // rcx
  const unsigned __int16 *v9; // rax
  ESEDataSource *v10; // rcx
  __int64 v11; // rcx
  const WCHAR *v12; // rax
  JET_ERR DatabaseW; // eax
  __int64 v15; // [rsp+30h] [rbp-28h] BYREF
  int v16; // [rsp+38h] [rbp-20h]
  char *v17; // [rsp+40h] [rbp-18h]

  v15 = *((_QWORD *)this + 7);
  v16 = 0;
  v17 = (char *)this + 64;
  HresultFromJetError = auto_SessionContext::SetContext((auto_SessionContext *)&v15);
  v4 = HresultFromJetError;
  if ( HresultFromJetError >= 0 )
  {
    DatabasePath = ESEDataSource::GetDatabasePath(v3);
    v4 = CommsESE_JetAttachDatabaseW(*((_QWORD *)this + 7), DatabasePath, 0);
    if ( v4 != (unsigned int)DefaultMakeHresultFromJetError(1007) )
    {
      if ( v4 == (unsigned int)DefaultMakeHresultFromJetError(4294965882LL) )
      {
        v9 = ESEDataSource::GetDatabasePath(v8);
        HresultFromJetError = CommsESE_JetAttachDatabaseW(*((_QWORD *)this + 7), v9, 0x10u);
        v4 = HresultFromJetError;
        v6 = 1;
        if ( HresultFromJetError < 0 )
        {
          v5 = 1277;
          goto LABEL_8;
        }
        HresultFromJetError = ESEDataSource::SetRebuildUnicodeIndexesKey(v10, 1);
        v4 = HresultFromJetError;
        if ( HresultFromJetError < 0 )
        {
          v5 = 1281;
          goto LABEL_3;
        }
      }
      else if ( v4 == -2147024894 )
      {
        v12 = ESEDataSource::GetDatabasePath(v8);
        DatabaseW = JetCreateDatabaseW(*((_QWORD *)this + 7), v12, 0, (JET_DBID *)this + 6, 0);
        if ( DatabaseW < 0 )
        {
          HresultFromJetError = MakeHresultFromJetError(DatabaseW);
          v4 = HresultFromJetError;
          v5 = 1290;
          v6 = 0;
          goto LABEL_8;
        }
      }
      else if ( v4 < 0 )
      {
        v5 = 1295;
        v6 = 1;
        v11 = (unsigned int)v4;
        goto LABEL_9;
      }
      *((_DWORD *)this + 90) = 1;
    }
    v4 = 0;
    goto LABEL_19;
  }
  v5 = 1258;
LABEL_3:
  v6 = 1;
LABEL_8:
  v11 = (unsigned int)HresultFromJetError;
LABEL_9:
  Log_HREvent(
    v11,
    v6,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
    v5);
LABEL_19:
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180018630  mov     r11, rsp
0x180018633  mov     [r11+8], rbx
0x180018637  push    rsi
0x180018638  sub     rsp, 50h
0x18001863c  mov     rax, [rcx+38h]
0x180018640  mov     rsi, rcx
0x180018643  mov     [r11-28h], rax
0x180018647  lea     rax, [rcx+40h]
0x18001864b  mov     [rsp+58h+var_20], 0
0x180018653  lea     rcx, [r11-28h]; this
0x180018657  mov     [r11-18h], rax
0x18001865b  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x180018660  mov     ebx, eax
0x180018662  test    eax, eax
0x180018664  jns     short loc_180018673
0x180018666  mov     r9d, 4EAh
0x18001866c  mov     edx, 1
0x180018671  jmp     short loc_1800186D3
0x180018673  call    ?GetDatabasePath@ESEDataSource@@QEAAQEBGXZ; ESEDataSource::GetDatabasePath(void)
0x180018678  mov     rcx, [rsi+38h]; unsigned __int64
0x18001867c  xor     r8d, r8d; unsigned int
0x18001867f  mov     rdx, rax; unsigned __int16 *
0x180018682  call    ?CommsESE_JetAttachDatabaseW@@YAJ_KPEBGK@Z; CommsESE_JetAttachDatabaseW(unsigned __int64,ushort const *,ulong)
0x180018687  mov     ecx, 3EFh
0x18001868c  mov     ebx, eax
0x18001868e  call    cs:__imp_DefaultMakeHresultFromJetError
0x180018694  cmp     ebx, eax
0x180018696  jz      loc_180018756
0x18001869c  mov     ecx, 0FFFFFA7Ah
0x1800186a1  call    cs:__imp_DefaultMakeHresultFromJetError
0x1800186a7  cmp     ebx, eax
0x1800186a9  jnz     short loc_1800186F9
0x1800186ab  call    ?GetDatabasePath@ESEDataSource@@QEAAQEBGXZ; ESEDataSource::GetDatabasePath(void)
0x1800186b0  mov     rcx, [rsi+38h]; unsigned __int64
0x1800186b4  mov     r8d, 10h; unsigned int
0x1800186ba  mov     rdx, rax; unsigned __int16 *
0x1800186bd  call    ?CommsESE_JetAttachDatabaseW@@YAJ_KPEBGK@Z; CommsESE_JetAttachDatabaseW(unsigned __int64,ushort const *,ulong)
0x1800186c2  mov     ebx, eax
0x1800186c4  mov     edx, 1; int
0x1800186c9  test    eax, eax
0x1800186cb  jns     short loc_1800186E3
0x1800186cd  mov     r9d, 4FDh
0x1800186d3  mov     ecx, eax
0x1800186d5  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800186dc  call    Log_HREvent
0x1800186e1  jmp     short loc_180018758
0x1800186e3  call    ?SetRebuildUnicodeIndexesKey@ESEDataSource@@QEAAJH@Z; ESEDataSource::SetRebuildUnicodeIndexesKey(int)
0x1800186e8  mov     ebx, eax
0x1800186ea  test    eax, eax
0x1800186ec  jns     short loc_18001874C
0x1800186ee  mov     r9d, 501h
0x1800186f4  jmp     loc_18001866C
0x1800186f9  cmp     ebx, 80070002h
0x1800186ff  jnz     short loc_180018739
0x180018701  call    ?GetDatabasePath@ESEDataSource@@QEAAQEBGXZ; ESEDataSource::GetDatabasePath(void)
0x180018706  mov     rcx, [rsi+38h]; sesid
0x18001870a  lea     r9, [rsi+18h]; pdbid
0x18001870e  xor     r8d, r8d; szConnect
0x180018711  mov     [rsp+58h+grbit], 0; grbit
0x180018719  mov     rdx, rax; szFilename
0x18001871c  call    cs:__imp_JetCreateDatabaseW
0x180018722  test    eax, eax
0x180018724  jns     short loc_18001874C
0x180018726  mov     ecx, eax; int
0x180018728  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18001872d  mov     ebx, eax
0x18001872f  mov     r9d, 50Ah
0x180018735  xor     edx, edx
0x180018737  jmp     short loc_1800186D3
0x180018739  test    ebx, ebx
0x18001873b  jns     short loc_18001874C
0x18001873d  mov     r9d, 50Fh
0x180018743  mov     edx, 1
0x180018748  mov     ecx, ebx
0x18001874a  jmp     short loc_1800186D5
0x18001874c  mov     dword ptr [rsi+168h], 1
0x180018756  xor     ebx, ebx
0x180018758  lea     rcx, [rsp+58h+var_28]; this
0x18001875d  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x180018762  mov     eax, ebx
0x180018764  mov     rbx, [rsp+58h+arg_0]
0x180018769  add     rsp, 50h
0x18001876d  pop     rsi
0x18001876e  retn
```
