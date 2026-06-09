# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsBase,Windows::ApplicationModel::Activation::IPhoneCallActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18000ac00`
- end: `0x18000ac79`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VCActivatedEventArgsBase@@UIPhoneCallActivatedEventArgs@Activation@ApplicationModel@Windows@@U?$CloakedIid@UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ac80`
- `0x18000ac90`
- `0x18000aca0`
- `0x18000acb0`
- `0x18000acd0`
- `0x18000acf0`

## callees

- `0x18000ac00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ac22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ac22`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsBase,Windows::ApplicationModel::Activation::IPhoneCallActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_cf651713_cd08_4fd8_b697_a281b6544e2e;
  v5[1] = GUID_1cf09b9e_9962_4936_80ff_afc8e8ae5c8c;
  v5[2] = GUID_00000038_0000_0000_c000_000000000046;
  v5[3] = GUID_54615221_a3c1_4ced_b62f_8c60523619ad;
  *a2 = 4;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000ac00  mov     [rsp+arg_0], rbx
0x18000ac05  push    rdi
0x18000ac06  sub     rsp, 20h
0x18000ac0a  mov     qword ptr [r8], 0
0x18000ac11  mov     ecx, 40h ; '@'; cb
0x18000ac16  mov     dword ptr [rdx], 0
0x18000ac1c  mov     rbx, r8
0x18000ac1f  mov     rdi, rdx
0x18000ac22  call    cs:__imp_CoTaskMemAlloc
0x18000ac28  test    rax, rax
0x18000ac2b  jnz     short loc_18000AC34
0x18000ac2d  mov     eax, 8007000Eh
0x18000ac32  jmp     short loc_18000AC6E
0x18000ac34  movups  xmm0, xmmword ptr cs:_GUID_cf651713_cd08_4fd8_b697_a281b6544e2e.Data1
0x18000ac3b  movdqu  xmmword ptr [rax], xmm0
0x18000ac3f  movups  xmm1, xmmword ptr cs:_GUID_1cf09b9e_9962_4936_80ff_afc8e8ae5c8c.Data1
0x18000ac46  movdqu  xmmword ptr [rax+10h], xmm1
0x18000ac4b  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18000ac52  movdqu  xmmword ptr [rax+20h], xmm0
0x18000ac57  movups  xmm1, xmmword ptr cs:_GUID_54615221_a3c1_4ced_b62f_8c60523619ad.Data1
0x18000ac5e  movdqu  xmmword ptr [rax+30h], xmm1
0x18000ac63  mov     dword ptr [rdi], 4
0x18000ac69  mov     [rbx], rax
0x18000ac6c  xor     eax, eax
0x18000ac6e  mov     rbx, [rsp+28h+arg_0]
0x18000ac73  add     rsp, 20h
0x18000ac77  pop     rdi
0x18000ac78  retn
```
