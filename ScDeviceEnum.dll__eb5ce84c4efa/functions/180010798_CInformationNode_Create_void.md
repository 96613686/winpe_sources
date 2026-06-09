# CInformationNode::Create(void)

- ea: `0x180010798`
- end: `0x180010b4b`
- name: `?Create@CInformationNode@@QEAAJXZ`
- size: `947`
- prototype: `__int64 __fastcall(CInformationNode *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cf60`
- `0x180010b54`

## callees

- `0x180006d40`
- `0x180007178`
- `0x1800071d4`
- `0x180007d34`
- `0x180008af4`
- `0x180009c38`
- `0x18000fd4c`
- `0x180010118`
- `0x18001056c`
- `0x180010638`
- `0x180010798`
- `0x1800118f0`
- `0x18001dfe2`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800108db`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800108db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108f4`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180010a43`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180010a43`

## string_xrefs

- `0x1800107d4`: `CInformationNode::Create`

## pseudocode

```c
__int64 __fastcall CInformationNode::Create(CInformationNode *this)
{
  __int64 v2; // rcx
  int v3; // r8d
  PVOID v4; // rcx
  CInformationNode *v5; // rax
  unsigned int v6; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 *v9; // rax
  CInformationNode *v10; // rcx
  __int64 *v11; // rdx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // edi
  signed int v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v18; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v19; // [rsp+58h] [rbp-A8h]
  _QWORD *v20; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v21[3]; // [rsp+68h] [rbp-98h] BYREF
  int v22; // [rsp+80h] [rbp-80h] BYREF
  __int64 v23; // [rsp+88h] [rbp-78h]
  const wchar_t *v24; // [rsp+90h] [rbp-70h]
  int v25; // [rsp+A8h] [rbp-58h]
  const wchar_t *v26; // [rsp+B0h] [rbp-50h]
  DEVPROPKEY v27; // [rsp+D0h] [rbp-30h] BYREF
  int v28; // [rsp+E4h] [rbp-1Ch]
  __int64 v29; // [rsp+E8h] [rbp-18h]
  int v30; // [rsp+F0h] [rbp-10h]
  int v31; // [rsp+F4h] [rbp-Ch]
  char *v32; // [rsp+F8h] [rbp-8h]
  DEVPROPKEY v33; // [rsp+100h] [rbp+0h]
  int v34; // [rsp+114h] [rbp+14h]
  __int64 v35; // [rsp+118h] [rbp+18h]
  int v36; // [rsp+120h] [rbp+20h]
  int v37; // [rsp+124h] [rbp+24h]
  CInformationNode *v38; // [rsp+128h] [rbp+28h]
  char v39[32]; // [rsp+130h] [rbp+30h] BYREF

  v16 = 0;
  v17 = 0;
  strcpy(v39, "CInformationNode::Create");
  v21[0] = v39;
  v21[1] = &v17;
  v21[2] = &v16;
  lambda_dfdc5e9c395ac45fbbb0083d1faef26a_::operator()(v21);
  v17 = 1;
  v20 = v21;
  WppTraceIndent(v2, 2);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    if ( *((_QWORD *)this + 3) < 8u )
      v5 = this;
    else
      v5 = *(CInformationNode **)this;
    WPP_SF_sdS(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v3, (_DWORD)WPP_pszIndent, *((_DWORD *)this + 13), (__int64)v5);
  }
  if ( *((_QWORD *)this + 8) )
  {
    WppTraceIndent(v4, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids, WPP_pszIndent);
    }
    v6 = v16;
    goto LABEL_35;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(
    (char *)this + 72,
    EventW);
  if ( !*((_QWORD *)this + 10) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v16 = LastError;
    v6 = LastError;
    goto LABEL_35;
  }
  CTaskCounter::Increment();
  v18 = *(_OWORD *)lambda_7b962508ef797b8a60bb150b3e2a6f9c_::_lambda_7b962508ef797b8a60bb150b3e2a6f9c_(&v18, this, &v16);
  v19 = 258;
  memset_0(&v22, 0, 0x48u);
  v22 = 72;
  v9 = (__int64 *)*((_QWORD *)this + 4);
  if ( (unsigned __int64)v9[3] < 8 )
    v9 = (__int64 *)((char *)this + 32);
  v23 = *v9;
  v26 = L"Smart Card Device Information Node";
  v24 = L"ScDeviceInformationNode\\node";
  v25 = 6;
  v29 = 0;
  v35 = 0;
  v27 = DEVPKEY_Device_SessionId;
  v28 = 0;
  v30 = 7;
  v31 = 4;
  v32 = (char *)this + 52;
  if ( *((_QWORD *)this + 3) < 8u )
    v10 = this;
  else
    v10 = *(CInformationNode **)this;
  v33 = DEVPKEY_Device_FriendlyName;
  v34 = 0;
  v36 = 18;
  v37 = 2 * *((_DWORD *)this + 4) + 2;
  v38 = v10;
  v11 = &qword_18002B0D0;
  if ( (unsigned __int64)qword_18002B0E8 >= 8 )
    v11 = (__int64 *)qword_18002B0D0;
  v12 = SwDeviceCreate(L"ScDeviceEnum", v11, &v22, 2, &v27, CInformationNode::_CreateCallback, this, (char *)this + 64);
  v14 = v12;
  v16 = v12;
  if ( v12 >= 0 )
  {
LABEL_34:
    HIBYTE(v19) = 0;
    wil::details::ScopeExitFnGuard__lambda_20719347f9a528df7ea1b11ec20d636d___::operator()(&v18);
    v6 = v14;
    goto LABEL_35;
  }
  if ( v12 == -2147024713 )
  {
    WppTraceIndent(v13, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      if ( *((_QWORD *)this + 3) >= 8u )
        this = *(CInformationNode **)this;
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids,
        (_DWORD)WPP_pszIndent,
        (__int64)this);
    }
    v16 = 0;
    v14 = 0;
    goto LABEL_34;
  }
  WppTraceIndent(v13, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)&WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids,
      (_DWORD)WPP_pszIndent,
      v16);
  }
  v6 = v16;
  wil::details::ScopeExitFnGuard__lambda_20719347f9a528df7ea1b11ec20d636d___::operator()(&v18);
LABEL_35:
  WppTraceUnwinder__lambda_dfdc5e9c395ac45fbbb0083d1faef26a____::_WppTraceUnwinder__lambda_dfdc5e9c395ac45fbbb0083d1faef26a____(&v20);
  return v6;
}

```

