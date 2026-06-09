# BfsGetPolicy

- ea: `0x140006e14`
- end: `0x14000703d`
- name: `BfsGetPolicy`
- size: `553`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400055d8`
- `0x140005d4c`
- `0x140009b9c`

## callees

- `0x1400034e4`
- `0x140006e14`
- `0x14001079c`
- `0x14001126c`
- `0x1400116a0`
- `0x140011a38`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140006eb0`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140006f9d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140006eb0`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140006f9d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140006ed0`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140006fbd`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140006ed0`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140006fbd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006e9f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006f88`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006e9f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006f88`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006edc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006fc9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006edc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006fc9`

## pseudocode

```c
__int64 __fastcall BfsGetPolicy(__int64 a1, const UNICODE_STRING *a2, __int128 *a3, _BYTE *a4)
{
  __int128 v4; // xmm1
  PVOID *v9; // rsi
  unsigned int v10; // edi
  unsigned int v11; // ebx
  __int64 Entry; // r14
  int v13; // eax
  int v14; // eax
  volatile signed __int32 *v15; // rcx
  unsigned int v16; // r14d
  int v17; // edi
  __int128 v18; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING v19; // [rsp+30h] [rbp-28h] BYREF
  __int16 v20[12]; // [rsp+40h] [rbp-18h] BYREF
  PVOID *v21; // [rsp+A0h] [rbp+48h] BYREF

  v4 = *a3;
  v21 = 0;
  v18 = v4;
  v19 = 0;
  if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline() )
    *a4 = 0;
  if ( (int)BfsCreateDirectory(a1 + 48, a2, 1, &v21) < 0 )
    return 0;
  v9 = v21;
  v10 = 0;
  v11 = 0;
  v18 = *(_OWORD *)BfsGetPathComponent(v20, &v18, (__int64)&v19);
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(v9, 0);
  Entry = BfsFindEntry(v9, &v19);
  ExReleasePushLockSharedEx(v9, 0);
  KeLeaveCriticalRegion();
  while ( Entry )
  {
    v13 = v10 | *(_DWORD *)(Entry + 8);
    v10 = *(_DWORD *)(Entry + 8) & 0xFFFFFFFE;
    if ( (*(_DWORD *)(Entry + 8) & 1) == 0 )
      v10 = v13;
    if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( (v10 & 2) != 0 && v11 && v11 != 3 )
      {
        if ( v11 == 1 || v11 == 2 && *(_DWORD *)(Entry + 4) == 1 )
          v11 = 1;
      }
      else
      {
        v11 = *(_DWORD *)(Entry + 4);
      }
    }
    else
    {
      v11 = *(_DWORD *)(Entry + 4);
    }
    if ( (unsigned __int16)v18 < 2u )
      goto LABEL_34;
    v14 = BfsCreateDirectory((__int64)v9, &v19, 1, &v21);
    v15 = (volatile signed __int32 *)(v9 - 1);
    v16 = v14;
    if ( v14 < 0 )
    {
      BfsDereferenceTableEntry(v15);
      return v16;
    }
    BfsDereferenceTableEntry(v15);
    v18 = *(_OWORD *)BfsGetPathComponent(v20, &v18, (__int64)&v19);
    KeEnterCriticalRegion();
    v9 = v21;
    ExAcquirePushLockSharedEx(v21, 0);
    Entry = BfsFindEntry(v9, &v19);
    ExReleasePushLockSharedEx(v9, 0);
    KeLeaveCriticalRegion();
  }
  if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    v17 = v10 & 2;
    if ( (unsigned __int16)v18 < 2u || v17 )
    {
      if ( v11 - 1 <= 1 && v17 )
        *a4 = 1;
      goto LABEL_34;
    }
  }
  else if ( (unsigned __int16)v18 < 2u || (v10 & 2) != 0 )
  {
    goto LABEL_34;
  }
  v11 = 0;
LABEL_34:
  BfsDereferenceTableEntry((volatile signed __int32 *)v9 - 2);
  return v11;
}

