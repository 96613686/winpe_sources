# winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::IsSingleApiDeployed(winrt::hstring const &,winrt::guid)

- ea: `0x1800229c0`
- end: `0x180022dc9`
- name: `?IsSingleApiDeployed@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@AEAA_NAEBUhstring@6@Uguid@6@@Z`
- size: `1033`
- prototype: `_BOOL8 __fastcall(__int64, __int64 *, EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180022650`

## callees

- `0x1800018f0`
- `0x180004810`
- `0x18000d970`
- `0x1800119b0`
- `0x1800229c0`
- `0x180034ef0`
- `0x180035060`
- `0x18003509c`
- `0x180036140`
- `0x180039893`
- `0x18003bed0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180022cc6`
- `ADVAPI32!EventWriteTransfer` at `0x180022cc6`
- `OLEAUT32!__imp_SysAllocString` at `0x180022ae4`
- `OLEAUT32!__imp_SysAllocString` at `0x180022b54`
- `OLEAUT32!__imp_SysAllocString` at `0x180022ae4`
- `OLEAUT32!__imp_SysAllocString` at `0x180022b54`
- `OLEAUT32!__imp_SysFreeString` at `0x180022ce8`
- `OLEAUT32!__imp_SysFreeString` at `0x180022d23`
- `OLEAUT32!__imp_SysFreeString` at `0x180022ce8`
- `OLEAUT32!__imp_SysFreeString` at `0x180022d23`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::IsSingleApiDeployed(
        __int64 a1,
        __int64 *a2,
        EVENT_DESCRIPTOR *a3)
{
  const wchar_t *v6; // rbx
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  HRESULT v10; // eax
  LPVOID v11; // r15
  const OLECHAR *v12; // rdi
  BSTR *v13; // rbx
  BSTR v14; // rax
  const OLECHAR *v15; // rsi
  BSTR *v16; // rdi
  BSTR v17; // rax
  int v18; // eax
  __int64 v19; // r14
  const wchar_t *v20; // r14
  __int64 v21; // rdx
  const struct _tlgProvider_t *v22; // r10
  __int64 v23; // rax
  int v24; // eax
  bool v25; // r14
  BSTR v26; // rcx
  BSTR v27; // rcx
  const wchar_t *v29; // [rsp+30h] [rbp-89h] BYREF
  IID rclsid; // [rsp+38h] [rbp-81h] BYREF
  LPVOID v31; // [rsp+48h] [rbp-71h] BYREF
  EVENT_DESCRIPTOR v32; // [rsp+50h] [rbp-69h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v34; // [rsp+68h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-39h] BYREF
  char *v37; // [rsp+90h] [rbp-29h]
  int v38; // [rsp+98h] [rbp-21h]
  int v39; // [rsp+9Ch] [rbp-1Dh]
  const wchar_t *v40; // [rsp+A0h] [rbp-19h]
  int v41; // [rsp+A8h] [rbp-11h]
  int v42; // [rsp+ACh] [rbp-Dh]
  EVENT_DESCRIPTOR *v43; // [rsp+B0h] [rbp-9h]
  __int64 v44; // [rsp+B8h] [rbp-1h]
  IID *p_rclsid; // [rsp+C0h] [rbp+7h]
  __int64 v46; // [rsp+C8h] [rbp+Fh]

  if ( *a2 )
    v6 = *(const wchar_t **)(*a2 + 16);
  else
    v6 = &Src;
  v7 = TraceLogger::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    EventDescriptor = *a3;
    ppv = &EventDescriptor;
    v29 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>>(
      (__int64)v7,
      (unsigned __int8 *)byte_18004D749,
      v8,
      v9,
      &v29,
      (__int64 *)&ppv);
  }
  rclsid.Data1 = -455322399;
  *(_DWORD *)&rclsid.Data2 = 1148794293;
  *(_DWORD *)rclsid.Data4 = -2075124834;
  *(_DWORD *)&rclsid.Data4[4] = 1989909936;
  ppv = 0;
  v10 = CoCreateInstance_0(&rclsid, 0, *(_DWORD *)(a1 + 224), &winrt::impl::guid_v<ISessionManagerBroker>, &ppv);
  if ( v10 < 0 )
  {
LABEL_53:
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v10);
  }
  v11 = ppv;
  v31 = ppv;
  v34 = 0;
  v12 = (const OLECHAR *)(a1 + 72);
  if ( *((_QWORD *)v12 + 3) > 7u )
    v12 = *(const OLECHAR **)v12;
  v13 = (BSTR *)operator new(0x18u);
  v29 = (const wchar_t *)v13;
  if ( v13 )
  {
    *(_OWORD *)v13 = 0;
    v13[2] = 0;
    v13[1] = 0;
    *((_DWORD *)v13 + 4) = 1;
    v14 = SysAllocString(v12);
    *v13 = v14;
    if ( !v14 && v12 )
    {
      _com_issue_error(2147942414LL);
LABEL_52:
      _com_issue_error(2147942414LL);
      goto LABEL_53;
    }
  }
  else
  {
    v13 = 0;
  }
  v29 = (const wchar_t *)v13;
  if ( !v13 )
  {
    _com_issue_error(2147942414LL);
    goto LABEL_55;
  }
  if ( *a2 )
    v15 = *(const OLECHAR **)(*a2 + 16);
  else
    v15 = &Src;
  v16 = (BSTR *)operator new(0x18u);
  *(_QWORD *)&rclsid.Data1 = v16;
  if ( !v16 )
  {
    v16 = 0;
    goto LABEL_23;
  }
  *(_OWORD *)v16 = 0;
  v16[2] = 0;
  v16[1] = 0;
  *((_DWORD *)v16 + 4) = 1;
  v17 = SysAllocString(v15);
  *v16 = v17;
  if ( !v17 && v15 )
    goto LABEL_52;
