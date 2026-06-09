# System::Runtime::InteropServices::Marshal::ThrowExceptionForHR(int)

- ea: `0x18008d5bc`
- end: `0x18008d950`
- name: `?ThrowExceptionForHR@Marshal@InteropServices@Runtime@System@@SAXH@Z`
- size: `916`
- prototype: `void __fastcall(int)`
- caller_count: `274`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006880`
- `0x180006940`
- `0x1800070a0`
- `0x180007b20`
- `0x180007d90`
- `0x180017bf0`
- `0x180019208`
- `0x180022824`
- `0x180022ee8`
- `0x180023070`
- `0x1800277e0`
- `0x18002a130`
- `0x1800308e8`
- `0x180030c84`
- `0x1800325b8`
- `0x180033ea4`
- `0x180034624`
- `0x180034f84`
- `0x18003b744`
- `0x18003b8b0`
- `0x18003b968`
- `0x18003c364`
- `0x18003c5e4`
- `0x18003c71c`
- `0x18003ccf0`
- `0x18003ce88`
- `0x18003cef8`
- `0x180043a7c`
- `0x180043bb0`
- `0x180044338`
- `0x1800444a0`
- `0x180044678`
- `0x180045b9c`
- `0x1800486f0`
- `0x180048810`
- `0x180048930`
- `0x180049e7c`
- `0x18004b320`
- `0x18004bc84`
- `0x18004bf64`
- `0x1800537e0`
- `0x1800561a4`
- `0x180056260`
- `0x18005631c`
- `0x1800565e0`
- `0x180057470`
- `0x180057928`
- `0x180057c14`
- `0x1800586e8`
- `0x18005abd4`

## callees

- `0x1800111dc`
- `0x18002e654`
- `0x18002eb74`
- `0x180030c30`
- `0x18003950c`
- `0x1800726ac`
- `0x18007af94`
- `0x18008d5bc`
- `0x18008db10`
- `0x1800a2318`
- `0x1800c69a0`
- `0x1800c722c`
- `0x1800c85ac`
- `0x1800c8614`
- `0x1800c866c`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18008d882`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18008d882`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall System::Runtime::InteropServices::Marshal::ThrowExceptionForHR(int a1)
{
  bool v2; // zf
  System::Exception *v3; // rbx
  struct System::Exception *v4; // rdx
  bool v5; // r9
  struct System::Exception *v6; // rdx
  bool v7; // r9
  DWORD v8; // eax
  __int64 v9; // r8
  __int64 v10; // rax
  _BYTE *v11; // rcx
  _QWORD *v12; // rax
  __int64 v13; // rax
  System::Exception *v14; // rbx
  struct System::Exception *v15; // rdx
  bool v16; // r9
  System::Exception *v17; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[8]; // [rsp+48h] [rbp-B8h] BYREF
  System::Exception *v19; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[8]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[512]; // [rsp+60h] [rbp-A0h] BYREF

  if ( a1 < 0 )
  {
    if ( a1 > -2146233068 )
    {
      if ( a1 > -2146232832 )
      {
        if ( a1 == -2146232831 || a1 == -2146232830 )
          goto LABEL_53;
        v2 = a1 == -2146232829;
      }
      else
      {
        if ( a1 == -2146232832 )
          goto LABEL_53;
        if ( a1 > -2146233049 )
        {
          if ( a1 == -2146233048
            || a1 == -2146233047
            || a1 == -2146233040
            || a1 == -2146233039
            || a1 == -2146233038
            || a1 == -2146233037
            || a1 == -2146233036 )
          {
            goto LABEL_53;
          }
          v2 = a1 == -2146233033;
        }
        else
        {
          if ( a1 == -2146233049
            || a1 == -2146233067
            || a1 == -2146233066
            || a1 == -2146233065
            || a1 == -2146233064
            || a1 == -2146233063
            || a1 == -2146233062
            || a1 == -2146233056
            || a1 == -2146233055 )
          {
            goto LABEL_53;
          }
          v2 = a1 == -2146233054;
        }
      }
      goto LABEL_48;
    }
    if ( a1 == -2146233068 )
      goto LABEL_53;
    if ( a1 <= -2146233085 )
    {
      if ( a1 == -2146233085 )
        goto LABEL_53;
      if ( a1 <= -2147024882 )
      {
        if ( a1 == -2147024882 )
          CFlat::Abandonment::FailWithHR(-2147024882, 0, -2147024882);
        if ( a1 == -2147467263 || a1 == -2147467262 || a1 == -2147467261 || a1 == -2147352562 || a1 == -2147352558 )
          goto LABEL_53;
        v2 = a1 == -2147024885;
LABEL_48:
        if ( !v2 )
        {
LABEL_49:
          v17 = 0;
          v8 = FormatMessageW(0x32FFu, 0, a1, 0, Buffer, 0x200u, 0);
          if ( v8 )
          {
            v10 = System::String::Create$(v18, Buffer, v9, v8);
            CFlat::SmartPtr<System::Action>::operator=(&v17, v10);
            v11 = v18;
          }
          else
          {
            v12 = (_QWORD *)System::Int32::ToString(v20, (unsigned int)a1);
            v13 = System::String::Concat(v18, &off_1800DF860, *v12);
            CFlat::SmartPtr<System::Action>::operator=(&v17, v13);
            CFlat::SmartPtr<System::Collections::Generic::EqualityComparer$1<enum Microsoft::CoreUI::Registrar::RegistrarClientId>>::~SmartPtr<System::Collections::Generic::EqualityComparer$1<enum Microsoft::CoreUI::Registrar::RegistrarClientId>>(v18);
            v11 = v20;
          }
          CFlat::SmartPtr<System::Collections::Generic::EqualityComparer$1<enum Microsoft::CoreUI::Registrar::RegistrarClientId>>::~SmartPtr<System::Collections::Generic::EqualityComparer$1<enum Microsoft::CoreUI::Registrar::RegistrarClientId>>(v11);
          CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<System::Runtime::InteropServices::COMException>>(&v19);
          v14 = v19;
          System::SystemException::Init$(v19, v17);
          *((_DWORD *)v14 + 10) = a1;
          CFlat::ExceptionHandling::OnThrowExceptionForHR(a1, v15, 0, v16);
          System::Exception::Throw$(v19);
        }
LABEL_53:
        CFlat::Abandonment::FailWithHR(a1, 0, a1);
      }
      if ( a1 == -2147024809 || a1 == -2147024362 || a1 == -2147023895 )
        goto LABEL_53;
      LODWORD(v3) = -2146233088;
      if ( a1 != -2146233088 )
      {
        if ( a1 != -2146233087 )
        {
          v2 = a1 == -2146233086;
          goto LABEL_48;
        }
        CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<System::SystemException>>(&v17);
        v3 = v17;
        System::Exception::Init$(v17, (struct System::String *)&System::SR::Arg_SystemException$backingField$);
        *((_DWORD *)v3 + 10) = -2146233087;
        CFlat::ExceptionHandling::OnThrowExceptionForHR(-2146233087, v4, 0, v5);
        System::Exception::Throw$(v17);
      }
      CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<System::Exception>>(&v17);
      System::Exception::Init$(v17);
      CFlat::ExceptionHandling::OnThrowExceptionForHR((int)v3, v6, 0, v7);
      System::Exception::Throw$(v17);
    }
    switch ( a1 )
    {
      case -2146233084:
      case -2146233082:
      case -2146233081:
      case -2146233080:
      case -2146233079:
      case -2146233078:
      case -2146233076:
      case -2146233075:
      case -2146233072:
      case -2146233071:
      case -2146233070:
      case -2146233069:
        goto LABEL_53;
      default:
        goto LABEL_49;
    }
  }
}

```

