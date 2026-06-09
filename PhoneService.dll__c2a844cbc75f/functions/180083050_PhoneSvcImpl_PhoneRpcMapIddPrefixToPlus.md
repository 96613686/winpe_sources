# PhoneSvcImpl_PhoneRpcMapIddPrefixToPlus

- ea: `0x180083050`
- end: `0x1800833f4`
- name: `PhoneSvcImpl_PhoneRpcMapIddPrefixToPlus`
- size: `932`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006e94`
- `0x18004c2ac`
- `0x180080894`
- `0x180083050`
- `0x180089ee0`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `PhoneUtil!GetCountryCodeFromOperatorNum` at `0x180083141`
- `PhoneUtil!GetCountryCodeFromOperatorNum` at `0x180083141`
- `PhoneUtil!CreateDialAssist` at `0x1800830e8`
- `PhoneUtil!CreateDialAssist` at `0x1800830e8`
- `PhoneUtil!CreatePerUserSecurityTokenForRpcClient` at `0x180083096`
- `PhoneUtil!CreatePerUserSecurityTokenForRpcClient` at `0x180083096`

## string_xrefs

- `0x1800830af`: `onecoreuap\net\phone\phoneservice\service\lib\internalphonerpc.cpp`
- `0x180083101`: `onecoreuap\net\phone\phoneservice\service\lib\internalphonerpc.cpp`
- `0x1800831b5`: `onecoreuap\net\phone\phoneservice\service\lib\internalphonerpc.cpp`
- `0x180083232`: `onecoreuap\net\phone\phoneservice\service\lib\internalphonerpc.cpp`
- `0x1800832f3`: `onecoreuap\net\phone\phoneservice\service\lib\internalphonerpc.cpp`

## pseudocode

```c
__int64 __fastcall PhoneSvcImpl_PhoneRpcMapIddPrefixToPlus(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  int v8; // eax
  BackTraceCollection *v9; // rcx
  unsigned int v10; // ebx
  int v12; // eax
  BackTraceCollection *v13; // rcx
  __int64 v14; // r9
  int CountryCodeFromOperatorNum; // eax
  BackTraceCollection *v16; // rcx
  int DefaultOutgoingLine; // eax
  BackTraceCollection *v18; // rcx
  int v19; // eax
  BackTraceCollection *v20; // rcx
  int v21; // eax
  BackTraceCollection *v22; // rcx
  unsigned int v23; // edi
  void (*v24)(void); // rax
  __int64 v25; // rax
  unsigned __int16 *v26; // rcx
  __int64 v27; // rdx
  unsigned __int16 *v28; // r8
  BackTraceCollection *v29; // rcx
  int v30; // eax
  BackTraceCollection *v31; // rcx
  struct ISecurityToken *v32; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v34; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v35[128]; // [rsp+60h] [rbp-A0h] BYREF
  char v36; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v37[8]; // [rsp+1A0h] [rbp+A0h] BYREF

  v32 = 0;
  v8 = CreatePerUserSecurityTokenForRpcClient(&v32);
  v10 = v8;
  if ( v8 < 0 )
  {
    BackTraceCollection::Capture(v9, v8);
    Log_HREvent_28(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\internalphonerpc.cpp", 322);
LABEL_3:
    if ( v32 )
      (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v32 + 16LL))(v32);
    return v10;
  }
  v33 = 0;
  v12 = CreateDialAssist(&v33);
  v10 = v12;
  if ( v12 < 0 )
  {
    BackTraceCollection::Capture(v13, v12);
    v14 = 325;
LABEL_8:
    Log_HREvent_28(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\internalphonerpc.cpp", v14);
    goto LABEL_9;
  }
  if ( !a3 )
  {
    v34 = 0;
    DefaultOutgoingLine = PhoneSvcImpl_PhoneRpcGetDefaultOutgoingLine(0, (__int64)&v34);
    v10 = DefaultOutgoingLine;
    if ( DefaultOutgoingLine < 0 )
    {
      BackTraceCollection::Capture(v18, DefaultOutgoingLine);
      v14 = 336;
      goto LABEL_8;
    }
    v19 = WrappedComPtrBase<IPhoneController,DoesNotSupportShutdown,utl::recursive_mutex>::Get(&g_phoneRpcServer);
    v10 = v19;
    if ( v19 < 0 )
    {
      BackTraceCollection::Capture(v20, v19);
      Log_HREvent_28(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\internalphonerpc.cpp", 339);
LABEL_9:
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      goto LABEL_3;
    }
    memset_0(v35, 0, 0x13Cu);
    v21 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _BYTE *, struct ISecurityToken *))(MEMORY[0] + 400LL))(
            0,
            &v34,
            v35,
            v32);
    v23 = v21;
    if ( v21 >= 0 )
    {
      v25 = 2147483646;
      v26 = (unsigned __int16 *)&v36;
      v27 = 8;
      v28 = v37;
      do
      {
        if ( !v25 )
          break;
        if ( !*v26 )
          break;
        *v28++ = *v26++;
        --v25;
        --v27;
      }
      while ( v27 );
      v29 = (BackTraceCollection *)(v28 - 1);
      v23 = v27 == 0 ? 0x8007007A : 0;
      if ( v27 )
        v29 = (BackTraceCollection *)v28;
      *(_WORD *)v29 = 0;
      if ( v27 )
        goto LABEL_36;
      BackTraceCollection::Capture(v29, v23);
      Log_HREvent_28(v23, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\internalphonerpc.cpp", 343);
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      if ( !v32 )
        return v23;
      v24 = *(void (**)(void))(*(_QWORD *)v32 + 16LL);
    }
    else
    {
      BackTraceCollection::Capture(v22, v21);
      Log_HREvent_28(v23, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\internalphonerpc.cpp", 342);
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      if ( !v32 )
        return v23;
      v24 = *(void (**)(void))(*(_QWORD *)v32 + 16LL);
    }
    v24();
    return v23;
  }
  CountryCodeFromOperatorNum = GetCountryCodeFromOperatorNum(a3, v37, 8u);
  v10 = CountryCodeFromOperatorNum;
  if ( CountryCodeFromOperatorNum < 0 )
  {
    BackTraceCollection::Capture(v16, CountryCodeFromOperatorNum);
    v14 = 330;
    goto LABEL_8;
  }
LABEL_36:
  v30 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *, __int64, int))(*(_QWORD *)v33 + 32LL))(
          v33,
          a2,
          v37,
          a5,
          a6);
  v10 = v30;
  if ( v30 < 0 )
  {
    BackTraceCollection::Capture(v31, v30);
    v14 = 348;
    goto LABEL_8;
  }
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v32 )
    (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v32 + 16LL))(v32);
  return 0;
}

