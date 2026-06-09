# Windows::System::AppMemoryUsageLimitChangingEventArgs::GetIids(ulong *,_GUID * *)

- ea: `0x1800183b0`
- end: `0x18001840f`
- name: `?GetIids@AppMemoryUsageLimitChangingEventArgs@System@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(Windows::System::AppMemoryUsageLimitChangingEventArgs *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800182ec`
- `0x1800183b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800183d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800183d2`

## pseudocode

```c
__int64 __fastcall Windows::System::AppMemoryUsageLimitChangingEventArgs::GetIids(
        Windows::System::AppMemoryUsageLimitChangingEventArgs *this,
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::System::IAppMemoryUsageLimitChangingEventArgs,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x1800183b0  mov     [rsp+arg_0], rbx
0x1800183b5  push    rdi
0x1800183b6  sub     rsp, 20h
0x1800183ba  mov     qword ptr [r8], 0
0x1800183c1  mov     ecx, 20h ; ' '; cb
0x1800183c6  mov     dword ptr [rdx], 0
0x1800183cc  mov     rbx, r8
0x1800183cf  mov     rdi, rdx
0x1800183d2  call    cs:__imp_CoTaskMemAlloc
0x1800183d8  mov     r8, rax
0x1800183db  test    rax, rax
0x1800183de  jnz     short loc_1800183E7
0x1800183e0  mov     eax, 8007000Eh
0x1800183e5  jmp     short loc_180018404
0x1800183e7  lea     rdx, [rsp+28h+arg_8]
0x1800183ec  mov     [rsp+28h+arg_8], 0
0x1800183f4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIAppMemoryUsageLimitChangingEventArgs@System@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::System::IAppMemoryUsageLimitChangingEventArgs,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800183f9  mov     dword ptr [rdi], 2
0x1800183ff  xor     eax, eax
0x180018401  mov     [rbx], r8
0x180018404  mov     rbx, [rsp+28h+arg_0]
0x180018409  add     rsp, 20h
0x18001840d  pop     rdi
0x18001840e  retn
```
