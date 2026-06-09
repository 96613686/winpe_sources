# ChatServiceRegistrationToken::_Initialize(ChatServiceHttpHeader *)

- ea: `0x18009b060`
- end: `0x18009b24e`
- name: `?_Initialize@ChatServiceRegistrationToken@@AEAAJPEAVChatServiceHttpHeader@@@Z`
- size: `494`
- prototype: `__int64 __fastcall(ChatServiceRegistrationToken *__hidden this, struct ChatServiceHttpHeader *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18000b7fc`
- `0x18009ab88`
- `0x18009adb4`
- `0x18009b060`
- `0x1800c6940`

## import_xrefs

- `msvcrt!_wtoi64` at `0x18009b17a`
- `msvcrt!_wtoi64` at `0x18009b17a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18009b1fb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18009b1fb`

## string_xrefs

- `0x18009b09f`: `registrationToken`

## pseudocode

```c
__int64 __fastcall ChatServiceRegistrationToken::_Initialize(
        ChatServiceRegistrationToken *this,
        struct ChatServiceHttpHeader *a2)
{
  unsigned int v4; // ebx
  char *v5; // rbx
  __int64 v6; // rcx
  GUID pclsid; // [rsp+30h] [rbp-29h] BYREF
  _OWORD v9[2]; // [rsp+40h] [rbp-19h] BYREF
  _OWORD v10[2]; // [rsp+60h] [rbp+7h] BYREF
  _OWORD v11[2]; // [rsp+80h] [rbp+27h] BYREF

  memset(v9, 0, sizeof(v9));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v9);
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          v9,
                          L"registrationToken",
                          17)
    && (v5 = (char *)a2 + 88,
        *(_QWORD *)&pclsid.Data1 = 0,
        utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::find<void>(
          v5,
          &pclsid,
          v9),
        (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 24,
                           *(_QWORD *)(*(_QWORD *)&pclsid.Data1 + 56LL),
                           (__int64)(*(_QWORD *)(*(_QWORD *)&pclsid.Data1 + 64LL)
                                   - *(_QWORD *)(*(_QWORD *)&pclsid.Data1 + 56LL)) >> 1)) )
  {
    memset(v10, 0, sizeof(v10));
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v10);
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            v10,
                            L"expires",
                            7) )
    {
      *(_QWORD *)&pclsid.Data1 = 0;
      utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::find<void>(
        v5,
        &pclsid,
        v10);
      *((_QWORD *)this + 7) = _wtoi64(*(const wchar_t **)(*(_QWORD *)&pclsid.Data1 + 56LL));
      memset(v11, 0, sizeof(v11));
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v11);
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                              v11,
                              L"endpointId",
                              10) )
      {
        *(_QWORD *)&pclsid.Data1 = 0;
        utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::find<void>(
          v5,
          &pclsid,
          v11);
        v6 = *(_QWORD *)&pclsid.Data1;
        if ( *(char **)&pclsid.Data1 != v5 )
        {
          pclsid = GUID_NULL;
          if ( CLSIDFromString(*(LPCOLESTR *)(v6 + 56), &pclsid) >= 0 )
            *((GUID *)this + 4) = pclsid;
        }
        v4 = 0;
      }
      else
      {
        v4 = -2147024882;
        Log_HREvent_73(-2147024882);
      }
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v11);
    }
    else
    {
      v4 = -2147024882;
      Log_HREvent_73(-2147024882);
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v10);
  }
  else
  {
    v4 = -2147024882;
    Log_HREvent_73(-2147024882);
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v9);
  return v4;
}

```

## disassembly

