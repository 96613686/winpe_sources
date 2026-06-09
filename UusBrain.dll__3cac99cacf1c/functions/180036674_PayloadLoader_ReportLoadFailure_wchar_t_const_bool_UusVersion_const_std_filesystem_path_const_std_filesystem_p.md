# PayloadLoader::ReportLoadFailure(wchar_t const *,bool,UusVersion const &,std::filesystem::path const &,std::filesystem::path const &,wchar_t const *,uint,bool,long)

- ea: `0x180036674`
- end: `0x1800367f7`
- name: `?ReportLoadFailure@PayloadLoader@@SAJPEB_W_NAEBVUusVersion@@AEBVpath@filesystem@std@@30I1J@Z`
- size: `387`
- prototype: `static int(const wchar_t *, bool, const struct UusVersion *, const struct std::filesystem::path *, const struct std::filesystem::path *, const wchar_t *, unsigned int, bool, int)`
- caller_count: `4`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18004b187`
- `0x18004b223`
- `0x18004b897`
- `0x18004b997`

## callees

- `0x1800089f4`
- `0x18000ab24`
- `0x1800266b0`
- `0x180028728`
- `0x180029518`
- `0x180029644`
- `0x180033c14`
- `0x180036674`
- `0x180036a04`
- `0x18003cb54`
- `0x180042bfc`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PayloadLoader::ReportLoadFailure(
        const wchar_t *a1,
        bool a2,
        const struct UusVersion *a3,
        const struct std::filesystem::path *a4,
        wchar_t *a5,
        const wchar_t *a6,
        unsigned int a7,
        bool a8,
        unsigned int a9)
{
  const wchar_t *v12; // rbx
  bool v13; // r14
  UusPackage *v14; // rax
  UusPackage *v15; // rsi
  _QWORD *v16; // rax
  __int64 v17; // r8
  char IsFileInPayload; // r15
  __int64 String; // rax
  const wchar_t *v20; // r8
  __int128 v23; // [rsp+78h] [rbp-69h] BYREF
  __int64 v24; // [rsp+88h] [rbp-59h]
  __int64 v25; // [rsp+90h] [rbp-51h]
  _BYTE v26[32]; // [rsp+A0h] [rbp-41h] BYREF
  _BYTE v27[96]; // [rsp+C0h] [rbp-21h] BYREF

  v12 = a5;
  v13 = 0;
  v14 = (UusPackage *)operator new(0x58u);
  v15 = UusPackage::UusPackage(v14, a4);
  std::wstring::wstring(v27, a5);
  v16 = (_QWORD *)std::filesystem::path::filename(v27, v26);
  if ( v16[3] > 7u )
    v16 = (_QWORD *)*v16;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v17 = -1;
  do
    ++v17;
  while ( *((_WORD *)v16 + v17) );
  std::wstring::_Construct<1,wchar_t const *>(&v23);
  IsFileInPayload = UusPackage::IsFileInPayload((__int64)v15, (__int64)&v23);
  std::wstring::_Tidy_deallocate(v26);
  std::wstring::_Tidy_deallocate(v27);
  if ( IsFileInPayload )
    v13 = PayloadLoader::ExcludePackageIfEnabled(a3, a2);
  if ( *((_QWORD *)a5 + 3) > 7u )
    v12 = *(const wchar_t **)a5;
  if ( *((_QWORD *)a4 + 3) > 7u )
    a4 = *(const struct std::filesystem::path **)a4;
  String = UusVersion::GetString(a3, v26);
  v20 = (const wchar_t *)String;
  if ( *(_QWORD *)(String + 24) > 7u )
    v20 = *(const wchar_t **)String;
  uus::UndockedUpdateTelemetry::UusPayloadLoadFailure(
    a1,
    a2,
    v20,
    (const wchar_t *)a4,
    v12,
    a6,
    a7,
    a8,
    a9,
    v13,
    IsFileInPayload);
  std::wstring::_Tidy_deallocate(v26);
  if ( v15 )
    (**(void (__fastcall ***)(UusPackage *, __int64))v15)(v15, 1);
  return a9;
}

```

## disassembly

