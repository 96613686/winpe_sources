# ESESession::UpdateUnicodeIndexes(void)

- ea: `0x180017f74`
- end: `0x1800180bb`
- name: `?UpdateUnicodeIndexes@ESESession@@QEAAJXZ`
- size: `327`
- prototype: `__int64 __fastcall(ESESession *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x180011f70`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x180010638`
- `0x180016860`
- `0x1800179c8`
- `0x180017b04`
- `0x180017d74`
- `0x180017f74`
- `0x18001848c`

## import_xrefs

- `ESENT!JetDeleteIndexA` at `0x180018025`
- `ESENT!JetDeleteIndexA` at `0x180018025`

## string_xrefs

- `0x18001806b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180018089`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x18001800d`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\ESESession.h`

## pseudocode

```c
__int64 __fastcall ESESession::UpdateUnicodeIndexes(ESESession *this)
{
  int HresultFromJetError; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // rdx
  unsigned int i; // ebx
  int v7; // esi
  __int64 TableDefinitionFromTableId; // rbp
  const char *v9; // r14
  JET_ERR v10; // eax
  __int64 v11; // r9
  __int64 v13; // [rsp+30h] [rbp-58h] BYREF
  int v14; // [rsp+38h] [rbp-50h]
  char *v15; // [rsp+40h] [rbp-48h]

  v13 = *((_QWORD *)this + 7);
  v15 = (char *)this + 64;
  v14 = 0;
  HresultFromJetError = auto_SessionContext::SetContext((auto_SessionContext *)&v13);
  v3 = HresultFromJetError;
  if ( HresultFromJetError >= 0 )
  {
    for ( i = 0; i < 5; ++i )
    {
      v7 = ESESession::OpenTable((__int64)this, i);
      if ( v7 < 0 )
      {
        v11 = 850;
        goto LABEL_16;
      }
      TableDefinitionFromTableId = GetTableDefinitionFromTableId(i);
      v9 = *(const char **)(*(_QWORD *)(TableDefinitionFromTableId + 32) + 8LL);
      if ( *((_QWORD *)this + 6 * (int)i + 14) == -1 )
        Log_AssertionEvent(
          (int)i,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\ESESession.h",
          118);
      v10 = JetDeleteIndexA(*((_QWORD *)this + 7), *((_QWORD *)this + 6 * (int)i + 14), v9);
      if ( ((v10 + 0x80000000) & 0x80000000) == 0 && v10 != -1404 )
      {
        HresultFromJetError = MakeHresultFromJetError(v10);
        v3 = HresultFromJetError;
        v4 = 864;
        v5 = 0;
        goto LABEL_13;
      }
      v7 = ESESession::_AddIndex((__int64)this, i, *(_QWORD *)(*(_QWORD *)(TableDefinitionFromTableId + 32) + 8LL));
      if ( v7 < 0 )
      {
        v11 = 870;
LABEL_16:
        Log_HREvent(
          (unsigned int)v7,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
          v11);
        v3 = v7;
        goto LABEL_18;
      }
    }
    v3 = 0;
  }
  else
  {
    v4 = 844;
    v5 = 1;
LABEL_13:
    Log_HREvent(
      (unsigned int)HresultFromJetError,
      v5,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      v4);
  }
LABEL_18:
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v13);
  return v3;
}