LABEL_23:
  *(_QWORD *)&rclsid.Data1 = v16;
  if ( !v16 )
  {
LABEL_55:
    _com_issue_error(2147942414LL);
    JUMPOUT(0x180022DC8LL);
  }
  EventDescriptor = *a3;
  v18 = (*(__int64 (__fastcall **)(LPVOID, BSTR, BSTR, EVENT_DESCRIPTOR *, unsigned int *))(*(_QWORD *)v11 + 40LL))(
          v11,
          *v13,
          *v16,
          &EventDescriptor,
          &v34);
  if ( v18 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v18);
  }
  v19 = *a2;
  if ( v19 )
    v20 = *(const wchar_t **)(v19 + 16);
  else
    v20 = &Src;
  v22 = TraceLogger::Provider();
  if ( *(_DWORD *)v22 > 5u )
  {
    rclsid.Data1 = v34;
    v32 = *a3;
    p_rclsid = &rclsid;
    v46 = 4;
    v43 = &v32;
    v44 = 16;
    if ( v20 )
    {
      v23 = -1;
      do
        ++v23;
      while ( v20[v23] );
      v24 = 2 * v23 + 2;
    }
    else
    {
      v20 = &Src;
      v24 = 2;
    }
    v40 = v20;
    v41 = v24;
    v42 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = *((_QWORD *)v22 + 1);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v37 = byte_18004D6FD;
    v38 = 75;
    v39 = 1;
    LODWORD(v29) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*((_QWORD *)v22 + 4), &EventDescriptor, 0, 0, 5u, &UserData);
  }
  v25 = v34 != 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 4, 0xFFFFFFFF) == 1 )
  {
    if ( *v16 )
    {
      SysFreeString(*v16);
      *v16 = 0;
    }
    v26 = v16[1];
    if ( v26 )
    {
      operator delete(v26);
      v16[1] = 0;
    }
    operator delete(v16);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 4, 0xFFFFFFFF) == 1 )
  {
    if ( *v13 )
    {
      SysFreeString(*v13);
      *v13 = 0;
    }
    v27 = v13[1];
    if ( v27 )
    {
      operator delete(v27);
      v13[1] = 0;
    }
    operator delete(v13);
  }
  if ( ppv )
    winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(&v31, v21);
  return v25;
}

