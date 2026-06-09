# appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(_UNICODE_STRING const &)

- ea: `0x18000a864`
- end: `0x18000a950`
- name: `?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, const void **, __int64, __int64)`
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
        struct _UNICODE_STRING *a1,
        const void **a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // eax
  __int64 v7; // rsi
  __int64 v8; // rdx
  __int64 result; // rax
  wchar_t *Buffer; // rcx
  unsigned int v11; // ecx
  __int16 v12; // dx
  __int16 v13; // ax
  wchar_t *v14; // r8
  __int16 v15; // dx
  unsigned __int16 v16; // ax
  const WCHAR *v17; // rdx
  unsigned int v18; // ecx
  __int16 v19; // dx
  __int16 v20; // ax

  v4 = *(unsigned __int16 *)a2;
  if ( !(_WORD)v4 )
    return 0;
  v7 = *(unsigned int *)&a1->Length;
  v8 = (unsigned int)(v7 + v4);
  if ( (_DWORD)v7 )
  {
    result = appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(
               a1,
               v8,
               a3,
               a4);
    Buffer = (wchar_t *)((char *)a1->Buffer + v7 - 2);
  }
  else
  {
    result = appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(
               a1,
               (unsigned int)(v8 + 2),
               a3,
               a4);
    Buffer = a1->Buffer;
  }
  if ( (int)result >= 0 )
  {
    memmove(Buffer, a2[1], *(unsigned __int16 *)a2);
    if ( *(_DWORD *)&a1->Length )
    {
      v11 = *(_DWORD *)&a1->Length >> 1;
      if ( v11 > 0xFFFF )
        v12 = -1;
      else
        v12 = *(_DWORD *)&a1->Length >> 1;
      v13 = 0;
      v14 = 0;
      if ( v11 <= 0xFFFF )
        v13 = v12;
      if ( v13 )
        v14 = a1->Buffer;
      if ( v11 > 0xFFFF )
        v15 = -1;
      else
        v15 = *(_DWORD *)&a1->Length >> 1;
      v16 = 0;
      if ( v11 <= 0xFFFF )
        v16 = v15;
      v14[v16 - 1] = 0;
    }
    if ( *(_DWORD *)&a1->Length )
    {
      v18 = *(_DWORD *)&a1->Length >> 1;
      if ( v18 > 0xFFFF )
        v19 = -1;
      else
        v19 = *(_DWORD *)&a1->Length >> 1;
      v20 = 0;
      if ( v18 <= 0xFFFF )
        v20 = v19;
      v17 = 0;
      if ( v20 )
        v17 = a1->Buffer;
    }
    else
    {
      v17 = 0;
    }
    RtlInitUnicodeString(a1 + 1, v17);
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
