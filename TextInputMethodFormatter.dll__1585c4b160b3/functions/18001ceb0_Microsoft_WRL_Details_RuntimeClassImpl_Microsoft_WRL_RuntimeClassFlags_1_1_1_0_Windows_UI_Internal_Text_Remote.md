# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextConversionModeUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001ceb0`
- end: `0x18001cf11`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextConversionModeUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ceb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ced2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ced2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextConversionModeUpdatingEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_8ccb1729_9df7_4165_886d_2c2fd852b8fc;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001ceb0  mov     [rsp+arg_0], rbx
0x18001ceb5  push    rdi
0x18001ceb6  sub     rsp, 20h
0x18001ceba  mov     qword ptr [r8], 0
0x18001cec1  mov     ecx, 20h ; ' '; cb
0x18001cec6  mov     dword ptr [rdx], 0
0x18001cecc  mov     rbx, r8
0x18001cecf  mov     rdi, rdx
0x18001ced2  call    cs:__imp_CoTaskMemAlloc
0x18001ced8  test    rax, rax
0x18001cedb  jnz     short loc_18001CEE4
0x18001cedd  mov     eax, 8007000Eh
0x18001cee2  jmp     short loc_18001CF06
0x18001cee4  movups  xmm0, xmmword ptr cs:_GUID_8ccb1729_9df7_4165_886d_2c2fd852b8fc.Data1
0x18001ceeb  movdqu  xmmword ptr [rax], xmm0
0x18001ceef  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001cef6  movdqu  xmmword ptr [rax+10h], xmm1
0x18001cefb  mov     dword ptr [rdi], 2
0x18001cf01  mov     [rbx], rax
0x18001cf04  xor     eax, eax
0x18001cf06  mov     rbx, [rsp+28h+arg_0]
0x18001cf0b  add     rsp, 20h
0x18001cf0f  pop     rdi
0x18001cf10  retn
```