```

## disassembly

```asm
0x1800229c0  mov     [rsp-8+arg_18], rbx
0x1800229c5  push    rbp
0x1800229c6  push    rsi
0x1800229c7  push    rdi
0x1800229c8  push    r12
0x1800229ca  push    r13
0x1800229cc  push    r14
0x1800229ce  push    r15
0x1800229d0  lea     rbp, [rsp-27h]
0x1800229d5  sub     rsp, 0E0h
0x1800229dc  mov     rax, cs:__security_cookie
0x1800229e3  xor     rax, rsp
0x1800229e6  mov     [rbp+57h+var_40], rax
0x1800229ea  mov     r12, r8
0x1800229ed  mov     r14, rdx
0x1800229f0  mov     rdi, rcx
0x1800229f3  xor     r13d, r13d
0x1800229f6  mov     rbx, [rdx]
0x1800229f9  test    rbx, rbx
0x1800229fc  jz      short loc_180022A04
0x1800229fe  mov     rbx, [rbx+10h]
0x180022a02  jmp     short loc_180022A0B
0x180022a04  lea     rbx, Src
0x180022a0b  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x180022a10  cmp     dword ptr [rax], 5
0x180022a13  jbe     short loc_180022A4D
0x180022a15  movups  xmm0, xmmword ptr [r12]
0x180022a1a  movups  xmmword ptr [rbp+57h+EventDescriptor.Id], xmm0
0x180022a1e  lea     rcx, [rbp+57h+EventDescriptor]
0x180022a22  mov     [rbp+57h+var_B0], rcx
0x180022a26  mov     [rsp+110h+var_E0], rbx
0x180022a2b  lea     rcx, [rbp+57h+var_B0]
0x180022a2f  mov     [rsp+110h+UserData], rcx
0x180022a34  lea     rcx, [rsp+110h+var_E0]
0x180022a39  mov     [rsp+110h+ppv], rcx
0x180022a3e  lea     rdx, byte_18004D749
0x180022a45  mov     rcx, rax
0x180022a48  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByRef<16> const &)
0x180022a4d  mov     [rsp+110h+rclsid.Data1], 0E4DC54E1h
0x180022a55  mov     dword ptr [rbp+57h+rclsid.Data2], 447935B5h
0x180022a5c  mov     dword ptr [rbp+57h+rclsid.Data4], 84501B9Eh
0x180022a63  mov     dword ptr [rbp+57h+rclsid.Data4+4], 769B9DB0h
0x180022a6a  mov     [rbp+57h+var_B0], r13
0x180022a6e  lea     rax, [rbp+57h+var_B0]
0x180022a72  mov     [rsp+110h+ppv], rax; ppv
0x180022a77  lea     r9, ??$guid_v@UISessionManagerBroker@@@impl@winrt@@3Uguid@2@B; riid
0x180022a7e  mov     r8d, [rdi+0E0h]; dwClsContext
0x180022a85  xor     edx, edx; pUnkOuter
0x180022a87  lea     rcx, [rsp+110h+rclsid]; rclsid
0x180022a8c  call    CoCreateInstance_0
0x180022a91  test    eax, eax
0x180022a93  js      loc_180022DA8
0x180022a99  mov     r15, [rbp+57h+var_B0]
0x180022a9d  mov     [rbp+57h+var_C8], r15
0x180022aa1  mov     [rbp+57h+var_A8], r13d
0x180022aa5  add     rdi, 48h ; 'H'
0x180022aa9  cmp     qword ptr [rdi+18h], 7
0x180022aae  jbe     short loc_180022AB3
0x180022ab0  mov     rdi, [rdi]
0x180022ab3  mov     ecx, 18h; Size
0x180022ab8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022abd  mov     rbx, rax
0x180022ac0  mov     [rsp+110h+var_E0], rax
0x180022ac5  test    rax, rax
0x180022ac8  jz      short loc_180022AFD
0x180022aca  xorps   xmm0, xmm0
0x180022acd  xor     eax, eax
0x180022acf  movups  xmmword ptr [rbx], xmm0
0x180022ad2  mov     [rbx+10h], rax
0x180022ad6  mov     [rbx+8], r13
0x180022ada  mov     dword ptr [rbx+10h], 1
0x180022ae1  mov     rcx, rdi; psz
0x180022ae4  call    cs:__imp_SysAllocString
0x180022aea  mov     [rbx], rax
0x180022aed  test    rax, rax
0x180022af0  jnz     short loc_180022B00
0x180022af2  test    rdi, rdi
0x180022af5  jnz     loc_180022D92
0x180022afb  jmp     short loc_180022B00
0x180022afd  mov     rbx, r13
0x180022b00  mov     [rsp+110h+var_E0], rbx
0x180022b05  test    rbx, rbx
0x180022b08  jz      loc_180022DB3
0x180022b0e  mov     rsi, [r14]
0x180022b11  test    rsi, rsi
0x180022b14  jz      short loc_180022B1C
0x180022b16  mov     rsi, [rsi+10h]
0x180022b1a  jmp     short loc_180022B23
0x180022b1c  lea     rsi, Src
0x180022b23  mov     ecx, 18h; Size
0x180022b28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022b2d  mov     rdi, rax
0x180022b30  mov     qword ptr [rsp+110h+rclsid.Data1], rax
0x180022b35  test    rax, rax
0x180022b38  jz      short loc_180022B6D
0x180022b3a  xorps   xmm0, xmm0
0x180022b3d  xor     eax, eax
0x180022b3f  movups  xmmword ptr [rdi], xmm0
0x180022b42  mov     [rdi+10h], rax
0x180022b46  mov     [rdi+8], r13
0x180022b4a  mov     dword ptr [rdi+10h], 1
0x180022b51  mov     rcx, rsi; psz
0x180022b54  call    cs:__imp_SysAllocString
0x180022b5a  mov     [rdi], rax
0x180022b5d  test    rax, rax
0x180022b60  jnz     short loc_180022B70
0x180022b62  test    rsi, rsi
0x180022b65  jnz     loc_180022D9D
0x180022b6b  jmp     short loc_180022B70
0x180022b6d  mov     rdi, r13
0x180022b70  mov     qword ptr [rsp+110h+rclsid.Data1], rdi
0x180022b75  test    rdi, rdi
0x180022b78  jz      loc_180022DBE
0x180022b7e  movups  xmm0, xmmword ptr [r12]
0x180022b83  movaps  xmmword ptr [rbp+57h+EventDescriptor.Id], xmm0
0x180022b87  mov     rax, [r15]
0x180022b8a  lea     rcx, [rbp+57h+var_A8]
0x180022b8e  mov     [rsp+110h+ppv], rcx
0x180022b93  lea     r9, [rbp+57h+EventDescriptor]
0x180022b97  mov     r8, [rdi]
0x180022b9a  mov     rdx, [rbx]
0x180022b9d  mov     rcx, r15
0x180022ba0  mov     rax, [rax+28h]
0x180022ba4  call    cs:__guard_dispatch_icall_fptr
0x180022baa  test    eax, eax
0x180022bac  js      loc_180022D87
0x180022bb2  mov     r14, [r14]
0x180022bb5  test    r14, r14
0x180022bb8  jz      short loc_180022BC0
0x180022bba  mov     r14, [r14+10h]
0x180022bbe  jmp     short loc_180022BC7
0x180022bc0  lea     r14, Src
0x180022bc7  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x180022bcc  mov     r10, rax
0x180022bcf  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180022bd6  cmp     dword ptr [rax], 5
0x180022bd9  jbe     loc_180022CCC
0x180022bdf  mov     ecx, [rbp+57h+var_A8]
0x180022be2  mov     [rsp+110h+rclsid.Data1], ecx
0x180022be6  movups  xmm0, xmmword ptr [r12]
0x180022beb  movups  [rbp+57h+var_C0], xmm0
0x180022bef  lea     rax, [rsp+110h+rclsid]
0x180022bf4  mov     [rbp+57h+var_50], rax
0x180022bf8  mov     [rbp+57h+var_48], 4
0x180022c00  lea     rax, [rbp+57h+var_C0]
0x180022c04  mov     [rbp+57h+var_60], rax
0x180022c08  mov     [rbp+57h+var_58], 10h
0x180022c10  test    r14, r14
0x180022c13  jz      short loc_180022C35
0x180022c15  mov     rax, rsi
0x180022c18  nop     dword ptr [rax+rax+00000000h]
0x180022c20  lea     rax, [rax+1]
0x180022c24  cmp     word ptr [r14+rax*2], 0
0x180022c2a  jnz     short loc_180022C20
0x180022c2c  lea     eax, ds:2[rax*2]
0x180022c33  jmp     short loc_180022C41
0x180022c35  lea     r14, Src
0x180022c3c  mov     eax, 2
0x180022c41  mov     [rbp+57h+var_70], r14
0x180022c45  mov     [rbp+57h+var_68], eax
0x180022c48  mov     [rbp+57h+var_64], r13d
0x180022c4c  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180022c53  movzx   eax, cs:word_18004D6F3
0x180022c5a  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180022c5d  mov     [rbp+57h+EventDescriptor.Keyword], r13
0x180022c61  mov     rax, [r10+8]
0x180022c65  mov     [rbp+57h+var_90.Ptr], rax
0x180022c69  movzx   eax, word ptr [rax]
0x180022c6c  mov     [rbp+57h+var_90.Size], eax
0x180022c6f  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x180022c76  lea     rax, byte_18004D6FD
0x180022c7d  mov     [rbp+57h+var_80], rax
0x180022c81  mov     [rbp+57h+var_78], 4Bh ; 'K'
0x180022c88  mov     [rbp+57h+var_74], 1
0x180022c8f  lea     rax, _TraceLoggingMetadataEnd
0x180022c96  lea     rcx, _TraceLoggingMetadata
0x180022c9d  sub     eax, ecx
0x180022c9f  mov     dword ptr [rsp+110h+var_E0], eax
0x180022ca3  mov     eax, dword ptr [rsp+110h+var_E0]
0x180022ca7  lea     rax, [rbp+57h+var_90]
0x180022cab  mov     [rsp+110h+UserData], rax; UserData
0x180022cb0  mov     dword ptr [rsp+110h+ppv], 5; UserDataCount
0x180022cb8  xor     r9d, r9d; RelatedActivityId
0x180022cbb  xor     r8d, r8d; ActivityId
0x180022cbe  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180022cc2  mov     rcx, [r10+20h]; RegHandle
0x180022cc6  call    cs:__imp_EventWriteTransfer
0x180022ccc  cmp     [rbp+57h+var_A8], 0
0x180022cd0  setnz   r14b
0x180022cd4  mov     eax, esi
0x180022cd6  lock xadd [rdi+10h], eax
0x180022cdb  cmp     eax, 1
0x180022cde  jnz     short loc_180022D11
0x180022ce0  mov     rcx, [rdi]; bstrString
0x180022ce3  test    rcx, rcx
0x180022ce6  jz      short loc_180022CF1
0x180022ce8  call    cs:__imp_SysFreeString
0x180022cee  mov     [rdi], r13
0x180022cf1  mov     rcx, [rdi+8]; void *
0x180022cf5  test    rcx, rcx
0x180022cf8  jz      short loc_180022D03
0x180022cfa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022cff  mov     [rdi+8], r13
0x180022d03  mov     edx, 18h; unsigned __int64
0x180022d08  mov     rcx, rdi; void *
0x180022d0b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022d10  nop
0x180022d11  lock xadd [rbx+10h], esi
0x180022d16  cmp     esi, 1
0x180022d19  jnz     short loc_180022D4C
0x180022d1b  mov     rcx, [rbx]; bstrString
0x180022d1e  test    rcx, rcx
0x180022d21  jz      short loc_180022D2C
0x180022d23  call    cs:__imp_SysFreeString
0x180022d29  mov     [rbx], r13
0x180022d2c  mov     rcx, [rbx+8]; void *
0x180022d30  test    rcx, rcx
0x180022d33  jz      short loc_180022D3E
0x180022d35  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022d3a  mov     [rbx+8], r13
0x180022d3e  mov     edx, 18h; unsigned __int64
0x180022d43  mov     rcx, rbx; void *
0x180022d46  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022d4b  nop
0x180022d4c  cmp     [rbp+57h+var_B0], 0
0x180022d51  jz      short loc_180022D5C
0x180022d53  lea     rcx, [rbp+57h+var_C8]
0x180022d57  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerBroker@@@winrt@@AEAAXXZ; winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(void)
0x180022d5c  movzx   eax, r14b
0x180022d60  mov     rcx, [rbp+57h+var_40]
0x180022d64  xor     rcx, rsp; StackCookie
0x180022d67  call    __security_check_cookie
0x180022d6c  mov     rbx, [rsp+110h+arg_18]
0x180022d74  add     rsp, 0E0h
0x180022d7b  pop     r15
0x180022d7d  pop     r14
0x180022d7f  pop     r13
0x180022d81  pop     r12
0x180022d83  pop     rdi
0x180022d84  pop     rsi
0x180022d85  pop     rbp
0x180022d86  retn
0x180022d87  lfence
0x180022d8a  mov     ecx, eax
0x180022d8c  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180022d92  mov     ecx, 8007000Eh; int
0x180022d97  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180022d9c  nop
0x180022d9d  mov     ecx, 8007000Eh; int
0x180022da2  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180022da7  nop
0x180022da8  lfence
0x180022dab  mov     ecx, eax
0x180022dad  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180022db3  mov     ecx, 8007000Eh; int
0x180022db8  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180022dbd  nop
0x180022dbe  mov     ecx, 8007000Eh; int
0x180022dc3  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
