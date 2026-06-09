# Windows::Globalization::Spelling::CSpellerDecorator::GetWordList(WORDLIST_TYPE,IEnumString * *)

- ea: `0x180086380`
- end: `0x180086473`
- name: `?GetWordList@CSpellerDecorator@Spelling@Globalization@Windows@@UEAAJW4WORDLIST_TYPE@@PEAPEAUIEnumString@@@Z`
- size: `243`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180032b6c`
- `0x18003627c`
- `0x180040cc4`
- `0x1800511f4`
- `0x180086380`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800863e3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800863e3`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800863bc`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800863bc`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::CSpellerDecorator::GetWordList(__int64 a1, int a2, _QWORD *a3)
{
  int v6; // ebx
  HRESULT v7; // edi
  char IsRunningUnderAppContainer; // bp
  __int64 v9; // rcx
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF
  __int64 v12; // [rsp+68h] [rbp+20h] BYREF

  v12 = 0;
  v11 = 0;
  if ( !a3 )
    goto LABEL_14;
  *a3 = 0;
  v6 = 0;
  v7 = CoImpersonateClient();
  if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147417833 )
  {
    IsRunningUnderAppContainer = Windows::Globalization::Spelling::IsRunningUnderAppContainer(0x80000000);
    if ( v7 >= 0 )
      CoRevertToSelf();
    if ( !IsRunningUnderAppContainer )
    {
      if ( a2 == 1 )
      {
        v9 = *(_QWORD *)(a1 + 184);
LABEL_11:
        v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 32LL))(v9, &v12);
        if ( v6 >= 0 )
        {
          v6 = Windows::Globalization::Spelling::CEnumStringDecorator::CreateInstance(&v12, &v11);
          if ( v6 >= 0 )
          {
            *a3 = v11;
            v11 = 0;
          }
        }
        goto LABEL_15;
      }
      if ( a2 == 2 )
      {
        v9 = *(_QWORD *)(a1 + 200);
        goto LABEL_11;
      }
LABEL_14:
      v6 = -2147024809;
    }
  }
LABEL_15:
  ATL::CComPtrBase<Windows::Globalization::Spelling::CPrivateSpellCheckerFactoryWrapper>::~CComPtrBase<Windows::Globalization::Spelling::CPrivateSpellCheckerFactoryWrapper>(&v11);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180086380  mov     [rsp+arg_0], rbx
0x180086385  push    rbp
0x180086386  push    rsi
0x180086387  push    rdi
0x180086388  push    r14
0x18008638a  push    r15
0x18008638c  sub     rsp, 20h
0x180086390  mov     [rsp+48h+arg_18], 0
0x180086399  mov     r14, r8
0x18008639c  mov     [rsp+48h+arg_10], 0
0x1800863a5  mov     esi, edx
0x1800863a7  mov     r15, rcx
0x1800863aa  test    r8, r8
0x1800863ad  jz      loc_180086447
0x1800863b3  mov     qword ptr [r8], 0
0x1800863ba  xor     ebx, ebx
0x1800863bc  call    cs:__imp_CoImpersonateClient
0x1800863c2  mov     ecx, 80000000h
0x1800863c7  mov     edi, eax
0x1800863c9  add     eax, ecx
0x1800863cb  test    ecx, eax
0x1800863cd  jnz     short loc_1800863D7
0x1800863cf  cmp     edi, 80010117h
0x1800863d5  jnz     short loc_18008644C
0x1800863d7  call    Windows__Globalization__Spelling__IsRunningUnderAppContainer
0x1800863dc  mov     bpl, al
0x1800863df  test    edi, edi
0x1800863e1  js      short loc_1800863E9
0x1800863e3  call    cs:__imp_CoRevertToSelf
0x1800863e9  test    bpl, bpl
0x1800863ec  jnz     short loc_18008644C
0x1800863ee  cmp     esi, 1
0x1800863f1  jnz     short loc_1800863FC
0x1800863f3  mov     rcx, [r15+0B8h]
0x1800863fa  jmp     short loc_180086408
0x1800863fc  cmp     esi, 2
0x1800863ff  jnz     short loc_180086447
0x180086401  mov     rcx, [r15+0C8h]
0x180086408  mov     rax, [rcx]
0x18008640b  lea     rdx, [rsp+48h+arg_18]
0x180086410  mov     rax, [rax+20h]
0x180086414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086419  mov     ebx, eax
0x18008641b  test    eax, eax
0x18008641d  js      short loc_18008644C
0x18008641f  lea     rdx, [rsp+48h+arg_10]
0x180086424  lea     rcx, [rsp+48h+arg_18]
0x180086429  call    ?CreateInstance@CEnumStringDecorator@Spelling@Globalization@Windows@@SAJAEBV?$CComPtr@UIEnumString@@@ATL@@PEAPEAV1234@@Z; Windows::Globalization::Spelling::CEnumStringDecorator::CreateInstance(ATL::CComPtr<IEnumString> const &,Windows::Globalization::Spelling::CEnumStringDecorator * *)
0x18008642e  mov     ebx, eax
0x180086430  test    eax, eax
0x180086432  js      short loc_18008644C
0x180086434  mov     rax, [rsp+48h+arg_10]
0x180086439  mov     [r14], rax
0x18008643c  mov     [rsp+48h+arg_10], 0
0x180086445  jmp     short loc_18008644C
0x180086447  mov     ebx, 80070057h
0x18008644c  lea     rcx, [rsp+48h+arg_10]
0x180086451  call    ??1?$CComPtrBase@VCPrivateSpellCheckerFactoryWrapper@Spelling@Globalization@Windows@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Windows::Globalization::Spelling::CPrivateSpellCheckerFactoryWrapper>::~CComPtrBase<Windows::Globalization::Spelling::CPrivateSpellCheckerFactoryWrapper>(void)
0x180086456  lea     rcx, [rsp+48h+arg_18]
0x18008645b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180086460  mov     eax, ebx
0x180086462  mov     rbx, [rsp+48h+arg_0]
0x180086467  add     rsp, 20h
0x18008646b  pop     r15
0x18008646d  pop     r14
0x18008646f  pop     rdi
0x180086470  pop     rsi
0x180086471  pop     rbp
0x180086472  retn
```
