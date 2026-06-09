# AhcApiSnapCache

- ea: `0x14002b950`
- end: `0x14002baa0`
- name: `AhcApiSnapCache`
- size: `336`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400497bc`

## callees

- `0x140001c9c`
- `0x140027c9c`
- `0x14002b950`
- `0x14003e364`
- `0x140045d6c`
- `0x14004c2e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002ba84`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ba84`

## string_xrefs

- `0x14002b9fa`: `Failed to save cache to stream [%x]`
- `0x14002b99e`: `Failed to pass security check [%x]`
- `0x14002ba2b`: `AhcSafeCopyMemoryToUserMode failed [%x]`
- `0x14002b9d5`: `AhcApiSnapCache`
- `0x14002ba38`: `AhcApiSnapCache`

## pseudocode

```c
__int64 __fastcall AhcApiSnapCache(__int64 a1, void *a2, unsigned int a3, void *a4)
{
  size_t v4; // rdi
  int v8; // eax
  void *v9; // rdx
  int v10; // ebx
  const char *v11; // r9
  __int64 v12; // r8
  int v13; // eax
  int Src; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+38h] [rbp-40h] BYREF
  size_t Size[2]; // [rsp+40h] [rbp-38h]
  __int64 v18; // [rsp+50h] [rbp-28h]
  PVOID P[2]; // [rsp+58h] [rbp-20h]

  v4 = a3;
  v16 = 0;
  *(_OWORD *)Size = 0;
  *(_OWORD *)P = 0;
  v18 = 4096;
  Src = 0;
  v8 = AhcVerifyAdminContext();
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = "Failed to pass security check [%x]";
    v12 = 924;
LABEL_11:
    AslLogCallPrintf(1, "AhcApiSnapCache", v12, v11, v8);
LABEL_12:
    if ( v10 != -1073741789 )
      goto LABEL_17;
    goto LABEL_15;
  }
  v10 = RtlMemoryStream::Initialize((RtlMemoryStream *)&v16, v9, 0x40000u, 0x40000u);
  if ( v10 < 0 )
  {
    AslLogCallPrintf(1, "AhcApiSnapCache", 934, "Out of memory");
    goto LABEL_12;
  }
  v8 = AhcCacheSave(a1, &v16);
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = "Failed to save cache to stream [%x]";
    v12 = 940;
    goto LABEL_11;
  }
  if ( Size[0] <= v4 )
  {
    v8 = AhcSafeCopyMemoryToUserMode(a2, P[1], Size[0]);
    v10 = v8;
    if ( v8 < 0 )
    {
      v11 = "AhcSafeCopyMemoryToUserMode failed [%x]";
      v12 = 960;
      goto LABEL_11;
    }
    v10 = 0;
  }
  else
  {
    v10 = -1073741789;
  }
LABEL_15:
  Src = Size[0];
  v13 = AhcSafeCopyMemoryToUserMode(a4, &Src, 4u);
  if ( v13 < 0 )
    v10 = v13;
LABEL_17:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x7274534Du);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14002b950  push    rbp
0x14002b952  push    rbx
0x14002b953  push    rsi
0x14002b954  push    rdi
0x14002b955  push    r14
0x14002b957  push    r15
0x14002b959  mov     rbp, rsp
0x14002b95c  sub     rsp, 78h
0x14002b960  xorps   xmm0, xmm0
0x14002b963  mov     edi, r8d
0x14002b966  xorps   xmm1, xmm1
0x14002b969  mov     [rbp+var_40], 0
0x14002b971  movdqu  xmmword ptr [rbp+Size], xmm0
0x14002b976  mov     r15, r9
0x14002b979  mov     r14, rdx
0x14002b97c  movdqu  xmmword ptr [rbp+P], xmm1
0x14002b981  mov     rsi, rcx
0x14002b984  mov     [rbp+var_28], 1000h
0x14002b98c  mov     [rbp+Src], 0
0x14002b993  call    AhcVerifyAdminContext
0x14002b998  mov     ebx, eax
0x14002b99a  test    eax, eax
0x14002b99c  jns     short loc_14002B9B0
0x14002b99e  lea     r9, aFailedToPassSe; "Failed to pass security check [%x]"
0x14002b9a5  mov     r8d, 39Ch
0x14002b9ab  jmp     loc_14002BA38
0x14002b9b0  mov     r8d, 40000h; unsigned __int64
0x14002b9b6  lea     rcx, [rbp+var_40]; this
0x14002b9ba  mov     r9d, r8d; unsigned __int64
0x14002b9bd  call    ?Initialize@RtlMemoryStream@@QEAAJPEAX_K1@Z; RtlMemoryStream::Initialize(void *,unsigned __int64,unsigned __int64)
0x14002b9c2  mov     ebx, eax
0x14002b9c4  test    eax, eax
0x14002b9c6  jns     short loc_14002B9E8
0x14002b9c8  lea     r9, aOutOfMemory; "Out of memory"
0x14002b9cf  mov     r8d, 3A6h
0x14002b9d5  lea     rdx, aAhcapisnapcach; "AhcApiSnapCache"
0x14002b9dc  mov     ecx, 1
0x14002b9e1  call    AslLogCallPrintf
0x14002b9e6  jmp     short loc_14002BA4D
0x14002b9e8  lea     rdx, [rbp+var_40]
0x14002b9ec  mov     rcx, rsi
0x14002b9ef  call    AhcCacheSave
0x14002b9f4  mov     ebx, eax
0x14002b9f6  test    eax, eax
0x14002b9f8  jns     short loc_14002BA09
0x14002b9fa  lea     r9, aFailedToSaveCa_0; "Failed to save cache to stream [%x]"
0x14002ba01  mov     r8d, 3ACh
0x14002ba07  jmp     short loc_14002BA38
0x14002ba09  mov     r8, [rbp+Size]; Size
0x14002ba0d  cmp     r8, rdi
0x14002ba10  jbe     short loc_14002BA19
0x14002ba12  mov     ebx, 0C0000023h
0x14002ba17  jmp     short loc_14002BA59
0x14002ba19  mov     rdx, [rbp+P+8]; Src
0x14002ba1d  mov     rcx, r14; void *
0x14002ba20  call    AhcSafeCopyMemoryToUserMode
0x14002ba25  mov     ebx, eax
0x14002ba27  test    eax, eax
0x14002ba29  jns     short loc_14002BA57
0x14002ba2b  lea     r9, aAhcsafecopymem_1; "AhcSafeCopyMemoryToUserMode failed [%x]"
0x14002ba32  mov     r8d, 3C0h
0x14002ba38  lea     rdx, aAhcapisnapcach; "AhcApiSnapCache"
0x14002ba3f  mov     [rsp+78h+var_58], eax
0x14002ba43  mov     ecx, 1
0x14002ba48  call    AslLogCallPrintf
0x14002ba4d  cmp     ebx, 0C0000023h
0x14002ba53  jnz     short loc_14002BA76
0x14002ba55  jmp     short loc_14002BA59
0x14002ba57  xor     ebx, ebx
0x14002ba59  mov     eax, dword ptr [rbp+Size]
0x14002ba5c  lea     rdx, [rbp+Src]; Src
0x14002ba60  mov     r8d, 4; Size
0x14002ba66  mov     [rbp+Src], eax
0x14002ba69  mov     rcx, r15; void *
0x14002ba6c  call    AhcSafeCopyMemoryToUserMode
0x14002ba71  test    eax, eax
0x14002ba73  cmovs   ebx, eax
0x14002ba76  mov     rcx, [rbp+P+8]; P
0x14002ba7a  test    rcx, rcx
0x14002ba7d  jz      short loc_14002BA90
0x14002ba7f  mov     edx, 7274534Dh; Tag
0x14002ba84  call    cs:__imp_ExFreePoolWithTag
0x14002ba8b  nop     dword ptr [rax+rax+00h]
0x14002ba90  mov     eax, ebx
0x14002ba92  add     rsp, 78h
0x14002ba96  pop     r15
0x14002ba98  pop     r14
0x14002ba9a  pop     rdi
0x14002ba9b  pop     rsi
0x14002ba9c  pop     rbx
0x14002ba9d  pop     rbp
0x14002ba9e  retn
```
