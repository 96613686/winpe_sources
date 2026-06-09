# CBusNode::Initialize(void)

- ea: `0x180008c14`
- end: `0x18000900a`
- name: `?Initialize@CBusNode@@SAJXZ`
- size: `1014`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180006670`

## callees

- `0x18000236c`
- `0x1800023ec`
- `0x180006d40`
- `0x1800071d4`
- `0x1800083dc`
- `0x1800084d8`
- `0x18000853c`
- `0x180008684`
- `0x180008948`
- `0x180008af4`
- `0x180008c14`
- `0x180009274`
- `0x180009ba8`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008cfb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008edb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008edb`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180008eca`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180008eca`

## pseudocode

```c
__int64 CBusNode::Initialize(void)
{
  CBusNode::CCreateContext *v0; // rbx
  unsigned __int64 v1; // rdi
  HANDLE EventW; // rax
  void *v3; // rcx
  signed int LastError; // ebx
  __int64 v5; // rcx
  const unsigned __int16 *v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rcx
  int v9; // edx
  __int64 v10; // rcx
  DWORD v11; // eax
  __int64 v12; // rcx
  unsigned __int64 i; // rbx
  __int64 v14; // rcx
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD *v21; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[3]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handles[2]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v24[32]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v25[3]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v26[24]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v27[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v28; // [rsp+C8h] [rbp-38h]
  __int64 v29; // [rsp+D8h] [rbp-28h]
  __int64 v30; // [rsp+E0h] [rbp-20h]
  _QWORD v31[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int16 v32; // [rsp+F8h] [rbp-8h]
  __int64 v33; // [rsp+108h] [rbp+8h]
  __int64 v34; // [rsp+110h] [rbp+10h]
  char v35[24]; // [rsp+118h] [rbp+18h] BYREF

  v19 = 0;
  v20 = 0;
  strcpy(v35, "CBusNode::Initialize");
  v22[0] = v35;
  v22[1] = &v20;
  v22[2] = &v19;
  lambda_b10ddd926283de899fd71ab53d9261f8_::operator()(v22);
  v20 = 1;
  v21 = v22;
  `eh vector constructor iterator'(
    v24,
    0x10u,
    2u,
    (void (*)(void *))Microsoft::WRL::Wrappers::Event::Event,
    (void (*)(void *))Microsoft::WRL::Wrappers::Event::~Event);
  *(_OWORD *)Handles = 0;
  v0 = (CBusNode::CCreateContext *)v25;
  v1 = 2;
  do
  {
    CBusNode::CCreateContext::CCreateContext(v0);
    v0 = (CBusNode::CCreateContext *)((char *)v0 + 24);
    --v1;
  }
  while ( v1 );
  while ( 1 )
  {
    if ( v1 >= 2 )
    {
      v31[0] = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable';
      v31[1] = 0;
      v34 = 7;
      v33 = 0;
      v32 = 0;
      v27[0] = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable';
      v27[1] = 0;
      v30 = 7;
      v29 = 0;
      v28 = 0;
      v19 = CBusNode::_Create(
              (CBusNode *)v31,
              &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable',
              L"0",
              L"Smart Card Device Enumeration Bus",
              (struct CBusNode::CCreateContext *)v25);
      if ( v19 >= 0 )
      {
        v19 = CBusNode::_Create(
                (CBusNode *)v27,
                v6,
                L"1",
                L"Microsoft Passport Container Enumeration Bus",
                (struct CBusNode::CCreateContext *)v26);
        if ( v19 >= 0 )
        {
          v11 = WaitForMultipleObjects(2u, Handles, 1, 0x7530u);
          LastError = v11;
          if ( v11 )
          {
            if ( v11 == -1 )
              LastError = GetLastError();
            WppTraceIndent(v12, 2);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                16,
                (unsigned int)&WPP_6cda2a62f3993c60960f64b829dda9e7_Traceguids,
                (_DWORD)WPP_pszIndent,
                LastError);
            }
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v19 = LastError;
            goto LABEL_44;
          }
          for ( i = 0; ; ++i )
          {
            if ( i >= 2 )
            {
              CBusNode::operator=(&CBusNode::s_InformationBus, v31);
              CBusNode::operator=(&CBusNode::s_NgcBus, v27);
              goto LABEL_43;
            }
            v14 = LODWORD(v25[3 * i + 1]);
            if ( (int)v14 < 0 )
              break;
          }
          v19 = v25[3 * i + 1];
          WppTraceIndent(v14, 2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_sPd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, v17, i, v19);
          }
LABEL_43:
          LastError = v19;
LABEL_44:
          CBusNode::~CBusNode((CBusNode *)v27);
          CBusNode::~CBusNode((CBusNode *)v31);
          goto LABEL_45;
        }
        WppTraceIndent(v10, 2);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_43;
        }
        v9 = 15;
      }
      else
      {
        WppTraceIndent(v7, 2);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_43;
        }
        v9 = 14;
      }
      WPP_SF_sd(v8[2], v9, (unsigned int)&WPP_6cda2a62f3993c60960f64b829dda9e7_Traceguids, (_DWORD)WPP_pszIndent, v19);
      goto LABEL_43;
    }
    EventW = CreateEventW(0, 1, 0, 0);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(
      &v24[16 * v1],
      EventW);
    v3 = *(void **)&v24[16 * v1 + 8];
    if ( !v3 )
      break;
    Handles[v1] = v3;
    v25[3 * v1++] = v3;
  }
  LastError = GetLastError();
  WppTraceIndent(v5, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)&WPP_6cda2a62f3993c60960f64b829dda9e7_Traceguids,
      (_DWORD)WPP_pszIndent,
      LastError);
  }
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v19 = LastError;
LABEL_45:
  `eh vector destructor iterator'(v24, 0x10u, 2u, (void (*)(void *))Microsoft::WRL::Wrappers::Event::~Event);
  WppTraceUnwinder__lambda_b10ddd926283de899fd71ab53d9261f8____::_WppTraceUnwinder__lambda_b10ddd926283de899fd71ab53d9261f8____(&v21);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180008c14  push    rbp
0x180008c16  push    rbx
0x180008c17  push    rsi
0x180008c18  push    rdi
0x180008c19  push    r13
0x180008c1b  lea     rbp, [rsp-40h]
0x180008c20  sub     rsp, 140h
0x180008c27  mov     rax, cs:__security_cookie
0x180008c2e  xor     rax, rsp
0x180008c31  mov     [rbp+60h+var_30], rax
0x180008c35  mov     [rsp+160h+var_130], 0
0x180008c3d  mov     [rsp+160h+var_12C], 0
0x180008c45  movups  xmm0, xmmword ptr cs:aCbusnodeInitia; "CBusNode::Initialize"
0x180008c4c  movups  xmmword ptr [rbp+60h+var_48], xmm0
0x180008c50  movsd   xmm1, qword ptr cs:aCbusnodeInitia+0Dh; "tialize"
0x180008c58  movsd   qword ptr [rbp+60h+var_48+0Dh], xmm1
0x180008c5d  lea     rax, [rbp+60h+var_48]
0x180008c61  mov     [rsp+160h+var_120], rax
0x180008c66  lea     rax, [rsp+160h+var_12C]
0x180008c6b  mov     [rsp+160h+var_118], rax
0x180008c70  lea     rax, [rsp+160h+var_130]
0x180008c75  mov     [rsp+160h+var_110], rax
0x180008c7a  lea     rcx, [rsp+160h+var_120]
0x180008c7f  call    _lambda_b10ddd926283de899fd71ab53d9261f8___operator__
0x180008c84  mov     [rsp+160h+var_12C], 1
0x180008c8c  lea     rax, [rsp+160h+var_120]
0x180008c91  mov     [rsp+160h+var_128], rax
0x180008c96  lea     r13, ??1Event@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Event::~Event(void)
0x180008c9d  mov     [rsp+160h+var_140], r13; void (*)(void *)
0x180008ca2  lea     r9, ??0Event@Wrappers@WRL@Microsoft@@QEAA@XZ; void (*)(void *)
0x180008ca9  mov     esi, 2
0x180008cae  mov     r8d, esi; unsigned __int64
0x180008cb1  lea     edx, [rsi+0Eh]; unsigned __int64
0x180008cb4  lea     rcx, [rsp+160h+var_F8]; void *
0x180008cb9  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180008cbe  nop
0x180008cbf  xorps   xmm0, xmm0
0x180008cc2  movups  xmmword ptr [rsp+160h+Handles], xmm0
0x180008cc7  lea     rbx, [rbp+60h+var_D8]
0x180008ccb  mov     edi, esi
0x180008ccd  mov     rcx, rbx; this
0x180008cd0  call    ??0CCreateContext@CBusNode@@QEAA@XZ; CBusNode::CCreateContext::CCreateContext(void)
0x180008cd5  add     rbx, 18h
0x180008cd9  sub     rdi, 1
0x180008cdd  jnz     short loc_180008CCD
0x180008cdf  cmp     rdi, rsi
0x180008ce2  jnb     loc_180008D92
0x180008ce8  mov     rbx, rdi
0x180008ceb  shl     rbx, 4
0x180008cef  xor     r9d, r9d; lpName
0x180008cf2  xor     r8d, r8d; bInitialState
0x180008cf5  lea     edx, [r9+1]; bManualReset
0x180008cf9  xor     ecx, ecx; lpEventAttributes
0x180008cfb  call    cs:__imp_CreateEventW
0x180008d01  mov     rdx, rax
0x180008d04  lea     rcx, [rsp+160h+var_F8]
0x180008d09  add     rcx, rbx
0x180008d0c  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x180008d11  mov     rcx, [rsp+rbx+160h+var_F0]
0x180008d16  test    rcx, rcx
0x180008d19  jz      short loc_180008D2E
0x180008d1b  mov     [rsp+rdi*8+160h+Handles], rcx
0x180008d20  lea     rax, [rdi+rdi*2]
0x180008d24  mov     [rbp+rax*8+60h+var_D8], rcx
0x180008d29  inc     rdi
0x180008d2c  jmp     short loc_180008CDF
0x180008d2e  call    cs:__imp_GetLastError
0x180008d34  mov     ebx, eax
0x180008d36  mov     edx, esi
0x180008d38  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008d3d  lea     rax, WPP_GLOBAL_Control
0x180008d44  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d4b  cmp     rcx, rax
0x180008d4e  jz      short loc_180008D7C
0x180008d50  test    byte ptr [rcx+1Ch], 1
0x180008d54  jz      short loc_180008D7C
0x180008d56  cmp     [rcx+19h], sil
0x180008d5a  jb      short loc_180008D7C
0x180008d5c  mov     edx, 0Dh
0x180008d61  mov     dword ptr [rsp+160h+var_140], ebx
0x180008d65  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180008d6c  lea     r8, WPP_6cda2a62f3993c60960f64b829dda9e7_Traceguids
0x180008d73  mov     rcx, [rcx+10h]
0x180008d77  call    WPP_SF_sd
0x180008d7c  test    ebx, ebx
0x180008d7e  jle     short loc_180008D89
0x180008d80  movzx   ebx, bx
0x180008d83  or      ebx, 80070000h
0x180008d89  mov     [rsp+160h+var_130], ebx
0x180008d8d  jmp     loc_180008FCE
0x180008d92  lea     rdx, ??_7?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@6B@; unsigned __int16 *
0x180008d99  mov     [rbp+60h+var_78], rdx
0x180008d9d  mov     [rbp+60h+var_70], 0
0x180008da5  mov     ecx, 7
0x180008daa  mov     [rbp+60h+var_50], rcx
0x180008dae  mov     [rbp+60h+var_58], 0
0x180008db6  xor     eax, eax
0x180008db8  mov     [rbp+60h+var_68], ax
0x180008dbc  mov     [rbp+60h+var_A8], rdx
0x180008dc0  mov     [rbp+60h+var_A0], rax
0x180008dc4  mov     [rbp+60h+var_80], rcx
0x180008dc8  mov     [rbp+60h+var_88], rax
0x180008dcc  mov     [rbp+60h+var_98], ax
0x180008dd0  lea     rax, [rbp+60h+var_D8]
0x180008dd4  mov     [rsp+160h+var_140], rax; struct CBusNode::CCreateContext *
0x180008dd9  lea     r9, aSmartCardDevic; "Smart Card Device Enumeration Bus"
0x180008de0  lea     r8, a0; "0"
0x180008de7  lea     rcx, [rbp+60h+var_78]; this
0x180008deb  call    ?_Create@CBusNode@@AEAAJPEBG00PEAUCCreateContext@1@@Z; CBusNode::_Create(ushort const *,ushort const *,ushort const *,CBusNode::CCreateContext *)
0x180008df0  mov     [rsp+160h+var_130], eax
0x180008df4  test    eax, eax
0x180008df6  jns     short loc_180008E53
0x180008df8  mov     edx, esi
0x180008dfa  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008dff  lea     rax, WPP_GLOBAL_Control
0x180008e06  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e0d  cmp     rcx, rax
0x180008e10  jz      loc_180008FB6
0x180008e16  test    byte ptr [rcx+1Ch], 1
0x180008e1a  jz      loc_180008FB6
0x180008e20  cmp     [rcx+19h], sil
0x180008e24  jb      loc_180008FB6
0x180008e2a  mov     edx, 0Eh
0x180008e2f  mov     eax, [rsp+160h+var_130]
0x180008e33  mov     dword ptr [rsp+160h+var_140], eax
0x180008e37  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180008e3e  lea     r8, WPP_6cda2a62f3993c60960f64b829dda9e7_Traceguids
0x180008e45  mov     rcx, [rcx+10h]
0x180008e49  call    WPP_SF_sd
0x180008e4e  jmp     loc_180008FB6
0x180008e53  lea     rax, [rbp+60h+var_C0]
0x180008e57  mov     [rsp+160h+var_140], rax; struct CBusNode::CCreateContext *
0x180008e5c  lea     r9, aMicrosoftPassp_0; "Microsoft Passport Container Enumeratio"...
0x180008e63  lea     r8, a1; "1"
0x180008e6a  lea     rcx, [rbp+60h+var_A8]; this
0x180008e6e  call    ?_Create@CBusNode@@AEAAJPEBG00PEAUCCreateContext@1@@Z; CBusNode::_Create(ushort const *,ushort const *,ushort const *,CBusNode::CCreateContext *)
0x180008e73  mov     [rsp+160h+var_130], eax
0x180008e77  test    eax, eax
0x180008e79  jns     short loc_180008EB7
0x180008e7b  mov     edx, esi
0x180008e7d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008e82  lea     rax, WPP_GLOBAL_Control
0x180008e89  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e90  cmp     rcx, rax
0x180008e93  jz      loc_180008FB6
0x180008e99  test    byte ptr [rcx+1Ch], 1
0x180008e9d  jz      loc_180008FB6
0x180008ea3  cmp     [rcx+19h], sil
0x180008ea7  jb      loc_180008FB6
0x180008ead  mov     edx, 0Fh
0x180008eb2  jmp     loc_180008E2F
0x180008eb7  mov     r9d, 7530h; dwMilliseconds
0x180008ebd  mov     r8d, 1; bWaitAll
0x180008ec3  lea     rdx, [rsp+160h+Handles]; lpHandles
0x180008ec8  mov     ecx, esi; nCount
0x180008eca  call    cs:__imp_WaitForMultipleObjects
0x180008ed0  mov     ebx, eax
0x180008ed2  test    eax, eax
0x180008ed4  jz      short loc_180008F3C
0x180008ed6  cmp     eax, 0FFFFFFFFh
0x180008ed9  jnz     short loc_180008EE3
0x180008edb  call    cs:__imp_GetLastError
0x180008ee1  mov     ebx, eax
0x180008ee3  mov     edx, esi
0x180008ee5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008eea  lea     rax, WPP_GLOBAL_Control
0x180008ef1  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ef8  cmp     rcx, rax
0x180008efb  jz      short loc_180008F29
0x180008efd  test    byte ptr [rcx+1Ch], 1
0x180008f01  jz      short loc_180008F29
0x180008f03  cmp     [rcx+19h], sil
0x180008f07  jb      short loc_180008F29
0x180008f09  mov     edx, 10h
0x180008f0e  mov     dword ptr [rsp+160h+var_140], ebx
0x180008f12  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180008f19  lea     r8, WPP_6cda2a62f3993c60960f64b829dda9e7_Traceguids
0x180008f20  mov     rcx, [rcx+10h]
0x180008f24  call    WPP_SF_sd
0x180008f29  test    ebx, ebx
0x180008f2b  jle     short loc_180008F36
0x180008f2d  movzx   ebx, bx
0x180008f30  or      ebx, 80070000h
0x180008f36  mov     [rsp+160h+var_130], ebx
0x180008f3a  jmp     short loc_180008FBA
0x180008f3c  xor     ebx, ebx
0x180008f3e  cmp     rbx, rsi
0x180008f41  jnb     short loc_180008F96
0x180008f43  lea     rax, [rbx+rbx*2]
0x180008f47  mov     ecx, [rbp+rax*8+60h+var_D0]
0x180008f4b  test    ecx, ecx
0x180008f4d  js      short loc_180008F54
0x180008f4f  inc     rbx
0x180008f52  jmp     short loc_180008F3E
0x180008f54  mov     [rsp+160h+var_130], ecx
0x180008f58  mov     edx, esi
0x180008f5a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008f5f  lea     rax, WPP_GLOBAL_Control
0x180008f66  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f6d  cmp     rcx, rax
0x180008f70  jz      short loc_180008FB6
0x180008f72  test    byte ptr [rcx+1Ch], 1
0x180008f76  jz      short loc_180008FB6
0x180008f78  cmp     [rcx+19h], sil
0x180008f7c  jb      short loc_180008FB6
0x180008f7e  mov     eax, [rsp+160h+var_130]
0x180008f82  mov     [rsp+160h+var_138], eax
0x180008f86  mov     [rsp+160h+var_140], rbx
0x180008f8b  mov     rcx, [rcx+10h]
0x180008f8f  call    WPP_SF_sPd
0x180008f94  jmp     short loc_180008FB6
0x180008f96  lea     rdx, [rbp+60h+var_78]
0x180008f9a  lea     rcx, ?s_InformationBus@CBusNode@@0V1@A; CBusNode CBusNode::s_InformationBus
0x180008fa1  call    ??4CBusNode@@QEAAAEAV0@$$QEAV0@@Z; CBusNode::operator=(CBusNode &&)
0x180008fa6  lea     rdx, [rbp+60h+var_A8]
0x180008faa  lea     rcx, ?s_NgcBus@CBusNode@@0V1@A; CBusNode CBusNode::s_NgcBus
0x180008fb1  call    ??4CBusNode@@QEAAAEAV0@$$QEAV0@@Z; CBusNode::operator=(CBusNode &&)
0x180008fb6  mov     ebx, [rsp+160h+var_130]
0x180008fba  lea     rcx, [rbp+60h+var_A8]; this
0x180008fbe  call    ??1CBusNode@@QEAA@XZ; CBusNode::~CBusNode(void)
0x180008fc3  nop
0x180008fc4  lea     rcx, [rbp+60h+var_78]; this
0x180008fc8  call    ??1CBusNode@@QEAA@XZ; CBusNode::~CBusNode(void)
0x180008fcd  nop
0x180008fce  mov     r9, r13; void (*)(void *)
0x180008fd1  mov     r8, rsi; unsigned __int64
0x180008fd4  mov     edx, 10h; unsigned __int64
0x180008fd9  lea     rcx, [rsp+160h+var_F8]; void *
0x180008fde  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180008fe3  nop
0x180008fe4  lea     rcx, [rsp+160h+var_128]
0x180008fe9  call    WppTraceUnwinder__lambda_b10ddd926283de899fd71ab53d9261f8_______WppTraceUnwinder__lambda_b10ddd926283de899fd71ab53d9261f8____
0x180008fee  mov     eax, ebx
0x180008ff0  mov     rcx, [rbp+60h+var_30]
0x180008ff4  xor     rcx, rsp; StackCookie
0x180008ff7  call    __security_check_cookie
0x180008ffc  add     rsp, 140h
0x180009003  pop     r13
0x180009005  pop     rdi
0x180009006  pop     rsi
0x180009007  pop     rbx
0x180009008  pop     rbp
0x180009009  retn
```
