# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::Media::IVideoFrameFactory,Windows::Media::IVideoFrameStatics,IVideoFrameNativeFactory,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternalFactory>>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18002bd00`
- end: `0x18002bd79`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$Implements@UIVideoFrameFactory@Media@Windows@@UIVideoFrameStatics@23@UIVideoFrameNativeFactory@@U?$CloakedIid@UIVideoFrameInternalFactory@Internal@Media@Windows@@@WRL@Microsoft@@@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002bd80`
- `0x18002bd90`
- `0x18002bda0`
- `0x18002bdb0`

## callees

- `0x18002bd00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bd22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bd22`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::Media::IVideoFrameFactory,Windows::Media::IVideoFrameStatics,IVideoFrameNativeFactory,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternalFactory>>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  v5[1] = GUID_014b6d69_2228_4c92_92ff_50c380d3e776;
  v5[2] = GUID_ab2a556f_6111_4b33_8ec3_2b209a02e17a;
  v5[3] = GUID_69e3693e_8e1e_4e63_ac4c_7fdc21d9731d;
  *a2 = 4;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18002bd00  mov     [rsp+arg_0], rbx
0x18002bd05  push    rdi
0x18002bd06  sub     rsp, 20h
0x18002bd0a  mov     qword ptr [r8], 0
0x18002bd11  mov     ecx, 40h ; '@'; cb
0x18002bd16  mov     dword ptr [rdx], 0
0x18002bd1c  mov     rbx, r8
0x18002bd1f  mov     rdi, rdx
0x18002bd22  call    cs:__imp_CoTaskMemAlloc
0x18002bd28  test    rax, rax
0x18002bd2b  jnz     short loc_18002BD34
0x18002bd2d  mov     eax, 8007000Eh
0x18002bd32  jmp     short loc_18002BD6E
0x18002bd34  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18002bd3b  movdqu  xmmword ptr [rax], xmm0
0x18002bd3f  movups  xmm1, xmmword ptr cs:_GUID_014b6d69_2228_4c92_92ff_50c380d3e776.Data1
0x18002bd46  movdqu  xmmword ptr [rax+10h], xmm1
0x18002bd4b  movups  xmm0, xmmword ptr cs:_GUID_ab2a556f_6111_4b33_8ec3_2b209a02e17a.Data1
0x18002bd52  movdqu  xmmword ptr [rax+20h], xmm0
0x18002bd57  movups  xmm1, xmmword ptr cs:_GUID_69e3693e_8e1e_4e63_ac4c_7fdc21d9731d.Data1
0x18002bd5e  movdqu  xmmword ptr [rax+30h], xmm1
0x18002bd63  mov     dword ptr [rdi], 4
0x18002bd69  mov     [rbx], rax
0x18002bd6c  xor     eax, eax
0x18002bd6e  mov     rbx, [rsp+28h+arg_0]
0x18002bd73  add     rsp, 20h
0x18002bd77  pop     rdi
0x18002bd78  retn
```
