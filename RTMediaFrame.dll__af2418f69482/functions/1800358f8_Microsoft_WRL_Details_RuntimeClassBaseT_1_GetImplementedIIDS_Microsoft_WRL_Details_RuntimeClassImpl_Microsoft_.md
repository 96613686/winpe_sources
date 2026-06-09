# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>> *,ulong *,_GUID * *)

- ea: `0x1800358f8`
- end: `0x180035997`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIVideoFrame@Media@7@UIVideoFrame2@97@U?$CloakedIid@UIVideoFrameNative@@@23@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIVideoFrame@Media@7@UIVideoFrame2@97@U?$CloakedIid@UIVideoFrameNative@@@23@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@123@PEAKPEAPEAU_GUID@@@Z`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037b80`

## callees

- `0x180035424`
- `0x1800358f8`
- `0x1800375fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003591f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003591f`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>>(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  unsigned int v8; // edx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // [rsp+30h] [rbp+8h] BYREF

  v12 = a1;
  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x50u);
  if ( !v6 )
    return 2147942414LL;
  LODWORD(v12) = 0;
  Microsoft::WRL::Implements<Windows::Media::IMediaFrame,Microsoft::WRL::FtmBase>::FillArrayWithIid(v5, &v12, v6);
  v8 = v12 + 1;
  *(GUID *)(v9 + 16LL * (unsigned int)v12) = GUID_00000038_0000_0000_c000_000000000046;
  *(GUID *)(v9 + 16LL * v8) = GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e;
  LODWORD(v12) = v8 + 1;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>::FillArrayWithIid(
    v10,
    &v12);
  *a2 = 5;
  result = 0;
  *a3 = v11;
  return result;
}

```

## disassembly

```asm
0x1800358f8  mov     [rsp+arg_8], rbx
0x1800358fd  mov     [rsp+arg_0], rcx
0x180035902  push    rdi
0x180035903  sub     rsp, 20h
0x180035907  mov     qword ptr [r8], 0
0x18003590e  mov     ecx, 50h ; 'P'; cb
0x180035913  mov     dword ptr [rdx], 0
0x180035919  mov     rbx, r8
0x18003591c  mov     rdi, rdx
0x18003591f  call    cs:__imp_CoTaskMemAlloc
0x180035925  mov     r8, rax
0x180035928  test    rax, rax
0x18003592b  jnz     short loc_180035934
0x18003592d  mov     eax, 8007000Eh
0x180035932  jmp     short loc_18003598C
0x180035934  lea     rdx, [rsp+28h+arg_0]
0x180035939  mov     dword ptr [rsp+28h+arg_0], 0
0x180035941  call    ?FillArrayWithIid@?$Implements@UIMediaFrame@Media@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Windows::Media::IMediaFrame,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180035946  mov     edx, dword ptr [rsp+28h+arg_0]
0x18003594a  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180035951  mov     eax, edx
0x180035953  add     rax, rax
0x180035956  inc     edx
0x180035958  movdqu  xmmword ptr [r8+rax*8], xmm0
0x18003595e  mov     eax, edx
0x180035960  movups  xmm0, xmmword ptr cs:_GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e.Data1
0x180035967  add     rax, rax
0x18003596a  movdqu  xmmword ptr [r8+rax*8], xmm0
0x180035970  lea     eax, [rdx+1]
0x180035973  lea     rdx, [rsp+28h+arg_0]
0x180035978  mov     dword ptr [rsp+28h+arg_0], eax
0x18003597c  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIVideoFrame@Media@Windows@@UIVideoFrame2@56@U?$CloakedIid@UIVideoFrameNative@@@23@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>::FillArrayWithIid(ulong *,_GUID *)
0x180035981  mov     dword ptr [rdi], 5
0x180035987  xor     eax, eax
0x180035989  mov     [rbx], r8
0x18003598c  mov     rbx, [rsp+28h+arg_8]
0x180035991  add     rsp, 20h
0x180035995  pop     rdi
0x180035996  retn
```
