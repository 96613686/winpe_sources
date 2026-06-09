# Windows::Services::Cortana::CortanaSettings::GetIids(ulong *,_GUID * *)

- ea: `0x180010f90`
- end: `0x180010fef`
- name: `?GetIids@CortanaSettings@Cortana@Services@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(Windows::Services::Cortana::CortanaSettings *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180010d68`
- `0x180010f90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010fb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010fb2`

## pseudocode

```c
__int64 __fastcall Windows::Services::Cortana::CortanaSettings::GetIids(
        Windows::Services::Cortana::CortanaSettings *this,
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Services::Cortana::ICortanaSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180010f90  mov     [rsp+arg_0], rbx
0x180010f95  push    rdi
0x180010f96  sub     rsp, 20h
0x180010f9a  mov     qword ptr [r8], 0
0x180010fa1  mov     ecx, 20h ; ' '; cb
0x180010fa6  mov     dword ptr [rdx], 0
0x180010fac  mov     rbx, r8
0x180010faf  mov     rdi, rdx
0x180010fb2  call    cs:__imp_CoTaskMemAlloc
0x180010fb8  mov     r8, rax
0x180010fbb  test    rax, rax
0x180010fbe  jnz     short loc_180010FC7
0x180010fc0  mov     eax, 8007000Eh
0x180010fc5  jmp     short loc_180010FE4
0x180010fc7  lea     rdx, [rsp+28h+arg_8]
0x180010fcc  mov     [rsp+28h+arg_8], 0
0x180010fd4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UICortanaSettings@Cortana@Services@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Services::Cortana::ICortanaSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180010fd9  mov     dword ptr [rdi], 2
0x180010fdf  xor     eax, eax
0x180010fe1  mov     [rbx], r8
0x180010fe4  mov     rbx, [rsp+28h+arg_0]
0x180010fe9  add     rsp, 20h
0x180010fed  pop     rdi
0x180010fee  retn
```
