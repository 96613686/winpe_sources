# PhoneService::_CreateEvent(ushort const *,ushort const *,int,int,void * *)

- ea: `0x1800083b4`
- end: `0x180008568`
- name: `?_CreateEvent@PhoneService@@AEAAJPEBG0HHPEAPEAX@Z`
- size: `436`
- prototype: `__int64 __fastcall(PhoneService *this, const unsigned __int16 *, const unsigned __int16 *, __int64, int, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180008f44`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x180007780`
- `0x180007b04`
- `0x1800083b4`
- `0x180009094`
- `0x1800091a8`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800084f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800084f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084ff`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000849c`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000849c`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800084cb`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000852f`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800084cb`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000852f`

## string_xrefs

- `0x1800083ef`: `Global\PhoneServiceFilteringReady`

## pseudocode

```c
__int64 __fastcall PhoneService::_CreateEvent(
        PhoneService *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        int a5,
        void **a6)
{
  BackTraceCollection *v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  BackTraceCollection *v12; // rcx
  __int64 v14; // rax
  int TransientObjectSecurityDescriptor; // eax
  BackTraceCollection *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  HANDLE v19; // rax
  signed int LastError; // eax
  BackTraceCollection *v21; // rcx
  void *v22; // rcx
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+30h] [rbp-29h] BYREF
  void *v24; // [rsp+48h] [rbp-11h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-9h] BYREF
  __int16 v26; // [rsp+60h] [rbp+7h] BYREF
  __int64 v27; // [rsp+62h] [rbp+9h]
  int v28; // [rsp+6Ah] [rbp+11h]
  __int16 v29; // [rsp+6Eh] [rbp+15h]

  Block[0] = &v26;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  Block[1] = &v26;
  v26 = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(Block) )
  {
    v8 = -2147024882;
    BackTraceCollection::Capture(v7, -2147024882);
    v10 = 54;
LABEL_8:
    Log_HREvent_0(2147942414LL, 0, v9, v10);
LABEL_9:
    if ( Block[0] != &v26 )
      operator delete(Block[0]);
    return v8;
  }
  if ( a3 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a3[v11] );
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             Block,
                             a3) )
    {
      v8 = -2147024882;
      BackTraceCollection::Capture(v12, -2147024882);
      v10 = 58;
      goto LABEL_8;
    }
  }
  v24 = 0;
  v14 = tlx::replace<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),0>(&v24);
  TransientObjectSecurityDescriptor = QueryTransientObjectSecurityDescriptor(1, Block[0], v14);
  if ( TransientObjectSecurityDescriptor < 0 )
  {
    v8 = TransientObjectSecurityDescriptor | 0x10000000;
    BackTraceCollection::Capture(v16, TransientObjectSecurityDescriptor | 0x10000000);
    v18 = 64;
LABEL_14:
    Log_HREvent_0(v8, 0, v17, v18);
    if ( v24 )
      FreeTransientObjectSecurityDescriptor();
    goto LABEL_9;
  }
  EventAttributes.lpSecurityDescriptor = v24;
  *(_QWORD *)&EventAttributes.nLength = 24;
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  v19 = CreateEventW(&EventAttributes, 0, 0, (LPCWSTR)Block[0]);
  if ( !v19 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    BackTraceCollection::Capture(v21, v8);
    v18 = 71;
    goto LABEL_14;
  }
  v22 = v24;
  *a6 = v19;
  if ( v22 )
    FreeTransientObjectSecurityDescriptor();
  if ( Block[0] != &v26 )
    operator delete(Block[0]);
  return 0;
}

```

## disassembly

