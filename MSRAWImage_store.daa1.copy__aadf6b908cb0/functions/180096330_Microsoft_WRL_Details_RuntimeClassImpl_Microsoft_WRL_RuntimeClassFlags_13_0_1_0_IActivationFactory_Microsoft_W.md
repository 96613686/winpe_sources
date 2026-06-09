# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(ulong *,_GUID * *)

- ea: `0x180096330`
- end: `0x18009638e`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@VNil@Details@23@V5623@V5623@V5623@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180096330`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009634f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009634f`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  unsigned int v3; // ebx
  GUID *v6; // rax

  v3 = 0;
  *a3 = 0;
  *a2 = 0;
  v6 = (GUID *)CoTaskMemAlloc(0x10u);
  if ( v6 )
  {
    *v6 = GUID_00000035_0000_0000_c000_000000000046;
    *a2 = 1;
    *a3 = v6;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v3;
}

```

## disassembly

```asm
0x180096330  mov     [rsp+arg_0], rbx
0x180096335  mov     [rsp+arg_8], rsi
0x18009633a  push    rdi
0x18009633b  sub     rsp, 20h
0x18009633f  xor     ebx, ebx
0x180096341  mov     rdi, r8
0x180096344  mov     [r8], rbx
0x180096347  mov     rsi, rdx
0x18009634a  mov     [rdx], ebx
0x18009634c  lea     ecx, [rbx+10h]; cb
0x18009634f  call    cs:__imp_CoTaskMemAlloc
0x180096356  nop     dword ptr [rax+rax+00h]
0x18009635b  test    rax, rax
0x18009635e  jnz     short loc_180096367
0x180096360  mov     ebx, 8007000Eh
0x180096365  jmp     short loc_18009637B
0x180096367  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18009636e  movdqu  xmmword ptr [rax], xmm0
0x180096372  mov     dword ptr [rsi], 1
0x180096378  mov     [rdi], rax
0x18009637b  mov     rsi, [rsp+28h+arg_8]
0x180096380  mov     eax, ebx
0x180096382  mov     rbx, [rsp+28h+arg_0]
0x180096387  add     rsp, 20h
0x18009638b  pop     rdi
0x18009638c  retn
```
