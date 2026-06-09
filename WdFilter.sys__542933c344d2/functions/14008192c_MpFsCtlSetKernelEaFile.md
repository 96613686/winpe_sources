# MpFsCtlSetKernelEaFile

- ea: `0x14008192c`
- end: `0x140081bd0`
- name: `MpFsCtlSetKernelEaFile`
- size: `676`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1400448f0`

## callees

- `0x1400018a4`
- `0x1400026c0`
- `0x1400049dc`
- `0x140006110`
- `0x140011900`
- `0x1400743b4`
- `0x14008192c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14008195e`
- `ntoskrnl!ProbeForRead` at `0x140081a01`
- `ntoskrnl!ProbeForRead` at `0x14008195e`
- `ntoskrnl!ProbeForRead` at `0x140081a01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081b66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081b66`

## pseudocode

```c
__int64 __fastcall MpFsCtlSetKernelEaFile(__int64 a1, __int64 a2)
{
  unsigned int *PoolWithTag; // rax
  unsigned int *v5; // rsi
  __int64 v7; // r9
  __int64 v8; // r8
  unsigned int v9; // ebx
  unsigned int *v10; // r10
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // r11
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  SIZE_T Length[2]; // [rsp+38h] [rbp-20h]

  ProbeForRead(*(volatile void **)(*(_QWORD *)(a1 + 16) + 48LL), 0x18u, 4u);
  *(_OWORD *)Length = *(_OWORD *)*(_QWORD *)(*(_QWORD *)(a1 + 16) + 48LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_ZDD(
      WPP_GLOBAL_Control->AttachedDevice,
      37,
      (unsigned int)WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
      *(_QWORD *)(a2 + 32) + 88,
      SBYTE4(Length[0]),
      Length[1]);
  if ( HIDWORD(Length[0]) > 0x20000 || (unsigned int)(LODWORD(Length[1]) + 12) > HIDWORD(Length[0]) )
    return 3221225485LL;
  ProbeForRead(*(volatile void **)(*(_QWORD *)(a1 + 16) + 48LL), HIDWORD(Length[0]), 4u);
  PoolWithTag = (unsigned int *)MpAllocatePoolWithTag(1, HIDWORD(Length[0]), 1634029645);
  v5 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225495LL;
  memmove(PoolWithTag, *(const void **)(*(_QWORD *)(a1 + 16) + 48LL), HIDWORD(Length[0]));
  v8 = v5[2];
  if ( (int)v8 + 12 <= v5[1] )
  {
    v10 = v5 + 3;
    while ( 1 )
    {
      v11 = *v10;
      v12 = *((unsigned __int16 *)v10 + 3);
      v13 = *((unsigned __int8 *)v10 + 5);
      if ( !(_DWORD)v11 )
        break;
      if ( (unsigned int)v11 < (int)v13 + (int)v12 + 9 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v15 = 39;
          goto LABEL_20;
        }
        goto LABEL_9;
      }
      v10 = (unsigned int *)((char *)v10 + v11);
      if ( v10 >= (unsigned int *)((char *)v5 + v8 + 12) )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v15 = 40;
LABEL_20:
          WPP_SF_(v14->AttachedDevice, v15, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids);
          goto LABEL_9;
        }
        goto LABEL_9;
      }
    }
    if ( (char *)v10 + v12 + v13 + 9 <= (char *)v5 + v8 + 12 )
    {
      _mm_lfence();
      LOBYTE(v7) = 1;
      v16 = MpSetFileKernelEa(*(_QWORD *)(a2 + 32), v10, v8, v7);
      v9 = v16;
      if ( v16 >= 0 )
      {
        v9 = 0;
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          42,
          WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
          (unsigned int)v16);
      }
      goto LABEL_30;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v15 = 41;
      goto LABEL_20;
    }
  }
LABEL_9:
  v9 = -1073741811;
LABEL_30:
  ExFreePoolWithTag(v5, 0x6165504Du);
  return v9;
}

