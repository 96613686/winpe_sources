# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkElementIterator::GetIids(ulong *,_GUID * *)

- ea: `0x180046ea0`
- end: `0x180046f01`
- name: `?GetIids@ChunkElementIterator@?$NaiveSplitView@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180046ea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046ec2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046ec2`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkElementIterator::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_5db5fa32_707c_5849_a06b_91c8eb9d10e8;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180046ea0  mov     [rsp+arg_0], rbx
0x180046ea5  push    rdi
0x180046ea6  sub     rsp, 20h
0x180046eaa  mov     qword ptr [r8], 0
0x180046eb1  mov     ecx, 20h ; ' '; cb
0x180046eb6  mov     dword ptr [rdx], 0
0x180046ebc  mov     rbx, r8
0x180046ebf  mov     rdi, rdx
0x180046ec2  call    cs:__imp_CoTaskMemAlloc
0x180046ec8  test    rax, rax
0x180046ecb  jnz     short loc_180046ED4
0x180046ecd  mov     eax, 8007000Eh
0x180046ed2  jmp     short loc_180046EF6
0x180046ed4  movups  xmm0, xmmword ptr cs:_GUID_5db5fa32_707c_5849_a06b_91c8eb9d10e8.Data1
0x180046edb  movdqu  xmmword ptr [rax], xmm0
0x180046edf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180046ee6  movdqu  xmmword ptr [rax+10h], xmm1
0x180046eeb  mov     dword ptr [rdi], 2
0x180046ef1  mov     [rbx], rax
0x180046ef4  xor     eax, eax
0x180046ef6  mov     rbx, [rsp+28h+arg_0]
0x180046efb  add     rsp, 20h
0x180046eff  pop     rdi
0x180046f00  retn
```
