# CopyRule(IMultiObjectElevationFactory *,INetFwRule *,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes)

- ea: `0x180028918`
- end: `0x180028a8d`
- name: `?CopyRule@@YAPEAUINetFwRule@@PEAUIMultiObjectElevationFactory@@PEAU1@W4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@winrt@@@Z`
- size: `373`
- prototype: `struct INetFwRule *__fastcall(__int64, struct INetFwRule *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026784`

## callees

- `0x18000b5f0`
- `0x1800148d0`
- `0x18002761c`
- `0x180028918`
- `0x18002d010`

## string_xrefs

- `0x180028a27`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x180028a3c`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x180028a51`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x180028a66`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x180028a7b`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`

## pseudocode

```c
struct INetFwRule *__fastcall CopyRule(__int64 a1, struct INetFwRule *a2, unsigned int a3)
{
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  struct INetFwRule *v10; // rbx
  struct INetFwRule *v11; // rax
  int v13; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  struct INetFwRule *v15; // [rsp+40h] [rbp+10h] BYREF
  __int64 v16; // [rsp+58h] [rbp+28h] BYREF

  v15 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, struct INetFwRule **))(*(_QWORD *)a1 + 40LL))(
         a1,
         &GUID_2c5bc43e_3369_4c33_ab0c_be9469677af4,
         &GUID_af230d27_baba_4e42_aced_f524f22cfce2,
         &v15);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x17E,
      (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
      (const char *)(unsigned int)v5,
      v13);
  v6 = CopyINetFwRule(a2, v15);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x180,
      (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
      (const char *)(unsigned int)v6,
      v13);
  v7 = ((__int64 (__fastcall *)(struct INetFwRule *, _QWORD))v15->lpVtbl->put_Profiles)(v15, a3);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x181,
      (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
      (const char *)(unsigned int)v7,
      v13);
  v16 = 0;
  v8 = ((__int64 (__fastcall *)(struct INetFwRule *, GUID *, __int64 *))v15->lpVtbl->QueryInterface)(
         v15,
         &GUID_9c27c8da_189b_4dde_89f7_8b39a316782c,
         &v16);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x184,
      (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
      (const char *)(unsigned int)v8,
      v13);
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 352LL))(v16, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x186,
      (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
      (const char *)(unsigned int)v9,
      v13);
  v10 = v15;
  v11 = 0;
  v15 = 0;
  if ( v16 )
  {
    winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v16);
    v11 = v15;
  }
  if ( v11 )
    winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v15);
  return v10;
}

```

## disassembly

```asm
0x180028918  mov     [rsp-8+arg_8], rbx
0x18002891d  mov     [rsp-8+arg_10], rdi
0x180028922  push    rbp
0x180028923  mov     rbp, rsp
0x180028926  sub     rsp, 30h
0x18002892a  mov     edi, r8d
0x18002892d  mov     rbx, rdx
0x180028930  mov     [rbp+arg_0], 0
0x180028938  mov     rax, [rcx]
0x18002893b  lea     r9, [rbp+arg_0]
0x18002893f  lea     r8, _GUID_af230d27_baba_4e42_aced_f524f22cfce2
0x180028946  lea     rdx, _GUID_2c5bc43e_3369_4c33_ab0c_be9469677af4
0x18002894d  mov     rax, [rax+28h]
0x180028951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028956  mov     rcx, [rbp+8]; this
0x18002895a  test    eax, eax
0x18002895c  js      loc_180028A39
0x180028962  mov     rdx, [rbp+arg_0]; struct INetFwRule *
0x180028966  mov     rcx, rbx; struct INetFwRule *
0x180028969  call    ?CopyINetFwRule@@YAJPEAUINetFwRule@@0@Z; CopyINetFwRule(INetFwRule *,INetFwRule *)
0x18002896e  mov     rcx, [rbp+8]; this
0x180028972  test    eax, eax
0x180028974  js      loc_180028A4E
0x18002897a  mov     rcx, [rbp+arg_0]
0x18002897e  mov     rax, [rcx]
0x180028981  mov     edx, edi
0x180028983  mov     rax, [rax+130h]
0x18002898a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002898f  mov     rcx, [rbp+8]; this
0x180028993  test    eax, eax
0x180028995  js      loc_180028A63
0x18002899b  mov     [rbp+arg_18], 0
0x1800289a3  mov     rcx, [rbp+arg_0]
0x1800289a7  mov     rax, [rcx]
0x1800289aa  lea     r8, [rbp+arg_18]
0x1800289ae  lea     rdx, _GUID_9c27c8da_189b_4dde_89f7_8b39a316782c
0x1800289b5  mov     rax, [rax]
0x1800289b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289bd  mov     rcx, [rbp+8]; this
0x1800289c1  test    eax, eax
0x1800289c3  js      loc_180028A78
0x1800289c9  mov     rcx, [rbp+arg_18]
0x1800289cd  mov     rax, [rcx]
0x1800289d0  xor     edx, edx
0x1800289d2  mov     rax, [rax+160h]
0x1800289d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289de  mov     rcx, [rbp+8]; this
0x1800289e2  test    eax, eax
0x1800289e4  js      short loc_180028A24
0x1800289e6  mov     rbx, [rbp+arg_0]
0x1800289ea  xor     eax, eax
0x1800289ec  mov     [rbp+arg_0], rax
0x1800289f0  cmp     [rbp+arg_18], rax
0x1800289f4  jz      short loc_180028A03
0x1800289f6  lea     rcx, [rbp+arg_18]
0x1800289fa  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x1800289ff  mov     rax, [rbp+arg_0]
0x180028a03  test    rax, rax
0x180028a06  jz      short loc_180028A11
0x180028a08  lea     rcx, [rbp+arg_0]
0x180028a0c  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180028a11  mov     rax, rbx
0x180028a14  mov     rbx, [rsp+30h+arg_8]
0x180028a19  mov     rdi, [rsp+30h+arg_10]
0x180028a1e  add     rsp, 30h
0x180028a22  pop     rbp
0x180028a23  retn
0x180028a24  mov     r9d, eax; char *
0x180028a27  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x180028a2e  mov     edx, 186h; void *
0x180028a33  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180028a39  mov     r9d, eax; char *
0x180028a3c  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x180028a43  mov     edx, 17Eh; void *
0x180028a48  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180028a4e  mov     r9d, eax; char *
0x180028a51  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x180028a58  mov     edx, 180h; void *
0x180028a5d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180028a63  mov     r9d, eax; char *
0x180028a66  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x180028a6d  mov     edx, 181h; void *
0x180028a72  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180028a78  mov     r9d, eax; char *
0x180028a7b  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x180028a82  mov     edx, 184h; void *
0x180028a87  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
