# FveBcdUtil::UpdateBcdRecoveryStringData(void *,ulong,ushort const *)

- ea: `0x18006bec4`
- end: `0x18006c0d5`
- name: `?UpdateBcdRecoveryStringData@FveBcdUtil@@SAJPEAXKPEBG@Z`
- size: `529`
- prototype: `static int(void *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x18001bdb0`

## callees

- `0x180001fe8`
- `0x1800020e0`
- `0x180009f60`
- `0x18001b890`
- `0x180025ed4`
- `0x18002f28c`
- `0x180034610`
- `0x180034ca4`
- `0x18006b0b8`
- `0x18006bec4`

## import_xrefs

- `bcd!BcdSetElementData` at `0x18006bfee`
- `bcd!BcdSetElementData` at `0x18006bfee`
- `bcd!BcdDeleteElement` at `0x18006bf6b`
- `bcd!BcdDeleteElement` at `0x18006bf6b`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::UpdateBcdRecoveryStringData(void *a1, unsigned int a2, const unsigned __int16 *a3)
{
  unsigned int BcdElementData; // ebx
  wchar_t *v7; // rdi
  int v8; // eax
  unsigned int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rsi
  int v14; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  void *Block; // [rsp+30h] [rbp-28h] BYREF
  PSRWLOCK v19[4]; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v20; // [rsp+B8h] [rbp+60h] BYREF

  Block = 0;
  v20 = 0;
  BcdElementData = FveBcdUtil::GetBcdElementData(a1, a2, &Block, &v20);
  if ( BcdElementData == (unsigned int)FromNtStatus(-1073741275) )
  {
    v7 = 0;
    BcdElementData = 0;
  }
  else
  {
    if ( BcdElementData )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
          BcdElementData);
      if ( (BcdElementData & 0x80000000) != 0 )
      {
        v7 = (wchar_t *)Block;
        goto LABEL_26;
      }
    }
    v7 = (wchar_t *)Block;
  }
  if ( a3 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a3[v13] );
    if ( !v7 || v20 != 2 * v13 + 2 || wcsicmp(v7, a3) )
    {
      v14 = BcdSetElementData(a1, a2, a3, (unsigned int)(2 * v13 + 2));
      BcdElementData = FromNtStatus(v14);
      if ( BcdElementData )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v11 = 72;
          v12 = BcdElementData;
          goto LABEL_25;
        }
      }
    }
  }
  else if ( v7 )
  {
    v8 = BcdDeleteElement(a1, a2);
    v9 = FromNtStatus(v8);
    BcdElementData = v9;
    if ( v9 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v11 = 71;
        v12 = v9;
LABEL_25:
        WPP_SF_d(v10[2], v11, &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids, v12);
      }
    }
  }
LABEL_26:
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v19,
    &g_hBitLockerBcdUpdateProvider,
    &g_bitLockerBcdUpdateProviderInitLock,
    &g_bitLockerBcdUpdateProviderRefCount);
  if ( (unsigned int)dword_18009A468 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A468, 0x400000000000LL) )
  {
    Block = (void *)0x1000000;
    v20 = BcdElementData;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (int)&dword_18009A468,
      (int)&byte_18008E3FF,
      v15,
      v16,
      (__int64)&v20,
      (__int64)&Block);
  }
  if ( v7 )
    operator delete(v7);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar(v19);
  return BcdElementData;
}

