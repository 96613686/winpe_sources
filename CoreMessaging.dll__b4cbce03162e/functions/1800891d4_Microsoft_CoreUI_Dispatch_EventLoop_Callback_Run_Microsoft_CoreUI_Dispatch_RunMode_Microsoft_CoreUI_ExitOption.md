# Microsoft::CoreUI::Dispatch::EventLoop::Callback_Run(Microsoft::CoreUI::Dispatch::RunMode,Microsoft::CoreUI::ExitOptions,bool *)

- ea: `0x1800891d4`
- end: `0x1800893bb`
- name: `?Callback_Run@EventLoop@Dispatch@CoreUI@Microsoft@@AEAAXW4RunMode@234@W4ExitOptions@34@PEA_N@Z`
- size: `487`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180070d50`
- `0x180083c00`
- `0x180089010`
- `0x1800891c0`

## callees

- `0x18000ec10`
- `0x1800111dc`
- `0x180011cec`
- `0x18007abdc`
- `0x18007e8ec`
- `0x1800891d4`
- `0x1800893c4`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089200`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089200`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall Microsoft::CoreUI::Dispatch::EventLoop::Callback_Run(__int64 a1, int a2, int a3, __int64 a4)
{
  __int64 v8; // rbx
  System::Exception *v9; // rcx
  System::Exception *v10; // rcx
  int v11; // eax
  char v12; // r14
  __int64 v13; // rax
  __int64 v14; // r15
  _DWORD *v15; // r12
  _DWORD *v16; // r13
  __int64 *v17; // rax
  System::Object *v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rdx
  int v22; // [rsp+30h] [rbp-A8h] BYREF
  int v23; // [rsp+34h] [rbp-A4h] BYREF
  System::Exception *v24; // [rsp+38h] [rbp-A0h] BYREF
  __int64 *v25; // [rsp+40h] [rbp-98h] BYREF
  __int64 v26; // [rsp+48h] [rbp-90h] BYREF
  char v27; // [rsp+50h] [rbp-88h]
  __int64 v28; // [rsp+58h] [rbp-80h]
  _DWORD *v29; // [rsp+60h] [rbp-78h]
  _DWORD *v30; // [rsp+68h] [rbp-70h]
  System::Exception *v31; // [rsp+70h] [rbp-68h]
  __int64 *v32; // [rsp+78h] [rbp-60h]
  System::Object *v33; // [rsp+80h] [rbp-58h]
  char v34; // [rsp+88h] [rbp-50h] BYREF
  int v35; // [rsp+E0h] [rbp+8h] BYREF

  v8 = *(_QWORD *)(a1 + 48);
  if ( GetCurrentThreadId() != *(_DWORD *)(v8 + 176) )
  {
    v9 = *(System::Exception **)Microsoft::CoreUI::Messaging::MessagingValidationException::get_IncorrectThread(&v25);
    System::Exception::Throw$(v9);
  }
  if ( a2 != 1 && a2 != 2 && a2 != 3 && (unsigned int)(a2 - 4) >= 2 )
  {
    v10 = *(System::Exception **)Microsoft::CoreUI::ValidationException::get_ArgumentInvalid(&v25);
    System::Exception::Throw$(v10);
  }
  v11 = *(_DWORD *)(a1 + 64);
  if ( v11 || (v12 = 0, *(_DWORD *)(a1 + 72)) )
    v12 = 1;
  if ( *(_BYTE *)(a1 + 32) )
  {
LABEL_14:
    if ( v12 )
      goto LABEL_16;
    goto LABEL_15;
  }
  if ( v12 )
  {
    Microsoft::CoreUI::Messaging::MessagingValidationException::FromResult(&v24, 2);
    System::Exception::Throw$(v24);
    goto LABEL_14;
  }
LABEL_15:
  *(_BYTE *)(a1 + 80) = 0;
LABEL_16:
  v23 = v11;
  v22 = *(_DWORD *)(a1 + 68);
  v35 = *(_DWORD *)(a1 + 84);
  v26 = *(_QWORD *)(a1 + 88);
  *(_DWORD *)(a1 + 64) = 1;
  *(_DWORD *)(a1 + 68) = a2;
  *(_DWORD *)(a1 + 84) = a3;
  *(_QWORD *)(a1 + 88) = a4;
  v27 = 0;
  v13 = lambda_bfcd5ef1e675e352cb06890cc36b3edf_::_lambda_bfcd5ef1e675e352cb06890cc36b3edf_(
          (unsigned int)&v34,
          a1,
          (unsigned int)&v23,
          (unsigned int)&v22,
          (__int64)&v35,
          (__int64)&v26);
  v14 = *(_QWORD *)v13;
  v28 = *(_QWORD *)v13;
  v15 = *(_DWORD **)(v13 + 8);
  v29 = v15;
  v16 = *(_DWORD **)(v13 + 16);
  v30 = v16;
  v24 = *(System::Exception **)(v13 + 24);
  v31 = v24;
  v17 = *(__int64 **)(v13 + 32);
  v25 = v17;
  v32 = v17;
  v18 = *(System::Object **)(a1 + 168);
  v33 = v18;
  if ( v18 )
    ++*((_DWORD *)v18 + 4);
  try
  {
    (*(void (**)(void))(*(_QWORD *)v18 + 80LL))();
    if ( v18 )
      System::Object::ReleaseNotFrozen$(v18);
    *(_DWORD *)(v14 + 64) = *v15;
    *(_DWORD *)(v14 + 68) = *v16;
    *(_DWORD *)(v14 + 84) = *(_DWORD *)v24;
    v19 = *v25;
    *(_QWORD *)(v14 + 88) = *v25;
    if ( !v12 )
    {
      LOBYTE(v19) = (unsigned int)(a2 - 3) <= 1;
      *(_BYTE *)(a1 + 80) = v19;
    }
  }
  catch ( ... )
  {
    v27 = 1;
    v20 = v28;
    *(_DWORD *)(v28 + 64) = *v29;
    *(_DWORD *)(v20 + 68) = *v30;
    *(_DWORD *)(v20 + 84) = *(_DWORD *)v31;
    *(_QWORD *)(v20 + 88) = *v32;
    throw;
  }
  return v19;
}

```

