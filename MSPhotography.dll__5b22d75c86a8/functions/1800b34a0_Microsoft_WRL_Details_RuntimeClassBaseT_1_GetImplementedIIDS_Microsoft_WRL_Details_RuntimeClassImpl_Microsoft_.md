# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,CResultFrameBase,Windows::Media::Core::ISceneAnalysisEffectFrame,Windows::Media::Core::ISceneAnalysisEffectFrame2,Windows::Media::Core::ISceneAnalysisEffectFrameInternal>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,CResultFrameBase,Windows::Media::Core::ISceneAnalysisEffectFrame,Windows::Media::Core::ISceneAnalysisEffectFrame2,Windows::Media::Core::ISceneAnalysisEffectFrameInternal> *,ulong *,_GUID * *)

- ea: `0x1800b34a0`
- end: `0x1800b3555`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCResultFrameBase@@UISceneAnalysisEffectFrame@Core@Media@Windows@@UISceneAnalysisEffectFrame2@678@UISceneAnalysisEffectFrameInternal@678@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCResultFrameBase@@UISceneAnalysisEffectFrame@Core@Media@Windows@@UISceneAnalysisEffectFrame2@678@UISceneAnalysisEffectFrameInternal@678@@123@PEAKPEAPEAU_GUID@@@Z`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b4550`

## callees

- `0x180029d40`
- `0x1800b34a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b34c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b34c7`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,CResultFrameBase,Windows::Media::Core::ISceneAnalysisEffectFrame,Windows::Media::Core::ISceneAnalysisEffectFrame2,Windows::Media::Core::ISceneAnalysisEffectFrameInternal>>(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  unsigned int v8; // edx
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // [rsp+30h] [rbp+8h] BYREF

  v11 = a1;
  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x60u);
  if ( !v6 )
    return 2147942414LL;
  LODWORD(v11) = 0;
  Microsoft::WRL::Implements<Windows::Media::IMediaFrame,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v11,
    v6);
  v8 = v11 + 1;
  *(GUID *)(v9 + 16LL * (unsigned int)v11) = GUID_00000038_0000_0000_c000_000000000046;
  v10 = 2LL * v8++;
  *(GUID *)(v9 + 8 * v10) = GUID_d8b10e4c_7fd9_42e1_85eb_6572c297c987;
  *(GUID *)(v9 + 16LL * v8) = GUID_2d4e29be_061f_47ae_9915_02524b5f9a5f;
  result = 0;
  *(GUID *)(v9 + 16LL * (v8 + 1)) = GUID_4176c763_3dd1_4fb1_a64b_57dec6a90eed;
  *a2 = 6;
  *a3 = v9;
  return result;
}

```

## disassembly

```asm
0x1800b34a0  mov     [rsp+arg_8], rbx
0x1800b34a5  mov     [rsp+arg_0], rcx
0x1800b34aa  push    rdi
0x1800b34ab  sub     rsp, 20h
0x1800b34af  mov     qword ptr [r8], 0
0x1800b34b6  mov     ecx, 60h ; '`'; cb
0x1800b34bb  mov     dword ptr [rdx], 0
0x1800b34c1  mov     rbx, r8
0x1800b34c4  mov     rdi, rdx
0x1800b34c7  call    cs:__imp_CoTaskMemAlloc
0x1800b34cd  mov     r8, rax
0x1800b34d0  test    rax, rax
0x1800b34d3  jnz     short loc_1800B34DC
0x1800b34d5  mov     eax, 8007000Eh
0x1800b34da  jmp     short loc_1800B354A
0x1800b34dc  lea     rdx, [rsp+28h+arg_0]
0x1800b34e1  mov     dword ptr [rsp+28h+arg_0], 0
0x1800b34e9  call    ?FillArrayWithIid@?$Implements@UIMediaFrame@Media@Windows@@UIClosable@Foundation@3@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Windows::Media::IMediaFrame,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800b34ee  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800b34f5  mov     edx, dword ptr [rsp+28h+arg_0]
0x1800b34f9  mov     eax, edx
0x1800b34fb  add     rax, rax
0x1800b34fe  inc     edx
0x1800b3500  movdqu  xmmword ptr [r8+rax*8], xmm0
0x1800b3506  mov     eax, edx
0x1800b3508  movups  xmm0, xmmword ptr cs:_GUID_d8b10e4c_7fd9_42e1_85eb_6572c297c987.Data1
0x1800b350f  add     rax, rax
0x1800b3512  inc     edx
0x1800b3514  movdqu  xmmword ptr [r8+rax*8], xmm0
0x1800b351a  mov     eax, edx
0x1800b351c  lea     ecx, [rdx+1]
0x1800b351f  movups  xmm0, xmmword ptr cs:_GUID_2d4e29be_061f_47ae_9915_02524b5f9a5f.Data1
0x1800b3526  add     rax, rax
0x1800b3529  add     rcx, rcx
0x1800b352c  movdqu  xmmword ptr [r8+rax*8], xmm0
0x1800b3532  xor     eax, eax
0x1800b3534  movups  xmm0, xmmword ptr cs:_GUID_4176c763_3dd1_4fb1_a64b_57dec6a90eed.Data1
0x1800b353b  movdqu  xmmword ptr [r8+rcx*8], xmm0
0x1800b3541  mov     dword ptr [rdi], 6
0x1800b3547  mov     [rbx], r8
0x1800b354a  mov     rbx, [rsp+28h+arg_8]
0x1800b354f  add     rsp, 20h
0x1800b3553  pop     rdi
0x1800b3554  retn
```