```asm
0x18009b060  mov     [rsp-8+arg_10], rbx
0x18009b065  mov     [rsp-8+arg_18], rdi
0x18009b06a  push    rbp
0x18009b06b  lea     rbp, [rsp-57h]
0x18009b070  sub     rsp, 0B0h
0x18009b077  mov     rax, cs:__security_cookie
0x18009b07e  xor     rax, rsp
0x18009b081  mov     [rbp+57h+var_10], rax
0x18009b085  xorps   xmm0, xmm0
0x18009b088  mov     rdi, rcx
0x18009b08b  lea     rcx, [rbp+57h+var_70]
0x18009b08f  mov     rbx, rdx
0x18009b092  movups  [rbp+57h+var_70], xmm0
0x18009b096  movups  [rbp+57h+var_60], xmm0
0x18009b09a  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18009b09f  lea     rdx, aRegistrationto; "registrationToken"
0x18009b0a6  mov     r8d, 11h
0x18009b0ac  lea     rcx, [rbp+57h+var_70]
0x18009b0b0  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18009b0b5  test    al, al
0x18009b0b7  jnz     short loc_18009B0D2
0x18009b0b9  mov     r9d, 24h ; '$'
0x18009b0bf  mov     ebx, 8007000Eh
0x18009b0c4  xor     edx, edx
0x18009b0c6  mov     ecx, ebx; int
0x18009b0c8  call    Log_HREvent_73
0x18009b0cd  jmp     loc_18009B222
0x18009b0d2  add     rbx, 58h ; 'X'
0x18009b0d6  mov     qword ptr [rbp+57h+pclsid.Data1], 0
0x18009b0de  mov     rcx, rbx
0x18009b0e1  lea     r8, [rbp+57h+var_70]
0x18009b0e5  lea     rdx, [rbp+57h+pclsid]
0x18009b0e9  call    ??$find@X@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEBA?AV?$_DlistConstIt@U?$_HashNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@@1@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::find<void>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18009b0ee  mov     rax, qword ptr [rbp+57h+pclsid.Data1]
0x18009b0f2  lea     rcx, [rdi+18h]
0x18009b0f6  mov     rdx, [rax+38h]
0x18009b0fa  mov     r8, [rax+40h]
0x18009b0fe  sub     r8, rdx
0x18009b101  sar     r8, 1
0x18009b104  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18009b109  test    al, al
0x18009b10b  jnz     short loc_18009B115
0x18009b10d  mov     r9d, 26h ; '&'
0x18009b113  jmp     short loc_18009B0BF
0x18009b115  xorps   xmm0, xmm0
0x18009b118  lea     rcx, [rbp+57h+var_50]
0x18009b11c  movups  [rbp+57h+var_50], xmm0
0x18009b120  movups  [rbp+57h+var_40], xmm0
0x18009b124  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18009b129  lea     rdx, aExpires; "expires"
0x18009b130  mov     r8d, 7
0x18009b136  lea     rcx, [rbp+57h+var_50]
0x18009b13a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18009b13f  test    al, al
0x18009b141  jnz     short loc_18009B15A
0x18009b143  xor     edx, edx
0x18009b145  mov     ebx, 8007000Eh
0x18009b14a  mov     ecx, ebx; int
0x18009b14c  lea     r9d, [rdx+29h]
0x18009b150  call    Log_HREvent_73
0x18009b155  jmp     loc_18009B219
0x18009b15a  lea     r8, [rbp+57h+var_50]
0x18009b15e  mov     qword ptr [rbp+57h+pclsid.Data1], 0
0x18009b166  lea     rdx, [rbp+57h+pclsid]
0x18009b16a  mov     rcx, rbx
0x18009b16d  call    ??$find@X@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEBA?AV?$_DlistConstIt@U?$_HashNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@@1@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::find<void>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18009b172  mov     rcx, qword ptr [rbp+57h+pclsid.Data1]
0x18009b176  mov     rcx, [rcx+38h]; String
0x18009b17a  call    cs:__imp__wtoi64
0x18009b180  xorps   xmm0, xmm0
0x18009b183  lea     rcx, [rbp+57h+var_30]
0x18009b187  mov     [rdi+38h], rax
0x18009b18b  movups  [rbp+57h+var_30], xmm0
0x18009b18f  movups  [rbp+57h+var_20], xmm0
0x18009b193  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18009b198  lea     rdx, aEndpointid; "endpointId"
0x18009b19f  mov     r8d, 0Ah
0x18009b1a5  lea     rcx, [rbp+57h+var_30]
0x18009b1a9  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18009b1ae  test    al, al
0x18009b1b0  jnz     short loc_18009B1C6
0x18009b1b2  xor     edx, edx
0x18009b1b4  mov     ebx, 8007000Eh
0x18009b1b9  mov     ecx, ebx; int
0x18009b1bb  lea     r9d, [rdx+2Eh]
0x18009b1bf  call    Log_HREvent_73
0x18009b1c4  jmp     short loc_18009B210
0x18009b1c6  lea     r8, [rbp+57h+var_30]
0x18009b1ca  mov     qword ptr [rbp+57h+pclsid.Data1], 0
0x18009b1d2  lea     rdx, [rbp+57h+pclsid]
0x18009b1d6  mov     rcx, rbx
0x18009b1d9  call    ??$find@X@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEBA?AV?$_DlistConstIt@U?$_HashNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@@1@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::find<void>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18009b1de  mov     rcx, qword ptr [rbp+57h+pclsid.Data1]
0x18009b1e2  cmp     rcx, rbx
0x18009b1e5  jz      short loc_18009B20E
0x18009b1e7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18009b1ee  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18009b1f2  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18009b1f7  mov     rcx, [rcx+38h]; lpsz
0x18009b1fb  call    cs:__imp_CLSIDFromString
0x18009b201  test    eax, eax
0x18009b203  js      short loc_18009B20E
0x18009b205  movups  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x18009b209  movdqu  xmmword ptr [rdi+40h], xmm0
0x18009b20e  xor     ebx, ebx
0x18009b210  lea     rcx, [rbp+57h+var_30]
0x18009b214  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18009b219  lea     rcx, [rbp+57h+var_50]
0x18009b21d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18009b222  lea     rcx, [rbp+57h+var_70]
0x18009b226  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18009b22b  mov     eax, ebx
0x18009b22d  mov     rcx, [rbp+57h+var_10]
0x18009b231  xor     rcx, rsp; StackCookie
0x18009b234  call    __security_check_cookie
0x18009b239  lea     r11, [rsp+0B0h+var_s0]
0x18009b241  mov     rbx, [r11+20h]
0x18009b245  mov     rdi, [r11+28h]
0x18009b249  mov     rsp, r11
0x18009b24c  pop     rbp
0x18009b24d  retn
```
