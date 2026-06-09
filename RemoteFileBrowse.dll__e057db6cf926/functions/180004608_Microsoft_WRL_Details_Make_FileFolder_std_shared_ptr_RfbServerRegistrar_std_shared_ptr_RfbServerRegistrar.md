# Microsoft::WRL::Details::Make<FileFolder,std::shared_ptr<RfbServerRegistrar> &>(std::shared_ptr<RfbServerRegistrar> &)

- ea: `0x180004608`
- end: `0x180004661`
- name: `??$Make@VFileFolder@@AEAV?$shared_ptr@VRfbServerRegistrar@@@std@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VFileFolder@@@12@AEAV?$shared_ptr@VRfbServerRegistrar@@@std@@@Z`
- size: `89`
- prototype: `__int64 *__fastcall(__int64 *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005e70`
- `0x180007d40`

## callees

- `0x1800020d0`
- `0x180004608`
- `0x180006fe0`
- `0x1800076fc`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::Details::Make<FileFolder,std::shared_ptr<RfbServerRegistrar> &>(
        __int64 *a1,
        __int64 a2)
{
  void *v4; // rax
  __int64 v5; // rdi

  *a1 = 0;
  v4 = operator new(0xC0u, (const struct std::nothrow_t *)std::nothrow);
  if ( v4 )
  {
    v5 = FileFolder::FileFolder(v4, a2);
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::MixIn<FileFolder,RfbShellFolderBase,1>>::Release();
    *a1 = v5;
  }
  return a1;
}

```

## disassembly

```asm
0x180004608  mov     [rsp+arg_0], rbx
0x18000460d  push    rdi
0x18000460e  sub     rsp, 20h
0x180004612  mov     rdi, rdx
0x180004615  mov     qword ptr [rcx], 0
0x18000461c  mov     rbx, rcx
0x18000461f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004626  mov     ecx, 0C0h; unsigned __int64
0x18000462b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004630  test    rax, rax
0x180004633  jz      short loc_180004653
0x180004635  mov     rdx, rdi
0x180004638  mov     rcx, rax
0x18000463b  call    ??0FileFolder@@QEAA@AEBV?$shared_ptr@VRfbServerRegistrar@@@std@@@Z; FileFolder::FileFolder(std::shared_ptr<RfbServerRegistrar> const &)
0x180004640  mov     rcx, [rbx]
0x180004643  mov     rdi, rax
0x180004646  test    rcx, rcx
0x180004649  jz      short loc_180004650
0x18000464b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$MixIn@VFileFolder@@VRfbShellFolderBase@@$00@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::MixIn<FileFolder,RfbShellFolderBase,1>>::Release(void)
0x180004650  mov     [rbx], rdi
0x180004653  mov     rax, rbx
0x180004656  mov     rbx, [rsp+28h+arg_0]
0x18000465b  add     rsp, 20h
0x18000465f  pop     rdi
0x180004660  retn
```
