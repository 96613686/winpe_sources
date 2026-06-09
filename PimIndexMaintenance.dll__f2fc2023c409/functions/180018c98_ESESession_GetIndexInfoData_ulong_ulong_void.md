# ESESession::_GetIndexInfoData(ulong,ulong,void *)

- ea: `0x180018c98`
- end: `0x180018e11`
- name: `?_GetIndexInfoData@ESESession@@AEAAJKKPEAX@Z`
- size: `377`
- prototype: `__int64 __fastcall(ESESession *this, unsigned int, unsigned int, void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1800177fc`
- `0x180017a34`

## callees

- `0x180002da8`
- `0x18000b5f4`
- `0x180010638`
- `0x180016860`
- `0x18001774c`
- `0x180017d74`
- `0x180018c98`
- `0x1800211f2`
- `0x18002120a`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018cff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018cff`
- `ESENT!JetMove` at `0x180018d48`
- `ESENT!JetMove` at `0x180018d48`

## string_xrefs

- `0x180018de0`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::_GetIndexInfoData(ESESession *this, unsigned int a2, unsigned int a3, void *a4)
{
  SIZE_T v5; // r14
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rcx
  HLOCAL v13; // rax
  void *v14; // rbx
  int Column; // eax
  int v16; // eax
  unsigned int HresultFromJetError; // eax
  void *v19; // [rsp+30h] [rbp-28h] BYREF
  __int64 v20; // [rsp+38h] [rbp-20h] BYREF
  int v21; // [rsp+40h] [rbp-18h]
  char *v22; // [rsp+48h] [rbp-10h]
  int v23; // [rsp+A0h] [rbp+48h] BYREF

  v20 = *((_QWORD *)this + 7);
  v5 = a3;
  v22 = (char *)this + 64;
  v19 = 0;
  v23 = 0;
  v21 = 0;
  v8 = auto_SessionContext::SetContext((auto_SessionContext *)&v20);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 254;
    v11 = 1;
    v12 = (unsigned int)v8;
LABEL_19:
    Log_HREvent(
      v12,
      v11,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      v10);
    goto LABEL_20;
  }
  v13 = LocalAlloc(0x40u, v5);
  v14 = v13;
  if ( !v13 )
  {
    v10 = 258;
    v9 = -2147024882;
    goto LABEL_17;
  }
  v19 = v13;
  Column = auto_JET_TABLEID::GetColumn((ESESession *)((char *)this + 32), a2, v13, v5, &v23);
  if ( Column != -1603 )
  {
    if ( Column < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(Column);
      v10 = 299;
      goto LABEL_10;
    }
    goto LABEL_15;
  }
  if ( JetMove(*((_QWORD *)this + 7), *((_QWORD *)this + 5), 0x80000000, 0) != -1603 )
  {
    v16 = auto_JET_TABLEID::GetColumn((ESESession *)((char *)this + 32), a2, v14, v5, &v23);
    if ( v16 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v16);
      v10 = 289;
LABEL_10:
      v9 = HresultFromJetError;
      v12 = HresultFromJetError;
LABEL_18:
      v11 = 0;
      goto LABEL_19;
    }
    if ( !v23 )
    {
      v10 = 294;
      v9 = -2147023728;
LABEL_17:
      v12 = v9;
      goto LABEL_18;
    }
LABEL_15:
    memcpy_0(a4, v14, v5);
    goto LABEL_7;
  }
  memset_0(a4, 0, v5);
LABEL_7:
  v9 = 0;
LABEL_20:
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v20);
  auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(&v19);
  return v9;
}

```

## disassembly

