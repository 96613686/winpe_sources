# VfsLookupMappingEntry

- ea: `0x1400090c8`
- end: `0x14000920f`
- name: `VfsLookupMappingEntry`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140009218`

## callees

- `0x1400090c8`
- `0x140011c50`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14000911e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000911e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400090ff`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400090ff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400091eb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400091eb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400091df`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400091df`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400090ee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400090ee`

## pseudocode

```c
bool __fastcall VfsLookupMappingEntry(
        __int64 a1,
        const UNICODE_STRING *a2,
        unsigned __int16 *a3,
        __m128i *a4,
        _QWORD *a5)
{
  struct _ERESOURCE *v5; // rbx
  __int64 v6; // rbp
  const UNICODE_STRING *i; // rbx
  LONG v12; // eax
  __int64 v13; // rcx
  __int64 prefix; // rbx
  void *v15; // rcx
  __m128i v16; // xmm0
  _WORD *v17; // rdx
  __m128i v19[5]; // [rsp+20h] [rbp-58h] BYREF

  v5 = *(struct _ERESOURCE **)a1;
  v6 = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite(v5, 1u);
  for ( i = *(const UNICODE_STRING **)(a1 + 8);
        i != (const UNICODE_STRING *)(a1 + 8);
        i = *(const UNICODE_STRING **)&i->Length )
  {
    v12 = RtlCompareUnicodeString(i + 1, a2, 1u);
    if ( v12 >= 0 )
    {
      if ( v12 <= 0 )
      {
        if ( *a3 )
        {
          v13 = *(_QWORD *)&i[2].Length;
          v19[0] = 0;
          prefix = appv::shared::vfs::prefix_tree<PrefixTreeContext,PrefixTreeAllocator>::find_prefix(v13, a3, v19);
          if ( prefix )
          {
            if ( PrefixTreeContext::referenceCallback )
            {
              v15 = *(void **)(prefix + 160);
              if ( v15 )
                PrefixTreeContext::referenceCallback(v15);
            }
            v16 = v19[0];
            v6 = *(_QWORD *)(prefix + 160);
            *a5 = v6;
            *a4 = v16;
            if ( !(unsigned __int16)_mm_cvtsi128_si32(v16) && *a3 >= 2u )
            {
              v17 = (_WORD *)(*((_QWORD *)a3 + 1) - 2LL + 2 * ((unsigned __int64)*a3 >> 1));
              if ( *v17 == 92 )
              {
                a4->m128i_i64[1] = (__int64)v17;
                a4->m128i_i32[0] = 131074;
              }
            }
          }
        }
      }
      break;
    }
  }
  ExReleaseResourceLite(*(PERESOURCE *)a1);
  KeLeaveCriticalRegion();
  return v6 != 0;
}

