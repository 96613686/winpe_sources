# CWwanSmsDevice::PublishSmsWNF(WwanSmsStoreMessage const &,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_SYSTEMTIME,int,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004ef50`
- end: `0x18004f270`
- name: `?PublishSmsWNF@CWwanSmsDevice@@AEAAXAEBUWwanSmsStoreMessage@@KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_SYSTEMTIME@@H1@Z`
- size: `800`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004d928`
- `0x18004e378`

## callees

- `0x180003640`
- `0x180003a60`
- `0x1800069f0`
- `0x18000cf90`
- `0x18000d388`
- `0x18002623c`
- `0x18004a7a0`
- `0x18004cf34`
- `0x18004eea4`
- `0x18004ef50`
- `0x180051628`
- `0x180052a74`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004efbb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004efbb`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f1e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f22f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f1e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f22f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CWwanSmsDevice::PublishSmsWNF(
        __int64 a1,
        int *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        __int64 a5,
        unsigned int a6,
        _QWORD *a7)
{
  _QWORD *v9; // r12
  __int64 v10; // rcx
  __int64 v11; // r8
  unsigned int v12; // r13d
  __int64 v13; // rax
  const unsigned __int16 *v14; // rsi
  const unsigned __int16 *v15; // rbx
  __int64 trivial_2; // rax
  __int64 v17; // rax
  const unsigned __int16 *v18; // rdx
  __int64 v19; // rbx
  OLECHAR *v20; // rdi
  int v21; // eax
  OLECHAR *Ptr; // rbx
  const unsigned __int16 *v23; // rdx
  int v24; // eax
  unsigned int v25; // r12d
  __int64 v26; // r13
  int v27; // eax
  __int64 v28; // [rsp+30h] [rbp-91h]
  unsigned int v29; // [rsp+38h] [rbp-89h]
  int v30; // [rsp+60h] [rbp-61h] BYREF
  unsigned int v31; // [rsp+64h] [rbp-5Dh]
  LPVOID ppv; // [rsp+68h] [rbp-59h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-51h] BYREF
  __int64 v34; // [rsp+78h] [rbp-49h]
  SYSTEMTIME v35; // [rsp+80h] [rbp-41h] BYREF
  unsigned __int16 *v36[2]; // [rsp+90h] [rbp-31h] BYREF
  __m128i si128; // [rsp+A0h] [rbp-21h]
  struct _EVENT_DATA_DESCRIPTOR v38; // [rsp+B0h] [rbp-11h] BYREF

  v31 = a3;
  v34 = a1;
  v9 = a7;
  *(_QWORD *)&v35.wYear = a5;
  v30 = 0;
  ppv = 0;
  if ( CoCreateInstance(&CLSID_ProvisioningEngine, 0, 0x17u, &IID_IProvisioningNotificationProcessor, &ppv) >= 0 )
  {
    v12 = 0;
    if ( a6 )
    {
      if ( (Microsoft_Windows_CoreSystem_SmsRouterEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(v10, (const EVENT_DESCRIPTOR *)SMSClass0TextReceivedEvent, v11, 1u, &v38);
      v12 = 1;
    }
    bstrString = 0;
    v13 = *((_QWORD *)a4 + 2);
    if ( *((_QWORD *)a4 + 3) <= 7u )
      v14 = a4;
    else
      v14 = *(const unsigned __int16 **)a4;
    if ( !v13
      || (v15 = &v14[v13], trivial_2 = _std_find_trivial_2(v14, v15, 43), (const unsigned __int16 *)trivial_2 == v15)
      || (trivial_2 - (__int64)v14) >> 1 == -1 )
    {
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(const unsigned __int16 **)a4;
      ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, a4);
    }
    else
    {
      v17 = *((_QWORD *)a4 + 2);
      *(_OWORD *)v36 = 0;
      si128 = 0;
      if ( !v17 )
        std::_String_val<std::_Simple_types<char>>::_Xran();
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(const unsigned __int16 **)a4;
      std::wstring::_Construct<1,unsigned short const *>((char **)v36, a4 + 1, v17 - 1);
      v18 = (const unsigned __int16 *)v36;
      if ( si128.m128i_i64[1] > 7uLL )
        v18 = v36[0];
      ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, v18);
      std::wstring::~wstring((char **)v36);
    }
    v19 = v34;
    v20 = bstrString;
    v21 = (*(__int64 (__fastcall **)(LPVOID, __int64, BSTR, _QWORD, _DWORD, int *))(*(_QWORD *)ppv + 32LL))(
            ppv,
            v34 + 152,
            bstrString,
            v12,
            0,
            &v30);
    if ( v21 >= 0 && v30 )
    {
      Ptr = 0;
      v38.Ptr = 0;
      *(_OWORD *)v36 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v36[0]) = 0;
      if ( a7[3] > 7u )
        v9 = (_QWORD *)*a7;
      if ( (int)CWwanMessageXmlHelper::GetDecodedMessage(a2, v9, v36) >= 0 )
      {
        v23 = (const unsigned __int16 *)v36;
        if ( si128.m128i_i64[1] > 7uLL )
          v23 = v36[0];
        v24 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v38, v23);
        Ptr = (OLECHAR *)v38.Ptr;
        if ( v24 >= 0 )
        {
          v35 = *(SYSTEMTIME *)*(_QWORD *)&v35.wYear;
          v29 = v12;
          v25 = v31;
          v26 = v34;
          v27 = CWwanSmsDevice::ProcessOperatorNotification(
                  v34,
                  (__int64)ppv,
                  v31,
                  (struct _FILETIME)v20,
                  &v35,
                  v38.Ptr,
                  v28,
                  v29,
                  a6 != 0,
                  (__int64)a2 + 5,
                  *a2);
          if ( v27 < 0 || v27 == 1 )
            CWwanSmsDevice::ProcessUserText(v26, v25, a6);
        }
      }
      std::wstring::~wstring((char **)v36);
      SysFreeString(Ptr);
    }
    else
    {
      LogSmsRouterInfo(
        "CWwanSmsDevice::PublishSmsWNF",
        0x7A5u,
        "Provisioning Engine Can Process Notification returned hr : 0x%x, fOperatorMessage : %d",
        v21,
        v30);
      CWwanSmsDevice::ProcessUserText(v19, v31, a6);
    }
    SysFreeString(v20);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x18004ef50  push    rbp
