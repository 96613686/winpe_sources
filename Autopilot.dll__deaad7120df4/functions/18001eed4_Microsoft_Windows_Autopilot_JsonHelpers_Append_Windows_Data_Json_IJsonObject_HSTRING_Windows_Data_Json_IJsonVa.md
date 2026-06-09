# Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,HSTRING__ *,Windows::Data::Json::IJsonValue *)

- ea: `0x18001eed4`
- end: `0x18001f028`
- name: `?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEAUHSTRING__@@PEAUIJsonValue@673@@Z`
- size: `340`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, HSTRING, struct Windows::Data::Json::IJsonValue *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f030`
- `0x18001f28c`

## callees

- `0x180010764`
- `0x18001eed4`
- `0x18002f010`

## string_xrefs

- `0x18001ef2c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001efa4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

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
0x18001eed4  mov     [rsp+arg_8], rbx
0x18001eed9  push    rbp
0x18001eeda  push    rsi
0x18001eedb  push    rdi
0x18001eedc  sub     rsp, 30h
0x18001eee0  mov     rsi, r8
0x18001eee3  mov     rbp, rdx
0x18001eee6  mov     rbx, rcx
0x18001eee9  test    rcx, rcx
0x18001eeec  jz      short loc_18001EEFB
0x18001eeee  mov     rax, [rcx]
0x18001eef1  mov     rax, [rax+8]
0x18001eef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eefa  nop
0x18001eefb  mov     [rsp+48h+arg_18], 0
0x18001ef04  mov     rax, [rbx]
0x18001ef07  lea     r8, [rsp+48h+arg_18]
0x18001ef0c  lea     rdx, _GUID_c9d9a725_786b_5113_b4b7_9b61764c220b
0x18001ef13  mov     rcx, rbx
0x18001ef16  mov     rax, [rax]
0x18001ef19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef1e  mov     edi, eax
0x18001ef20  test    eax, eax
0x18001ef22  jns     short loc_18001EF75
0x18001ef24  mov     rcx, [rsp+48h]; this
0x18001ef29  mov     r9d, eax; char *
0x18001ef2c  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ef33  mov     edx, 53h ; 'S'; void *
0x18001ef38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef3d  nop
0x18001ef3e  mov     rcx, [rsp+48h+arg_18]
0x18001ef43  test    rcx, rcx
0x18001ef46  jz      short loc_18001EF5E
0x18001ef48  mov     [rsp+48h+arg_18], 0
0x18001ef51  mov     rax, [rcx]
0x18001ef54  mov     rax, [rax+10h]
0x18001ef58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef5d  nop
0x18001ef5e  mov     rax, [rbx]
0x18001ef61  mov     rcx, rbx
0x18001ef64  mov     rax, [rax+10h]
0x18001ef68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef6d  nop
0x18001ef6e  mov     eax, edi
0x18001ef70  jmp     loc_18001F01A
0x18001ef75  mov     [rsp+48h+arg_0], 0
0x18001ef7a  mov     rcx, [rsp+48h+arg_18]
0x18001ef7f  mov     rax, [rcx]
0x18001ef82  lea     r9, [rsp+48h+arg_0]
0x18001ef87  mov     r8, rsi
0x18001ef8a  mov     rdx, rbp
0x18001ef8d  mov     rax, [rax+50h]
0x18001ef91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef96  mov     edi, eax
0x18001ef98  test    eax, eax
0x18001ef9a  jns     short loc_18001EFE8
0x18001ef9c  mov     rcx, [rsp+48h]; this
0x18001efa1  mov     r9d, eax; char *
0x18001efa4  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001efab  mov     edx, 56h ; 'V'; void *
0x18001efb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001efb5  nop
0x18001efb6  mov     rcx, [rsp+48h+arg_18]
0x18001efbb  test    rcx, rcx
0x18001efbe  jz      short loc_18001EFD6
0x18001efc0  mov     [rsp+48h+arg_18], 0
0x18001efc9  mov     rax, [rcx]
0x18001efcc  mov     rax, [rax+10h]
0x18001efd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efd5  nop
0x18001efd6  mov     rax, [rbx]
0x18001efd9  mov     rcx, rbx
0x18001efdc  mov     rax, [rax+10h]
0x18001efe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efe5  nop
0x18001efe6  jmp     short loc_18001EF6E
0x18001efe8  mov     rcx, [rsp+48h+arg_18]
0x18001efed  test    rcx, rcx
0x18001eff0  jz      short loc_18001F008
0x18001eff2  mov     [rsp+48h+arg_18], 0
0x18001effb  mov     rax, [rcx]
0x18001effe  mov     rax, [rax+10h]
0x18001f002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f007  nop
0x18001f008  mov     rax, [rbx]
0x18001f00b  mov     rcx, rbx
0x18001f00e  mov     rax, [rax+10h]
0x18001f012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f017  nop
0x18001f018  xor     eax, eax
0x18001f01a  mov     rbx, [rsp+48h+arg_8]
0x18001f01f  add     rsp, 30h
0x18001f023  pop     rdi
0x18001f024  pop     rsi
0x18001f025  pop     rbp
0x18001f026  retn
```
