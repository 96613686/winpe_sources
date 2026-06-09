# Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgsServer::GetIids(ulong *,_GUID * *)

- ea: `0x180020240`
- end: `0x18002029f`
- name: `?GetIids@SecondaryTileUserChangedEventArgsServer@StateRepository@Internal@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgsServer *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180020218`
- `0x180020240`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020262`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020262`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgsServer::GetIids(
        Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgsServer *this,
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgs,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180020240  mov     [rsp+arg_0], rbx
0x180020245  push    rdi
0x180020246  sub     rsp, 20h
0x18002024a  mov     qword ptr [r8], 0
0x180020251  mov     ecx, 20h ; ' '; cb
0x180020256  mov     dword ptr [rdx], 0
0x18002025c  mov     rbx, r8
0x18002025f  mov     rdi, rdx
0x180020262  call    cs:__imp_CoTaskMemAlloc
0x180020268  mov     r8, rax
0x18002026b  test    rax, rax
0x18002026e  jnz     short loc_180020277
0x180020270  mov     eax, 8007000Eh
0x180020275  jmp     short loc_180020294
0x180020277  lea     rdx, [rsp+28h+arg_8]
0x18002027c  mov     [rsp+28h+arg_8], 0
0x180020284  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UISecondaryTileUserChangedEventArgs@StateRepository@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgs,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180020289  mov     dword ptr [rdi], 2
0x18002028f  xor     eax, eax
0x180020291  mov     [rbx], r8
0x180020294  mov     rbx, [rsp+28h+arg_0]
0x180020299  add     rsp, 20h
0x18002029d  pop     rdi
0x18002029e  retn
```
