# HNS::Service::Network::InternalNetwork::AssignIPToInternalNic(void)

- ea: `0x18012422c`
- end: `0x1801243cb`
- name: `?AssignIPToInternalNic@InternalNetwork@Network@Service@HNS@@QEAAXXZ`
- size: `415`
- prototype: `void __fastcall(HNS::Service::Network::InternalNetwork *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801252f0`
- `0x180129c7c`

## callees

- `0x1800759d8`
- `0x180075aac`
- `0x180077db0`
- `0x18007cbc8`
- `0x18008b50c`
- `0x180108eac`
- `0x1801091c0`
- `0x180123f98`
- `0x18012422c`
- `0x180126564`
- `0x18019dbb4`

## import_xrefs

- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18012434d`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18012434d`
- `IPHLPAPI!InternalDeleteUnicastIpAddressEntry` at `0x1801242f8`
- `IPHLPAPI!InternalDeleteUnicastIpAddressEntry` at `0x1801242f8`
- `IPHLPAPI!InternalGetUnicastIpAddressTable` at `0x1801242bc`
- `IPHLPAPI!InternalGetUnicastIpAddressTable` at `0x1801242bc`
- `IPHLPAPI!FreeMibTable` at `0x18012431c`
- `IPHLPAPI!FreeMibTable` at `0x18012431c`

## string_xrefs

- `0x1801243a4`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`
- `0x1801243b9`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall HNS::Service::Network::InternalNetwork::AssignIPToInternalNic(
        HNS::Service::Network::InternalNetwork *this)
{
  __int64 v2; // rbx
  unsigned int v3; // ebx
  __int64 v4; // r15
  unsigned int *v5; // r14
  unsigned int UnicastIpAddressTable; // eax
  _DWORD *v7; // rbx
  __int64 v8; // rsi
  unsigned int v9; // eax
  __int64 FirstIpv4Subnet; // rax
  __int64 FirstIpv6Subnet; // rax
  unsigned int v12[2]; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v13[24]; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  char v15; // [rsp+70h] [rbp+30h] BYREF
  PVOID Memory; // [rsp+78h] [rbp+38h] BYREF

  v2 = *((_QWORD *)this + 294);
  if ( (unsigned int)HNSObject::PropertyExists(*(_QWORD *)(v2 + 2296), v2 + 2240) )
    v3 = 0;
  else
    v3 = Property<unsigned long>::get(v2 + 2240);
  v4 = *((_QWORD *)this + 294);
  HNSTraceProvider::TraceEnter("IPHelper::ResetIPAddress", 0x2AAu);
  v12[0] = 0;
  v12[1] = 1;
  IPHelper::SetCurrentThreadCompartmentId(&v15, v3);
  v5 = v12;
  do
  {
    Memory = 0;
    UnicastIpAddressTable = InternalGetUnicastIpAddressTable(*v5, 2, &Memory);
    if ( UnicastIpAddressTable )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2B4,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\iphelper.cpp",
        (const char *)UnicastIpAddressTable,
        v12[0]);
    v7 = Memory;
    v8 = 0;
    if ( *(_DWORD *)Memory )
    {
      do
      {
        if ( *(_QWORD *)&v7[20 * v8 + 10] == *(_QWORD *)(v4 + 3136) )
        {
          v9 = InternalDeleteUnicastIpAddressEntry(*v5, &v7[20 * v8 + 2]);
          if ( v9 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x2BB,
              (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\iphelper.cpp",
              (const char *)v9,
              v12[0]);
        }
        v8 = (unsigned int)(v8 + 1);
      }
      while ( (unsigned int)v8 < *v7 );
      v7 = Memory;
    }
    if ( v7 )
      FreeMibTable(v7);
    ++v5;
  }
  while ( v5 != (unsigned int *)v13 );
  HNSTraceProvider::TraceSuccess("IPHelper::ResetIPAddress", 0x2BFu);
  if ( v15 )
    SetCurrentThreadCompartmentId(0);
  FirstIpv4Subnet = HNS::Service::Network::BaseNetwork::GetFirstIpv4Subnet(this, v13);
  HNS::Service::Network::InternalNetwork::AssignIPToInternalNic(this, FirstIpv4Subnet);
  if ( HNS::Service::Network::BaseNetwork::SupportsIpv6(this) )
  {
    FirstIpv6Subnet = HNS::Service::Network::BaseNetwork::GetFirstIpv6Subnet(this, v13);
    HNS::Service::Network::InternalNetwork::AssignIPToInternalNic(this, FirstIpv6Subnet);
  }
}

```

## disassembly

