# winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(winrt::param::hstring const &)

- ea: `0x180012220`
- end: `0x1800122d5`
- name: `?LoadXml@?$consume_Windows_Data_Xml_Dom_IXmlDocumentIO@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
- size: `181`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *), _QWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180011e50`
- `0x1800120b8`
- `0x180016a30`
- `0x180016b6c`
- `0x18001874c`

## callees

- `0x180010a38`
- `0x180012220`
- `0x180012e00`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(
        __int64 (__fastcall ****a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, __int64 *, __int64 *); // rcx
  int v4; // eax
  __int64 v5; // rbx
  int v6; // eax
  int v8; // [rsp+20h] [rbp-20h] BYREF
  __int128 v9; // [rsp+28h] [rbp-18h]
  __int64 v10; // [rsp+50h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+20h] BYREF

  v3 = *a1;
  if ( v3 )
  {
    v10 = 0;
    v4 = (**v3)(v3, winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlDocumentIO>, &v10);
    v5 = v10;
    v11 = v10;
  }
  else
  {
    v4 = 0;
    v11 = 0;
    v5 = 0;
  }
  v8 = 0;
  v9 = 0;
  winrt::check_hresult((int *)&v10, v4, (__int64)&v8);
  v8 = 0;
  v9 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 48LL))(v5, *a2);
  winrt::check_hresult((int *)&v10, v6, (__int64)&v8);
  return winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v11);
}

```

## disassembly

```asm
0x180012220  mov     [rsp-8+arg_8], rbx
0x180012225  mov     [rsp-8+arg_18], rdi
0x18001222a  push    rbp
0x18001222b  mov     rbp, rsp
0x18001222e  sub     rsp, 40h
0x180012232  mov     rdi, rdx
0x180012235  mov     rcx, [rcx]
0x180012238  test    rcx, rcx
0x18001223b  jnz     short loc_180012247
0x18001223d  xor     eax, eax
0x18001223f  mov     [rbp+arg_10], rax
0x180012243  xor     ebx, ebx
0x180012245  jmp     short loc_18001226D
0x180012247  mov     [rbp+arg_0], 0
0x18001224f  mov     rax, [rcx]
0x180012252  lea     r8, [rbp+arg_0]
0x180012256  lea     rdx, ??$guid_v@UIXmlDocumentIO@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlDocumentIO>
0x18001225d  mov     rax, [rax]
0x180012260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012265  mov     rbx, [rbp+arg_0]
0x180012269  mov     [rbp+arg_10], rbx
0x18001226d  mov     [rbp+var_20], 0
0x180012274  xorps   xmm0, xmm0
0x180012277  movdqu  [rbp+var_18], xmm0
0x18001227c  lea     r8, [rbp+var_20]
0x180012280  mov     edx, eax
0x180012282  lea     rcx, [rbp+arg_0]
0x180012286  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001228b  mov     [rbp+var_20], 0
0x180012292  xorps   xmm0, xmm0
0x180012295  movdqu  [rbp+var_18], xmm0
0x18001229a  mov     rax, [rbx]
0x18001229d  mov     rdx, [rdi]
0x1800122a0  mov     rcx, rbx
0x1800122a3  mov     rax, [rax+30h]
0x1800122a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122ac  lea     r8, [rbp+var_20]
0x1800122b0  mov     edx, eax
0x1800122b2  lea     rcx, [rbp+arg_0]
0x1800122b6  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800122bb  nop
0x1800122bc  lea     rcx, [rbp+arg_10]
0x1800122c0  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x1800122c5  mov     rbx, [rsp+40h+arg_8]
0x1800122ca  mov     rdi, [rsp+40h+arg_18]
0x1800122cf  add     rsp, 40h
0x1800122d3  pop     rbp
0x1800122d4  retn
```
