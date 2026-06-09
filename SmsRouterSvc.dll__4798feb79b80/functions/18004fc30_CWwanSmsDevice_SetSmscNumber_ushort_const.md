# CWwanSmsDevice::SetSmscNumber(ushort const *)

- ea: `0x18004fc30`
- end: `0x18004ff5b`
- name: `?SetSmscNumber@CWwanSmsDevice@@UEAAJPEBG@Z`
- size: `811`
- prototype: `__int64 __fastcall(CWwanSmsDevice *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003a60`
- `0x18000498c`
- `0x180018fe4`
- `0x180025b04`
- `0x180049460`
- `0x18004fc30`
- `0x180051108`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004fc84`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004fc84`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004fdfa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004fdfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fc99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fc99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fee7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fee7`
- `wwapi!WwanSetSmsConfiguration` at `0x18004fd5c`
- `wwapi!WwanSetSmsConfiguration` at `0x18004fd5c`

## string_xrefs

- `0x18004fd73`: `WwanSetSmsConfiguration called with SMSC %s, requestid=%d and result %d.`
- `0x18004fef0`: `WwanSetSmsConfiguration modem response hr=0x%08X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall CWwanSmsDevice::SetSmscNumber(CWwanSmsDevice *this, const unsigned __int16 *a2)
{
  signed int result; // eax
  HANDLE EventW; // r12
  char *v6; // rdi
  char *v7; // r14
  signed int v8; // ebx
  DWORD v9; // ebx
  signed int LastError; // eax
  __int64 v11; // r8
  char *v12; // rcx
  size_t v13; // rsi
  void *v14; // r15
  unsigned int v15; // [rsp+30h] [rbp-50h] BYREF
  void **v16; // [rsp+38h] [rbp-48h]
  char *v17; // [rsp+40h] [rbp-40h]
  _BYTE v18[16]; // [rsp+48h] [rbp-38h] BYREF
  _OWORD Src[2]; // [rsp+58h] [rbp-28h] BYREF

  memset(Src, 0, 28);
  if ( !a2 )
    return -2147024809;
  EventW = CreateEventW(0, 0, 0, 0);
  v15 = 0;
  if ( EventW )
  {
    v16 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
    v6 = (char *)this + 32;
    v17 = (char *)this + 32;
    (**((void (__fastcall ***)(char *))this + 4))((char *)this + 32);
    if ( !*((_DWORD *)this + 6) || (*((_DWORD *)this + 42) & 0xFFFFFFFB) != 0 )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))((char *)this + 32);
      return -2147024875;
    }
    v7 = (char *)this + 192;
    if ( *((_QWORD *)this + 26) )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))((char *)this + 32);
      return -2147019873;
    }
    DWORD2(Src[1]) = *((_DWORD *)this + 42);
    StringCchPrintfA((char *)Src, 0x15u, "%S", a2);
    v8 = WwanSetSmsConfiguration(*((_QWORD *)this + 18), (char *)this + 152, Src, &v15, 0, 0);
    LogSmsRouterInfo(
      "CWwanSmsDevice::SetSmscNumber",
      0x1DAu,
      "WwanSetSmsConfiguration called with SMSC %s, requestid=%d and result %d.",
      (const char *)Src,
      v15,
      v8);
    if ( v8 )
    {
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))((char *)this + 32);
      return v8;
    }
    *(_QWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned long,SmsSetConfigParam,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,SmsSetConfigParam>>,0>>::_Try_emplace<unsigned long const &,>(
                             (__int64)this + 192,
                             (__int64)v18,
                             &v15)
              + 24LL) = EventW;
    *(_DWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned long,SmsSetConfigParam,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,SmsSetConfigParam>>,0>>::_Try_emplace<unsigned long const &,>(
                             (__int64)this + 192,
                             (__int64)v18,
                             &v15)
              + 32LL) = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))((char *)this + 32);
    v9 = WaitForSingleObject(EventW, 0x3A980u);
    v16 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
    v17 = (char *)this + 32;
    (**(void (__fastcall ***)(char *))v6)((char *)this + 32);
    if ( v9 )
    {
      if ( v9 == 258 )
      {
        v8 = -2147023436;
        goto LABEL_32;
      }
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError <= 0 )
        goto LABEL_32;
      v8 = (unsigned __int16)LastError;
    }
    else
    {
      if ( !*(_DWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned long,SmsSetConfigParam,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,SmsSetConfigParam>>,0>>::_Try_emplace<unsigned long const &,>(
                                     (__int64)this + 192,
                                     (__int64)v18,
                                     &v15)
                      + 32LL) )
      {
        v8 = 0;
        v12 = (char *)this + 512;
        v13 = -1;
        do
          ++v13;
        while ( *((_BYTE *)Src + v13) );
        if ( v13 > *((_QWORD *)v12 + 3) )
        {
          std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(v12, v13, v11, Src);
        }
        else
        {
          if ( *((_QWORD *)v12 + 3) <= 0xFu )
            v14 = v12;
          else
            v14 = *(void **)v12;
          *((_QWORD *)v12 + 2) = v13;
          memmove_0(v14, Src, v13);
          *((_BYTE *)v14 + v13) = 0;
        }
        goto LABEL_32;
      }
      v8 = *(_DWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned long,SmsSetConfigParam,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,SmsSetConfigParam>>,0>>::_Try_emplace<unsigned long const &,>(
                                    (__int64)this + 192,
                                    (__int64)v18,
                                    &v15)
                     + 32LL);
      if ( v8 <= 0 )
      {
LABEL_32:
        std::_Hash<stdext::_Hmap_traits<unsigned long,SmsSetConfigParam,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<std::pair<unsigned long const,SmsSetConfigParam>>,0>>::erase(
          v7,
          &v15);
        CloseHandle(EventW);
        LogSmsRouterInfo(
          "CWwanSmsDevice::SetSmscNumber",
          0x1FEu,
          "WwanSetSmsConfiguration modem response hr=0x%08X.",
          v8);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
        return v8;
      }
      v8 = (unsigned __int16)v8;
    }
    v8 |= 0x80070000;
    goto LABEL_32;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18004fc30  mov     [rsp-28h+arg_10], rbx
