# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextHostOperationAcknowledgedEventArgs,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001d2a0`
- end: `0x18001d301`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextHostOperationAcknowledgedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001d2a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d2c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d2c2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextHostOperationAcknowledgedEventArgs,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_1d6ae750_90de_4cd4_b755_b9389d2a668d;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001d2a0  mov     [rsp+arg_0], rbx
0x18001d2a5  push    rdi
0x18001d2a6  sub     rsp, 20h
0x18001d2aa  mov     qword ptr [r8], 0
0x18001d2b1  mov     ecx, 20h ; ' '; cb
0x18001d2b6  mov     dword ptr [rdx], 0
0x18001d2bc  mov     rbx, r8
0x18001d2bf  mov     rdi, rdx
0x18001d2c2  call    cs:__imp_CoTaskMemAlloc
0x18001d2c8  test    rax, rax
0x18001d2cb  jnz     short loc_18001D2D4
0x18001d2cd  mov     eax, 8007000Eh
0x18001d2d2  jmp     short loc_18001D2F6
0x18001d2d4  movups  xmm0, xmmword ptr cs:_GUID_1d6ae750_90de_4cd4_b755_b9389d2a668d.Data1
0x18001d2db  movdqu  xmmword ptr [rax], xmm0
0x18001d2df  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001d2e6  movdqu  xmmword ptr [rax+10h], xmm1
0x18001d2eb  mov     dword ptr [rdi], 2
0x18001d2f1  mov     [rbx], rax
0x18001d2f4  xor     eax, eax
0x18001d2f6  mov     rbx, [rsp+28h+arg_0]
0x18001d2fb  add     rsp, 20h
0x18001d2ff  pop     rdi
0x18001d300  retn
```