```asm
0x18012422c  mov     [rsp-28h+arg_10], rbx
0x180124231  push    rbp
0x180124232  push    rsi
0x180124233  push    rdi
0x180124234  push    r14
0x180124236  push    r15
0x180124238  mov     rbp, rsp
0x18012423b  sub     rsp, 40h
0x18012423f  mov     rdi, rcx
0x180124242  mov     rbx, [rcx+930h]
0x180124249  lea     rdx, [rbx+8C0h]
0x180124250  mov     rcx, [rbx+8F8h]
0x180124257  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x18012425c  test    eax, eax
0x18012425e  jnz     short loc_180124270
0x180124260  lea     rcx, [rbx+8C0h]
0x180124267  call    ?get@?$Property@K@@QEBA?BKXZ; Property<ulong>::get(void)
0x18012426c  mov     ebx, eax
0x18012426e  jmp     short loc_180124272
0x180124270  xor     ebx, ebx
0x180124272  mov     r15, [rdi+930h]
0x180124279  mov     edx, 2AAh; unsigned int
0x18012427e  lea     rcx, aIphelperReseti; "IPHelper::ResetIPAddress"
0x180124285  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x18012428a  mov     [rbp+var_20], 0
0x180124291  mov     [rbp+var_1C], 1
0x180124298  mov     edx, ebx
0x18012429a  lea     rcx, [rbp+arg_0]
0x18012429e  call    ?SetCurrentThreadCompartmentId@IPHelper@@SA?AV?$unique_call@P6AXXZ$1?ClearCompartment@IPHelper@@SAXXZ$00@wil@@I@Z; IPHelper::SetCurrentThreadCompartmentId(uint)
0x1801242a3  nop
0x1801242a4  lea     r14, [rbp+var_20]
0x1801242a8  mov     [rbp+Memory], 0
0x1801242b0  mov     edx, 2
0x1801242b5  lea     r8, [rbp+Memory]
0x1801242b9  mov     ecx, [r14]
0x1801242bc  call    cs:__imp_InternalGetUnicastIpAddressTable
0x1801242c2  mov     rcx, [rbp+28h]; this
0x1801242c6  test    eax, eax
0x1801242c8  jnz     loc_1801243B6
0x1801242ce  mov     rbx, [rbp+Memory]
0x1801242d2  xor     esi, esi
0x1801242d4  cmp     [rbx], esi
0x1801242d6  jbe     short loc_180124314
0x1801242d8  lea     rcx, [rsi+rsi*4]
0x1801242dc  shl     rcx, 4
0x1801242e0  mov     rax, [r15+0C40h]
0x1801242e7  cmp     [rcx+rbx+28h], rax
0x1801242ec  jnz     short loc_18012430A
0x1801242ee  lea     rdx, [rbx+8]
0x1801242f2  add     rdx, rcx
0x1801242f5  mov     ecx, [r14]
0x1801242f8  call    cs:__imp_InternalDeleteUnicastIpAddressEntry
0x1801242fe  mov     rcx, [rbp+28h]; this
0x180124302  test    eax, eax
0x180124304  jnz     loc_1801243A1
0x18012430a  inc     esi
0x18012430c  cmp     esi, [rbx]
0x18012430e  jb      short loc_1801242D8
0x180124310  mov     rbx, [rbp+Memory]
0x180124314  test    rbx, rbx
0x180124317  jz      short loc_180124322
0x180124319  mov     rcx, rbx; Memory
0x18012431c  call    cs:__imp_FreeMibTable
0x180124322  add     r14, 4
0x180124326  lea     rax, [rbp+var_18]
0x18012432a  cmp     r14, rax
0x18012432d  jnz     loc_1801242A8
0x180124333  mov     edx, 2BFh; unsigned int
0x180124338  lea     rcx, aIphelperReseti; "IPHelper::ResetIPAddress"
0x18012433f  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x180124344  nop
0x180124345  cmp     [rbp+arg_0], 0
0x180124349  jz      short loc_180124353
0x18012434b  xor     ecx, ecx; CompartmentId
0x18012434d  call    cs:__imp_SetCurrentThreadCompartmentId
0x180124353  lea     rdx, [rbp+var_18]
0x180124357  mov     rcx, rdi
0x18012435a  call    ?GetFirstIpv4Subnet@BaseNetwork@Network@Service@HNS@@QEBA?AV?$shared_ptr@VSubnet@Network@Service@HNS@@@std@@XZ; HNS::Service::Network::BaseNetwork::GetFirstIpv4Subnet(void)
0x18012435f  mov     rdx, rax
0x180124362  mov     rcx, rdi
0x180124365  call    ?AssignIPToInternalNic@InternalNetwork@Network@Service@HNS@@IEAAXV?$shared_ptr@VSubnet@Network@Service@HNS@@@std@@@Z; HNS::Service::Network::InternalNetwork::AssignIPToInternalNic(std::shared_ptr<HNS::Service::Network::Subnet>)
0x18012436a  mov     rcx, rdi; this
0x18012436d  call    ?SupportsIpv6@BaseNetwork@Network@Service@HNS@@QEBA_NXZ; HNS::Service::Network::BaseNetwork::SupportsIpv6(void)
0x180124372  test    al, al
0x180124374  jz      short loc_18012438D
0x180124376  lea     rdx, [rbp+var_18]
0x18012437a  mov     rcx, rdi
0x18012437d  call    ?GetFirstIpv6Subnet@BaseNetwork@Network@Service@HNS@@QEBA?AV?$shared_ptr@VSubnet@Network@Service@HNS@@@std@@XZ; HNS::Service::Network::BaseNetwork::GetFirstIpv6Subnet(void)
0x180124382  mov     rdx, rax
0x180124385  mov     rcx, rdi
0x180124388  call    ?AssignIPToInternalNic@InternalNetwork@Network@Service@HNS@@IEAAXV?$shared_ptr@VSubnet@Network@Service@HNS@@@std@@@Z; HNS::Service::Network::InternalNetwork::AssignIPToInternalNic(std::shared_ptr<HNS::Service::Network::Subnet>)
0x18012438d  mov     rbx, [rsp+40h+arg_10]
0x180124395  add     rsp, 40h
0x180124399  pop     r15
0x18012439b  pop     r14
0x18012439d  pop     rdi
0x18012439e  pop     rsi
0x18012439f  pop     rbp
0x1801243a0  retn
0x1801243a1  mov     r9d, eax; char *
0x1801243a4  lea     r8, aOnecoreVmDvNet_158; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x1801243ab  mov     edx, 2BBh; void *
0x1801243b0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801243b6  mov     r9d, eax; char *
0x1801243b9  lea     r8, aOnecoreVmDvNet_158; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x1801243c0  mov     edx, 2B4h; void *
0x1801243c5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
