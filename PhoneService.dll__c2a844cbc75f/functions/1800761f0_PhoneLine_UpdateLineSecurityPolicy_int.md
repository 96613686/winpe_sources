# PhoneLine::UpdateLineSecurityPolicy(int)

- ea: `0x1800761f0`
- end: `0x18007642f`
- name: `?UpdateLineSecurityPolicy@PhoneLine@@UEAAJH@Z`
- size: `575`
- prototype: `__int64 __fastcall(PhoneLine *__hidden this, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180006e94`
- `0x180070030`
- `0x180071ba8`
- `0x1800761f0`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076217`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076217`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800763d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800763d9`
- `PhoneUtil!CreatePerUserSecurityPolicy` at `0x180076350`
- `PhoneUtil!CreatePerUserSecurityPolicy` at `0x1800763fe`
- `PhoneUtil!CreatePerUserSecurityPolicy` at `0x180076350`
- `PhoneUtil!CreatePerUserSecurityPolicy` at `0x1800763fe`

## string_xrefs

- `0x180076247`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x1800762db`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x180076369`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x180076417`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`

## pseudocode

```c
__int64 __fastcall PhoneLine::UpdateLineSecurityPolicy(PhoneLine *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  int v5; // eax
  BackTraceCollection *v6; // rcx
  unsigned int v7; // ebx
  struct ISecurityPolicy **v8; // rdi
  struct ISecurityPolicy *v9; // rcx
  __int64 v10; // rbx
  int v11; // eax
  BackTraceCollection *v12; // rcx
  unsigned int v13; // esi
  __int64 v14; // r9
  int v15; // eax
  BackTraceCollection *v16; // rcx
  int PerUserSecurityPolicy; // eax
  BackTraceCollection *v18; // rcx
  unsigned int v19; // edi
  int v21; // eax
  BackTraceCollection *v22; // rcx
  __int64 v23; // [rsp+30h] [rbp-38h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v23 = 0;
  v5 = WrappedComPtrBase<IPhoneLine,SupportsShutdown,utl::recursive_mutex>::Get((char *)this + 24, &v23);
  v7 = v5;
  if ( v5 < 0 )
  {
    BackTraceCollection::Capture(v6, v5);
    Log_HREvent_19(v7, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1901);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    goto LABEL_26;
  }
  v8 = (struct ISecurityPolicy **)((char *)this + 96);
  v9 = *v8;
  if ( *v8 )
  {
    *v8 = 0;
    (*(void (__fastcall **)(struct ISecurityPolicy *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v10 = v23;
  if ( a2 )
  {
    v23 = 0;
    v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v10)(
            v10,
            &GUID_0f31a217_5ed9_4ff1_9ba3_0ba38d781483,
            &v23);
    v13 = v11;
    if ( v11 < 0 )
    {
      BackTraceCollection::Capture(v12, v11);
      v14 = 1907;
LABEL_9:
      Log_HREvent_19(v13, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", v14);
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v7 = v13;
      goto LABEL_26;
    }
    v15 = (*(__int64 (__fastcall **)(__int64, struct ISecurityPolicy **))(*(_QWORD *)v23 + 24LL))(v23, v8);
    v13 = v15;
    if ( v15 < 0 )
    {
      BackTraceCollection::Capture(v16, v15);
      v14 = 1908;
      goto LABEL_9;
    }
    if ( !*v8 )
    {
      PerUserSecurityPolicy = CreatePerUserSecurityPolicy(0, 0, v8);
      v19 = PerUserSecurityPolicy;
      if ( PerUserSecurityPolicy < 0 )
      {
        BackTraceCollection::Capture(v18, PerUserSecurityPolicy);
        Log_HREvent_19(v19, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1913);
        if ( v23 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        goto LABEL_18;
      }
    }
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  else
  {
    v21 = CreatePerUserSecurityPolicy(0, 0, v8);
    v19 = v21;
    if ( v21 < 0 )
    {
      BackTraceCollection::Capture(v22, v21);
      Log_HREvent_19(v19, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1918);
LABEL_18:
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v7 = v19;
      goto LABEL_26;
    }
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v7 = 0;
LABEL_26:
  LeaveCriticalSection(v2);
  return v7;
}

```

## disassembly

```asm
0x1800761f0  push    rbx
0x1800761f2  push    rbp
0x1800761f3  push    rsi
0x1800761f4  push    rdi
0x1800761f5  sub     rsp, 48h
0x1800761f9  mov     rax, cs:__security_cookie
0x180076200  xor     rax, rsp
0x180076203  mov     [rsp+68h+var_30], rax
0x180076208  lea     rbp, [rcx+80h]
0x18007620f  mov     rdi, rcx
0x180076212  mov     rcx, rbp; lpCriticalSection
0x180076215  mov     esi, edx
0x180076217  call    cs:__imp_EnterCriticalSection
0x18007621d  lea     rcx, [rdi+18h]
0x180076221  mov     [rsp+68h+var_38], 0
0x18007622a  lea     rdx, [rsp+68h+var_38]
0x18007622f  call    ?Get@?$WrappedComPtrBase@UIPhoneLine@@VSupportsShutdown@@Vrecursive_mutex@utl@@@@QEAAJPEAPEAUIPhoneLine@@@Z; WrappedComPtrBase<IPhoneLine,SupportsShutdown,utl::recursive_mutex>::Get(IPhoneLine * *)
0x180076234  mov     ebx, eax
0x180076236  test    eax, eax
0x180076238  jns     short loc_180076279
0x18007623a  mov     edx, eax; int
0x18007623c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180076241  mov     r9d, 76Dh
0x180076247  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18007624e  mov     edx, 1
0x180076253  mov     ecx, ebx
0x180076255  call    Log_HREvent_19
0x18007625a  mov     rcx, [rsp+68h+var_38]
0x18007625f  test    rcx, rcx
0x180076262  jz      loc_1800763D6
0x180076268  mov     rax, [rcx]
0x18007626b  mov     rax, [rax+10h]
0x18007626f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076274  jmp     loc_1800763D6
0x180076279  add     rdi, 60h ; '`'
0x18007627d  mov     rcx, [rdi]
0x180076280  test    rcx, rcx
0x180076283  jz      short loc_180076298
0x180076285  mov     qword ptr [rdi], 0
0x18007628c  mov     rax, [rcx]
0x18007628f  mov     rax, [rax+10h]
0x180076293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076298  mov     rbx, [rsp+68h+var_38]
0x18007629d  test    esi, esi
0x18007629f  jz      loc_1800763F7
0x1800762a5  mov     [rsp+68h+var_38], 0
0x1800762ae  lea     r8, [rsp+68h+var_38]
0x1800762b3  mov     rax, [rbx]
0x1800762b6  lea     rdx, _GUID_0f31a217_5ed9_4ff1_9ba3_0ba38d781483
0x1800762bd  mov     rcx, rbx
0x1800762c0  mov     rax, [rax]
0x1800762c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800762c8  mov     esi, eax
0x1800762ca  test    eax, eax
0x1800762cc  jns     short loc_18007631A
0x1800762ce  mov     edx, eax; int
0x1800762d0  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800762d5  mov     r9d, 773h
0x1800762db  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800762e2  mov     edx, 1
0x1800762e7  mov     ecx, esi
0x1800762e9  call    Log_HREvent_19
0x1800762ee  mov     rcx, [rsp+68h+var_38]
0x1800762f3  test    rcx, rcx
0x1800762f6  jz      short loc_180076304
0x1800762f8  mov     rax, [rcx]
0x1800762fb  mov     rax, [rax+10h]
0x1800762ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076304  mov     rax, [rbx]
0x180076307  mov     rcx, rbx
0x18007630a  mov     rax, [rax+10h]
0x18007630e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076313  mov     ebx, esi
0x180076315  jmp     loc_1800763D6
0x18007631a  mov     rcx, [rsp+68h+var_38]
0x18007631f  mov     rdx, rdi
0x180076322  mov     rax, [rcx]
0x180076325  mov     rax, [rax+18h]
0x180076329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007632e  mov     esi, eax
0x180076330  test    eax, eax
0x180076332  jns     short loc_180076343
0x180076334  mov     edx, eax; int
0x180076336  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18007633b  mov     r9d, 774h
0x180076341  jmp     short loc_1800762DB
0x180076343  cmp     qword ptr [rdi], 0
0x180076347  jnz     short loc_1800763AA
0x180076349  mov     r8, rdi
0x18007634c  xor     edx, edx
0x18007634e  xor     ecx, ecx
0x180076350  call    cs:__imp_?CreatePerUserSecurityPolicy@@YAJPEBQEAXIPEAPEAUISecurityPolicy@@@Z; CreatePerUserSecurityPolicy(void * const *,uint,ISecurityPolicy * *)
0x180076356  mov     edi, eax
0x180076358  test    eax, eax
0x18007635a  jns     short loc_1800763AA
0x18007635c  mov     edx, eax; int
0x18007635e  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180076363  mov     r9d, 779h
0x180076369  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180076370  mov     edx, 1
0x180076375  mov     ecx, edi
0x180076377  call    Log_HREvent_19
0x18007637c  mov     rcx, [rsp+68h+var_38]
0x180076381  test    rcx, rcx
0x180076384  jz      short loc_180076392
0x180076386  mov     rax, [rcx]
0x180076389  mov     rax, [rax+10h]
0x18007638d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076392  test    rbx, rbx
0x180076395  jz      short loc_1800763A6
0x180076397  mov     rax, [rbx]
0x18007639a  mov     rcx, rbx
0x18007639d  mov     rax, [rax+10h]
0x1800763a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800763a6  mov     ebx, edi
0x1800763a8  jmp     short loc_1800763D6
0x1800763aa  mov     rcx, [rsp+68h+var_38]
0x1800763af  test    rcx, rcx
0x1800763b2  jz      short loc_1800763C0
0x1800763b4  mov     rax, [rcx]
0x1800763b7  mov     rax, [rax+10h]
0x1800763bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800763c0  test    rbx, rbx
0x1800763c3  jz      short loc_1800763D4
0x1800763c5  mov     rax, [rbx]
0x1800763c8  mov     rcx, rbx
0x1800763cb  mov     rax, [rax+10h]
0x1800763cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800763d4  xor     ebx, ebx
0x1800763d6  mov     rcx, rbp; lpCriticalSection
0x1800763d9  call    cs:__imp_LeaveCriticalSection
0x1800763df  mov     eax, ebx
0x1800763e1  mov     rcx, [rsp+68h+var_30]
0x1800763e6  xor     rcx, rsp; StackCookie
0x1800763e9  call    __security_check_cookie
0x1800763ee  add     rsp, 48h
0x1800763f2  pop     rdi
0x1800763f3  pop     rsi
0x1800763f4  pop     rbp
0x1800763f5  pop     rbx
0x1800763f6  retn
0x1800763f7  mov     r8, rdi
0x1800763fa  xor     edx, edx
0x1800763fc  xor     ecx, ecx
0x1800763fe  call    cs:__imp_?CreatePerUserSecurityPolicy@@YAJPEBQEAXIPEAPEAUISecurityPolicy@@@Z; CreatePerUserSecurityPolicy(void * const *,uint,ISecurityPolicy * *)
0x180076404  mov     edi, eax
0x180076406  test    eax, eax
0x180076408  jns     short loc_1800763C0
0x18007640a  mov     edx, eax; int
0x18007640c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180076411  mov     r9d, 77Eh
0x180076417  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18007641e  mov     edx, 1
0x180076423  mov     ecx, edi
0x180076425  call    Log_HREvent_19
0x18007642a  jmp     loc_180076392
```
