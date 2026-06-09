# Streaming::StreamingTargetFileCache::Close(Streaming::InstanceContext &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> const &,bool)

- ea: `0x140011cb0`
- end: `0x140011ebb`
- name: `?Close@StreamingTargetFileCache@Streaming@@QEAAJAEAVInstanceContext@2@AEBV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@_N@Z`
- size: `523`
- prototype: `__int64 __fastcall(__int64, __int64, const UNICODE_STRING *, char)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000935c`
- `0x140011f30`
- `0x140012b18`

## callees

- `0x1400041cc`
- `0x140004c40`
- `0x140011cb0`
- `0x140011ec4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011d3c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011df9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011d3c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011df9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011d30`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011ded`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011d30`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011ded`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140011cf7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140011cf7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011ce5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011ce5`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140011dab`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140011dab`

## pseudocode

```c
__int64 __fastcall Streaming::StreamingTargetFileCache::Close(
        __int64 a1,
        __int64 a2,
        const UNICODE_STRING *a3,
        char a4)
{
  bool v4; // si
  bool v5; // zf
  int v10; // ebp
  struct _ERESOURCE *v11; // rcx
  volatile signed __int32 *v12; // rdi
  _QWORD *i; // rbx
  struct _ERESOURCE *v15; // rcx
  volatile signed __int32 *v16; // rdi
  unsigned int v17; // eax
  volatile signed __int32 *v18; // rdi
  unsigned int v19; // esi
  _BYTE v20[8]; // [rsp+20h] [rbp-68h] BYREF
  _OWORD v21[6]; // [rsp+28h] [rbp-60h] BYREF
  _QWORD *v22; // [rsp+90h] [rbp+8h] BYREF

  v4 = 0;
  v5 = *(_QWORD *)(a1 + 8) == 0;
  v21[0] = 0;
  if ( !v5 )
  {
    KeEnterCriticalRegion();
    v4 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 8), 1u) == 1;
  }
  v10 = Streaming::StreamingTargetFileCache::Find(a1, a3, v21);
  if ( v10 >= 0 )
  {
    for ( i = *(_QWORD **)(a1 + 48); i != (_QWORD *)(a1 + 24); i = (_QWORD *)i[3] )
    {
      if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(*i + 40LL), a3 + 1, 1u) )
      {
        v22 = i;
        appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::erase(
          a1 + 16,
          v20,
          &v22);
        break;
      }
    }
    if ( v4 )
    {
      v15 = *(struct _ERESOURCE **)(a1 + 8);
      if ( v15 )
      {
        ExReleaseResourceLite(v15);
        KeLeaveCriticalRegion();
      }
    }
    if ( a4 )
    {
      v17 = Streaming::FlushRequestManager::Process(*(_QWORD *)(*(_QWORD *)a2 + 288LL), v21);
      v18 = (volatile signed __int32 *)*((_QWORD *)&v21[0] + 1);
      v19 = v17;
      if ( *((_QWORD *)&v21[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 16LL))(v18);
        }
      }
      return v19;
    }
    else
    {
      v16 = (volatile signed __int32 *)*((_QWORD *)&v21[0] + 1);
      if ( *((_QWORD *)&v21[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
        }
      }
      return 0;
    }
  }
  else
  {
    if ( v4 )
    {
      v11 = *(struct _ERESOURCE **)(a1 + 8);
      if ( v11 )
      {
        ExReleaseResourceLite(v11);
        KeLeaveCriticalRegion();
      }
    }
    v12 = (volatile signed __int32 *)*((_QWORD *)&v21[0] + 1);
    if ( *((_QWORD *)&v21[0] + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x140011cb0  push    rbx
0x140011cb2  push    rbp
0x140011cb3  push    rsi
0x140011cb4  push    rdi
0x140011cb5  push    r12
0x140011cb7  push    r13
0x140011cb9  push    r14
0x140011cbb  push    r15
0x140011cbd  sub     rsp, 48h
0x140011cc1  xor     sil, sil
0x140011cc4  xorps   xmm0, xmm0
0x140011cc7  cmp     qword ptr [rcx+8], 0
0x140011ccc  mov     r12b, r9b
0x140011ccf  mov     r15, r8
0x140011cd2  mov     r13, rdx
0x140011cd5  mov     rdi, rcx
0x140011cd8  mov     ebx, 1
0x140011cdd  movdqu  [rsp+88h+var_60], xmm0
0x140011ce3  jz      short loc_140011D0C
0x140011ce5  call    cs:__imp_KeEnterCriticalRegion
0x140011cec  nop     dword ptr [rax+rax+00h]
0x140011cf1  mov     rcx, [rdi+8]; Resource
0x140011cf5  mov     dl, bl; Wait
0x140011cf7  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140011cfe  nop     dword ptr [rax+rax+00h]
0x140011d03  cmp     al, bl
0x140011d05  movzx   esi, sil
0x140011d09  cmovz   esi, ebx
0x140011d0c  lea     r8, [rsp+88h+var_60]
0x140011d11  mov     rdx, r15
0x140011d14  mov     rcx, rdi
0x140011d17  call    ?Find@StreamingTargetFileCache@Streaming@@AEAAJAEBV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@VStreamingTargetFileObject@Streaming@@@kernel_std@@@Z; Streaming::StreamingTargetFileCache::Find(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> const &,kernel_std::shared_ptr<Streaming::StreamingTargetFileObject> &)
0x140011d1c  mov     ebp, eax
0x140011d1e  test    eax, eax
0x140011d20  jns     short loc_140011D90
0x140011d22  test    sil, sil
0x140011d25  jz      short loc_140011D48
0x140011d27  mov     rcx, [rdi+8]; Resource
0x140011d2b  test    rcx, rcx
0x140011d2e  jz      short loc_140011D48
0x140011d30  call    cs:__imp_ExReleaseResourceLite
0x140011d37  nop     dword ptr [rax+rax+00h]
0x140011d3c  call    cs:__imp_KeLeaveCriticalRegion
0x140011d43  nop     dword ptr [rax+rax+00h]
0x140011d48  mov     rdi, qword ptr [rsp+88h+var_60+8]
0x140011d4d  test    rdi, rdi
0x140011d50  jz      short loc_140011D89
0x140011d52  or      ebx, 0FFFFFFFFh
0x140011d55  mov     eax, ebx
0x140011d57  lock xadd [rdi+8], eax
0x140011d5c  add     eax, ebx
0x140011d5e  jnz     short loc_140011D89
0x140011d60  mov     rax, [rdi]
0x140011d63  mov     rcx, rdi
0x140011d66  mov     rax, [rax+8]
0x140011d6a  call    _guard_dispatch_icall
0x140011d6f  mov     eax, ebx
0x140011d71  lock xadd [rdi+0Ch], eax
0x140011d76  add     eax, ebx
0x140011d78  jnz     short loc_140011D89
0x140011d7a  mov     rax, [rdi]
0x140011d7d  mov     rcx, rdi
0x140011d80  mov     rax, [rax+10h]
0x140011d84  call    _guard_dispatch_icall
0x140011d89  mov     eax, ebp
0x140011d8b  jmp     loc_140011EA9
0x140011d90  mov     rbx, [rdi+30h]
0x140011d94  lea     r14, [rdi+18h]
0x140011d98  cmp     rbx, r14
0x140011d9b  jz      short loc_140011DDF
0x140011d9d  mov     rcx, [rbx]
0x140011da0  lea     rdx, [r15+10h]; String2
0x140011da4  add     rcx, 28h ; '('; String1
0x140011da8  mov     r8b, 1; CaseInSensitive
0x140011dab  call    cs:__imp_RtlCompareUnicodeString
0x140011db2  nop     dword ptr [rax+rax+00h]
0x140011db7  test    eax, eax
0x140011db9  jz      short loc_140011DC1
0x140011dbb  mov     rbx, [rbx+18h]
0x140011dbf  jmp     short loc_140011D98
0x140011dc1  lea     r8, [rsp+88h+arg_0]
0x140011dc9  mov     [rsp+88h+arg_0], rbx
0x140011dd1  lea     rdx, [rsp+88h+var_68]
0x140011dd6  lea     rcx, [rdi+10h]
0x140011dda  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>>>)
0x140011ddf  test    sil, sil
0x140011de2  jz      short loc_140011E05
0x140011de4  mov     rcx, [rdi+8]; Resource
0x140011de8  test    rcx, rcx
0x140011deb  jz      short loc_140011E05
0x140011ded  call    cs:__imp_ExReleaseResourceLite
0x140011df4  nop     dword ptr [rax+rax+00h]
0x140011df9  call    cs:__imp_KeLeaveCriticalRegion
0x140011e00  nop     dword ptr [rax+rax+00h]
0x140011e05  test    r12b, r12b
0x140011e08  jnz     short loc_140011E4F
0x140011e0a  mov     rdi, qword ptr [rsp+88h+var_60+8]
0x140011e0f  test    rdi, rdi
0x140011e12  jz      short loc_140011E4B
0x140011e14  or      ebx, 0FFFFFFFFh
0x140011e17  mov     eax, ebx
0x140011e19  lock xadd [rdi+8], eax
0x140011e1e  add     eax, ebx
0x140011e20  jnz     short loc_140011E4B
0x140011e22  mov     rax, [rdi]
0x140011e25  mov     rcx, rdi
0x140011e28  mov     rax, [rax+8]
0x140011e2c  call    _guard_dispatch_icall
0x140011e31  mov     eax, ebx
0x140011e33  lock xadd [rdi+0Ch], eax
0x140011e38  add     eax, ebx
0x140011e3a  jnz     short loc_140011E4B
0x140011e3c  mov     rax, [rdi]
0x140011e3f  mov     rcx, rdi
0x140011e42  mov     rax, [rax+10h]
0x140011e46  call    _guard_dispatch_icall
0x140011e4b  xor     eax, eax
0x140011e4d  jmp     short loc_140011EA9
0x140011e4f  mov     rcx, [r13+0]
0x140011e53  lea     rdx, [rsp+88h+var_60]
0x140011e58  mov     rcx, [rcx+120h]
0x140011e5f  call    ?Process@FlushRequestManager@Streaming@@QEAAJAEAV?$shared_ptr@VStreamingTargetFileObject@Streaming@@@kernel_std@@@Z; Streaming::FlushRequestManager::Process(kernel_std::shared_ptr<Streaming::StreamingTargetFileObject> &)
0x140011e64  mov     rdi, qword ptr [rsp+88h+var_60+8]
0x140011e69  mov     esi, eax
0x140011e6b  test    rdi, rdi
0x140011e6e  jz      short loc_140011EA7
0x140011e70  or      ebx, 0FFFFFFFFh
0x140011e73  mov     ecx, ebx
0x140011e75  lock xadd [rdi+8], ecx
0x140011e7a  add     ecx, ebx
0x140011e7c  jnz     short loc_140011EA7
0x140011e7e  mov     rdx, [rdi]
0x140011e81  mov     rcx, rdi
0x140011e84  mov     rax, [rdx+8]
0x140011e88  call    _guard_dispatch_icall
0x140011e8d  mov     eax, ebx
0x140011e8f  lock xadd [rdi+0Ch], eax
0x140011e94  add     eax, ebx
0x140011e96  jnz     short loc_140011EA7
0x140011e98  mov     rax, [rdi]
0x140011e9b  mov     rcx, rdi
0x140011e9e  mov     rax, [rax+10h]
0x140011ea2  call    _guard_dispatch_icall
0x140011ea7  mov     eax, esi
0x140011ea9  add     rsp, 48h
0x140011ead  pop     r15
0x140011eaf  pop     r14
0x140011eb1  pop     r13
0x140011eb3  pop     r12
0x140011eb5  pop     rdi
0x140011eb6  pop     rsi
0x140011eb7  pop     rbp
0x140011eb8  pop     rbx
0x140011eb9  retn
```
