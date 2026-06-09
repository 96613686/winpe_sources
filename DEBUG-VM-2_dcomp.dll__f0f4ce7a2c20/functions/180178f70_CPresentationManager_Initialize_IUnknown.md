# CPresentationManager::Initialize(IUnknown *)

- ea: `0x180178f70`
- end: `0x1801790c6`
- name: `?Initialize@CPresentationManager@@AEAAJPEAUIUnknown@@@Z`
- size: `342`
- prototype: `__int64 __fastcall(CPresentationManager *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180178be8`

## callees

- `0x180013528`
- `0x18007fbd4`
- `0x180081bac`
- `0x180084ba0`
- `0x180178998`
- `0x180178f70`
- `0x18017976c`
- `0x180182010`

## import_xrefs

- `win32u!NtFlipObjectCreate` at `0x180178fe4`
- `win32u!NtFlipObjectCreate` at `0x180178fe4`
- `win32u!NtFlipObjectOpen` at `0x180179029`
- `win32u!NtFlipObjectOpen` at `0x180179029`
- `win32u!NtFlipObjectQueryLostEvent` at `0x180179053`
- `win32u!NtFlipObjectQueryLostEvent` at `0x180179053`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180179072`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180179072`

## pseudocode

```c
__int64 __fastcall CPresentationManager::Initialize(CPresentationManager *this, struct IUnknown *a2)
{
  _QWORD *v2; // rsi
  int v4; // ebx
  __int64 v5; // rax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int LostEvent; // eax
  unsigned int v10; // edx
  int v11; // ecx
  char *v13; // [rsp+20h] [rbp-20h] BYREF
  struct CSynchronizationContext *v14; // [rsp+28h] [rbp-18h] BYREF
  char v15; // [rsp+30h] [rbp-10h]
  __int64 v16; // [rsp+60h] [rbp+20h] BYREF
  LARGE_INTEGER Frequency; // [rsp+70h] [rbp+30h] BYREF

  v16 = 0;
  v2 = (_QWORD *)((char *)this + 168);
  v14 = 0;
  v13 = (char *)this + 168;
  v15 = 1;
  v4 = CSynchronizationContext::Create(a2, &v14);
  wil::details::out_param_t<std::unique_ptr<CSynchronizationContext>>::~out_param_t<std::unique_ptr<CSynchronizationContext>>(&v13);
  if ( v4 < 0 )
  {
    v10 = 39;
    v11 = v4;
    goto LABEL_11;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v16,
    0);
  v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 64LL))(*v2);
  v6 = NtFlipObjectCreate(v5, &v16);
  v7 = HRESULTFromNTSTATUS(v6);
  v4 = v7;
  if ( v7 < 0 )
  {
    v10 = 44;
    goto LABEL_7;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 136,
    0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 120,
    0);
  v8 = NtFlipObjectOpen(v16, 1, (char *)this + 120, (char *)this + 136, v13);
  v7 = HRESULTFromNTSTATUS(v8);
  v4 = v7;
  if ( v7 < 0 )
  {
    v10 = 50;
    goto LABEL_7;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 128,
    0);
  LostEvent = NtFlipObjectQueryLostEvent(*((_QWORD *)this + 15), (char *)this + 128);
  v7 = HRESULTFromNTSTATUS(LostEvent);
  v4 = v7;
  if ( v7 < 0 )
  {
    v10 = 54;
LABEL_7:
    v11 = v7;
LABEL_11:
    DoStackCaptureDirect(v11, v10);
    goto LABEL_12;
  }
  Frequency.QuadPart = 0;
  QueryPerformanceFrequency(&Frequency);
  *((double *)this + 24) = (double)(int)Frequency.LowPart;
LABEL_12:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180178f70  mov     [rsp-18h+arg_8], rbx
0x180178f75  push    rbp
0x180178f76  push    rsi
0x180178f77  push    rdi
0x180178f78  mov     rbp, rsp
0x180178f7b  sub     rsp, 40h
0x180178f7f  mov     rax, rdx
0x180178f82  mov     [rbp+arg_0], 0
0x180178f8a  lea     rsi, [rcx+0A8h]
0x180178f91  mov     [rbp+var_18], 0
0x180178f99  mov     rdi, rcx
0x180178f9c  mov     [rbp+var_20], rsi
0x180178fa0  mov     rcx, rax; struct IUnknown *
0x180178fa3  mov     [rbp+var_10], 1
0x180178fa7  lea     rdx, [rbp+var_18]; struct CSynchronizationContext **
0x180178fab  call    ?Create@CSynchronizationContext@@SAJPEAUIUnknown@@PEAPEAV1@@Z; CSynchronizationContext::Create(IUnknown *,CSynchronizationContext * *)
0x180178fb0  lea     rcx, [rbp+var_20]
0x180178fb4  mov     ebx, eax
0x180178fb6  call    ??1?$out_param_t@V?$unique_ptr@VCSynchronizationContext@@U?$default_delete@VCSynchronizationContext@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<CSynchronizationContext>>::~out_param_t<std::unique_ptr<CSynchronizationContext>>(void)
0x180178fbb  test    ebx, ebx
0x180178fbd  js      loc_1801790A2
0x180178fc3  xor     edx, edx
0x180178fc5  lea     rcx, [rbp+arg_0]
0x180178fc9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180178fce  mov     rcx, [rsi]
0x180178fd1  mov     rax, [rcx]
0x180178fd4  mov     rax, [rax+40h]
0x180178fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178fdd  lea     rdx, [rbp+arg_0]
0x180178fe1  mov     rcx, rax
0x180178fe4  call    cs:__imp_NtFlipObjectCreate
0x180178fea  mov     ecx, eax; int
0x180178fec  call    ?HRESULTFromNTSTATUS@@YAJJ@Z; HRESULTFromNTSTATUS(long)
0x180178ff1  mov     ebx, eax
0x180178ff3  test    eax, eax
0x180178ff5  js      loc_18017909B
0x180178ffb  lea     rbx, [rdi+88h]
0x180179002  xor     edx, edx
0x180179004  mov     rcx, rbx
0x180179007  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18017900c  lea     rsi, [rdi+78h]
0x180179010  xor     edx, edx
0x180179012  mov     rcx, rsi
0x180179015  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18017901a  mov     rcx, [rbp+arg_0]
0x18017901e  mov     r9, rbx
0x180179021  mov     r8, rsi
0x180179024  mov     edx, 1
0x180179029  call    cs:__imp_NtFlipObjectOpen
0x18017902f  mov     ecx, eax; int
0x180179031  call    ?HRESULTFromNTSTATUS@@YAJJ@Z; HRESULTFromNTSTATUS(long)
0x180179036  mov     ebx, eax
0x180179038  test    eax, eax
0x18017903a  js      short loc_180179094
0x18017903c  lea     rbx, [rdi+80h]
0x180179043  xor     edx, edx
0x180179045  mov     rcx, rbx
0x180179048  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18017904d  mov     rcx, [rsi]
0x180179050  mov     rdx, rbx
0x180179053  call    cs:__imp_NtFlipObjectQueryLostEvent
0x180179059  mov     ecx, eax; int
0x18017905b  call    ?HRESULTFromNTSTATUS@@YAJJ@Z; HRESULTFromNTSTATUS(long)
0x180179060  mov     ebx, eax
0x180179062  test    eax, eax
0x180179064  js      short loc_18017908B
0x180179066  lea     rcx, [rbp+Frequency]; lpFrequency
0x18017906a  mov     qword ptr [rbp+Frequency], 0
0x180179072  call    cs:__imp_QueryPerformanceFrequency
0x180179078  xorps   xmm0, xmm0
0x18017907b  cvtsi2sd xmm0, qword ptr [rbp+Frequency]
0x180179081  movsd   qword ptr [rdi+0C0h], xmm0
0x180179089  jmp     short loc_1801790AE
0x18017908b  mov     edx, 36h ; '6'
0x180179090  mov     ecx, eax
0x180179092  jmp     short loc_1801790A9
0x180179094  mov     edx, 32h ; '2'
0x180179099  jmp     short loc_180179090
0x18017909b  mov     edx, 2Ch ; ','
0x1801790a0  jmp     short loc_180179090
0x1801790a2  mov     edx, 27h ; '''; unsigned int
0x1801790a7  mov     ecx, ebx; int
0x1801790a9  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x1801790ae  lea     rcx, [rbp+arg_0]
0x1801790b2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801790b7  mov     eax, ebx
0x1801790b9  mov     rbx, [rsp+40h+arg_8]
0x1801790be  add     rsp, 40h
0x1801790c2  pop     rdi
0x1801790c3  pop     rsi
0x1801790c4  pop     rbp
0x1801790c5  retn
```
