# ESESession::EndTransaction(int)

- ea: `0x180016f5c`
- end: `0x180017065`
- name: `?EndTransaction@ESESession@@QEAAJH@Z`
- size: `265`
- prototype: `__int64 __fastcall(ESESession *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180013678`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x180010638`
- `0x180016860`
- `0x180016f5c`
- `0x180017d74`

## import_xrefs

- `ESENT!JetRollback` at `0x18001702e`
- `ESENT!JetRollback` at `0x18001702e`
- `ESENT!JetIdle` at `0x180017013`
- `ESENT!JetIdle` at `0x180017013`
- `ESENT!JetCommitTransaction2` at `0x180016fdf`
- `ESENT!JetCommitTransaction2` at `0x180016fdf`

## string_xrefs

- `0x180016fb4`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180016ffa`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::EndTransaction(ESESession *this, int a2)
{
  int HresultFromJetError; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  JET_SESID v9; // rcx
  int v10; // eax
  JET_ERR v11; // eax
  JET_ERR v12; // eax
  __int64 v14; // [rsp+30h] [rbp-28h] BYREF
  int v15; // [rsp+38h] [rbp-20h]
  char *v16; // [rsp+40h] [rbp-18h]

  v14 = *((_QWORD *)this + 7);
  v15 = 0;
  v16 = (char *)this + 64;
  HresultFromJetError = auto_SessionContext::SetContext((auto_SessionContext *)&v14);
  v6 = HresultFromJetError;
  if ( HresultFromJetError >= 0 )
  {
    if ( !*((_DWORD *)this + 88) )
      Log_AssertionEvent(
        v5,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
        208);
    v9 = *((_QWORD *)this + 7);
    *((_DWORD *)this + 88) = 0;
    if ( a2 )
    {
      v10 = JetCommitTransaction2(v9, 1, 120000);
      if ( v10 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v10);
        v7 = 218;
LABEL_8:
        v6 = HresultFromJetError;
        v8 = 0;
        goto LABEL_9;
      }
      v11 = JetIdle(*((_QWORD *)this + 7), 2u);
      if ( v11 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v11);
        v7 = 222;
        goto LABEL_8;
      }
    }
    else
    {
      v12 = JetRollback(v9, 0);
      if ( v12 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v12);
        v7 = 229;
        goto LABEL_8;
      }
    }
    v6 = 0;
    goto LABEL_15;
  }
  v7 = 205;
  v8 = 1;
LABEL_9:
  Log_HREvent(
    (unsigned int)HresultFromJetError,
    v8,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
    v7);
LABEL_15:
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v14);
  return v6;
}

```

## disassembly

```asm
0x180016f5c  mov     r11, rsp
0x180016f5f  mov     [r11+8], rbx
0x180016f63  mov     [r11+10h], rbp
0x180016f67  push    rdi
0x180016f68  sub     rsp, 50h
0x180016f6c  mov     rax, [rcx+38h]
0x180016f70  mov     rdi, rcx
0x180016f73  mov     [r11-28h], rax
0x180016f77  mov     ebp, edx
0x180016f79  lea     rax, [rcx+40h]
0x180016f7d  mov     [rsp+58h+var_20], 0
0x180016f85  lea     rcx, [r11-28h]; this
0x180016f89  mov     [r11-18h], rax
0x180016f8d  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x180016f92  mov     ebx, eax
0x180016f94  test    eax, eax
0x180016f96  jns     short loc_180016FA5
0x180016f98  mov     r9d, 0CDh
0x180016f9e  mov     edx, 1
0x180016fa3  jmp     short loc_180016FFA
0x180016fa5  cmp     dword ptr [rdi+160h], 0
0x180016fac  jnz     short loc_180016FC0
0x180016fae  mov     r8d, 0D0h
0x180016fb4  lea     rdx, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016fbb  call    Log_AssertionEvent
0x180016fc0  mov     rcx, [rdi+38h]; sesid
0x180016fc4  mov     dword ptr [rdi+160h], 0
0x180016fce  test    ebp, ebp
0x180016fd0  jz      short loc_18001702C
0x180016fd2  xor     r9d, r9d
0x180016fd5  mov     r8d, 1D4C0h
0x180016fdb  lea     edx, [r9+1]
0x180016fdf  call    cs:__imp_JetCommitTransaction2
0x180016fe5  test    eax, eax
0x180016fe7  jns     short loc_18001700A
0x180016fe9  mov     ecx, eax; int
0x180016feb  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180016ff0  mov     r9d, 0DAh
0x180016ff6  mov     ebx, eax
0x180016ff8  xor     edx, edx
0x180016ffa  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180017001  mov     ecx, eax
0x180017003  call    Log_HREvent
0x180017008  jmp     short loc_180017049
0x18001700a  mov     rcx, [rdi+38h]; sesid
0x18001700e  mov     edx, 2; grbit
0x180017013  call    cs:__imp_JetIdle
0x180017019  test    eax, eax
0x18001701b  jns     short loc_180017047
0x18001701d  mov     ecx, eax; int
0x18001701f  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180017024  mov     r9d, 0DEh
0x18001702a  jmp     short loc_180016FF6
0x18001702c  xor     edx, edx; grbit
0x18001702e  call    cs:__imp_JetRollback
0x180017034  test    eax, eax
0x180017036  jns     short loc_180017047
0x180017038  mov     ecx, eax; int
0x18001703a  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18001703f  mov     r9d, 0E5h
0x180017045  jmp     short loc_180016FF6
0x180017047  xor     ebx, ebx
0x180017049  lea     rcx, [rsp+58h+var_28]; this
0x18001704e  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x180017053  mov     rbp, [rsp+58h+arg_8]
0x180017058  mov     eax, ebx
0x18001705a  mov     rbx, [rsp+58h+arg_0]
0x18001705f  add     rsp, 50h
0x180017063  pop     rdi
0x180017064  retn
```
