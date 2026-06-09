# VfsScbTableCloseScb

- ea: `0x14000da2c`
- end: `0x14000db4a`
- name: `VfsScbTableCloseScb`
- size: `286`
- prototype: `void __fastcall(__int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000d868`

## callees

- `0x14000da2c`
- `0x140013b00`
- `0x140014000`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14000dad9`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14000dad9`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000dafe`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000dafe`
- `ntoskrnl!RtlCopySid` at `0x14000dac4`
- `ntoskrnl!RtlCopySid` at `0x14000dac4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000db19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000db19`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000db0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000db0d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000da6f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000da6f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000da5e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000da5e`

## pseudocode

```c
void __fastcall VfsScbTableCloseScb(__int64 a1, __int64 a2, _BYTE *a3)
{
  struct _ERESOURCE *v4; // rbx
  __int128 v7; // xmm1
  _QWORD *v8; // rax
  _OWORD Buffer[7]; // [rsp+20h] [rbp-98h] BYREF

  *a3 = 0;
  v4 = *(struct _ERESOURCE **)a2;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(v4, 1u);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 276), 0xFFFFFFFF) == 1 )
  {
    memset(Buffer, 0, 0x64u);
    v7 = *(_OWORD *)(a1 + 236);
    Buffer[0] = *(_OWORD *)(a1 + 220);
    Buffer[1] = v7;
    RtlCopySid(0x44u, &Buffer[2], (PSID)(a1 + 152));
    v8 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(a2 + 8), Buffer);
    if ( v8 )
    {
      if ( v8[14] )
        *a3 = 1;
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a2 + 8), Buffer);
    }
  }
  ExReleaseResourceLite(*(PERESOURCE *)a2);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14000da2c  mov     [rsp+arg_18], rbx
0x14000da31  push    rsi
0x14000da32  push    rdi
0x14000da33  push    r14
0x14000da35  sub     rsp, 0A0h
0x14000da3c  mov     rax, cs:__security_cookie
0x14000da43  xor     rax, rsp
0x14000da46  mov     [rsp+0B8h+var_28], rax
0x14000da4e  mov     byte ptr [r8], 0
0x14000da52  mov     r14, r8
0x14000da55  mov     rbx, [rdx]
0x14000da58  mov     rdi, rdx
0x14000da5b  mov     rsi, rcx
0x14000da5e  call    cs:__imp_KeEnterCriticalRegion
0x14000da65  nop     dword ptr [rax+rax+00h]
0x14000da6a  mov     dl, 1; Wait
0x14000da6c  mov     rcx, rbx; Resource
0x14000da6f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000da76  nop     dword ptr [rax+rax+00h]
0x14000da7b  or      eax, 0FFFFFFFFh
0x14000da7e  lock xadd [rsi+114h], eax
0x14000da86  cmp     eax, 1
0x14000da89  jnz     short loc_14000DB0A
0x14000da8b  xor     edx, edx; Val
0x14000da8d  lea     r8d, [rax+63h]; Size
0x14000da91  lea     rcx, [rsp+0B8h+Buffer]; void *
0x14000da96  call    memset
0x14000da9b  movups  xmm0, xmmword ptr [rsi+0DCh]
0x14000daa2  lea     r8, [rsi+98h]; SourceSid
0x14000daa9  mov     ecx, 44h ; 'D'; DestinationSidLength
0x14000daae  movups  xmm1, xmmword ptr [rsi+0ECh]
0x14000dab5  lea     rdx, [rsp+0B8h+DestinationSid]; DestinationSid
0x14000daba  movaps  [rsp+0B8h+Buffer], xmm0
0x14000dabf  movaps  [rsp+0B8h+var_88], xmm1
0x14000dac4  call    cs:__imp_RtlCopySid
0x14000dacb  nop     dword ptr [rax+rax+00h]
0x14000dad0  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x14000dad5  lea     rcx, [rdi+8]; Table
0x14000dad9  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14000dae0  nop     dword ptr [rax+rax+00h]
0x14000dae5  test    rax, rax
0x14000dae8  jz      short loc_14000DB0A
0x14000daea  cmp     qword ptr [rax+70h], 0
0x14000daef  jz      short loc_14000DAF5
0x14000daf1  mov     byte ptr [r14], 1
0x14000daf5  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x14000dafa  lea     rcx, [rdi+8]; Table
0x14000dafe  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14000db05  nop     dword ptr [rax+rax+00h]
0x14000db0a  mov     rcx, [rdi]; Resource
0x14000db0d  call    cs:__imp_ExReleaseResourceLite
0x14000db14  nop     dword ptr [rax+rax+00h]
0x14000db19  call    cs:__imp_KeLeaveCriticalRegion
0x14000db20  nop     dword ptr [rax+rax+00h]
0x14000db25  mov     rcx, [rsp+0B8h+var_28]
0x14000db2d  xor     rcx, rsp; StackCookie
0x14000db30  call    __security_check_cookie
0x14000db35  mov     rbx, [rsp+0B8h+arg_18]
0x14000db3d  add     rsp, 0A0h
0x14000db44  pop     r14
0x14000db46  pop     rdi
0x14000db47  pop     rsi
0x14000db48  retn
```