```

## disassembly

```asm
0x1400090c8  push    rbx
0x1400090ca  push    rbp
0x1400090cb  push    rsi
0x1400090cc  push    rdi
0x1400090cd  push    r12
0x1400090cf  push    r13
0x1400090d1  push    r14
0x1400090d3  push    r15
0x1400090d5  sub     rsp, 38h
0x1400090d9  mov     rbx, [rcx]
0x1400090dc  xor     r13d, r13d
0x1400090df  mov     ebp, r13d
0x1400090e2  mov     rsi, r9
0x1400090e5  mov     rdi, r8
0x1400090e8  mov     r12, rdx
0x1400090eb  mov     r15, rcx
0x1400090ee  call    cs:__imp_KeEnterCriticalRegion
0x1400090f5  nop     dword ptr [rax+rax+00h]
0x1400090fa  mov     dl, 1; Wait
0x1400090fc  mov     rcx, rbx; Resource
0x1400090ff  call    cs:__imp_ExAcquireResourceSharedLite
0x140009106  nop     dword ptr [rax+rax+00h]
0x14000910b  lea     r14, [r15+8]
0x14000910f  mov     rbx, [r14]
0x140009112  jmp     short loc_140009131
0x140009114  lea     rcx, [rbx+10h]; String1
0x140009118  mov     r8b, 1; CaseInSensitive
0x14000911b  mov     rdx, r12; String2
0x14000911e  call    cs:__imp_RtlCompareUnicodeString
0x140009125  nop     dword ptr [rax+rax+00h]
0x14000912a  test    eax, eax
0x14000912c  jns     short loc_14000913B
0x14000912e  mov     rbx, [rbx]
0x140009131  cmp     rbx, r14
0x140009134  jnz     short loc_140009114
0x140009136  jmp     loc_1400091DC
0x14000913b  jg      loc_1400091DC
0x140009141  cmp     r13w, [rdi]
0x140009145  jz      loc_1400091DC
0x14000914b  mov     rcx, [rbx+20h]
0x14000914f  lea     r8, [rsp+78h+var_58]
0x140009154  xorps   xmm0, xmm0
0x140009157  mov     rdx, rdi
0x14000915a  movups  [rsp+78h+var_58], xmm0
0x14000915f  call    ?find_prefix@?$prefix_tree@VPrefixTreeContext@@VPrefixTreeAllocator@@@vfs@shared@appv@@AEBAPEAU?$prefix_tree_name_entry@VPrefixTreeContext@@@234@AEBU_UNICODE_STRING@@AEAU6@@Z; appv::shared::vfs::prefix_tree<PrefixTreeContext,PrefixTreeAllocator>::find_prefix(_UNICODE_STRING const &,_UNICODE_STRING &)
0x140009164  mov     rbx, rax
0x140009167  test    rax, rax
0x14000916a  jz      short loc_1400091DC
0x14000916c  mov     rax, cs:?referenceCallback@PrefixTreeContext@@2P6AXPEAX@ZEA; void (*PrefixTreeContext::referenceCallback)(void *)
0x140009173  test    rax, rax
0x140009176  jz      short loc_140009189
0x140009178  mov     rcx, [rbx+0A0h]
0x14000917f  test    rcx, rcx
0x140009182  jz      short loc_140009189
0x140009184  call    _guard_dispatch_icall
0x140009189  mov     rax, [rsp+78h+arg_20]
0x140009191  movups  xmm0, [rsp+78h+var_58]
0x140009196  mov     rbp, [rbx+0A0h]
0x14000919d  mov     [rax], rbp
0x1400091a0  movd    eax, xmm0
0x1400091a4  movdqu  xmmword ptr [rsi], xmm0
0x1400091a8  test    ax, ax
0x1400091ab  jnz     short loc_1400091DC
0x1400091ad  movzx   eax, word ptr [rdi]
0x1400091b0  mov     r8d, 2
0x1400091b6  cmp     ax, r8w
0x1400091ba  jb      short loc_1400091DC
0x1400091bc  mov     edx, eax
0x1400091be  mov     rax, [rdi+8]
0x1400091c2  sub     rax, r8
0x1400091c5  shr     rdx, 1
0x1400091c8  lea     rdx, [rax+rdx*2]
0x1400091cc  cmp     word ptr [rdx], 5Ch ; '\'
0x1400091d0  jnz     short loc_1400091DC
0x1400091d2  mov     [rsi+8], rdx
0x1400091d6  mov     dword ptr [rsi], 20002h
0x1400091dc  mov     rcx, [r15]; Resource
0x1400091df  call    cs:__imp_ExReleaseResourceLite
0x1400091e6  nop     dword ptr [rax+rax+00h]
0x1400091eb  call    cs:__imp_KeLeaveCriticalRegion
0x1400091f2  nop     dword ptr [rax+rax+00h]
0x1400091f7  test    rbp, rbp
0x1400091fa  setnz   al
0x1400091fd  add     rsp, 38h
0x140009201  pop     r15
0x140009203  pop     r14
0x140009205  pop     r13
0x140009207  pop     r12
0x140009209  pop     rdi
0x14000920a  pop     rsi
0x14000920b  pop     rbp
0x14000920c  pop     rbx
0x14000920d  retn
```
