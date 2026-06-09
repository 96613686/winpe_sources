# appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(_UNICODE_STRING const &)

- ea: `0x18000a864`
- end: `0x18000a950`
- name: `?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z`
- size: `236`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800038fc`
- `0x18000a958`
- `0x18000e354`
- `0x180013f40`
- `0x180014470`

## callees

- `0x18000a864`
- `0x18000e8d4`
- `0x18001bc00`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18000a938`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a938`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
        unsigned int *a1,
        const void **a2)
{
  int v2; // eax
  __int64 v5; // rsi
  unsigned int v6; // edx
  __int64 result; // rax
  void *v8; // rcx
  unsigned int v9; // ecx
  __int16 v10; // dx
  __int16 v11; // ax
  __int64 v12; // r8
  __int16 v13; // dx
  unsigned __int16 v14; // ax
  const WCHAR *v15; // rdx
  unsigned int v16; // ecx
  __int16 v17; // dx
  __int16 v18; // ax

  v2 = *(unsigned __int16 *)a2;
  if ( !(_WORD)v2 )
    return 0;
  v5 = *a1;
  v6 = v5 + v2;
  if ( (_DWORD)v5 )
  {
    result = appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(a1, v6);
    v8 = (void *)(v5 + *((_QWORD *)a1 + 1) - 2LL);
  }
  else
  {
    result = appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(
               a1,
               v6 + 2);
    v8 = (void *)*((_QWORD *)a1 + 1);
  }
  if ( (int)result >= 0 )
  {
    memmove(v8, a2[1], *(unsigned __int16 *)a2);
    if ( *a1 )
    {
      v9 = *a1 >> 1;
      if ( v9 > 0xFFFF )
        v10 = -1;
      else
        v10 = *a1 >> 1;
      v11 = 0;
      v12 = 0;
      if ( v9 <= 0xFFFF )
        v11 = v10;
      if ( v11 )
        v12 = *((_QWORD *)a1 + 1);
      if ( v9 > 0xFFFF )
        v13 = -1;
      else
        v13 = *a1 >> 1;
      v14 = 0;
      if ( v9 <= 0xFFFF )
        v14 = v13;
      *(_WORD *)(v12 + 2LL * v14 - 2) = 0;
    }
    if ( *a1 )
    {
      v16 = *a1 >> 1;
      if ( v16 > 0xFFFF )
        v17 = -1;
      else
        v17 = *a1 >> 1;
      v18 = 0;
      if ( v16 <= 0xFFFF )
        v18 = v17;
      v15 = 0;
      if ( v18 )
        v15 = (const WCHAR *)*((_QWORD *)a1 + 1);
    }
    else
    {
      v15 = 0;
    }
    RtlInitUnicodeString((PUNICODE_STRING)a1 + 1, v15);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a864  push    rbx
0x18000a866  push    rbp
0x18000a867  push    rsi
0x18000a868  push    rdi
0x18000a869  sub     rsp, 28h
0x18000a86d  movzx   eax, word ptr [rdx]
0x18000a870  xor     ebp, ebp
0x18000a872  mov     rdi, rdx
0x18000a875  mov     rbx, rcx
0x18000a878  test    ax, ax
0x18000a87b  jz      loc_18000A944
0x18000a881  mov     esi, [rcx]
0x18000a883  lea     edx, [rsi+rax]
0x18000a886  test    esi, esi
0x18000a888  jnz     short loc_18000A898
0x18000a88a  add     edx, 2
0x18000a88d  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x18000a892  mov     rcx, [rbx+8]
0x18000a896  jmp     short loc_18000A8A8
0x18000a898  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x18000a89d  mov     rcx, [rbx+8]
0x18000a8a1  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18000a8a5  add     rcx, rsi; void *
0x18000a8a8  mov     edx, eax
0x18000a8aa  test    eax, eax
0x18000a8ac  jns     short loc_18000A8B3
0x18000a8ae  jmp     loc_18000A946
0x18000a8b3  movzx   r8d, word ptr [rdi]; Size
0x18000a8b7  mov     rdx, [rdi+8]; Src
0x18000a8bb  call    memmove
0x18000a8c0  mov     ecx, [rbx]
0x18000a8c2  mov     r9d, 0FFFFh
0x18000a8c8  test    ecx, ecx
0x18000a8ca  jz      short loc_18000A909
0x18000a8cc  shr     ecx, 1
0x18000a8ce  cmp     ecx, r9d
0x18000a8d1  ja      short loc_18000A8D8
0x18000a8d3  movzx   edx, cx
0x18000a8d6  jmp     short loc_18000A8DB
0x18000a8d8  mov     edx, r9d
0x18000a8db  mov     eax, ebp
0x18000a8dd  mov     r8, rbp
0x18000a8e0  cmovbe  ax, dx
0x18000a8e4  test    ax, ax
0x18000a8e7  jz      short loc_18000A8ED
0x18000a8e9  mov     r8, [rbx+8]
0x18000a8ed  cmp     ecx, r9d
0x18000a8f0  ja      short loc_18000A8F7
0x18000a8f2  movzx   edx, cx
0x18000a8f5  jmp     short loc_18000A8FA
0x18000a8f7  mov     edx, r9d
0x18000a8fa  mov     eax, ebp
0x18000a8fc  cmovbe  ax, dx
0x18000a900  movzx   ecx, ax
0x18000a903  mov     [r8+rcx*2-2], bp
0x18000a909  mov     ecx, [rbx]
0x18000a90b  test    ecx, ecx
0x18000a90d  jnz     short loc_18000A913
0x18000a90f  xor     edx, edx
0x18000a911  jmp     short loc_18000A934
0x18000a913  shr     ecx, 1
0x18000a915  cmp     ecx, r9d
0x18000a918  ja      short loc_18000A91F
0x18000a91a  movzx   edx, cx
0x18000a91d  jmp     short loc_18000A922
0x18000a91f  mov     edx, r9d
0x18000a922  mov     eax, ebp
0x18000a924  cmovbe  ax, dx
0x18000a928  mov     rdx, rbp
0x18000a92b  test    ax, ax
0x18000a92e  jz      short loc_18000A934
0x18000a930  mov     rdx, [rbx+8]; SourceString
0x18000a934  lea     rcx, [rbx+10h]; DestinationString
0x18000a938  call    cs:__imp_RtlInitUnicodeString
0x18000a93f  nop     dword ptr [rax+rax+00h]
0x18000a944  xor     eax, eax
0x18000a946  add     rsp, 28h
0x18000a94a  pop     rdi
0x18000a94b  pop     rsi
0x18000a94c  pop     rbp
0x18000a94d  pop     rbx
0x18000a94e  retn
```
