# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::FamilySafety::AppLimits::IParentalControlsAppInventory,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800079b0`
- end: `0x180007a11`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIParentalControlsAppInventory@AppLimits@FamilySafety@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800079b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800079d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800079d2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::FamilySafety::AppLimits::IParentalControlsAppInventory,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_222eb002_1c9e_515d_9965_e5231a6d4574;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800079b0  mov     [rsp+arg_0], rbx
0x1800079b5  push    rdi
0x1800079b6  sub     rsp, 20h
0x1800079ba  mov     qword ptr [r8], 0
0x1800079c1  mov     ecx, 20h ; ' '; cb
0x1800079c6  mov     dword ptr [rdx], 0
0x1800079cc  mov     rbx, r8
0x1800079cf  mov     rdi, rdx
0x1800079d2  call    cs:__imp_CoTaskMemAlloc
0x1800079d8  test    rax, rax
0x1800079db  jnz     short loc_1800079E4
0x1800079dd  mov     eax, 8007000Eh
0x1800079e2  jmp     short loc_180007A06
0x1800079e4  movups  xmm0, xmmword ptr cs:_GUID_222eb002_1c9e_515d_9965_e5231a6d4574.Data1
0x1800079eb  movdqu  xmmword ptr [rax], xmm0
0x1800079ef  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800079f6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800079fb  mov     dword ptr [rdi], 2
0x180007a01  mov     [rbx], rax
0x180007a04  xor     eax, eax
0x180007a06  mov     rbx, [rsp+28h+arg_0]
0x180007a0b  add     rsp, 20h
0x180007a0f  pop     rdi
0x180007a10  retn
```