```

## disassembly

```asm
0x14008192c  mov     rax, rsp
0x14008192f  mov     [rax+8], rbx
0x140081933  mov     [rax+10h], rsi
0x140081937  mov     [rax+18h], r13
0x14008193b  mov     [rax+20h], r14
0x14008193f  push    r15
0x140081941  sub     rsp, 50h
0x140081945  mov     r15, rdx
0x140081948  mov     rbx, rcx
0x14008194b  mov     rcx, [rcx+10h]
0x14008194f  mov     esi, 4
0x140081954  mov     r8d, esi; Alignment
0x140081957  lea     edx, [rsi+14h]; Length
0x14008195a  mov     rcx, [rcx+30h]; Address
0x14008195e  call    cs:__imp_ProbeForRead
0x140081965  nop     dword ptr [rax+rax+00h]
0x14008196a  mov     rax, [rbx+10h]
0x14008196e  mov     rcx, [rax+30h]
0x140081972  movups  xmm0, xmmword ptr [rcx]
0x140081975  movups  xmmword ptr [rsp+58h+Length], xmm0
0x14008197a  movsd   xmm1, qword ptr [rcx+10h]
0x14008197f  movsd   [rsp+58h+var_10], xmm1
0x140081985  lea     r13, WPP_GLOBAL_Control
0x14008198c  mov     rcx, cs:WPP_GLOBAL_Control
0x140081993  cmp     rcx, r13
0x140081996  jz      short loc_1400819D1
0x140081998  mov     eax, [rcx+2Ch]
0x14008199b  test    sil, al
0x14008199e  jz      short loc_1400819D1
0x1400819a0  mov     r8, [rsp+58h+Length]
0x1400819a5  shr     r8, 20h
0x1400819a9  mov     r9, [r15+20h]
0x1400819ad  add     r9, 58h ; 'X'
0x1400819b1  lea     edx, [rsi+21h]
0x1400819b4  mov     eax, dword ptr [rsp+58h+Length+8]
0x1400819b8  mov     [rsp+58h+var_30], eax
0x1400819bc  mov     [rsp+58h+var_38], r8d
0x1400819c1  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x1400819c8  mov     rcx, [rcx+18h]
0x1400819cc  call    WPP_SF_ZDD
0x1400819d1  mov     ecx, dword ptr [rsp+58h+Length+4]
0x1400819d5  cmp     ecx, 20000h
0x1400819db  ja      loc_140081B76
0x1400819e1  mov     eax, dword ptr [rsp+58h+Length+8]
0x1400819e5  add     eax, 0Ch
0x1400819e8  cmp     eax, ecx
0x1400819ea  ja      loc_140081B76
0x1400819f0  mov     r14d, ecx
0x1400819f3  mov     rcx, [rbx+10h]
0x1400819f7  mov     r8d, esi; Alignment
0x1400819fa  mov     edx, r14d; Length
0x1400819fd  mov     rcx, [rcx+30h]; Address
0x140081a01  call    cs:__imp_ProbeForRead
0x140081a08  nop     dword ptr [rax+rax+00h]
0x140081a0d  mov     r8d, 6165504Dh
0x140081a13  mov     edx, r14d
0x140081a16  mov     ecx, 1
0x140081a1b  call    MpAllocatePoolWithTag
0x140081a20  mov     rsi, rax
0x140081a23  mov     [rsp+58h+var_28], rax
0x140081a28  test    rax, rax
0x140081a2b  jnz     short loc_140081A37
0x140081a2d  mov     eax, 0C0000017h
0x140081a32  jmp     loc_140081BB4
0x140081a37  mov     rdx, [rbx+10h]
0x140081a3b  mov     r8, r14; Size
0x140081a3e  mov     rdx, [rdx+30h]; Src
0x140081a42  mov     rcx, rsi; void *
0x140081a45  call    memmove
0x140081a4a  nop
0x140081a4b  mov     r8d, [rsi+8]
0x140081a4f  lea     eax, [r8+0Ch]
0x140081a53  cmp     eax, [rsi+4]
0x140081a56  jbe     short loc_140081A62
0x140081a58  mov     ebx, 0C000000Dh
0x140081a5d  jmp     loc_140081B5E
0x140081a62  lea     r10, [rsi+0Ch]
0x140081a66  mov     edx, [r10]
0x140081a69  movzx   eax, word ptr [r10+6]
0x140081a6e  movzx   r11d, byte ptr [r10+5]
0x140081a73  test    edx, edx
0x140081a75  jz      short loc_140081AD4
0x140081a77  lea     ecx, [rax+9]
0x140081a7a  add     ecx, r11d
0x140081a7d  cmp     edx, ecx
0x140081a7f  jb      short loc_140081AAA
0x140081a81  add     r10, rdx
0x140081a84  lea     rax, [rsi+0Ch]
0x140081a88  add     rax, r8
0x140081a8b  cmp     r10, rax
0x140081a8e  jb      short loc_140081A66
0x140081a90  mov     rcx, cs:WPP_GLOBAL_Control
0x140081a97  cmp     rcx, r13
0x140081a9a  jz      short loc_140081A58
0x140081a9c  mov     eax, [rcx+2Ch]
0x140081a9f  test    al, 1
0x140081aa1  jz      short loc_140081A58
0x140081aa3  mov     edx, 28h ; '('
0x140081aa8  jmp     short loc_140081AC2
0x140081aaa  mov     rcx, cs:WPP_GLOBAL_Control
0x140081ab1  cmp     rcx, r13
0x140081ab4  jz      short loc_140081A58
0x140081ab6  mov     eax, [rcx+2Ch]
0x140081ab9  test    al, 1
0x140081abb  jz      short loc_140081A58
0x140081abd  mov     edx, 27h ; '''
0x140081ac2  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x140081ac9  mov     rcx, [rcx+18h]
0x140081acd  call    WPP_SF_
0x140081ad2  jmp     short loc_140081A58
0x140081ad4  lea     rdx, [rax+9]
0x140081ad8  add     rdx, r10
0x140081adb  add     rdx, r11
0x140081ade  lea     rax, [rsi+0Ch]
0x140081ae2  add     rax, r8
0x140081ae5  cmp     rdx, rax
0x140081ae8  jbe     short loc_140081B0C
0x140081aea  mov     rcx, cs:WPP_GLOBAL_Control
0x140081af1  cmp     rcx, r13
0x140081af4  jz      loc_140081A58
0x140081afa  mov     eax, [rcx+2Ch]
0x140081afd  test    al, 1
0x140081aff  jz      loc_140081A58
0x140081b05  mov     edx, 29h ; ')'
0x140081b0a  jmp     short loc_140081AC2
0x140081b0c  lfence
0x140081b0f  mov     r9b, 1
0x140081b12  mov     rdx, r10
0x140081b15  mov     rcx, [r15+20h]
0x140081b19  call    MpSetFileKernelEa
0x140081b1e  mov     ebx, eax
0x140081b20  test    eax, eax
0x140081b22  jns     short loc_140081B5C
0x140081b24  mov     rcx, cs:WPP_GLOBAL_Control
0x140081b2b  cmp     rcx, r13
0x140081b2e  jz      short loc_140081B5E
0x140081b30  mov     ecx, [rcx+2Ch]
0x140081b33  test    cl, 1
0x140081b36  jz      short loc_140081B5E
0x140081b38  lfence
0x140081b3b  mov     edx, 2Ah ; '*'
0x140081b40  mov     r9d, eax
0x140081b43  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x140081b4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140081b51  mov     rcx, [rcx+18h]
0x140081b55  call    WPP_SF_d
0x140081b5a  jmp     short loc_140081B5E
0x140081b5c  xor     ebx, ebx
0x140081b5e  mov     edx, 6165504Dh; Tag
0x140081b63  mov     rcx, rsi; P
0x140081b66  call    cs:__imp_ExFreePoolWithTag
0x140081b6d  nop     dword ptr [rax+rax+00h]
0x140081b72  mov     eax, ebx
0x140081b74  jmp     short loc_140081BB4
0x140081b76  mov     eax, 0C000000Dh
0x140081b7b  jmp     short loc_140081BB4
0x140081b7d  mov     ebx, eax
0x140081b7f  lea     rax, WPP_GLOBAL_Control
0x140081b86  mov     rcx, cs:WPP_GLOBAL_Control
0x140081b8d  cmp     rcx, rax
0x140081b90  jz      short loc_140081BB2
0x140081b92  mov     edx, [rcx+2Ch]
0x140081b95  test    dl, 1
0x140081b98  jz      short loc_140081BB2
0x140081b9a  mov     edx, 26h ; '&'
0x140081b9f  mov     r9d, ebx
0x140081ba2  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x140081ba9  mov     rcx, [rcx+18h]
0x140081bad  call    WPP_SF_d
0x140081bb2  mov     eax, ebx
0x140081bb4  mov     rbx, [rsp+58h+arg_0]
0x140081bb9  mov     rsi, [rsp+58h+arg_8]
0x140081bbe  mov     r13, [rsp+58h+arg_10]
0x140081bc3  mov     r14, [rsp+58h+arg_18]
0x140081bc8  add     rsp, 50h
0x140081bcc  pop     r15
0x140081bce  retn
```
