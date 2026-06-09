# MpFsCtlSetDynamicFsHardeningItems

- ea: `0x140081808`
- end: `0x140081929`
- name: `MpFsCtlSetDynamicFsHardeningItems`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400448f0`

## callees

- `0x1400018a4`
- `0x1400026c0`
- `0x1400078a4`
- `0x140072464`
- `0x140081808`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140081835`
- `ntoskrnl!ProbeForRead` at `0x14008185c`
- `ntoskrnl!ProbeForRead` at `0x140081835`
- `ntoskrnl!ProbeForRead` at `0x14008185c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081904`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081904`

## pseudocode

```c
__int64 __fastcall MpFsCtlSetDynamicFsHardeningItems(__int64 a1)
{
  void *v2; // rbx
  unsigned int *v3; // rsi
  unsigned int v4; // r14d
  unsigned int *v5; // rsi
  rsize_t v6; // rdi
  void *PoolWithTag; // rax
  unsigned int v9; // edi

  v2 = 0;
  ProbeForRead(*(volatile void **)(*(_QWORD *)(a1 + 16) + 48LL), 0x10u, 4u);
  v3 = *(unsigned int **)(*(_QWORD *)(a1 + 16) + 48LL);
  v4 = v3[1];
  ProbeForRead(v3, v3[2], 4u);
  if ( v3[2] > 0xC )
  {
    v5 = v3 + 3;
    v6 = *v5;
    PoolWithTag = (void *)MpAllocatePoolWithTag(1, v6, 1768443981);
    v2 = PoolWithTag;
    if ( !PoolWithTag )
      return 3221225495LL;
    memcpy_s(PoolWithTag, v6, v5, v6);
  }
  v9 = MpFsHardeningSetServiceHardeningItems(v2, v4);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x6968504Du);
  return v9;
}

```

## disassembly

```asm
0x140081808  mov     rax, rsp
0x14008180b  mov     [rax+8], rbx
0x14008180f  mov     [rax+10h], rsi
0x140081813  mov     [rax+18h], rdi
0x140081817  push    r14
0x140081819  sub     rsp, 30h
0x14008181d  mov     rdi, rcx
0x140081820  xor     ebx, ebx
0x140081822  mov     [rax-10h], rbx
0x140081826  mov     rcx, [rcx+10h]
0x14008182a  lea     edx, [rbx+10h]; Length
0x14008182d  lea     r8d, [rbx+4]; Alignment
0x140081831  mov     rcx, [rcx+30h]; Address
0x140081835  call    cs:__imp_ProbeForRead
0x14008183c  nop     dword ptr [rax+rax+00h]
0x140081841  mov     rax, [rdi+10h]
0x140081845  mov     rsi, [rax+30h]
0x140081849  mov     r14d, [rsi+4]
0x14008184d  mov     [rsp+38h+var_18], r14d
0x140081852  mov     edx, [rsi+8]; Length
0x140081855  lea     r8d, [rbx+4]; Alignment
0x140081859  mov     rcx, rsi; Address
0x14008185c  call    cs:__imp_ProbeForRead
0x140081863  nop     dword ptr [rax+rax+00h]
0x140081868  cmp     dword ptr [rsi+8], 0Ch
0x14008186c  jbe     short loc_1400818AF
0x14008186e  add     rsi, 0Ch
0x140081872  mov     [rsp+38h+var_10], rsi
0x140081877  mov     edi, [rsi]
0x140081879  mov     r8d, 6968504Dh
0x14008187f  mov     edx, edi
0x140081881  lea     ecx, [rbx+1]
0x140081884  call    MpAllocatePoolWithTag
0x140081889  mov     rbx, rax
0x14008188c  mov     [rsp+38h+var_10], rax
0x140081891  test    rax, rax
0x140081894  jnz     short loc_14008189D
0x140081896  mov     eax, 0C0000017h
0x14008189b  jmp     short loc_140081912
0x14008189d  mov     r9, rdi; MaxCount
0x1400818a0  mov     r8, rsi; Src
0x1400818a3  mov     rdx, rdi; DstSize
0x1400818a6  mov     rcx, rax; void *
0x1400818a9  call    memcpy_s
0x1400818ae  nop
0x1400818af  mov     edx, r14d
0x1400818b2  mov     rcx, rbx
0x1400818b5  call    MpFsHardeningSetServiceHardeningItems
0x1400818ba  mov     edi, eax
0x1400818bc  jmp     short loc_1400818F7
0x1400818be  mov     edi, eax
0x1400818c0  lea     rax, WPP_GLOBAL_Control
0x1400818c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400818ce  cmp     rcx, rax
0x1400818d1  jz      short loc_1400818F2
0x1400818d3  mov     eax, [rcx+2Ch]
0x1400818d6  test    al, 1
0x1400818d8  jz      short loc_1400818F2
0x1400818da  mov     edx, 21h ; '!'
0x1400818df  mov     r9d, edi
0x1400818e2  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x1400818e9  mov     rcx, [rcx+18h]
0x1400818ed  call    WPP_SF_d
0x1400818f2  mov     rbx, [rsp+38h+var_10]
0x1400818f7  test    rbx, rbx
0x1400818fa  jz      short loc_140081910
0x1400818fc  mov     edx, 6968504Dh; Tag
0x140081901  mov     rcx, rbx; P
0x140081904  call    cs:__imp_ExFreePoolWithTag
0x14008190b  nop     dword ptr [rax+rax+00h]
0x140081910  mov     eax, edi
0x140081912  mov     rbx, [rsp+38h+arg_0]
0x140081917  mov     rsi, [rsp+38h+arg_8]
0x14008191c  mov     rdi, [rsp+38h+arg_10]
0x140081921  add     rsp, 30h
0x140081925  pop     r14
0x140081927  retn
```