## disassembly

```asm
0x18008d5bc  test    ecx, ecx
0x18008d5be  jns     locret_18008D936
0x18008d5c4  mov     [rsp-8+arg_8], rbx
0x18008d5c9  mov     [rsp-8+arg_10], rdi
0x18008d5ce  push    rbp
0x18008d5cf  lea     rbp, [rsp-370h]
0x18008d5d7  sub     rsp, 470h
0x18008d5de  mov     rax, cs:__security_cookie
0x18008d5e5  xor     rax, rsp
0x18008d5e8  mov     [rbp+370h+var_10], rax
0x18008d5ef  mov     edi, ecx
0x18008d5f1  mov     eax, 80131514h
0x18008d5f6  cmp     ecx, eax
0x18008d5f8  jg      loc_18008D747
0x18008d5fe  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d604  mov     eax, 80131503h
0x18008d609  cmp     ecx, eax
0x18008d60b  jg      loc_18008D71B
0x18008d611  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d617  mov     ecx, 8007000Eh; int
0x18008d61c  cmp     edi, ecx
0x18008d61e  jg      short loc_18008D674
0x18008d620  jz      short loc_18008D669
0x18008d622  cmp     edi, 80004001h
0x18008d628  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d62e  cmp     edi, 80004002h
0x18008d634  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d63a  cmp     edi, 80004003h
0x18008d640  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d646  cmp     edi, 8002000Eh
0x18008d64c  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d652  cmp     edi, 80020012h
0x18008d658  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d65e  cmp     edi, 8007000Bh
0x18008d664  jmp     loc_18008D84B
0x18008d669  mov     r8d, ecx; int
0x18008d66c  xor     edx, edx; void *
0x18008d66e  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x18008d674  cmp     edi, 80070057h
0x18008d67a  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d680  cmp     edi, 80070216h
0x18008d686  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d68c  cmp     edi, 800703E9h
0x18008d692  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d698  mov     ebx, 80131500h
0x18008d69d  cmp     edi, ebx
0x18008d69f  jz      short loc_18008D6F1
0x18008d6a1  cmp     edi, 80131501h
0x18008d6a7  jz      short loc_18008D6B4
0x18008d6a9  cmp     edi, 80131502h
0x18008d6af  jmp     loc_18008D84B
0x18008d6b4  lea     rcx, [rsp+470h+var_430]
0x18008d6b9  call    ??$Allocate@V?$SmartPtr@VSystemException@System@@@CFlat@@@MemoryManagement@CFlat@@SA?AV?$SmartPtr@VSystemException@System@@@1@XZ; CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<System::SystemException>>(void)
0x18008d6be  mov     rbx, [rsp+470h+var_430]
0x18008d6c3  lea     rdx, ?Arg_SystemException$backingField$@SR@System@@0U?$FrozenString@$0N@@CFlat@@B; struct System::String *
0x18008d6ca  mov     rcx, rbx; this
0x18008d6cd  call    ?Init$@Exception@System@@IEAAXPEAVString@2@@Z; System::Exception::Init$(System::String *)
0x18008d6d2  mov     dword ptr [rbx+28h], 80131501h
0x18008d6d9  xor     r8d, r8d; bool
0x18008d6dc  mov     ecx, 80131501h; int
0x18008d6e1  call    ?OnThrowExceptionForHR@ExceptionHandling@CFlat@@SAXHPEAVException@System@@_N1@Z; CFlat::ExceptionHandling::OnThrowExceptionForHR(int,System::Exception *,bool,bool)
0x18008d6e6  mov     rcx, [rsp+470h+var_430]; this
0x18008d6eb  call    ?Throw$@Exception@System@@QEAAXXZ; System::Exception::Throw$(void)
0x18008d6f0  nop
0x18008d6f1  lea     rcx, [rsp+470h+var_430]
0x18008d6f6  call    ??$Allocate@V?$SmartPtr@VException@System@@@CFlat@@@MemoryManagement@CFlat@@SA?AV?$SmartPtr@VException@System@@@1@XZ; CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<System::Exception>>(void)
0x18008d6fb  mov     rcx, [rsp+470h+var_430]; this
0x18008d700  call    ?Init$@Exception@System@@IEAAXXZ; System::Exception::Init$(void)
0x18008d705  nop
0x18008d706  xor     r8d, r8d; bool
0x18008d709  mov     ecx, ebx; int
0x18008d70b  call    ?OnThrowExceptionForHR@ExceptionHandling@CFlat@@SAXHPEAVException@System@@_N1@Z; CFlat::ExceptionHandling::OnThrowExceptionForHR(int,System::Exception *,bool,bool)
0x18008d710  mov     rcx, [rsp+470h+var_430]; this
0x18008d715  call    ?Throw$@Exception@System@@QEAAXXZ; System::Exception::Throw$(void)
0x18008d71a  nop
0x18008d71b  lea     eax, [rcx+7FECEAFCh]; switch 16 cases
0x18008d721  cmp     eax, 0Fh
0x18008d724  ja      def_18008D745; jumptable 000000018008D745 default case, cases -2146233083,-2146233077,-2146233074,-2146233073
0x18008d72a  cdqe
0x18008d72c  lea     rdx, __ImageBase
0x18008d733  movzx   eax, ds:(byte_18008D940 - 180000000h)[rdx+rax]
0x18008d73b  mov     ecx, ds:(jpt_18008D745 - 180000000h)[rdx+rax*4]
0x18008d742  add     rcx, rdx
0x18008d745  jmp     rcx; switch jump
0x18008d747  mov     eax, 80131600h
0x18008d74c  cmp     edi, eax
0x18008d74e  jg      loc_18008D82D
0x18008d754  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d75a  mov     eax, 80131527h
0x18008d75f  cmp     edi, eax
0x18008d761  jg      short loc_18008D7D1
0x18008d763  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d769  cmp     edi, 80131515h
0x18008d76f  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d775  cmp     edi, 80131516h
0x18008d77b  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d781  cmp     edi, 80131517h
0x18008d787  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d78d  cmp     edi, 80131518h
0x18008d793  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d799  cmp     edi, 80131519h
0x18008d79f  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d7a5  cmp     edi, 8013151Ah
0x18008d7ab  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d7b1  cmp     edi, 80131520h
0x18008d7b7  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d7bd  cmp     edi, 80131521h
0x18008d7c3  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d7c9  cmp     edi, 80131522h
0x18008d7cf  jmp     short loc_18008D84B
0x18008d7d1  cmp     edi, 80131528h
0x18008d7d7  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d7dd  cmp     edi, 80131529h
0x18008d7e3  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d7e9  cmp     edi, 80131530h
0x18008d7ef  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d7f5  cmp     edi, 80131531h
0x18008d7fb  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d801  cmp     edi, 80131532h
0x18008d807  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d80d  cmp     edi, 80131533h
0x18008d813  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d819  cmp     edi, 80131534h
0x18008d81f  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d825  cmp     edi, 80131537h
0x18008d82b  jmp     short loc_18008D84B
0x18008d82d  cmp     edi, 80131601h
0x18008d833  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d839  cmp     edi, 80131602h
0x18008d83f  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d845  cmp     edi, 80131603h
0x18008d84b  jz      loc_18008D929; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d851  mov     [rsp+470h+var_430], 0; jumptable 000000018008D745 default case, cases -2146233083,-2146233077,-2146233074,-2146233073
0x18008d85a  mov     [rsp+470h+Arguments], 0; Arguments
0x18008d863  mov     [rsp+470h+nSize], 200h; nSize
0x18008d86b  lea     rax, [rsp+470h+Buffer]
0x18008d870  mov     [rsp+470h+lpBuffer], rax; lpBuffer
0x18008d875  xor     r9d, r9d; dwLanguageId
0x18008d878  mov     r8d, edi; dwMessageId
0x18008d87b  xor     edx, edx; lpSource
0x18008d87d  mov     ecx, 32FFh; dwFlags
0x18008d882  call    cs:__imp_FormatMessageW
0x18008d888  test    eax, eax
0x18008d88a  jz      short loc_18008D8B2
0x18008d88c  mov     r9d, eax
0x18008d88f  lea     rdx, [rsp+470h+Buffer]
0x18008d894  lea     rcx, [rsp+470h+var_428]
0x18008d899  call    ?Create$@String@System@@SA?AV?$SmartPtr@VString@System@@@CFlat@@PEA_WHH@Z; System::String::Create$(wchar_t *,int,int)
0x18008d89e  mov     rdx, rax
0x18008d8a1  lea     rcx, [rsp+470h+var_430]
0x18008d8a6  call    ??4?$SmartPtr@VAction@System@@@CFlat@@QEAAAEAV01@$$QEAV01@@Z; CFlat::SmartPtr<System::Action>::operator=(CFlat::SmartPtr<System::Action> &&)
0x18008d8ab  lea     rcx, [rsp+470h+var_428]
0x18008d8b0  jmp     short loc_18008D8F0
0x18008d8b2  mov     edx, edi
0x18008d8b4  lea     rcx, [rsp+470h+var_418]
0x18008d8b9  call    ?ToString@Int32@System@@SA?AV?$SmartPtr@VString@System@@@CFlat@@H@Z; System::Int32::ToString(int)
0x18008d8be  nop
0x18008d8bf  mov     r8, [rax]
0x18008d8c2  lea     rdx, off_1800DF860
0x18008d8c9  lea     rcx, [rsp+470h+var_428]
0x18008d8ce  call    ?Concat@String@System@@SA?AV?$SmartPtr@VString@System@@@CFlat@@PEAV12@0@Z; System::String::Concat(System::String *,System::String *)
0x18008d8d3  mov     rdx, rax
0x18008d8d6  lea     rcx, [rsp+470h+var_430]
0x18008d8db  call    ??4?$SmartPtr@VAction@System@@@CFlat@@QEAAAEAV01@$$QEAV01@@Z; CFlat::SmartPtr<System::Action>::operator=(CFlat::SmartPtr<System::Action> &&)
0x18008d8e0  lea     rcx, [rsp+470h+var_428]; void *
0x18008d8e5  call    ??1?$SmartPtr@V?$EqualityComparer$1@W4RegistrarClientId@Registrar@CoreUI@Microsoft@@@Generic@Collections@System@@@CFlat@@QEAA@XZ; CFlat::SmartPtr<System::Collections::Generic::EqualityComparer$1<Microsoft::CoreUI::Registrar::RegistrarClientId>>::~SmartPtr<System::Collections::Generic::EqualityComparer$1<Microsoft::CoreUI::Registrar::RegistrarClientId>>(void)
0x18008d8ea  nop
0x18008d8eb  lea     rcx, [rsp+470h+var_418]; void *
0x18008d8f0  call    ??1?$SmartPtr@V?$EqualityComparer$1@W4RegistrarClientId@Registrar@CoreUI@Microsoft@@@Generic@Collections@System@@@CFlat@@QEAA@XZ; CFlat::SmartPtr<System::Collections::Generic::EqualityComparer$1<Microsoft::CoreUI::Registrar::RegistrarClientId>>::~SmartPtr<System::Collections::Generic::EqualityComparer$1<Microsoft::CoreUI::Registrar::RegistrarClientId>>(void)
0x18008d8f5  lea     rcx, [rsp+470h+var_420]
0x18008d8fa  call    ??$Allocate@V?$SmartPtr@VCOMException@InteropServices@Runtime@System@@@CFlat@@@MemoryManagement@CFlat@@SA?AV?$SmartPtr@VCOMException@InteropServices@Runtime@System@@@1@XZ; CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<System::Runtime::InteropServices::COMException>>(void)
0x18008d8ff  mov     rbx, [rsp+470h+var_420]
0x18008d904  mov     rdx, [rsp+470h+var_430]; struct System::String *
0x18008d909  mov     rcx, rbx; this
0x18008d90c  call    ?Init$@SystemException@System@@IEAAXPEAVString@2@@Z; System::SystemException::Init$(System::String *)
0x18008d911  mov     [rbx+28h], edi
0x18008d914  xor     r8d, r8d; bool
0x18008d917  mov     ecx, edi; int
0x18008d919  call    ?OnThrowExceptionForHR@ExceptionHandling@CFlat@@SAXHPEAVException@System@@_N1@Z; CFlat::ExceptionHandling::OnThrowExceptionForHR(int,System::Exception *,bool,bool)
0x18008d91e  mov     rcx, [rsp+470h+var_420]; this
0x18008d923  call    ?Throw$@Exception@System@@QEAAXXZ; System::Exception::Throw$(void)
0x18008d928  nop
0x18008d929  mov     r8d, edi; jumptable 000000018008D745 cases -2146233084,-2146233082--2146233078,-2146233076,-2146233075,-2146233072--2146233069
0x18008d92c  xor     edx, edx; void *
0x18008d92e  mov     ecx, edi; int
0x18008d930  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x18008d936  retn
```
