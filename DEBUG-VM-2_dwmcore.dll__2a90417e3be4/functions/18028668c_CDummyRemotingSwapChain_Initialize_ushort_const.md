# CDummyRemotingSwapChain::Initialize(ushort const *)

- ea: `0x18028668c`
- end: `0x180286833`
- name: `?Initialize@CDummyRemotingSwapChain@@IEAAJPEBG@Z`
- size: `423`
- prototype: `__int64 __fastcall(CDummyRemotingSwapChain *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180286154`

## callees

- `0x1800098f8`
- `0x180009c30`
- `0x180042de0`
- `0x18022943c`
- `0x18028668c`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802866b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802866b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18028679f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802867bd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18028679f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802867bd`

## string_xrefs

- `0x1802866a9`: `DwmIndirectCreate`

## pseudocode

```c
__int64 __fastcall CDummyRemotingSwapChain::Initialize(HMODULE *this, const unsigned __int16 *a2)
{
  FARPROC ProcAddress; // rbx
  int v5; // eax
  unsigned int v6; // edi
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rdi
  _QWORD *v8; // r14
  __int64 (__fastcall *v9)(_QWORD, GUID *, HMODULE *); // rbx
  __int64 v10; // rcx
  HANDLE EventW; // rax
  HANDLE v12; // rax
  int v13; // r9d
  unsigned int v15; // [rsp+20h] [rbp-49h]
  __int128 v16; // [rsp+30h] [rbp-39h] BYREF
  const unsigned __int16 *v17; // [rsp+40h] [rbp-29h]
  __int64 v18; // [rsp+48h] [rbp-21h]
  __int64 v19; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v20[104]; // [rsp+58h] [rbp-11h] BYREF

  ProcAddress = GetProcAddress(this[8], "DwmIndirectCreate");
  if ( !ProcAddress )
  {
    v6 = -2147024809;
    v13 = -2147024809;
    v15 = 92;
    goto LABEL_11;
  }
  v17 = a2;
  v16 = 0;
  v18 = 0;
  wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(this + 9);
  v5 = ((__int64 (__fastcall *)(__int128 *, HMODULE *))ProcAddress)(&v16, this + 9);
  v6 = v5;
  if ( v5 < 0 )
  {
    v15 = 66;
    goto LABEL_8;
  }
  v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))this[9];
  v8 = this + 10;
  v9 = (__int64 (__fastcall *)(_QWORD, GUID *, HMODULE *))**v7;
  wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(this + 10);
  v5 = v9(v7, &IID_IDWMRemotingIndirectEx, this + 10);
  v6 = v5;
  if ( v5 < 0 )
  {
    v15 = 69;
LABEL_8:
    v13 = v5;
LABEL_11:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v13, v15, 0);
    return v6;
  }
  v19 = 7;
  memset_0(v20, 0, 0x40u);
  (*(void (__fastcall **)(_QWORD, __int64 *, __int64))(*(_QWORD *)*v8 + 56LL))(*v8, &v19, 1);
  if ( *((_BYTE *)g_pComposition + 808) )
  {
    v10 = *v8;
    LODWORD(v19) = 11;
    v20[8] = 1;
    (*(void (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v10 + 56LL))(v10, &v19, 1);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    this + 13,
    EventW);
  v12 = CreateEventW(0, 1, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    this + 25,
    v12);
  return v6;
}

