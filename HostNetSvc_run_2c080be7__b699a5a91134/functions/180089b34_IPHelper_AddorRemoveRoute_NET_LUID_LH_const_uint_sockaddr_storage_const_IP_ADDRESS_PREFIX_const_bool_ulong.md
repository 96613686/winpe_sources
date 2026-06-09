# IPHelper::AddorRemoveRoute(_NET_LUID_LH const &,uint,sockaddr_storage const &,_IP_ADDRESS_PREFIX const &,bool,ulong)

- ea: `0x180089b34`
- end: `0x180089d1b`
- name: `?AddorRemoveRoute@IPHelper@@SA_NAEBT_NET_LUID_LH@@IAEBUsockaddr_storage@@AEBU_IP_ADDRESS_PREFIX@@_NK@Z`
- size: `487`
- prototype: `bool __fastcall(const union _NET_LUID_LH *, unsigned int, const struct sockaddr_storage *, const struct _IP_ADDRESS_PREFIX *, bool, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18024d2e4`

## callees

- `0x18005f0c0`
- `0x18005ff2a`
- `0x18005ffc4`
- `0x180061240`
- `0x1800666b4`
- `0x1800759d8`
- `0x180075aac`
- `0x18007cbc8`
- `0x180089b34`
- `0x18008b50c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180089bfa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180089bfa`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180089c4a`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180089cc0`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180089c4a`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180089cc0`
- `IPHLPAPI!InitializeIpForwardEntry` at `0x180089b83`
- `IPHLPAPI!InitializeIpForwardEntry` at `0x180089b83`
- `IPHLPAPI!InternalCreateIpForwardEntry2` at `0x180089c23`
- `IPHLPAPI!InternalCreateIpForwardEntry2` at `0x180089c23`
- `IPHLPAPI!InternalDeleteIpForwardEntry2` at `0x180089c7b`
- `IPHLPAPI!InternalDeleteIpForwardEntry2` at `0x180089c7b`

## string_xrefs

- `0x180089cd8`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`
- `0x180089ced`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`
- `0x180089d09`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`
- `0x180089b64`: `IPHelper::AddorRemoveRoute`
- `0x180089c35`: `IPHelper::AddorRemoveRoute`
- `0x180089cab`: `IPHelper::AddorRemoveRoute`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall IPHelper::AddorRemoveRoute(
        const union _NET_LUID_LH *a1,
        __int64 a2,
        const struct sockaddr_storage *a3,
        const struct _IP_ADDRESS_PREFIX *a4,
        bool a5)
{
  unsigned int v8; // eax
  signed int v10; // eax
  bool v11; // sf
  unsigned int v12; // eax
  unsigned int v13[4]; // [rsp+20h] [rbp-59h] BYREF
  _MIB_IPFORWARD_ROW2 Row; // [rsp+30h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]

  HNSTraceProvider::TraceEnter("IPHelper::AddorRemoveRoute", 0x5C4u);
  memset_0(&Row, 0, sizeof(Row));
  InitializeIpForwardEntry(&Row);
  Row.InterfaceLuid = (NET_LUID)a1->Value;
  Row.Protocol = RouteProtocolNetMgmt;
  Row.DestinationPrefix = *a4;
  Row.Metric = 100;
  if ( a3->ss_family == 2 )
  {
    if ( a3 )
    {
      Row.NextHop.Ipv4 = *(SOCKADDR_IN *)&a3->ss_family;
      goto LABEL_10;
    }
    Row.NextHop.Ipv4 = 0;
  }
  else
  {
    if ( a3->ss_family != 23 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5DF,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\iphelper.cpp",
        (const char *)0x57,
        v13[0]);
    if ( a3 )
    {
      Row.NextHop.Ipv4 = *(SOCKADDR_IN *)&a3->ss_family;
      *(_OWORD *)(&Row.NextHop.si_family + 6) = *(_OWORD *)((char *)&a3->__ss_align + 4);
      goto LABEL_10;
    }
    memset(&Row.NextHop, 0, sizeof(Row.NextHop));
  }
  *(_DWORD *)_o__errno() = 22;
  invalid_parameter_noinfo();
LABEL_10:
  IPHelper::SetCurrentThreadCompartmentId(v13, 0);
  if ( a5 )
  {
    v8 = InternalCreateIpForwardEntry2(2, &Row);
    if ( v8 == 5010 )
    {
      HNSTraceProvider::TraceSuccess("IPHelper::AddorRemoveRoute", 0x5EAu);
      if ( LOBYTE(v13[0]) )
        SetCurrentThreadCompartmentId(0);
      return 0;
    }
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5ED,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\iphelper.cpp",
        (const char *)v8,
        v13[0]);
  }
  else
  {
    v10 = InternalDeleteIpForwardEntry2(2, &Row);
    v11 = v10 < 0;
    if ( v10 > 0 )
    {
      v10 = (unsigned __int16)v10 | 0x80070000;
      v11 = v10 < 0;
    }
    if ( v11 && v10 != -2147024894 && v10 != -2147023728 && v10 != -1073741772 )
    {
      v12 = wil::verify_hresult<long>((unsigned int)v10);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F1,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\iphelper.cpp",
        (const char *)v12,
        v13[0]);
    }
  }
  HNSTraceProvider::TraceSuccess("IPHelper::AddorRemoveRoute", 0x5F4u);
  if ( LOBYTE(v13[0]) )
    SetCurrentThreadCompartmentId(0);
  return 1;
}

```

