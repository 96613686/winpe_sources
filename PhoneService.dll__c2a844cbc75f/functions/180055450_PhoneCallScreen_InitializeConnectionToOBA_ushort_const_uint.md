# PhoneCallScreen::InitializeConnectionToOBA(ushort const *,uint)

- ea: `0x180055450`
- end: `0x1800555e6`
- name: `?InitializeConnectionToOBA@PhoneCallScreen@@UEAAJPEBGI@Z`
- size: `406`
- prototype: `__int64 __fastcall(PhoneCallScreen *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005660`
- `0x180006e94`
- `0x180055450`
- `0x1800557b8`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055470`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055470`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800555cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800555cd`
- `UserDataPlatformHelperUtil!?_InitializeSecureRpcBinding@SecureRpcClient@Comms@@IEAAJPEBG0@Z` at `0x1800554f2`
- `UserDataPlatformHelperUtil!?_InitializeSecureRpcBinding@SecureRpcClient@Comms@@IEAAJPEBG0@Z` at `0x1800554f2`
- `UserDataPlatformHelperUtil!??0SecureRpcClient@Comms@@QEAA@XZ` at `0x1800554a0`
- `UserDataPlatformHelperUtil!??0SecureRpcClient@Comms@@QEAA@XZ` at `0x1800554a0`

## string_xrefs

- `0x180055526`: `onecoreuap\net\phone\phoneservice\service\lib\phonecallscreen.cpp`
- `0x1800555bc`: `onecoreuap\net\phone\phoneservice\service\lib\phonecallscreen.cpp`
- `0x180055503`: `onecoreuap\private\base\inc\appmodel\userdataaccess\CommsRpcClient.h`
- `0x180055596`: `onecoreuap\private\base\inc\appmodel\userdataaccess\CommsRpcClient.h`

## pseudocode

```c
__int64 __fastcall PhoneCallScreen::InitializeConnectionToOBA(
        PhoneCallScreen *this,
        const unsigned __int16 *a2,
        int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  struct ATL::CAtlModule *v9; // rcx
  int v10; // eax
  unsigned int v11; // edi
  BackTraceCollection *v12; // rcx
  __int64 v13; // rcx
  BackTraceCollection *v14; // rcx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v7 = operator new(0x28u);
  v8 = v7;
  if ( v7 )
  {
    *(_OWORD *)v7 = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_QWORD *)v7 + 4) = 0;
    Comms::SecureRpcClient::SecureRpcClient((Comms::SecureRpcClient *)(v7 + 2));
    v9 = ATL::_pAtlModule;
    *(_QWORD *)v8 = &ATL::CComObject<Comms::SecureRpcBinding>::`vftable'{for `IUnknown'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<Comms::SecureRpcBinding>::`vftable'{for `Comms::SecureRpcClient'};
    v8[6] = 0;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 8LL))(v8);
    v10 = Comms::SecureRpcClient::_InitializeSecureRpcBinding(
            (Comms::SecureRpcClient *)(v8 + 2),
            a2,
            L"PhoneCallFilter\\Server");
    v11 = v10;
    if ( v10 >= 0 )
    {
      if ( *((_DWORD **)this + 13) != v8 )
      {
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 8LL))(v8);
        v13 = *((_QWORD *)this + 13);
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        *((_QWORD *)this + 13) = v8;
      }
      *((_DWORD *)this + 38) = a3;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
      v11 = 0;
    }
    else
    {
      Log_HREvent_15(
        (unsigned int)v10,
        1,
        "onecoreuap\\private\\base\\inc\\appmodel\\userdataaccess\\CommsRpcClient.h",
        135);
      BackTraceCollection::Capture(v12, v11);
      Log_HREvent_15(v11, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phonecallscreen.cpp", 66);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  else
  {
    v11 = -2147024882;
    Log_HREvent_15(2147942414LL, 1, "onecoreuap\\private\\base\\inc\\appmodel\\userdataaccess\\CommsRpcClient.h", 115);
    BackTraceCollection::Capture(v14, -2147024882);
    Log_HREvent_15(2147942414LL, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phonecallscreen.cpp", 65);
  }
  LeaveCriticalSection(v3);
  return v11;
}

```

## disassembly

```asm
0x180055450  mov     [rsp+arg_10], rbx
0x180055455  push    rbp
0x180055456  push    rsi
0x180055457  push    rdi
0x180055458  push    r14
0x18005545a  push    r15
0x18005545c  sub     rsp, 30h
0x180055460  lea     rbp, [rcx+40h]
0x180055464  mov     rsi, rcx
0x180055467  mov     rcx, rbp; lpCriticalSection
0x18005546a  mov     r14d, r8d
0x18005546d  mov     r15, rdx
0x180055470  call    cs:__imp_EnterCriticalSection
0x180055476  mov     ecx, 28h ; '('; Size
0x18005547b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180055480  mov     rbx, rax
0x180055483  test    rax, rax
0x180055486  jz      loc_180055590
0x18005548c  xorps   xmm0, xmm0
0x18005548f  lea     rcx, [rbx+8]
0x180055493  movups  xmmword ptr [rbx], xmm0
0x180055496  xor     eax, eax
0x180055498  movups  xmmword ptr [rbx+10h], xmm0
0x18005549c  mov     [rbx+20h], rax
0x1800554a0  call    cs:__imp_??0SecureRpcClient@Comms@@QEAA@XZ; Comms::SecureRpcClient::SecureRpcClient(void)
0x1800554a6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800554ad  lea     rax, ??_7?$CComObject@VSecureRpcBinding@Comms@@@ATL@@6BIUnknown@@@; const ATL::CComObject<Comms::SecureRpcBinding>::`vftable'{for `IUnknown'}
0x1800554b4  mov     [rbx], rax
0x1800554b7  lea     rax, ??_7?$CComObject@VSecureRpcBinding@Comms@@@ATL@@6BSecureRpcClient@Comms@@@; const ATL::CComObject<Comms::SecureRpcBinding>::`vftable'{for `Comms::SecureRpcClient'}
0x1800554be  mov     [rbx+8], rax
0x1800554c2  mov     dword ptr [rbx+18h], 0
0x1800554c9  mov     rax, [rcx]
0x1800554cc  mov     rax, [rax+8]
0x1800554d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800554d5  mov     rax, [rbx]
0x1800554d8  mov     rcx, rbx
0x1800554db  mov     rax, [rax+8]
0x1800554df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800554e4  lea     rcx, [rbx+8]
0x1800554e8  mov     rdx, r15
0x1800554eb  lea     r8, aPhonecallfilte; "PhoneCallFilter\\Server"
0x1800554f2  call    cs:__imp_?_InitializeSecureRpcBinding@SecureRpcClient@Comms@@IEAAJPEBG0@Z; Comms::SecureRpcClient::_InitializeSecureRpcBinding(ushort const *,ushort const *)
0x1800554f8  mov     edi, eax
0x1800554fa  test    eax, eax
0x1800554fc  jns     short loc_180055548
0x1800554fe  mov     esi, 1
0x180055503  lea     r8, aOnecoreuapPriv_4; "onecoreuap\\private\\base\\inc\\appmode"...
0x18005550a  mov     edx, esi
0x18005550c  mov     r9d, 87h
0x180055512  mov     ecx, eax
0x180055514  call    Log_HREvent_15
0x180055519  mov     edx, edi; int
0x18005551b  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180055520  lea     r9d, [rsi+41h]
0x180055524  mov     edx, esi
0x180055526  lea     r8, aOnecoreuapNetP_12; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18005552d  mov     ecx, edi
0x18005552f  call    Log_HREvent_15
0x180055534  mov     rax, [rbx]
0x180055537  mov     rcx, rbx
0x18005553a  mov     rax, [rax+10h]
0x18005553e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055543  jmp     loc_1800555CA
0x180055548  cmp     [rsi+68h], rbx
0x18005554c  jz      short loc_180055576
0x18005554e  mov     rax, [rbx]
0x180055551  mov     rcx, rbx
0x180055554  mov     rax, [rax+8]
0x180055558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005555d  mov     rcx, [rsi+68h]
0x180055561  test    rcx, rcx
0x180055564  jz      short loc_180055572
0x180055566  mov     rax, [rcx]
0x180055569  mov     rax, [rax+10h]
0x18005556d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055572  mov     [rsi+68h], rbx
0x180055576  mov     [rsi+98h], r14d
0x18005557d  mov     rcx, rbx
0x180055580  mov     rax, [rbx]
0x180055583  mov     rax, [rax+10h]
0x180055587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005558c  xor     edi, edi
0x18005558e  jmp     short loc_1800555CA
0x180055590  mov     r9d, 73h ; 's'
0x180055596  lea     r8, aOnecoreuapPriv_4; "onecoreuap\\private\\base\\inc\\appmode"...
0x18005559d  mov     edi, 8007000Eh
0x1800555a2  mov     ecx, edi
0x1800555a4  lea     esi, [r9-72h]
0x1800555a8  mov     edx, esi
0x1800555aa  call    Log_HREvent_15
0x1800555af  mov     edx, edi; int
0x1800555b1  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800555b6  lea     r9d, [rsi+40h]
0x1800555ba  mov     edx, esi
0x1800555bc  lea     r8, aOnecoreuapNetP_12; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800555c3  mov     ecx, edi
0x1800555c5  call    Log_HREvent_15
0x1800555ca  mov     rcx, rbp; lpCriticalSection
0x1800555cd  call    cs:__imp_LeaveCriticalSection
0x1800555d3  mov     rbx, [rsp+58h+arg_10]
0x1800555d8  mov     eax, edi
0x1800555da  add     rsp, 30h
0x1800555de  pop     r15
0x1800555e0  pop     r14
0x1800555e2  pop     rdi
0x1800555e3  pop     rsi
0x1800555e4  pop     rbp
0x1800555e5  retn
```
