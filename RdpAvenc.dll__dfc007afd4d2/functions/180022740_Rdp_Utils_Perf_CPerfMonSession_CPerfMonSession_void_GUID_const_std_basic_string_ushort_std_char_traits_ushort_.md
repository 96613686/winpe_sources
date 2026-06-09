# Rdp::Utils::Perf::CPerfMonSession::CPerfMonSession(void *,_GUID const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,uint)

- ea: `0x180022740`
- end: `0x180022837`
- name: `??0CPerfMonSession@Perf@Utils@Rdp@@QEAA@PEAXAEBU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800238a0`

## callees

- `0x180006580`
- `0x18000d0ac`
- `0x180022740`
- `0x180026824`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800227dd`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800227dd`

## string_xrefs

- `0x1800227f2`: `PerfCreateInstance failed`
- `0x180022802`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PerfMon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Utils::Perf::CPerfMonSession::CPerfMonSession(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  const WCHAR *v7; // r8
  PPERF_COUNTERSET_INSTANCE Instance; // rax
  const char *v10; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_QWORD *)a1 = a2;
  *(_OWORD *)(a1 + 8) = GraphicsPerSessionGuid;
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 32) = a5;
  *(_OWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_OWORD *)(a1 + 40) = *(_OWORD *)a4;
  *(_OWORD *)(a1 + 56) = *(_OWORD *)(a4 + 16);
  *(_WORD *)a4 = 0;
  *(_QWORD *)(a4 + 16) = 0;
  *(_QWORD *)(a4 + 24) = 7;
  v7 = (const WCHAR *)(a1 + 40);
  if ( *(_QWORD *)(a1 + 64) > 7u )
    v7 = *(const WCHAR **)v7;
  Instance = PerfCreateInstance(*(HANDLE *)a1, (LPCGUID)(a1 + 8), v7, *(_DWORD *)(a1 + 32));
  *(_QWORD *)(a1 + 24) = Instance;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x149,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PerfMon.h",
    (const char *)(Instance == 0),
    "PerfCreateInstance failed",
    v10);
  std::wstring::~wstring(a4);
  return a1;
}

```

## disassembly

```asm
0x180022740  mov     [rsp+arg_8], rbx
0x180022745  push    rdi
0x180022746  sub     rsp, 50h
0x18002274a  mov     rax, cs:__security_cookie
0x180022751  xor     rax, rsp
0x180022754  mov     [rsp+58h+var_18], rax
0x180022759  mov     rdi, r9
0x18002275c  mov     rbx, rcx
0x18002275f  mov     [rsp+58h+var_28], rcx
0x180022764  mov     [rsp+58h+var_20], r9
0x180022769  mov     [rcx], rdx
0x18002276c  movups  xmm0, cs:GraphicsPerSessionGuid
0x180022773  movdqu  xmmword ptr [rcx+8], xmm0
0x180022778  mov     qword ptr [rcx+18h], 0
0x180022780  mov     eax, [rsp+58h+arg_20]
0x180022787  mov     [rcx+20h], eax
0x18002278a  xorps   xmm0, xmm0
0x18002278d  movups  xmmword ptr [rcx+28h], xmm0
0x180022791  mov     qword ptr [rcx+38h], 0
0x180022799  mov     qword ptr [rcx+40h], 0
0x1800227a1  movups  xmm0, xmmword ptr [r9]
0x1800227a5  movups  xmmword ptr [rcx+28h], xmm0
0x1800227a9  movups  xmm1, xmmword ptr [r9+10h]
0x1800227ae  movups  xmmword ptr [rcx+38h], xmm1
0x1800227b2  xor     eax, eax
0x1800227b4  mov     [r9], ax
0x1800227b8  mov     [r9+10h], rax
0x1800227bc  mov     qword ptr [r9+18h], 7
0x1800227c4  lea     r8, [rcx+28h]
0x1800227c8  cmp     qword ptr [r8+18h], 7
0x1800227cd  jbe     short loc_1800227D2
0x1800227cf  mov     r8, [r8]; Name
0x1800227d2  lea     rdx, [rcx+8]; CounterSetGuid
0x1800227d6  mov     r9d, [rcx+20h]; Id
0x1800227da  mov     rcx, [rcx]; ProviderHandle
0x1800227dd  call    cs:__imp_PerfCreateInstance
0x1800227e3  mov     [rbx+18h], rax
0x1800227e7  test    rax, rax
0x1800227ea  setz    dl
0x1800227ed  mov     rcx, [rsp+58h]; this
0x1800227f2  lea     rax, aPerfcreateinst; "PerfCreateInstance failed"
0x1800227f9  mov     [rsp+58h+var_38], rax; void *
0x1800227fe  movzx   r9d, dl; char *
0x180022802  lea     r8, aOnecoreuapTerm_29; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180022809  mov     edx, 149h; void *
0x18002280e  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180022813  nop
0x180022814  mov     rcx, rdi
0x180022817  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002281c  mov     rax, rbx
0x18002281f  mov     rcx, [rsp+58h+var_18]
0x180022824  xor     rcx, rsp; StackCookie
0x180022827  call    __security_check_cookie
0x18002282c  mov     rbx, [rsp+58h+arg_8]
0x180022831  add     rsp, 50h
0x180022835  pop     rdi
0x180022836  retn
```
