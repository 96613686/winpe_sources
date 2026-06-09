# Streaming::FlushRequestManager::Process(kernel_std::shared_ptr<Streaming::StreamingTargetFileObject> &)

- ea: `0x1400041cc`
- end: `0x140004370`
- name: `?Process@FlushRequestManager@Streaming@@QEAAJAEAV?$shared_ptr@VStreamingTargetFileObject@Streaming@@@kernel_std@@@Z`
- size: `420`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140011bf8`
- `0x140011cb0`

## callees

- `0x14000404c`
- `0x1400041cc`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004353`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004353`
- `ntoskrnl!ExAllocatePool2` at `0x1400041ef`
- `ntoskrnl!ExAllocatePool2` at `0x140004232`
- `ntoskrnl!ExAllocatePool2` at `0x1400041ef`
- `ntoskrnl!ExAllocatePool2` at `0x140004232`

## pseudocode

```c
__int64 __fastcall Streaming::FlushRequestManager::Process(__int64 a1, _QWORD *a2)
{
  _QWORD *Pool2; // rax
  _QWORD *v5; // r14
  __int64 v6; // rax
  __int64 v7; // rax
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // rsi
  unsigned int v10; // ebp
  volatile signed __int32 *v12; // rbx
  _QWORD v13[7]; // [rsp+20h] [rbp-38h] BYREF

  Pool2 = (_QWORD *)ExAllocatePool2(256, 16, 1718773363);
  v5 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = *a2;
    v6 = a2[1];
    v5[1] = v6;
    if ( v6 )
      _InterlockedAdd((volatile signed __int32 *)(v6 + 8), 1u);
  }
  else
  {
    v5 = 0;
  }
  v7 = ExAllocatePool2(256, 24, 1715758931);
  v8 = (volatile signed __int32 *)v7;
  if ( !v7 )
  {
    if ( v5 )
    {
      v12 = (volatile signed __int32 *)v5[1];
      if ( v12 )
      {
        if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
      ExFreePoolWithTag(v5, 0);
    }
    return 3221225626LL;
  }
  *(_DWORD *)(v7 + 8) = 1;
  v9 = (volatile signed __int32 *)(v7 + 8);
  *(_DWORD *)(v7 + 12) = 1;
  *(_QWORD *)v7 = &kernel_std::detail::sp_counted_impl_p<Streaming::FlushRequestManager::FlushRequest>::`vftable';
  *(_QWORD *)(v7 + 16) = v5;
  if ( !*(_DWORD *)(v7 + 8) || !v5 || !*(_DWORD *)(v7 + 8) )
  {
    if ( _InterlockedExchangeAdd(v9, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return 3221225626LL;
  }
  v13[0] = v5;
  v13[1] = v7;
  _InterlockedAdd(v9, 1u);
  v10 = Streaming::FlushRequestManager::Process(a1, v13);
  if ( _InterlockedExchangeAdd(v9, 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return v10;
}

```

## disassembly

```asm
0x1400041cc  push    rbx
0x1400041ce  push    rbp
0x1400041cf  push    rsi
0x1400041d0  push    rdi
0x1400041d1  push    r14
0x1400041d3  sub     rsp, 30h
0x1400041d7  mov     rbx, rdx
0x1400041da  mov     rdi, rcx
0x1400041dd  mov     esi, 100h
0x1400041e2  mov     edx, 10h
0x1400041e7  mov     ecx, esi
0x1400041e9  mov     r8d, 66726673h
0x1400041ef  call    cs:__imp_ExAllocatePool2
0x1400041f6  nop     dword ptr [rax+rax+00h]
0x1400041fb  mov     r14, rax
0x1400041fe  mov     ebp, 1
0x140004203  test    rax, rax
0x140004206  jz      short loc_140004221
0x140004208  mov     rax, [rbx]
0x14000420b  mov     [r14], rax
0x14000420e  mov     rax, [rbx+8]
0x140004212  mov     [r14+8], rax
0x140004216  test    rax, rax
0x140004219  jz      short loc_140004224
0x14000421b  lock add [rax+8], ebp
0x14000421f  jmp     short loc_140004224
0x140004221  xor     r14d, r14d
0x140004224  mov     edx, 18h
0x140004229  mov     r8d, 66446753h
0x14000422f  mov     rcx, rsi
0x140004232  call    cs:__imp_ExAllocatePool2
0x140004239  nop     dword ptr [rax+rax+00h]
0x14000423e  mov     rbx, rax
0x140004241  test    rax, rax
0x140004244  jz      loc_140004309
0x14000424a  mov     [rax+8], ebp
0x14000424d  lea     rsi, [rbx+8]
0x140004251  mov     [rax+0Ch], ebp
0x140004254  lea     rax, ??_7?$sp_counted_impl_p@VFlushRequest@FlushRequestManager@Streaming@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<Streaming::FlushRequestManager::FlushRequest>::`vftable'
0x14000425b  mov     [rbx], rax
0x14000425e  mov     [rbx+10h], r14
0x140004262  mov     eax, [rsi]
0x140004264  test    eax, eax
0x140004266  jz      short loc_1400042CD
0x140004268  test    r14, r14
0x14000426b  jz      short loc_1400042CD
0x14000426d  mov     eax, [rbx+8]
0x140004270  test    eax, eax
0x140004272  jz      short loc_1400042CD
0x140004274  mov     [rsp+58h+var_38], r14
0x140004279  mov     [rsp+58h+var_30], rbx
0x14000427e  lock add [rsi], ebp
0x140004281  lea     rdx, [rsp+58h+var_38]
0x140004286  mov     rcx, rdi
0x140004289  call    ?Process@FlushRequestManager@Streaming@@AEAAJV?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@@Z; Streaming::FlushRequestManager::Process(kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>)
0x14000428e  or      edi, 0FFFFFFFFh
0x140004291  mov     ebp, eax
0x140004293  mov     ecx, edi
0x140004295  lock xadd [rsi], ecx
0x140004299  add     ecx, edi
0x14000429b  jnz     short loc_1400042C6
0x14000429d  mov     rcx, [rbx]
0x1400042a0  mov     rax, [rcx+8]
0x1400042a4  mov     rcx, rbx
0x1400042a7  call    _guard_dispatch_icall
0x1400042ac  mov     eax, edi
0x1400042ae  lock xadd [rbx+0Ch], eax
0x1400042b3  add     eax, edi
0x1400042b5  jnz     short loc_1400042C6
0x1400042b7  mov     rax, [rbx]
0x1400042ba  mov     rcx, rbx
0x1400042bd  mov     rax, [rax+10h]
0x1400042c1  call    _guard_dispatch_icall
0x1400042c6  mov     eax, ebp
0x1400042c8  jmp     loc_140004364
0x1400042cd  or      edi, 0FFFFFFFFh
0x1400042d0  mov     eax, edi
0x1400042d2  lock xadd [rsi], eax
0x1400042d6  add     eax, edi
0x1400042d8  jnz     loc_14000435F
0x1400042de  mov     rax, [rbx]
0x1400042e1  mov     rcx, rbx
0x1400042e4  mov     rax, [rax+8]
0x1400042e8  call    _guard_dispatch_icall
0x1400042ed  mov     eax, edi
0x1400042ef  lock xadd [rbx+0Ch], eax
0x1400042f4  add     eax, edi
0x1400042f6  jnz     short loc_14000435F
0x1400042f8  mov     rax, [rbx]
0x1400042fb  mov     rcx, rbx
0x1400042fe  mov     rax, [rax+10h]
0x140004302  call    _guard_dispatch_icall
0x140004307  jmp     short loc_14000435F
0x140004309  test    r14, r14
0x14000430c  jz      short loc_14000435F
0x14000430e  mov     rbx, [r14+8]
0x140004312  test    rbx, rbx
0x140004315  jz      short loc_14000434E
0x140004317  or      edi, 0FFFFFFFFh
0x14000431a  mov     eax, edi
0x14000431c  lock xadd [rbx+8], eax
0x140004321  add     eax, edi
0x140004323  jnz     short loc_14000434E
0x140004325  mov     rax, [rbx]
0x140004328  mov     rcx, rbx
0x14000432b  mov     rax, [rax+8]
0x14000432f  call    _guard_dispatch_icall
0x140004334  mov     eax, edi
0x140004336  lock xadd [rbx+0Ch], eax
0x14000433b  add     eax, edi
0x14000433d  jnz     short loc_14000434E
0x14000433f  mov     rax, [rbx]
0x140004342  mov     rcx, rbx
0x140004345  mov     rax, [rax+10h]
0x140004349  call    _guard_dispatch_icall
0x14000434e  xor     edx, edx; Tag
0x140004350  mov     rcx, r14; P
0x140004353  call    cs:__imp_ExFreePoolWithTag
0x14000435a  nop     dword ptr [rax+rax+00h]
0x14000435f  mov     eax, 0C000009Ah
0x140004364  add     rsp, 30h
0x140004368  pop     r14
0x14000436a  pop     rdi
0x14000436b  pop     rsi
0x14000436c  pop     rbp
0x14000436d  pop     rbx
0x14000436e  retn
```
