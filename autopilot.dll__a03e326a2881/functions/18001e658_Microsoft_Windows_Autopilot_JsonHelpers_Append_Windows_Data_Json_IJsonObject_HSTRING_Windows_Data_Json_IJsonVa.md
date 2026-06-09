# Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,HSTRING__ *,Windows::Data::Json::IJsonValue *)

- ea: `0x18001e658`
- end: `0x18001e7ab`
- name: `?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEAUHSTRING__@@PEAUIJsonValue@673@@Z`
- size: `339`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, HSTRING, struct Windows::Data::Json::IJsonValue *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e7b4`
- `0x18001ea04`

## callees

- `0x1800105f4`
- `0x18001e658`
- `0x18002e010`

## string_xrefs

- `0x18001e6b0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001e728`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Autopilot::JsonHelpers::Append(
        struct Windows::Data::Json::IJsonObject *a1,
        HSTRING a2,
        struct Windows::Data::Json::IJsonValue *a3)
{
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+68h] [rbp+20h] BYREF

  if ( a1 )
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)a1 + 8LL))(a1);
  v16 = 0;
  v6 = (**(__int64 (__fastcall ***)(struct Windows::Data::Json::IJsonObject *, GUID *, __int64 *))a1)(
         a1,
         &GUID_c9d9a725_786b_5113_b4b7_9b61764c220b,
         &v16);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v6,
      v13);
    v8 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
LABEL_6:
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)a1 + 16LL))(a1);
    return v7;
  }
  v15 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Data::Json::IJsonValue *, char *))(*(_QWORD *)v16 + 80LL))(
          v16,
          a2,
          a3,
          &v15);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v10,
      v13);
    v11 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    goto LABEL_6;
  }
  v12 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x18001e658  mov     [rsp+arg_8], rbx
0x18001e65d  push    rbp
0x18001e65e  push    rsi
0x18001e65f  push    rdi
0x18001e660  sub     rsp, 30h
0x18001e664  mov     rsi, r8
0x18001e667  mov     rbp, rdx
0x18001e66a  mov     rbx, rcx
0x18001e66d  test    rcx, rcx
0x18001e670  jz      short loc_18001E67F
0x18001e672  mov     rax, [rcx]
0x18001e675  mov     rax, [rax+8]
0x18001e679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e67e  nop
0x18001e67f  mov     [rsp+48h+arg_18], 0
0x18001e688  mov     rax, [rbx]
0x18001e68b  lea     r8, [rsp+48h+arg_18]
0x18001e690  lea     rdx, _GUID_c9d9a725_786b_5113_b4b7_9b61764c220b
0x18001e697  mov     rcx, rbx
0x18001e69a  mov     rax, [rax]
0x18001e69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6a2  mov     edi, eax
0x18001e6a4  test    eax, eax
0x18001e6a6  jns     short loc_18001E6F9
0x18001e6a8  mov     rcx, [rsp+48h]; this
0x18001e6ad  mov     r9d, eax; char *
0x18001e6b0  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e6b7  mov     edx, 53h ; 'S'; void *
0x18001e6bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e6c1  nop
0x18001e6c2  mov     rcx, [rsp+48h+arg_18]
0x18001e6c7  test    rcx, rcx
0x18001e6ca  jz      short loc_18001E6E2
0x18001e6cc  mov     [rsp+48h+arg_18], 0
0x18001e6d5  mov     rax, [rcx]
0x18001e6d8  mov     rax, [rax+10h]
0x18001e6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6e1  nop
0x18001e6e2  mov     rax, [rbx]
0x18001e6e5  mov     rcx, rbx
0x18001e6e8  mov     rax, [rax+10h]
0x18001e6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6f1  nop
0x18001e6f2  mov     eax, edi
0x18001e6f4  jmp     loc_18001E79E
0x18001e6f9  mov     [rsp+48h+arg_0], 0
0x18001e6fe  mov     rcx, [rsp+48h+arg_18]
0x18001e703  mov     rax, [rcx]
0x18001e706  lea     r9, [rsp+48h+arg_0]
0x18001e70b  mov     r8, rsi
0x18001e70e  mov     rdx, rbp
0x18001e711  mov     rax, [rax+50h]
0x18001e715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e71a  mov     edi, eax
0x18001e71c  test    eax, eax
0x18001e71e  jns     short loc_18001E76C
0x18001e720  mov     rcx, [rsp+48h]; this
0x18001e725  mov     r9d, eax; char *
0x18001e728  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e72f  mov     edx, 56h ; 'V'; void *
0x18001e734  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e739  nop
0x18001e73a  mov     rcx, [rsp+48h+arg_18]
0x18001e73f  test    rcx, rcx
0x18001e742  jz      short loc_18001E75A
0x18001e744  mov     [rsp+48h+arg_18], 0
0x18001e74d  mov     rax, [rcx]
0x18001e750  mov     rax, [rax+10h]
0x18001e754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e759  nop
0x18001e75a  mov     rax, [rbx]
0x18001e75d  mov     rcx, rbx
0x18001e760  mov     rax, [rax+10h]
0x18001e764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e769  nop
0x18001e76a  jmp     short loc_18001E6F2
0x18001e76c  mov     rcx, [rsp+48h+arg_18]
0x18001e771  test    rcx, rcx
0x18001e774  jz      short loc_18001E78C
0x18001e776  mov     [rsp+48h+arg_18], 0
0x18001e77f  mov     rax, [rcx]
0x18001e782  mov     rax, [rax+10h]
0x18001e786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e78b  nop
0x18001e78c  mov     rax, [rbx]
0x18001e78f  mov     rcx, rbx
0x18001e792  mov     rax, [rax+10h]
0x18001e796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e79b  nop
0x18001e79c  xor     eax, eax
0x18001e79e  mov     rbx, [rsp+48h+arg_8]
0x18001e7a3  add     rsp, 30h
0x18001e7a7  pop     rdi
0x18001e7a8  pop     rsi
0x18001e7a9  pop     rbp
0x18001e7aa  retn
```
