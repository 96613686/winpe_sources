# PhoneController::_SendDeferredControllerMessage(tagPH_MSG,_GUID const &,ushort const *,ushort const *)

- ea: `0x180047a48`
- end: `0x180047c8a`
- name: `?_SendDeferredControllerMessage@PhoneController@@IEAAJW4tagPH_MSG@@AEBU_GUID@@PEBG2@Z`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041084`

## callees

- `0x180005660`
- `0x180006e94`
- `0x1800091a8`
- `0x18002c574`
- `0x18002c580`
- `0x180047a48`
- `0x18007f9ec`
- `0x18008d95a`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047a70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047a91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047a70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047a91`

## string_xrefs

- `0x180047b84`: `onecoreuap\net\phone\phoneservice\service\lib\ControllerMessagesPriv.h`
- `0x180047c3a`: `onecoreuap\net\phone\phoneservice\service\lib\ControllerMessagesPriv.h`
- `0x180047a85`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180047bfc`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180047c60`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_SendDeferredControllerMessage(
        __int64 a1,
        int a2,
        __int128 *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v9; // rcx
  char *v10; // rax
  char *v11; // rdi
  struct ATL::CAtlModule *v12; // rcx
  __int128 v13; // xmm0
  __int64 v14; // rsi
  __int64 v15; // r8
  __int64 v16; // r9
  BackTraceCollection *v17; // rcx
  int v18; // eax
  BackTraceCollection *v19; // rcx
  unsigned int v20; // ebx

  if ( *(_DWORD *)(a1 + 240) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v9, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4744);
    if ( *(_DWORD *)(a1 + 240) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v10 = (char *)operator new(0x78u);
  v11 = v10;
  if ( !v10 )
  {
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\ControllerMessagesPriv.h", 1276);
    goto LABEL_19;
  }
  memset_0(v10, 0, 0x78u);
  *((_DWORD *)v11 + 8) = 76;
  *(GUID *)(v11 + 36) = GUID_00000000_0000_0000_0000_000000000000;
  *((_QWORD *)v11 + 11) = v11 + 104;
  *((_QWORD *)v11 + 12) = v11 + 104;
  *((_QWORD *)v11 + 7) = v11 + 72;
  *((_QWORD *)v11 + 8) = v11 + 72;
  v12 = ATL::_pAtlModule;
  *(_QWORD *)v11 = &ATL::CComObject<ControllerSinkMessage>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v12 + 8LL))(v12);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 16LL))(v11);
  *((_DWORD *)v11 + 6) = 26;
  *((_DWORD *)v11 + 8) = a2;
  v13 = *a3;
  v14 = -1;
  *(_OWORD *)(v11 + 36) = v13;
  if ( a4 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(a4 + 2 * v15) );
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(v11 + 56) )
    {
      v16 = 1285;
LABEL_10:
      Log_HREvent_7(
        2147942414LL,
        0,
        "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\ControllerMessagesPriv.h",
        v16);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 16LL))(v11);
LABEL_19:
      BackTraceCollection::Capture(v17, -2147024882);
      Log_HREvent_7(2147942414LL, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4748);
      return 2147942414LL;
    }
  }
  if ( a5 )
  {
    do
      ++v14;
    while ( *(_WORD *)(a5 + 2 * v14) );
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(v11 + 88) )
    {
      v16 = 1290;
      goto LABEL_10;
    }
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(a1 + 208) + 40LL))(*(_QWORD *)(a1 + 208), v11);
  v20 = v18;
  if ( v18 >= 0 )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 16LL))(v11);
    return 0;
  }
  else
  {
    BackTraceCollection::Capture(v19, v18);
    Log_HREvent_7(v20, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4751);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 16LL))(v11);
    return v20;
  }
}