## disassembly

```asm
0x180010798  mov     [rsp-8+arg_8], rbx
0x18001079d  mov     [rsp-8+arg_10], rdi
0x1800107a2  push    rbp
0x1800107a3  push    r12
0x1800107a5  push    r13
0x1800107a7  lea     rbp, [rsp-60h]
0x1800107ac  sub     rsp, 160h
0x1800107b3  mov     rax, cs:__security_cookie
0x1800107ba  xor     rax, rsp
0x1800107bd  mov     [rbp+70h+var_20], rax
0x1800107c1  mov     rbx, rcx
0x1800107c4  mov     [rsp+170h+var_130], 0
0x1800107cc  mov     [rsp+170h+var_12C], 0
0x1800107d4  movups  xmm0, xmmword ptr cs:aCinformationno_3; "CInformationNode::Create"
0x1800107db  movups  xmmword ptr [rbp+70h+var_40], xmm0
0x1800107df  movups  xmm1, xmmword ptr cs:aCinformationno_3+9; "ionNode::Create"
0x1800107e6  movups  xmmword ptr [rbp+70h+var_40+9], xmm1
0x1800107ea  lea     rax, [rbp+70h+var_40]
0x1800107ee  mov     [rsp+170h+var_108], rax
0x1800107f3  lea     rax, [rsp+170h+var_12C]
0x1800107f8  mov     [rsp+170h+var_100], rax
0x1800107fd  lea     rax, [rsp+170h+var_130]
0x180010802  mov     [rsp+170h+var_F8], rax
0x180010807  lea     rcx, [rsp+170h+var_108]
0x18001080c  call    _lambda_dfdc5e9c395ac45fbbb0083d1faef26a___operator__
0x180010811  mov     [rsp+170h+var_12C], 1
0x180010819  lea     rax, [rsp+170h+var_108]
0x18001081e  mov     [rsp+170h+var_110], rax
0x180010823  mov     r12d, 2
0x180010829  mov     edx, r12d
0x18001082c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180010831  lea     r13, WPP_GLOBAL_Control
0x180010838  mov     rcx, cs:WPP_GLOBAL_Control
0x18001083f  cmp     rcx, r13
0x180010842  jz      short loc_180010880
0x180010844  test    byte ptr [rcx+1Ch], 1
0x180010848  jz      short loc_180010880
0x18001084a  cmp     byte ptr [rcx+19h], 4
0x18001084e  jb      short loc_180010880
0x180010850  cmp     qword ptr [rbx+18h], 8
0x180010855  jb      short loc_18001085C
0x180010857  mov     rax, [rbx]
0x18001085a  jmp     short loc_18001085F
0x18001085c  mov     rax, rbx
0x18001085f  mov     edx, 10h
0x180010864  mov     [rsp+170h+var_148], rax
0x180010869  mov     eax, [rbx+34h]
0x18001086c  mov     dword ptr [rsp+170h+var_150], eax
0x180010870  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180010877  mov     rcx, [rcx+10h]
0x18001087b  call    WPP_SF_sdS
0x180010880  lea     rdi, [rbx+40h]
0x180010884  cmp     qword ptr [rdi], 0
0x180010888  jz      short loc_1800108CF
0x18001088a  mov     edx, r12d
0x18001088d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180010892  mov     rcx, cs:WPP_GLOBAL_Control
0x180010899  cmp     rcx, r13
0x18001089c  jz      short loc_1800108C6
0x18001089e  test    byte ptr [rcx+1Ch], 1
0x1800108a2  jz      short loc_1800108C6
0x1800108a4  cmp     byte ptr [rcx+19h], 4
0x1800108a8  jb      short loc_1800108C6
0x1800108aa  mov     edx, 11h
0x1800108af  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800108b6  lea     r8, WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids
0x1800108bd  mov     rcx, [rcx+10h]
0x1800108c1  call    WPP_SF_s
0x1800108c6  mov     ebx, [rsp+170h+var_130]
0x1800108ca  jmp     loc_180010AC4
0x1800108cf  xor     r9d, r9d; lpName
0x1800108d2  xor     r8d, r8d; bInitialState
0x1800108d5  lea     edx, [r9+1]; bManualReset
0x1800108d9  xor     ecx, ecx; lpEventAttributes
0x1800108db  call    cs:__imp_CreateEventW
0x1800108e1  mov     rdx, rax
0x1800108e4  lea     rcx, [rbx+48h]
0x1800108e8  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x1800108ed  cmp     qword ptr [rbx+50h], 0
0x1800108f2  jnz     short loc_180010911
0x1800108f4  call    cs:__imp_GetLastError
0x1800108fa  test    eax, eax
0x1800108fc  jle     short loc_180010906
0x1800108fe  movzx   eax, ax
0x180010901  or      eax, 80070000h
0x180010906  mov     [rsp+170h+var_130], eax
0x18001090a  mov     ebx, eax
0x18001090c  jmp     loc_180010AC4
0x180010911  call    ?Increment@CTaskCounter@@SAJXZ; CTaskCounter::Increment(void)
0x180010916  lea     r8, [rsp+170h+var_130]
0x18001091b  mov     rdx, rbx
0x18001091e  lea     rcx, [rsp+170h+var_128]
0x180010923  call    _lambda_7b962508ef797b8a60bb150b3e2a6f9c____lambda_7b962508ef797b8a60bb150b3e2a6f9c_
0x180010928  movups  xmm0, xmmword ptr [rax]
0x18001092b  movdqu  [rsp+170h+var_128], xmm0
0x180010931  mov     [rsp+170h+var_118], 102h
0x180010938  xor     edx, edx; Val
0x18001093a  lea     r8d, [rdx+48h]; Size
0x18001093e  lea     rcx, [rbp+70h+var_F0]; void *
0x180010942  call    memset_0
0x180010947  mov     [rbp+70h+var_F0], 48h ; 'H'
0x18001094e  lea     rcx, [rbx+20h]
0x180010952  mov     rax, [rcx]
0x180010955  cmp     qword ptr [rax+18h], 8
0x18001095a  cmovb   rax, rcx
0x18001095e  mov     rax, [rax]
0x180010961  mov     [rbp+70h+var_E8], rax
0x180010965  lea     rax, aSmartCardDevic_0; "Smart Card Device Information Node"
0x18001096c  mov     [rbp+70h+var_C0], rax
0x180010970  lea     rax, aScdeviceinform; "ScDeviceInformationNode\\node"
0x180010977  mov     [rbp+70h+var_E0], rax
0x18001097b  mov     [rbp+70h+var_C8], 6
0x180010982  xor     eax, eax
0x180010984  mov     [rbp+70h+var_88], rax
0x180010988  mov     [rbp+70h+var_58], rax
0x18001098c  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_SessionId.fmtid.Data1
0x180010993  movaps  [rbp+70h+var_A0], xmm0
0x180010997  mov     eax, cs:DEVPKEY_Device_SessionId.pid
0x18001099d  mov     [rbp+70h+var_90], eax
0x1800109a0  mov     [rbp+70h+var_8C], 0
0x1800109a7  mov     [rbp+70h+var_80], 7
0x1800109ae  mov     [rbp+70h+var_7C], 4
0x1800109b5  lea     rax, [rbx+34h]
0x1800109b9  mov     [rbp+70h+var_78], rax
0x1800109bd  cmp     qword ptr [rbx+18h], 8
0x1800109c2  jb      short loc_1800109C9
0x1800109c4  mov     rcx, [rbx]
0x1800109c7  jmp     short loc_1800109CC
0x1800109c9  mov     rcx, rbx
0x1800109cc  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x1800109d3  movaps  [rbp+70h+var_70], xmm0
0x1800109d7  mov     eax, cs:DEVPKEY_Device_FriendlyName.pid
0x1800109dd  mov     [rbp+70h+var_60], eax
0x1800109e0  mov     [rbp+70h+var_5C], 0
0x1800109e7  mov     [rbp+70h+var_50], 12h
0x1800109ee  mov     eax, [rbx+10h]
0x1800109f1  lea     eax, ds:2[rax*2]
0x1800109f8  mov     [rbp+70h+var_4C], eax
0x1800109fb  mov     [rbp+70h+var_48], rcx
0x1800109ff  lea     rdx, qword_18002B0D0
0x180010a06  cmp     cs:qword_18002B0E8, 8
0x180010a0e  cmovnb  rdx, cs:qword_18002B0D0
0x180010a16  mov     [rsp+170h+var_138], rdi
0x180010a1b  mov     [rsp+170h+var_140], rbx
0x180010a20  lea     rax, ?_CreateCallback@CInformationNode@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; CInformationNode::_CreateCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x180010a27  mov     [rsp+170h+var_148], rax
0x180010a2c  lea     rax, [rbp+70h+var_A0]
0x180010a30  mov     [rsp+170h+var_150], rax
0x180010a35  mov     r9d, r12d
0x180010a38  lea     r8, [rbp+70h+var_F0]
0x180010a3c  lea     rcx, ServiceName; "ScDeviceEnum"
0x180010a43  call    cs:__imp_SwDeviceCreate
0x180010a49  mov     edi, eax
0x180010a4b  mov     [rsp+170h+var_130], eax
0x180010a4f  test    eax, eax
0x180010a51  jns     short loc_180010AB3
0x180010a53  mov     edx, r12d
0x180010a56  cmp     eax, 800700B7h
0x180010a5b  jnz     loc_180010AF5
0x180010a61  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180010a66  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a6d  cmp     rcx, r13
0x180010a70  jz      short loc_180010AA9
0x180010a72  test    byte ptr [rcx+1Ch], 1
0x180010a76  jz      short loc_180010AA9
0x180010a78  cmp     byte ptr [rcx+19h], 4
0x180010a7c  jb      short loc_180010AA9
0x180010a7e  cmp     qword ptr [rbx+18h], 8
0x180010a83  jb      short loc_180010A88
0x180010a85  mov     rbx, [rbx]
0x180010a88  mov     edx, 12h
0x180010a8d  mov     [rsp+170h+var_150], rbx
0x180010a92  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180010a99  lea     r8, WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids
0x180010aa0  mov     rcx, [rcx+10h]
0x180010aa4  call    WPP_SF_sS
0x180010aa9  mov     [rsp+170h+var_130], 0
0x180010ab1  xor     edi, edi
0x180010ab3  mov     byte ptr [rsp+170h+var_118+1], 0
0x180010ab8  lea     rcx, [rsp+170h+var_128]
0x180010abd  call    wil__details__ScopeExitFnGuard__lambda_20719347f9a528df7ea1b11ec20d636d_____operator__
0x180010ac2  mov     ebx, edi
0x180010ac4  lea     rcx, [rsp+170h+var_110]
0x180010ac9  call    WppTraceUnwinder__lambda_dfdc5e9c395ac45fbbb0083d1faef26a_______WppTraceUnwinder__lambda_dfdc5e9c395ac45fbbb0083d1faef26a____
0x180010ace  mov     eax, ebx
0x180010ad0  mov     rcx, [rbp+70h+var_20]
0x180010ad4  xor     rcx, rsp; StackCookie
0x180010ad7  call    __security_check_cookie
0x180010adc  lea     r11, [rsp+170h+var_10]
0x180010ae4  mov     rbx, [r11+28h]
0x180010ae8  mov     rdi, [r11+30h]
0x180010aec  mov     rsp, r11
0x180010aef  pop     r13
0x180010af1  pop     r12
0x180010af3  pop     rbp
0x180010af4  retn
0x180010af5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180010afa  nop
0x180010afb  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b02  cmp     rcx, r13
0x180010b05  jz      short loc_180010B37
0x180010b07  test    byte ptr [rcx+1Ch], 1
0x180010b0b  jz      short loc_180010B37
0x180010b0d  cmp     [rcx+19h], r12b
0x180010b11  jb      short loc_180010B37
0x180010b13  mov     edx, 13h
0x180010b18  mov     eax, [rsp+170h+var_130]
0x180010b1c  mov     dword ptr [rsp+170h+var_150], eax
0x180010b20  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180010b27  lea     r8, WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids
0x180010b2e  mov     rcx, [rcx+10h]
0x180010b32  call    WPP_SF_sd
0x180010b37  mov     ebx, [rsp+170h+var_130]
0x180010b3b  lea     rcx, [rsp+170h+var_128]
0x180010b40  call    wil__details__ScopeExitFnGuard__lambda_20719347f9a528df7ea1b11ec20d636d_____operator__
0x180010b45  jmp     loc_180010AC4
```
