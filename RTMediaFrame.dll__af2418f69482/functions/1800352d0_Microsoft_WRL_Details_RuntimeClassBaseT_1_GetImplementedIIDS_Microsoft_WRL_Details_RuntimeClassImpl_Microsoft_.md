# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>> *,ulong *,_GUID * *)

- ea: `0x1800352d0`
- end: `0x180035371`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIAudioFrame@Media@7@U?$CloakedIid@UIAudioFrameNative@@@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIAudioFrame@Media@7@U?$CloakedIid@UIAudioFrameNative@@@23@@123@PEAKPEAPEAU_GUID@@@Z`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035450`

## callees

- `0x1800352d0`
- `0x180035424`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800352f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800352f7`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IAudioFrame,Microsoft::WRL::CloakedIid<IAudioFrameNative>>>(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  unsigned int v8; // edx
  __int64 v9; // r8
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = a1;
  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x40u);
  if ( !v6 )
    return 2147942414LL;
  LODWORD(v10) = 0;
  Microsoft::WRL::Implements<Windows::Media::IMediaFrame,Microsoft::WRL::FtmBase>::FillArrayWithIid(v5, &v10, v6);
  v8 = v10 + 1;
  *(GUID *)(v9 + 16LL * (unsigned int)v10) = GUID_00000038_0000_0000_c000_000000000046;
  *(GUID *)(v9 + 16LL * v8) = GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e;
  result = 0;
  *(GUID *)(v9 + 16LL * (v8 + 1)) = GUID_e36ac304_aab2_4277_9ed0_43cedf8e29c6;
  *a2 = 4;
  *a3 = v9;
  return result;
}

```

## disassembly

```asm
0x1800352d0  mov     [rsp+arg_8], rbx
0x1800352d5  mov     [rsp+arg_0], rcx
0x1800352da  push    rdi
0x1800352db  sub     rsp, 20h
0x1800352df  mov     qword ptr [r8], 0
0x1800352e6  mov     ecx, 40h ; '@'; cb
0x1800352eb  mov     dword ptr [rdx], 0
0x1800352f1  mov     rbx, r8
0x1800352f4  mov     rdi, rdx
0x1800352f7  call    cs:__imp_CoTaskMemAlloc
0x1800352fd  mov     r8, rax
0x180035300  test    rax, rax
0x180035303  jnz     short loc_18003530C
0x180035305  mov     eax, 8007000Eh
0x18003530a  jmp     short loc_180035366
0x18003530c  lea     rdx, [rsp+28h+arg_0]
0x180035311  mov     dword ptr [rsp+28h+arg_0], 0
0x180035319  call    ?FillArrayWithIid@?$Implements@UIMediaFrame@Media@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Windows::Media::IMediaFrame,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003531e  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180035325  mov     edx, dword ptr [rsp+28h+arg_0]
0x180035329  mov     eax, edx
0x18003532b  add     rax, rax
0x18003532e  inc     edx
0x180035330  movdqu  xmmword ptr [r8+rax*8], xmm0
0x180035336  mov     eax, edx
0x180035338  lea     ecx, [rdx+1]
0x18003533b  movups  xmm0, xmmword ptr cs:_GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e.Data1
0x180035342  add     rax, rax
0x180035345  add     rcx, rcx
0x180035348  movdqu  xmmword ptr [r8+rax*8], xmm0
0x18003534e  xor     eax, eax
0x180035350  movups  xmm0, xmmword ptr cs:_GUID_e36ac304_aab2_4277_9ed0_43cedf8e29c6.Data1
0x180035357  movdqu  xmmword ptr [r8+rcx*8], xmm0
0x18003535d  mov     dword ptr [rdi], 4
0x180035363  mov     [rbx], r8
0x180035366  mov     rbx, [rsp+28h+arg_8]
0x18003536b  add     rsp, 20h
0x18003536f  pop     rdi
0x180035370  retn
```
