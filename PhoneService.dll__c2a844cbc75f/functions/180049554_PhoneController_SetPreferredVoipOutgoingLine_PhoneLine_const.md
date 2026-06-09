# PhoneController::_SetPreferredVoipOutgoingLine(PhoneLine const *)

- ea: `0x180049554`
- end: `0x1800496d6`
- name: `?_SetPreferredVoipOutgoingLine@PhoneController@@IEAAJPEBVPhoneLine@@@Z`
- size: `386`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const struct PhoneLine *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18003a950`
- `0x180043690`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x1800091a8`
- `0x18002c574`
- `0x18002c580`
- `0x18003084c`
- `0x180049554`
- `0x18007f9ec`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800495ea`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800495ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004957c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004959c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004957c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004959c`

## string_xrefs

- `0x180049590`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180049625`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004967c`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_SetPreferredVoipOutgoingLine(PhoneController *this, const struct PhoneLine *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  BackTraceCollection *v6; // rcx
  unsigned int v7; // ebx
  void *v8; // rcx
  bool v9; // zf
  int v11; // eax
  BackTraceCollection *v12; // rcx
  void *Block[2]; // [rsp+30h] [rbp-49h] BYREF
  __int16 v14; // [rsp+40h] [rbp-39h] BYREF
  __int64 v15; // [rsp+42h] [rbp-37h]
  int v16; // [rsp+4Ah] [rbp-2Fh]
  __int16 v17; // [rsp+4Eh] [rbp-2Bh]
  GUID rguid; // [rsp+50h] [rbp-29h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-19h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 877);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  Block[0] = &v14;
  Block[1] = &v14;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v14 = 0;
  if ( a2 )
  {
    rguid = *(GUID *)((char *)a2 + 88);
    StringFromGUID2(&rguid, sz, 39);
    v5 = -1;
    do
      ++v5;
    while ( sz[v5] );
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(Block) )
    {
      v7 = -2147024882;
      BackTraceCollection::Capture(v6, -2147024882);
      Log_HREvent_7(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 885);
      v8 = Block[0];
      v9 = Block[0] == &v14;
LABEL_9:
      if ( !v9 )
        operator delete(v8);
      return v7;
    }
  }
  v11 = ConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Set(
          *((_QWORD *)this + 61) + 1696LL,
          (__int64)Block);
  v7 = v11;
  if ( v11 < 0 )
  {
    BackTraceCollection::Capture(v12, v11);
    Log_HREvent_7(v7, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 889);
    v8 = Block[0];
    v9 = Block[0] == &v14;
    goto LABEL_9;
  }
  if ( Block[0] != &v14 )
    operator delete(Block[0]);
  return 0;
}

```

## disassembly

```asm
0x180049554  mov     [rsp-8+arg_10], rbx
0x180049559  push    rbp
0x18004955a  push    rsi
0x18004955b  push    rdi
0x18004955c  lea     rbp, [rsp-47h]
0x180049561  sub     rsp, 0C0h
0x180049568  mov     rax, cs:__security_cookie
0x18004956f  xor     rax, rsp
0x180049572  mov     [rbp+57h+var_20], rax
0x180049576  mov     rdi, rdx
0x180049579  mov     rbx, rcx
0x18004957c  call    cs:__imp_GetCurrentThreadId
0x180049582  cmp     [rbx+0F0h], eax
0x180049588  jz      short loc_1800495AF
0x18004958a  mov     r8d, 36Dh
0x180049590  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180049597  call    Log_AssertionEvent_3
0x18004959c  call    cs:__imp_GetCurrentThreadId
0x1800495a2  cmp     [rbx+0F0h], eax
0x1800495a8  jz      short loc_1800495AF
0x1800495aa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800495af  xor     esi, esi
0x1800495b1  lea     rax, [rbp+57h+var_90]
0x1800495b5  mov     [rbp+57h+Block], rax
0x1800495b9  lea     rax, [rbp+57h+var_90]
0x1800495bd  mov     [rbp+57h+var_98], rax
0x1800495c1  mov     [rbp+57h+var_8E], rsi
0x1800495c5  mov     [rbp+57h+var_86], esi
0x1800495c8  mov     [rbp+57h+var_82], si
0x1800495cc  mov     [rbp+57h+var_90], si
0x1800495d0  test    rdi, rdi
0x1800495d3  jz      short loc_180049652
0x1800495d5  movups  xmm0, xmmword ptr [rdi+58h]
0x1800495d9  lea     r8d, [rsi+27h]; cchMax
0x1800495dd  lea     rdx, [rbp+57h+sz]; lpsz
0x1800495e1  lea     rcx, [rbp+57h+rguid]; rguid
0x1800495e5  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x1800495ea  call    cs:__imp_StringFromGUID2
0x1800495f0  lea     rax, [rbp+57h+sz]
0x1800495f4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800495f8  inc     r8
0x1800495fb  cmp     [rax+r8*2], si
0x180049600  jnz     short loc_1800495F8
0x180049602  lea     rdx, [rbp+57h+sz]
0x180049606  lea     rcx, [rbp+57h+Block]
0x18004960a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18004960f  test    al, al
0x180049611  jnz     short loc_180049652
0x180049613  mov     ebx, 8007000Eh
0x180049618  mov     edx, ebx; int
0x18004961a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004961f  mov     r9d, 375h
0x180049625  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004962c  xor     edx, edx
0x18004962e  mov     ecx, ebx
0x180049630  call    Log_HREvent_7
0x180049635  mov     rcx, [rbp+57h+Block]; Block
0x180049639  lea     rdx, [rbp+57h+var_90]
0x18004963d  cmp     rcx, rdx
0x180049640  jz      short loc_18004964E
0x180049642  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180049649  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004964e  mov     eax, ebx
0x180049650  jmp     short loc_1800496B7
0x180049652  mov     rcx, [rbx+1E8h]
0x180049659  lea     rdx, [rbp+57h+Block]
0x18004965d  add     rcx, 6A0h
0x180049664  call    ?Set@?$ConfigValue@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; ConfigValue<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Set(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180049669  mov     ebx, eax
0x18004966b  test    eax, eax
0x18004966d  jns     short loc_18004969C
0x18004966f  mov     edx, eax; int
0x180049671  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180049676  mov     r9d, 379h
0x18004967c  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180049683  mov     edx, 1
0x180049688  mov     ecx, ebx
0x18004968a  call    Log_HREvent_7
0x18004968f  mov     rcx, [rbp+57h+Block]
0x180049693  lea     rax, [rbp+57h+var_90]
0x180049697  cmp     rcx, rax
0x18004969a  jmp     short loc_180049640
0x18004969c  mov     rcx, [rbp+57h+Block]; Block
0x1800496a0  lea     rax, [rbp+57h+var_90]
0x1800496a4  cmp     rcx, rax
0x1800496a7  jz      short loc_1800496B5
0x1800496a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800496b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800496b5  xor     eax, eax
0x1800496b7  mov     rcx, [rbp+57h+var_20]
0x1800496bb  xor     rcx, rsp; StackCookie
0x1800496be  call    __security_check_cookie
0x1800496c3  mov     rbx, [rsp+0D0h+arg_10]
0x1800496cb  add     rsp, 0C0h
0x1800496d2  pop     rdi
0x1800496d3  pop     rsi
0x1800496d4  pop     rbp
0x1800496d5  retn
```
