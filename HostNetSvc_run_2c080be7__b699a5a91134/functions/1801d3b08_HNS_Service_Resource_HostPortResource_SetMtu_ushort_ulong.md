# HNS::Service::Resource::HostPortResource::SetMtu(ushort,ulong)

- ea: `0x1801d3b08`
- end: `0x1801d3dcd`
- name: `?SetMtu@HostPortResource@Resource@Service@HNS@@QEAAXGK@Z`
- size: `709`
- prototype: `void __fastcall(HNS::Service::Resource::HostPortResource *__hidden this, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180157ae0`

## callees

- `0x180001b68`
- `0x18005f0c0`
- `0x18005ffc4`
- `0x1800666b4`
- `0x1800677fc`
- `0x1800759d8`
- `0x180075aac`
- `0x180077db0`
- `0x180080804`
- `0x18008b50c`
- `0x1800b65d8`
- `0x18019dbb4`
- `0x1801d2b30`
- `0x1801d3b08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801d3d77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801d3d77`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801d3b4e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801d3b4e`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1801d3d2c`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1801d3d2c`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1801d3baf`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1801d3baf`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x1801d3c88`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x1801d3c88`
- `IPHLPAPI!GetIpInterfaceEntry` at `0x1801d3ca7`
- `IPHLPAPI!GetIpInterfaceEntry` at `0x1801d3ca7`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x1801d3ce4`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x1801d3ce4`

## string_xrefs

- `0x1801d3cc3`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`
- `0x1801d3d00`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`
- `0x1801d3b3b`: `HNS::Service::Resource::HostPortResource::SetMtu`
- `0x1801d3d82`: `HNS::Service::Resource::HostPortResource::SetMtu`
- `0x1801d3db8`: `onecore\vm\dv\net\hns\service\resourcemgr\resources\src\hostportresource.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall HNS::Service::Resource::HostPortResource::SetMtu(RTL_SRWLOCK *this, __int64 a2, ULONG a3)
{
  GUID v5; // xmm0
  __int64 v6; // rbx
  unsigned int v7; // ebx
  unsigned int IpInterfaceEntry; // eax
  unsigned int v9; // eax
  int v10; // [rsp+20h] [rbp-E0h]
  char *v11; // [rsp+28h] [rbp-D8h]
  char *v12; // [rsp+28h] [rbp-D8h]
  _BYTE v13[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int Mtu; // [rsp+34h] [rbp-CCh] BYREF
  NET_LUID InterfaceLuid; // [rsp+38h] [rbp-C8h] BYREF
  RTL_SRWLOCK *v16; // [rsp+40h] [rbp-C0h]
  GUID v17; // [rsp+50h] [rbp-B0h] BYREF
  GUID InterfaceGuid; // [rsp+60h] [rbp-A0h] BYREF
  struct _MIB_IPINTERFACE_ROW Row; // [rsp+70h] [rbp-90h] BYREF
  char v20[32]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int *v21; // [rsp+140h] [rbp+40h]
  __int64 v22; // [rsp+148h] [rbp+48h]
  GUID *p_InterfaceGuid; // [rsp+150h] [rbp+50h]
  __int64 v24; // [rsp+158h] [rbp+58h]
  GUID *v25; // [rsp+160h] [rbp+60h]
  __int64 v26; // [rsp+168h] [rbp+68h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  HNSTraceProvider::TraceEnter("HNS::Service::Resource::HostPortResource::SetMtu", 0x22Fu);
  AcquireSRWLockExclusive(this + 5);
  v16 = this + 5;
  InterfaceLuid.Value = 0;
  if ( (unsigned int)HNSObject::PropertyExists(this[319].Ptr, &this[312]) )
  {
    v5 = GUID_NULL;
  }
  else
  {
    HNSObject::Get<_GUID>(this[319].Ptr, &v17, &this[312]);
    v5 = v17;
  }
  InterfaceGuid = v5;
  if ( ConvertInterfaceGuidToLuid(&InterfaceGuid, &InterfaceLuid) < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x237,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\resourcemgr\\resources\\src\\hostportresource.cpp",
      (const char *)0x803B0006LL,
      v10);
  v6 = qword_18039C168;
  if ( *(_DWORD *)qword_18039C168 > 4u )
  {
    HNSObject::Get<_GUID>(this[128].Ptr, &v17, &this[121]);
    Mtu = a3;
    v25 = &v17;
    v26 = 16;
    p_InterfaceGuid = &InterfaceGuid;
    v24 = 16;
    v21 = &Mtu;
    v22 = 4;
    tlgWriteTransfer_EventWriteTransfer(v6, qword_18033FF38, 0, 0, 5, v20);
  }
  v7 = Property<unsigned long>::get(&this[280]);
  HNSTraceProvider::TraceEnter("IPHelper::SetMtu", 0x215u);
  memset_0(&Row, 0, sizeof(Row));
  IPHelper::SetCurrentThreadCompartmentId(v13, v7);
  InitializeIpInterfaceEntry(&Row);
  Row.InterfaceLuid = InterfaceLuid;
  Row.Family = 2;
  IpInterfaceEntry = GetIpInterfaceEntry(&Row);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x223,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\iphelper.cpp",
    (const char *)IpInterfaceEntry,
    (unsigned int)"Could not get IP Interface Entry",
    v11);
  Row.NlMtu = a3;
  Row.SitePrefixLength = 0;
  v9 = SetIpInterfaceEntry(&Row);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x228,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\iphelper.cpp",
    (const char *)v9,
    (unsigned int)"Could not set interface MTU",
    v12);
  HNSTraceProvider::TraceSuccess("IPHelper::SetMtu", 0x22Au);
  if ( v13[0] )
    SetCurrentThreadCompartmentId(0);
  Mtu = HNS::Service::Resource::HostPortResource::GetMtu((HNS::Service::Resource::HostPortResource *)this);
  v17 = *(GUID *)&this[372].Ptr;
  HNSObject::Set<unsigned long>(this[375].Ptr, &this[368], &Mtu, LODWORD(this[374].Ptr));
  if ( this != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(this + 5);
  HNSTraceProvider::TraceSuccess("HNS::Service::Resource::HostPortResource::SetMtu", 0x243u);
}

