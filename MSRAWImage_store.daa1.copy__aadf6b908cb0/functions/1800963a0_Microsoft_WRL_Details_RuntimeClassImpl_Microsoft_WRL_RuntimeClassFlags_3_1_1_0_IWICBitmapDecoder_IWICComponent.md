# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWICBitmapDecoder,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800963a0`
- end: `0x18009642b`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIWICBitmapDecoder@@UIWICComponentInternal@@UIMediaExtension@Media@Windows@@U?$CloakedIid@UIMFTransform@@@23@U?$CloakedIid@UIMFTelemetryComponent@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180096440`

## callees

- `0x180096130`
- `0x1800963a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800963bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800963bf`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWICBitmapDecoder,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  GUID *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  int v10; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  *a3 = 0;
  *a2 = 0;
  v6 = (GUID *)CoTaskMemAlloc(0x50u);
  if ( v6 )
  {
    v10 = 3;
    *v6 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
    v6[1] = GUID_9edde9e7_8dee_47ea_99df_e6faf2ed44bf;
    v6[2] = GUID_00000038_0000_0000_c000_000000000046;
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
      v7,
      &v10,
      v6);
    *a2 = 5;
    *a3 = v8;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v3;
}

```

## disassembly

```asm
0x1800963a0  mov     [rsp+arg_0], rbx
0x1800963a5  mov     [rsp+arg_10], rsi
0x1800963aa  push    rdi
0x1800963ab  sub     rsp, 20h
0x1800963af  xor     ebx, ebx
0x1800963b1  mov     rdi, r8
0x1800963b4  mov     [r8], rbx
0x1800963b7  mov     rsi, rdx
0x1800963ba  mov     [rdx], ebx
0x1800963bc  lea     ecx, [rbx+50h]; cb
0x1800963bf  call    cs:__imp_CoTaskMemAlloc
0x1800963c6  nop     dword ptr [rax+rax+00h]
0x1800963cb  mov     r8, rax
0x1800963ce  test    rax, rax
0x1800963d1  jnz     short loc_1800963DA
0x1800963d3  mov     ebx, 8007000Eh
0x1800963d8  jmp     short loc_180096418
0x1800963da  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x1800963e1  lea     rdx, [rsp+28h+arg_8]
0x1800963e6  mov     [rsp+28h+arg_8], 3
0x1800963ee  movdqu  xmmword ptr [rax], xmm0
0x1800963f2  movups  xmm1, xmmword ptr cs:_GUID_9edde9e7_8dee_47ea_99df_e6faf2ed44bf.Data1
0x1800963f9  movdqu  xmmword ptr [rax+10h], xmm1
0x1800963fe  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180096405  movdqu  xmmword ptr [rax+20h], xmm0
0x18009640a  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWICComponentInternal@@UIMediaExtension@Media@Windows@@U?$CloakedIid@UIMFTransform@@@23@U?$CloakedIid@UIMFTelemetryComponent@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18009640f  mov     dword ptr [rsi], 5
0x180096415  mov     [rdi], r8
0x180096418  mov     rsi, [rsp+28h+arg_10]
0x18009641d  mov     eax, ebx
0x18009641f  mov     rbx, [rsp+28h+arg_0]
0x180096424  add     rsp, 20h
0x180096428  pop     rdi
0x180096429  retn
```
