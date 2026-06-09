# FactoryLifeTimeThread::QuotaCheck(void)

- ea: `0x140008d40`
- end: `0x140008f21`
- name: `?QuotaCheck@FactoryLifeTimeThread@@QEAAHXZ`
- size: `481`
- prototype: `__int64 __fastcall(FactoryLifeTimeThread *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1400071a0`

## callees

- `0x140008d40`
- `0x14000a0f0`
- `0x14000a530`
- `0x14002c4a0`
- `0x14002cb2c`
- `0x14002d448`
- `0x14002ddf4`
- `0x140046430`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x140008d94`
- `ntdll!NtQuerySystemInformation` at `0x140008d94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140008dd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140008dd7`

## string_xrefs

- `0x140008e8e`: `ThreadCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FactoryLifeTimeThread::QuotaCheck(FactoryLifeTimeThread *this)
{
  ULONG v1; // ebx
  unsigned int *v2; // rsi
  unsigned int v3; // ebp
  int v4; // edi
  NTSTATUS v5; // eax
  unsigned int *v7; // rbx
  unsigned int v8; // edi
  __int64 v9; // rcx
  unsigned int v10; // edx
  const unsigned __int16 *v11; // r9
  unsigned int v12; // edx
  const unsigned __int16 *v13; // r9
  unsigned __int64 v14; // rdx
  const unsigned __int16 *v15; // r9
  ULONG ReturnLength; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int16 *v17[3]; // [rsp+28h] [rbp-50h] BYREF
  unsigned __int64 v18; // [rsp+40h] [rbp-38h]

  ReturnLength = 0;
  v1 = 1572864;
  v2 = (unsigned int *)operator new(0x180000u);
  if ( !v2 )
    return 0;
  v3 = 1;
  v4 = 1;
  while ( v4 )
  {
    v5 = NtQuerySystemInformation(SystemProcessInformation, v2, v1, &ReturnLength);
    if ( v5 == -1073741820 )
    {
      operator delete(v2);
      v1 = (ReturnLength >> 4) + ReturnLength + 0x8000;
      v2 = (unsigned int *)operator new(v1);
      if ( !v2 )
        return 0;
    }
    else
    {
      v4 = 0;
      if ( v5 < 0 )
      {
        operator delete(v2);
        return 0;
      }
    }
  }
  v7 = v2;
  do
  {
    v8 = v7[20];
    if ( v8 == GetCurrentProcessId()
      && (v7[24] > ProviderSubSystem_Globals::s_Quota_HandleCount
       || v7[1] > ProviderSubSystem_Globals::s_Quota_NumberOfThreads
       || *((_QWORD *)v7 + 25) > *(_QWORD *)&ProviderSubSystem_Globals::s_Quota_PrivatePageCount)
      && !ProviderSubSystem_Globals::s_IsHighMemoryUsageHost )
    {
      std::wstring::wstring(v17);
      GetProvidersList(v17);
      v10 = v7[24];
      if ( v10 > ProviderSubSystem_Globals::s_Quota_HandleCount )
      {
        v11 = (const unsigned __int16 *)v17;
        if ( v18 >= 8 )
          v11 = v17[0];
        ReportWarningEvent(L"HandleCount", v10, ProviderSubSystem_Globals::s_Quota_HandleCount, v11);
        v3 = 0;
      }
      v12 = v7[1];
      if ( v12 > ProviderSubSystem_Globals::s_Quota_NumberOfThreads )
      {
        v13 = (const unsigned __int16 *)v17;
        if ( v18 >= 8 )
          v13 = v17[0];
        ReportWarningEvent(L"ThreadCount", v12, ProviderSubSystem_Globals::s_Quota_NumberOfThreads, v13);
        v3 = 0;
      }
      v14 = *((_QWORD *)v7 + 25);
      if ( v14 > *(_QWORD *)&ProviderSubSystem_Globals::s_Quota_PrivatePageCount )
      {
        v15 = (const unsigned __int16 *)v17;
        if ( v18 >= 8 )
          v15 = v17[0];
        ReportWarningEvent(L"PrivatePageCount", v14, ProviderSubSystem_Globals::s_Quota_PrivatePageCount, v15);
        v3 = 0;
      }
      LOBYTE(v14) = 1;
      std::wstring::_Tidy(v17, v14, 0);
    }
    v9 = *v7;
    if ( !(_DWORD)v9 )
      break;
    v7 = (unsigned int *)((char *)v7 + v9);
  }
  while ( v7 );
  operator delete(v2);
  return v3;
}

