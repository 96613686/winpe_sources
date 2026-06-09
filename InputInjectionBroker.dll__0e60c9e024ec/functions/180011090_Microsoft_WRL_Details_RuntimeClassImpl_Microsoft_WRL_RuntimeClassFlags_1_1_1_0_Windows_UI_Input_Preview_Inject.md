# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfo,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180011090`
- end: `0x1800110f1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectedInputGamepadInfo@Injection@Preview@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180011090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800110b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800110b2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfo,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_20ae9a3f_df11_4572_a9ab_d75b8a5e48ad;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180011090  mov     [rsp+arg_0], rbx
0x180011095  push    rdi
0x180011096  sub     rsp, 20h
0x18001109a  mov     qword ptr [r8], 0
0x1800110a1  mov     ecx, 20h ; ' '; cb
0x1800110a6  mov     dword ptr [rdx], 0
0x1800110ac  mov     rbx, r8
0x1800110af  mov     rdi, rdx
0x1800110b2  call    cs:__imp_CoTaskMemAlloc
0x1800110b8  test    rax, rax
0x1800110bb  jnz     short loc_1800110C4
0x1800110bd  mov     eax, 8007000Eh
0x1800110c2  jmp     short loc_1800110E6
0x1800110c4  movups  xmm0, xmmword ptr cs:_GUID_20ae9a3f_df11_4572_a9ab_d75b8a5e48ad.Data1
0x1800110cb  movdqu  xmmword ptr [rax], xmm0
0x1800110cf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800110d6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800110db  mov     dword ptr [rdi], 2
0x1800110e1  mov     [rbx], rax
0x1800110e4  xor     eax, eax
0x1800110e6  mov     rbx, [rsp+28h+arg_0]
0x1800110eb  add     rsp, 20h
0x1800110ef  pop     rdi
0x1800110f0  retn
```