```

## disassembly

```asm
0x18006bec4  push    rbp
0x18006bec6  push    rbx
0x18006bec7  push    rsi
0x18006bec8  push    rdi
0x18006bec9  push    r12
0x18006becb  push    r13
0x18006becd  push    r14
0x18006becf  push    r15
0x18006bed1  mov     rbp, rsp
0x18006bed4  sub     rsp, 58h
0x18006bed8  mov     r14, r8
0x18006bedb  lea     r9, [rbp+arg_18]; unsigned int *
0x18006bedf  xor     r13d, r13d
0x18006bee2  lea     r8, [rbp+Block]; void **
0x18006bee6  mov     [rbp+Block], r13
0x18006beea  mov     r15d, edx
0x18006beed  mov     [rbp+arg_18], r13d
0x18006bef1  mov     r12, rcx
0x18006bef4  call    ?GetBcdElementData@FveBcdUtil@@SAJPEAXKPEAPEAXPEAK@Z; FveBcdUtil::GetBcdElementData(void *,ulong,void * *,ulong *)
0x18006bef9  mov     ecx, 0C0000225h; int
0x18006befe  mov     ebx, eax
0x18006bf00  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18006bf05  lea     rsi, WPP_GLOBAL_Control
0x18006bf0c  cmp     ebx, eax
0x18006bf0e  jnz     short loc_18006BF18
0x18006bf10  mov     edi, r13d
0x18006bf13  mov     ebx, r13d
0x18006bf16  jmp     short loc_18006BF57
0x18006bf18  test    ebx, ebx
0x18006bf1a  jz      short loc_18006BF53
0x18006bf1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bf23  cmp     rcx, rsi
0x18006bf26  jz      short loc_18006BF46
0x18006bf28  test    byte ptr [rcx+1Ch], 40h
0x18006bf2c  jz      short loc_18006BF46
0x18006bf2e  mov     rcx, [rcx+10h]
0x18006bf32  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18006bf39  mov     edx, 46h ; 'F'
0x18006bf3e  mov     r9d, ebx
0x18006bf41  call    WPP_SF_d
0x18006bf46  test    ebx, ebx
0x18006bf48  jns     short loc_18006BF53
0x18006bf4a  mov     rdi, [rbp+Block]
0x18006bf4e  jmp     loc_18006C038
0x18006bf53  mov     rdi, [rbp+Block]
0x18006bf57  test    r14, r14
0x18006bf5a  jnz     short loc_18006BFAB
0x18006bf5c  test    rdi, rdi
0x18006bf5f  jz      loc_18006C038
0x18006bf65  mov     edx, r15d
0x18006bf68  mov     rcx, r12
0x18006bf6b  call    cs:__imp_BcdDeleteElement
0x18006bf72  nop     dword ptr [rax+rax+00h]
0x18006bf77  mov     ecx, eax; int
0x18006bf79  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18006bf7e  mov     ebx, eax
0x18006bf80  test    eax, eax
0x18006bf82  jz      loc_18006C038
0x18006bf88  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bf8f  cmp     rcx, rsi
0x18006bf92  jz      loc_18006C038
0x18006bf98  test    byte ptr [rcx+1Ch], 40h
0x18006bf9c  jz      loc_18006C038
0x18006bfa2  lea     edx, [r14+47h]
0x18006bfa6  mov     r9d, eax
0x18006bfa9  jmp     short loc_18006C028
0x18006bfab  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006bfaf  inc     rsi
0x18006bfb2  cmp     [r14+rsi*2], r13w
0x18006bfb7  jnz     short loc_18006BFAF
0x18006bfb9  test    rdi, rdi
0x18006bfbc  jz      short loc_18006BFDD
0x18006bfbe  mov     eax, [rbp+arg_18]
0x18006bfc1  lea     rcx, ds:2[rsi*2]
0x18006bfc9  cmp     rax, rcx
0x18006bfcc  jnz     short loc_18006BFDD
0x18006bfce  mov     rdx, r14; String2
0x18006bfd1  mov     rcx, rdi; String1
0x18006bfd4  call    _wcsicmp
0x18006bfd9  test    eax, eax
0x18006bfdb  jz      short loc_18006C038
0x18006bfdd  lea     r9d, ds:2[rsi*2]
0x18006bfe5  mov     r8, r14
0x18006bfe8  mov     edx, r15d
0x18006bfeb  mov     rcx, r12
0x18006bfee  call    cs:__imp_BcdSetElementData
0x18006bff5  nop     dword ptr [rax+rax+00h]
0x18006bffa  mov     ecx, eax; int
0x18006bffc  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18006c001  mov     ebx, eax
0x18006c003  test    eax, eax
0x18006c005  jz      short loc_18006C038
0x18006c007  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c00e  lea     rax, WPP_GLOBAL_Control
0x18006c015  cmp     rcx, rax
0x18006c018  jz      short loc_18006C038
0x18006c01a  test    byte ptr [rcx+1Ch], 40h
0x18006c01e  jz      short loc_18006C038
0x18006c020  mov     edx, 48h ; 'H'
0x18006c025  mov     r9d, ebx
0x18006c028  mov     rcx, [rcx+10h]
0x18006c02c  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18006c033  call    WPP_SF_d
0x18006c038  lea     r9, ?g_bitLockerBcdUpdateProviderRefCount@@3JC; volatile int *
0x18006c03f  lea     r8, ?g_bitLockerBcdUpdateProviderInitLock@@3U_RTL_SRWLOCK@@A; struct _RTL_SRWLOCK *
0x18006c046  lea     rdx, g_hBitLockerBcdUpdateProvider; struct _tlgProvider_t **
0x18006c04d  lea     rcx, [rbp+var_20]; this
0x18006c051  call    ??0TelemetryProviderRegistrar@@QEAA@PEBQEBU_tlgProvider_t@@PEAU_RTL_SRWLOCK@@PECJ@Z; TelemetryProviderRegistrar::TelemetryProviderRegistrar(_tlgProvider_t const * const *,_RTL_SRWLOCK *,long volatile *)
0x18006c056  mov     eax, cs:dword_18009A468
0x18006c05c  cmp     eax, 4
0x18006c05f  jbe     short loc_18006C0AB
0x18006c061  mov     rdx, 400000000000h
0x18006c06b  lea     rcx, dword_18009A468
0x18006c072  call    _tlgKeywordOn
0x18006c077  test    al, al
0x18006c079  jz      short loc_18006C0AB
0x18006c07b  lea     rax, [rbp+Block]
0x18006c07f  mov     [rbp+Block], 1000000h
0x18006c087  mov     [rsp+58h+var_30], rax
0x18006c08c  lea     rdx, byte_18008E3FF
0x18006c093  lea     rax, [rbp+arg_18]
0x18006c097  mov     [rbp+arg_18], ebx
0x18006c09a  lea     rcx, dword_18009A468
0x18006c0a1  mov     [rsp+58h+var_38], rax
0x18006c0a6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18006c0ab  test    rdi, rdi
0x18006c0ae  jz      short loc_18006C0B8
0x18006c0b0  mov     rcx, rdi; Block
0x18006c0b3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006c0b8  lea     rcx, [rbp+var_20]; this
0x18006c0bc  call    ??1TelemetryProviderRegistrar@@QEAA@XZ; TelemetryProviderRegistrar::~TelemetryProviderRegistrar(void)
0x18006c0c1  mov     eax, ebx
0x18006c0c3  add     rsp, 58h
0x18006c0c7  pop     r15
0x18006c0c9  pop     r14
0x18006c0cb  pop     r13
0x18006c0cd  pop     r12
0x18006c0cf  pop     rdi
0x18006c0d0  pop     rsi
0x18006c0d1  pop     rbx
0x18006c0d2  pop     rbp
0x18006c0d3  retn
```