```

## disassembly

```asm
0x140008d40  push    rbx
0x140008d42  push    rbp
0x140008d43  push    rsi
0x140008d44  push    rdi
0x140008d45  sub     rsp, 58h
0x140008d49  mov     rax, cs:__security_cookie
0x140008d50  xor     rax, rsp
0x140008d53  mov     [rsp+78h+var_30], rax
0x140008d58  mov     [rsp+78h+ReturnLength], 0
0x140008d60  mov     ebx, 180000h
0x140008d65  mov     ecx, ebx; dwBytes
0x140008d67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140008d6c  mov     rsi, rax
0x140008d6f  test    rax, rax
0x140008d72  jz      short loc_140008DCD
0x140008d74  mov     ebp, 1
0x140008d79  mov     edi, ebp
0x140008d7b  nop     dword ptr [rax+rax+00h]
0x140008d80  test    edi, edi
0x140008d82  jz      short loc_140008DD1
0x140008d84  lea     r9, [rsp+78h+ReturnLength]; ReturnLength
0x140008d89  mov     r8d, ebx; SystemInformationLength
0x140008d8c  mov     rdx, rsi; SystemInformation
0x140008d8f  mov     ecx, 5; SystemInformationClass
0x140008d94  call    cs:__imp_NtQuerySystemInformation
0x140008d9a  cmp     eax, 0C0000004h
0x140008d9f  jnz     loc_140008EE2
0x140008da5  mov     rcx, rsi; lpMem
0x140008da8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140008dad  mov     ecx, [rsp+78h+ReturnLength]
0x140008db1  mov     eax, ecx
0x140008db3  shr     eax, 4
0x140008db6  lea     ebx, [rcx+8000h]
0x140008dbc  add     ebx, eax
0x140008dbe  mov     ecx, ebx; dwBytes
0x140008dc0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140008dc5  mov     rsi, rax
0x140008dc8  test    rax, rax
0x140008dcb  jnz     short loc_140008D80
0x140008dcd  xor     eax, eax
0x140008dcf  jmp     short loc_140008DF6
0x140008dd1  mov     rbx, rsi
0x140008dd4  mov     edi, [rbx+50h]
0x140008dd7  call    cs:__imp_GetCurrentProcessId
0x140008ddd  cmp     edi, eax
0x140008ddf  jz      short loc_140008E0C
0x140008de1  mov     ecx, [rbx]
0x140008de3  test    ecx, ecx
0x140008de5  jz      short loc_140008DEC
0x140008de7  add     rbx, rcx
0x140008dea  jnz     short loc_140008DD4
0x140008dec  mov     rcx, rsi; lpMem
0x140008def  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140008df4  mov     eax, ebp
0x140008df6  mov     rcx, [rsp+78h+var_30]
0x140008dfb  xor     rcx, rsp; StackCookie
0x140008dfe  call    __security_check_cookie
0x140008e03  add     rsp, 58h
0x140008e07  pop     rdi
0x140008e08  pop     rsi
0x140008e09  pop     rbp
0x140008e0a  pop     rbx
0x140008e0b  retn
0x140008e0c  mov     eax, cs:?s_Quota_HandleCount@ProviderSubSystem_Globals@@2KA; ulong ProviderSubSystem_Globals::s_Quota_HandleCount
0x140008e12  cmp     [rbx+60h], eax
0x140008e15  jbe     loc_140008EF9
0x140008e1b  cmp     cs:?s_IsHighMemoryUsageHost@ProviderSubSystem_Globals@@2HA, 0; int ProviderSubSystem_Globals::s_IsHighMemoryUsageHost
0x140008e22  jnz     short loc_140008DE1
0x140008e24  lea     rdx, word_14004EE4C
0x140008e2b  lea     rcx, [rsp+78h+var_50]; void *
0x140008e30  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140008e35  nop
0x140008e36  lea     rcx, [rsp+78h+var_50]
0x140008e3b  call    ?GetProvidersList@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetProvidersList(std::wstring &)
0x140008e40  mov     edx, [rbx+60h]; int
0x140008e43  mov     r8d, cs:?s_Quota_HandleCount@ProviderSubSystem_Globals@@2KA; int
0x140008e4a  cmp     edx, r8d
0x140008e4d  jbe     short loc_140008E6E
0x140008e4f  lea     r9, [rsp+78h+var_50]
0x140008e54  cmp     [rsp+78h+var_38], 8
0x140008e5a  cmovnb  r9, [rsp+78h+var_50]; unsigned __int16 *
0x140008e60  lea     rcx, aHandlecount; "HandleCount"
0x140008e67  call    ?ReportWarningEvent@@YAJPEAGHHPEBG@Z; ReportWarningEvent(ushort *,int,int,ushort const *)
0x140008e6c  xor     ebp, ebp
0x140008e6e  mov     edx, [rbx+4]; int
0x140008e71  mov     r8d, cs:?s_Quota_NumberOfThreads@ProviderSubSystem_Globals@@2KA; int
0x140008e78  cmp     edx, r8d
0x140008e7b  jbe     short loc_140008E9C
0x140008e7d  lea     r9, [rsp+78h+var_50]
0x140008e82  cmp     [rsp+78h+var_38], 8
0x140008e88  cmovnb  r9, [rsp+78h+var_50]; unsigned __int16 *
0x140008e8e  lea     rcx, aThreadcount; "ThreadCount"
0x140008e95  call    ?ReportWarningEvent@@YAJPEAGHHPEBG@Z; ReportWarningEvent(ushort *,int,int,ushort const *)
0x140008e9a  xor     ebp, ebp
0x140008e9c  mov     rdx, [rbx+0C8h]; int
0x140008ea3  mov     r8, cs:?s_Quota_PrivatePageCount@ProviderSubSystem_Globals@@2_KA; int
0x140008eaa  cmp     rdx, r8
0x140008ead  jbe     short loc_140008ECE
0x140008eaf  lea     r9, [rsp+78h+var_50]
0x140008eb4  cmp     [rsp+78h+var_38], 8
0x140008eba  cmovnb  r9, [rsp+78h+var_50]; unsigned __int16 *
0x140008ec0  lea     rcx, aPrivatepagecou; "PrivatePageCount"
0x140008ec7  call    ?ReportWarningEvent@@YAJPEAGHHPEBG@Z; ReportWarningEvent(ushort *,int,int,ushort const *)
0x140008ecc  xor     ebp, ebp
0x140008ece  xor     r8d, r8d
0x140008ed1  mov     dl, 1
0x140008ed3  lea     rcx, [rsp+78h+var_50]
0x140008ed8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140008edd  jmp     loc_140008DE1
0x140008ee2  xor     edi, edi
0x140008ee4  test    eax, eax
0x140008ee6  jns     loc_140008D80
0x140008eec  mov     rcx, rsi; lpMem
0x140008eef  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140008ef4  jmp     loc_140008DCD
0x140008ef9  mov     eax, cs:?s_Quota_NumberOfThreads@ProviderSubSystem_Globals@@2KA; ulong ProviderSubSystem_Globals::s_Quota_NumberOfThreads
0x140008eff  cmp     [rbx+4], eax
0x140008f02  ja      loc_140008E1B
0x140008f08  mov     rax, cs:?s_Quota_PrivatePageCount@ProviderSubSystem_Globals@@2_KA; unsigned __int64 ProviderSubSystem_Globals::s_Quota_PrivatePageCount
0x140008f0f  cmp     [rbx+0C8h], rax
0x140008f16  jbe     loc_140008DE1
0x140008f1c  jmp     loc_140008E1B
```
