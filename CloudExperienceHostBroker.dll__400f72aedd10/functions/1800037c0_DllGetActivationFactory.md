# DllGetActivationFactory

- ea: `0x1800037c0`
- end: `0x180003ad2`
- name: `DllGetActivationFactory`
- size: `786`
- prototype: `__int64 __fastcall(HSTRING string, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800037c0`
- `0x180009f30`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800037f9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800037f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003a81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003a81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000396a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000396a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003a5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003a73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003a5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003a73`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003a16`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003a16`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180003984`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180003984`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800039c6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003a28`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800039c6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003a28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18000382a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18000382a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003848`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003848`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180003814`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180003814`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800039e8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800039e8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180003ac1`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180003ac1`

## string_xrefs

- `0x180003a8c`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
  __int64 v12; // rdi
  int v13; // ebx
  PVOID v14; // rbx
  RTL_SRWLOCK *v16; // rsi
  void *v17; // rcx
  RTL_SRWLOCK *v18; // rsi
  void *v19; // rcx
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
  byte_18004E9C8 = 1;
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
          v22 = 1;
          v12 = *(_QWORD *)v5;
          *a2 = 0;
          Ptr = 0;
          if ( !**(_QWORD **)(v12 + 24) )
            goto LABEL_13;
          v18 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                    + 56))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
          AcquireSRWLockShared(v18);
          v19 = **(void ***)(v12 + 24);
          if ( v19 )
          {
            Ptr = DecodePointer(v19);
            v13 = (**(__int64 (__fastcall ***)(PVOID, GUID *, _QWORD *))Ptr)(
                    Ptr,
                    &GUID_00000035_0000_0000_c000_000000000046,
                    a2);
            if ( v18 )
              ReleaseSRWLockShared(v18);
          }
          else
          {
            if ( v18 )
              ReleaseSRWLockShared(v18);
LABEL_13:
            v13 = (*(__int64 (__fastcall **)(int *, __int64, GUID *, PVOID *))v12)(
                    &v22,
                    v12,
                    &GUID_00000035_0000_0000_c000_000000000046,
                    &Ptr);
            if ( v13 >= 0 )
            {
              if ( (v22 & 4) != 0 )
                goto LABEL_15;
              v16 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                        + 56))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
              AcquireSRWLockExclusive(v16);
              v17 = **(void ***)(v12 + 24);
              if ( v17 )
              {
                v14 = DecodePointer(v17);
                (*(void (__fastcall **)(PVOID))(*(_QWORD *)v14 + 8LL))(v14);
              }
              else
              {
                v14 = 0;
                **(_QWORD **)(v12 + 24) = EncodePointer(Ptr);
              }
              if ( v16 )
                ReleaseSRWLockExclusive(v16);
              if ( !v14 )
              {
LABEL_15:
                v14 = Ptr;
              }
              else
              {
                (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
                (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
              }
              *a2 = v14;
              return 0;
            }
          }
          return (unsigned int)v13;
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
0x1800037c0  mov     [rsp+arg_10], rbx
0x1800037c5  push    rbp
0x1800037c6  push    rsi
0x1800037c7  push    rdi
0x1800037c8  push    r14
0x1800037ca  push    r15
0x1800037cc  sub     rsp, 70h
0x1800037d0  mov     rax, cs:__security_cookie
0x1800037d7  xor     rax, rsp
0x1800037da  mov     [rsp+98h+var_30], rax
0x1800037df  mov     r14, rdx
0x1800037e2  mov     rbp, rcx
0x1800037e5  xor     r9d, r9d; Context
0x1800037e8  xor     r8d, r8d; Parameter
0x1800037eb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800037f2  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800037f9  call    cs:__imp_InitOnceExecuteOnce
0x1800037ff  mov     cs:byte_18004E9C8, 1
0x180003806  xor     r15d, r15d
0x180003809  mov     [r14], r15
0x18000380c  mov     [rsp+98h+hasEmbedNull], r15d
0x180003811  mov     rcx, rbp; string
0x180003814  call    cs:__imp_WindowsIsStringEmpty
0x18000381a  test    eax, eax
0x18000381c  jnz     loc_180003A8C
0x180003822  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180003827  mov     rcx, rbp; string
0x18000382a  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180003830  test    eax, eax
0x180003832  js      loc_180003A8C
0x180003838  cmp     [rsp+98h+hasEmbedNull], 1
0x18000383d  jz      loc_180003A8C
0x180003843  xor     edx, edx; length
0x180003845  mov     rcx, rbp; string
0x180003848  call    cs:__imp_WindowsGetStringRawBuffer
0x18000384e  mov     rsi, rax
0x180003851  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180003858  mov     rax, [rcx+28h]
0x18000385c  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180003863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003868  lea     rbx, [rax+8]
0x18000386c  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180003873  mov     rax, [rcx+30h]
0x180003877  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000387e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003883  mov     rdi, rax
0x180003886  cmp     rbx, rdi
0x180003889  jnb     loc_1800039E0
0x18000388f  mov     rax, [rbx]
0x180003892  test    rax, rax
0x180003895  jz      short loc_1800038CA
0x180003897  mov     rax, [rax+8]
0x18000389b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038a0  mov     rcx, rsi
0x1800038a3  sub     rax, rsi
0x1800038a6  nop     word ptr [rax+rax+00000000h]
0x1800038b0  movzx   r8d, word ptr [rcx]
0x1800038b4  movzx   edx, word ptr [rcx+rax]
0x1800038b8  sub     r8d, edx
0x1800038bb  jnz     short loc_1800038C5
0x1800038bd  add     rcx, 2
0x1800038c1  test    edx, edx
0x1800038c3  jnz     short loc_1800038B0
0x1800038c5  test    r8d, r8d
0x1800038c8  jz      short loc_1800038D0
0x1800038ca  add     rbx, 8
0x1800038ce  jmp     short loc_180003886
0x1800038d0  lfence
0x1800038d3  mov     [rsp+98h+var_5C], 1
0x1800038db  mov     rdi, [rbx]
0x1800038de  mov     [r14], r15
0x1800038e1  mov     [rsp+98h+Ptr], r15
0x1800038e6  mov     rax, [rdi+18h]
0x1800038ea  mov     rcx, [rax]
0x1800038ed  test    rcx, rcx
0x1800038f0  jnz     loc_1800039F9
0x1800038f6  lea     r9, [rsp+98h+Ptr]
0x1800038fb  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x180003902  mov     rdx, rdi
0x180003905  lea     rcx, [rsp+98h+var_5C]
0x18000390a  mov     rax, [rdi]
0x18000390d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003912  mov     ebx, eax
0x180003914  test    eax, eax
0x180003916  js      short loc_18000392A
0x180003918  test    byte ptr [rsp+98h+var_5C], 4
0x18000391d  jz      short loc_18000394D
0x18000391f  mov     rbx, [rsp+98h+Ptr]
0x180003924  mov     [r14], rbx
0x180003927  mov     ebx, r15d
0x18000392a  mov     eax, ebx
0x18000392c  mov     rcx, [rsp+98h+var_30]
0x180003931  xor     rcx, rsp; StackCookie
0x180003934  call    __security_check_cookie
0x180003939  mov     rbx, [rsp+98h+arg_10]
0x180003941  add     rsp, 70h
0x180003945  pop     r15
0x180003947  pop     r14
0x180003949  pop     rdi
0x18000394a  pop     rsi
0x18000394b  pop     rbp
0x18000394c  retn
0x18000394d  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180003954  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000395b  mov     rax, [rax+38h]
0x18000395f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003964  mov     rsi, rax
0x180003967  mov     rcx, rax; SRWLock
0x18000396a  call    cs:__imp_AcquireSRWLockExclusive
0x180003970  mov     rcx, [rdi+18h]
0x180003974  mov     rcx, [rcx]; Ptr
0x180003977  test    rcx, rcx
0x18000397a  jnz     short loc_1800039C6
0x18000397c  mov     rbx, r15
0x18000397f  mov     rcx, [rsp+98h+Ptr]; Ptr
0x180003984  call    cs:__imp_EncodePointer
0x18000398a  mov     rcx, [rdi+18h]
0x18000398e  mov     [rcx], rax
0x180003991  test    rsi, rsi
0x180003994  jnz     loc_180003A7E
0x18000399a  test    rbx, rbx
0x18000399d  jz      short loc_18000391F
0x18000399f  mov     rcx, [rsp+98h+Ptr]
0x1800039a4  mov     rax, [rcx]
0x1800039a7  mov     rax, [rax+10h]
0x1800039ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039b0  mov     rcx, [rsp+98h+Ptr]
0x1800039b5  mov     rax, [rcx]
0x1800039b8  mov     rax, [rax+10h]
0x1800039bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039c1  jmp     loc_180003924
0x1800039c6  call    cs:__imp_DecodePointer
0x1800039cc  mov     rbx, rax
0x1800039cf  mov     rcx, [rax]
0x1800039d2  mov     rax, [rcx+8]
0x1800039d6  mov     rcx, rbx
0x1800039d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039de  jmp     short loc_180003991
0x1800039e0  mov     rdx, rbp
0x1800039e3  mov     ecx, 80040111h
0x1800039e8  call    cs:__imp_RoOriginateError
0x1800039ee  nop
0x1800039ef  mov     eax, 80040111h
0x1800039f4  jmp     loc_18000392C
0x1800039f9  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180003a00  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180003a07  mov     rax, [rax+38h]
0x180003a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a10  mov     rsi, rax
0x180003a13  mov     rcx, rax; SRWLock
0x180003a16  call    cs:__imp_AcquireSRWLockShared
0x180003a1c  mov     rcx, [rdi+18h]
0x180003a20  mov     rcx, [rcx]; Ptr
0x180003a23  test    rcx, rcx
0x180003a26  jz      short loc_180003A67
0x180003a28  call    cs:__imp_DecodePointer
0x180003a2e  mov     r9, rax
0x180003a31  mov     [rsp+98h+Ptr], rax
0x180003a36  mov     rcx, [rax]
0x180003a39  mov     rax, [rcx]
0x180003a3c  mov     r8, r14
0x180003a3f  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180003a46  mov     rcx, r9
0x180003a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a4e  mov     ebx, eax
0x180003a50  test    rsi, rsi
0x180003a53  jz      loc_18000392A
0x180003a59  mov     rcx, rsi; SRWLock
0x180003a5c  call    cs:__imp_ReleaseSRWLockShared
0x180003a62  jmp     loc_18000392A
0x180003a67  test    rsi, rsi
0x180003a6a  jz      loc_1800038F6
0x180003a70  mov     rcx, rsi; SRWLock
0x180003a73  call    cs:__imp_ReleaseSRWLockShared
0x180003a79  jmp     loc_1800038F6
0x180003a7e  mov     rcx, rsi; SRWLock
0x180003a81  call    cs:__imp_ReleaseSRWLockExclusive
0x180003a87  jmp     loc_18000399A
0x180003a8c  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180003a93  movups  [rsp+98h+var_58], xmm0
0x180003a98  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180003a9f  movups  xmmword ptr [rsp+98h+var_48], xmm1
0x180003aa4  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180003aac  movsd   qword ptr [rsp+98h+var_48+0Eh], xmm0
0x180003ab2  lea     r8, [rsp+98h+var_58]
0x180003ab7  mov     edx, 12h
0x180003abc  mov     ecx, 80070057h
0x180003ac1  call    cs:__imp_RoOriginateErrorW
0x180003ac7  nop
0x180003ac8  mov     eax, 80070057h
0x180003acd  jmp     loc_18000392C
```
