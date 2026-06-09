# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputMouseInfo,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180010150`
- end: `0x1800101b1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectedInputMouseInfo@Injection@Preview@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010150`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010172`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputMouseInfo,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_96f56e6b_e47a_5cf4_418d_8a5fb9670c7d;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180010150  mov     [rsp+arg_0], rbx
0x180010155  push    rdi
0x180010156  sub     rsp, 20h
0x18001015a  mov     qword ptr [r8], 0
0x180010161  mov     ecx, 20h ; ' '; cb
0x180010166  mov     dword ptr [rdx], 0
0x18001016c  mov     rbx, r8
0x18001016f  mov     rdi, rdx
0x180010172  call    cs:__imp_CoTaskMemAlloc
0x180010178  test    rax, rax
0x18001017b  jnz     short loc_180010184
0x18001017d  mov     eax, 8007000Eh
0x180010182  jmp     short loc_1800101A6
0x180010184  movups  xmm0, xmmword ptr cs:_GUID_96f56e6b_e47a_5cf4_418d_8a5fb9670c7d.Data1
0x18001018b  movdqu  xmmword ptr [rax], xmm0
0x18001018f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180010196  movdqu  xmmword ptr [rax+10h], xmm1
0x18001019b  mov     dword ptr [rdi], 2
0x1800101a1  mov     [rbx], rax
0x1800101a4  xor     eax, eax
0x1800101a6  mov     rbx, [rsp+28h+arg_0]
0x1800101ab  add     rsp, 20h
0x1800101af  pop     rdi
0x1800101b0  retn
```
