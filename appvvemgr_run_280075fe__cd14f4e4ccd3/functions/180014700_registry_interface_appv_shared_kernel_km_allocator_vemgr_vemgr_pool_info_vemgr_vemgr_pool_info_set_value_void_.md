# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)

- ea: `0x180014700`
- end: `0x1800147f5`
- name: `?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180014d1c`
- `0x180015154`

## callees

- `0x180014700`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x1800147d6`
- `ntoskrnl!ZwSetValueKey` at `0x1800147d6`

## pseudocode

```c
NTSTATUS __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
        HANDLE KeyHandle,
        wchar_t *a2,
        __int64 a3)
{
  __int64 v6; // rax
  unsigned int v7; // edx
  unsigned __int16 v8; // cx
  unsigned int v9; // ecx
  __int16 v10; // ax
  unsigned __int16 v12; // r8
  unsigned int v13; // ecx
  bool v14; // cc
  __int16 v15; // dx
  __int16 v16; // ax
  void *Data; // rcx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF

  if ( !KeyHandle || !a2 )
    return -1073741811;
  v6 = -1;
  ValueName = 0;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( (unsigned int)(2 * v6) > 0xFFFF )
    v8 = -1;
  else
    v8 = 2 * v6;
  if ( (v7 > 0xFFFF ? 0xC0000000 : 0) == 0xC0000000 )
  {
    if ( v7 > 0xFFFF )
      return v7 > 0xFFFF ? 0xC0000095 : 0;
  }
  else
  {
    ValueName.Buffer = a2;
    ValueName.MaximumLength = v8;
    ValueName.Length = v8;
  }
  v9 = *(_DWORD *)a3;
  if ( *(_DWORD *)a3 > 0xFFFFu )
    v10 = -1;
  else
    v10 = *(_DWORD *)a3;
  v12 = 0;
  if ( v9 <= 0xFFFF )
    v12 = v10;
  v13 = v9 >> 1;
  v14 = v13 <= 0xFFFF;
  if ( v13 > 0xFFFF )
    v15 = -1;
  else
    v15 = v13;
  v16 = 0;
  Data = 0;
  if ( v14 )
    v16 = v15;
  if ( v16 )
    Data = *(void **)(a3 + 8);
  return ZwSetValueKey(KeyHandle, &ValueName, 0, 1u, Data, v12);
}

```

## disassembly

```asm
0x180014700  mov     [rsp+arg_0], rsi
0x180014705  push    rdi
0x180014706  sub     rsp, 40h
0x18001470a  xor     esi, esi
0x18001470c  mov     r10, r8
0x18001470f  mov     r9, rdx
0x180014712  mov     r11, rcx
0x180014715  test    rcx, rcx
0x180014718  jz      loc_1800147E4
0x18001471e  test    rdx, rdx
0x180014721  jz      loc_1800147E4
0x180014727  xorps   xmm0, xmm0
0x18001472a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001472e  movups  xmmword ptr [rsp+48h+ValueName.Length], xmm0
0x180014733  inc     rax
0x180014736  cmp     [rdx+rax*2], si
0x18001473a  jnz     short loc_180014733
0x18001473c  lea     rdx, [rax+rax]
0x180014740  mov     edi, 0FFFFh
0x180014745  cmp     edx, edi
0x180014747  ja      short loc_18001474E
0x180014749  movzx   ecx, dx
0x18001474c  jmp     short loc_180014750
0x18001474e  mov     ecx, edi
0x180014750  cmp     edi, edx
0x180014752  sbb     r8d, r8d
0x180014755  and     r8d, 0C0000095h
0x18001475c  mov     eax, r8d
0x18001475f  and     eax, 0C0000000h
0x180014764  cmp     eax, 0C0000000h
0x180014769  jz      short loc_180014786
0x18001476b  mov     [rsp+48h+ValueName.Buffer], r9
0x180014770  mov     [rsp+48h+ValueName.MaximumLength], cx
0x180014775  mov     [rsp+48h+ValueName.Length], cx
0x18001477a  mov     ecx, [r10]
0x18001477d  cmp     ecx, edi
0x18001477f  ja      short loc_18001478F
0x180014781  movzx   eax, cx
0x180014784  jmp     short loc_180014791
0x180014786  cmp     edx, edi
0x180014788  jbe     short loc_18001477A
0x18001478a  mov     eax, r8d
0x18001478d  jmp     short loc_1800147E9
0x18001478f  mov     eax, edi
0x180014791  mov     r8d, esi
0x180014794  cmovbe  r8w, ax
0x180014799  shr     ecx, 1
0x18001479b  cmp     ecx, edi
0x18001479d  ja      short loc_1800147A4
0x18001479f  movzx   edx, cx
0x1800147a2  jmp     short loc_1800147A6
0x1800147a4  mov     edx, edi
0x1800147a6  mov     eax, esi
0x1800147a8  mov     rcx, rsi
0x1800147ab  cmovbe  ax, dx
0x1800147af  test    ax, ax
0x1800147b2  jz      short loc_1800147B8
0x1800147b4  mov     rcx, [r10+8]
0x1800147b8  movzx   eax, r8w
0x1800147bc  lea     rdx, [rsp+48h+ValueName]; ValueName
0x1800147c1  mov     [rsp+48h+DataSize], eax; DataSize
0x1800147c5  mov     r9d, 1; Type
0x1800147cb  mov     [rsp+48h+Data], rcx; Data
0x1800147d0  xor     r8d, r8d; TitleIndex
0x1800147d3  mov     rcx, r11; KeyHandle
0x1800147d6  call    cs:__imp_ZwSetValueKey
0x1800147dd  nop     dword ptr [rax+rax+00h]
0x1800147e2  jmp     short loc_1800147E9
0x1800147e4  mov     eax, 0C000000Dh
0x1800147e9  mov     rsi, [rsp+48h+arg_0]
0x1800147ee  add     rsp, 40h
0x1800147f2  pop     rdi
0x1800147f3  retn
```