```

## disassembly

```asm
0x180047a48  mov     [rsp+arg_8], rbx
0x180047a4d  push    rbp
0x180047a4e  push    rsi
0x180047a4f  push    rdi
0x180047a50  push    r12
0x180047a52  push    r13
0x180047a54  push    r14
0x180047a56  push    r15
0x180047a58  sub     rsp, 30h
0x180047a5c  mov     rbp, [rsp+68h+arg_20]
0x180047a64  mov     r15, r9
0x180047a67  mov     rsi, r8
0x180047a6a  mov     r12d, edx
0x180047a6d  mov     r14, rcx
0x180047a70  call    cs:__imp_GetCurrentThreadId
0x180047a76  cmp     [r14+0F0h], eax
0x180047a7d  jz      short loc_180047AA5
0x180047a7f  mov     r8d, 1288h
0x180047a85  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180047a8c  call    Log_AssertionEvent_3
0x180047a91  call    cs:__imp_GetCurrentThreadId
0x180047a97  cmp     [r14+0F0h], eax
0x180047a9e  jz      short loc_180047AA5
0x180047aa0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180047aa5  xor     r13d, r13d
0x180047aa8  lea     ecx, [r13+78h]; Size
0x180047aac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180047ab1  mov     rdi, rax
0x180047ab4  test    rax, rax
0x180047ab7  jz      loc_180047C35
0x180047abd  xor     edx, edx; Val
0x180047abf  lea     r8d, [r13+78h]; Size
0x180047ac3  mov     rcx, rax; void *
0x180047ac6  call    memset_0
0x180047acb  mov     dword ptr [rdi+20h], 4Ch ; 'L'
0x180047ad2  lea     rcx, [rdi+48h]
0x180047ad6  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180047add  lea     rax, [rdi+68h]
0x180047ae1  movdqu  xmmword ptr [rdi+24h], xmm0
0x180047ae6  mov     [rdi+58h], rax
0x180047aea  mov     [rdi+60h], rax
0x180047aee  lea     rax, ??_7?$CComObject@VControllerSinkMessage@@@ATL@@6B@; const ATL::CComObject<ControllerSinkMessage>::`vftable'
0x180047af5  mov     [rdi+38h], rcx
0x180047af9  mov     [rdi+40h], rcx
0x180047afd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180047b04  mov     [rdi], rax
0x180047b07  mov     rax, [rcx]
0x180047b0a  mov     rax, [rax+8]
0x180047b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b13  mov     rax, [rdi]
0x180047b16  mov     rcx, rdi
0x180047b19  mov     rax, [rax+8]
0x180047b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b22  mov     rax, [rdi]
0x180047b25  mov     rcx, rdi
0x180047b28  mov     rax, [rax+8]
0x180047b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b31  mov     rax, [rdi]
0x180047b34  mov     rcx, rdi
0x180047b37  mov     rax, [rax+10h]
0x180047b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b40  mov     dword ptr [rdi+18h], 1Ah
0x180047b47  mov     [rdi+20h], r12d
0x180047b4b  movups  xmm0, xmmword ptr [rsi]
0x180047b4e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180047b52  movdqu  xmmword ptr [rdi+24h], xmm0
0x180047b57  test    r15, r15
0x180047b5a  jz      short loc_180047BA8
0x180047b5c  mov     r8, rsi
0x180047b5f  inc     r8
0x180047b62  cmp     [r15+r8*2], r13w
0x180047b67  jnz     short loc_180047B5F
0x180047b69  lea     rcx, [rdi+38h]
0x180047b6d  mov     rdx, r15
0x180047b70  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180047b75  test    al, al
0x180047b77  jnz     short loc_180047BA8
0x180047b79  mov     r9d, 505h
0x180047b7f  mov     esi, 8007000Eh
0x180047b84  lea     r8, aOnecoreuapNetP_24; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180047b8b  mov     ecx, esi
0x180047b8d  xor     edx, edx
0x180047b8f  call    Log_HREvent_7
0x180047b94  mov     rax, [rdi]
0x180047b97  mov     rcx, rdi
0x180047b9a  mov     rax, [rax+10h]
0x180047b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ba3  jmp     loc_180047C53
0x180047ba8  test    rbp, rbp
0x180047bab  jz      short loc_180047BD3
0x180047bad  inc     rsi
0x180047bb0  cmp     [rbp+rsi*2+0], r13w
0x180047bb6  jnz     short loc_180047BAD
0x180047bb8  lea     rcx, [rdi+58h]
0x180047bbc  mov     r8, rsi
0x180047bbf  mov     rdx, rbp
0x180047bc2  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180047bc7  test    al, al
0x180047bc9  jnz     short loc_180047BD3
0x180047bcb  mov     r9d, 50Ah
0x180047bd1  jmp     short loc_180047B7F
0x180047bd3  mov     rcx, [r14+0D0h]
0x180047bda  mov     rdx, rdi
0x180047bdd  mov     rax, [rcx]
0x180047be0  mov     rax, [rax+28h]
0x180047be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047be9  mov     ebx, eax
0x180047beb  test    eax, eax
0x180047bed  jns     short loc_180047C22
0x180047bef  mov     edx, eax; int
0x180047bf1  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180047bf6  mov     r9d, 128Fh
0x180047bfc  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180047c03  mov     edx, 1
0x180047c08  mov     ecx, ebx
0x180047c0a  call    Log_HREvent_7
0x180047c0f  mov     rcx, [rdi]
0x180047c12  mov     rax, [rcx+10h]
0x180047c16  mov     rcx, rdi
0x180047c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c1e  mov     eax, ebx
0x180047c20  jmp     short loc_180047C75
0x180047c22  mov     rax, [rdi]
0x180047c25  mov     rcx, rdi
0x180047c28  mov     rax, [rax+10h]
0x180047c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c31  xor     eax, eax
0x180047c33  jmp     short loc_180047C75
0x180047c35  mov     esi, 8007000Eh
0x180047c3a  lea     r8, aOnecoreuapNetP_24; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180047c41  mov     ecx, esi
0x180047c43  mov     r9d, 4FCh
0x180047c49  mov     edx, 1
0x180047c4e  call    Log_HREvent_7
0x180047c53  mov     edx, esi; int
0x180047c55  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180047c5a  mov     r9d, 128Ch
0x180047c60  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180047c67  mov     edx, 1
0x180047c6c  mov     ecx, esi
0x180047c6e  call    Log_HREvent_7
0x180047c73  mov     eax, esi
0x180047c75  mov     rbx, [rsp+68h+arg_8]
0x180047c7a  add     rsp, 30h
0x180047c7e  pop     r15
0x180047c80  pop     r14
0x180047c82  pop     r13
0x180047c84  pop     r12
0x180047c86  pop     rdi
0x180047c87  pop     rsi
0x180047c88  pop     rbp
0x180047c89  retn
```
