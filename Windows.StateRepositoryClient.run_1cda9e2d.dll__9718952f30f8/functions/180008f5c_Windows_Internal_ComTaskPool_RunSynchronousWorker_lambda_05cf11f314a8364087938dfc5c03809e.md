# Windows::Internal::ComTaskPool::RunSynchronousWorker__lambda_05cf11f314a8364087938dfc5c03809e___

- ea: `0x180008f5c`
- end: `0x1800090e5`
- name: `Windows::Internal::ComTaskPool::RunSynchronousWorker__lambda_05cf11f314a8364087938dfc5c03809e___`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d090`

## callees

- `0x1800075e4`
- `0x180008d64`
- `0x180008f5c`
- `0x18000969c`
- `0x18000bbb0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009036`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009036`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800090b3`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800090b3`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x1800090cf`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x1800090cf`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180008f85`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180008f85`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180009056`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180009056`

## string_xrefs

- `0x180009022`: `onecore\internal\sdk\inc\winrt\ComTaskPool.h`
- `0x180009066`: `onecore\internal\sdk\inc\winrt\ComTaskPool.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::RunSynchronousWorker__lambda_05cf11f314a8364087938dfc5c03809e___(
        __int64 a1)
{
  char v1; // cl
  bool v2; // al
  __int64 *v3; // rax
  __int64 v4; // rdi
  unsigned int v5; // ebx
  __int64 v6; // rdx
  DWORD CurrentThreadId; // eax
  int v8; // eax
  int v10; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  APTTYPE pAptType; // [rsp+50h] [rbp+20h] BYREF
  int v13; // [rsp+54h] [rbp+24h]
  APTTYPEQUALIFIER pAptQualifier; // [rsp+58h] [rbp+28h] BYREF
  __int64 v15; // [rsp+60h] [rbp+30h] BYREF
  __int64 v16; // [rsp+68h] [rbp+38h] BYREF

  v13 = HIDWORD(a1);
  pAptType = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  if ( CoGetApartmentType(&pAptType, &pAptQualifier) < 0 )
  {
    v15 = 0;
    goto LABEL_28;
  }
  v1 = 1;
  v2 = pAptType == APTTYPE_STA
    || pAptType == APTTYPE_MAINSTA
    || pAptType == APTTYPE_NA && ((pAptQualifier - 3) & 0xFFFFFFFD) == 0;
  if ( (pAptType || pAptQualifier != APTTYPEQUALIFIER_APPLICATION_STA)
    && pAptType == APTTYPE_MTA
    && pAptQualifier == APTTYPEQUALIFIER_IMPLICIT_MTA )
  {
    v1 = 0;
  }
  if ( !v2 )
  {
    v15 = 0;
    if ( v1 )
    {
LABEL_24:
      v5 = lambda_05cf11f314a8364087938dfc5c03809e_::operator()();
      if ( v15 )
        CoDecrementMTAUsage();
      return v5;
    }
LABEL_28:
    v5 = CoIncrementMTAUsage(&v15);
    if ( (v5 & 0x80000000) != 0 )
    {
      v6 = 430;
      goto LABEL_18;
    }
    goto LABEL_24;
  }
  LODWORD(v15) = 0;
  v3 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_05cf11f314a8364087938dfc5c03809e____long____lambda_05cf11f314a8364087938dfc5c03809e___(
                    &v16,
                    &v15);
  v4 = *v3;
  *v3 = 0;
  if ( v16 )
  {
    v16 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  if ( !v4 )
  {
    v5 = -2147024882;
    v6 = 446;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\internal\\sdk\\inc\\winrt\\ComTaskPool.h",
      (const char *)v5,
      v10);
    return v5;
  }
  CurrentThreadId = GetCurrentThreadId();
  v8 = SHTaskPoolQueueTask(0, 32, CurrentThreadId);
  v5 = v8;
  if ( v8 >= 0 )
    v5 = v15;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\internal\\sdk\\inc\\winrt\\ComTaskPool.h",
      (const char *)(unsigned int)v8,
      v4);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return v5;
}

```

## disassembly

