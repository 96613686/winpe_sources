# Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x18001f638`
- end: `0x18001f781`
- name: `?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `329`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f440`
- `0x180023cb0`
- `0x180024c34`

## callees

- `0x1800105f4`
- `0x18001f638`
- `0x18002e010`

## string_xrefs

- `0x18001f690`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001f6fb`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Autopilot::JsonHelpers::ToString(__int64 a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // edi
  __int64 v6; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v13; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v13 = 0;
  v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
         a1,
         &GUID_96369f54_8eb6_48f0_abce_c1b211e627c3,
         &v13);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v4,
      v11);
    v6 = v13;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
LABEL_6:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
    return v5;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 48LL))(v13, a2);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v8,
      v11);
    v9 = v13;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    goto LABEL_6;
  }
  v10 = v13;
  if ( v13 )
  {
    v13 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x18001f638  mov     [rsp+arg_8], rbx
0x18001f63d  mov     [rsp+arg_10], rsi
0x18001f642  push    rdi; int
0x18001f643  sub     rsp, 20h
0x18001f647  mov     rsi, rdx
0x18001f64a  mov     rbx, rcx
0x18001f64d  test    rcx, rcx
0x18001f650  jz      short loc_18001F65F
0x18001f652  mov     rax, [rcx]
0x18001f655  mov     rax, [rax+8]
0x18001f659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f65e  nop
0x18001f65f  mov     [rsp+28h+arg_0], 0
0x18001f668  mov     rax, [rbx]
0x18001f66b  lea     r8, [rsp+28h+arg_0]
0x18001f670  lea     rdx, _GUID_96369f54_8eb6_48f0_abce_c1b211e627c3
0x18001f677  mov     rcx, rbx
0x18001f67a  mov     rax, [rax]
0x18001f67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f682  mov     edi, eax
0x18001f684  test    eax, eax
0x18001f686  jns     short loc_18001F6D9
0x18001f688  mov     rcx, [rsp+28h]; this
0x18001f68d  mov     r9d, eax; char *
0x18001f690  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f697  mov     edx, 0ADh; void *
0x18001f69c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f6a1  nop
0x18001f6a2  mov     rcx, [rsp+28h+arg_0]
0x18001f6a7  test    rcx, rcx
0x18001f6aa  jz      short loc_18001F6C2
0x18001f6ac  mov     [rsp+28h+arg_0], 0
0x18001f6b5  mov     rax, [rcx]
0x18001f6b8  mov     rax, [rax+10h]
0x18001f6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6c1  nop
0x18001f6c2  mov     rax, [rbx]
0x18001f6c5  mov     rcx, rbx
0x18001f6c8  mov     rax, [rax+10h]
0x18001f6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6d1  nop
0x18001f6d2  mov     eax, edi
0x18001f6d4  jmp     loc_18001F771
0x18001f6d9  mov     rcx, [rsp+28h+arg_0]
0x18001f6de  mov     rax, [rcx]
0x18001f6e1  mov     rdx, rsi
0x18001f6e4  mov     rax, [rax+30h]
0x18001f6e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6ed  mov     edi, eax
0x18001f6ef  test    eax, eax
0x18001f6f1  jns     short loc_18001F73F
0x18001f6f3  mov     rcx, [rsp+28h]; this
0x18001f6f8  mov     r9d, eax; char *
0x18001f6fb  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f702  mov     edx, 0AFh; void *
0x18001f707  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f70c  nop
0x18001f70d  mov     rcx, [rsp+28h+arg_0]
0x18001f712  test    rcx, rcx
0x18001f715  jz      short loc_18001F72D
0x18001f717  mov     [rsp+28h+arg_0], 0
0x18001f720  mov     rax, [rcx]
0x18001f723  mov     rax, [rax+10h]
0x18001f727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f72c  nop
0x18001f72d  mov     rax, [rbx]
0x18001f730  mov     rcx, rbx
0x18001f733  mov     rax, [rax+10h]
0x18001f737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f73c  nop
0x18001f73d  jmp     short loc_18001F6D2
0x18001f73f  mov     rcx, [rsp+28h+arg_0]
0x18001f744  test    rcx, rcx
0x18001f747  jz      short loc_18001F75F
0x18001f749  mov     [rsp+28h+arg_0], 0
0x18001f752  mov     rax, [rcx]
0x18001f755  mov     rax, [rax+10h]
0x18001f759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f75e  nop
0x18001f75f  mov     rax, [rbx]
0x18001f762  mov     rcx, rbx
0x18001f765  mov     rax, [rax+10h]
0x18001f769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f76e  nop
0x18001f76f  xor     eax, eax
0x18001f771  mov     rbx, [rsp+28h+arg_8]
0x18001f776  mov     rsi, [rsp+28h+arg_10]
0x18001f77b  add     rsp, 20h
0x18001f77f  pop     rdi
0x18001f780  retn
```
