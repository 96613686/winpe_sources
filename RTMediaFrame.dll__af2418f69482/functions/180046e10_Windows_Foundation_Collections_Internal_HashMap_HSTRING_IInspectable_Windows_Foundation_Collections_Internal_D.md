# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::View::GetIids(ulong *,_GUID * *)

- ea: `0x180046e10`
- end: `0x180046e7d`
- name: `?GetIids@View@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046e90`

## callees

- `0x180046e10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046e32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046e32`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::View::GetIids(
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
  *v5 = GUID_bb78502a_f79d_54fa_92c9_90c5039fdf7e;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_fe2f3d47_5d47_5499_8374_430c7cda0204;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180046e10  mov     [rsp+arg_0], rbx
0x180046e15  push    rdi
0x180046e16  sub     rsp, 20h
0x180046e1a  mov     qword ptr [r8], 0
0x180046e21  mov     ecx, 30h ; '0'; cb
0x180046e26  mov     dword ptr [rdx], 0
0x180046e2c  mov     rbx, r8
0x180046e2f  mov     rdi, rdx
0x180046e32  call    cs:__imp_CoTaskMemAlloc
0x180046e38  test    rax, rax
0x180046e3b  jnz     short loc_180046E44
0x180046e3d  mov     eax, 8007000Eh
0x180046e42  jmp     short loc_180046E72
0x180046e44  movups  xmm0, xmmword ptr cs:_GUID_bb78502a_f79d_54fa_92c9_90c5039fdf7e.Data1
0x180046e4b  movdqu  xmmword ptr [rax], xmm0
0x180046e4f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180046e56  movdqu  xmmword ptr [rax+10h], xmm1
0x180046e5b  movups  xmm0, xmmword ptr cs:_GUID_fe2f3d47_5d47_5499_8374_430c7cda0204.Data1
0x180046e62  movdqu  xmmword ptr [rax+20h], xmm0
0x180046e67  mov     dword ptr [rdi], 3
0x180046e6d  mov     [rbx], rax
0x180046e70  xor     eax, eax
0x180046e72  mov     rbx, [rsp+28h+arg_0]
0x180046e77  add     rsp, 20h
0x180046e7b  pop     rdi
0x180046e7c  retn
```
