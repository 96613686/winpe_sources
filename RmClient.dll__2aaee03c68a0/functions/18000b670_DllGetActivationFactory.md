# DllGetActivationFactory

- ea: `0x18000b670`
- end: `0x18000b990`
- name: `DllGetActivationFactory`
- size: `800`
- prototype: `__int64 __fastcall(HSTRING string, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b670`
- `0x18001aec0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000b6a6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000b6a6`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000b8f3`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000b8f3`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b7e9`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b923`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b7e9`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b923`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b7d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b7d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b908`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b908`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b819`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b961`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b819`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b961`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b8d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b8d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18000b6d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18000b6d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b707`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b707`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000b6c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000b6c1`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b945`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b945`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000b882`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000b882`

## string_xrefs

- `0x18000b84d`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(HSTRING string, _QWORD *a2)
{
  PCWSTR StringRawBuffer; // rsi
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rbx
  RTL_SRWLOCK *v13; // rdi
  void *v14; // rcx
  int v15; // esi
  RTL_SRWLOCK *v17; // rsi
  void *v18; // rcx
  PVOID v19; // rdi
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
  byte_18002ED98 = 1;
  *a2 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v23 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v24 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v24[14] = *(_QWORD *)L"sId";
    RoOriginateErrorW(2147942487LL, 18, &v23);
    return 2147942487LL;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                              + 40))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
       + 8;
    v6 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                              + 48))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
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
          *a2 = 0;
          Ptr = 0;
          if ( **(_QWORD **)(v12 + 24) )
          {
            v13 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                      + 56))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
            AcquireSRWLockShared(v13);
            v14 = **(void ***)(v12 + 24);
            if ( v14 )
            {
              Ptr = DecodePointer(v14);
              v15 = (**(__int64 (__fastcall ***)(PVOID, GUID *, _QWORD *))Ptr)(
                      Ptr,
                      &GUID_00000035_0000_0000_c000_000000000046,
                      a2);
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
              goto LABEL_26;
            v17 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                      + 56))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
            AcquireSRWLockExclusive(v17);
            v18 = **(void ***)(v12 + 24);
            if ( v18 )
            {
              v19 = DecodePointer(v18);
              (*(void (__fastcall **)(PVOID))(*(_QWORD *)v19 + 8LL))(v19);
            }
            else
            {
              v19 = 0;
              **(_QWORD **)(v12 + 24) = EncodePointer(Ptr);
            }
            if ( v17 )
              ReleaseSRWLockExclusive(v17);
            if ( v19 )
            {
              (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
              (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
            }
            else
            {
LABEL_26:
              v19 = Ptr;
            }
            *a2 = v19;
            return 0;
          }
          return (unsigned int)v15;
        }
      }
      v5 += 8LL;
    }
    RoOriginateError(2147746065LL, string);
    return 2147746065LL;
  }
}

```

## disassembly

