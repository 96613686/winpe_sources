# winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNodeSerializer<winrt::Windows::Data::Xml::Dom::IXmlElement>::InnerText(winrt::param::hstring const &)

- ea: `0x18000d22c`
- end: `0x18000d2e1`
- name: `?InnerText@?$consume_Windows_Data_Xml_Dom_IXmlNodeSerializer@UIXmlElement@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
- size: `181`
- prototype: `void __fastcall(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *), _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d424`

## callees

- `0x18000a360`
- `0x18000d22c`
- `0x18000f38c`
- `0x180018010`

## pseudocode

```c
void __fastcall winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNodeSerializer<winrt::Windows::Data::Xml::Dom::IXmlElement>::InnerText(
        __int64 (__fastcall ****a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, __int64 *, __int64 *); // rcx
  int v4; // eax
  __int64 v5; // rbx
  int v6; // eax
  int v7; // [rsp+20h] [rbp-20h] BYREF
  __int128 v8; // [rsp+28h] [rbp-18h]
  __int64 v9; // [rsp+50h] [rbp+10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+20h] BYREF

  v3 = *a1;
  if ( v3 )
  {
    v9 = 0;
    v4 = (**v3)(v3, winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlNodeSerializer>, &v9);
    v5 = v9;
    v10 = v9;
  }
  else
  {
    v4 = 0;
    v10 = 0;
    v5 = 0;
  }
  v7 = 0;
  v8 = 0;
  winrt::check_hresult((int *)&v9, v4, (__int64)&v7);
  v7 = 0;
  v8 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 64LL))(v5, *a2);
  winrt::check_hresult((int *)&v9, v6, (__int64)&v7);
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v10);
}

```

## disassembly

```asm
0x18000d22c  mov     [rsp-8+arg_8], rbx
0x18000d231  mov     [rsp-8+arg_18], rdi
0x18000d236  push    rbp
0x18000d237  mov     rbp, rsp
0x18000d23a  sub     rsp, 40h
0x18000d23e  mov     rdi, rdx
0x18000d241  mov     rcx, [rcx]
0x18000d244  test    rcx, rcx
0x18000d247  jnz     short loc_18000D253
0x18000d249  xor     eax, eax
0x18000d24b  mov     [rbp+arg_10], rax
0x18000d24f  xor     ebx, ebx
0x18000d251  jmp     short loc_18000D279
0x18000d253  mov     [rbp+arg_0], 0
0x18000d25b  mov     rax, [rcx]
0x18000d25e  lea     r8, [rbp+arg_0]
0x18000d262  lea     rdx, ??$guid_v@UIXmlNodeSerializer@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlNodeSerializer>
0x18000d269  mov     rax, [rax]
0x18000d26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d271  mov     rbx, [rbp+arg_0]
0x18000d275  mov     [rbp+arg_10], rbx
0x18000d279  mov     [rbp+var_20], 0
0x18000d280  xorps   xmm0, xmm0
0x18000d283  movdqu  [rbp+var_18], xmm0
0x18000d288  lea     r8, [rbp+var_20]
0x18000d28c  mov     edx, eax
0x18000d28e  lea     rcx, [rbp+arg_0]
0x18000d292  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000d297  mov     [rbp+var_20], 0
0x18000d29e  xorps   xmm0, xmm0
0x18000d2a1  movdqu  [rbp+var_18], xmm0
0x18000d2a6  mov     rax, [rbx]
0x18000d2a9  mov     rdx, [rdi]
0x18000d2ac  mov     rcx, rbx
0x18000d2af  mov     rax, [rax+40h]
0x18000d2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2b8  lea     r8, [rbp+var_20]
0x18000d2bc  mov     edx, eax
0x18000d2be  lea     rcx, [rbp+arg_0]
0x18000d2c2  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000d2c7  nop
0x18000d2c8  lea     rcx, [rbp+arg_10]; this
0x18000d2cc  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d2d1  mov     rbx, [rsp+40h+arg_8]
0x18000d2d6  mov     rdi, [rsp+40h+arg_18]
0x18000d2db  add     rsp, 40h
0x18000d2df  pop     rbp
0x18000d2e0  retn
```
