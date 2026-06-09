# QOEAccumulator::Initialize(void)

- ea: `0x1800aa710`
- end: `0x1800aa939`
- name: `?Initialize@QOEAccumulator@@UEAAJXZ`
- size: `553`
- prototype: `__int64 __fastcall(QOEAccumulator *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800012dc`
- `0x180001f84`
- `0x180002d3c`
- `0x18003ab0c`
- `0x180077aa0`
- `0x180079770`
- `0x18007f76c`
- `0x1800aa710`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa785`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa785`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aa929`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aa929`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aa746`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aa746`

## string_xrefs

- `0x1800aa73f`: `Software\Policies\Microsoft\Windows NT\Terminal Services`

## pseudocode

```c
__int64 __fastcall QOEAccumulator::Initialize(QOEAccumulator *this)
{
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  BOOL v5; // eax
  void *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  void *v9; // rdi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v11; // edi
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  const char *v17; // [rsp+58h] [rbp-8h] BYREF
  char *Data; // [rsp+80h] [rbp+20h] BYREF
  const char *cbData; // [rsp+88h] [rbp+28h] BYREF
  const char *Type; // [rsp+90h] [rbp+30h] BYREF
  __int64 v21; // [rsp+98h] [rbp+38h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
          0,
          0x20019u,
          &hKey) )
  {
    LODWORD(Data) = 0;
    LODWORD(Type) = 0;
    LODWORD(cbData) = 4;
    if ( !RegQueryValueExW(
            hKey,
            L"fEnableConnectionIntervalGraphicsData",
            0,
            (LPDWORD)&Type,
            (LPBYTE)&Data,
            (LPDWORD)&cbData) )
    {
      v5 = (_DWORD)Data != 0;
      *((_DWORD *)this + 41576) = v5;
      *((_DWORD *)this + 13728) = v5;
      *((_DWORD *)this + 27578) = v5;
      *((_DWORD *)this + 41428) = v5;
      if ( (unsigned int)CallbackContext > 4 )
      {
        LODWORD(v21) = *((_DWORD *)this + 41576);
        v17 = "Start Logging QoE data Intervals";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v2,
          (unsigned int)byte_18027E0CD,
          v3,
          v4,
          (__int64)&v17,
          (__int64)&v21);
      }
    }
  }
  *((_DWORD *)this + 5) |= 2u;
  v6 = operator new(0x29040u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v6;
  if ( v6 )
    `vector constructor iterator'(v6, 0xA8u, 0x3E8u, (void *(*)(void *))FrameInfo::FrameInfo);
  else
    v9 = 0;
  *((_QWORD *)this + 20784) = v9;
  if ( v9 )
  {
    v11 = 0;
    if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v7, v8) )
    {
      v21 = 0x1000000;
      Data = (char *)this + 166256;
      cbData = "QoE";
      Type = "Stack";
      v17 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v12,
        (unsigned int)byte_18027E071,
        v13,
        v14,
        (__int64)&v17,
        (__int64)&v21,
        (__int64)&Type,
        (__int64)&cbData,
        (__int64)&Data);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)&WPP_07aa794f20be355cbe1c19337e7a8fed_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"m_pFrameInfo");
    }
    v11 = -2147467261;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v11;
}