```

## disassembly

```asm
0x18028668c  push    rbp
0x18028668e  push    rbx
0x18028668f  push    rsi
0x180286690  push    rdi
0x180286691  push    r14
0x180286693  lea     rbp, [rsp-37h]
0x180286698  sub     rsp, 0A0h
0x18028669f  mov     rdi, rdx
0x1802866a2  mov     rsi, rcx
0x1802866a5  mov     rcx, [rcx+40h]; hModule
0x1802866a9  lea     rdx, aDwmindirectcre; "DwmIndirectCreate"
0x1802866b0  call    cs:__imp_GetProcAddress
0x1802866b6  mov     rbx, rax
0x1802866b9  test    rax, rax
0x1802866bc  jz      loc_1802867FD
0x1802866c2  xorps   xmm0, xmm0
0x1802866c5  mov     [rbp+57h+var_80], rdi
0x1802866c9  lea     r14, [rsi+48h]
0x1802866cd  movdqa  [rbp+57h+var_90], xmm0
0x1802866d2  mov     rcx, r14
0x1802866d5  mov     [rbp+57h+var_78], 0
0x1802866dd  call    ?reset@?$com_ptr_t@UIDXGISwapChain1@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(void)
0x1802866e2  mov     rdx, r14
0x1802866e5  lea     rcx, [rbp+57h+var_90]
0x1802866e9  mov     rax, rbx
0x1802866ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802866f1  mov     edi, eax
0x1802866f3  test    eax, eax
0x1802866f5  js      loc_1802867EA
0x1802866fb  mov     rdi, [r14]
0x1802866fe  lea     r14, [rsi+50h]
0x180286702  mov     rcx, r14
0x180286705  mov     rax, [rdi]
0x180286708  mov     rbx, [rax]
0x18028670b  call    ?reset@?$com_ptr_t@UIDXGISwapChain1@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(void)
0x180286710  mov     r8, r14
0x180286713  lea     rdx, IID_IDWMRemotingIndirectEx
0x18028671a  mov     rcx, rdi
0x18028671d  mov     rax, rbx
0x180286720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180286725  mov     edi, eax
0x180286727  test    eax, eax
0x180286729  js      loc_1802867D4
0x18028672f  xor     edx, edx; Val
0x180286731  mov     [rbp+57h+var_70], 7
0x180286739  lea     rcx, [rbp+57h+var_68]; void *
0x18028673d  lea     r8d, [rdx+40h]; Size
0x180286741  call    memset_0
0x180286746  mov     rcx, [r14]
0x180286749  lea     rdx, [rbp+57h+var_70]
0x18028674d  mov     r8d, 1
0x180286753  mov     rax, [rcx]
0x180286756  mov     rax, [rax+38h]
0x18028675a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028675f  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x180286766  cmp     byte ptr [rax+328h], 0
0x18028676d  jz      short loc_180286793
0x18028676f  mov     rcx, [r14]
0x180286772  lea     rdx, [rbp+57h+var_70]
0x180286776  mov     dword ptr [rbp+57h+var_70], 0Bh
0x18028677d  mov     r8d, 1
0x180286783  mov     [rbp+57h+var_60], 1
0x180286787  mov     rax, [rcx]
0x18028678a  mov     rax, [rax+38h]
0x18028678e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180286793  xor     r9d, r9d; lpName
0x180286796  xor     r8d, r8d; bInitialState
0x180286799  xor     ecx, ecx; lpEventAttributes
0x18028679b  lea     edx, [r9+1]; bManualReset
0x18028679f  call    cs:__imp_CreateEventW
0x1802867a5  mov     rdx, rax
0x1802867a8  lea     rcx, [rsi+68h]
0x1802867ac  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802867b1  xor     r9d, r9d; lpName
0x1802867b4  xor     r8d, r8d; bInitialState
0x1802867b7  xor     ecx, ecx; lpEventAttributes
0x1802867b9  lea     edx, [r9+1]; bManualReset
0x1802867bd  call    cs:__imp_CreateEventW
0x1802867c3  mov     rdx, rax
0x1802867c6  lea     rcx, [rsi+0C8h]
0x1802867cd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802867d2  jmp     short loc_180286823
0x1802867d4  mov     [rsp+0C0h+var_98], 0
0x1802867dd  mov     [rsp+0C0h+var_A0], 45h ; 'E'
0x1802867e5  mov     r9d, eax
0x1802867e8  jmp     short loc_180286816
0x1802867ea  mov     [rsp+0C0h+var_98], 0
0x1802867f3  mov     [rsp+0C0h+var_A0], 42h ; 'B'
0x1802867fb  jmp     short loc_1802867E5
0x1802867fd  mov     edi, 80070057h
0x180286802  mov     [rsp+0C0h+var_98], 0; void *
0x18028680b  mov     r9d, edi; int
0x18028680e  mov     [rsp+0C0h+var_A0], 5Ch ; '\'; unsigned int
0x180286816  xor     edx, edx; int *
0x180286818  xor     r8d, r8d; unsigned int
0x18028681b  lea     ecx, [rdx+14h]; unsigned int
0x18028681e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180286823  mov     eax, edi
0x180286825  add     rsp, 0A0h
0x18028682c  pop     r14
0x18028682e  pop     rdi
0x18028682f  pop     rsi
0x180286830  pop     rbx
0x180286831  pop     rbp
0x180286832  retn
```
