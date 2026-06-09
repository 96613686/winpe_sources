# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Gaming::IGipSystemButtonEventArgs>::GetIids(ulong *,_GUID * *)

- ea: `0x180010250`
- end: `0x1800102b1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIGipSystemButtonEventArgs@Gaming@Internal@Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010250`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010272`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010272`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Gaming::IGipSystemButtonEventArgs>::GetIids(
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
  *v5 = GUID_93abfcf0_9f31_45bd_b1c6_31b6fc2ad00c;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180010250  mov     [rsp+arg_0], rbx
0x180010255  push    rdi
0x180010256  sub     rsp, 20h
0x18001025a  mov     qword ptr [r8], 0
0x180010261  mov     ecx, 20h ; ' '; cb
0x180010266  mov     dword ptr [rdx], 0
0x18001026c  mov     rbx, r8
0x18001026f  mov     rdi, rdx
0x180010272  call    cs:__imp_CoTaskMemAlloc
0x180010278  test    rax, rax
0x18001027b  jnz     short loc_180010284
0x18001027d  mov     eax, 8007000Eh
0x180010282  jmp     short loc_1800102A6
0x180010284  movups  xmm0, xmmword ptr cs:_GUID_93abfcf0_9f31_45bd_b1c6_31b6fc2ad00c.Data1
0x18001028b  movdqu  xmmword ptr [rax], xmm0
0x18001028f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180010296  movdqu  xmmword ptr [rax+10h], xmm1
0x18001029b  mov     dword ptr [rdi], 2
0x1800102a1  mov     [rbx], rax
0x1800102a4  xor     eax, eax
0x1800102a6  mov     rbx, [rsp+28h+arg_0]
0x1800102ab  add     rsp, 20h
0x1800102af  pop     rdi
0x1800102b0  retn
```
