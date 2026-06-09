# PrintSupportUtility::IsActivationContractSupported(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180034bc8`
- end: `0x180034cb5`
- name: `?IsActivationContractSupported@PrintSupportUtility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012b88`

## callees

- `0x180006b48`
- `0x18000fa18`
- `0x18001d020`
- `0x180034ae0`
- `0x180034bc8`

## import_xrefs

- `Print.PrintSupport.Source!IsActivationContractSupportedForUserContext` at `0x180034c1e`
- `Print.PrintSupport.Source!IsActivationContractSupportedForUserContext` at `0x180034c1e`
- `Print.PrintSupport.Source!IsActivationContractSupported` at `0x180034c45`
- `Print.PrintSupport.Source!IsActivationContractSupported` at `0x180034c45`

## string_xrefs

- `0x180034c8f`: `onecoreuap\printscan\print\printscanbroker\class\printsupportutility.cpp`

## pseudocode

```c
char __fastcall PrintSupportUtility::IsActivationContractSupported(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  int v6; // eax
  unsigned int v8; // r8d
  unsigned int v9; // eax
  const char *v10; // rdx
  _QWORD v11[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v13; // [rsp+68h] [rbp+20h] BYREF

  v13 = 0;
  v11[0] = 0;
  if ( (int)PrintCore::UserContextHelpers::GetUserContextForPrinter(a1, v11) < 0 )
  {
    if ( a3[3] > 7u )
      a3 = (_QWORD *)*a3;
    if ( a2[3] > 7u )
      a2 = (_QWORD *)*a2;
    v6 = IsActivationContractSupported(a2, a3, &v13);
  }
  else
  {
    if ( a3[3] > 7u )
      a3 = (_QWORD *)*a3;
    if ( a2[3] > 7u )
      a2 = (_QWORD *)*a2;
    v6 = IsActivationContractSupportedForUserContext(v11[0], a2, a3, &v13);
  }
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147023728 )
  {
    std::wstring::c_str(a1);
    v9 = wil::verify_hresult<long>(v8);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printsupportutility.cpp",
      (const char *)v9,
      (int)"Failed to determine if an activation contract was supported for printer: %ws",
      v10);
  }
  return v13;
}

```

## disassembly

```asm
0x180034bc8  mov     rax, rsp
0x180034bcb  mov     [rax+8], rbx
0x180034bcf  mov     [rax+10h], rsi
0x180034bd3  push    rdi
0x180034bd4  sub     rsp, 40h
0x180034bd8  mov     rbx, rdx
0x180034bdb  mov     byte ptr [rax+20h], 0
0x180034bdf  lea     rdx, [rax-18h]
0x180034be3  mov     qword ptr [rax-18h], 0
0x180034beb  mov     rdi, r8
0x180034bee  mov     rsi, rcx
0x180034bf1  call    ?GetUserContextForPrinter@UserContextHelpers@PrintCore@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_K@Z; PrintCore::UserContextHelpers::GetUserContextForPrinter(std::wstring const &,unsigned __int64 *)
0x180034bf6  test    eax, eax
0x180034bf8  js      short loc_180034C26
0x180034bfa  cmp     qword ptr [rdi+18h], 7
0x180034bff  jbe     short loc_180034C04
0x180034c01  mov     rdi, [rdi]
0x180034c04  cmp     qword ptr [rbx+18h], 7
0x180034c09  jbe     short loc_180034C0E
0x180034c0b  mov     rbx, [rbx]
0x180034c0e  mov     rcx, [rsp+48h+var_18]
0x180034c13  lea     r9, [rsp+48h+arg_18]
0x180034c18  mov     r8, rdi
0x180034c1b  mov     rdx, rbx
0x180034c1e  call    cs:__imp_IsActivationContractSupportedForUserContext
0x180034c24  jmp     short loc_180034C4B
0x180034c26  cmp     qword ptr [rdi+18h], 7
0x180034c2b  jbe     short loc_180034C30
0x180034c2d  mov     rdi, [rdi]
0x180034c30  cmp     qword ptr [rbx+18h], 7
0x180034c35  jbe     short loc_180034C3A
0x180034c37  mov     rbx, [rbx]
0x180034c3a  lea     r8, [rsp+48h+arg_18]
0x180034c3f  mov     rdx, rdi
0x180034c42  mov     rcx, rbx
0x180034c45  call    cs:__imp_IsActivationContractSupported
0x180034c4b  mov     ecx, 80000000h
0x180034c50  mov     r8d, eax
0x180034c53  lea     eax, [rax+rcx]
0x180034c56  test    ecx, eax
0x180034c58  jnz     short loc_180034C63
0x180034c5a  cmp     r8d, 80070490h
0x180034c61  jnz     short loc_180034C77
0x180034c63  mov     al, [rsp+48h+arg_18]
0x180034c67  mov     rbx, [rsp+48h+arg_0]
0x180034c6c  mov     rsi, [rsp+48h+arg_8]
0x180034c71  add     rsp, 40h
0x180034c75  pop     rdi
0x180034c76  retn
0x180034c77  mov     rcx, rsi
0x180034c7a  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180034c7f  mov     ecx, r8d
0x180034c82  mov     rdx, rax
0x180034c85  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180034c8a  mov     rcx, [rsp+48h]; this
0x180034c8f  lea     r8, aOnecoreuapPrin_2; "onecoreuap\\printscan\\print\\printscan"...
0x180034c96  mov     [rsp+48h+var_20], rdx; char *
0x180034c9b  mov     r9d, eax; char *
0x180034c9e  lea     rax, aFailedToDeterm; "Failed to determine if an activation co"...
0x180034ca5  mov     edx, 43h ; 'C'; void *
0x180034caa  mov     qword ptr [rsp+48h+var_28], rax; int
0x180034caf  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