## disassembly

```asm
0x180089b34  mov     [rsp-8+arg_8], rbx
0x180089b39  push    rbp
0x180089b3a  push    rsi
0x180089b3b  push    rdi
0x180089b3c  lea     rbp, [rsp-37h]
0x180089b41  sub     rsp, 0B0h
0x180089b48  mov     rax, cs:__security_cookie
0x180089b4f  xor     rax, rsp
0x180089b52  mov     [rbp+47h+var_20], rax
0x180089b56  mov     rdi, r9
0x180089b59  mov     rsi, r8
0x180089b5c  mov     rbx, rcx
0x180089b5f  mov     edx, 5C4h; unsigned int
0x180089b64  lea     rcx, aIphelperAddorr; "IPHelper::AddorRemoveRoute"
0x180089b6b  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x180089b70  xor     edx, edx; Val
0x180089b72  lea     r8d, [rdx+68h]; Size
0x180089b76  lea     rcx, [rbp+47h+Row]; void *
0x180089b7a  call    memset_0
0x180089b7f  lea     rcx, [rbp+47h+Row]; Row
0x180089b83  call    cs:__imp_InitializeIpForwardEntry
0x180089b89  mov     rax, [rbx]
0x180089b8c  mov     qword ptr [rbp+47h+Row.InterfaceLuid], rax
0x180089b90  mov     [rbp+47h+Row.Protocol], 3
0x180089b97  movups  xmm0, xmmword ptr [rdi]
0x180089b9a  movups  xmmword ptr [rbp+47h+Row.DestinationPrefix.Prefix], xmm0
0x180089b9e  movups  xmm1, xmmword ptr [rdi+10h]
0x180089ba2  movups  xmmword ptr [rbp+47h+Row.DestinationPrefix.Prefix+10h], xmm1
0x180089ba6  mov     [rbp+47h+Row.Metric], 64h ; 'd'
0x180089bad  mov     ebx, 2
0x180089bb2  cmp     [rsi], bx
0x180089bb5  jnz     short loc_180089BCF
0x180089bb7  test    rsi, rsi
0x180089bba  jz      short loc_180089BC6
0x180089bbc  movaps  xmm0, xmmword ptr [rsi]
0x180089bbf  movdqu  xmmword ptr [rbp+47h+Row.NextHop], xmm0
0x180089bc4  jmp     short loc_180089C0B
0x180089bc6  xorps   xmm0, xmm0
0x180089bc9  movups  xmmword ptr [rbp+47h+Row.NextHop], xmm0
0x180089bcd  jmp     short loc_180089BFA
0x180089bcf  cmp     word ptr [rsi], 17h
0x180089bd3  jnz     loc_180089CFF
0x180089bd9  test    rsi, rsi
0x180089bdc  jz      short loc_180089BEF
0x180089bde  movaps  xmm0, xmmword ptr [rsi]
0x180089be1  movups  xmmword ptr [rbp+47h+Row.NextHop], xmm0
0x180089be5  movups  xmm1, xmmword ptr [rsi+0Ch]
0x180089be9  movups  xmmword ptr [rbp+47h+Row.NextHop+0Ch], xmm1
0x180089bed  jmp     short loc_180089C0B
0x180089bef  xorps   xmm0, xmm0
0x180089bf2  movups  xmmword ptr [rbp+47h+Row.NextHop], xmm0
0x180089bf6  movups  xmmword ptr [rbp+47h+Row.NextHop+0Ch], xmm0
0x180089bfa  call    cs:__imp__o__errno
0x180089c00  mov     dword ptr [rax], 16h
0x180089c06  call    _invalid_parameter_noinfo
0x180089c0b  xor     edx, edx
0x180089c0d  lea     rcx, [rbp+47h+var_A0]
0x180089c11  call    ?SetCurrentThreadCompartmentId@IPHelper@@SA?AV?$unique_call@P6AXXZ$1?ClearCompartment@IPHelper@@SAXXZ$00@wil@@I@Z; IPHelper::SetCurrentThreadCompartmentId(uint)
0x180089c16  nop
0x180089c17  lea     rdx, [rbp+47h+Row]
0x180089c1b  mov     ecx, ebx
0x180089c1d  cmp     [rbp+47h+arg_20], 0
0x180089c21  jz      short loc_180089C7B
0x180089c23  call    cs:__imp_InternalCreateIpForwardEntry2
0x180089c29  cmp     eax, 1392h
0x180089c2e  jnz     short loc_180089C71
0x180089c30  mov     edx, 5EAh; unsigned int
0x180089c35  lea     rcx, aIphelperAddorr; "IPHelper::AddorRemoveRoute"
0x180089c3c  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x180089c41  nop
0x180089c42  cmp     byte ptr [rbp+47h+var_A0], 0
0x180089c46  jz      short loc_180089C50
0x180089c48  xor     ecx, ecx; CompartmentId
0x180089c4a  call    cs:__imp_SetCurrentThreadCompartmentId
0x180089c50  xor     al, al
0x180089c52  mov     rcx, [rbp+47h+var_20]
0x180089c56  xor     rcx, rsp; StackCookie
0x180089c59  call    __security_check_cookie
0x180089c5e  mov     rbx, [rsp+0C0h+arg_8]
0x180089c66  add     rsp, 0B0h
0x180089c6d  pop     rdi
0x180089c6e  pop     rsi
0x180089c6f  pop     rbp
0x180089c70  retn
0x180089c71  mov     rcx, [rbp+4Fh]; this
0x180089c75  test    eax, eax
0x180089c77  jnz     short loc_180089CEA
0x180089c79  jmp     short loc_180089CA6
0x180089c7b  call    cs:__imp_InternalDeleteIpForwardEntry2
0x180089c81  test    eax, eax
0x180089c83  jle     short loc_180089C8F
0x180089c85  movzx   eax, ax
0x180089c88  or      eax, 80070000h
0x180089c8d  test    eax, eax
0x180089c8f  jns     short loc_180089CA6
0x180089c91  cmp     eax, 80070002h
0x180089c96  jz      short loc_180089CA6
0x180089c98  cmp     eax, 80070490h
0x180089c9d  jz      short loc_180089CA6
0x180089c9f  cmp     eax, 0C0000034h
0x180089ca4  jnz     short loc_180089CCA
0x180089ca6  mov     edx, 5F4h; unsigned int
0x180089cab  lea     rcx, aIphelperAddorr; "IPHelper::AddorRemoveRoute"
0x180089cb2  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x180089cb7  nop
0x180089cb8  cmp     byte ptr [rbp+47h+var_A0], 0
0x180089cbc  jz      short loc_180089CC6
0x180089cbe  xor     ecx, ecx; CompartmentId
0x180089cc0  call    cs:__imp_SetCurrentThreadCompartmentId
0x180089cc6  mov     al, 1
0x180089cc8  jmp     short loc_180089C52
0x180089cca  mov     ecx, eax
0x180089ccc  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180089cd1  mov     r9d, eax; char *
0x180089cd4  mov     rcx, [rbp+4Fh]; this
0x180089cd8  lea     r8, aOnecoreVmDvNet_158; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x180089cdf  mov     edx, 5F1h; void *
0x180089ce4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180089cea  mov     r9d, eax; char *
0x180089ced  lea     r8, aOnecoreVmDvNet_158; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x180089cf4  mov     edx, 5EDh; void *
0x180089cf9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180089cff  mov     rcx, [rbp+4Fh]; this
0x180089d03  mov     r9d, 57h ; 'W'; char *
0x180089d09  lea     r8, aOnecoreVmDvNet_158; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x180089d10  mov     edx, 5DFh; void *
0x180089d15  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
