# Windows::Internal::StateRepository::SecondaryTileUserNotifierServer::GetIids(ulong *,_GUID * *)

- ea: `0x18001ee70`
- end: `0x18001eecf`
- name: `?GetIids@SecondaryTileUserNotifierServer@StateRepository@Internal@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::SecondaryTileUserNotifierServer *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ee44`
- `0x18001ee70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ee92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ee92`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::SecondaryTileUserNotifierServer::GetIids(
        Windows::Internal::StateRepository::SecondaryTileUserNotifierServer *this,
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::StateRepository::ISecondaryTileUserNotifier,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18001ee70  mov     [rsp+arg_0], rbx
0x18001ee75  push    rdi
0x18001ee76  sub     rsp, 20h
0x18001ee7a  mov     qword ptr [r8], 0
0x18001ee81  mov     ecx, 20h ; ' '; cb
0x18001ee86  mov     dword ptr [rdx], 0
0x18001ee8c  mov     rbx, r8
0x18001ee8f  mov     rdi, rdx
0x18001ee92  call    cs:__imp_CoTaskMemAlloc
0x18001ee98  mov     r8, rax
0x18001ee9b  test    rax, rax
0x18001ee9e  jnz     short loc_18001EEA7
0x18001eea0  mov     eax, 8007000Eh
0x18001eea5  jmp     short loc_18001EEC4
0x18001eea7  lea     rdx, [rsp+28h+arg_8]
0x18001eeac  mov     [rsp+28h+arg_8], 0
0x18001eeb4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UISecondaryTileUserNotifier@StateRepository@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::StateRepository::ISecondaryTileUserNotifier,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001eeb9  mov     dword ptr [rdi], 2
0x18001eebf  xor     eax, eax
0x18001eec1  mov     [rbx], r8
0x18001eec4  mov     rbx, [rsp+28h+arg_0]
0x18001eec9  add     rsp, 20h
0x18001eecd  pop     rdi
0x18001eece  retn
```
