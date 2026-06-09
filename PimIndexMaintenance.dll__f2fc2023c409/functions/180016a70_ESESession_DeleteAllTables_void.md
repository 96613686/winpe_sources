# ESESession::DeleteAllTables(void)

- ea: `0x180016a70`
- end: `0x180016b61`
- name: `?DeleteAllTables@ESESession@@QEAAJXZ`
- size: `241`
- prototype: `__int64 __fastcall(ESESession *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000ee40`

## callees

- `0x180002da8`
- `0x180016860`
- `0x180016a70`
- `0x180016db0`
- `0x180017d74`
- `0x180018be4`

## string_xrefs

- `0x180016b03`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180016b30`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::DeleteAllTables(ESESession *this)
{
  int v2; // eax
  unsigned int v3; // edi
  __int64 v4; // r9
  __int64 v5; // rdi
  unsigned int i; // ebp
  int v7; // eax
  int v8; // r14d
  __int64 v10; // [rsp+30h] [rbp-58h] BYREF
  int v11; // [rsp+38h] [rbp-50h]
  char *v12; // [rsp+40h] [rbp-48h]

  v10 = *((_QWORD *)this + 7);
  v12 = (char *)this + 64;
  v11 = 0;
  v2 = auto_SessionContext::SetContext((auto_SessionContext *)&v10);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 788;
LABEL_13:
    Log_HREvent(
      (unsigned int)v2,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      v4);
    goto LABEL_15;
  }
  v5 = 0;
LABEL_4:
  if ( (_DWORD)v5 )
  {
    v2 = ESESession::_DeleteIndexInfoTable(this);
    v3 = v2;
    if ( v2 >= 0 )
    {
      v3 = 0;
      goto LABEL_15;
    }
    v4 = 803;
    goto LABEL_13;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)&gc_tableDefinitionMappings + 6 * v5 + 4) )
    {
      v5 = 1;
      goto LABEL_4;
    }
    v7 = ESESession::DeleteTable(
           this,
           *(unsigned int *)(*((_QWORD *)&gc_tableDefinitionMappings + 3 * v5 + 1) + 208LL * i + 200),
           0);
    v8 = v7;
    if ( v7 < 0 )
      break;
  }
  Log_HREvent(
    (unsigned int)v7,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
    799);
  v3 = v8;
LABEL_15:
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v10);
  return v3;
}

```

## disassembly

```asm
0x180016a70  push    rbp
0x180016a72  push    rsi
0x180016a73  push    rdi
0x180016a74  push    r12
0x180016a76  push    r14
0x180016a78  push    r15
0x180016a7a  sub     rsp, 58h
0x180016a7e  mov     rax, [rcx+38h]
0x180016a82  mov     rsi, rcx
0x180016a85  mov     [rsp+88h+var_58], rax
0x180016a8a  lea     rax, [rcx+40h]
0x180016a8e  lea     rcx, [rsp+88h+var_58]; this
0x180016a93  mov     [rsp+88h+var_48], rax
0x180016a98  mov     [rsp+88h+var_50], 0
0x180016aa0  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x180016aa5  mov     edi, eax
0x180016aa7  test    eax, eax
0x180016aa9  jns     short loc_180016AB3
0x180016aab  mov     r9d, 314h
0x180016ab1  jmp     short loc_180016B30
0x180016ab3  xor     edi, edi
0x180016ab5  lea     r12, ?gc_tableDefinitionMappings@@3QBUIndexTableMapping@@B; IndexTableMapping const near * const gc_tableDefinitionMappings
0x180016abc  cmp     edi, 1
0x180016abf  jnb     short loc_180016B1C
0x180016ac1  xor     ebp, ebp
0x180016ac3  lea     r15, [rdi+rdi*2]
0x180016ac7  cmp     ebp, [r12+r15*8+10h]
0x180016acc  jnb     short loc_180016AF9
0x180016ace  mov     rdx, [r12+r15*8+8]
0x180016ad3  xor     r8d, r8d
0x180016ad6  mov     eax, ebp
0x180016ad8  imul    rcx, rax, 0D0h
0x180016adf  mov     edx, [rdx+rcx+0C8h]
0x180016ae6  mov     rcx, rsi
0x180016ae9  call    ?DeleteTable@ESESession@@QEAAJW4_INDEXTABLE_ID@@H@Z; ESESession::DeleteTable(_INDEXTABLE_ID,int)
0x180016aee  mov     r14d, eax
0x180016af1  test    eax, eax
0x180016af3  js      short loc_180016AFD
0x180016af5  inc     ebp
0x180016af7  jmp     short loc_180016AC7
0x180016af9  inc     edi
0x180016afb  jmp     short loc_180016ABC
0x180016afd  mov     r9d, 31Fh
0x180016b03  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016b0a  mov     edx, 1
0x180016b0f  mov     ecx, r14d
0x180016b12  call    Log_HREvent
0x180016b17  mov     edi, r14d
0x180016b1a  jmp     short loc_180016B47
0x180016b1c  mov     rcx, rsi; this
0x180016b1f  call    ?_DeleteIndexInfoTable@ESESession@@AEAAJXZ; ESESession::_DeleteIndexInfoTable(void)
0x180016b24  mov     edi, eax
0x180016b26  test    eax, eax
0x180016b28  jns     short loc_180016B45
0x180016b2a  mov     r9d, 323h
0x180016b30  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180016b37  mov     edx, 1
0x180016b3c  mov     ecx, eax
0x180016b3e  call    Log_HREvent
0x180016b43  jmp     short loc_180016B47
0x180016b45  xor     edi, edi
0x180016b47  lea     rcx, [rsp+88h+var_58]; this
0x180016b4c  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x180016b51  mov     eax, edi
0x180016b53  add     rsp, 58h
0x180016b57  pop     r15
0x180016b59  pop     r14
0x180016b5b  pop     r12
0x180016b5d  pop     rdi
0x180016b5e  pop     rsi
0x180016b5f  pop     rbp
0x180016b60  retn
```
