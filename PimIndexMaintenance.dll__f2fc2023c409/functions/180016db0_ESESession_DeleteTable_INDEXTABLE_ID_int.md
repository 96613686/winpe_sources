# ESESession::DeleteTable(_INDEXTABLE_ID,int)

- ea: `0x180016db0`
- end: `0x180016f55`
- name: `?DeleteTable@ESESession@@QEAAJW4_INDEXTABLE_ID@@H@Z`
- size: `421`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800134a0`
- `0x180016a70`

## callees

- `0x180002da8`
- `0x18000c800`
- `0x180010638`
- `0x180013678`
- `0x180013f14`
- `0x180016860`
- `0x1800168e8`
- `0x180016db0`
- `0x1800178b0`
- `0x180017d74`
- `0x180018778`

## import_xrefs

- `ESENT!JetDeleteTableA` at `0x180016eae`
- `ESENT!JetDeleteTableA` at `0x180016eae`

## string_xrefs

- `0x180016e8f`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x180016f2b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ScopedEndTransaction.h`
- `0x180016e2b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180016e68`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::DeleteTable(__int64 a1, __int64 a2, int a3)
{
  unsigned int v4; // esi
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  const char *v9; // r15
  int started; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  JET_ERR v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  int v18; // [rsp+30h] [rbp-38h] BYREF
  __int64 v19; // [rsp+38h] [rbp-30h]
  __int64 v20; // [rsp+40h] [rbp-28h] BYREF
  int v21; // [rsp+48h] [rbp-20h]
  __int64 v22; // [rsp+50h] [rbp-18h]

  v4 = a2;
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(a1, a2, "Deleting Table");
  v20 = *(_QWORD *)(a1 + 56);
  v22 = a1 + 64;
  v21 = 0;
  v6 = auto_SessionContext::SetContext((auto_SessionContext *)&v20);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 730;
LABEL_7:
    Log_HREvent(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      v8);
    goto LABEL_24;
  }
  v9 = *(const char **)GetIndexDataFromTableId(v4);
  v6 = ESESession::CloseTable(a1, v4);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 737;
    goto LABEL_7;
  }
  v18 = 0;
  v19 = a1;
  started = ScopedEndTransaction<ESESession>::StartTransaction(&v18);
  v7 = started;
  if ( started < 0 )
  {
    v11 = 743;
LABEL_10:
    v12 = 1;
    goto LABEL_11;
  }
  v14 = JetDeleteTableA(*(_QWORD *)(a1 + 56), *(_DWORD *)(a1 + 24), v9);
  v15 = 0x80000000LL;
  if ( (int)(v14 + 0x80000000) >= 0 && v14 != -1305 )
  {
    started = MakeHresultFromJetError(v14);
    v7 = started;
    v11 = 755;
    v12 = 0;
LABEL_11:
    Log_HREvent(
      (unsigned int)started,
      v12,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      v11);
    v13 = ScopedEndTransaction<ESESession>::EndTransaction(&v18, 0);
    if ( v13 < 0 )
      Log_HREvent(
        (unsigned int)v13,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
        57);
    goto LABEL_24;
  }
  if ( a3 )
  {
    started = ESESession::_CreateTable(a1, v4);
    v7 = started;
    if ( started < 0 )
    {
      v11 = 761;
      goto LABEL_10;
    }
  }
  LOBYTE(v15) = 1;
  started = ScopedEndTransaction<ESESession>::EndTransaction(&v18, v15);
  v7 = started;
  if ( started < 0 )
  {
    v11 = 764;
    goto LABEL_10;
  }
  v16 = ScopedEndTransaction<ESESession>::EndTransaction(&v18, 0);
  if ( v16 < 0 )
    Log_HREvent(
      (unsigned int)v16,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ScopedEndTransaction.h",
      57);
  v7 = 0;
LABEL_24:
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v20);
  return v7;
}

