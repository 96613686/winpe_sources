# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::System::IMemoryManagerStatics,Windows::System::IMemoryManagerStatics2,Windows::System::IMemoryManagerStatics3,Windows::System::IMemoryManagerStatics4>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180014d30`
- end: `0x180014db5`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$Implements@UIMemoryManagerStatics@System@Windows@@UIMemoryManagerStatics2@23@UIMemoryManagerStatics3@23@UIMemoryManagerStatics4@23@@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014dc0`
- `0x180014dd0`
- `0x180014de0`
- `0x180014df0`

## callees

- `0x180014d30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014d52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014d52`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::System::IMemoryManagerStatics,Windows::System::IMemoryManagerStatics2,Windows::System::IMemoryManagerStatics3,Windows::System::IMemoryManagerStatics4>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x50u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  v5[1] = GUID_5c6c279c_d7ca_4779_9188_4057219ce64c;
  v5[2] = GUID_6eee351f_6d62_423f_9479_b01f9c9f7669;
  v5[3] = GUID_149b59ce_92ad_4e35_89eb_50dfb4c0d91c;
  v5[4] = GUID_c5a94828_e84e_4886_8a0d_44b3190e3b72;
  *a2 = 5;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180014d30  mov     [rsp+arg_0], rbx
0x180014d35  push    rdi
0x180014d36  sub     rsp, 20h
0x180014d3a  mov     qword ptr [r8], 0
0x180014d41  mov     ecx, 50h ; 'P'; cb
0x180014d46  mov     dword ptr [rdx], 0
0x180014d4c  mov     rbx, r8
0x180014d4f  mov     rdi, rdx
0x180014d52  call    cs:__imp_CoTaskMemAlloc
0x180014d58  test    rax, rax
0x180014d5b  jnz     short loc_180014D64
0x180014d5d  mov     eax, 8007000Eh
0x180014d62  jmp     short loc_180014DAA
0x180014d64  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x180014d6b  movdqu  xmmword ptr [rax], xmm0
0x180014d6f  movups  xmm1, xmmword ptr cs:_GUID_5c6c279c_d7ca_4779_9188_4057219ce64c.Data1
0x180014d76  movdqu  xmmword ptr [rax+10h], xmm1
0x180014d7b  movups  xmm0, xmmword ptr cs:_GUID_6eee351f_6d62_423f_9479_b01f9c9f7669.Data1
0x180014d82  movdqu  xmmword ptr [rax+20h], xmm0
0x180014d87  movups  xmm1, xmmword ptr cs:_GUID_149b59ce_92ad_4e35_89eb_50dfb4c0d91c.Data1
0x180014d8e  movdqu  xmmword ptr [rax+30h], xmm1
0x180014d93  movups  xmm0, xmmword ptr cs:_GUID_c5a94828_e84e_4886_8a0d_44b3190e3b72.Data1
0x180014d9a  movdqu  xmmword ptr [rax+40h], xmm0
0x180014d9f  mov     dword ptr [rdi], 5
0x180014da5  mov     [rbx], rax
0x180014da8  xor     eax, eax
0x180014daa  mov     rbx, [rsp+28h+arg_0]
0x180014daf  add     rsp, 20h
0x180014db3  pop     rdi
0x180014db4  retn
```
