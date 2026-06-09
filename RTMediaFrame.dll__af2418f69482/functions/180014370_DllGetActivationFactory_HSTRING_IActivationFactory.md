# DllGetActivationFactory(HSTRING__ *,IActivationFactory * *)

- ea: `0x180014370`
- end: `0x180014676`
- name: `?DllGetActivationFactory@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `774`
- prototype: `__int64 __fastcall(HSTRING string, struct IActivationFactory **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180014370`
- `0x180026920`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001457e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001457e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180014568`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180014568`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800145d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800145d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014605`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014605`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014509`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014646`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014509`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014646`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800144c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800144c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800143da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800143da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800143c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800143c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800143f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800143f8`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800145f0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800145f0`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800144d9`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180014620`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800144d9`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180014620`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800143a9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800143a9`

## string_xrefs

- `0x180014533`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DllGetActivationFactory(HSTRING string, struct IActivationFactory **a2)
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
  RTL_SRWLOCK *v13; // rbx
  void *v14; // rcx
  int v15; // esi
  RTL_SRWLOCK *v17; // rsi
  void *v18; // rcx
  struct IActivationFactory *v19; // rbx
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
  byte_180072D28 = 1;
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
          if ( **(_QWORD **)(v12 + 24) )
          {
            v13 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                      + 56))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
            AcquireSRWLockShared(v13);
            v14 = **(void ***)(v12 + 24);
            if ( v14 )
            {
              Ptr = DecodePointer(v14);
              v15 = (**(__int64 (__fastcall ***)(PVOID, GUID *, struct IActivationFactory **))Ptr)(
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
              v19 = (struct IActivationFactory *)DecodePointer(v18);
              (*(void (__fastcall **)(struct IActivationFactory *))(*(_QWORD *)v19 + 8LL))(v19);
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
              v19 = (struct IActivationFactory *)Ptr;
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
0x180014370  mov     [rsp+arg_10], rbx
0x180014375  push    rbp
0x180014376  push    rsi
0x180014377  push    rdi
0x180014378  push    r14
0x18001437a  push    r15
0x18001437c  sub     rsp, 70h
0x180014380  mov     rax, cs:__security_cookie
0x180014387  xor     rax, rsp
0x18001438a  mov     [rsp+98h+var_30], rax
0x18001438f  mov     r14, rdx
0x180014392  mov     rbp, rcx
0x180014395  xor     r9d, r9d; Context
0x180014398  xor     r8d, r8d; Parameter
0x18001439b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800143a2  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800143a9  call    cs:__imp_InitOnceExecuteOnce
0x1800143af  mov     cs:byte_180072D28, 1
0x1800143b6  xor     r15d, r15d
0x1800143b9  mov     [r14], r15
0x1800143bc  mov     [rsp+98h+hasEmbedNull], r15d
0x1800143c1  mov     rcx, rbp; string
0x1800143c4  call    cs:__imp_WindowsIsStringEmpty
0x1800143ca  test    eax, eax
0x1800143cc  jnz     loc_180014533
0x1800143d2  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x1800143d7  mov     rcx, rbp; string
0x1800143da  call    cs:__imp_WindowsStringHasEmbeddedNull
0x1800143e0  test    eax, eax
0x1800143e2  js      loc_180014533
0x1800143e8  cmp     [rsp+98h+hasEmbedNull], 1
0x1800143ed  jz      loc_180014533
0x1800143f3  xor     edx, edx; length
0x1800143f5  mov     rcx, rbp; string
0x1800143f8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800143fe  mov     rsi, rax
0x180014401  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180014408  mov     rax, [rcx+28h]
0x18001440c  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180014413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014418  lea     rbx, [rax+8]
0x18001441c  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180014423  mov     rax, [rcx+30h]
0x180014427  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18001442e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014433  mov     rdi, rax
0x180014436  cmp     rbx, rdi
0x180014439  jnb     loc_180014576
0x18001443f  mov     rax, [rbx]
0x180014442  test    rax, rax
0x180014445  jz      short loc_18001447A
0x180014447  mov     rax, [rax+8]
0x18001444b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014450  mov     rcx, rsi
0x180014453  sub     rax, rsi
0x180014456  nop     word ptr [rax+rax+00000000h]
0x180014460  movzx   r8d, word ptr [rcx]
0x180014464  movzx   edx, word ptr [rcx+rax]
0x180014468  sub     r8d, edx
0x18001446b  jnz     short loc_180014475
0x18001446d  add     rcx, 2
0x180014471  test    edx, edx
0x180014473  jnz     short loc_180014460
0x180014475  test    r8d, r8d
0x180014478  jz      short loc_180014480
0x18001447a  add     rbx, 8
0x18001447e  jmp     short loc_180014436
0x180014480  lfence
0x180014483  mov     [rsp+98h+var_5C], 1
0x18001448b  mov     rdi, [rbx]
0x18001448e  mov     [r14], r15
0x180014491  mov     [rsp+98h+Ptr], r15
0x180014496  mov     rax, [rdi+18h]
0x18001449a  mov     rcx, [rax]
0x18001449d  test    rcx, rcx
0x1800144a0  jz      loc_18001458C
0x1800144a6  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800144ad  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800144b4  mov     rax, [rax+38h]
0x1800144b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144bd  mov     rbx, rax
0x1800144c0  mov     rcx, rax; SRWLock
0x1800144c3  call    cs:__imp_AcquireSRWLockShared
0x1800144c9  mov     rcx, [rdi+18h]
0x1800144cd  mov     rcx, [rcx]; Ptr
0x1800144d0  test    rcx, rcx
0x1800144d3  jz      loc_18001463A
0x1800144d9  call    cs:__imp_DecodePointer
0x1800144df  mov     r9, rax
0x1800144e2  mov     [rsp+98h+Ptr], rax
0x1800144e7  mov     rcx, [rax]
0x1800144ea  mov     rax, [rcx]
0x1800144ed  mov     r8, r14
0x1800144f0  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x1800144f7  mov     rcx, r9
0x1800144fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144ff  mov     esi, eax
0x180014501  test    rbx, rbx
0x180014504  jz      short loc_180014510
0x180014506  mov     rcx, rbx; SRWLock
0x180014509  call    cs:__imp_ReleaseSRWLockShared
0x18001450f  nop
0x180014510  mov     eax, esi
0x180014512  mov     rcx, [rsp+98h+var_30]
0x180014517  xor     rcx, rsp; StackCookie
0x18001451a  call    __security_check_cookie
0x18001451f  mov     rbx, [rsp+98h+arg_10]
0x180014527  add     rsp, 70h
0x18001452b  pop     r15
0x18001452d  pop     r14
0x18001452f  pop     rdi
0x180014530  pop     rsi
0x180014531  pop     rbp
0x180014532  retn
0x180014533  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x18001453a  movups  [rsp+98h+var_58], xmm0
0x18001453f  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180014546  movups  xmmword ptr [rsp+98h+var_48], xmm1
0x18001454b  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180014553  movsd   qword ptr [rsp+98h+var_48+0Eh], xmm0
0x180014559  lea     r8, [rsp+98h+var_58]
0x18001455e  mov     edx, 12h
0x180014563  mov     ecx, 80070057h
0x180014568  call    cs:__imp_RoOriginateErrorW
0x18001456e  nop
0x18001456f  mov     eax, 80070057h
0x180014574  jmp     short loc_180014512
0x180014576  mov     rdx, rbp
0x180014579  mov     ecx, 80040111h
0x18001457e  call    cs:__imp_RoOriginateError
0x180014584  nop
0x180014585  mov     eax, 80040111h
0x18001458a  jmp     short loc_180014512
0x18001458c  lea     r9, [rsp+98h+Ptr]
0x180014591  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x180014598  mov     rdx, rdi
0x18001459b  lea     rcx, [rsp+98h+var_5C]
0x1800145a0  mov     rax, [rdi]
0x1800145a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145a8  mov     esi, eax
0x1800145aa  test    eax, eax
0x1800145ac  js      loc_180014510
0x1800145b2  test    byte ptr [rsp+98h+var_5C], 4
0x1800145b7  jnz     short loc_180014610
0x1800145b9  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800145c0  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800145c7  mov     rax, [rax+38h]
0x1800145cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145d0  mov     rsi, rax
0x1800145d3  mov     rcx, rax; SRWLock
0x1800145d6  call    cs:__imp_AcquireSRWLockExclusive
0x1800145dc  mov     rcx, [rdi+18h]
0x1800145e0  mov     rcx, [rcx]; Ptr
0x1800145e3  test    rcx, rcx
0x1800145e6  jnz     short loc_180014620
0x1800145e8  mov     rbx, r15
0x1800145eb  mov     rcx, [rsp+98h+Ptr]; Ptr
0x1800145f0  call    cs:__imp_EncodePointer
0x1800145f6  mov     rcx, [rdi+18h]
0x1800145fa  mov     [rcx], rax
0x1800145fd  test    rsi, rsi
0x180014600  jz      short loc_18001460B
0x180014602  mov     rcx, rsi; SRWLock
0x180014605  call    cs:__imp_ReleaseSRWLockExclusive
0x18001460b  test    rbx, rbx
0x18001460e  jnz     short loc_180014651
0x180014610  mov     rbx, [rsp+98h+Ptr]
0x180014615  mov     [r14], rbx
0x180014618  mov     esi, r15d
0x18001461b  jmp     loc_180014510
0x180014620  call    cs:__imp_DecodePointer
0x180014626  mov     rbx, rax
0x180014629  mov     rcx, [rax]
0x18001462c  mov     rax, [rcx+8]
0x180014630  mov     rcx, rbx
0x180014633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014638  jmp     short loc_1800145FD
0x18001463a  test    rbx, rbx
0x18001463d  jz      loc_18001458C
0x180014643  mov     rcx, rbx; SRWLock
0x180014646  call    cs:__imp_ReleaseSRWLockShared
0x18001464c  jmp     loc_18001458C
0x180014651  mov     rcx, [rsp+98h+Ptr]
0x180014656  mov     rax, [rcx]
0x180014659  mov     rax, [rax+10h]
0x18001465d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014662  mov     rcx, [rsp+98h+Ptr]
0x180014667  mov     rax, [rcx]
0x18001466a  mov     rax, [rax+10h]
0x18001466e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014673  jmp     short loc_180014615
```