```asm
0x18000b670  push    rbp
0x18000b672  push    r14
0x18000b674  push    r15
0x18000b676  sub     rsp, 80h
0x18000b67d  mov     rax, cs:__security_cookie
0x18000b684  xor     rax, rsp
0x18000b687  mov     [rsp+98h+var_30], rax
0x18000b68c  mov     r14, rdx
0x18000b68f  mov     rbp, rcx
0x18000b692  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000b699  xor     r9d, r9d; Context
0x18000b69c  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000b6a3  xor     r8d, r8d; Parameter
0x18000b6a6  call    cs:__imp_InitOnceExecuteOnce
0x18000b6ac  xor     r15d, r15d
0x18000b6af  mov     cs:byte_18002ED98, 1
0x18000b6b6  mov     rcx, rbp; string
0x18000b6b9  mov     [r14], r15
0x18000b6bc  mov     [rsp+98h+hasEmbedNull], r15d
0x18000b6c1  call    cs:__imp_WindowsIsStringEmpty
0x18000b6c7  test    eax, eax
0x18000b6c9  jnz     loc_18000B84D
0x18000b6cf  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x18000b6d4  mov     rcx, rbp; string
0x18000b6d7  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18000b6dd  test    eax, eax
0x18000b6df  js      loc_18000B84D
0x18000b6e5  cmp     [rsp+98h+hasEmbedNull], 1
0x18000b6ea  jz      loc_18000B84D
0x18000b6f0  mov     [rsp+98h+arg_10], rbx
0x18000b6f8  xor     edx, edx; length
0x18000b6fa  mov     [rsp+98h+var_20], rsi
0x18000b6ff  mov     rcx, rbp; string
0x18000b702  mov     [rsp+98h+var_28], rdi
0x18000b707  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b70d  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b714  mov     rsi, rax
0x18000b717  mov     rax, [rcx+28h]
0x18000b71b  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b727  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b72e  lea     rbx, [rax+8]
0x18000b732  mov     rax, [rcx+30h]
0x18000b736  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b742  mov     rdi, rax
0x18000b745  cmp     rbx, rdi
0x18000b748  jnb     loc_18000B93D
0x18000b74e  mov     rax, [rbx]
0x18000b751  test    rax, rax
0x18000b754  jz      short loc_18000B78A
0x18000b756  mov     rax, [rax+8]
0x18000b75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b75f  mov     rcx, rsi
0x18000b762  sub     rax, rsi
0x18000b765  nop     word ptr [rax+rax+00000000h]
0x18000b770  movzx   r8d, word ptr [rcx]
0x18000b774  movzx   edx, word ptr [rcx+rax]
0x18000b778  sub     r8d, edx
0x18000b77b  jnz     short loc_18000B785
0x18000b77d  add     rcx, 2
0x18000b781  test    edx, edx
0x18000b783  jnz     short loc_18000B770
0x18000b785  test    r8d, r8d
0x18000b788  jz      short loc_18000B790
0x18000b78a  add     rbx, 8
0x18000b78e  jmp     short loc_18000B745
0x18000b790  lfence
0x18000b793  mov     rbx, [rbx]
0x18000b796  mov     [rsp+98h+var_5C], 1
0x18000b79e  mov     [r14], r15
0x18000b7a1  mov     [rsp+98h+Ptr], r15
0x18000b7a6  mov     rax, [rbx+18h]
0x18000b7aa  mov     rcx, [rax]
0x18000b7ad  test    rcx, rcx
0x18000b7b0  jz      loc_18000B88F
0x18000b7b6  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b7bd  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b7c4  mov     rax, [rax+38h]
0x18000b7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7cd  mov     rcx, rax; SRWLock
0x18000b7d0  mov     rdi, rax
0x18000b7d3  call    cs:__imp_AcquireSRWLockShared
0x18000b7d9  mov     rcx, [rbx+18h]
0x18000b7dd  mov     rcx, [rcx]; Ptr
0x18000b7e0  test    rcx, rcx
0x18000b7e3  jz      loc_18000B955
0x18000b7e9  call    cs:__imp_DecodePointer
0x18000b7ef  mov     [rsp+98h+Ptr], rax
0x18000b7f4  mov     r8, r14
0x18000b7f7  mov     r9, rax
0x18000b7fa  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18000b801  mov     rcx, [rax]
0x18000b804  mov     rax, [rcx]
0x18000b807  mov     rcx, r9
0x18000b80a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b80f  mov     esi, eax
0x18000b811  test    rdi, rdi
0x18000b814  jz      short loc_18000B81F
0x18000b816  mov     rcx, rdi; SRWLock
0x18000b819  call    cs:__imp_ReleaseSRWLockShared
0x18000b81f  mov     eax, esi
0x18000b821  mov     rsi, [rsp+98h+var_20]
0x18000b826  mov     rbx, [rsp+98h+arg_10]
0x18000b82e  mov     rdi, [rsp+98h+var_28]
0x18000b833  mov     rcx, [rsp+98h+var_30]
0x18000b838  xor     rcx, rsp; StackCookie
0x18000b83b  call    __security_check_cookie
0x18000b840  add     rsp, 80h
0x18000b847  pop     r15
0x18000b849  pop     r14
0x18000b84b  pop     rbp
0x18000b84c  retn
0x18000b84d  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x18000b854  lea     r8, [rsp+98h+var_58]
0x18000b859  mov     edx, 12h
0x18000b85e  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x18000b865  mov     ecx, 80070057h
0x18000b86a  movups  [rsp+98h+var_58], xmm0
0x18000b86f  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x18000b877  movups  xmmword ptr [rsp+98h+var_48], xmm1
0x18000b87c  movsd   qword ptr [rsp+98h+var_48+0Eh], xmm0
0x18000b882  call    cs:__imp_RoOriginateErrorW
0x18000b888  mov     eax, 80070057h
0x18000b88d  jmp     short loc_18000B833
0x18000b88f  mov     rax, [rbx]
0x18000b892  lea     r9, [rsp+98h+Ptr]
0x18000b897  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x18000b89e  mov     rdx, rbx
0x18000b8a1  lea     rcx, [rsp+98h+var_5C]
0x18000b8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8ab  mov     esi, eax
0x18000b8ad  test    eax, eax
0x18000b8af  js      loc_18000B81F
0x18000b8b5  test    byte ptr [rsp+98h+var_5C], 4
0x18000b8ba  jnz     short loc_18000B913
0x18000b8bc  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b8c3  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b8ca  mov     rax, [rax+38h]
0x18000b8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8d3  mov     rcx, rax; SRWLock
0x18000b8d6  mov     rsi, rax
0x18000b8d9  call    cs:__imp_AcquireSRWLockExclusive
0x18000b8df  mov     rcx, [rbx+18h]
0x18000b8e3  mov     rcx, [rcx]; Ptr
0x18000b8e6  test    rcx, rcx
0x18000b8e9  jnz     short loc_18000B923
0x18000b8eb  mov     rcx, [rsp+98h+Ptr]; Ptr
0x18000b8f0  mov     rdi, r15
0x18000b8f3  call    cs:__imp_EncodePointer
0x18000b8f9  mov     rcx, [rbx+18h]
0x18000b8fd  mov     [rcx], rax
0x18000b900  test    rsi, rsi
0x18000b903  jz      short loc_18000B90E
0x18000b905  mov     rcx, rsi; SRWLock
0x18000b908  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b90e  test    rdi, rdi
0x18000b911  jnz     short loc_18000B96C
0x18000b913  mov     rdi, [rsp+98h+Ptr]
0x18000b918  mov     [r14], rdi
0x18000b91b  mov     esi, r15d
0x18000b91e  jmp     loc_18000B81F
0x18000b923  call    cs:__imp_DecodePointer
0x18000b929  mov     rdi, rax
0x18000b92c  mov     rcx, [rax]
0x18000b92f  mov     rax, [rcx+8]
0x18000b933  mov     rcx, rdi
0x18000b936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b93b  jmp     short loc_18000B900
0x18000b93d  mov     rdx, rbp
0x18000b940  mov     ecx, 80040111h
0x18000b945  call    cs:__imp_RoOriginateError
0x18000b94b  mov     eax, 80040111h
0x18000b950  jmp     loc_18000B821
0x18000b955  test    rdi, rdi
0x18000b958  jz      loc_18000B88F
0x18000b95e  mov     rcx, rdi; SRWLock
0x18000b961  call    cs:__imp_ReleaseSRWLockShared
0x18000b967  jmp     loc_18000B88F
0x18000b96c  mov     rcx, [rsp+98h+Ptr]
0x18000b971  mov     rax, [rcx]
0x18000b974  mov     rax, [rax+10h]
0x18000b978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b97d  mov     rcx, [rsp+98h+Ptr]
0x18000b982  mov     rax, [rcx]
0x18000b985  mov     rax, [rax+10h]
0x18000b989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b98e  jmp     short loc_18000B918
```
