# Microsoft::Diagnostics::UtcDecoderHostApiServer::StartRpcServer(void)

- ea: `0x140012104`
- end: `0x140012230`
- name: `?StartRpcServer@UtcDecoderHostApiServer@Diagnostics@Microsoft@@QEAAJXZ`
- size: `300`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcDecoderHostApiServer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400110a4`

## callees

- `0x140008660`
- `0x14000a840`
- `0x14000c434`
- `0x14000ebb4`
- `0x1400120e4`
- `0x140012104`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012158`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400121ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001220e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012158`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400121ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001220e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140012135`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140012135`
- `RPCRT4!RpcServerUseProtseqW` at `0x1400121a8`
- `RPCRT4!RpcServerUseProtseqW` at `0x1400121a8`

## string_xrefs

- `0x1400121c9`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapiserver.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::UtcDecoderHostApiServer::StartRpcServer(
        Microsoft::Diagnostics::UtcDecoderHostApiServer *this)
{
  unsigned int v1; // r8d
  const char *v2; // r9
  unsigned int v3; // ebx
  unsigned __int16 *v5; // rcx
  RPC_STATUS v6; // eax
  unsigned int v7; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-38h] BYREF
  RPC_WSTR Protseq[2]; // [rsp+28h] [rbp-30h] BYREF
  __int128 v10; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GA;;;S-1-5-80-2620808479-2171380039-3191355562-2070425692-3097948119)(A;;GA;;;S-1-15-2-3403125134-4244430"
          "74-1489734032-3328068408-1744204695-205958814-4102323917)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    *(_OWORD *)Protseq = 0;
    v10 = 0;
    std::wstring::_Construct<1,wchar_t const *>(Protseq, L"ncalrpc", 7u);
    v5 = (unsigned __int16 *)Protseq;
    if ( *((_QWORD *)&v10 + 1) > 7u )
      v5 = Protseq[0];
    v6 = RpcServerUseProtseqW(v5, 0xAu, SecurityDescriptor);
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80010000;
    if ( (v7 & 0x80000000) == 0 )
    {
      std::wstring::~wstring((char **)Protseq);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22,
        (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapiserver.cpp",
        (const char *)v7);
      std::wstring::~wstring((char **)Protseq);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      return v7;
    }
  }
  else
  {
    v3 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x1D, v1, v2, (unsigned int)SecurityDescriptor);
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return v3;
  }
}

```

## disassembly

```asm
0x140012104  push    rbx
0x140012106  sub     rsp, 50h
0x14001210a  mov     rax, cs:__security_cookie
0x140012111  xor     rax, rsp
0x140012114  mov     [rsp+58h+var_10], rax
0x140012119  mov     [rsp+58h+SecurityDescriptor], 0; int
0x140012122  xor     r9d, r9d; SecurityDescriptorSize
0x140012125  lea     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x14001212a  lea     edx, [r9+1]; StringSDRevision
0x14001212e  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;S-1-5-80-2620808479-21713800"...
0x140012135  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14001213b  test    eax, eax
0x14001213d  jnz     short loc_140012165
0x14001213f  mov     rcx, [rsp+58h]; this
0x140012144  lea     edx, [rax+1Dh]; void *
0x140012147  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001214c  mov     ebx, eax
0x14001214e  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x140012153  test    rcx, rcx
0x140012156  jz      short loc_14001215E
0x140012158  call    cs:__imp_LocalFree
0x14001215e  mov     eax, ebx
0x140012160  jmp     loc_14001221C
0x140012165  xorps   xmm0, xmm0
0x140012168  movups  xmmword ptr [rsp+58h+Protseq], xmm0
0x14001216d  xorps   xmm1, xmm1
0x140012170  movdqu  [rsp+58h+var_20], xmm1
0x140012176  mov     r8d, 7
0x14001217c  lea     rdx, aNcalrpc; "ncalrpc"
0x140012183  lea     rcx, [rsp+58h+Protseq]
0x140012188  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001218d  lea     rcx, [rsp+58h+Protseq]
0x140012192  cmp     qword ptr [rsp+58h+var_20+8], 7
0x140012198  cmova   rcx, [rsp+58h+Protseq]; Protseq
0x14001219e  mov     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x1400121a3  mov     edx, 0Ah; MaxCalls
0x1400121a8  call    cs:__imp_RpcServerUseProtseqW
0x1400121ae  mov     ebx, eax
0x1400121b0  test    eax, eax
0x1400121b2  jle     short loc_1400121BD
0x1400121b4  movzx   ebx, ax
0x1400121b7  or      ebx, 80010000h
0x1400121bd  test    ebx, ebx
0x1400121bf  jns     short loc_1400121F9
0x1400121c1  mov     rcx, [rsp+58h]; this
0x1400121c6  mov     r9d, ebx; char *
0x1400121c9  lea     r8, aOnecoreBaseTel_2; "onecore\\base\\telemetry\\utc\\service"...
0x1400121d0  mov     edx, 22h ; '"'; void *
0x1400121d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400121da  lea     rcx, [rsp+58h+Protseq]; void *
0x1400121df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400121e4  nop
0x1400121e5  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x1400121ea  test    rcx, rcx
0x1400121ed  jz      short loc_1400121F5
0x1400121ef  call    cs:__imp_LocalFree
0x1400121f5  mov     eax, ebx
0x1400121f7  jmp     short loc_14001221C
0x1400121f9  lea     rcx, [rsp+58h+Protseq]; void *
0x1400121fe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140012203  nop
0x140012204  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x140012209  test    rcx, rcx
0x14001220c  jz      short loc_140012214
0x14001220e  call    cs:__imp_LocalFree
0x140012214  xor     eax, eax
0x140012216  jmp     short loc_14001221C
0x140012218  mov     eax, dword ptr [rsp+58h+SecurityDescriptor]
0x14001221c  mov     rcx, [rsp+58h+var_10]
0x140012221  xor     rcx, rsp; StackCookie
0x140012224  call    __security_check_cookie
0x140012229  add     rsp, 50h
0x14001222d  pop     rbx
0x14001222e  retn
```
