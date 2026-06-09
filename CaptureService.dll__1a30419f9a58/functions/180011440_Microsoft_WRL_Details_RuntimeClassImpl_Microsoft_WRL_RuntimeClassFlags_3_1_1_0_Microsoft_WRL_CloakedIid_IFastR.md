# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Microsoft::WRL::CloakedIid<ICapturableItemCom>,Microsoft::WRL::CloakedIid<ICapturableItemCom_Old>,Microsoft::WRL::CloakedIid<Windows::Graphics::Capture::Server::ICapturableItemClosedHandler>,Windows::Graphics::Capture::Server::ICapturableItem>::GetIids(ulong *,_GUID * *)

- ea: `0x180011440`
- end: `0x1800114ad`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$CloakedIid@UIFastRundown@@@23@U?$CloakedIid@UICapturableItemCom@@@23@U?$CloakedIid@UICapturableItemCom_Old@@@23@U?$CloakedIid@UICapturableItemClosedHandler@Server@Capture@Graphics@Windows@@@23@UICapturableItem@Server@Capture@Graphics@Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800114c0`
- `0x1800114d0`
- `0x180011690`

## callees

- `0x180011440`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011462`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011462`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Microsoft::WRL::CloakedIid<ICapturableItemCom>,Microsoft::WRL::CloakedIid<ICapturableItemCom_Old>,Microsoft::WRL::CloakedIid<Windows::Graphics::Capture::Server::ICapturableItemClosedHandler>,Windows::Graphics::Capture::Server::ICapturableItem>::GetIids(
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
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_68c70dc3_5682_5647_a4c2_5e79cf1626dc;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180011440  mov     [rsp+arg_0], rbx
0x180011445  push    rdi
0x180011446  sub     rsp, 20h
0x18001144a  mov     qword ptr [r8], 0
0x180011451  mov     ecx, 30h ; '0'; cb
0x180011456  mov     dword ptr [rdx], 0
0x18001145c  mov     rbx, r8
0x18001145f  mov     rdi, rdx
0x180011462  call    cs:__imp_CoTaskMemAlloc
0x180011468  test    rax, rax
0x18001146b  jnz     short loc_180011474
0x18001146d  mov     eax, 8007000Eh
0x180011472  jmp     short loc_1800114A2
0x180011474  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18001147b  movdqu  xmmword ptr [rax], xmm0
0x18001147f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180011486  movdqu  xmmword ptr [rax+10h], xmm1
0x18001148b  movups  xmm0, xmmword ptr cs:_GUID_68c70dc3_5682_5647_a4c2_5e79cf1626dc.Data1
0x180011492  movdqu  xmmword ptr [rax+20h], xmm0
0x180011497  mov     dword ptr [rdi], 3
0x18001149d  mov     [rbx], rax
0x1800114a0  xor     eax, eax
0x1800114a2  mov     rbx, [rsp+28h+arg_0]
0x1800114a7  add     rsp, 20h
0x1800114ab  pop     rdi
0x1800114ac  retn
```
