# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180005350`
- end: `0x1800053b1`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800053c0`

## callees

- `0x180005350`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005372`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005372`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  v5[1] = GUID_d738e8ac_c3c8_4864_bdaa_20714029ed19;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180005350  mov     [rsp+arg_0], rbx
0x180005355  push    rdi
0x180005356  sub     rsp, 20h
0x18000535a  mov     qword ptr [r8], 0
0x180005361  mov     ecx, 20h ; ' '; cb
0x180005366  mov     dword ptr [rdx], 0
0x18000536c  mov     rbx, r8
0x18000536f  mov     rdi, rdx
0x180005372  call    cs:__imp_CoTaskMemAlloc
0x180005378  test    rax, rax
0x18000537b  jnz     short loc_180005384
0x18000537d  mov     eax, 8007000Eh
0x180005382  jmp     short loc_1800053A6
0x180005384  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000538b  movdqu  xmmword ptr [rax], xmm0
0x18000538f  movups  xmm1, xmmword ptr cs:_GUID_d738e8ac_c3c8_4864_bdaa_20714029ed19.Data1
0x180005396  movdqu  xmmword ptr [rax+10h], xmm1
0x18000539b  mov     dword ptr [rdi], 2
0x1800053a1  mov     [rbx], rax
0x1800053a4  xor     eax, eax
0x1800053a6  mov     rbx, [rsp+28h+arg_0]
0x1800053ab  add     rsp, 20h
0x1800053af  pop     rdi
0x1800053b0  retn
```