```asm
0x180036674  push    rbp
0x180036676  push    rbx
0x180036677  push    rsi
0x180036678  push    rdi
0x180036679  push    r12
0x18003667b  push    r13
0x18003667d  push    r14
0x18003667f  push    r15
0x180036681  lea     rbp, [rsp-7]
0x180036686  sub     rsp, 0E8h
0x18003668d  mov     rdi, r9
0x180036690  mov     r12, r8
0x180036693  mov     r13b, dl
0x180036696  mov     [rbp+3Fh+var_B0], rcx
0x18003669a  mov     rbx, [rbp+3Fh+arg_20]
0x18003669e  mov     rax, [rbp+3Fh+arg_28]
0x1800366a2  mov     [rbp+3Fh+var_B8], rax
0x1800366a6  xor     r14d, r14d
0x1800366a9  lea     ecx, [r14+58h]; Size
0x1800366ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800366b2  mov     [rsp+120h+var_C0], rax
0x1800366b7  mov     rdx, rdi; struct std::filesystem::path *
0x1800366ba  mov     rcx, rax; this
0x1800366bd  call    ??0UusPackage@@QEAA@AEBVpath@filesystem@std@@@Z; UusPackage::UusPackage(std::filesystem::path const &)
0x1800366c2  mov     rsi, rax
0x1800366c5  mov     [rsp+120h+var_C0], rax
0x1800366ca  mov     rdx, rbx
0x1800366cd  lea     rcx, [rbp+3Fh+var_60]
0x1800366d1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800366d6  nop
0x1800366d7  lea     rdx, [rbp+3Fh+var_80]
0x1800366db  lea     rcx, [rbp+3Fh+var_60]
0x1800366df  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x1800366e4  nop
0x1800366e5  cmp     qword ptr [rax+18h], 7
0x1800366ea  jbe     short loc_1800366EF
0x1800366ec  mov     rax, [rax]
0x1800366ef  xorps   xmm0, xmm0
0x1800366f2  movups  [rbp+3Fh+var_A8], xmm0
0x1800366f6  mov     [rbp+3Fh+var_98], r14
0x1800366fa  mov     [rbp+3Fh+var_90], r14
0x1800366fe  or      r8, 0FFFFFFFFFFFFFFFFh
0x180036702  inc     r8
0x180036705  cmp     [rax+r8*2], r14w
0x18003670a  jnz     short loc_180036702
0x18003670c  mov     rdx, rax
0x18003670f  lea     rcx, [rbp+3Fh+var_A8]
0x180036713  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180036718  lea     rdx, [rbp+3Fh+var_A8]
0x18003671c  mov     rcx, rsi
0x18003671f  call    ?IsFileInPayload@UusPackage@@QEAA_NV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UusPackage::IsFileInPayload(std::wstring)
0x180036724  mov     r15b, al
0x180036727  lea     rcx, [rbp+3Fh+var_80]
0x18003672b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036730  nop
0x180036731  lea     rcx, [rbp+3Fh+var_60]
0x180036735  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003673a  test    r15b, r15b
0x18003673d  jz      short loc_18003674D
0x18003673f  mov     dl, r13b; bool
0x180036742  mov     rcx, r12; struct UusVersion *
0x180036745  call    ?ExcludePackageIfEnabled@PayloadLoader@@CA_NAEBVUusVersion@@_N@Z; PayloadLoader::ExcludePackageIfEnabled(UusVersion const &,bool)
0x18003674a  mov     r14b, al
0x18003674d  cmp     qword ptr [rbx+18h], 7
0x180036752  jbe     short loc_180036757
0x180036754  mov     rbx, [rbx]
0x180036757  cmp     qword ptr [rdi+18h], 7
0x18003675c  jbe     short loc_180036761
0x18003675e  mov     rdi, [rdi]
0x180036761  lea     rdx, [rbp+3Fh+var_80]
0x180036765  mov     rcx, r12
0x180036768  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x18003676d  mov     r8, rax
0x180036770  cmp     qword ptr [rax+18h], 7
0x180036775  jbe     short loc_18003677A
0x180036777  mov     r8, [rax]; wchar_t *
0x18003677a  mov     [rsp+120h+var_D0], r15b; bool
0x18003677f  mov     [rsp+120h+var_D8], r14b; bool
0x180036784  mov     r14d, [rbp+3Fh+arg_40]
0x18003678b  mov     [rsp+120h+var_E0], r14d; int
0x180036790  mov     al, [rbp+3Fh+arg_38]
0x180036796  mov     [rsp+120h+var_E8], al; bool
0x18003679a  mov     eax, [rbp+3Fh+arg_30]
0x18003679d  mov     [rsp+120h+var_F0], eax; unsigned int
0x1800367a1  mov     rax, [rbp+3Fh+var_B8]
0x1800367a5  mov     [rsp+120h+var_F8], rax; wchar_t *
0x1800367aa  mov     [rsp+120h+var_100], rbx; wchar_t *
0x1800367af  mov     r9, rdi; wchar_t *
0x1800367b2  mov     dl, r13b; bool
0x1800367b5  mov     rcx, [rbp+3Fh+var_B0]; wchar_t *
0x1800367b9  call    ?UusPayloadLoadFailure@UndockedUpdateTelemetry@uus@@SAXPEB_W_N0000I1J11@Z; uus::UndockedUpdateTelemetry::UusPayloadLoadFailure(wchar_t const *,bool,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,uint,bool,long,bool,bool)
0x1800367be  lea     rcx, [rbp+3Fh+var_80]
0x1800367c2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800367c7  nop
0x1800367c8  test    rsi, rsi
0x1800367cb  jz      short loc_1800367E0
0x1800367cd  mov     rcx, [rsi]
0x1800367d0  mov     rax, [rcx]
0x1800367d3  mov     edx, 1
0x1800367d8  mov     rcx, rsi
0x1800367db  call    _guard_dispatch_icall
0x1800367e0  mov     eax, r14d
0x1800367e3  add     rsp, 0E8h
0x1800367ea  pop     r15
0x1800367ec  pop     r14
0x1800367ee  pop     r13
0x1800367f0  pop     r12
0x1800367f2  pop     rdi
0x1800367f3  pop     rsi
0x1800367f4  pop     rbx
0x1800367f5  pop     rbp
0x1800367f6  retn
```
