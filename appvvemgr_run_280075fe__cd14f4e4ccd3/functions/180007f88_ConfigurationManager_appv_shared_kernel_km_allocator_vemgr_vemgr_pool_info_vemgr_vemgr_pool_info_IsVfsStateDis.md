# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(bool &)

- ea: `0x180007f88`
- end: `0x180008042`
- name: `?IsVfsStateDisabled@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEA_N@Z`
- size: `186`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005890`
- `0x1800062bc`
- `0x180006460`
- `0x180008900`
- `0x180008fc8`

## callees

- `0x180007f88`
- `0x18001baf0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x180007fbf`
- `ntoskrnl!EtwActivityIdControl` at `0x180007fbf`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008011`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008011`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000801d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000801d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180007fe8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180007fe8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180007fd5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180007fd5`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(
        __int64 a1,
        _BYTE *a2)
{
  bool v4; // di
  struct _ERESOURCE *v5; // rcx
  GUID ActivityId; // [rsp+20h] [rbp-48h] BYREF

  ActivityId = GUID_NULL;
  EtwActivityIdControl(1u, &ActivityId);
  v4 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    KeEnterCriticalRegion();
    v4 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 88), 1u) == 1;
  }
  *a2 = *(_BYTE *)(a1 + 105);
  if ( v4 )
  {
    v5 = *(struct _ERESOURCE **)(a1 + 88);
    if ( v5 )
    {
      ExReleaseResourceLite(v5);
      KeLeaveCriticalRegion();
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180007f88  push    rbx
0x180007f8a  push    rbp
0x180007f8b  push    rsi
0x180007f8c  push    rdi
0x180007f8d  sub     rsp, 48h
0x180007f91  mov     rax, cs:__security_cookie
0x180007f98  xor     rax, rsp
0x180007f9b  mov     [rsp+68h+var_38], rax
0x180007fa0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180007fa7  mov     rsi, rdx
0x180007faa  mov     rbx, rcx
0x180007fad  mov     ebp, 1
0x180007fb2  lea     rdx, [rsp+68h+ActivityId]; ActivityId
0x180007fb7  mov     ecx, ebp; ControlCode
0x180007fb9  movdqu  xmmword ptr [rsp+68h+ActivityId.Data1], xmm0
0x180007fbf  call    cs:__imp_EtwActivityIdControl
0x180007fc6  nop     dword ptr [rax+rax+00h]
0x180007fcb  xor     dil, dil
0x180007fce  cmp     qword ptr [rbx+58h], 0
0x180007fd3  jz      short loc_180007FFE
0x180007fd5  call    cs:__imp_KeEnterCriticalRegion
0x180007fdc  nop     dword ptr [rax+rax+00h]
0x180007fe1  mov     rcx, [rbx+58h]; Resource
0x180007fe5  mov     dl, bpl; Wait
0x180007fe8  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180007fef  nop     dword ptr [rax+rax+00h]
0x180007ff4  cmp     al, bpl
0x180007ff7  movzx   edi, dil
0x180007ffb  cmovz   edi, ebp
0x180007ffe  mov     al, [rbx+69h]
0x180008001  mov     [rsi], al
0x180008003  test    dil, dil
0x180008006  jz      short loc_180008029
0x180008008  mov     rcx, [rbx+58h]; Resource
0x18000800c  test    rcx, rcx
0x18000800f  jz      short loc_180008029
0x180008011  call    cs:__imp_ExReleaseResourceLite
0x180008018  nop     dword ptr [rax+rax+00h]
0x18000801d  call    cs:__imp_KeLeaveCriticalRegion
0x180008024  nop     dword ptr [rax+rax+00h]
0x180008029  xor     eax, eax
0x18000802b  mov     rcx, [rsp+68h+var_38]
0x180008030  xor     rcx, rsp; StackCookie
0x180008033  call    __security_check_cookie
0x180008038  add     rsp, 48h
0x18000803c  pop     rdi
0x18000803d  pop     rsi
0x18000803e  pop     rbp
0x18000803f  pop     rbx
0x180008040  retn
```