```

## disassembly

```asm
0x140006e14  push    rbp
0x140006e16  push    rbx
0x140006e17  push    rsi
0x140006e18  push    rdi
0x140006e19  push    r12
0x140006e1b  push    r13
0x140006e1d  push    r14
0x140006e1f  push    r15
0x140006e21  mov     rbp, rsp
0x140006e24  sub     rsp, 58h
0x140006e28  movups  xmm1, xmmword ptr [r8]
0x140006e2c  mov     [rbp+arg_0], 0
0x140006e34  mov     r15, r9
0x140006e37  xorps   xmm0, xmm0
0x140006e3a  mov     rbx, rdx
0x140006e3d  movdqu  [rbp+var_38], xmm1
0x140006e42  mov     rdi, rcx
0x140006e45  movups  [rbp+var_28], xmm0
0x140006e49  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x140006e4e  test    eax, eax
0x140006e50  jz      short loc_140006E56
0x140006e52  mov     byte ptr [r15], 0
0x140006e56  mov     r12d, 1
0x140006e5c  lea     rcx, [rdi+30h]
0x140006e60  mov     r8d, r12d
0x140006e63  lea     r9, [rbp+arg_0]
0x140006e67  mov     rdx, rbx
0x140006e6a  call    BfsCreateDirectory
0x140006e6f  test    eax, eax
0x140006e71  jns     short loc_140006E7A
0x140006e73  xor     eax, eax
0x140006e75  jmp     loc_14000702B
0x140006e7a  mov     rsi, [rbp+arg_0]
0x140006e7e  lea     r8, [rbp+var_28]
0x140006e82  lea     rdx, [rbp+var_38]
0x140006e86  mov     [rbp+arg_0], rsi
0x140006e8a  lea     rcx, [rbp+var_18]
0x140006e8e  xor     edi, edi
0x140006e90  xor     ebx, ebx
0x140006e92  call    BfsGetPathComponent
0x140006e97  movups  xmm1, xmmword ptr [rax]
0x140006e9a  movdqu  [rbp+var_38], xmm1
0x140006e9f  call    cs:__imp_KeEnterCriticalRegion
0x140006ea6  nop     dword ptr [rax+rax+00h]
0x140006eab  xor     edx, edx
0x140006ead  mov     rcx, rsi
0x140006eb0  call    cs:__imp_ExAcquirePushLockSharedEx
0x140006eb7  nop     dword ptr [rax+rax+00h]
0x140006ebc  lea     rdx, [rbp+var_28]
0x140006ec0  mov     rcx, rsi
0x140006ec3  call    BfsFindEntry
0x140006ec8  xor     edx, edx
0x140006eca  mov     rcx, rsi
0x140006ecd  mov     r14, rax
0x140006ed0  call    cs:__imp_ExReleasePushLockSharedEx
0x140006ed7  nop     dword ptr [rax+rax+00h]
0x140006edc  call    cs:__imp_KeLeaveCriticalRegion
0x140006ee3  nop     dword ptr [rax+rax+00h]
0x140006ee8  lea     r13d, [rdi+2]
0x140006eec  jmp     loc_140006FD5
0x140006ef1  mov     ecx, [r14+8]
0x140006ef5  mov     eax, ecx
0x140006ef7  or      eax, edi
0x140006ef9  mov     edi, ecx
0x140006efb  and     edi, 0FFFFFFFEh
0x140006efe  test    r12b, cl
0x140006f01  cmovz   edi, eax
0x140006f04  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x140006f09  test    eax, eax
0x140006f0b  jnz     short loc_140006F13
0x140006f0d  mov     ebx, [r14+4]
0x140006f11  jmp     short loc_140006F3D
0x140006f13  mov     eax, [r14+4]
0x140006f17  test    r13b, dil
0x140006f1a  jz      short loc_140006F3B
0x140006f1c  test    ebx, ebx
0x140006f1e  jz      short loc_140006F3B
0x140006f20  cmp     ebx, 3
0x140006f23  jz      short loc_140006F3B
0x140006f25  cmp     ebx, r12d
0x140006f28  jnz     short loc_140006F2F
0x140006f2a  mov     ebx, r12d
0x140006f2d  jmp     short loc_140006F3D
0x140006f2f  cmp     ebx, r13d
0x140006f32  jnz     short loc_140006F3D
0x140006f34  cmp     eax, r12d
0x140006f37  jnz     short loc_140006F3D
0x140006f39  jmp     short loc_140006F2A
0x140006f3b  mov     ebx, eax
0x140006f3d  cmp     word ptr [rbp+var_38], r13w
0x140006f42  jb      loc_140007020
0x140006f48  lea     r9, [rbp+arg_0]
0x140006f4c  mov     r8d, r12d
0x140006f4f  lea     rdx, [rbp+var_28]
0x140006f53  mov     rcx, rsi
0x140006f56  call    BfsCreateDirectory
0x140006f5b  lea     rcx, [rsi-8]; Buffer
0x140006f5f  mov     r14d, eax
0x140006f62  test    eax, eax
0x140006f64  js      loc_140006FF5
0x140006f6a  call    BfsDereferenceTableEntry
0x140006f6f  lea     r8, [rbp+var_28]
0x140006f73  lea     rdx, [rbp+var_38]
0x140006f77  lea     rcx, [rbp+var_18]
0x140006f7b  call    BfsGetPathComponent
0x140006f80  movups  xmm1, xmmword ptr [rax]
0x140006f83  movdqu  [rbp+var_38], xmm1
0x140006f88  call    cs:__imp_KeEnterCriticalRegion
0x140006f8f  nop     dword ptr [rax+rax+00h]
0x140006f94  mov     rsi, [rbp+arg_0]
0x140006f98  xor     edx, edx
0x140006f9a  mov     rcx, rsi
0x140006f9d  call    cs:__imp_ExAcquirePushLockSharedEx
0x140006fa4  nop     dword ptr [rax+rax+00h]
0x140006fa9  lea     rdx, [rbp+var_28]
0x140006fad  mov     rcx, rsi
0x140006fb0  call    BfsFindEntry
0x140006fb5  xor     edx, edx
0x140006fb7  mov     rcx, rsi
0x140006fba  mov     r14, rax
0x140006fbd  call    cs:__imp_ExReleasePushLockSharedEx
0x140006fc4  nop     dword ptr [rax+rax+00h]
0x140006fc9  call    cs:__imp_KeLeaveCriticalRegion
0x140006fd0  nop     dword ptr [rax+rax+00h]
0x140006fd5  test    r14, r14
0x140006fd8  jnz     loc_140006EF1
0x140006fde  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x140006fe3  test    eax, eax
0x140006fe5  jnz     short loc_140006FFF
0x140006fe7  cmp     word ptr [rbp+var_38], r13w
0x140006fec  jb      short loc_140007020
0x140006fee  test    r13b, dil
0x140006ff1  jnz     short loc_140007020
0x140006ff3  jmp     short loc_14000700D
0x140006ff5  call    BfsDereferenceTableEntry
0x140006ffa  mov     eax, r14d
0x140006ffd  jmp     short loc_14000702B
0x140006fff  and     edi, r13d
0x140007002  cmp     word ptr [rbp+var_38], r13w
0x140007007  jb      short loc_140007011
0x140007009  test    edi, edi
0x14000700b  jnz     short loc_140007011
0x14000700d  xor     ebx, ebx
0x14000700f  jmp     short loc_140007020
0x140007011  lea     eax, [rbx-1]
0x140007014  cmp     eax, r12d
0x140007017  ja      short loc_140007020
0x140007019  test    edi, edi
0x14000701b  jz      short loc_140007020
0x14000701d  mov     [r15], r12b
0x140007020  lea     rcx, [rsi-8]; Buffer
0x140007024  call    BfsDereferenceTableEntry
0x140007029  mov     eax, ebx
0x14000702b  add     rsp, 58h
0x14000702f  pop     r15
0x140007031  pop     r14
0x140007033  pop     r13
0x140007035  pop     r12
0x140007037  pop     rdi
0x140007038  pop     rsi
0x140007039  pop     rbx
0x14000703a  pop     rbp
0x14000703b  retn
```