0x18004fc35  mov     [rsp-28h+arg_18], rsi
0x18004fc3a  push    rbp
0x18004fc3b  push    rdi
0x18004fc3c  push    r12
0x18004fc3e  push    r14
0x18004fc40  push    r15
0x18004fc42  mov     rbp, rsp
0x18004fc45  sub     rsp, 80h
0x18004fc4c  mov     rax, cs:__security_cookie
0x18004fc53  xor     rax, rsp
0x18004fc56  mov     [rbp+var_8], rax
0x18004fc5a  mov     rbx, rdx
0x18004fc5d  mov     rsi, rcx
0x18004fc60  xorps   xmm0, xmm0
0x18004fc63  movups  [rbp+Src], xmm0
0x18004fc67  movups  [rbp+Src+0Ch], xmm0
0x18004fc6b  test    rdx, rdx
0x18004fc6e  jnz     short loc_18004FC7A
0x18004fc70  mov     eax, 80070057h
0x18004fc75  jmp     loc_18004FF33
0x18004fc7a  xor     r9d, r9d; lpName
0x18004fc7d  xor     r8d, r8d; bInitialState
0x18004fc80  xor     edx, edx; bManualReset
0x18004fc82  xor     ecx, ecx; lpEventAttributes
0x18004fc84  call    cs:__imp_CreateEventW
0x18004fc8a  mov     r12, rax
0x18004fc8d  mov     [rbp+var_50], 0
0x18004fc94  test    rax, rax
0x18004fc97  jnz     short loc_18004FCB4
0x18004fc99  call    cs:__imp_GetLastError
0x18004fc9f  test    eax, eax
0x18004fca1  jle     loc_18004FF33
0x18004fca7  movzx   eax, ax
0x18004fcaa  or      eax, 80070000h
0x18004fcaf  jmp     loc_18004FF33
0x18004fcb4  lea     r15, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004fcbb  mov     [rbp+var_48], r15
0x18004fcbf  lea     rdi, [rsi+20h]
0x18004fcc3  mov     [rbp+var_40], rdi
0x18004fcc7  mov     rax, [rdi]
0x18004fcca  mov     rcx, rdi
0x18004fccd  mov     rax, [rax]
0x18004fcd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fcd5  nop
0x18004fcd6  cmp     dword ptr [rsi+18h], 0
0x18004fcda  jz      loc_18004FF1E
0x18004fce0  mov     eax, [rsi+0A8h]
0x18004fce6  test    eax, 0FFFFFFFBh
0x18004fceb  jnz     loc_18004FF1E
0x18004fcf1  lea     r14, [rsi+0C0h]
0x18004fcf8  cmp     qword ptr [r14+10h], 0
0x18004fcfd  jbe     short loc_18004FD19
0x18004fcff  mov     rax, [rdi]
0x18004fd02  mov     rcx, rdi
0x18004fd05  mov     rax, [rax+8]
0x18004fd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fd0e  nop
0x18004fd0f  mov     eax, 8007139Fh
0x18004fd14  jmp     loc_18004FF33
0x18004fd19  mov     [rbp+var_10], eax
0x18004fd1c  mov     r9, rbx
0x18004fd1f  lea     r8, aS; "%S"
0x18004fd26  mov     edx, 15h; unsigned __int64
0x18004fd2b  lea     rcx, [rbp+Src]; char *
0x18004fd2f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18004fd34  lea     rdx, [rsi+98h]
0x18004fd3b  mov     [rsp+80h+var_58], 0
0x18004fd44  mov     [rsp+80h+var_60], 0
0x18004fd4d  lea     r9, [rbp+var_50]
0x18004fd51  lea     r8, [rbp+Src]
0x18004fd55  mov     rcx, [rsi+90h]
0x18004fd5c  call    cs:__imp_WwanSetSmsConfiguration
0x18004fd62  mov     ebx, eax
0x18004fd64  mov     dword ptr [rsp+80h+var_58], eax
0x18004fd68  mov     eax, [rbp+var_50]
0x18004fd6b  mov     dword ptr [rsp+80h+var_60], eax
0x18004fd6f  lea     r9, [rbp+Src]
0x18004fd73  lea     r8, aWwansetsmsconf_0; "WwanSetSmsConfiguration called with SMS"...
0x18004fd7a  mov     edx, 1DAh; unsigned int
0x18004fd7f  lea     rcx, aCwwansmsdevice_4; "CWwanSmsDevice::SetSmscNumber"
0x18004fd86  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004fd8b  test    ebx, ebx
0x18004fd8d  jz      short loc_18004FDB1
0x18004fd8f  jle     short loc_18004FD9A
0x18004fd91  movzx   ebx, bx
0x18004fd94  or      ebx, 80070000h
0x18004fd9a  mov     rcx, [rdi]
0x18004fd9d  mov     rax, [rcx+8]
0x18004fda1  mov     rcx, rdi
0x18004fda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fda9  nop
0x18004fdaa  mov     eax, ebx
0x18004fdac  jmp     loc_18004FF33
0x18004fdb1  lea     r8, [rbp+var_50]
0x18004fdb5  lea     rdx, [rbp+var_38]
0x18004fdb9  mov     rcx, r14
0x18004fdbc  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Hmap_traits@KVSmsSetConfigParam@@V?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKVSmsSetConfigParam@@@std@@@std@@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKVSmsSetConfigParam@@@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<stdext::_Hmap_traits<ulong,SmsSetConfigParam,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,SmsSetConfigParam>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x18004fdc1  mov     rcx, [rax]
0x18004fdc4  mov     [rcx+18h], r12
0x18004fdc8  lea     r8, [rbp+var_50]
0x18004fdcc  lea     rdx, [rbp+var_38]
0x18004fdd0  mov     rcx, r14
0x18004fdd3  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Hmap_traits@KVSmsSetConfigParam@@V?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKVSmsSetConfigParam@@@std@@@std@@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKVSmsSetConfigParam@@@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<stdext::_Hmap_traits<ulong,SmsSetConfigParam,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,SmsSetConfigParam>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x18004fdd8  mov     rcx, [rax]
0x18004fddb  mov     dword ptr [rcx+20h], 0
0x18004fde2  mov     rax, [rdi]
0x18004fde5  mov     rcx, rdi
0x18004fde8  mov     rax, [rax+8]
0x18004fdec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fdf1  nop
0x18004fdf2  mov     edx, 3A980h; dwMilliseconds
0x18004fdf7  mov     rcx, r12; hHandle
0x18004fdfa  call    cs:__imp_WaitForSingleObject
0x18004fe00  mov     ebx, eax
0x18004fe02  mov     [rbp+var_48], r15
0x18004fe06  mov     [rbp+var_40], rdi
0x18004fe0a  mov     rcx, [rdi]
0x18004fe0d  mov     rax, [rcx]
0x18004fe10  mov     rcx, rdi
0x18004fe13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe18  nop
0x18004fe19  test    ebx, ebx
0x18004fe1b  jz      short loc_18004FE47
0x18004fe1d  cmp     ebx, 102h
0x18004fe23  jnz     short loc_18004FE2F
0x18004fe25  mov     ebx, 800705B4h
0x18004fe2a  jmp     loc_18004FED8
0x18004fe2f  call    cs:__imp_GetLastError
0x18004fe35  mov     ebx, eax
0x18004fe37  test    eax, eax
0x18004fe39  jle     loc_18004FED8
0x18004fe3f  movzx   ebx, ax
0x18004fe42  jmp     loc_18004FED2
0x18004fe47  lea     r8, [rbp+var_50]
0x18004fe4b  lea     rdx, [rbp+var_38]
0x18004fe4f  mov     rcx, r14
0x18004fe52  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Hmap_traits@KVSmsSetConfigParam@@V?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKVSmsSetConfigParam@@@std@@@std@@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKVSmsSetConfigParam@@@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<stdext::_Hmap_traits<ulong,SmsSetConfigParam,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,SmsSetConfigParam>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x18004fe57  mov     rcx, [rax]
0x18004fe5a  cmp     dword ptr [rcx+20h], 0
0x18004fe5e  jnz     short loc_18004FEB5
0x18004fe60  xor     ebx, ebx
0x18004fe62  lea     rcx, [rsi+200h]
0x18004fe69  lea     rax, [rbp+Src]
0x18004fe6d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004fe71  inc     rsi
0x18004fe74  cmp     [rax+rsi], bl
0x18004fe77  jnz     short loc_18004FE71
0x18004fe79  cmp     rsi, [rcx+18h]
0x18004fe7d  ja      short loc_18004FEA7
0x18004fe7f  cmp     qword ptr [rcx+18h], 0Fh
0x18004fe84  jbe     short loc_18004FE8B
0x18004fe86  mov     r15, [rcx]
0x18004fe89  jmp     short loc_18004FE8E
0x18004fe8b  mov     r15, rcx
0x18004fe8e  mov     [rcx+10h], rsi
0x18004fe92  mov     r8, rsi; Size
0x18004fe95  lea     rdx, [rbp+Src]; Src
0x18004fe99  mov     rcx, r15; void *
0x18004fe9c  call    memmove_0
0x18004fea1  mov     [rsi+r15], bl
0x18004fea5  jmp     short loc_18004FED8
0x18004fea7  lea     r9, [rbp+Src]
0x18004feab  mov     rdx, rsi
0x18004feae  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x18004feb3  jmp     short loc_18004FED8
0x18004feb5  lea     r8, [rbp+var_50]
0x18004feb9  lea     rdx, [rbp+var_38]
0x18004febd  mov     rcx, r14
0x18004fec0  call    ??$_Try_emplace@AEBK$$V@?$_Hash@V?$_Hmap_traits@KVSmsSetConfigParam@@V?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKVSmsSetConfigParam@@@std@@@std@@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKVSmsSetConfigParam@@@std@@PEAX@std@@_N@1@AEBK@Z; std::_Hash<stdext::_Hmap_traits<ulong,SmsSetConfigParam,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,SmsSetConfigParam>>,0>>::_Try_emplace<ulong const &,>(ulong const &)
0x18004fec5  mov     rcx, [rax]
0x18004fec8  mov     ebx, [rcx+20h]
0x18004fecb  test    ebx, ebx
0x18004fecd  jle     short loc_18004FED8
0x18004fecf  movzx   ebx, bx
0x18004fed2  or      ebx, 80070000h
0x18004fed8  lea     rdx, [rbp+var_50]
0x18004fedc  mov     rcx, r14
0x18004fedf  call    ?erase@?$_Hash@V?$_Hmap_traits@KVSmsSetConfigParam@@V?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@U?$pair@$$CBKVSmsSetConfigParam@@@std@@@std@@$0A@@stdext@@@std@@QEAA_KAEBK@Z; std::_Hash<stdext::_Hmap_traits<ulong,SmsSetConfigParam,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<std::pair<ulong const,SmsSetConfigParam>>,0>>::erase(ulong const &)
0x18004fee4  mov     rcx, r12; hObject
0x18004fee7  call    cs:__imp_CloseHandle
0x18004feed  mov     r9d, ebx
0x18004fef0  lea     r8, aWwansetsmsconf_1; "WwanSetSmsConfiguration modem response "...
0x18004fef7  mov     edx, 1FEh; unsigned int
0x18004fefc  lea     rcx, aCwwansmsdevice_4; "CWwanSmsDevice::SetSmscNumber"
0x18004ff03  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004ff08  nop
0x18004ff09  mov     rdx, [rdi]
0x18004ff0c  mov     rcx, rdi
0x18004ff0f  mov     rax, [rdx+8]
0x18004ff13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff18  nop
0x18004ff19  jmp     loc_18004FDAA
0x18004ff1e  mov     rax, [rdi]
0x18004ff21  mov     rcx, rdi
0x18004ff24  mov     rax, [rax+8]
0x18004ff28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff2d  nop
0x18004ff2e  mov     eax, 80070015h
0x18004ff33  mov     rcx, [rbp+var_8]
0x18004ff37  xor     rcx, rsp; StackCookie
0x18004ff3a  call    __security_check_cookie
0x18004ff3f  lea     r11, [rsp+80h+var_s0]
0x18004ff47  mov     rbx, [r11+40h]
0x18004ff4b  mov     rsi, [r11+48h]
0x18004ff4f  mov     rsp, r11
0x18004ff52  pop     r15
0x18004ff54  pop     r14
0x18004ff56  pop     r12
0x18004ff58  pop     rdi
0x18004ff59  pop     rbp
0x18004ff5a  retn
```
