# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Core::IFaceDetectionEffectDefinition,Windows::Media::Effects::IVideoEffectDefinition,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18000b400`
- end: `0x18000b46a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIFaceDetectionEffectDefinition@Core@Media@Windows@@UIVideoEffectDefinition@Effects@67@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b470`

## callees

- `0x18000b3dc`
- `0x18000b400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b422`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b422`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Core::IFaceDetectionEffectDefinition,Windows::Media::Effects::IVideoEffectDefinition,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_43dca081_b848_4f33_b702_1fd2624fb016;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Media::Effects::IVideoEffectDefinition,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18000b400  mov     [rsp+arg_0], rbx
0x18000b405  push    rdi
0x18000b406  sub     rsp, 20h
0x18000b40a  mov     qword ptr [r8], 0
0x18000b411  mov     ecx, 30h ; '0'; cb
0x18000b416  mov     dword ptr [rdx], 0
0x18000b41c  mov     rbx, r8
0x18000b41f  mov     rdi, rdx
0x18000b422  call    cs:__imp_CoTaskMemAlloc
0x18000b428  mov     r8, rax
0x18000b42b  test    rax, rax
0x18000b42e  jnz     short loc_18000B437
0x18000b430  mov     eax, 8007000Eh
0x18000b435  jmp     short loc_18000B45F
0x18000b437  movups  xmm0, xmmword ptr cs:_GUID_43dca081_b848_4f33_b702_1fd2624fb016.Data1
0x18000b43e  lea     rdx, [rsp+28h+arg_8]
0x18000b443  mov     [rsp+28h+arg_8], 1
0x18000b44b  movdqu  xmmword ptr [rax], xmm0
0x18000b44f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIVideoEffectDefinition@Effects@Media@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Media::Effects::IVideoEffectDefinition,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18000b454  mov     dword ptr [rdi], 3
0x18000b45a  xor     eax, eax
0x18000b45c  mov     [rbx], r8
0x18000b45f  mov     rbx, [rsp+28h+arg_0]
0x18000b464  add     rsp, 20h
0x18000b468  pop     rdi
0x18000b469  retn
```
