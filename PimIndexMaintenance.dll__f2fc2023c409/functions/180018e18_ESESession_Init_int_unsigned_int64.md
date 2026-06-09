# ESESession::_Init(int,unsigned __int64)

- ea: `0x180018e18`
- end: `0x180018f52`
- name: `?_Init@ESESession@@AEAAJH_K@Z`
- size: `314`
- prototype: `__int64 __fastcall(ESESession *this, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x180016978`

## callees

- `0x180002da8`
- `0x180010638`
- `0x1800177b8`
- `0x180018630`
- `0x180018e18`
- `0x180018f58`

## import_xrefs

- `ESENT!JetBeginSessionA` at `0x180018e72`
- `ESENT!JetBeginSessionA` at `0x180018e72`
- `ESENT!JetOpenDatabaseW` at `0x180018ee6`
- `ESENT!JetOpenDatabaseW` at `0x180018ee6`

## string_xrefs

- `0x180018e41`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180018eaf`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180018efd`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::_Init(ESESession *this, int a2, __int64 a3)
{
  __int64 v5; // r9
  __int64 v6; // rdx
  unsigned int HresultFromJetError; // ebx
  __int64 v8; // rcx
  JET_SESID *v10; // rsi
  JET_ERR v11; // eax
  ESEDataSource *v12; // rcx
  int v13; // edi
  __int64 v14; // r9
  const WCHAR *DatabasePath; // rax
  JET_ERR v16; // eax

  if ( a3 == -1 )
  {
    v5 = 144;
    v6 = 0;
    HresultFromJetError = -2147024809;
LABEL_3:
    v8 = HresultFromJetError;
LABEL_4:
    Log_HREvent(
      v8,
      v6,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      v5);
    return HresultFromJetError;
  }
  *((_QWORD *)this + 1) = a3;
  v10 = (JET_SESID *)((char *)this + 56);
  *((_QWORD *)this + 43) = 0;
  v11 = JetBeginSessionA(*((_QWORD *)this + 1), (JET_SESID *)this + 7, 0, 0);
  if ( v11 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v11);
    v5 = 154;
    v6 = 0;
    v8 = HresultFromJetError;
    goto LABEL_4;
  }
  *((_DWORD *)this + 89) = a2;
  if ( a2 )
  {
    v13 = ESESession::_AttachDatabaseToSession(this);
    if ( v13 < 0 )
    {
      v14 = 160;
LABEL_10:
      Log_HREvent(
        (unsigned int)v13,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
        v14);
      return (unsigned int)v13;
    }
  }
  if ( *((_DWORD *)this + 6) == -1
    && (DatabasePath = ESEDataSource::GetDatabasePath(v12),
        v16 = JetOpenDatabaseW(*v10, DatabasePath, 0, (JET_DBID *)this + 6, 0),
        v16 < 0) )
  {
    v13 = MakeHresultFromJetError(v16);
    Log_HREvent(
      (unsigned int)v13,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      1316);
    if ( v13 < 0 )
    {
      v14 = 164;
      goto LABEL_10;
    }
  }
  else
  {
    *((_QWORD *)this + 2) = *v10;
  }
  HresultFromJetError = ESESession::_InitAllTables(this);
  if ( (HresultFromJetError & 0x80000000) != 0 )
  {
    v5 = 166;
    v6 = 1;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180018e18  mov     [rsp+arg_0], rbx
0x180018e1d  mov     [rsp+arg_8], rsi
0x180018e22  push    rdi
0x180018e23  sub     rsp, 30h
0x180018e27  mov     edi, edx
0x180018e29  mov     rbx, rcx
0x180018e2c  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180018e30  jnz     short loc_180018E54
0x180018e32  mov     r9d, 90h
0x180018e38  xor     edx, edx
0x180018e3a  mov     ebx, 80070057h
0x180018e3f  mov     ecx, ebx
0x180018e41  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018e48  call    Log_HREvent
0x180018e4d  mov     eax, ebx
0x180018e4f  jmp     loc_180018F42
0x180018e54  mov     [rcx+8], r8
0x180018e58  lea     rsi, [rcx+38h]
0x180018e5c  xor     eax, eax
0x180018e5e  xor     r9d, r9d; szPassword
0x180018e61  mov     [rcx+158h], rax
0x180018e68  xor     r8d, r8d; szUserName
0x180018e6b  mov     rcx, [rcx+8]; instance
0x180018e6f  mov     rdx, rsi; psesid
0x180018e72  call    cs:__imp_JetBeginSessionA
0x180018e78  test    eax, eax
0x180018e7a  jns     short loc_180018E91
0x180018e7c  mov     ecx, eax; int
0x180018e7e  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018e83  mov     ebx, eax
0x180018e85  mov     r9d, 9Ah
0x180018e8b  xor     edx, edx
0x180018e8d  mov     ecx, eax
0x180018e8f  jmp     short loc_180018E41
0x180018e91  mov     [rbx+164h], edi
0x180018e97  test    edi, edi
0x180018e99  jz      short loc_180018EC6
0x180018e9b  mov     rcx, rbx; this
0x180018e9e  call    ?_AttachDatabaseToSession@ESESession@@AEAAJXZ; ESESession::_AttachDatabaseToSession(void)
0x180018ea3  mov     edi, eax
0x180018ea5  test    eax, eax
0x180018ea7  jns     short loc_180018EC6
0x180018ea9  mov     r9d, 0A0h
0x180018eaf  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018eb6  mov     edx, 1
0x180018ebb  mov     ecx, edi
0x180018ebd  call    Log_HREvent
0x180018ec2  mov     eax, edi
0x180018ec4  jmp     short loc_180018F42
0x180018ec6  cmp     dword ptr [rbx+18h], 0FFFFFFFFh
0x180018eca  jnz     short loc_180018F1B
0x180018ecc  call    ?GetDatabasePath@ESEDataSource@@QEAAQEBGXZ; ESEDataSource::GetDatabasePath(void)
0x180018ed1  mov     rcx, [rsi]; sesid
0x180018ed4  lea     r9, [rbx+18h]; pdbid
0x180018ed8  xor     r8d, r8d; szConnect
0x180018edb  mov     [rsp+38h+grbit], 0; grbit
0x180018ee3  mov     rdx, rax; szFilename
0x180018ee6  call    cs:__imp_JetOpenDatabaseW
0x180018eec  test    eax, eax
0x180018eee  jns     short loc_180018F1B
0x180018ef0  mov     ecx, eax; int
0x180018ef2  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018ef7  mov     r9d, 524h
0x180018efd  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018f04  xor     edx, edx
0x180018f06  mov     ecx, eax
0x180018f08  mov     edi, eax
0x180018f0a  call    Log_HREvent
0x180018f0f  test    edi, edi
0x180018f11  jns     short loc_180018F22
0x180018f13  mov     r9d, 0A4h
0x180018f19  jmp     short loc_180018EAF
0x180018f1b  mov     rax, [rsi]
0x180018f1e  mov     [rbx+10h], rax
0x180018f22  mov     rcx, rbx; this
0x180018f25  call    ?_InitAllTables@ESESession@@AEAAJXZ; ESESession::_InitAllTables(void)
0x180018f2a  mov     ebx, eax
0x180018f2c  test    eax, eax
0x180018f2e  jns     short loc_180018F40
0x180018f30  mov     r9d, 0A6h
0x180018f36  mov     edx, 1
0x180018f3b  jmp     loc_180018E3F
0x180018f40  xor     eax, eax
0x180018f42  mov     rbx, [rsp+38h+arg_0]
0x180018f47  mov     rsi, [rsp+38h+arg_8]
0x180018f4c  add     rsp, 30h
0x180018f50  pop     rdi
0x180018f51  retn
```
