# DllGetActivationFactory

- ea: `0x180004080`
- end: `0x180004394`
- name: `DllGetActivationFactory`
- size: `788`
- prototype: `HRESULT __fastcall(HSTRING__ *activatibleClassId, IActivationFactory **factory)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004080`
- `0x180020520`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800040b6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800040b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000428c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000428c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800042d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800042d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004225`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004238`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004225`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004238`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800041df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800041df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004117`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004117`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800040e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800040e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800040d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800040d1`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800041f1`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800042b5`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800041f1`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800042b5`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800042a6`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800042a6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180004387`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180004387`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004345`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004345`

## string_xrefs

- `0x180004352`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(HSTRING activatibleClassId, IActivationFactory **factory)
{
  PCWSTR StringRawBuffer; // rsi
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rdi
  _RTL_SRWLOCK *v13; // rsi
  void *v14; // rcx
  int v15; // ebx
  _RTL_SRWLOCK *v16; // rsi
  void *v17; // rcx
  IActivationFactory *v18; // rbx
  PVOID Ptr; // [rsp+30h] [rbp-68h] BYREF
  BOOL hasEmbedNull; // [rsp+38h] [rbp-60h] BYREF
  int v22; // [rsp+3Ch] [rbp-5Ch] BYREF
  __int128 v23; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v24[22]; // [rsp+50h] [rbp-48h]

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_.initialized_ = 1;
  *factory = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(activatibleClassId)
    || WindowsStringHasEmbeddedNull(activatibleClassId, &hasEmbedNull) < 0
    || hasEmbedNull )
  {
    v23 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v24 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v24[14] = *(_QWORD *)L"sId";
    RoOriginateErrorW(2147942487LL, 18, &v23);
    return 2147942487LL;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(activatibleClassId, 0);
    v5 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> *))(*(_QWORD *)Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_.data_ + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
       + 8;
    v6 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> *))(*(_QWORD *)Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_.data_ + 48LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
    while ( v5 < v6 )
    {
      if ( *(_QWORD *)v5 )
      {
        v7 = (*(__int64 (**)(void))(*(_QWORD *)v5 + 8LL))();
        v8 = (unsigned __int16 *)StringRawBuffer;
        v9 = v7 - (_QWORD)StringRawBuffer;
        do
        {
          v10 = *(unsigned __int16 *)((char *)v8 + v9);
          v11 = *v8 - v10;
          if ( v11 )
            break;
          ++v8;
        }
        while ( v10 );
        if ( !v11 )
        {
          _mm_lfence();
          v12 = *(_QWORD *)v5;
          v22 = 1;
          *factory = 0;
          Ptr = 0;
          if ( **(_QWORD **)(v12 + 24) )
          {
            v13 = (_RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> *))(*(_QWORD *)Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_.data_ + 56LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
            AcquireSRWLockShared(v13);
            v14 = **(void ***)(v12 + 24);
            if ( v14 )
            {
              Ptr = DecodePointer(v14);
              v15 = (**(__int64 (__fastcall ***)(PVOID, GUID *, IActivationFactory **))Ptr)(
                      Ptr,
                      &GUID_00000035_0000_0000_c000_000000000046,
                      factory);
              if ( v13 )
                ReleaseSRWLockShared(v13);
              return (unsigned int)v15;
            }
            if ( v13 )
              ReleaseSRWLockShared(v13);
          }
          v15 = (*(__int64 (__fastcall **)(int *, __int64, GUID *, PVOID *))v12)(
                  &v22,
                  v12,
                  &GUID_00000035_0000_0000_c000_000000000046,
                  &Ptr);
          if ( v15 >= 0 )
          {
            if ( (v22 & 4) != 0 )
              goto LABEL_27;
            v16 = (_RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> *))(*(_QWORD *)Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_.data_ + 56LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
            AcquireSRWLockExclusive(v16);
            v17 = **(void ***)(v12 + 24);
            if ( v17 )
            {
              v18 = (IActivationFactory *)DecodePointer(v17);
              v18->AddRef(v18);
            }
            else
            {
              v18 = 0;
              **(_QWORD **)(v12 + 24) = EncodePointer(Ptr);
            }
            if ( v16 )
              ReleaseSRWLockExclusive(v16);
            if ( !v18 )
            {
LABEL_27:
              v18 = (IActivationFactory *)Ptr;
            }
            else
            {
              (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
              (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
            }
            *factory = v18;
            return 0;
          }
          return (unsigned int)v15;
        }
      }
      v5 += 8LL;
    }
    RoOriginateError(2147746065LL, activatibleClassId);
    return 2147746065LL;
  }
}

```

## disassembly

```asm
0x180004080  push    rbp
0x180004082  push    r14
0x180004084  push    r15
0x180004086  sub     rsp, 80h
0x18000408d  mov     rax, cs:__security_cookie
0x180004094  xor     rax, rsp
0x180004097  mov     [rsp+98h+var_30], rax
0x18000409c  mov     r14, factory
0x18000409f  mov     rbp, activatibleClassId
0x1800040a2  lea     factory, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800040a9  xor     r9d, r9d; Context
0x1800040ac  lea     activatibleClassId, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800040b3  xor     r8d, r8d; Parameter
0x1800040b6  call    cs:__imp_InitOnceExecuteOnce
0x1800040bc  xor     r15d, r15d
0x1800040bf  mov     cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A.initialized_, 1
0x1800040c6  mov     activatibleClassId, rbp; string
0x1800040c9  mov     [r14], r15
0x1800040cc  mov     [rsp+98h+hasEmbedNull], r15d
0x1800040d1  call    cs:__imp_WindowsIsStringEmpty
0x1800040d7  test    eax, eax
0x1800040d9  jnz     loc_180004352
0x1800040df  lea     factory, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x1800040e4  mov     activatibleClassId, rbp; string
0x1800040e7  call    cs:__imp_WindowsStringHasEmbeddedNull
0x1800040ed  test    eax, eax
0x1800040ef  js      loc_180004352
0x1800040f5  cmp     [rsp+98h+hasEmbedNull], 1
0x1800040fa  jz      loc_180004352
0x180004100  mov     [rsp+98h+arg_10], rbx
0x180004108  xor     edx, edx; length
0x18000410a  mov     [rsp+98h+var_20], rsi
0x18000410f  mov     activatibleClassId, rbp; string
0x180004112  mov     [rsp+98h+var_28], rdi
0x180004117  call    cs:__imp_WindowsGetStringRawBuffer
0x18000411d  mov     activatibleClassId, qword ptr cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A.data_
0x180004124  mov     rsi, rax
0x180004127  mov     rax, [activatibleClassId+28h]
0x18000412b  lea     activatibleClassId, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A
0x180004132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004137  mov     activatibleClassId, qword ptr cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A.data_
0x18000413e  lea     rbx, [rax+8]
0x180004142  mov     rax, [activatibleClassId+30h]
0x180004146  lea     activatibleClassId, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A
0x18000414d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004152  mov     rdi, rax
0x180004155  cmp     rbx, rdi
0x180004158  jnb     loc_18000433D
0x18000415e  mov     rax, [rbx]
0x180004161  test    rax, rax
0x180004164  jz      short loc_18000419A
0x180004166  mov     rax, [rax+8]
0x18000416a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000416f  mov     activatibleClassId, rsi
0x180004172  sub     rax, rsi
0x180004175  nop     word ptr [rax+rax+00000000h]
0x180004180  movzx   r8d, word ptr [activatibleClassId]
0x180004184  movzx   edx, word ptr [activatibleClassId+rax]
0x180004188  sub     r8d, edx
0x18000418b  jnz     short loc_180004195
0x18000418d  add     activatibleClassId, 2
0x180004191  test    edx, edx
0x180004193  jnz     short loc_180004180
0x180004195  test    r8d, r8d
0x180004198  jz      short loc_1800041A0
0x18000419a  add     rbx, 8
0x18000419e  jmp     short loc_180004155
0x1800041a0  lfence
0x1800041a3  mov     rdi, [rbx]
0x1800041a6  mov     [rsp+98h+var_5C], 1
0x1800041ae  mov     [r14], r15
0x1800041b1  mov     [rsp+98h+Ptr], r15
0x1800041b6  mov     rax, [rdi+18h]
0x1800041ba  mov     activatibleClassId, [rax]
0x1800041bd  test    activatibleClassId, activatibleClassId
0x1800041c0  jz      short loc_18000423E
0x1800041c2  mov     rax, qword ptr cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A.data_
0x1800041c9  lea     activatibleClassId, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A
0x1800041d0  mov     rax, [rax+38h]
0x1800041d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041d9  mov     activatibleClassId, rax; SRWLock
0x1800041dc  mov     rsi, rax
0x1800041df  call    cs:__imp_AcquireSRWLockShared
0x1800041e5  mov     activatibleClassId, [rdi+18h]
0x1800041e9  mov     activatibleClassId, [activatibleClassId]; Ptr
0x1800041ec  test    activatibleClassId, activatibleClassId
0x1800041ef  jz      short loc_180004230
0x1800041f1  call    cs:__imp_DecodePointer
0x1800041f7  mov     [rsp+98h+Ptr], rax
0x1800041fc  mov     r8, r14
0x1800041ff  mov     r9, rax
0x180004202  lea     factory, _GUID_00000035_0000_0000_c000_000000000046
0x180004209  mov     activatibleClassId, [rax]
0x18000420c  mov     rax, [activatibleClassId]
0x18000420f  mov     activatibleClassId, r9
0x180004212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004217  mov     ebx, eax
0x180004219  test    rsi, rsi
0x18000421c  jz      loc_18000430F
0x180004222  mov     activatibleClassId, rsi; SRWLock
0x180004225  call    cs:__imp_ReleaseSRWLockShared
0x18000422b  jmp     loc_18000430F
0x180004230  test    rsi, rsi
0x180004233  jz      short loc_18000423E
0x180004235  mov     activatibleClassId, rsi; SRWLock
0x180004238  call    cs:__imp_ReleaseSRWLockShared
0x18000423e  mov     rax, [rdi]
0x180004241  lea     r9, [rsp+98h+Ptr]
0x180004246  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x18000424d  mov     factory, rdi
0x180004250  lea     activatibleClassId, [rsp+98h+var_5C]
0x180004255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000425a  mov     ebx, eax
0x18000425c  test    eax, eax
0x18000425e  js      loc_18000430F
0x180004264  test    byte ptr [rsp+98h+var_5C], 4
0x180004269  jnz     loc_180004304
0x18000426f  mov     rax, qword ptr cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A.data_
0x180004276  lea     activatibleClassId, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A
0x18000427d  mov     rax, [rax+38h]
0x180004281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004286  mov     activatibleClassId, rax; SRWLock
0x180004289  mov     rsi, rax
0x18000428c  call    cs:__imp_AcquireSRWLockExclusive
0x180004292  mov     activatibleClassId, [rdi+18h]
0x180004296  mov     activatibleClassId, [activatibleClassId]; Ptr
0x180004299  test    activatibleClassId, activatibleClassId
0x18000429c  jnz     short loc_1800042B5
0x18000429e  mov     activatibleClassId, [rsp+98h+Ptr]; Ptr
0x1800042a3  mov     rbx, r15
0x1800042a6  call    cs:__imp_EncodePointer
0x1800042ac  mov     activatibleClassId, [rdi+18h]
0x1800042b0  mov     [activatibleClassId], rax
0x1800042b3  jmp     short loc_1800042CD
0x1800042b5  call    cs:__imp_DecodePointer
0x1800042bb  mov     rbx, rax
0x1800042be  mov     activatibleClassId, [rax]
0x1800042c1  mov     rax, [activatibleClassId+8]
0x1800042c5  mov     activatibleClassId, rbx
0x1800042c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042cd  test    rsi, rsi
0x1800042d0  jz      short loc_1800042DB
0x1800042d2  mov     activatibleClassId, rsi; SRWLock
0x1800042d5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800042db  test    rbx, rbx
0x1800042de  jz      short loc_180004304
0x1800042e0  mov     activatibleClassId, [rsp+98h+Ptr]
0x1800042e5  mov     rax, [activatibleClassId]
0x1800042e8  mov     rax, [rax+10h]
0x1800042ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042f1  mov     activatibleClassId, [rsp+98h+Ptr]
0x1800042f6  mov     rax, [activatibleClassId]
0x1800042f9  mov     rax, [rax+10h]
0x1800042fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004302  jmp     short loc_180004309
0x180004304  mov     rbx, [rsp+98h+Ptr]
0x180004309  mov     [r14], rbx
0x18000430c  mov     ebx, r15d
0x18000430f  mov     eax, ebx
0x180004311  mov     rsi, [rsp+98h+var_20]
0x180004316  mov     rbx, [rsp+98h+arg_10]
0x18000431e  mov     rdi, [rsp+98h+var_28]
0x180004323  mov     activatibleClassId, [rsp+98h+var_30]
0x180004328  xor     activatibleClassId, rsp; StackCookie
0x18000432b  call    __security_check_cookie
0x180004330  add     rsp, 80h
0x180004337  pop     r15
0x180004339  pop     r14
0x18000433b  pop     rbp
0x18000433c  retn
0x18000433d  mov     factory, rbp
0x180004340  mov     ecx, 80040111h
0x180004345  call    cs:__imp_RoOriginateError
0x18000434b  mov     eax, 80040111h
0x180004350  jmp     short loc_180004311
0x180004352  movups  xmm0, xmmword ptr cs:aActivatiblecla
0x180004359  lea     r8, [rsp+98h+var_58]
0x18000435e  mov     edx, 12h
0x180004363  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h
0x18000436a  mov     ecx, 80070057h
0x18000436f  movups  [rsp+98h+var_58], xmm0
0x180004374  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh
0x18000437c  movups  xmmword ptr [rsp+98h+var_48], xmm1
0x180004381  movsd   qword ptr [rsp+98h+var_48+0Eh], xmm0
0x180004387  call    cs:__imp_RoOriginateErrorW
0x18000438d  mov     eax, 80070057h
0x180004392  jmp     short loc_180004323
```
