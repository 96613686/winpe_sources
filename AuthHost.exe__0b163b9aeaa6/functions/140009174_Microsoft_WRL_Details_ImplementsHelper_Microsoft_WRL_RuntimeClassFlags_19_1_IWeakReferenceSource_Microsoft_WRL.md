# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)

- ea: `0x140009174`
- end: `0x14000918e`
- name: `?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140009194`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
        __int64 a1,
        unsigned int *a2,
        __int64 a3)
{
  int v3; // ecx
  __int64 result; // rax

  v3 = *a2;
  *(GUID *)(a3 + 16LL * *a2) = GUID_00000038_0000_0000_c000_000000000046;
  result = (unsigned int)(v3 + 1);
  *a2 = result;
  return result;
}

```

## disassembly

```asm
0x140009174  mov     ecx, [rdx]
0x140009176  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x14000917d  mov     eax, ecx
0x14000917f  add     rax, rax
0x140009182  movdqu  xmmword ptr [r8+rax*8], xmm0
0x140009188  lea     eax, [rcx+1]
0x14000918b  mov     [rdx], eax
0x14000918d  retn
```
