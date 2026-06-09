# ESESession::_DeleteIndexInfoTable(void)

- ea: `0x180018be4`
- end: `0x180018c91`
- name: `?_DeleteIndexInfoTable@ESESession@@AEAAJXZ`
- size: `173`
- prototype: `__int64 __fastcall(ESESession *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180016a70`

## callees

- `0x180002da8`
- `0x180010638`
- `0x180016860`
- `0x180017d74`
- `0x180018be4`
- `0x18001968c`

## import_xrefs

- `ESENT!JetDeleteTableA` at `0x180018c3e`
- `ESENT!JetDeleteTableA` at `0x180018c3e`

## string_xrefs

- `0x180018c68`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::_DeleteIndexInfoTable(ESESession *this)
{
  int HresultFromJetError; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // rdx
  JET_ERR v6; // eax
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  int v9; // [rsp+38h] [rbp-20h]
  char *v10; // [rsp+40h] [rbp-18h]

  v8 = *((_QWORD *)this + 7);
  v9 = 0;
  v10 = (char *)this + 64;
  HresultFromJetError = auto_SessionContext::SetContext((auto_SessionContext *)&v8);
  v3 = HresultFromJetError;
  if ( HresultFromJetError >= 0 )
  {
    auto_JET_TABLEID::close((ESESession *)((char *)this + 32));
    v6 = JetDeleteTableA(*((_QWORD *)this + 7), *((_DWORD *)this + 6), "IndexingInfo");
    if ( (int)(v6 + 0x80000000) < 0 || v6 == -1305 )
    {
      v3 = 0;
      goto LABEL_8;
    }
    HresultFromJetError = MakeHresultFromJetError(v6);
    v3 = HresultFromJetError;
    v4 = 1406;
    v5 = 0;
  }
  else
  {
    v4 = 1395;
    v5 = 1;
  }
  Log_HREvent(
    (unsigned int)HresultFromJetError,
    v5,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
    v4);
LABEL_8:
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v8);
  return v3;
}

```

## disassembly

```asm
0x180018be4  mov     r11, rsp
0x180018be7  mov     [r11+8], rbx
0x180018beb  push    rdi
0x180018bec  sub     rsp, 50h
0x180018bf0  mov     rax, [rcx+38h]
0x180018bf4  mov     rdi, rcx
0x180018bf7  mov     [r11-28h], rax
0x180018bfb  lea     rax, [rcx+40h]
0x180018bff  mov     [rsp+58h+var_20], 0
0x180018c07  lea     rcx, [r11-28h]; this
0x180018c0b  mov     [r11-18h], rax
0x180018c0f  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x180018c14  mov     ebx, eax
0x180018c16  test    eax, eax
0x180018c18  jns     short loc_180018C27
0x180018c1a  mov     r9d, 573h
0x180018c20  mov     edx, 1
0x180018c25  jmp     short loc_180018C68
0x180018c27  lea     rcx, [rdi+20h]; this
0x180018c2b  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x180018c30  mov     edx, [rdi+18h]; dbid
0x180018c33  lea     r8, szTableName; "IndexingInfo"
0x180018c3a  mov     rcx, [rdi+38h]; sesid
0x180018c3e  call    cs:__imp_JetDeleteTableA
0x180018c44  mov     edx, 80000000h
0x180018c49  lea     ecx, [rax+rdx]
0x180018c4c  test    edx, ecx
0x180018c4e  jnz     short loc_180018C78
0x180018c50  cmp     eax, 0FFFFFAE7h
0x180018c55  jz      short loc_180018C78
0x180018c57  mov     ecx, eax; int
0x180018c59  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018c5e  mov     ebx, eax
0x180018c60  mov     r9d, 57Eh
0x180018c66  xor     edx, edx
0x180018c68  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018c6f  mov     ecx, eax
0x180018c71  call    Log_HREvent
0x180018c76  jmp     short loc_180018C7A
0x180018c78  xor     ebx, ebx
0x180018c7a  lea     rcx, [rsp+58h+var_28]; this
0x180018c7f  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x180018c84  mov     eax, ebx
0x180018c86  mov     rbx, [rsp+58h+arg_0]
0x180018c8b  add     rsp, 50h
0x180018c8f  pop     rdi
0x180018c90  retn
```