```

## disassembly

```asm
0x180083050  mov     [rsp-8+arg_0], rbx
0x180083055  push    rbp
0x180083056  push    rsi
0x180083057  push    rdi
0x180083058  push    r14
0x18008305a  push    r15
0x18008305c  lea     rbp, [rsp-0C0h]
0x180083064  sub     rsp, 1C0h
0x18008306b  mov     rax, cs:__security_cookie
0x180083072  xor     rax, rsp
0x180083075  mov     [rbp+0E0h+var_30], rax
0x18008307c  mov     r14, [rbp+0E0h+arg_20]
0x180083083  lea     rcx, [rsp+1E0h+var_1A8]
0x180083088  xor     r15d, r15d
0x18008308b  mov     rdi, r8
0x18008308e  mov     [rsp+1E0h+var_1A8], r15
0x180083093  mov     rsi, rdx
0x180083096  call    cs:__imp_?CreatePerUserSecurityTokenForRpcClient@@YAJPEAPEAUISecurityToken@@@Z; CreatePerUserSecurityTokenForRpcClient(ISecurityToken * *)
0x18008309c  mov     ebx, eax
0x18008309e  test    eax, eax
0x1800830a0  jns     short loc_1800830DE
0x1800830a2  mov     edx, eax; int
0x1800830a4  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800830a9  mov     r9d, 142h
0x1800830af  lea     r8, aOnecoreuapNetP_16; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800830b6  lea     edx, [r15+1]
0x1800830ba  mov     ecx, ebx
0x1800830bc  call    Log_HREvent_28
0x1800830c1  mov     rcx, [rsp+1E0h+var_1A8]
0x1800830c6  test    rcx, rcx
0x1800830c9  jz      short loc_1800830D7
0x1800830cb  mov     rax, [rcx]
0x1800830ce  mov     rax, [rax+10h]
0x1800830d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800830d7  mov     eax, ebx
0x1800830d9  jmp     loc_1800833CE
0x1800830de  lea     rcx, [rsp+1E0h+var_1A0]
0x1800830e3  mov     [rsp+1E0h+var_1A0], r15
0x1800830e8  call    cs:__imp_CreateDialAssist
0x1800830ee  mov     ebx, eax
0x1800830f0  test    eax, eax
0x1800830f2  jns     short loc_18008312C
0x1800830f4  mov     edx, eax; int
0x1800830f6  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800830fb  mov     r9d, 145h
0x180083101  lea     r8, aOnecoreuapNetP_16; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180083108  mov     edx, 1
0x18008310d  mov     ecx, ebx
0x18008310f  call    Log_HREvent_28
0x180083114  mov     rcx, [rsp+1E0h+var_1A0]
0x180083119  test    rcx, rcx
0x18008311c  jz      short loc_1800830C1
0x18008311e  mov     rax, [rcx]
0x180083121  mov     rax, [rax+10h]
0x180083125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008312a  jmp     short loc_1800830C1
0x18008312c  test    rdi, rdi
0x18008312f  jz      short loc_180083160
0x180083131  mov     r8d, 8
0x180083137  lea     rdx, [rbp+0E0h+var_40]
0x18008313e  mov     rcx, rdi
0x180083141  call    cs:__imp_?GetCountryCodeFromOperatorNum@@YAJPEBGPEAG_K@Z; GetCountryCodeFromOperatorNum(ushort const *,ushort *,unsigned __int64)
0x180083147  mov     ebx, eax
0x180083149  test    eax, eax
0x18008314b  jns     loc_18008335E
0x180083151  mov     edx, eax; int
0x180083153  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180083158  mov     r9d, 14Ah
0x18008315e  jmp     short loc_180083101
0x180083160  xorps   xmm0, xmm0
0x180083163  lea     rdx, [rsp+1E0h+var_198]
0x180083168  xor     ecx, ecx
0x18008316a  movups  [rsp+1E0h+var_198], xmm0
0x18008316f  call    PhoneSvcImpl_PhoneRpcGetDefaultOutgoingLine
0x180083174  mov     ebx, eax
0x180083176  test    eax, eax
0x180083178  jns     short loc_18008318C
0x18008317a  mov     edx, eax; int
0x18008317c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180083181  mov     r9d, 150h
0x180083187  jmp     loc_180083101
0x18008318c  lea     rdx, [rsp+1E0h+var_1B0]
0x180083191  mov     [rsp+1E0h+var_1B0], r15
0x180083196  lea     rcx, ?g_phoneRpcServer@@3VSecurePhoneRpcServer@@A; lpCriticalSection
0x18008319d  call    ?Get@?$WrappedComPtrBase@UIPhoneController@@VDoesNotSupportShutdown@@Vrecursive_mutex@utl@@@@QEAAJPEAPEAUIPhoneController@@@Z; WrappedComPtrBase<IPhoneController,DoesNotSupportShutdown,utl::recursive_mutex>::Get(IPhoneController * *)
0x1800831a2  mov     ebx, eax
0x1800831a4  test    eax, eax
0x1800831a6  jns     short loc_1800831E7
0x1800831a8  mov     edx, eax; int
0x1800831aa  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800831af  mov     r9d, 153h
0x1800831b5  lea     r8, aOnecoreuapNetP_16; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800831bc  mov     edx, 1
0x1800831c1  mov     ecx, ebx
0x1800831c3  call    Log_HREvent_28
0x1800831c8  mov     rcx, [rsp+1E0h+var_1B0]
0x1800831cd  test    rcx, rcx
0x1800831d0  jz      loc_180083114
0x1800831d6  mov     rax, [rcx]
0x1800831d9  mov     rax, [rax+10h]
0x1800831dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800831e2  jmp     loc_180083114
0x1800831e7  xor     edx, edx; Val
0x1800831e9  lea     rcx, [rsp+1E0h+var_180]; void *
0x1800831ee  mov     r8d, 13Ch; Size
0x1800831f4  call    memset_0
0x1800831f9  mov     rbx, [rsp+1E0h+var_1B0]
0x1800831fe  lea     r8, [rsp+1E0h+var_180]
0x180083203  mov     r9, [rsp+1E0h+var_1A8]
0x180083208  lea     rdx, [rsp+1E0h+var_198]
0x18008320d  mov     rcx, rbx
0x180083210  mov     rax, [rbx]
0x180083213  mov     rax, [rax+190h]
0x18008321a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008321f  mov     edi, eax
0x180083221  test    eax, eax
0x180083223  jns     short loc_18008328C
0x180083225  mov     edx, eax; int
0x180083227  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18008322c  mov     r9d, 156h
0x180083232  lea     r8, aOnecoreuapNetP_16; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180083239  mov     edx, 1
0x18008323e  mov     ecx, edi
0x180083240  call    Log_HREvent_28
0x180083245  test    rbx, rbx
0x180083248  jz      short loc_180083259
0x18008324a  mov     rax, [rbx]
0x18008324d  mov     rcx, rbx
0x180083250  mov     rax, [rax+10h]
0x180083254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083259  mov     rcx, [rsp+1E0h+var_1A0]
0x18008325e  test    rcx, rcx
0x180083261  jz      short loc_18008326F
0x180083263  mov     rax, [rcx]
0x180083266  mov     rax, [rax+10h]
0x18008326a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008326f  mov     rcx, [rsp+1E0h+var_1A8]
0x180083274  test    rcx, rcx
0x180083277  jz      short loc_180083285
0x180083279  mov     rax, [rcx]
0x18008327c  mov     rax, [rax+10h]
0x180083280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083285  mov     eax, edi
0x180083287  jmp     loc_1800833CE
0x18008328c  mov     eax, 7FFFFFFEh
0x180083291  lea     rcx, [rbp+0E0h+var_100]
0x180083295  mov     edx, 8
0x18008329a  lea     r8, [rbp+0E0h+var_40]
0x1800832a1  test    rax, rax
0x1800832a4  jz      short loc_1800832C5
0x1800832a6  movzx   r9d, word ptr [rcx]
0x1800832aa  test    r9w, r9w
0x1800832ae  jz      short loc_1800832C5
0x1800832b0  mov     [r8], r9w
0x1800832b4  add     rcx, 2
0x1800832b8  add     r8, 2
0x1800832bc  dec     rax
0x1800832bf  sub     rdx, 1
0x1800832c3  jnz     short loc_1800832A1
0x1800832c5  mov     rax, rdx
0x1800832c8  lea     rcx, [r8-2]
0x1800832cc  neg     rax
0x1800832cf  sbb     edi, edi
0x1800832d1  not     edi
0x1800832d3  and     edi, 8007007Ah
0x1800832d9  test    rdx, rdx
0x1800832dc  cmovnz  rcx, r8; this
0x1800832e0  mov     [rcx], r15w
0x1800832e4  jnz     short loc_18008334A
0x1800832e6  mov     edx, edi; int
0x1800832e8  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800832ed  mov     r9d, 157h
0x1800832f3  lea     r8, aOnecoreuapNetP_16; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800832fa  mov     edx, 1
0x1800832ff  mov     ecx, edi
0x180083301  call    Log_HREvent_28
0x180083306  test    rbx, rbx
0x180083309  jz      short loc_18008331A
0x18008330b  mov     rax, [rbx]
0x18008330e  mov     rcx, rbx
0x180083311  mov     rax, [rax+10h]
0x180083315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008331a  mov     rcx, [rsp+1E0h+var_1A0]
0x18008331f  test    rcx, rcx
0x180083322  jz      short loc_180083330
0x180083324  mov     rax, [rcx]
0x180083327  mov     rax, [rax+10h]
0x18008332b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083330  mov     rcx, [rsp+1E0h+var_1A8]
0x180083335  test    rcx, rcx
0x180083338  jz      loc_180083285
0x18008333e  mov     rdx, [rcx]
0x180083341  mov     rax, [rdx+10h]
0x180083345  jmp     loc_180083280
0x18008334a  test    rbx, rbx
0x18008334d  jz      short loc_18008335E
0x18008334f  mov     rax, [rbx]
0x180083352  mov     rcx, rbx
0x180083355  mov     rax, [rax+10h]
0x180083359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008335e  mov     rcx, [rsp+1E0h+var_1A0]
0x180083363  mov     r9, r14
0x180083366  mov     r8d, [rbp+0E0h+arg_28]
0x18008336d  mov     rdx, rsi
0x180083370  mov     [rsp+1E0h+var_1C0], r8d
0x180083375  lea     r8, [rbp+0E0h+var_40]
0x18008337c  mov     rax, [rcx]
0x18008337f  mov     rax, [rax+20h]
0x180083383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083388  mov     ebx, eax
0x18008338a  test    eax, eax
0x18008338c  jns     short loc_1800833A0
0x18008338e  mov     edx, eax; int
0x180083390  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180083395  mov     r9d, 15Ch
0x18008339b  jmp     loc_180083101
0x1800833a0  mov     rcx, [rsp+1E0h+var_1A0]
0x1800833a5  test    rcx, rcx
0x1800833a8  jz      short loc_1800833B6
0x1800833aa  mov     rax, [rcx]
0x1800833ad  mov     rax, [rax+10h]
0x1800833b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800833b6  mov     rcx, [rsp+1E0h+var_1A8]
0x1800833bb  test    rcx, rcx
0x1800833be  jz      short loc_1800833CC
0x1800833c0  mov     rax, [rcx]
0x1800833c3  mov     rax, [rax+10h]
0x1800833c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800833cc  xor     eax, eax
0x1800833ce  mov     rcx, [rbp+0E0h+var_30]
0x1800833d5  xor     rcx, rsp; StackCookie
0x1800833d8  call    __security_check_cookie
0x1800833dd  mov     rbx, [rsp+1E0h+arg_0]
0x1800833e5  add     rsp, 1C0h
0x1800833ec  pop     r15
0x1800833ee  pop     r14
0x1800833f0  pop     rdi
0x1800833f1  pop     rsi
0x1800833f2  pop     rbp
0x1800833f3  retn
```
