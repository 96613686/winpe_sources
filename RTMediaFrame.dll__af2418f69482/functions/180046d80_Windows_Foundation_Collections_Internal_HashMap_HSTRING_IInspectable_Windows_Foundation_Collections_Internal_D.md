# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::GetIids(ulong *,_GUID * *)

- ea: `0x180046d80`
- end: `0x180046ded`
- name: `?GetIids@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046e00`

## callees

- `0x180046d80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046da2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046da2`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::GetIids(
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
  *v5 = GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_fe2f3d47_5d47_5499_8374_430c7cda0204;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180046d80  mov     [rsp+arg_0], rbx
0x180046d85  push    rdi
0x180046d86  sub     rsp, 20h
0x180046d8a  mov     qword ptr [r8], 0
0x180046d91  mov     ecx, 30h ; '0'; cb
0x180046d96  mov     dword ptr [rdx], 0
0x180046d9c  mov     rbx, r8
0x180046d9f  mov     rdi, rdx
0x180046da2  call    cs:__imp_CoTaskMemAlloc
0x180046da8  test    rax, rax
0x180046dab  jnz     short loc_180046DB4
0x180046dad  mov     eax, 8007000Eh
0x180046db2  jmp     short loc_180046DE2
0x180046db4  movups  xmm0, xmmword ptr cs:_GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca.Data1
0x180046dbb  movdqu  xmmword ptr [rax], xmm0
0x180046dbf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180046dc6  movdqu  xmmword ptr [rax+10h], xmm1
0x180046dcb  movups  xmm0, xmmword ptr cs:_GUID_fe2f3d47_5d47_5499_8374_430c7cda0204.Data1
0x180046dd2  movdqu  xmmword ptr [rax+20h], xmm0
0x180046dd7  mov     dword ptr [rdi], 3
0x180046ddd  mov     [rbx], rax
0x180046de0  xor     eax, eax
0x180046de2  mov     rbx, [rsp+28h+arg_0]
0x180046de7  add     rsp, 20h
0x180046deb  pop     rdi
0x180046dec  retn
```
