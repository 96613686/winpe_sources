# AhcProbeAndReadEnvironment

- ea: `0x140046908`
- end: `0x140046bd1`
- name: `AhcProbeAndReadEnvironment`
- size: `713`
- prototype: `__int64 __fastcall(void *Src, size_t Size, RtlMemoryStream *this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140046f60`

## callees

- `0x140001b78`
- `0x1400045b0`
- `0x140007b40`
- `0x140007e40`
- `0x14003e364`
- `0x140045d44`
- `0x140046908`
- `0x14005498c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140046acd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046acd`
- `ntoskrnl!KeGetCurrentIrql` at `0x140046a15`
- `ntoskrnl!KeGetCurrentIrql` at `0x140046a5c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140046a15`
- `ntoskrnl!KeGetCurrentIrql` at `0x140046a5c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140046a34`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140046a7b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140046a34`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140046a7b`
- `ntoskrnl!ProbeForRead` at `0x14004693e`
- `ntoskrnl!ProbeForRead` at `0x14004693e`

## string_xrefs

- `0x1400469a6`: `AhcProbeAndReadEnvironment`
- `0x140046b84`: `AhcProbeAndReadEnvironment`
- `0x140046b52`: `Failed to write double null [%x]`
- `0x140046b77`: `Exception reading environment [%x]`

## pseudocode