```

## disassembly

```asm
0x180017f74  push    rbx
0x180017f76  push    rbp
0x180017f77  push    rsi
0x180017f78  push    rdi
0x180017f79  push    r14
0x180017f7b  push    r15
0x180017f7d  sub     rsp, 58h
0x180017f81  mov     rax, [rcx+38h]
0x180017f85  mov     rdi, rcx
0x180017f88  mov     [rsp+88h+var_58], rax
0x180017f8d  lea     rax, [rcx+40h]
0x180017f91  lea     rcx, [rsp+88h+var_58]; this
0x180017f96  mov     [rsp+88h+var_48], rax
0x180017f9b  mov     [rsp+88h+var_50], 0
0x180017fa3  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x180017fa8  mov     ebx, eax
0x180017faa  test    eax, eax
0x180017fac  jns     short loc_180017FBE
0x180017fae  mov     r9d, 34Ch
0x180017fb4  mov     edx, 1
0x180017fb9  jmp     loc_18001806B
0x180017fbe  xor     ebx, ebx
0x180017fc0  mov     r15d, 80000000h
0x180017fc6  cmp     ebx, 5
0x180017fc9  jnb     loc_1800180A0
0x180017fcf  mov     edx, ebx
0x180017fd1  mov     rcx, rdi
0x180017fd4  call    ?OpenTable@ESESession@@QEAAJW4_INDEXTABLE_ID@@@Z; ESESession::OpenTable(_INDEXTABLE_ID)
0x180017fd9  mov     esi, eax
0x180017fdb  test    eax, eax
0x180017fdd  js      loc_180018083
0x180017fe3  mov     ecx, ebx
0x180017fe5  call    ?GetTableDefinitionFromTableId@@YAPEBUDatabaseTableDefinition@@W4_INDEXTABLE_ID@@@Z; GetTableDefinitionFromTableId(_INDEXTABLE_ID)
0x180017fea  mov     rbp, rax
0x180017fed  mov     rcx, [rax+20h]
0x180017ff1  mov     r14, [rcx+8]
0x180017ff5  movsxd  rcx, ebx
0x180017ff8  lea     rsi, [rcx+rcx*2]
0x180017ffc  add     rsi, rsi
0x180017fff  cmp     qword ptr [rdi+rsi*8+70h], 0FFFFFFFFFFFFFFFFh
0x180018005  jnz     short loc_180018019
0x180018007  mov     r8d, 76h ; 'v'
0x18001800d  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018014  call    Log_AssertionEvent
0x180018019  mov     rdx, [rdi+rsi*8+70h]; tableid
0x18001801e  mov     r8, r14; szIndexName
0x180018021  mov     rcx, [rdi+38h]; sesid
0x180018025  call    cs:__imp_JetDeleteIndexA
0x18001802b  lea     ecx, [rax+r15]
0x18001802f  test    r15d, ecx
0x180018032  jnz     short loc_18001803B
0x180018034  cmp     eax, 0FFFFFA84h
0x180018039  jnz     short loc_18001805A
0x18001803b  mov     r8, [rbp+20h]
0x18001803f  mov     edx, ebx
0x180018041  mov     rcx, rdi
0x180018044  mov     r8, [r8+8]
0x180018048  call    ?_AddIndex@ESESession@@AEAAJW4_INDEXTABLE_ID@@PEBD@Z; ESESession::_AddIndex(_INDEXTABLE_ID,char const *)
0x18001804d  mov     esi, eax
0x18001804f  test    eax, eax
0x180018051  js      short loc_18001807B
0x180018053  inc     ebx
0x180018055  jmp     loc_180017FC6
0x18001805a  mov     ecx, eax; int
0x18001805c  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018061  mov     ebx, eax
0x180018063  mov     r9d, 360h
0x180018069  xor     edx, edx
0x18001806b  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018072  mov     ecx, eax
0x180018074  call    Log_HREvent
0x180018079  jmp     short loc_1800180A2
0x18001807b  mov     r9d, 366h
0x180018081  jmp     short loc_180018089
0x180018083  mov     r9d, 352h
0x180018089  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018090  mov     edx, 1
0x180018095  mov     ecx, esi
0x180018097  call    Log_HREvent
0x18001809c  mov     ebx, esi
0x18001809e  jmp     short loc_1800180A2
0x1800180a0  xor     ebx, ebx
0x1800180a2  lea     rcx, [rsp+88h+var_58]; this
0x1800180a7  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x1800180ac  mov     eax, ebx
0x1800180ae  add     rsp, 58h
0x1800180b2  pop     r15
0x1800180b4  pop     r14
0x1800180b6  pop     rdi
0x1800180b7  pop     rsi
0x1800180b8  pop     rbp
0x1800180b9  pop     rbx
0x1800180ba  retn
```