```asm
0x180008f5c  mov     byte ptr [rsp-18h+pAptQualifier], dl
0x180008f60  mov     qword ptr [rsp-18h+pAptType], rcx
0x180008f65  push    rbp
0x180008f66  push    rbx
0x180008f67  push    rdi
0x180008f68  mov     rbp, rsp
0x180008f6b  sub     rsp, 30h
0x180008f6f  lea     rdx, [rbp+pAptQualifier]; pAptQualifier
0x180008f73  mov     [rbp+pAptType], 0
0x180008f7a  lea     rcx, [rbp+pAptType]; pAptType
0x180008f7e  mov     [rbp+pAptQualifier], 0
0x180008f85  call    cs:__imp_CoGetApartmentType
0x180008f8b  test    eax, eax
0x180008f8d  js      loc_1800090C3
0x180008f93  mov     edx, [rbp+pAptType]
0x180008f96  mov     ecx, 1
0x180008f9b  mov     r8d, [rbp+pAptQualifier]
0x180008f9f  test    edx, edx
0x180008fa1  jz      short loc_180008FBC
0x180008fa3  cmp     edx, 3
0x180008fa6  jz      short loc_180008FBC
0x180008fa8  cmp     edx, 2
0x180008fab  jnz     short loc_180008FB8
0x180008fad  lea     eax, [r8-3]
0x180008fb1  test    eax, 0FFFFFFFDh
0x180008fb6  jz      short loc_180008FBC
0x180008fb8  xor     al, al
0x180008fba  jmp     short loc_180008FBE
0x180008fbc  mov     al, cl
0x180008fbe  test    edx, edx
0x180008fc0  jnz     short loc_180008FC8
0x180008fc2  cmp     r8d, 6
0x180008fc6  jz      short loc_180008FD3
0x180008fc8  cmp     edx, ecx
0x180008fca  jnz     short loc_180008FD3
0x180008fcc  cmp     r8d, ecx
0x180008fcf  jnz     short loc_180008FD3
0x180008fd1  xor     cl, cl
0x180008fd3  test    al, al
0x180008fd5  jz      loc_180009097
0x180008fdb  lea     rdx, [rbp+arg_10]
0x180008fdf  mov     dword ptr [rbp+arg_10], 0
0x180008fe6  lea     rcx, [rbp+arg_18]
0x180008fea  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CResultTaskWrapper__lambda_05cf11f314a8364087938dfc5c03809e____long____lambda_05cf11f314a8364087938dfc5c03809e___
0x180008fef  mov     rdi, [rax]
0x180008ff2  mov     qword ptr [rax], 0
0x180008ff9  mov     rcx, [rbp+arg_18]
0x180008ffd  test    rcx, rcx
0x180009000  jz      short loc_18000900F
0x180009002  mov     [rbp+arg_18], 0
0x18000900a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18000900f  test    rdi, rdi
0x180009012  jnz     short loc_180009036
0x180009014  mov     ebx, 8007000Eh
0x180009019  mov     edx, 1BEh; void *
0x18000901e  mov     rcx, [rbp+18h]; this
0x180009022  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\winrt\\Com"...
0x180009029  mov     r9d, ebx; char *
0x18000902c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009031  jmp     loc_1800090B9
0x180009036  call    cs:__imp_GetCurrentThreadId
0x18000903c  xor     r9d, r9d
0x18000903f  mov     [rsp+30h+var_8], 0
0x180009048  mov     r8d, eax
0x18000904b  mov     qword ptr [rsp+30h+var_10], rdi; int
0x180009050  xor     ecx, ecx
0x180009052  lea     edx, [r9+20h]
0x180009056  call    cs:__imp_SHTaskPoolQueueTask
0x18000905c  mov     ebx, eax
0x18000905e  test    eax, eax
0x180009060  jns     short loc_18000908B
0x180009062  mov     rcx, [rbp+18h]; this
0x180009066  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\winrt\\Com"...
0x18000906d  mov     r9d, eax; char *
0x180009070  mov     edx, 1C2h; void *
0x180009075  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000907a  mov     rdx, [rdi]
0x18000907d  mov     rax, [rdx+10h]
0x180009081  mov     rcx, rdi
0x180009084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009089  jmp     short loc_1800090B9
0x18000908b  mov     rcx, [rdi]
0x18000908e  mov     ebx, dword ptr [rbp+arg_10]
0x180009091  mov     rax, [rcx+10h]
0x180009095  jmp     short loc_180009081
0x180009097  mov     [rbp+arg_10], 0
0x18000909f  test    cl, cl
0x1800090a1  jz      short loc_1800090CB
0x1800090a3  call    _lambda_05cf11f314a8364087938dfc5c03809e___operator__
0x1800090a8  mov     rcx, [rbp+arg_10]
0x1800090ac  mov     ebx, eax
0x1800090ae  test    rcx, rcx
0x1800090b1  jz      short loc_1800090B9
0x1800090b3  call    cs:__imp_CoDecrementMTAUsage
0x1800090b9  mov     eax, ebx
0x1800090bb  add     rsp, 30h
0x1800090bf  pop     rdi
0x1800090c0  pop     rbx
0x1800090c1  pop     rbp
0x1800090c2  retn
0x1800090c3  mov     [rbp+arg_10], 0
0x1800090cb  lea     rcx, [rbp+arg_10]
0x1800090cf  call    cs:__imp_CoIncrementMTAUsage
0x1800090d5  mov     ebx, eax
0x1800090d7  test    eax, eax
0x1800090d9  jns     short loc_1800090A3
0x1800090db  mov     edx, 1AEh
0x1800090e0  jmp     loc_18000901E
```
