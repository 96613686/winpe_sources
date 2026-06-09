# Windows::Foundation::Collections::Internal::MapChangedEventArgs<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::GetIids(ulong *,_GUID * *)

- ea: `0x18003b5f0`
- end: `0x18003b651`
- name: `?GetIids@?$MapChangedEventArgs@PEAUHSTRING__@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003b5f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b612`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b612`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::MapChangedEventArgs<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::GetIids(
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
  *v5 = GUID_60141efb_f2f9_5377_96fd_f8c60d9558b5;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18003b5f0  mov     [rsp+arg_0], rbx
0x18003b5f5  push    rdi
0x18003b5f6  sub     rsp, 20h
0x18003b5fa  mov     qword ptr [r8], 0
0x18003b601  mov     ecx, 20h ; ' '; cb
0x18003b606  mov     dword ptr [rdx], 0
0x18003b60c  mov     rbx, r8
0x18003b60f  mov     rdi, rdx
0x18003b612  call    cs:__imp_CoTaskMemAlloc
0x18003b618  test    rax, rax
0x18003b61b  jnz     short loc_18003B624
0x18003b61d  mov     eax, 8007000Eh
0x18003b622  jmp     short loc_18003B646
0x18003b624  movups  xmm0, xmmword ptr cs:_GUID_60141efb_f2f9_5377_96fd_f8c60d9558b5.Data1
0x18003b62b  movdqu  xmmword ptr [rax], xmm0
0x18003b62f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18003b636  movdqu  xmmword ptr [rax+10h], xmm1
0x18003b63b  mov     dword ptr [rdi], 2
0x18003b641  mov     [rbx], rax
0x18003b644  xor     eax, eax
0x18003b646  mov     rbx, [rsp+28h+arg_0]
0x18003b64b  add     rsp, 20h
0x18003b64f  pop     rdi
0x18003b650  retn
```