```

## disassembly

```asm
0x1801d3b08  mov     [rsp-8+arg_8], rbx
0x1801d3b0d  mov     [rsp-8+arg_18], rsi
0x1801d3b12  push    rbp
0x1801d3b13  push    rdi
0x1801d3b14  push    r14
0x1801d3b16  lea     rbp, [rsp-80h]
0x1801d3b1b  sub     rsp, 180h
0x1801d3b22  mov     rax, cs:__security_cookie
0x1801d3b29  xor     rax, rsp
0x1801d3b2c  mov     [rbp+90h+var_20], rax
0x1801d3b30  mov     r14d, r8d
0x1801d3b33  mov     rdi, rcx
0x1801d3b36  mov     edx, 22Fh; unsigned int
0x1801d3b3b  lea     rcx, aHnsServiceReso_25; "HNS::Service::Resource::HostPortResourc"...
0x1801d3b42  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1801d3b47  lea     rsi, [rdi+28h]
0x1801d3b4b  mov     rcx, rsi; SRWLock
0x1801d3b4e  call    cs:__imp_AcquireSRWLockExclusive
0x1801d3b54  mov     [rsp+190h+var_150], rsi
0x1801d3b59  mov     qword ptr [rsp+190h+InterfaceLuid], 0
0x1801d3b62  lea     rbx, [rdi+9C0h]
0x1801d3b69  mov     rdx, rbx
0x1801d3b6c  mov     rcx, [rbx+38h]
0x1801d3b70  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x1801d3b75  test    eax, eax
0x1801d3b77  jnz     short loc_1801D3B91
0x1801d3b79  mov     r8, rbx
0x1801d3b7c  lea     rdx, [rsp+190h+var_140]
0x1801d3b81  mov     rcx, [rbx+38h]
0x1801d3b85  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801d3b8a  movaps  xmm0, [rsp+190h+var_140]
0x1801d3b8f  jmp     short loc_1801D3B98
0x1801d3b91  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801d3b98  movdqa  xmmword ptr [rsp+190h+InterfaceGuid.Data1], xmm0
0x1801d3b9e  mov     rbx, [rbp+98h]
0x1801d3ba5  lea     rdx, [rsp+190h+InterfaceLuid]; InterfaceLuid
0x1801d3baa  lea     rcx, [rsp+190h+InterfaceGuid]; InterfaceGuid
0x1801d3baf  call    cs:__imp_ConvertInterfaceGuidToLuid
0x1801d3bb5  shr     eax, 1Fh
0x1801d3bb8  test    al, al
0x1801d3bba  jnz     loc_1801D3DB2
0x1801d3bc0  mov     rbx, cs:qword_18039C168
0x1801d3bc7  mov     eax, [rbx]
0x1801d3bc9  cmp     eax, 4
0x1801d3bcc  jbe     short loc_1801D3C45
0x1801d3bce  lea     rcx, [rdi+3C8h]
0x1801d3bd5  mov     r8, rcx
0x1801d3bd8  lea     rdx, [rsp+190h+var_140]
0x1801d3bdd  mov     rcx, [rcx+38h]
0x1801d3be1  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801d3be6  nop
0x1801d3be7  mov     [rsp+190h+var_15C], r14d
0x1801d3bec  lea     rax, [rsp+190h+var_140]
0x1801d3bf1  mov     [rbp+90h+var_30], rax
0x1801d3bf5  mov     [rbp+90h+var_28], 10h
0x1801d3bfd  lea     rax, [rsp+190h+InterfaceGuid]
0x1801d3c02  mov     [rbp+90h+var_40], rax
0x1801d3c06  mov     [rbp+90h+var_38], 10h
0x1801d3c0e  lea     rax, [rsp+190h+var_15C]
0x1801d3c13  mov     [rbp+90h+var_50], rax
0x1801d3c17  mov     [rbp+90h+var_48], 4
0x1801d3c1f  lea     rax, [rbp+90h+var_70]
0x1801d3c23  mov     [rsp+190h+var_168], rax; char *
0x1801d3c28  mov     [rsp+190h+var_170], 5
0x1801d3c30  xor     r9d, r9d
0x1801d3c33  xor     r8d, r8d
0x1801d3c36  lea     rdx, qword_18033FF38
0x1801d3c3d  mov     rcx, rbx
0x1801d3c40  call    _tlgWriteTransfer_EventWriteTransfer
0x1801d3c45  lea     rcx, [rdi+8C0h]
0x1801d3c4c  call    ?get@?$Property@K@@QEBA?BKXZ; Property<ulong>::get(void)
0x1801d3c51  mov     ebx, eax
0x1801d3c53  mov     edx, 215h; unsigned int
0x1801d3c58  lea     rcx, aIphelperSetmtu; "IPHelper::SetMtu"
0x1801d3c5f  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1801d3c64  xor     edx, edx; Val
0x1801d3c66  mov     r8d, 0A8h; Size
0x1801d3c6c  lea     rcx, [rsp+190h+Row]; void *
0x1801d3c71  call    memset_0
0x1801d3c76  mov     edx, ebx
0x1801d3c78  lea     rcx, [rsp+190h+var_160]
0x1801d3c7d  call    ?SetCurrentThreadCompartmentId@IPHelper@@SA?AV?$unique_call@P6AXXZ$1?ClearCompartment@IPHelper@@SAXXZ$00@wil@@I@Z; IPHelper::SetCurrentThreadCompartmentId(uint)
0x1801d3c82  nop
0x1801d3c83  lea     rcx, [rsp+190h+Row]; Row
0x1801d3c88  call    cs:__imp_InitializeIpInterfaceEntry
0x1801d3c8e  mov     rax, qword ptr [rsp+190h+InterfaceLuid]
0x1801d3c93  mov     qword ptr [rsp+190h+Row.InterfaceLuid], rax
0x1801d3c98  mov     eax, 2
0x1801d3c9d  mov     [rsp+190h+Row.Family], ax
0x1801d3ca2  lea     rcx, [rsp+190h+Row]; Row
0x1801d3ca7  call    cs:__imp_GetIpInterfaceEntry
0x1801d3cad  mov     r9d, eax; char *
0x1801d3cb0  mov     rcx, [rbp+98h]; this
0x1801d3cb7  lea     rax, aCouldNotGetIpI; "Could not get IP Interface Entry"
0x1801d3cbe  mov     qword ptr [rsp+190h+var_170], rax; unsigned int
0x1801d3cc3  lea     r8, aOnecoreVmDvNet_158; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x1801d3cca  mov     edx, 223h; void *
0x1801d3ccf  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1801d3cd4  mov     [rbp+90h+Row.NlMtu], r14d
0x1801d3cd8  mov     [rbp+90h+Row.SitePrefixLength], 0
0x1801d3cdf  lea     rcx, [rsp+190h+Row]; Row
0x1801d3ce4  call    cs:__imp_SetIpInterfaceEntry
0x1801d3cea  mov     r9d, eax; char *
0x1801d3ced  mov     rcx, [rbp+98h]; this
0x1801d3cf4  lea     rax, aCouldNotSetInt; "Could not set interface MTU"
0x1801d3cfb  mov     qword ptr [rsp+190h+var_170], rax; unsigned int
0x1801d3d00  lea     r8, aOnecoreVmDvNet_158; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x1801d3d07  mov     edx, 228h; void *
0x1801d3d0c  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1801d3d11  mov     edx, 22Ah; unsigned int
0x1801d3d16  lea     rcx, aIphelperSetmtu; "IPHelper::SetMtu"
0x1801d3d1d  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x1801d3d22  nop
0x1801d3d23  cmp     [rsp+190h+var_160], 0
0x1801d3d28  jz      short loc_1801D3D32
0x1801d3d2a  xor     ecx, ecx; CompartmentId
0x1801d3d2c  call    cs:__imp_SetCurrentThreadCompartmentId
0x1801d3d32  mov     rcx, rdi; this
0x1801d3d35  call    ?GetMtu@HostPortResource@Resource@Service@HNS@@AEAAKXZ; HNS::Service::Resource::HostPortResource::GetMtu(void)
0x1801d3d3a  mov     [rsp+190h+var_15C], eax
0x1801d3d3e  lea     rcx, [rdi+0B80h]
0x1801d3d45  movups  xmm0, xmmword ptr [rcx+20h]
0x1801d3d49  movdqu  [rsp+190h+var_140], xmm0
0x1801d3d4f  lea     rax, [rsp+190h+var_140]
0x1801d3d54  mov     qword ptr [rsp+190h+var_170], rax
0x1801d3d59  mov     r9d, [rcx+30h]
0x1801d3d5d  lea     r8, [rsp+190h+var_15C]
0x1801d3d62  mov     rdx, rcx
0x1801d3d65  mov     rcx, [rcx+38h]
0x1801d3d69  call    ??$Set@K@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBKKU_GUID@@@Z; HNSObject::Set<ulong>(std::wstring const &,ulong const &,ulong,_GUID)
0x1801d3d6e  nop
0x1801d3d6f  test    rsi, rsi
0x1801d3d72  jz      short loc_1801D3D7D
0x1801d3d74  mov     rcx, rsi; SRWLock
0x1801d3d77  call    cs:__imp_ReleaseSRWLockExclusive
0x1801d3d7d  mov     edx, 243h; unsigned int
0x1801d3d82  lea     rcx, aHnsServiceReso_25; "HNS::Service::Resource::HostPortResourc"...
0x1801d3d89  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x1801d3d8e  mov     rcx, [rbp+90h+var_20]
0x1801d3d92  xor     rcx, rsp; StackCookie
0x1801d3d95  call    __security_check_cookie
0x1801d3d9a  lea     r11, [rsp+190h+var_10]
0x1801d3da2  mov     rbx, [r11+28h]
0x1801d3da6  mov     rsi, [r11+38h]
0x1801d3daa  mov     rsp, r11
0x1801d3dad  pop     r14
0x1801d3daf  pop     rdi
0x1801d3db0  pop     rbp
0x1801d3db1  retn
0x1801d3db2  mov     r9d, 803B0006h; char *
0x1801d3db8  lea     r8, aOnecoreVmDvNet_137; "onecore\\vm\\dv\\net\\hns\\service\\res"...
0x1801d3dbf  mov     edx, 237h; void *
0x1801d3dc4  mov     rcx, rbx; this
0x1801d3dc7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