## disassembly

```asm
0x1800891d4  mov     [rsp+arg_8], rbx
0x1800891d9  mov     [rsp+arg_10], rsi
0x1800891de  push    rdi
0x1800891df  push    r12
0x1800891e1  push    r13
0x1800891e3  push    r14
0x1800891e5  push    r15
0x1800891e7  sub     rsp, 0B0h
0x1800891ee  mov     r15, r9
0x1800891f1  mov     r12d, r8d
0x1800891f4  mov     esi, edx
0x1800891f6  mov     rdi, rcx
0x1800891f9  xor     r13d, r13d
0x1800891fc  mov     rbx, [rcx+30h]
0x180089200  call    cs:__imp_GetCurrentThreadId
0x180089206  cmp     eax, [rbx+0B0h]
0x18008920c  jz      short loc_180089222
0x18008920e  lea     rcx, [rsp+0D8h+var_98]
0x180089213  call    ?get_IncorrectThread@MessagingValidationException@Messaging@CoreUI@Microsoft@@SA?AV?$SmartPtr@VException@System@@@CFlat@@XZ; Microsoft::CoreUI::Messaging::MessagingValidationException::get_IncorrectThread(void)
0x180089218  nop
0x180089219  mov     rcx, [rax]; this
0x18008921c  call    ?Throw$@Exception@System@@QEAAXXZ; System::Exception::Throw$(void)
0x180089221  nop
0x180089222  mov     ecx, esi
0x180089224  sub     ecx, 1
0x180089227  jz      short loc_180089251
0x180089229  sub     ecx, 1
0x18008922c  jz      short loc_180089251
0x18008922e  sub     ecx, 1
0x180089231  jz      short loc_180089251
0x180089233  sub     ecx, 1
0x180089236  jz      short loc_180089251
0x180089238  cmp     ecx, 1
0x18008923b  jz      short loc_180089251
0x18008923d  lea     rcx, [rsp+0D8h+var_98]
0x180089242  call    ?get_ArgumentInvalid@ValidationException@CoreUI@Microsoft@@SA?AV?$SmartPtr@VValidationException@CoreUI@Microsoft@@@CFlat@@XZ; Microsoft::CoreUI::ValidationException::get_ArgumentInvalid(void)
0x180089247  nop
0x180089248  mov     rcx, [rax]; this
0x18008924b  call    ?Throw$@Exception@System@@QEAAXXZ; System::Exception::Throw$(void)
0x180089250  nop
0x180089251  mov     eax, [rdi+40h]
0x180089254  test    eax, eax
0x180089256  jnz     short loc_180089261
0x180089258  cmp     [rdi+48h], r13d
0x18008925c  mov     r14b, r13b
0x18008925f  jz      short loc_180089264
0x180089261  mov     r14b, 1
0x180089264  cmp     [rdi+20h], r13b
0x180089268  jnz     short loc_18008928A
0x18008926a  test    r14b, r14b
0x18008926d  jz      short loc_18008928F
0x18008926f  mov     edx, 2
0x180089274  lea     rcx, [rsp+0D8h+var_A0]
0x180089279  call    ?FromResult@MessagingValidationException@Messaging@CoreUI@Microsoft@@SA?AV?$SmartPtr@VException@System@@@CFlat@@W4MessagingResults@234@@Z; Microsoft::CoreUI::Messaging::MessagingValidationException::FromResult(Microsoft::CoreUI::Messaging::MessagingResults)
0x18008927e  nop
0x18008927f  mov     rcx, [rsp+0D8h+var_A0]; this
0x180089284  call    ?Throw$@Exception@System@@QEAAXXZ; System::Exception::Throw$(void)
0x180089289  nop
0x18008928a  test    r14b, r14b
0x18008928d  jnz     short loc_180089293
0x18008928f  mov     [rdi+50h], r13b
0x180089293  mov     [rsp+0D8h+var_A4], eax
0x180089297  mov     eax, [rdi+44h]
0x18008929a  mov     [rsp+0D8h+var_A8], eax
0x18008929e  mov     eax, [rdi+54h]
0x1800892a1  mov     [rsp+0D8h+arg_0], eax
0x1800892a8  mov     rax, [rdi+58h]
0x1800892ac  mov     [rsp+0D8h+var_90], rax
0x1800892b1  mov     dword ptr [rdi+40h], 1
0x1800892b8  mov     [rdi+44h], esi
0x1800892bb  mov     [rdi+54h], r12d
0x1800892bf  mov     [rdi+58h], r15
0x1800892c3  mov     [rsp+0D8h+var_88], r13b
0x1800892c8  lea     rax, [rsp+0D8h+var_90]
0x1800892cd  mov     [rsp+0D8h+var_B0], rax
0x1800892d2  lea     rax, [rsp+0D8h+arg_0]
0x1800892da  mov     [rsp+0D8h+var_B8], rax
0x1800892df  lea     r9, [rsp+0D8h+var_A8]
0x1800892e4  lea     r8, [rsp+0D8h+var_A4]
0x1800892e9  mov     rdx, rdi
0x1800892ec  lea     rcx, [rsp+0D8h+var_50]
0x1800892f4  call    _lambda_bfcd5ef1e675e352cb06890cc36b3edf____lambda_bfcd5ef1e675e352cb06890cc36b3edf_
0x1800892f9  mov     r15, [rax]
0x1800892fc  mov     [rsp+0D8h+var_80], r15
0x180089301  mov     r12, [rax+8]
0x180089305  mov     [rsp+0D8h+var_78], r12
0x18008930a  mov     r13, [rax+10h]
0x18008930e  mov     [rsp+0D8h+var_70], r13
0x180089313  mov     rcx, [rax+18h]
0x180089317  mov     [rsp+0D8h+var_A0], rcx
0x18008931c  mov     [rsp+0D8h+var_68], rcx
0x180089321  mov     rax, [rax+20h]
0x180089325  mov     [rsp+0D8h+var_98], rax
0x18008932a  mov     [rsp+0D8h+var_60], rax
0x18008932f  mov     rbx, [rdi+0A8h]
0x180089336  mov     [rsp+0D8h+var_58], rbx
0x18008933e  test    rbx, rbx
0x180089341  jz      short loc_180089346
0x180089343  inc     dword ptr [rbx+10h]
0x180089346  mov     rax, [rbx]
0x180089349  mov     edx, esi
0x18008934b  mov     rcx, rbx
0x18008934e  mov     rax, [rax+50h]
0x180089352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089357  nop
0x180089358  test    rbx, rbx
0x18008935b  jz      short loc_180089366
0x18008935d  mov     rcx, rbx; this
0x180089360  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180089365  nop
0x180089366  mov     eax, [r12]
0x18008936a  mov     [r15+40h], eax
0x18008936e  mov     eax, [r13+0]
0x180089372  mov     [r15+44h], eax
0x180089376  mov     rax, [rsp+0D8h+var_A0]
0x18008937b  mov     eax, [rax]
0x18008937d  mov     [r15+54h], eax
0x180089381  mov     rax, [rsp+0D8h+var_98]
0x180089386  mov     rax, [rax]
0x180089389  mov     [r15+58h], rax
0x18008938d  test    r14b, r14b
0x180089390  jnz     short loc_18008939E
0x180089392  lea     eax, [rsi-3]
0x180089395  cmp     eax, 1
0x180089398  setbe   al
0x18008939b  mov     [rdi+50h], al
0x18008939e  lea     r11, [rsp+0D8h+var_28]
0x1800893a6  mov     rbx, [r11+38h]
0x1800893aa  mov     rsi, [r11+40h]
0x1800893ae  mov     rsp, r11
0x1800893b1  pop     r15
0x1800893b3  pop     r14
0x1800893b5  pop     r13
0x1800893b7  pop     r12
0x1800893b9  pop     rdi
0x1800893ba  retn
```
