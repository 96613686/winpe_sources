# _lambda_983deade1ef85b175d24d05d87d8a1b3_::operator()

- ea: `0x1800400a8`
- end: `0x1800401b7`
- name: `_lambda_983deade1ef85b175d24d05d87d8a1b3_::operator()`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800408f0`

## callees

- `0x18000e270`
- `0x18003808c`
- `0x180040070`
- `0x1800400a8`
- `0x1800401c0`
- `0x180040238`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180040130`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180040130`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180040109`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004016a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180040109`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004016a`

## pseudocode

```c
void __fastcall lambda_983deade1ef85b175d24d05d87d8a1b3_::operator()(__int64 *a1)
{
  int BackgroundWindow; // eax
  __int64 v3; // r9
  HANDLE v4; // rax
  int lpdwindex; // [rsp+20h] [rbp-20h]
  void **v6; // [rsp+30h] [rbp-10h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  DWORD dwindex; // [rsp+50h] [rbp+10h] BYREF
  __int64 v10; // [rsp+58h] [rbp+18h] BYREF

  v10 = 0;
  BackgroundWindow = HostAppBackground::CreateBackgroundWindow((HostAppBackground *)&v10);
  if ( BackgroundWindow < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\hostappenvironment.cpp",
      (const char *)(unsigned int)BackgroundWindow,
      lpdwindex);
  v3 = *a1;
  dwindex = 0;
  CoWaitForMultipleHandles(0x18u, 0xFFFFFFFF, 1u, (LPHANDLE)(v3 + 24), &dwindex);
  pHandles = 0;
  v6 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  v4 = OpenEventW(0x1F0003u, 0, L"DestroyCloudExperienceHostAppBackgroundEvent");
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(&v6, v4);
  if ( pHandles )
  {
    *(_BYTE *)(*a1 + 34) = 1;
    CoWaitForMultipleHandles(0x18u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v6);
    *(_BYTE *)(*a1 + 34) = 0;
  }
  v10 &= -(__int64)(*(_BYTE *)(*a1 + 33) != 0);
  v6 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v6);
  HostAppBackground::~HostAppBackground((HostAppBackground *)&v10);
}

```

## disassembly

```asm
0x1800400a8  mov     [rsp-8+arg_10], rbx
0x1800400ad  push    rbp
0x1800400ae  mov     rbp, rsp
0x1800400b1  sub     rsp, 40h
0x1800400b5  mov     rbx, rcx
0x1800400b8  mov     [rbp+arg_8], 0
0x1800400c0  lea     rcx, [rbp+arg_8]; this
0x1800400c4  call    ?CreateBackgroundWindow@HostAppBackground@@QEAAJXZ; HostAppBackground::CreateBackgroundWindow(void)
0x1800400c9  test    eax, eax
0x1800400cb  jns     short loc_1800400E5
0x1800400cd  mov     rcx, [rbp+8]; this
0x1800400d1  lea     r8, aShellLibCloude_1; "shell\\lib\\cloudexperiencehostappmanag"...
0x1800400d8  mov     r9d, eax; char *
0x1800400db  mov     edx, 7Dh ; '}'; void *
0x1800400e0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800400e5  mov     r9, [rbx]
0x1800400e8  lea     rax, [rbp+dwindex]
0x1800400ec  mov     r8d, 1; cHandles
0x1800400f2  mov     [rbp+dwindex], 0
0x1800400f9  add     r9, 18h; pHandles
0x1800400fd  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x180040102  or      edx, 0FFFFFFFFh; dwTimeout
0x180040105  lea     ecx, [r8+17h]; dwFlags
0x180040109  call    cs:__imp_CoWaitForMultipleHandles
0x18004010f  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180040116  mov     [rbp+pHandles], 0
0x18004011e  lea     r8, aDestroycloudex; "DestroyCloudExperienceHostAppBackground"...
0x180040125  mov     [rbp+var_10], rax
0x180040129  xor     edx, edx; bInheritHandle
0x18004012b  mov     ecx, 1F0003h; dwDesiredAccess
0x180040130  call    cs:__imp_OpenEventW
0x180040136  mov     rdx, rax
0x180040139  lea     rcx, [rbp+var_10]
0x18004013d  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x180040142  cmp     [rbp+pHandles], 0
0x180040147  jz      short loc_180040180
0x180040149  mov     rax, [rbx]
0x18004014c  lea     r9, [rbp+pHandles]; pHandles
0x180040150  mov     r8d, 1; cHandles
0x180040156  or      edx, 0FFFFFFFFh; dwTimeout
0x180040159  mov     byte ptr [rax+22h], 1
0x18004015d  lea     rax, [rbp+dwindex]
0x180040161  lea     ecx, [r8+17h]; dwFlags
0x180040165  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x18004016a  call    cs:__imp_CoWaitForMultipleHandles
0x180040170  lea     rcx, [rbp+var_10]
0x180040174  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180040179  mov     rax, [rbx]
0x18004017c  mov     byte ptr [rax+22h], 0
0x180040180  mov     rax, [rbx]
0x180040183  mov     cl, [rax+21h]
0x180040186  neg     cl
0x180040188  lea     rcx, [rbp+var_10]
0x18004018c  sbb     rax, rax
0x18004018f  and     [rbp+arg_8], rax
0x180040193  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18004019a  mov     [rbp+var_10], rax
0x18004019e  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x1800401a3  lea     rcx, [rbp+arg_8]; this
0x1800401a7  call    ??1HostAppBackground@@QEAA@XZ; HostAppBackground::~HostAppBackground(void)
0x1800401ac  mov     rbx, [rsp+40h+arg_10]
0x1800401b1  add     rsp, 40h
0x1800401b5  pop     rbp
0x1800401b6  retn
```
