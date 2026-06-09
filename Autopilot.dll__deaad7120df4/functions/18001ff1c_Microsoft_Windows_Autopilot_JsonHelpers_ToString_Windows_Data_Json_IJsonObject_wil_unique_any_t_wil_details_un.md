# Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x18001ff1c`
- end: `0x180020066`
- name: `?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fcec`
- `0x180024878`
- `0x180025958`

## callees

- `0x180010764`
- `0x18001ff1c`
- `0x18002f010`

## string_xrefs

- `0x18001ff74`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001ffdf`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

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
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v12; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v12 = 0;
  v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
         a1,
         &GUID_96369f54_8eb6_48f0_abce_c1b211e627c3,
         &v12);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v4);
    v6 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
LABEL_6:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
    return v5;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 48LL))(v12, a2);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v8);
    v9 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    goto LABEL_6;
  }
  v10 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x18001ff1c  mov     [rsp+arg_8], rbx
0x18001ff21  mov     [rsp+arg_10], rsi
0x18001ff26  push    rdi; int
0x18001ff27  sub     rsp, 20h
0x18001ff2b  mov     rsi, rdx
0x18001ff2e  mov     rbx, rcx
0x18001ff31  test    rcx, rcx
0x18001ff34  jz      short loc_18001FF43
0x18001ff36  mov     rax, [rcx]
0x18001ff39  mov     rax, [rax+8]
0x18001ff3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff42  nop
0x18001ff43  mov     [rsp+28h+arg_0], 0
0x18001ff4c  mov     rax, [rbx]
0x18001ff4f  lea     r8, [rsp+28h+arg_0]
0x18001ff54  lea     rdx, _GUID_96369f54_8eb6_48f0_abce_c1b211e627c3
0x18001ff5b  mov     rcx, rbx
0x18001ff5e  mov     rax, [rax]
0x18001ff61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff66  mov     edi, eax
0x18001ff68  test    eax, eax
0x18001ff6a  jns     short loc_18001FFBD
0x18001ff6c  mov     rcx, [rsp+28h]; this
0x18001ff71  mov     r9d, eax; char *
0x18001ff74  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ff7b  mov     edx, 0ADh; void *
0x18001ff80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ff85  nop
0x18001ff86  mov     rcx, [rsp+28h+arg_0]
0x18001ff8b  test    rcx, rcx
0x18001ff8e  jz      short loc_18001FFA6
0x18001ff90  mov     [rsp+28h+arg_0], 0
0x18001ff99  mov     rax, [rcx]
0x18001ff9c  mov     rax, [rax+10h]
0x18001ffa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffa5  nop
0x18001ffa6  mov     rax, [rbx]
0x18001ffa9  mov     rcx, rbx
0x18001ffac  mov     rax, [rax+10h]
0x18001ffb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffb5  nop
0x18001ffb6  mov     eax, edi
0x18001ffb8  jmp     loc_180020055
0x18001ffbd  mov     rcx, [rsp+28h+arg_0]
0x18001ffc2  mov     rax, [rcx]
0x18001ffc5  mov     rdx, rsi
0x18001ffc8  mov     rax, [rax+30h]
0x18001ffcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffd1  mov     edi, eax
0x18001ffd3  test    eax, eax
0x18001ffd5  jns     short loc_180020023
0x18001ffd7  mov     rcx, [rsp+28h]; this
0x18001ffdc  mov     r9d, eax; char *
0x18001ffdf  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ffe6  mov     edx, 0AFh; void *
0x18001ffeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fff0  nop
0x18001fff1  mov     rcx, [rsp+28h+arg_0]
0x18001fff6  test    rcx, rcx
0x18001fff9  jz      short loc_180020011
0x18001fffb  mov     [rsp+28h+arg_0], 0
0x180020004  mov     rax, [rcx]
0x180020007  mov     rax, [rax+10h]
0x18002000b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020010  nop
0x180020011  mov     rax, [rbx]
0x180020014  mov     rcx, rbx
0x180020017  mov     rax, [rax+10h]
0x18002001b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020020  nop
0x180020021  jmp     short loc_18001FFB6
0x180020023  mov     rcx, [rsp+28h+arg_0]
0x180020028  test    rcx, rcx
0x18002002b  jz      short loc_180020043
0x18002002d  mov     [rsp+28h+arg_0], 0
0x180020036  mov     rax, [rcx]
0x180020039  mov     rax, [rax+10h]
0x18002003d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020042  nop
0x180020043  mov     rax, [rbx]
0x180020046  mov     rcx, rbx
0x180020049  mov     rax, [rax+10h]
0x18002004d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020052  nop
0x180020053  xor     eax, eax
0x180020055  mov     rbx, [rsp+28h+arg_8]
0x18002005a  mov     rsi, [rsp+28h+arg_10]
0x18002005f  add     rsp, 20h
0x180020063  pop     rdi
0x180020064  retn
```