```c
__int64 __fastcall AhcProbeAndReadEnvironment(void *Src, size_t Size, RtlMemoryStream *this)
{
  size_t v5; // rbx
  __int64 v6; // rcx
  void *v7; // rax
  unsigned __int64 v8; // rcx
  void *v9; // r14
  int v10; // ebx
  int v11; // eax
  unsigned __int64 v12; // r13
  unsigned __int64 *v13; // r15
  __int64 v14; // rbx
  SIZE_T v15; // rbx
  KIRQL v16; // al
  POOL_TYPE v17; // ecx
  PVOID v18; // rax
  void *v19; // rsi
  KIRQL CurrentIrql; // al
  POOL_TYPE v21; // ecx
  PVOID PoolWithTag; // rax
  size_t v23; // r8
  _QWORD *v24; // rax
  int v25; // eax
  unsigned __int64 v26; // rax
  void *Srca; // [rsp+98h] [rbp+20h]

  v5 = (unsigned int)Size;
  ProbeForRead(Src, (unsigned int)Size, 1u);
  v7 = (void *)AslAlloc(v6, (unsigned int)v5, 1);
  v9 = v7;
  if ( !v7 )
  {
    v10 = -1073741801;
    goto LABEL_38;
  }
  RtlCopyFromUser(v7, Src, v5);
  v11 = RtlMemoryStream::InitializeFromBuffer(this, v9, v5);
  v10 = v11;
  if ( v11 < 0 )
  {
    AslLogCallPrintf(1, "AhcProbeAndReadEnvironment", 1172, "Failed to snap environment to stream [%x]", v11);
    goto LABEL_38;
  }
  v12 = *((_QWORD *)this + 1);
  v13 = (unsigned __int64 *)((char *)this + 32);
  *((_QWORD *)this + 4) = v12;
  v8 = v12 + 4;
  if ( v12 + 4 < v12 )
  {
    v10 = -1073741811;
    goto LABEL_35;
  }
  if ( v8 <= *((_QWORD *)this + 2) )
  {
    v24 = (_QWORD *)((char *)this + 32);
LABEL_27:
    *(_DWORD *)(*((_QWORD *)this + 5) + *v24) = 0;
    v8 = *v13 + 4;
    if ( v8 < *v13 )
    {
      v8 = -1;
      v25 = -2147024362;
    }
    else
    {
      v25 = 0;
    }
    *v13 = v8;
    if ( v25 >= 0 )
    {
      v26 = *((_QWORD *)this + 1);
      if ( v26 <= v8 )
        v26 = v8;
      *((_QWORD *)this + 1) = v26;
      v10 = 0;
      goto LABEL_35;
    }
    goto LABEL_31;
  }
  v14 = *((_QWORD *)this + 3) - 1LL;
  if ( v14 + v8 >= v8 )
  {
    v15 = (v14 + v8) & ~v14;
    Srca = (void *)*((_QWORD *)this + 5);
    if ( Srca )
    {
      CurrentIrql = KeGetCurrentIrql();
      v21 = 512;
      if ( CurrentIrql != 2 )
        v21 = PagedPool;
      PoolWithTag = ExAllocatePoolWithTag(v21, v15, 0x7274534Du);
      v19 = PoolWithTag;
      if ( PoolWithTag )
        memset(PoolWithTag, 0, v15);
      if ( !v19 )
        goto LABEL_24;
      v23 = v15;
      if ( v12 < v15 )
        v23 = v12;
      memmove(v19, Srca, v23);
      ExFreePoolWithTag(Srca, 0x7274534Du);
    }
    else
    {
      v16 = KeGetCurrentIrql();
      v17 = 512;
      if ( v16 != 2 )
        v17 = PagedPool;
      v18 = ExAllocatePoolWithTag(v17, v15, 0x7274534Du);
      v19 = v18;
      if ( v18 )
        memset(v18, 0, v15);
    }
    if ( !v19 )
    {
LABEL_24:
      v10 = -1073741801;
      goto LABEL_35;
    }
    *((_QWORD *)this + 5) = v19;
    *((_QWORD *)this + 2) = v15;
    v24 = (_QWORD *)((char *)this + 32);
    goto LABEL_27;
  }
LABEL_31:
  v10 = -1073741675;
LABEL_35:
  if ( v10 >= 0 )
    *v13 = 0;
  else
    AslLogCallPrintf(1, "AhcProbeAndReadEnvironment", 1184, "Failed to write double null [%x]", v10);
LABEL_38:
  if ( v9 && v9 != Src )
    AslFree(v8, v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140046908  mov     rax, rsp
0x14004690b  mov     [rax+10h], rbx
0x14004690f  mov     [rax+18h], rsi
0x140046913  mov     [rax+8], rcx
0x140046917  push    rdi
0x140046918  push    r12
0x14004691a  push    r13
0x14004691c  push    r14
0x14004691e  push    r15
0x140046920  sub     rsp, 50h
0x140046924  mov     rdi, r8
0x140046927  mov     r12, rcx
0x14004692a  mov     qword ptr [rax-38h], 0
0x140046932  mov     ebx, edx
0x140046934  mov     esi, 1
0x140046939  mov     r8d, esi; Alignment
0x14004693c  mov     edx, edx; Length
0x14004693e  call    cs:__imp_ProbeForRead
0x140046945  nop     dword ptr [rax+rax+00h]
0x14004694a  mov     r8d, esi
0x14004694d  mov     edx, ebx
0x14004694f  call    AslAlloc
0x140046954  mov     r14, rax
0x140046957  mov     [rsp+78h+var_38], rax
0x14004695c  test    rax, rax
0x14004695f  jnz     short loc_14004696F
0x140046961  mov     ebx, 0C0000017h
0x140046966  mov     [rsp+78h+var_48], ebx
0x14004696a  jmp     loc_140046B6B
0x14004696f  mov     r8, rbx; Size
0x140046972  mov     rdx, r12; Src
0x140046975  mov     rcx, r14; void *
0x140046978  call    RtlCopyFromUser
0x14004697d  mov     r8, rbx; unsigned __int64
0x140046980  mov     rdx, r14; void *
0x140046983  mov     rcx, rdi; this
0x140046986  call    ?InitializeFromBuffer@RtlMemoryStream@@QEAAJQEAX_K@Z; RtlMemoryStream::InitializeFromBuffer(void * const,unsigned __int64)
0x14004698b  mov     ebx, eax
0x14004698d  mov     [rsp+78h+var_48], eax
0x140046991  test    eax, eax
0x140046993  jns     short loc_1400469B9
0x140046995  mov     [rsp+78h+var_58], eax
0x140046999  lea     r9, aFailedToSnapEn; "Failed to snap environment to stream [%"...
0x1400469a0  mov     r8d, 494h
0x1400469a6  lea     rdx, aAhcprobeandrea; "AhcProbeAndReadEnvironment"
0x1400469ad  mov     ecx, esi
0x1400469af  call    AslLogCallPrintf
0x1400469b4  jmp     loc_140046B6B
0x1400469b9  mov     r13, [rdi+8]
0x1400469bd  lea     r15, [rdi+20h]
0x1400469c1  mov     [r15], r13
0x1400469c4  lea     rcx, [r13+4]
0x1400469c8  cmp     rcx, r13
0x1400469cb  jnb     short loc_1400469D7
0x1400469cd  mov     ebx, 0C000000Dh
0x1400469d2  jmp     loc_140046B46
0x1400469d7  cmp     rcx, [rdi+10h]
0x1400469db  jbe     loc_140046AFD
0x1400469e1  mov     rbx, [rdi+18h]
0x1400469e5  dec     rbx
0x1400469e8  lea     rax, [rbx+rcx]
0x1400469ec  cmp     rax, rcx
0x1400469ef  jb      loc_140046B2E
0x1400469f5  not     rbx
0x1400469f8  and     rbx, rax
0x1400469fb  mov     rax, [rdi+28h]
0x1400469ff  mov     [rsp+78h+Src], rax
0x140046a07  mov     [rsp+78h+var_40], 0
0x140046a10  test    rax, rax
0x140046a13  jnz     short loc_140046A5C
0x140046a15  call    cs:__imp_KeGetCurrentIrql
0x140046a1c  nop     dword ptr [rax+rax+00h]
0x140046a21  mov     ecx, 200h
0x140046a26  cmp     al, 2
0x140046a28  cmovnz  ecx, esi; PoolType
0x140046a2b  mov     r8d, 7274534Dh; Tag
0x140046a31  mov     rdx, rbx; NumberOfBytes
0x140046a34  call    cs:__imp_ExAllocatePoolWithTag
0x140046a3b  nop     dword ptr [rax+rax+00h]
0x140046a40  mov     rsi, rax
0x140046a43  test    rax, rax
0x140046a46  jz      short loc_140046A55
0x140046a48  mov     r8, rbx; Size
0x140046a4b  xor     edx, edx; Val
0x140046a4d  mov     rcx, rax; void *
0x140046a50  call    memset
0x140046a55  mov     [rsp+78h+var_40], rsi
0x140046a5a  jmp     short loc_140046AD9
0x140046a5c  call    cs:__imp_KeGetCurrentIrql
0x140046a63  nop     dword ptr [rax+rax+00h]
0x140046a68  mov     ecx, 200h
0x140046a6d  cmp     al, 2
0x140046a6f  cmovnz  ecx, esi; PoolType
0x140046a72  mov     r8d, 7274534Dh; Tag
0x140046a78  mov     rdx, rbx; NumberOfBytes
0x140046a7b  call    cs:__imp_ExAllocatePoolWithTag
0x140046a82  nop     dword ptr [rax+rax+00h]
0x140046a87  mov     rsi, rax
0x140046a8a  test    rax, rax
0x140046a8d  jz      short loc_140046A9C
0x140046a8f  mov     r8, rbx; Size
0x140046a92  xor     edx, edx; Val
0x140046a94  mov     rcx, rax; void *
0x140046a97  call    memset
0x140046a9c  mov     [rsp+78h+var_40], rsi
0x140046aa1  test    rsi, rsi
0x140046aa4  jz      short loc_140046ADE
0x140046aa6  mov     r8, rbx
0x140046aa9  cmp     r13, rbx
0x140046aac  cmovb   r8, r13; Size
0x140046ab0  mov     rdx, [rsp+78h+Src]; Src
0x140046ab8  mov     rcx, rsi; void *
0x140046abb  call    memmove
0x140046ac0  mov     edx, 7274534Dh; Tag
0x140046ac5  mov     rcx, [rsp+78h+Src]; P
0x140046acd  call    cs:__imp_ExFreePoolWithTag
0x140046ad4  nop     dword ptr [rax+rax+00h]
0x140046ad9  test    rsi, rsi
0x140046adc  jnz     short loc_140046AEA
0x140046ade  mov     ebx, 0C0000017h
0x140046ae3  mov     esi, 1
0x140046ae8  jmp     short loc_140046B46
0x140046aea  mov     [rdi+28h], rsi
0x140046aee  mov     [rdi+10h], rbx
0x140046af2  lea     rax, [rdi+20h]
0x140046af6  mov     esi, 1
0x140046afb  jmp     short loc_140046B00
0x140046afd  mov     rax, r15
0x140046b00  mov     rcx, [rdi+28h]
0x140046b04  mov     rax, [rax]
0x140046b07  mov     dword ptr [rcx+rax], 0
0x140046b0e  mov     rax, [r15]
0x140046b11  lea     rcx, [rax+4]
0x140046b15  cmp     rcx, rax
0x140046b18  jb      short loc_140046B1E
0x140046b1a  xor     eax, eax
0x140046b1c  jmp     short loc_140046B27
0x140046b1e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140046b22  mov     eax, 80070216h
0x140046b27  mov     [r15], rcx
0x140046b2a  test    eax, eax
0x140046b2c  jns     short loc_140046B35
0x140046b2e  mov     ebx, 0C0000095h
0x140046b33  jmp     short loc_140046B46
0x140046b35  mov     rax, [rdi+8]
0x140046b39  cmp     rax, rcx
0x140046b3c  cmovbe  rax, rcx
0x140046b40  mov     [rdi+8], rax
0x140046b44  xor     ebx, ebx
0x140046b46  mov     [rsp+78h+var_48], ebx
0x140046b4a  test    ebx, ebx
0x140046b4c  jns     short loc_140046B64
0x140046b4e  mov     [rsp+78h+var_58], ebx
0x140046b52  lea     r9, aFailedToWriteD; "Failed to write double null [%x]"
0x140046b59  mov     r8d, 4A0h
0x140046b5f  jmp     loc_1400469A6
0x140046b64  mov     qword ptr [r15], 0
0x140046b6b  jmp     short loc_140046BA2
0x140046b6d  mov     ebx, eax
0x140046b6f  mov     [rsp+78h+var_48], eax
0x140046b73  mov     [rsp+78h+var_58], eax
0x140046b77  lea     r9, aExceptionReadi_0; "Exception reading environment [%x]"
0x140046b7e  mov     r8d, 4A8h
0x140046b84  lea     rdx, aAhcprobeandrea; "AhcProbeAndReadEnvironment"
0x140046b8b  mov     ecx, 1
0x140046b90  call    AslLogCallPrintf
0x140046b95  mov     r12, [rsp+78h+arg_0]
0x140046b9d  mov     r14, [rsp+78h+var_38]
0x140046ba2  test    r14, r14
0x140046ba5  jz      short loc_140046BB4
0x140046ba7  cmp     r14, r12
0x140046baa  jz      short loc_140046BB4
0x140046bac  mov     rdx, r14
0x140046baf  call    AslFree
0x140046bb4  mov     eax, ebx
0x140046bb6  lea     r11, [rsp+78h+var_28]
0x140046bbb  mov     rbx, [r11+38h]
0x140046bbf  mov     rsi, [r11+40h]
0x140046bc3  mov     rsp, r11
0x140046bc6  pop     r15
0x140046bc8  pop     r14
0x140046bca  pop     r13
0x140046bcc  pop     r12
0x140046bce  pop     rdi
0x140046bcf  retn
```
