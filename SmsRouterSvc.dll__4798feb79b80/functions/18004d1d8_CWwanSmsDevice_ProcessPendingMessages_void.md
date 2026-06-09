# CWwanSmsDevice::ProcessPendingMessages(void)

- ea: `0x18004d1d8`
- end: `0x18004d920`
- name: `?ProcessPendingMessages@CWwanSmsDevice@@AEAAXXZ`
- size: `1864`
- prototype: `void __fastcall(CWwanSmsDevice *__hidden this)`
- caller_count: `3`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004aee0`
- `0x18004d928`
- `0x18004e378`

## callees

- `0x180003a60`
- `0x180003f50`
- `0x1800069f0`
- `0x180006c84`
- `0x18000eaa4`
- `0x18004a0e4`
- `0x18004b2e4`
- `0x18004d1d8`
- `0x180051420`
- `0x180051628`
- `0x180051b68`
- `0x180052b44`
- `0x180053ba4`
- `0x180053d10`
- `0x1800547d8`
- `0x18005e130`
- `0x18005e5ac`
- `0x180060030`
- `0x180060ea4`
- `0x180061a74`
- `0x180062204`
- `0x180062854`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18004d3cb`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18004d3cb`

## string_xrefs

- `0x18004d457`: `GetNextReadyMessage messagecacheid=%d, segments=%d, type=%d.`
- `0x18004d668`: `Failed to generate XML for sms pdus segments (segmentcount=%d).`
- `0x18004d47a`: `GetNextReadyMessage failed.`
- `0x18004d83d`: `WwanSmsDevice is in invalid state to delete the message from temporary store.`
- `0x18004d81b`: `Deleted messagecacheid=%d.`
- `0x18004d756`: `CSmsConcatenateStore::DeleteDeliveredMessage`
- `0x18004d3ae`: `CSmsConcatenateStore::GetNextReadyMessage`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall CWwanSmsDevice::ProcessPendingMessages(CWwanSmsDevice *this)
{
  CWwanSmsDevice *v1; // r13
  __int64 v2; // rbx
  char *v3; // r15
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // rdi
  __int64 v7; // r8
  struct WwanSmsStoreMessage *v8; // rdi
  struct SmsUiccInfo *v9; // r12
  unsigned int v10; // esi
  CSmsConcatenateStore *v11; // rsi
  int v12; // r14d
  unsigned int v13; // ecx
  __int64 v14; // r13
  __int64 v15; // rax
  __int64 v16; // r12
  volatile signed __int32 *v17; // rdi
  const char *DisplayString; // rax
  _QWORD *v19; // rax
  int v20; // eax
  unsigned __int16 *v21; // r14
  unsigned __int16 *v22; // r13
  unsigned __int16 *v23; // rax
  unsigned __int16 *v24; // r9
  int MessageTypeCdma; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int VoicemailMessageXml; // eax
  unsigned int v32; // r9d
  signed int v33; // ecx
  signed int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rsi
  __int64 v41; // rax
  volatile signed __int32 *v42; // rsi
  unsigned int v43; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v44; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 *v45; // [rsp+48h] [rbp-B8h] BYREF
  struct IXMLDOMDocument *v46; // [rsp+50h] [rbp-B0h] BYREF
  CWwanSmsDevice *v47; // [rsp+58h] [rbp-A8h]
  struct WwanSmsStoreMessage *v48; // [rsp+60h] [rbp-A0h] BYREF
  struct SmsUiccInfo *v49; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v50[2]; // [rsp+70h] [rbp-90h] BYREF
  void **v51; // [rsp+80h] [rbp-80h]
  char *v52; // [rsp+88h] [rbp-78h]
  __int64 v53; // [rsp+90h] [rbp-70h]
  _QWORD v54[2]; // [rsp+98h] [rbp-68h] BYREF
  void **v55; // [rsp+A8h] [rbp-58h]
  char *v56; // [rsp+B0h] [rbp-50h]
  __int128 v57; // [rsp+C0h] [rbp-40h]
  __int128 v58; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v59; // [rsp+E0h] [rbp-20h]
  char v60[16]; // [rsp+E8h] [rbp-18h] BYREF
  char v61[16]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v62; // [rsp+108h] [rbp+8h] BYREF
  __m128i v63; // [rsp+118h] [rbp+18h]
  unsigned __int16 *v64[2]; // [rsp+128h] [rbp+28h] BYREF
  __m128i v65; // [rsp+138h] [rbp+38h]
  unsigned __int16 *v66[2]; // [rsp+148h] [rbp+48h] BYREF
  __m128i si128; // [rsp+158h] [rbp+58h]

  v1 = this;
  v47 = this;
  *(_OWORD *)v66 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v66[0]) = 0;
  *(_OWORD *)v64 = 0;
  v65 = si128;
  LOWORD(v64[0]) = 0;
  v62 = 0;
  v63 = si128;
  LOWORD(v62) = 0;
  v2 = 0;
  v53 = 0;
  v46 = 0;
  v51 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v3 = (char *)this + 32;
  v52 = (char *)this + 32;
  (**((void (__fastcall ***)(char *))this + 4))((char *)this + 32);
  std::wstring::operator=((__int64)v66, (_QWORD *)v1 + 68, v4);
  v6 = *((_QWORD *)v1 + 86);
  if ( v6 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 8LL))(*((_QWORD *)v1 + 86));
    v2 = v6;
    v53 = v6;
  }
  std::wstring::operator=((__int64)v64, (_QWORD *)v1 + 80, v5);
  std::wstring::operator=((__int64)&v62, (_QWORD *)v1 + 10, v7);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
  if ( v6 )
  {
    v8 = 0;
    v48 = 0;
    v9 = 0;
    v49 = 0;
    v44 = 0;
    v10 = 0;
    v43 = 0;
    while ( 1 )
    {
      v55 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
      v56 = v3;
      (**(void (__fastcall ***)(char *))v3)(v3);
      if ( *((_QWORD *)v1 + 103) == -1 )
      {
        v12 = -2147023728;
      }
      else
      {
        v11 = (CWwanSmsDevice *)((char *)v1 + 696);
        if ( *((_QWORD *)v1 + 90) )
        {
          v13 = *((_DWORD *)v1 + 198);
          *((_DWORD *)v1 + 198) = v13 + 1;
          v44 = v13;
          v14 = **((_QWORD **)v1 + 89);
          v15 = *(_QWORD *)(v14 + 112);
          if ( v15 )
            _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
          v16 = *(_QWORD *)(v14 + 104);
          v54[0] = v16;
          v17 = *(volatile signed __int32 **)(v14 + 112);
          v54[1] = v17;
          v12 = CSmsConcatenateStore::ReadFullMessage(v11, (struct SmsStoreMessage *)v16, &v43, &v48, &v49);
          if ( v12 >= 0 )
          {
            DisplayString = GetDisplayString((unsigned __int8 *)(v14 + 36), *(_DWORD *)(v14 + 32));
            LogSmsRouterInfo(
              "CSmsConcatenateStore::GetNextReadyMessage",
              0x2DCu,
              "Delivering store messageid=%d, segments=%d, uid=%s",
              v44,
              v43,
              DisplayString);
            std::_Tree<std::_Tmap_traits<SmsUid,std::shared_ptr<SmsStoreMessage>,CSmsUidCompare,std::allocator<std::pair<SmsUid const,std::shared_ptr<SmsStoreMessage>>>,0>>::_Erase_unchecked(
              (__int64)v11 + 16,
              (__int64 *)v14);
            _time64((__time64_t *)(v16 + 8));
            v19 = (_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned long,std::shared_ptr<SmsStoreMessage>,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,std::shared_ptr<SmsStoreMessage>>>,0>>::_Try_emplace<unsigned long const &,>(
                              (__int64)v11 + 32,
                              (__int64)v60,
                              &v44);
            std::shared_ptr<SmsStoreMessage>::operator=(*v19 + 24LL, v54);
          }
          if ( v17 )
          {
            if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
              if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
            }
          }
          if ( v12 < 0 )
          {
            if ( v12 != -2147020590 )
              LogSmsRouterError("CWwanSmsDevice::ProcessPendingMessages", 0x6BBu, v12, "GetNextReadyMessage failed.");
            v8 = v48;
            v10 = v43;
          }
          else
          {
            v8 = v48;
            v10 = v43;
            v20 = v43 ? *((unsigned __int8 *)v48 + 4) : 0;
            LogSmsRouterInfo(
              "CWwanSmsDevice::ProcessPendingMessages",
              0x6B3u,
              "GetNextReadyMessage messagecacheid=%d, segments=%d, type=%d.",
              v44,
              v43,
              v20);
          }
          v9 = v49;
          v1 = v47;
        }
        else
        {
          v12 = -2147020590;
          v10 = v43;
        }
      }
      v55 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
      if ( v12 >= 0 )
        break;
LABEL_81:
      if ( v8 )
      {
        operator delete(v8);
        v8 = 0;
        v48 = 0;
      }
      if ( v9 )
      {
        operator delete(v9);
        v9 = 0;
        v49 = 0;
      }
      if ( v12 < 0 )
        goto LABEL_86;
    }
    v21 = 0;
    if ( v10 )
      v21 = (unsigned __int16 *)v9;
    v22 = (unsigned __int16 *)v64;
    if ( v65.m128i_i64[1] > 7uLL )
      v22 = v64[0];
    v23 = (unsigned __int16 *)v66;
    if ( si128.m128i_i64[1] > 7uLL )
      v23 = v66[0];
    v45 = v23;
    v24 = (unsigned __int16 *)&v62;
    if ( v63.m128i_i64[1] > 7uLL )
      v24 = (unsigned __int16 *)v62;
    v50[0] = v24;
    v58 = 0;
    v59 = 0;
    if ( *((_BYTE *)v8 + 4) )
    {
      if ( *((_BYTE *)v8 + 4) != 1 )
      {
        if ( *((_BYTE *)v8 + 4) != 2 )
          goto LABEL_50;
        goto LABEL_54;
      }
      MessageTypeCdma = CSmsEncodingHelper::GetMessageTypeCdma((char *)v8 + 5, *(unsigned int *)v8);
    }
    else
    {
      MessageTypeCdma = CSmsEncodingHelper::GetMessageTypeGsm((char *)v8 + 5, *(unsigned int *)v8);
    }
    v26 = MessageTypeCdma - 1;
    if ( v26 )
    {
      v27 = v26 - 1;
      if ( v27 )
      {
        v28 = v27 - 1;
        if ( !v28 )
        {
          VoicemailMessageXml = GetVoicemailMessageXml(v8, v10, v50[0], v45, v22, v21, &v46);
          goto LABEL_47;
        }
        v29 = v28 - 1;
        if ( v29 )
        {
          v30 = v29 - 1;
          if ( !v30 )
          {
            VoicemailMessageXml = GetStatusReportMessageXml(v8, v10, v50[0], v45, v22, v21, &v46);
            goto LABEL_47;
          }
          if ( v30 == 1 )
          {
            VoicemailMessageXml = GetBroadcastMessageXml(v8, v10, v50[0], v45, v22, v21, &v46);
LABEL_47:
            v12 = VoicemailMessageXml;
LABEL_51:
            std::vector<std::vector<unsigned char>>::~vector<std::vector<unsigned char>>((__int64)&v58);
            if ( v12 < 0 )
            {
              LogSmsRouterError(
                "CWwanSmsDevice::ProcessPendingMessages",
                0x6D5u,
                v12,
                "Failed to generate XML for sms pdus segments (segmentcount=%d).",
                v10);
              v1 = v47;
            }
            else
            {
              v1 = v47;
              (*(void (__fastcall **)(__int64, struct IXMLDOMDocument *, _QWORD))(*(_QWORD *)v2 + 24LL))(
                v2,
                v46,
                *((unsigned int *)v47 + 228));
            }
            v51 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
            v52 = v3;
            (**(void (__fastcall ***)(char *))v3)(v3);
            if ( *((_QWORD *)v1 + 103) == -1 )
            {
              v12 = -2147019873;
              LogSmsRouterError(
                "CWwanSmsDevice::ProcessPendingMessages",
                0x6E3u,
                -2147019873,
                "WwanSmsDevice is in invalid state to delete the message from temporary store.");
            }
            else
            {
              v32 = v44;
              LODWORD(v45) = v44;
              v33 = 16807 * ((v44 ^ 0xDEADBEEF) & 0x7FFFFFFF)
                  - 0x7FFFFFFF * (((v44 ^ 0xDEADBEEF) & 0x7FFFFFFF) / 0x1F31D);
              v34 = v33 + 0x7FFFFFFF;
              if ( v33 >= 0 )
                v34 = 16807 * ((v44 ^ 0xDEADBEEF) & 0x7FFFFFFF)
                    - 0x7FFFFFFF * (((v44 ^ 0xDEADBEEF) & 0x7FFFFFFF) / 0x1F31D);
              v35 = 2 * (*((_QWORD *)v1 + 97) & v34);
              v36 = *((_QWORD *)v1 + 94);
              v37 = *(_QWORD *)(v36 + 8 * v35 + 8);
              if ( v37 == *((_QWORD *)v1 + 92) )
              {
LABEL_60:
                v37 = 0;
              }
              else
              {
                v38 = *(_QWORD *)(v36 + 8 * v35);
                while ( v44 < *(_DWORD *)(v37 + 16) )
                {
                  if ( v37 == v38 )
                    goto LABEL_60;
                  v37 = *(_QWORD *)(v37 + 8);
                }
                if ( *(_DWORD *)(v37 + 16) < v44 )
                  v37 = 0;
              }
              if ( v37 && v37 != *((_QWORD *)v1 + 92) )
              {
                LogSmsRouterInfo(
                  "CSmsConcatenateStore::DeleteDeliveredMessage",
                  0x2BAu,
                  "Deleting store dwMessageId=%d.",
                  v44);
                v39 = std::_Hash<stdext::_Hmap_traits<unsigned long,std::shared_ptr<SmsStoreMessage>,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,std::shared_ptr<SmsStoreMessage>>>,0>>::_Try_emplace<unsigned long const &,>(
                        (__int64)v1 + 728,
                        (__int64)v61,
                        (unsigned int *)&v45);
                v40 = *(_QWORD *)v39;
                v41 = *(_QWORD *)(*(_QWORD *)v39 + 32LL);
                if ( v41 )
                  _InterlockedIncrement((volatile signed __int32 *)(v41 + 8));
                *(_QWORD *)&v57 = *(_QWORD *)(v40 + 24);
                v42 = *(volatile signed __int32 **)(v40 + 32);
                *((_QWORD *)&v57 + 1) = v42;
                *(_OWORD *)v50 = 0;
                if ( v42 )
                  _InterlockedIncrement(v42 + 2);
                *(_OWORD *)v50 = v57;
                CSmsConcatenateStore::DeleteMessage((CWwanSmsDevice *)((char *)v1 + 696), v50);
                std::_Hash<stdext::_Hmap_traits<unsigned long,std::shared_ptr<SmsStoreMessage>,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,std::shared_ptr<SmsStoreMessage>>>,0>>::erase(
                  (char *)v1 + 728,
                  &v45);
                if ( v42 )
                {
                  if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
                    if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
                  }
                }
                v10 = v43;
                v32 = v44;
              }
              LogSmsRouterInfo("CWwanSmsDevice::ProcessPendingMessages", 0x6DDu, "Deleted messagecacheid=%d.", v32);
            }
            v51 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
            (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
            CWwanSmsDevice::MaintainSmsListAtHalfFull(v1, 0);
            goto LABEL_81;
          }
LABEL_50:
          v12 = -2147023266;
          goto LABEL_51;
        }
      }
    }
    v23 = v45;
LABEL_54:
    VoicemailMessageXml = GetDeliverMessageXml(v8, v10, v50[0], v23, v22, v21, &v46);
    goto LABEL_47;
  }
LABEL_86:
  if ( v46 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v46->lpVtbl->Release)(v46);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  std::wstring::~wstring((char **)&v62);
  std::wstring::~wstring((char **)v64);
  std::wstring::~wstring((char **)v66);
}

```