0x18004ef52  push    rbx
0x18004ef53  push    rsi
0x18004ef54  push    rdi
0x18004ef55  push    r12
0x18004ef57  push    r13
0x18004ef59  push    r14
0x18004ef5b  lea     rbp, [rsp-0Fh]
0x18004ef60  sub     rsp, 0D0h
0x18004ef67  mov     rax, cs:__security_cookie
0x18004ef6e  xor     rax, rsp
0x18004ef71  mov     [rbp+3Fh+var_40], rax
0x18004ef75  mov     rdi, r9
0x18004ef78  mov     [rbp+3Fh+var_9C], r8d
0x18004ef7c  mov     r14, rdx
0x18004ef7f  mov     [rbp+3Fh+var_88], rcx
0x18004ef83  mov     r12, [rbp+3Fh+arg_30]
0x18004ef87  mov     rax, [rbp+3Fh+arg_20]
0x18004ef8b  mov     qword ptr [rbp+3Fh+var_80], rax
0x18004ef8f  mov     [rbp+3Fh+var_A0], 0
0x18004ef96  mov     [rbp+3Fh+var_98], 0
0x18004ef9e  lea     rax, [rbp+3Fh+var_98]
0x18004efa2  mov     [rsp+100h+ppv], rax; ppv
0x18004efa7  lea     r9, IID_IProvisioningNotificationProcessor; riid
0x18004efae  xor     edx, edx; pUnkOuter
0x18004efb0  lea     r8d, [rdx+17h]; dwClsContext
0x18004efb4  lea     rcx, CLSID_ProvisioningEngine; rclsid
0x18004efbb  call    cs:__imp_CoCreateInstance
0x18004efc1  test    eax, eax
0x18004efc3  js      loc_18004F236
0x18004efc9  xor     r13d, r13d
0x18004efcc  cmp     [rbp+3Fh+arg_28], r13d
0x18004efd0  jz      short loc_18004EFFA
0x18004efd2  test    cs:Microsoft_Windows_CoreSystem_SmsRouterEnableBits, 1
0x18004efd9  jz      short loc_18004EFF4
0x18004efdb  lea     rax, [rbp+3Fh+var_50]
0x18004efdf  mov     [rsp+100h+ppv], rax
0x18004efe4  lea     r9d, [r13+1]
0x18004efe8  lea     rdx, SMSClass0TextReceivedEvent
0x18004efef  call    McGenEventWrite_EventWriteTransfer
0x18004eff4  mov     r13d, 1
0x18004effa  mov     [rbp+3Fh+bstrString], 0
0x18004f002  mov     rax, [rdi+10h]
0x18004f006  cmp     qword ptr [rdi+18h], 7
0x18004f00b  jbe     short loc_18004F012
0x18004f00d  mov     rsi, [rdi]
0x18004f010  jmp     short loc_18004F015
0x18004f012  mov     rsi, rdi
0x18004f015  test    rax, rax
0x18004f018  jz      loc_18004F09E
0x18004f01e  lea     rbx, [rsi+rax*2]
0x18004f022  mov     r8d, 2Bh ; '+'
0x18004f028  mov     rdx, rbx
0x18004f02b  mov     rcx, rsi
0x18004f02e  call    __std_find_trivial_2
0x18004f033  cmp     rax, rbx
0x18004f036  jz      short loc_18004F09E
0x18004f038  sub     rax, rsi
0x18004f03b  sar     rax, 1
0x18004f03e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004f042  jz      short loc_18004F09E
0x18004f044  mov     rax, [rdi+10h]
0x18004f048  xorps   xmm0, xmm0
0x18004f04b  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x18004f04f  xorps   xmm1, xmm1
0x18004f052  movdqu  [rbp+3Fh+var_60], xmm1
0x18004f057  cmp     rax, 1
0x18004f05b  jb      loc_18004F26A
0x18004f061  lea     r8, [rax-1]
0x18004f065  cmp     qword ptr [rdi+18h], 7
0x18004f06a  jbe     short loc_18004F06F
0x18004f06c  mov     rdi, [rdi]
0x18004f06f  lea     rdx, [rdi+2]
0x18004f073  lea     rcx, [rbp+3Fh+var_70]
0x18004f077  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004f07c  lea     rdx, [rbp+3Fh+var_70]
0x18004f080  cmp     qword ptr [rbp+3Fh+var_60+8], 7
0x18004f085  cmova   rdx, [rbp+3Fh+var_70]; unsigned __int16 *
0x18004f08a  lea     rcx, [rbp+3Fh+bstrString]; this
0x18004f08e  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18004f093  lea     rcx, [rbp+3Fh+var_70]; void *
0x18004f097  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f09c  jmp     short loc_18004F0B4
0x18004f09e  cmp     qword ptr [rdi+18h], 7
0x18004f0a3  jbe     short loc_18004F0A8
0x18004f0a5  mov     rdi, [rdi]
0x18004f0a8  mov     rdx, rdi; unsigned __int16 *
0x18004f0ab  lea     rcx, [rbp+3Fh+bstrString]; this
0x18004f0af  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18004f0b4  mov     rcx, [rbp+3Fh+var_98]
0x18004f0b8  mov     rax, [rcx]
0x18004f0bb  mov     rbx, [rbp+3Fh+var_88]
0x18004f0bf  lea     rdx, [rbx+98h]
0x18004f0c6  lea     r8, [rbp+3Fh+var_A0]
0x18004f0ca  mov     [rsp+100h+var_D8], r8
0x18004f0cf  mov     dword ptr [rsp+100h+ppv], 0
0x18004f0d7  mov     r9d, r13d
0x18004f0da  mov     rdi, [rbp+3Fh+bstrString]
0x18004f0de  mov     r8, rdi
0x18004f0e1  mov     rax, [rax+20h]
0x18004f0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f0ea  mov     ecx, [rbp+3Fh+var_A0]
0x18004f0ed  test    eax, eax
0x18004f0ef  js      loc_18004F1ED
0x18004f0f5  test    ecx, ecx
0x18004f0f7  jz      loc_18004F1ED
0x18004f0fd  xor     ebx, ebx
0x18004f0ff  mov     qword ptr [rbp+3Fh+var_50], rbx
0x18004f103  xorps   xmm0, xmm0
0x18004f106  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x18004f10a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004f112  movdqu  [rbp+3Fh+var_60], xmm1
0x18004f117  xor     eax, eax
0x18004f119  mov     word ptr [rbp+3Fh+var_70], ax
0x18004f11d  cmp     qword ptr [r12+18h], 7
0x18004f123  jbe     short loc_18004F129
0x18004f125  mov     r12, [r12]
0x18004f129  lea     r8, [rbp+3Fh+var_70]
0x18004f12d  mov     rdx, r12
0x18004f130  mov     rcx, r14
0x18004f133  call    ?GetDecodedMessage@CWwanMessageXmlHelper@@SAJAEBUWwanSmsStoreMessage@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CWwanMessageXmlHelper::GetDecodedMessage(WwanSmsStoreMessage const &,ushort const *,std::wstring &)
0x18004f138  test    eax, eax
0x18004f13a  js      loc_18004F1D8
0x18004f140  lea     rdx, [rbp+3Fh+var_70]
0x18004f144  cmp     qword ptr [rbp+3Fh+var_60+8], 7
0x18004f149  cmova   rdx, [rbp+3Fh+var_70]; unsigned __int16 *
0x18004f14e  lea     rcx, [rbp+3Fh+var_50]; this
0x18004f152  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18004f157  mov     rbx, qword ptr [rbp+3Fh+var_50]
0x18004f15b  test    eax, eax
0x18004f15d  js      short loc_18004F1D8
0x18004f15f  lea     rsi, [r14+5]
0x18004f163  mov     rax, qword ptr [rbp+3Fh+var_80]
0x18004f167  movaps  xmm0, xmmword ptr [rax]
0x18004f16a  movdqa  [rbp+3Fh+var_80], xmm0
0x18004f16f  cmp     [rbp+3Fh+arg_28], 0
0x18004f173  setnz   cl
0x18004f176  mov     eax, [r14]
0x18004f179  mov     [rsp+100h+var_B0], eax
0x18004f17d  mov     [rsp+100h+var_B8], rsi
0x18004f182  mov     [rsp+100h+var_C0], cl
0x18004f186  mov     [rsp+100h+var_C8], r13d
0x18004f18b  mov     [rsp+100h+var_D8], rbx
0x18004f190  lea     rax, [rbp+3Fh+var_80]
0x18004f194  mov     [rsp+100h+ppv], rax
0x18004f199  mov     r9, rdi
0x18004f19c  mov     r12d, [rbp+3Fh+var_9C]
0x18004f1a0  mov     r8d, r12d
0x18004f1a3  mov     rdx, [rbp+3Fh+var_98]
0x18004f1a7  mov     r13, [rbp+3Fh+var_88]
0x18004f1ab  mov     rcx, r13
0x18004f1ae  call    ?ProcessOperatorNotification@CWwanSmsDevice@@AEAAJPEAUIProvisioningNotificationProcessor@@KQEAGU_SYSTEMTIME@@1W4NotificationMessageType@@W4PROVISIONING_NOTIFICATION_FLAG@@_NPEBEI@Z; CWwanSmsDevice::ProcessOperatorNotification(IProvisioningNotificationProcessor *,ulong,ushort * const,_SYSTEMTIME,ushort * const,NotificationMessageType,PROVISIONING_NOTIFICATION_FLAG,bool,uchar const *,uint)
0x18004f1b3  test    eax, eax
0x18004f1b5  js      short loc_18004F1BC
0x18004f1b7  cmp     eax, 1
0x18004f1ba  jnz     short loc_18004F1D8
0x18004f1bc  mov     eax, [r14]
0x18004f1bf  mov     dword ptr [rsp+100h+var_D8], eax
0x18004f1c3  mov     [rsp+100h+ppv], rsi
0x18004f1c8  mov     r8d, [rbp+3Fh+arg_28]
0x18004f1cc  mov     edx, r12d
0x18004f1cf  mov     rcx, r13
0x18004f1d2  call    ?ProcessUserText@CWwanSmsDevice@@AEAAJKHW4_WWAN_CELLULAR_CLASS@@PEBEI@Z; CWwanSmsDevice::ProcessUserText(ulong,int,_WWAN_CELLULAR_CLASS,uchar const *,uint)
0x18004f1d7  nop
0x18004f1d8  lea     rcx, [rbp+3Fh+var_70]; void *
0x18004f1dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f1e1  nop
0x18004f1e2  mov     rcx, rbx; bstrString
0x18004f1e5  call    cs:__imp_SysFreeString
0x18004f1eb  jmp     short loc_18004F22C
0x18004f1ed  mov     dword ptr [rsp+100h+ppv], ecx
0x18004f1f1  mov     r9d, eax
0x18004f1f4  lea     r8, aProvisioningEn_0; "Provisioning Engine Can Process Notific"...
0x18004f1fb  mov     edx, 7A5h; unsigned int
0x18004f200  lea     rcx, aCwwansmsdevice_3; "CWwanSmsDevice::PublishSmsWNF"
0x18004f207  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004f20c  lea     rcx, [r14+5]
0x18004f210  mov     eax, [r14]
0x18004f213  mov     dword ptr [rsp+100h+var_D8], eax
0x18004f217  mov     [rsp+100h+ppv], rcx
0x18004f21c  mov     r8d, [rbp+3Fh+arg_28]
0x18004f220  mov     edx, [rbp+3Fh+var_9C]
0x18004f223  mov     rcx, rbx
0x18004f226  call    ?ProcessUserText@CWwanSmsDevice@@AEAAJKHW4_WWAN_CELLULAR_CLASS@@PEBEI@Z; CWwanSmsDevice::ProcessUserText(ulong,int,_WWAN_CELLULAR_CLASS,uchar const *,uint)
0x18004f22b  nop
0x18004f22c  mov     rcx, rdi; bstrString
0x18004f22f  call    cs:__imp_SysFreeString
0x18004f235  nop
0x18004f236  mov     rcx, [rbp+3Fh+var_98]
0x18004f23a  test    rcx, rcx
0x18004f23d  jz      short loc_18004F24C
0x18004f23f  mov     rax, [rcx]
0x18004f242  mov     rax, [rax+10h]
0x18004f246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f24b  nop
0x18004f24c  mov     rcx, [rbp+3Fh+var_40]
0x18004f250  xor     rcx, rsp; StackCookie
0x18004f253  call    __security_check_cookie
0x18004f258  add     rsp, 0D0h
0x18004f25f  pop     r14
0x18004f261  pop     r13
0x18004f263  pop     r12
0x18004f265  pop     rdi
0x18004f266  pop     rsi
0x18004f267  pop     rbx
0x18004f268  pop     rbp
0x18004f269  retn
0x18004f26a  call    ?_Xran@?$_String_val@U?$_Simple_types@D@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<char>>::_Xran(void)
```
