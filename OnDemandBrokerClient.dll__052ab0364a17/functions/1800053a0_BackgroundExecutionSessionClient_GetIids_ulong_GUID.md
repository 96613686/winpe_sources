# BackgroundExecutionSessionClient::GetIids(ulong *,_GUID * *)

- ea: `0x1800053a0`
- end: `0x18000540a`
- name: `?GetIids@BackgroundExecutionSessionClient@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(BackgroundExecutionSessionClient *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005410`

## callees

- `0x180005364`
- `0x1800053a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800053c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800053c2`

## pseudocode

```c
__int64 __fastcall BackgroundExecutionSessionClient::GetIids(
        BackgroundExecutionSessionClient *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IInspectable>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800053a0  mov     [rsp+arg_0], rbx
0x1800053a5  push    rdi
0x1800053a6  sub     rsp, 20h
0x1800053aa  mov     qword ptr [r8], 0
0x1800053b1  mov     ecx, 30h ; '0'; cb
0x1800053b6  mov     dword ptr [rdx], 0
0x1800053bc  mov     rbx, r8
0x1800053bf  mov     rdi, rdx
0x1800053c2  call    cs:__imp_CoTaskMemAlloc
0x1800053c8  mov     r8, rax
0x1800053cb  test    rax, rax
0x1800053ce  jnz     short loc_1800053D7
0x1800053d0  mov     eax, 8007000Eh
0x1800053d5  jmp     short loc_1800053FF
0x1800053d7  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x1800053de  lea     rdx, [rsp+28h+arg_8]
0x1800053e3  mov     [rsp+28h+arg_8], 1
0x1800053eb  movdqu  xmmword ptr [rax], xmm0
0x1800053ef  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@UIInspectable@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IInspectable>::FillArrayWithIid(ulong *,_GUID *)
0x1800053f4  mov     dword ptr [rdi], 3
0x1800053fa  xor     eax, eax
0x1800053fc  mov     [rbx], r8
0x1800053ff  mov     rbx, [rsp+28h+arg_0]
0x180005404  add     rsp, 20h
0x180005408  pop     rdi
0x180005409  retn
```
