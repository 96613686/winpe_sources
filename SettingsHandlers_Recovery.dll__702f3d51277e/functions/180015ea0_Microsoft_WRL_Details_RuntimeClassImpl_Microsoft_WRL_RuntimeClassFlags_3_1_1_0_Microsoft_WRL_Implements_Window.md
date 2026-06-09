# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180015ea0`
- end: `0x180015f19`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015f20`
- `0x180015f30`
- `0x180016020`

## callees

- `0x180015ea0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180015ec2`
- `ole32!CoTaskMemAlloc` at `0x180015ec2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_b32bdca4_5e52_5b27_bc5d_d66a1a268c2a;
  v5[1] = GUID_092b849b_60b1_52be_a44a_6fe8e933cbe4;
  v5[2] = GUID_7b81c56a_0985_518d_baa9_0da9ae009f65;
  v5[3] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 4;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180015ea0  mov     [rsp+arg_0], rbx
0x180015ea5  push    rdi
0x180015ea6  sub     rsp, 20h
0x180015eaa  mov     qword ptr [r8], 0
0x180015eb1  mov     ecx, 40h ; '@'; cb
0x180015eb6  mov     dword ptr [rdx], 0
0x180015ebc  mov     rbx, r8
0x180015ebf  mov     rdi, rdx
0x180015ec2  call    cs:__imp_CoTaskMemAlloc
0x180015ec8  test    rax, rax
0x180015ecb  jnz     short loc_180015ED4
0x180015ecd  mov     eax, 8007000Eh
0x180015ed2  jmp     short loc_180015F0E
0x180015ed4  movups  xmm0, xmmword ptr cs:_GUID_b32bdca4_5e52_5b27_bc5d_d66a1a268c2a.Data1
0x180015edb  movdqu  xmmword ptr [rax], xmm0
0x180015edf  movups  xmm1, xmmword ptr cs:_GUID_092b849b_60b1_52be_a44a_6fe8e933cbe4.Data1
0x180015ee6  movdqu  xmmword ptr [rax+10h], xmm1
0x180015eeb  movups  xmm0, xmmword ptr cs:_GUID_7b81c56a_0985_518d_baa9_0da9ae009f65.Data1
0x180015ef2  movdqu  xmmword ptr [rax+20h], xmm0
0x180015ef7  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180015efe  movdqu  xmmword ptr [rax+30h], xmm1
0x180015f03  mov     dword ptr [rdi], 4
0x180015f09  mov     [rbx], rax
0x180015f0c  xor     eax, eax
0x180015f0e  mov     rbx, [rsp+28h+arg_0]
0x180015f13  add     rsp, 20h
0x180015f17  pop     rdi
0x180015f18  retn
```