```asm
0x180018c98  push    rbp
0x180018c9a  push    rbx
0x180018c9b  push    rsi
0x180018c9c  push    rdi
0x180018c9d  push    r12
0x180018c9f  push    r13
0x180018ca1  push    r14
0x180018ca3  push    r15
0x180018ca5  mov     rbp, rsp
0x180018ca8  sub     rsp, 58h
0x180018cac  mov     rax, [rcx+38h]
0x180018cb0  xor     r13d, r13d
0x180018cb3  mov     [rbp+var_20], rax
0x180018cb7  mov     rsi, rcx
0x180018cba  lea     rax, [rcx+40h]
0x180018cbe  mov     r14d, r8d
0x180018cc1  lea     rcx, [rbp+var_20]; this
0x180018cc5  mov     [rbp+var_10], rax
0x180018cc9  mov     r15, r9
0x180018ccc  mov     [rbp+var_28], r13
0x180018cd0  mov     r12d, edx
0x180018cd3  mov     [rbp+arg_0], r13d
0x180018cd7  mov     [rbp+var_18], r13d
0x180018cdb  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x180018ce0  mov     ebx, eax
0x180018ce2  test    eax, eax
0x180018ce4  jns     short loc_180018CF7
0x180018ce6  mov     r9d, 0FEh
0x180018cec  lea     edx, [r13+1]
0x180018cf0  mov     ecx, eax
0x180018cf2  jmp     loc_180018DE0
0x180018cf7  mov     rdx, r14; uBytes
0x180018cfa  mov     ecx, 40h ; '@'; uFlags
0x180018cff  call    cs:__imp_LocalAlloc
0x180018d05  mov     rbx, rax
0x180018d08  test    rax, rax
0x180018d0b  jz      loc_180018DD1
0x180018d11  mov     [rbp+var_28], rax
0x180018d15  lea     rcx, [rsi+20h]; this
0x180018d19  lea     rax, [rbp+arg_0]
0x180018d1d  mov     r9d, r14d; unsigned int
0x180018d20  mov     r8, rbx; void *
0x180018d23  mov     [rsp+58h+var_38], rax; int *
0x180018d28  mov     edx, r12d; unsigned int
0x180018d2b  call    ?GetColumn@auto_JET_TABLEID@@QEAAJKPEAXKPEAH@Z; auto_JET_TABLEID::GetColumn(ulong,void *,ulong,int *)
0x180018d30  cmp     eax, 0FFFFF9BDh
0x180018d35  jnz     short loc_180018DAE
0x180018d37  mov     rdx, [rsi+28h]; tableid
0x180018d3b  xor     r9d, r9d; grbit
0x180018d3e  mov     rcx, [rsi+38h]; sesid
0x180018d42  mov     r8d, 80000000h; cRow
0x180018d48  call    cs:__imp_JetMove
0x180018d4e  cmp     eax, 0FFFFF9BDh
0x180018d53  jnz     short loc_180018D69
0x180018d55  mov     r8, r14; Size
0x180018d58  xor     edx, edx; Val
0x180018d5a  mov     rcx, r15; void *
0x180018d5d  call    memset_0
0x180018d62  xor     ebx, ebx
0x180018d64  jmp     loc_180018DEC
0x180018d69  lea     rax, [rbp+arg_0]
0x180018d6d  mov     r9d, r14d; unsigned int
0x180018d70  mov     r8, rbx; void *
0x180018d73  mov     [rsp+58h+var_38], rax; int *
0x180018d78  mov     edx, r12d; unsigned int
0x180018d7b  lea     rcx, [rsi+20h]; this
0x180018d7f  call    ?GetColumn@auto_JET_TABLEID@@QEAAJKPEAXKPEAH@Z; auto_JET_TABLEID::GetColumn(ulong,void *,ulong,int *)
0x180018d84  test    eax, eax
0x180018d86  jns     short loc_180018D9B
0x180018d88  mov     ecx, eax; int
0x180018d8a  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018d8f  mov     r9d, 121h
0x180018d95  mov     ebx, eax
0x180018d97  mov     ecx, eax
0x180018d99  jmp     short loc_180018DDE
0x180018d9b  cmp     [rbp+arg_0], r13d
0x180018d9f  jnz     short loc_180018DC1
0x180018da1  mov     r9d, 126h
0x180018da7  mov     ebx, 80070490h
0x180018dac  jmp     short loc_180018DDC
0x180018dae  test    eax, eax
0x180018db0  jns     short loc_180018DC1
0x180018db2  mov     ecx, eax; int
0x180018db4  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180018db9  mov     r9d, 12Bh
0x180018dbf  jmp     short loc_180018D95
0x180018dc1  mov     r8, r14; Size
0x180018dc4  mov     rdx, rbx; Src
0x180018dc7  mov     rcx, r15; void *
0x180018dca  call    memcpy_0
0x180018dcf  jmp     short loc_180018D62
0x180018dd1  mov     r9d, 102h
0x180018dd7  mov     ebx, 8007000Eh
0x180018ddc  mov     ecx, ebx
0x180018dde  xor     edx, edx
0x180018de0  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018de7  call    Log_HREvent
0x180018dec  lea     rcx, [rbp+var_20]; this
0x180018df0  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x180018df5  lea     rcx, [rbp+var_28]
0x180018df9  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x180018dfe  mov     eax, ebx
0x180018e00  add     rsp, 58h
0x180018e04  pop     r15
0x180018e06  pop     r14
0x180018e08  pop     r13
0x180018e0a  pop     r12
0x180018e0c  pop     rdi
0x180018e0d  pop     rsi
0x180018e0e  pop     rbx
0x180018e0f  pop     rbp
0x180018e10  retn
```
