# Windows::System::ProcessLauncherOptionsImpl::GetIids(ulong *,_GUID * *)

- ea: `0x18000bf70`
- end: `0x18000bfcf`
- name: `?GetIids@ProcessLauncherOptionsImpl@System@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(Windows::System::ProcessLauncherOptionsImpl *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000bbf0`
- `0x18000bf70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bf92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bf92`

## pseudocode

```c
__int64 __fastcall Windows::System::ProcessLauncherOptionsImpl::GetIids(
        Windows::System::ProcessLauncherOptionsImpl *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::System::IProcessLauncherOptions,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18000bf70  mov     [rsp+arg_0], rbx
0x18000bf75  push    rdi
0x18000bf76  sub     rsp, 20h
0x18000bf7a  mov     qword ptr [r8], 0
0x18000bf81  mov     ecx, 20h ; ' '; cb
0x18000bf86  mov     dword ptr [rdx], 0
0x18000bf8c  mov     rbx, r8
0x18000bf8f  mov     rdi, rdx
0x18000bf92  call    cs:__imp_CoTaskMemAlloc
0x18000bf98  mov     r8, rax
0x18000bf9b  test    rax, rax
0x18000bf9e  jnz     short loc_18000BFA7
0x18000bfa0  mov     eax, 8007000Eh
0x18000bfa5  jmp     short loc_18000BFC4
0x18000bfa7  lea     rdx, [rsp+28h+arg_8]
0x18000bfac  mov     [rsp+28h+arg_8], 0
0x18000bfb4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIProcessLauncherOptions@System@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::System::IProcessLauncherOptions,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18000bfb9  mov     dword ptr [rdi], 2
0x18000bfbf  xor     eax, eax
0x18000bfc1  mov     [rbx], r8
0x18000bfc4  mov     rbx, [rsp+28h+arg_0]
0x18000bfc9  add     rsp, 20h
0x18000bfcd  pop     rdi
0x18000bfce  retn
```
