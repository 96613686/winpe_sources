# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextActivationStateRequestedEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001cc80`
- end: `0x18001cce1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextActivationStateRequestedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001cc80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cca2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextActivationStateRequestedEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_02637919_750c_4b9b_a866_a40f958fd02c;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001cc80  mov     [rsp+arg_0], rbx
0x18001cc85  push    rdi
0x18001cc86  sub     rsp, 20h
0x18001cc8a  mov     qword ptr [r8], 0
0x18001cc91  mov     ecx, 20h ; ' '; cb
0x18001cc96  mov     dword ptr [rdx], 0
0x18001cc9c  mov     rbx, r8
0x18001cc9f  mov     rdi, rdx
0x18001cca2  call    cs:__imp_CoTaskMemAlloc
0x18001cca8  test    rax, rax
0x18001ccab  jnz     short loc_18001CCB4
0x18001ccad  mov     eax, 8007000Eh
0x18001ccb2  jmp     short loc_18001CCD6
0x18001ccb4  movups  xmm0, xmmword ptr cs:_GUID_02637919_750c_4b9b_a866_a40f958fd02c.Data1
0x18001ccbb  movdqu  xmmword ptr [rax], xmm0
0x18001ccbf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001ccc6  movdqu  xmmword ptr [rax+10h], xmm1
0x18001cccb  mov     dword ptr [rdi], 2
0x18001ccd1  mov     [rbx], rax
0x18001ccd4  xor     eax, eax
0x18001ccd6  mov     rbx, [rsp+28h+arg_0]
0x18001ccdb  add     rsp, 20h
0x18001ccdf  pop     rdi
0x18001cce0  retn
```