```asm
0x1800083b4  push    rbp
0x1800083b6  push    rbx
0x1800083b7  push    rsi
0x1800083b8  push    rdi
0x1800083b9  lea     rbp, [rsp-2Fh]
0x1800083be  sub     rsp, 88h
0x1800083c5  mov     rax, cs:__security_cookie
0x1800083cc  xor     rax, rsp
0x1800083cf  mov     [rbp+47h+var_30], rax
0x1800083d3  mov     rdi, [rbp+47h+arg_28]
0x1800083d7  lea     rax, [rbp+47h+var_40]
0x1800083db  xor     esi, esi
0x1800083dd  mov     [rbp+47h+Block], rax
0x1800083e1  mov     rbx, r8
0x1800083e4  mov     [rbp+47h+var_3E], rsi
0x1800083e8  lea     rax, [rbp+47h+var_40]
0x1800083ec  mov     [rbp+47h+var_36], esi
0x1800083ef  lea     rdx, aGlobalPhoneser; "Global\\PhoneServiceFilteringReady"
0x1800083f6  mov     [rbp+47h+var_32], si
0x1800083fa  lea     r8d, [rsi+21h]
0x1800083fe  mov     [rbp+47h+var_48], rax
0x180008402  lea     rcx, [rbp+47h+Block]
0x180008406  mov     [rbp+47h+var_40], si
0x18000840a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000840f  test    al, al
0x180008411  jnz     short loc_180008425
0x180008413  mov     ebx, 8007000Eh
0x180008418  mov     edx, ebx; int
0x18000841a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18000841f  lea     r9d, [rsi+36h]
0x180008423  jmp     short loc_18000845A
0x180008425  test    rbx, rbx
0x180008428  jz      short loc_180008483
0x18000842a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000842e  inc     r8
0x180008431  cmp     [rbx+r8*2], si
0x180008436  jnz     short loc_18000842E
0x180008438  mov     rdx, rbx
0x18000843b  lea     rcx, [rbp+47h+Block]
0x18000843f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180008444  test    al, al
0x180008446  jnz     short loc_180008483
0x180008448  mov     ebx, 8007000Eh
0x18000844d  mov     edx, ebx; int
0x18000844f  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180008454  mov     r9d, 3Ah ; ':'
0x18000845a  xor     edx, edx
0x18000845c  mov     ecx, ebx
0x18000845e  call    Log_HREvent_0
0x180008463  mov     rcx, [rbp+47h+Block]; Block
0x180008467  lea     rax, [rbp+47h+var_40]
0x18000846b  cmp     rcx, rax
0x18000846e  jz      short loc_18000847C
0x180008470  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180008477  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000847c  mov     eax, ebx
0x18000847e  jmp     loc_180008550
0x180008483  lea     rcx, [rbp+47h+var_58]
0x180008487  mov     [rbp+47h+var_58], rsi
0x18000848b  call    ??$replace@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@0@@Z; tlx::replace<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0>(tlx::auto_xxx<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0> &)
0x180008490  mov     rdx, [rbp+47h+Block]
0x180008494  mov     r8, rax
0x180008497  mov     ecx, 1
0x18000849c  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x1800084a2  mov     ebx, eax
0x1800084a4  test    eax, eax
0x1800084a6  jns     short loc_1800084D3
0x1800084a8  bts     ebx, 1Ch
0x1800084ac  mov     edx, ebx; int
0x1800084ae  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800084b3  mov     r9d, 40h ; '@'
0x1800084b9  xor     edx, edx
0x1800084bb  mov     ecx, ebx
0x1800084bd  call    Log_HREvent_0
0x1800084c2  mov     rcx, [rbp+47h+var_58]
0x1800084c6  test    rcx, rcx
0x1800084c9  jz      short loc_180008463
0x1800084cb  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800084d1  jmp     short loc_180008463
0x1800084d3  mov     rax, [rbp+47h+var_58]
0x1800084d7  lea     rcx, [rbp+47h+EventAttributes]; lpEventAttributes
0x1800084db  mov     r9, [rbp+47h+Block]; lpName
0x1800084df  xor     r8d, r8d; bInitialState
0x1800084e2  xor     edx, edx; bManualReset
0x1800084e4  mov     [rbp+47h+EventAttributes.lpSecurityDescriptor], rax
0x1800084e8  mov     qword ptr [rbp+47h+EventAttributes.nLength], 18h
0x1800084f0  mov     qword ptr [rbp+47h+EventAttributes.bInheritHandle], rsi
0x1800084f4  call    cs:__imp_CreateEventW
0x1800084fa  test    rax, rax
0x1800084fd  jnz     short loc_180008523
0x1800084ff  call    cs:__imp_GetLastError
0x180008505  mov     ebx, eax
0x180008507  test    eax, eax
0x180008509  jle     short loc_180008514
0x18000850b  movzx   ebx, ax
0x18000850e  or      ebx, 80070000h
0x180008514  mov     edx, ebx; int
0x180008516  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18000851b  mov     r9d, 47h ; 'G'
0x180008521  jmp     short loc_1800084B9
0x180008523  mov     rcx, [rbp+47h+var_58]
0x180008527  mov     [rdi], rax
0x18000852a  test    rcx, rcx
0x18000852d  jz      short loc_180008535
0x18000852f  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180008535  mov     rcx, [rbp+47h+Block]; Block
0x180008539  lea     rax, [rbp+47h+var_40]
0x18000853d  cmp     rcx, rax
0x180008540  jz      short loc_18000854E
0x180008542  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180008549  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000854e  xor     eax, eax
0x180008550  mov     rcx, [rbp+47h+var_30]
0x180008554  xor     rcx, rsp; StackCookie
0x180008557  call    __security_check_cookie
0x18000855c  add     rsp, 88h
0x180008563  pop     rdi
0x180008564  pop     rsi
0x180008565  pop     rbx
0x180008566  pop     rbp
0x180008567  retn
```
