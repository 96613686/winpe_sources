# MF::AsyncAction::GetIids(ulong *,_GUID * *)

- ea: `0x180037b00`
- end: `0x180037b6a`
- name: `?GetIids@AsyncAction@MF@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(MF::AsyncAction *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180037b70`

## callees

- `0x180032f20`
- `0x180037b00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037b22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037b22`

## pseudocode

```c
__int64 __fastcall MF::AsyncAction::GetIids(MF::AsyncAction *this, unsigned int *a2, struct _GUID **a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_5a648006_843a_4da9_865b_9d26e5dfad7b;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::DisableCausality>>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180037b00  mov     [rsp+arg_0], rbx
0x180037b05  push    rdi
0x180037b06  sub     rsp, 20h
0x180037b0a  mov     qword ptr [r8], 0
0x180037b11  mov     ecx, 30h ; '0'; cb
0x180037b16  mov     dword ptr [rdx], 0
0x180037b1c  mov     rbx, r8
0x180037b1f  mov     rdi, rdx
0x180037b22  call    cs:__imp_CoTaskMemAlloc
0x180037b28  mov     r8, rax
0x180037b2b  test    rax, rax
0x180037b2e  jnz     short loc_180037B37
0x180037b30  mov     eax, 8007000Eh
0x180037b35  jmp     short loc_180037B5F
0x180037b37  movups  xmm0, xmmword ptr cs:_GUID_5a648006_843a_4da9_865b_9d26e5dfad7b.Data1
0x180037b3e  lea     rdx, [rsp+28h+arg_8]
0x180037b43  mov     [rsp+28h+arg_8], 1
0x180037b4b  movdqu  xmmword ptr [rax], xmm0
0x180037b4f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@V?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00UDisableCausality@WRL@Microsoft@@@Internal@Windows@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::DisableCausality>>::FillArrayWithIid(ulong *,_GUID *)
0x180037b54  mov     dword ptr [rdi], 3
0x180037b5a  xor     eax, eax
0x180037b5c  mov     [rbx], r8
0x180037b5f  mov     rbx, [rsp+28h+arg_0]
0x180037b64  add     rsp, 20h
0x180037b68  pop     rdi
0x180037b69  retn
```
