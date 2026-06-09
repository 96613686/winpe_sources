# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::Graphics::Imaging::ISoftwareBitmapFactory,Windows::Graphics::Imaging::ISoftwareBitmapStatics,Microsoft::WRL::CloakedIid<ISoftwareBitmapNativeFactory>>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18002bc50`
- end: `0x18002bcbd`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$Implements@UISoftwareBitmapFactory@Imaging@Graphics@Windows@@UISoftwareBitmapStatics@234@U?$CloakedIid@UISoftwareBitmapNativeFactory@@@WRL@Microsoft@@@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002bcd0`
- `0x18002bce0`
- `0x18002bcf0`

## callees

- `0x18002bc50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bc72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bc72`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::Graphics::Imaging::ISoftwareBitmapFactory,Windows::Graphics::Imaging::ISoftwareBitmapStatics,Microsoft::WRL::CloakedIid<ISoftwareBitmapNativeFactory>>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  v5[1] = GUID_c99feb69_2d62_4d47_a6b3_4fdb6a07fdf8;
  v5[2] = GUID_df0385db_672f_4a9d_806e_c2442f343e86;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18002bc50  mov     [rsp+arg_0], rbx
0x18002bc55  push    rdi
0x18002bc56  sub     rsp, 20h
0x18002bc5a  mov     qword ptr [r8], 0
0x18002bc61  mov     ecx, 30h ; '0'; cb
0x18002bc66  mov     dword ptr [rdx], 0
0x18002bc6c  mov     rbx, r8
0x18002bc6f  mov     rdi, rdx
0x18002bc72  call    cs:__imp_CoTaskMemAlloc
0x18002bc78  test    rax, rax
0x18002bc7b  jnz     short loc_18002BC84
0x18002bc7d  mov     eax, 8007000Eh
0x18002bc82  jmp     short loc_18002BCB2
0x18002bc84  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18002bc8b  movdqu  xmmword ptr [rax], xmm0
0x18002bc8f  movups  xmm1, xmmword ptr cs:_GUID_c99feb69_2d62_4d47_a6b3_4fdb6a07fdf8.Data1
0x18002bc96  movdqu  xmmword ptr [rax+10h], xmm1
0x18002bc9b  movups  xmm0, xmmword ptr cs:_GUID_df0385db_672f_4a9d_806e_c2442f343e86.Data1
0x18002bca2  movdqu  xmmword ptr [rax+20h], xmm0
0x18002bca7  mov     dword ptr [rdi], 3
0x18002bcad  mov     [rbx], rax
0x18002bcb0  xor     eax, eax
0x18002bcb2  mov     rbx, [rsp+28h+arg_0]
0x18002bcb7  add     rsp, 20h
0x18002bcbb  pop     rdi
0x18002bcbc  retn
```