```

## disassembly

```asm
0x1800aa710  push    rbp
0x1800aa712  push    rbx
0x1800aa713  push    rdi
0x1800aa714  mov     rbp, rsp
0x1800aa717  sub     rsp, 60h
0x1800aa71b  mov     rbx, rcx
0x1800aa71e  mov     [rbp+hKey], 0
0x1800aa726  lea     rax, [rbp+hKey]
0x1800aa72a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800aa731  mov     r9d, 20019h; samDesired
0x1800aa737  mov     [rsp+60h+phkResult], rax; phkResult
0x1800aa73c  xor     r8d, r8d; ulOptions
0x1800aa73f  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows "...
0x1800aa746  call    cs:__imp_RegOpenKeyExW
0x1800aa74c  test    eax, eax
0x1800aa74e  jnz     loc_1800AA7EA
0x1800aa754  mov     rcx, [rbp+hKey]; hKey
0x1800aa758  lea     r9, [rbp+Type]; lpType
0x1800aa75c  mov     dword ptr [rbp+Data], eax
0x1800aa75f  lea     rdx, aFenableconnect; "fEnableConnectionIntervalGraphicsData"
0x1800aa766  mov     dword ptr [rbp+Type], eax
0x1800aa769  xor     r8d, r8d; lpReserved
0x1800aa76c  lea     rax, [rbp+cbData]
0x1800aa770  mov     dword ptr [rbp+cbData], 4
0x1800aa777  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800aa77c  lea     rax, [rbp+Data]
0x1800aa780  mov     [rsp+60h+phkResult], rax; lpData
0x1800aa785  call    cs:__imp_RegQueryValueExW
0x1800aa78b  test    eax, eax
0x1800aa78d  jnz     short loc_1800AA7EA
0x1800aa78f  cmp     dword ptr [rbp+Data], eax
0x1800aa792  setnz   al
0x1800aa795  mov     [rbx+289A0h], eax
0x1800aa79b  mov     [rbx+0D680h], eax
0x1800aa7a1  mov     [rbx+1AEE8h], eax
0x1800aa7a7  mov     [rbx+28750h], eax
0x1800aa7ad  mov     eax, cs:CallbackContext
0x1800aa7b3  cmp     eax, 4
0x1800aa7b6  jbe     short loc_1800AA7EA
0x1800aa7b8  mov     eax, [rbx+289A0h]
0x1800aa7be  lea     rdx, byte_18027E0CD
0x1800aa7c5  mov     dword ptr [rbp+arg_18], eax
0x1800aa7c8  lea     rax, aStartLoggingQo; "Start Logging QoE data Intervals"
0x1800aa7cf  mov     [rbp+var_8], rax
0x1800aa7d3  lea     rax, [rbp+arg_18]
0x1800aa7d7  mov     [rsp+60h+lpcbData], rax
0x1800aa7dc  lea     rax, [rbp+var_8]
0x1800aa7e0  mov     [rsp+60h+phkResult], rax
0x1800aa7e5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800aa7ea  or      dword ptr [rbx+14h], 2
0x1800aa7ee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800aa7f5  mov     ecx, 29040h; unsigned __int64
0x1800aa7fa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800aa7ff  mov     rdi, rax
0x1800aa802  test    rax, rax
0x1800aa805  jz      short loc_1800AA823
0x1800aa807  lea     r9, ??0FrameInfo@@QEAA@XZ; void *(*)(void *)
0x1800aa80e  mov     edx, 0A8h; unsigned __int64
0x1800aa813  mov     r8d, 3E8h; unsigned __int64
0x1800aa819  mov     rcx, rax; void *
0x1800aa81c  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800aa821  jmp     short loc_1800AA825
0x1800aa823  xor     edi, edi
0x1800aa825  mov     [rbx+28980h], rdi
0x1800aa82c  test    rdi, rdi
0x1800aa82f  jnz     short loc_1800AA888
0x1800aa831  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa838  lea     rcx, WPP_GLOBAL_Control
0x1800aa83f  cmp     rax, rcx
0x1800aa842  jz      short loc_1800AA87E
0x1800aa844  test    byte ptr [rax+1Ch], 8
0x1800aa848  jz      short loc_1800AA87E
0x1800aa84a  cmp     byte ptr [rax+19h], 2
0x1800aa84e  jb      short loc_1800AA87E
0x1800aa850  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aa855  lea     rcx, aMPframeinfo; "m_pFrameInfo"
0x1800aa85c  mov     r9d, eax
0x1800aa85f  mov     [rsp+60h+phkResult], rcx
0x1800aa864  lea     edx, [rdi+2Ah]
0x1800aa867  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa86e  lea     r8, WPP_07aa794f20be355cbe1c19337e7a8fed_Traceguids
0x1800aa875  mov     rcx, [rcx+10h]
0x1800aa879  call    WPP_SF_Ds
0x1800aa87e  mov     edi, 80004003h
0x1800aa883  jmp     loc_1800AA920
0x1800aa888  mov     eax, cs:CallbackContext
0x1800aa88e  xor     edi, edi
0x1800aa890  cmp     eax, 4
0x1800aa893  jbe     loc_1800AA920
0x1800aa899  mov     rdx, 470000000000h
0x1800aa8a3  lea     rcx, CallbackContext
0x1800aa8aa  call    _tlgKeywordOn
0x1800aa8af  test    al, al
0x1800aa8b1  jz      short loc_1800AA920
0x1800aa8b3  lea     rax, [rbx+28970h]
0x1800aa8ba  mov     [rbp+arg_18], 1000000h
0x1800aa8c2  mov     [rbp+Data], rax
0x1800aa8c6  lea     rdx, byte_18027E071
0x1800aa8cd  lea     rax, aQoe_0; "QoE"
0x1800aa8d4  mov     [rbp+cbData], rax
0x1800aa8d8  lea     rax, aStack; "Stack"
0x1800aa8df  mov     [rbp+Type], rax
0x1800aa8e3  lea     rax, aCheckpoint; "Checkpoint"
0x1800aa8ea  mov     [rbp+var_8], rax
0x1800aa8ee  lea     rax, [rbp+Data]
0x1800aa8f2  mov     [rsp+60h+var_20], rax
0x1800aa8f7  lea     rax, [rbp+cbData]
0x1800aa8fb  mov     [rsp+60h+var_28], rax
0x1800aa900  lea     rax, [rbp+Type]
0x1800aa904  mov     [rsp+60h+var_30], rax
0x1800aa909  lea     rax, [rbp+arg_18]
0x1800aa90d  mov     [rsp+60h+lpcbData], rax
0x1800aa912  lea     rax, [rbp+var_8]
0x1800aa916  mov     [rsp+60h+phkResult], rax
0x1800aa91b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x1800aa920  mov     rcx, [rbp+hKey]; hKey
0x1800aa924  test    rcx, rcx
0x1800aa927  jz      short loc_1800AA92F
0x1800aa929  call    cs:__imp_RegCloseKey
0x1800aa92f  mov     eax, edi
0x1800aa931  add     rsp, 60h
0x1800aa935  pop     rdi
0x1800aa936  pop     rbx
0x1800aa937  pop     rbp
0x1800aa938  retn
```