## disassembly

```asm
0x18004d1d8  push    rbp
0x18004d1da  push    rbx
0x18004d1db  push    rsi
0x18004d1dc  push    rdi
0x18004d1dd  push    r12
0x18004d1df  push    r13
0x18004d1e1  push    r14
0x18004d1e3  push    r15
0x18004d1e5  lea     rbp, [rsp-78h]
0x18004d1ea  sub     rsp, 178h
0x18004d1f1  mov     rax, cs:__security_cookie
0x18004d1f8  xor     rax, rsp
0x18004d1fb  mov     [rbp+0B0h+var_48], rax
0x18004d1ff  mov     r13, rcx
0x18004d202  mov     [rsp+1B0h+var_158], rcx
0x18004d207  xorps   xmm0, xmm0
0x18004d20a  movups  xmmword ptr [rbp+0B0h+var_68], xmm0
0x18004d20e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004d216  movdqu  [rbp+0B0h+var_58], xmm1
0x18004d21b  xor     eax, eax
0x18004d21d  mov     word ptr [rbp+0B0h+var_68], ax
0x18004d221  movups  xmmword ptr [rbp+0B0h+var_88], xmm0
0x18004d225  movdqu  [rbp+0B0h+var_78], xmm1
0x18004d22a  mov     word ptr [rbp+0B0h+var_88], ax
0x18004d22e  movups  [rbp+0B0h+var_A8], xmm0
0x18004d232  movdqu  [rbp+0B0h+var_98], xmm1
0x18004d237  mov     word ptr [rbp+0B0h+var_A8], ax
0x18004d23b  xor     ebx, ebx
0x18004d23d  mov     [rbp+0B0h+var_120], rbx
0x18004d241  mov     [rsp+1B0h+var_160], rbx
0x18004d246  lea     r14, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004d24d  mov     [rbp+0B0h+var_130], r14
0x18004d251  lea     r15, [rcx+20h]
0x18004d255  mov     [rbp+0B0h+var_128], r15
0x18004d259  mov     rax, [r15]
0x18004d25c  mov     rcx, r15
0x18004d25f  mov     rax, [rax]
0x18004d262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d267  nop
0x18004d268  lea     rdx, [r13+220h]
0x18004d26f  lea     rcx, [rbp+0B0h+var_68]
0x18004d273  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004d278  mov     rdi, [r13+2B0h]
0x18004d27f  test    rdi, rdi
0x18004d282  jz      short loc_18004D29A
0x18004d284  mov     rax, [rdi]
0x18004d287  mov     rcx, rdi
0x18004d28a  mov     rax, [rax+8]
0x18004d28e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d293  mov     rbx, rdi
0x18004d296  mov     [rbp+0B0h+var_120], rbx
0x18004d29a  lea     rdx, [r13+280h]
0x18004d2a1  lea     rcx, [rbp+0B0h+var_88]
0x18004d2a5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004d2aa  lea     rdx, [r13+50h]
0x18004d2ae  lea     rcx, [rbp+0B0h+var_A8]
0x18004d2b2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004d2b7  nop
0x18004d2b8  mov     rax, [r15]
0x18004d2bb  mov     rcx, r15
0x18004d2be  mov     rax, [rax+8]
0x18004d2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2c7  nop
0x18004d2c8  test    rdi, rdi
0x18004d2cb  jz      loc_18004D8B7
0x18004d2d1  xor     edi, edi
0x18004d2d3  mov     [rsp+1B0h+var_150], rdi
0x18004d2d8  xor     r12d, r12d
0x18004d2db  mov     [rsp+1B0h+var_148], r12
0x18004d2e0  mov     [rsp+1B0h+var_16C], edi
0x18004d2e4  xor     esi, esi
0x18004d2e6  mov     [rsp+1B0h+var_170], esi
0x18004d2ea  mov     [rbp+0B0h+var_108], r14
0x18004d2ee  mov     [rbp+0B0h+var_100], r15
0x18004d2f2  mov     rax, [r15]
0x18004d2f5  mov     rcx, r15
0x18004d2f8  mov     rax, [rax]
0x18004d2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d300  nop
0x18004d301  cmp     qword ptr [r13+338h], 0FFFFFFFFFFFFFFFFh
0x18004d309  jz      loc_18004D4AA
0x18004d30f  lea     rsi, [r13+2B8h]
0x18004d316  cmp     qword ptr [rsi+18h], 0
0x18004d31b  jnz     short loc_18004D32C
0x18004d31d  mov     r14d, 800710D2h
0x18004d323  mov     esi, [rsp+1B0h+var_170]
0x18004d327  jmp     loc_18004D4B0
0x18004d32c  mov     ecx, [rsi+60h]
0x18004d32f  lea     eax, [rcx+1]
0x18004d332  mov     [rsi+60h], eax
0x18004d335  mov     [rsp+1B0h+var_16C], ecx
0x18004d339  mov     rax, [rsi+10h]
0x18004d33d  mov     r13, [rax]
0x18004d340  mov     rax, [r13+70h]
0x18004d344  test    rax, rax
0x18004d347  jz      short loc_18004D34D
0x18004d349  lock inc dword ptr [rax+8]
0x18004d34d  mov     r12, [r13+68h]
0x18004d351  mov     [rbp+0B0h+var_118], r12
0x18004d355  mov     rdi, [r13+70h]
0x18004d359  mov     [rbp+0B0h+var_110], rdi
0x18004d35d  lea     rax, [rsp+1B0h+var_148]
0x18004d362  mov     [rsp+1B0h+var_190], rax; struct SmsUiccInfo **
0x18004d367  lea     r9, [rsp+1B0h+var_150]; struct WwanSmsStoreMessage **
0x18004d36c  lea     r8, [rsp+1B0h+var_170]; unsigned int *
0x18004d371  mov     rdx, r12; struct SmsStoreMessage *
0x18004d374  mov     rcx, rsi; this
0x18004d377  call    ?ReadFullMessage@CSmsConcatenateStore@@AEAAJPEAUSmsStoreMessage@@PEAKPEAPEAUWwanSmsStoreMessage@@PEAPEAUSmsUiccInfo@@@Z; CSmsConcatenateStore::ReadFullMessage(SmsStoreMessage *,ulong *,WwanSmsStoreMessage * *,SmsUiccInfo * *)
0x18004d37c  mov     r14d, eax
0x18004d37f  test    eax, eax
0x18004d381  js      short loc_18004D3F4
0x18004d383  lea     rcx, [r13+24h]; unsigned __int8 *
0x18004d387  mov     edx, [r13+20h]; unsigned int
0x18004d38b  call    ?GetDisplayString@@YAPEBDPEAEK@Z; GetDisplayString(uchar *,ulong)
0x18004d390  mov     [rsp+1B0h+var_188], rax
0x18004d395  mov     eax, [rsp+1B0h+var_170]
0x18004d399  mov     dword ptr [rsp+1B0h+var_190], eax
0x18004d39d  mov     r9d, [rsp+1B0h+var_16C]
0x18004d3a2  lea     r8, aDeliveringStor; "Delivering store messageid=%d, segments"...
0x18004d3a9  mov     edx, 2DCh; unsigned int
0x18004d3ae  lea     rcx, aCsmsconcatenat_1; "CSmsConcatenateStore::GetNextReadyMessa"...
0x18004d3b5  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004d3ba  mov     rdx, r13
0x18004d3bd  lea     rcx, [rsi+10h]
0x18004d3c1  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@USmsUid@@V?$shared_ptr@USmsStoreMessage@@@std@@VCSmsUidCompare@@V?$allocator@U?$pair@$$CBUSmsUid@@V?$shared_ptr@USmsStoreMessage@@@std@@@std@@@3@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBUSmsUid@@V?$shared_ptr@USmsStoreMessage@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUSmsUid@@V?$shared_ptr@USmsStoreMessage@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<SmsUid,std::shared_ptr<SmsStoreMessage>,CSmsUidCompare,std::allocator<std::pair<SmsUid const,std::shared_ptr<SmsStoreMessage>>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<SmsUid const,std::shared_ptr<SmsStoreMessage>>>>,std::_Iterator_base0>)
0x18004d3c6  lea     rcx, [r12+8]; Time
0x18004d3cb  call    cs:__imp__time64
0x18004d3d1  lea     rcx, [rsi+20h]
0x18004d3d5  lea     r8, [rsp+1B0h+var_16C]
0x18004d3da  lea     rdx, [rbp+0B0h+var_C8]
0x18004d3de  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Hmap_traits@KV?$shared_ptr@USmsStoreMessage@@@std@@V?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKV?$shared_ptr@USmsStoreMessage@@@std@@@std@@@2@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKV?$shared_ptr@USmsStoreMessage@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<stdext::_Hmap_traits<ulong,std::shared_ptr<SmsStoreMessage>,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,std::shared_ptr<SmsStoreMessage>>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x18004d3e3  mov     rcx, [rax]
0x18004d3e6  add     rcx, 18h
0x18004d3ea  lea     rdx, [rbp+0B0h+var_118]
0x18004d3ee  call    ??4?$shared_ptr@USmsStoreMessage@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<SmsStoreMessage>::operator=(std::shared_ptr<SmsStoreMessage> const &)
0x18004d3f3  nop
0x18004d3f4  test    rdi, rdi
0x18004d3f7  jz      short loc_18004D430
0x18004d3f9  or      eax, 0FFFFFFFFh
0x18004d3fc  lock xadd [rdi+8], eax
0x18004d401  cmp     eax, 1
0x18004d404  jnz     short loc_18004D430
0x18004d406  mov     rax, [rdi]
0x18004d409  mov     rcx, rdi
0x18004d40c  mov     rax, [rax]
0x18004d40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d414  or      eax, 0FFFFFFFFh
0x18004d417  lock xadd [rdi+0Ch], eax
0x18004d41c  cmp     eax, 1
0x18004d41f  jnz     short loc_18004D430
0x18004d421  mov     rax, [rdi]
0x18004d424  mov     rcx, rdi
0x18004d427  mov     rax, [rax+8]
0x18004d42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d430  test    r14d, r14d
0x18004d433  js      short loc_18004D471
0x18004d435  mov     rdi, [rsp+1B0h+var_150]
0x18004d43a  mov     esi, [rsp+1B0h+var_170]
0x18004d43e  test    esi, esi
0x18004d440  jz      short loc_18004D448
0x18004d442  movzx   eax, byte ptr [rdi+4]
0x18004d446  jmp     short loc_18004D44A
0x18004d448  xor     eax, eax
0x18004d44a  mov     dword ptr [rsp+1B0h+var_188], eax
0x18004d44e  mov     dword ptr [rsp+1B0h+var_190], esi
0x18004d452  mov     r9d, [rsp+1B0h+var_16C]
0x18004d457  lea     r8, aGetnextreadyme_0; "GetNextReadyMessage messagecacheid=%d, "...
0x18004d45e  mov     edx, 6B3h; unsigned int
0x18004d463  lea     rcx, aCwwansmsdevice; "CWwanSmsDevice::ProcessPendingMessages"
0x18004d46a  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004d46f  jmp     short loc_18004D49E
0x18004d471  cmp     r14d, 800710D2h
0x18004d478  jz      short loc_18004D495
0x18004d47a  lea     r9, aGetnextreadyme; "GetNextReadyMessage failed."
0x18004d481  mov     r8d, r14d; int
0x18004d484  mov     edx, 6BBh; unsigned int
0x18004d489  lea     rcx, aCwwansmsdevice; "CWwanSmsDevice::ProcessPendingMessages"
0x18004d490  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18004d495  mov     rdi, [rsp+1B0h+var_150]
0x18004d49a  mov     esi, [rsp+1B0h+var_170]
0x18004d49e  mov     r12, [rsp+1B0h+var_148]
0x18004d4a3  mov     r13, [rsp+1B0h+var_158]
0x18004d4a8  jmp     short loc_18004D4B0
0x18004d4aa  mov     r14d, 80070490h
0x18004d4b0  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004d4b7  mov     [rbp+0B0h+var_108], rax
0x18004d4bb  mov     rax, [r15]
0x18004d4be  mov     rcx, r15
0x18004d4c1  mov     rax, [rax+8]
0x18004d4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4ca  nop
0x18004d4cb  test    r14d, r14d
0x18004d4ce  js      loc_18004D87E
0x18004d4d4  xor     r14d, r14d
0x18004d4d7  test    esi, esi
0x18004d4d9  cmovnz  r14, r12
0x18004d4dd  lea     r13, [rbp+0B0h+var_88]
0x18004d4e1  cmp     qword ptr [rbp+0B0h+var_78+8], 7
0x18004d4e6  cmova   r13, [rbp+0B0h+var_88]
0x18004d4eb  lea     rax, [rbp+0B0h+var_68]
0x18004d4ef  cmp     qword ptr [rbp+0B0h+var_58+8], 7
0x18004d4f4  cmova   rax, [rbp+0B0h+var_68]
0x18004d4f9  mov     [rsp+1B0h+var_168], rax
0x18004d4fe  lea     r9, [rbp+0B0h+var_A8]
0x18004d502  cmp     qword ptr [rbp+0B0h+var_98+8], 7
0x18004d507  cmova   r9, qword ptr [rbp+0B0h+var_A8]
0x18004d50c  mov     [rsp+1B0h+var_140], r9
0x18004d511  xorps   xmm0, xmm0
0x18004d514  movdqu  [rbp+0B0h+var_E0], xmm0
0x18004d519  mov     [rbp+0B0h+var_D0], 0
0x18004d521  cmp     byte ptr [rdi+4], 0
0x18004d525  jnz     short loc_18004D534
0x18004d527  lea     rcx, [rdi+5]
0x18004d52b  mov     edx, [rdi]
0x18004d52d  call    ?GetMessageTypeGsm@CSmsEncodingHelper@@SA?AW4SmsMessageType@Common@Sms@Windows@@PEAEK@Z; CSmsEncodingHelper::GetMessageTypeGsm(uchar *,ulong)
0x18004d532  jmp     short loc_18004D549
0x18004d534  cmp     byte ptr [rdi+4], 1
0x18004d538  jnz     loc_18004D5F8
0x18004d53e  lea     rcx, [rdi+5]
0x18004d542  mov     edx, [rdi]
0x18004d544  call    ?GetMessageTypeCdma@CSmsEncodingHelper@@SA?AW4SmsMessageType@Common@Sms@Windows@@PEBEK@Z; CSmsEncodingHelper::GetMessageTypeCdma(uchar const *,ulong)
0x18004d549  sub     eax, 1
0x18004d54c  jz      loc_18004D634
0x18004d552  sub     eax, 1
0x18004d555  jz      loc_18004D634
0x18004d55b  sub     eax, 1
0x18004d55e  jz      short loc_18004D5CE
0x18004d560  sub     eax, 1
0x18004d563  jz      loc_18004D634
0x18004d569  sub     eax, 1
0x18004d56c  jz      short loc_18004D5A1
0x18004d56e  cmp     eax, 1
0x18004d571  jnz     loc_18004D5FE
0x18004d577  lea     rax, [rsp+1B0h+var_160]
0x18004d57c  mov     [rsp+1B0h+var_180], rax; struct IXMLDOMDocument **
0x18004d581  mov     [rsp+1B0h+var_188], r14; unsigned __int16 *
0x18004d586  mov     [rsp+1B0h+var_190], r13; unsigned __int16 *
0x18004d58b  mov     r9, [rsp+1B0h+var_168]; unsigned __int16 *
0x18004d590  mov     r8, [rsp+1B0h+var_140]; unsigned __int16 *
0x18004d595  mov     edx, esi; unsigned int
0x18004d597  mov     rcx, rdi; struct WwanSmsStoreMessage *
0x18004d59a  call    ?GetBroadcastMessageXml@@YAJPEAUWwanSmsStoreMessage@@KPEBG111PEAPEAUIXMLDOMDocument@@@Z; GetBroadcastMessageXml(WwanSmsStoreMessage *,ulong,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMDocument * *)
0x18004d59f  jmp     short loc_18004D5C9
0x18004d5a1  lea     rax, [rsp+1B0h+var_160]
0x18004d5a6  mov     [rsp+1B0h+var_180], rax; struct IXMLDOMDocument **
0x18004d5ab  mov     [rsp+1B0h+var_188], r14; unsigned __int16 *
0x18004d5b0  mov     [rsp+1B0h+var_190], r13; unsigned __int16 *
0x18004d5b5  mov     r9, [rsp+1B0h+var_168]; unsigned __int16 *
0x18004d5ba  mov     r8, [rsp+1B0h+var_140]; unsigned __int16 *
0x18004d5bf  mov     edx, esi; unsigned int
0x18004d5c1  mov     rcx, rdi; struct WwanSmsStoreMessage *
0x18004d5c4  call    ?GetStatusReportMessageXml@@YAJPEAUWwanSmsStoreMessage@@KPEBG111PEAPEAUIXMLDOMDocument@@@Z; GetStatusReportMessageXml(WwanSmsStoreMessage *,ulong,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMDocument * *)
0x18004d5c9  mov     r14d, eax
0x18004d5cc  jmp     short loc_18004D604
0x18004d5ce  lea     rax, [rsp+1B0h+var_160]
0x18004d5d3  mov     [rsp+1B0h+var_180], rax; struct IXMLDOMDocument **
0x18004d5d8  mov     [rsp+1B0h+var_188], r14; unsigned __int16 *
0x18004d5dd  mov     [rsp+1B0h+var_190], r13; unsigned __int16 *
0x18004d5e2  mov     r9, [rsp+1B0h+var_168]; unsigned __int16 *
0x18004d5e7  mov     r8, [rsp+1B0h+var_140]; unsigned __int16 *
0x18004d5ec  mov     edx, esi; unsigned int
0x18004d5ee  mov     rcx, rdi; struct WwanSmsStoreMessage *
0x18004d5f1  call    ?GetVoicemailMessageXml@@YAJPEAUWwanSmsStoreMessage@@KPEBG111PEAPEAUIXMLDOMDocument@@@Z; GetVoicemailMessageXml(WwanSmsStoreMessage *,ulong,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMDocument * *)
0x18004d5f6  jmp     short loc_18004D5C9
0x18004d5f8  cmp     byte ptr [rdi+4], 2
0x18004d5fc  jz      short loc_18004D639
0x18004d5fe  mov     r14d, 8007065Eh
0x18004d604  lea     rcx, [rbp+0B0h+var_E0]
0x18004d608  call    ??1?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<uchar>>::~vector<std::vector<uchar>>(void)
0x18004d60d  test    r14d, r14d
0x18004d610  js      short loc_18004D664
0x18004d612  mov     rax, [rbx]
0x18004d615  mov     r13, [rsp+1B0h+var_158]
0x18004d61a  mov     r8d, [r13+390h]
0x18004d621  mov     rdx, [rsp+1B0h+var_160]
0x18004d626  mov     rcx, rbx
0x18004d629  mov     rax, [rax+18h]
0x18004d62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d632  jmp     short loc_18004D688
0x18004d634  mov     rax, [rsp+1B0h+var_168]
0x18004d639  lea     rcx, [rsp+1B0h+var_160]
0x18004d63e  mov     [rsp+1B0h+var_180], rcx; struct IXMLDOMDocument **
0x18004d643  mov     [rsp+1B0h+var_188], r14; unsigned __int16 *
0x18004d648  mov     [rsp+1B0h+var_190], r13; unsigned __int16 *
0x18004d64d  mov     r9, rax; unsigned __int16 *
0x18004d650  mov     r8, [rsp+1B0h+var_140]; unsigned __int16 *
0x18004d655  mov     edx, esi; unsigned int
0x18004d657  mov     rcx, rdi; struct WwanSmsStoreMessage *
0x18004d65a  call    ?GetDeliverMessageXml@@YAJPEAUWwanSmsStoreMessage@@KPEBG111PEAPEAUIXMLDOMDocument@@@Z; GetDeliverMessageXml(WwanSmsStoreMessage *,ulong,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMDocument * *)
0x18004d65f  jmp     loc_18004D5C9
0x18004d664  mov     dword ptr [rsp+1B0h+var_190], esi
0x18004d668  lea     r9, aFailedToGenera; "Failed to generate XML for sms pdus seg"...
0x18004d66f  mov     r8d, r14d; int
0x18004d672  mov     edx, 6D5h; unsigned int
0x18004d677  lea     rcx, aCwwansmsdevice; "CWwanSmsDevice::ProcessPendingMessages"
0x18004d67e  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18004d683  mov     r13, [rsp+1B0h+var_158]
0x18004d688  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004d68f  mov     [rbp+0B0h+var_130], rax
0x18004d693  mov     [rbp+0B0h+var_128], r15
  ... truncated ...
```
