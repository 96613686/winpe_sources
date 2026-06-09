# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::Media::IAudioFrameFactory,IAudioFrameNativeFactory>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18002bbb0`
- end: `0x18002bc1d`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$Implements@UIAudioFrameFactory@Media@Windows@@UIAudioFrameNativeFactory@@@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002bc30`
- `0x18002bc40`

## callees

- `0x18002bbb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bbd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bbd2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::Media::IAudioFrameFactory,IAudioFrameNativeFactory>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  v5[1] = GUID_91a90ade_2422_40a6_b9ad_30d02404317d;
  v5[2] = GUID_7bd67cf8_bf7d_43e6_af8d_b170ee0c0110;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18002bbb0  mov     [rsp+arg_0], rbx
0x18002bbb5  push    rdi
0x18002bbb6  sub     rsp, 20h
0x18002bbba  mov     qword ptr [r8], 0
0x18002bbc1  mov     ecx, 30h ; '0'; cb
0x18002bbc6  mov     dword ptr [rdx], 0
0x18002bbcc  mov     rbx, r8
0x18002bbcf  mov     rdi, rdx
0x18002bbd2  call    cs:__imp_CoTaskMemAlloc
0x18002bbd8  test    rax, rax
0x18002bbdb  jnz     short loc_18002BBE4
0x18002bbdd  mov     eax, 8007000Eh
0x18002bbe2  jmp     short loc_18002BC12
0x18002bbe4  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18002bbeb  movdqu  xmmword ptr [rax], xmm0
0x18002bbef  movups  xmm1, xmmword ptr cs:_GUID_91a90ade_2422_40a6_b9ad_30d02404317d.Data1
0x18002bbf6  movdqu  xmmword ptr [rax+10h], xmm1
0x18002bbfb  movups  xmm0, xmmword ptr cs:_GUID_7bd67cf8_bf7d_43e6_af8d_b170ee0c0110.Data1
0x18002bc02  movdqu  xmmword ptr [rax+20h], xmm0
0x18002bc07  mov     dword ptr [rdi], 3
0x18002bc0d  mov     [rbx], rax
0x18002bc10  xor     eax, eax
0x18002bc12  mov     rbx, [rsp+28h+arg_0]
0x18002bc17  add     rsp, 20h
0x18002bc1b  pop     rdi
0x18002bc1c  retn
```
