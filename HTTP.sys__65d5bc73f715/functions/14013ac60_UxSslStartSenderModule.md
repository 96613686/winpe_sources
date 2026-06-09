# UxSslStartSenderModule

- ea: `0x14013ac60`
- end: `0x14013ae2c`
- name: `UxSslStartSenderModule`
- size: `460`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x14013ac60`
- `0x1401c3f58`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14013ad2e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14013adca`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14013ad2e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14013adca`
- `ntoskrnl!MmSizeOfMdl` at `0x14013ac98`
- `ntoskrnl!MmSizeOfMdl` at `0x14013ad40`
- `ntoskrnl!MmSizeOfMdl` at `0x14013ac98`
- `ntoskrnl!MmSizeOfMdl` at `0x14013ad40`
- `ntoskrnl!ExAllocatePool3` at `0x14013acc6`
- `ntoskrnl!ExAllocatePool3` at `0x14013ad69`
- `ntoskrnl!ExAllocatePool3` at `0x14013acc6`
- `ntoskrnl!ExAllocatePool3` at `0x14013ad69`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013adeb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013adeb`

## pseudocode

```c
__int64 UxSslStartSenderModule()
{
  unsigned int v0; // ebx
  struct _MDL *Pool3; // rax
  struct _MDL *v2; // rsi
  unsigned __int64 v3; // rcx
  unsigned int v4; // ebp
  struct _MDL *v5; // rax
  struct _MDL *v6; // rdi
  unsigned int v7; // ebx
  unsigned __int64 v8; // rdx

  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1041, 10, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids);
  v0 = (MmSizeOfMdl((PVOID)0xFFF, 2u) + 7) & 0xFFFFFFF8;
  Pool3 = (struct _MDL *)ExAllocatePool3(66, v0 + 2, 1129543765, UxLowPriorityPool, 1);
  v2 = Pool3;
  if ( Pool3 )
  {
    v3 = (unsigned __int64)Pool3 + v0;
    *(_WORD *)v3 = 1;
    Pool3->Next = 0;
    Pool3->ByteCount = 2;
    Pool3->Size = 8 * (((unsigned __int16)((((_WORD)Pool3 + v0) & 0xFFF) + 4097) >> 12) + 6);
    Pool3->MdlFlags = 0;
    Pool3->ByteOffset = v3 & 0xFFF;
    Pool3->StartVa = (PVOID)(v3 & 0xFFFFFFFFFFFFF000uLL);
    MmBuildMdlForNonPagedPool(Pool3);
    v4 = (MmSizeOfMdl((PVOID)0xFFF, 4u) + 7) & 0xFFFFFFF8;
    v5 = (struct _MDL *)ExAllocatePool3(66, v4 + 4, 1213429845, UxLowPriorityPool, 1);
    v6 = v5;
    if ( v5 )
    {
      v7 = 0;
      v8 = (unsigned __int64)v5 + v4;
      *(_DWORD *)v8 = 0;
      v5->Next = 0;
      v5->ByteCount = 4;
      v5->MdlFlags = 0;
      v5->Size = 8 * (((unsigned __int16)((((_WORD)v5 + v4) & 0xFFF) + 4099) >> 12) + 6);
      v5->StartVa = (PVOID)(v8 & 0xFFFFFFFFFFFFF000uLL);
      v5->ByteOffset = v8 & 0xFFF;
      MmBuildMdlForNonPagedPool(v5);
      UxSslCloseNotifyMdl = v2;
      UxSslHelloRequestMdl = v6;
      goto LABEL_8;
    }
    ExFreePoolWithTag(v2, 0);
  }
  v7 = -1073741670;
LABEL_8:
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1041, 11, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x14013ac60  push    rbx
0x14013ac62  push    rbp
0x14013ac63  push    rsi
0x14013ac64  push    rdi
0x14013ac65  push    r13
0x14013ac67  sub     rsp, 30h
0x14013ac6b  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14013ac72  jz      short loc_14013AC8A
0x14013ac74  mov     edx, 0Ah
0x14013ac79  lea     r8, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids
0x14013ac80  mov     ecx, 411h
0x14013ac85  call    WPP_SF_
0x14013ac8a  mov     r13d, 0FFFh
0x14013ac90  mov     edx, 2; Length
0x14013ac95  mov     ecx, r13d; Base
0x14013ac98  call    cs:__imp_MmSizeOfMdl
0x14013ac9f  nop     dword ptr [rax+rax+00h]
0x14013aca4  mov     edi, 1
0x14013aca9  lea     r9, UxLowPriorityPool
0x14013acb0  mov     r8d, 43537855h
0x14013acb6  mov     [rsp+58h+var_38], edi
0x14013acba  lea     ebx, [rax+7]
0x14013acbd  and     ebx, 0FFFFFFF8h
0x14013acc0  lea     ecx, [rdi+41h]
0x14013acc3  lea     edx, [rbx+2]
0x14013acc6  call    cs:__imp_ExAllocatePool3
0x14013accd  nop     dword ptr [rax+rax+00h]
0x14013acd2  mov     rsi, rax
0x14013acd5  test    rax, rax
0x14013acd8  jz      loc_14013ADF7
0x14013acde  lea     edx, [r13+2]
0x14013ace2  mov     ecx, ebx
0x14013ace4  add     rcx, rax
0x14013ace7  mov     [rcx], di
0x14013acea  mov     qword ptr [rax], 0
0x14013acf1  movzx   eax, cx
0x14013acf4  and     ax, r13w
0x14013acf8  mov     dword ptr [rsi+28h], 2
0x14013acff  add     ax, dx
0x14013ad02  shr     ax, 0Ch
0x14013ad06  add     ax, 6
0x14013ad0a  shl     ax, 3
0x14013ad0e  mov     [rsi+8], ax
0x14013ad12  xor     eax, eax
0x14013ad14  mov     [rsi+0Ah], ax
0x14013ad18  mov     rax, rcx
0x14013ad1b  and     ecx, r13d
0x14013ad1e  and     rax, 0FFFFFFFFFFFFF000h
0x14013ad24  mov     [rsi+2Ch], ecx
0x14013ad27  mov     rcx, rsi; MemoryDescriptorList
0x14013ad2a  mov     [rsi+20h], rax
0x14013ad2e  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14013ad35  nop     dword ptr [rax+rax+00h]
0x14013ad3a  lea     edx, [rdi+3]; Length
0x14013ad3d  mov     ecx, r13d; Base
0x14013ad40  call    cs:__imp_MmSizeOfMdl
0x14013ad47  nop     dword ptr [rax+rax+00h]
0x14013ad4c  lea     r9, UxLowPriorityPool
0x14013ad53  mov     [rsp+58h+var_38], edi
0x14013ad57  lea     ecx, [rdi+41h]
0x14013ad5a  mov     r8d, 48537855h
0x14013ad60  lea     ebp, [rax+7]
0x14013ad63  and     ebp, 0FFFFFFF8h
0x14013ad66  lea     edx, [rbp+4]
0x14013ad69  call    cs:__imp_ExAllocatePool3
0x14013ad70  nop     dword ptr [rax+rax+00h]
0x14013ad75  mov     rdi, rax
0x14013ad78  test    rax, rax
0x14013ad7b  jz      short loc_14013ADE6
0x14013ad7d  xor     ebx, ebx
0x14013ad7f  mov     edx, ebp
0x14013ad81  add     rdx, rax
0x14013ad84  movzx   ecx, dx
0x14013ad87  and     cx, r13w
0x14013ad8b  mov     [rdx], ebx
0x14013ad8d  mov     [rax], rbx
0x14013ad90  lea     eax, [r13+4]
0x14013ad94  add     cx, ax
0x14013ad97  mov     dword ptr [rdi+28h], 4
0x14013ad9e  shr     cx, 0Ch
0x14013ada2  xor     eax, eax
0x14013ada4  add     cx, 6
0x14013ada8  mov     [rdi+0Ah], ax
0x14013adac  shl     cx, 3
0x14013adb0  mov     rax, rdx
0x14013adb3  mov     [rdi+8], cx
0x14013adb7  and     rax, 0FFFFFFFFFFFFF000h
0x14013adbd  and     edx, r13d
0x14013adc0  mov     [rdi+20h], rax
0x14013adc4  mov     rcx, rdi; MemoryDescriptorList
0x14013adc7  mov     [rdi+2Ch], edx
0x14013adca  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14013add1  nop     dword ptr [rax+rax+00h]
0x14013add6  mov     cs:UxSslCloseNotifyMdl, rsi
0x14013addd  mov     cs:UxSslHelloRequestMdl, rdi
0x14013ade4  jmp     short loc_14013ADFC
0x14013ade6  xor     edx, edx; Tag
0x14013ade8  mov     rcx, rsi; P
0x14013adeb  call    cs:__imp_ExFreePoolWithTag
0x14013adf2  nop     dword ptr [rax+rax+00h]
0x14013adf7  mov     ebx, 0C000009Ah
0x14013adfc  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14013ae03  jz      short loc_14013AE1E
0x14013ae05  mov     edx, 0Bh
0x14013ae0a  lea     r8, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids
0x14013ae11  mov     ecx, 411h
0x14013ae16  mov     r9d, ebx
0x14013ae19  call    WPP_SF_d
0x14013ae1e  mov     eax, ebx
0x14013ae20  add     rsp, 30h
0x14013ae24  pop     r13
0x14013ae26  pop     rdi
0x14013ae27  pop     rsi
0x14013ae28  pop     rbp
0x14013ae29  pop     rbx
0x14013ae2a  retn
```