```

## disassembly

```asm
0x180016db0  push    rbp
0x180016db2  push    rbx
0x180016db3  push    rsi
0x180016db4  push    rdi
0x180016db5  push    r14
0x180016db7  push    r15
0x180016db9  mov     rbp, rsp
0x180016dbc  sub     rsp, 68h
0x180016dc0  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 80h
0x180016dc7  mov     r14d, r8d
0x180016dca  mov     esi, edx
0x180016dcc  mov     rdi, rcx
0x180016dcf  jz      short loc_180016DDD
0x180016dd1  lea     r8, aDeletingTable; "Deleting Table"
0x180016dd8  call    McTemplateU0s_EventWriteTransfer
0x180016ddd  mov     rax, [rdi+38h]
0x180016de1  lea     rcx, [rbp+var_28]; this
0x180016de5  mov     [rbp+var_28], rax
0x180016de9  lea     rax, [rdi+40h]
0x180016ded  mov     [rbp+var_18], rax
0x180016df1  mov     [rbp+var_20], 0
0x180016df8  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x180016dfd  mov     ebx, eax
0x180016dff  test    eax, eax
0x180016e01  jns     short loc_180016E0B
0x180016e03  mov     r9d, 2DAh
0x180016e09  jmp     short loc_180016E2B
0x180016e0b  mov     ecx, esi
0x180016e0d  call    ?GetIndexDataFromTableId@@YAPEBU_IndexSourceData@IndexedFiltering@@W4_INDEXTABLE_ID@@@Z; GetIndexDataFromTableId(_INDEXTABLE_ID)
0x180016e12  mov     edx, esi
0x180016e14  mov     rcx, rdi
0x180016e17  mov     r15, [rax]
0x180016e1a  call    ?CloseTable@ESESession@@QEAAJW4_INDEXTABLE_ID@@@Z; ESESession::CloseTable(_INDEXTABLE_ID)
0x180016e1f  mov     ebx, eax
0x180016e21  test    eax, eax
0x180016e23  jns     short loc_180016E43
0x180016e25  mov     r9d, 2E1h
0x180016e2b  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016e32  mov     edx, 1
0x180016e37  mov     ecx, eax
0x180016e39  call    Log_HREvent
0x180016e3e  jmp     loc_180016F3D
0x180016e43  lea     rcx, [rbp+var_38]
0x180016e47  mov     [rbp+var_38], 0
0x180016e4e  mov     [rbp+var_30], rdi
0x180016e52  call    ?StartTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJXZ; ScopedEndTransaction<ESESession>::StartTransaction(void)
0x180016e57  mov     ebx, eax
0x180016e59  test    eax, eax
0x180016e5b  jns     short loc_180016EA4
0x180016e5d  mov     r9d, 2E7h
0x180016e63  mov     edx, 1
0x180016e68  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016e6f  mov     ecx, eax
0x180016e71  call    Log_HREvent
0x180016e76  xor     edx, edx
0x180016e78  lea     rcx, [rbp+var_38]
0x180016e7c  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x180016e81  test    eax, eax
0x180016e83  jns     loc_180016F3D
0x180016e89  mov     r9d, 39h ; '9'
0x180016e8f  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016e96  xor     edx, edx
0x180016e98  mov     ecx, eax
0x180016e9a  call    Log_HREvent
0x180016e9f  jmp     loc_180016F3D
0x180016ea4  mov     edx, [rdi+18h]; dbid
0x180016ea7  mov     r8, r15; szTableName
0x180016eaa  mov     rcx, [rdi+38h]; sesid
0x180016eae  call    cs:__imp_JetDeleteTableA
0x180016eb4  mov     edx, 80000000h
0x180016eb9  lea     ecx, [rax+rdx]
0x180016ebc  test    edx, ecx
0x180016ebe  jnz     short loc_180016EDA
0x180016ec0  cmp     eax, 0FFFFFAE7h
0x180016ec5  jz      short loc_180016EDA
0x180016ec7  mov     ecx, eax; int
0x180016ec9  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180016ece  mov     ebx, eax
0x180016ed0  mov     r9d, 2F3h
0x180016ed6  xor     edx, edx
0x180016ed8  jmp     short loc_180016E68
0x180016eda  test    r14d, r14d
0x180016edd  jz      short loc_180016EFA
0x180016edf  mov     edx, esi
0x180016ee1  mov     rcx, rdi
0x180016ee4  call    ?_CreateTable@ESESession@@AEAAJW4_INDEXTABLE_ID@@@Z; ESESession::_CreateTable(_INDEXTABLE_ID)
0x180016ee9  mov     ebx, eax
0x180016eeb  test    eax, eax
0x180016eed  jns     short loc_180016EFA
0x180016eef  mov     r9d, 2F9h
0x180016ef5  jmp     loc_180016E63
0x180016efa  mov     dl, 1
0x180016efc  lea     rcx, [rbp+var_38]
0x180016f00  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x180016f05  mov     ebx, eax
0x180016f07  test    eax, eax
0x180016f09  jns     short loc_180016F16
0x180016f0b  mov     r9d, 2FCh
0x180016f11  jmp     loc_180016E63
0x180016f16  xor     edx, edx
0x180016f18  lea     rcx, [rbp+var_38]
0x180016f1c  call    ?EndTransaction@?$ScopedEndTransaction@VESESession@@@@QEAAJ_N@Z; ScopedEndTransaction<ESESession>::EndTransaction(bool)
0x180016f21  test    eax, eax
0x180016f23  jns     short loc_180016F3B
0x180016f25  mov     r9d, 39h ; '9'
0x180016f2b  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016f32  xor     edx, edx
0x180016f34  mov     ecx, eax
0x180016f36  call    Log_HREvent
0x180016f3b  xor     ebx, ebx
0x180016f3d  lea     rcx, [rbp+var_28]; this
0x180016f41  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x180016f46  mov     eax, ebx
0x180016f48  add     rsp, 68h
0x180016f4c  pop     r15
0x180016f4e  pop     r14
0x180016f50  pop     rdi
0x180016f51  pop     rsi
0x180016f52  pop     rbx
0x180016f53  pop     rbp
0x180016f54  retn
```
