# VsmmEpfSetup

- ea: `0x1400aa868`
- end: `0x1400aaab6`
- name: `VsmmEpfSetup`
- size: `590`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400aa698`
- `0x1400fd330`

## callees

- `0x140005a84`
- `0x1400254ec`
- `0x14002e270`
- `0x1400347a4`
- `0x140034b64`
- `0x1400aa868`
- `0x1400aaabc`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400aaa2a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400aaa2a`
- `ntoskrnl!ExAllocatePool2` at `0x1400aa968`
- `ntoskrnl!ExAllocatePool2` at `0x1400aa968`

## pseudocode

```c
__int64 __fastcall VsmmEpfSetup(
        unsigned __int64 a1,
        char a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned __int64 a6,
        unsigned __int64 *a7)
{
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // rsi
  int v10; // ebx
  unsigned int v11; // r14d
  int v12; // ebx
  __int64 Pool2; // rax
  __int64 v14; // rdi
  unsigned int v15; // edx
  __int64 v16; // rcx
  _QWORD *v17; // rcx
  __int64 i; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v20[8]; // [rsp+48h] [rbp-40h] BYREF

  v20[0] = 0;
  i = 0;
  v8 = a1;
  if ( a3 != 1 || a4 )
    return (unsigned int)-1073741811;
  v9 = a6;
  if ( a6 > 1 )
  {
    if ( !a2 )
    {
      v9 = 1;
      goto LABEL_7;
    }
    return (unsigned int)-1073741811;
  }
  if ( !a6 )
    return (unsigned int)-1073741811;
LABEL_7:
  if ( *(_QWORD *)(a1 + 10760) )
  {
    v10 = -1073741811;
  }
  else
  {
    v10 = VsmmGpaRangeLookupByGpn(a1, 0, a5, 24, 0, (__int64)v20, (__int64)&i);
    if ( v10 >= 0 )
    {
      a1 = *(_QWORD *)(i + 272) - v20[0] + 1LL;
      if ( a1 >= v9 )
      {
        v11 = 16 * *(_DWORD *)(v8 + 3200);
        v12 = (*(_BYTE *)(v8 + 24) & 0x20) != 0 ? 0xFF8 : 0;
        Pool2 = ExAllocatePool2(64, v11 * (v12 + 104) + 112, 1833788502);
        v14 = Pool2;
        if ( Pool2 )
        {
          *(_DWORD *)Pool2 = 1;
          v15 = 0;
          *(_DWORD *)(Pool2 + 4) = a4;
          *(_QWORD *)(Pool2 + 8) = ((v9 << 12) - 16) >> 3;
          *(_QWORD *)(Pool2 + 24) = v20[0];
          *(_QWORD *)(Pool2 + 32) = v9;
          *(_QWORD *)(Pool2 + 16) = i;
          for ( i = 0; v15 < v11; *(_QWORD *)(Pool2 + 40) = v17 )
          {
            v16 = v15 * (v12 + 104);
            ++v15;
            v17 = (_QWORD *)(Pool2 + v16 + 112);
            *v17 = *(_QWORD *)(Pool2 + 40);
          }
          v10 = VsmmLockGpaRange(
                  *(_QWORD *)(Pool2 + 16),
                  *(_QWORD *)(Pool2 + 24),
                  *(_QWORD *)(Pool2 + 32),
                  9,
                  Pool2 + 56);
          if ( v10 >= 0 )
          {
            if ( MmMapLockedPagesSpecifyCache((PMDL)(v14 + 56), 0, MmCached, 0, 0, 0x40000010u) )
            {
              VidObjectLockAcquireExclusive(v8 + 10472);
              if ( *(_QWORD *)(v8 + 10760) )
              {
                v10 = -1073741811;
              }
              else
              {
                v10 = 0;
                *(_QWORD *)(v8 + 10760) = v14;
                v14 = 0;
                *a7 = v9;
              }
              VidObjectLockRelease(v8 + 10472);
              if ( !v14 )
                goto LABEL_24;
            }
            else
            {
              v10 = -1073741670;
            }
          }
          VsmmEpfpContextFree(a1, v14);
        }
        else
        {
          v10 = -1073741670;
        }
      }
      else
      {
        v10 = -1073741637;
      }
    }
  }
LABEL_24:
  if ( i )
    VsmmGpaRangeRelease(a1, i, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400aa868  push    rbx
0x1400aa86a  push    rbp
0x1400aa86b  push    rsi
0x1400aa86c  push    rdi
0x1400aa86d  push    r14
0x1400aa86f  push    r15
0x1400aa871  sub     rsp, 58h
0x1400aa875  mov     [rsp+88h+var_40], 0
0x1400aa87e  mov     r15d, r9d
0x1400aa881  mov     [rsp+88h+var_48], 0
0x1400aa88a  mov     rbp, rcx
0x1400aa88d  cmp     r8d, 1
0x1400aa891  jnz     loc_1400AAAA1
0x1400aa897  test    r9d, r9d
0x1400aa89a  jnz     loc_1400AAAA1
0x1400aa8a0  mov     rsi, [rsp+88h+arg_28]
0x1400aa8a8  cmp     rsi, 1
0x1400aa8ac  jbe     short loc_1400AA8BB
0x1400aa8ae  test    dl, dl
0x1400aa8b0  jnz     loc_1400AAAA1
0x1400aa8b6  mov     esi, r8d
0x1400aa8b9  jmp     short loc_1400AA8C4
0x1400aa8bb  test    rsi, rsi
0x1400aa8be  jz      loc_1400AAAA1
0x1400aa8c4  mov     rax, [rcx+2A08h]
0x1400aa8cb  test    rax, rax
0x1400aa8ce  jz      short loc_1400AA8DA
0x1400aa8d0  mov     ebx, 0C000000Dh
0x1400aa8d5  jmp     loc_1400AAA8D
0x1400aa8da  mov     r8, [rsp+88h+arg_20]
0x1400aa8e2  lea     rax, [rsp+88h+var_48]
0x1400aa8e7  mov     [rsp+88h+var_58], rax
0x1400aa8ec  mov     r9d, 18h
0x1400aa8f2  lea     rax, [rsp+88h+var_40]
0x1400aa8f7  xor     edx, edx
0x1400aa8f9  mov     qword ptr [rsp+88h+Priority], rax
0x1400aa8fe  mov     qword ptr [rsp+88h+BugCheckOnFailure], 0
0x1400aa907  call    VsmmGpaRangeLookupByGpn
0x1400aa90c  mov     ebx, eax
0x1400aa90e  test    eax, eax
0x1400aa910  js      loc_1400AAA8D
0x1400aa916  mov     rax, [rsp+88h+var_48]
0x1400aa91b  mov     rcx, [rax+110h]
0x1400aa922  sub     rcx, [rsp+88h+var_40]
0x1400aa927  inc     rcx
0x1400aa92a  cmp     rcx, rsi
0x1400aa92d  jnb     short loc_1400AA939
0x1400aa92f  mov     ebx, 0C00000BBh
0x1400aa934  jmp     loc_1400AAA8D
0x1400aa939  mov     al, [rbp+18h]
0x1400aa93c  mov     ecx, 40h ; '@'
0x1400aa941  mov     r14d, [rbp+0C80h]
0x1400aa948  and     al, 20h
0x1400aa94a  neg     al
0x1400aa94c  mov     r8d, 6D4D6456h
0x1400aa952  sbb     ebx, ebx
0x1400aa954  shl     r14d, 4
0x1400aa958  and     ebx, 0FF8h
0x1400aa95e  lea     edx, [rbx+68h]
0x1400aa961  imul    edx, r14d
0x1400aa965  add     edx, 70h ; 'p'
0x1400aa968  call    cs:__imp_ExAllocatePool2
0x1400aa96f  nop     dword ptr [rax+rax+00h]
0x1400aa974  mov     rdi, rax
0x1400aa977  test    rax, rax
0x1400aa97a  jnz     short loc_1400AA986
0x1400aa97c  mov     ebx, 0C000009Ah
0x1400aa981  jmp     loc_1400AAA8D
0x1400aa986  mov     dword ptr [rax], 1
0x1400aa98c  xor     edx, edx
0x1400aa98e  mov     [rax+4], r15d
0x1400aa992  mov     rax, rsi
0x1400aa995  shl     rax, 0Ch
0x1400aa999  sub     rax, 10h
0x1400aa99d  shr     rax, 3
0x1400aa9a1  mov     [rdi+8], rax
0x1400aa9a5  mov     rax, [rsp+88h+var_40]
0x1400aa9aa  mov     [rdi+18h], rax
0x1400aa9ae  mov     [rdi+20h], rsi
0x1400aa9b2  mov     rax, [rsp+88h+var_48]
0x1400aa9b7  mov     [rdi+10h], rax
0x1400aa9bb  mov     [rsp+88h+var_48], 0
0x1400aa9c4  test    r14d, r14d
0x1400aa9c7  jz      short loc_1400AA9E8
0x1400aa9c9  mov     rax, [rdi+28h]
0x1400aa9cd  lea     ecx, [rbx+68h]
0x1400aa9d0  imul    ecx, edx
0x1400aa9d3  inc     edx
0x1400aa9d5  add     rcx, 70h ; 'p'
0x1400aa9d9  add     rcx, rdi
0x1400aa9dc  mov     [rcx], rax
0x1400aa9df  mov     [rdi+28h], rcx
0x1400aa9e3  cmp     edx, r14d
0x1400aa9e6  jb      short loc_1400AA9C9
0x1400aa9e8  mov     r8, [rdi+20h]
0x1400aa9ec  lea     r14, [rdi+38h]
0x1400aa9f0  mov     rdx, [rdi+18h]
0x1400aa9f4  mov     r9d, 9
0x1400aa9fa  mov     rcx, [rdi+10h]
0x1400aa9fe  mov     qword ptr [rsp+88h+BugCheckOnFailure], r14
0x1400aaa03  call    VsmmLockGpaRange
0x1400aaa08  mov     ebx, eax
0x1400aaa0a  test    eax, eax
0x1400aaa0c  js      short loc_1400AAA85
0x1400aaa0e  xor     r9d, r9d; RequestedAddress
0x1400aaa11  mov     [rsp+88h+Priority], 40000010h; Priority
0x1400aaa19  xor     edx, edx; AccessMode
0x1400aaa1b  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400aaa23  mov     rcx, r14; MemoryDescriptorList
0x1400aaa26  lea     r8d, [r9+1]; CacheType
0x1400aaa2a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400aaa31  nop     dword ptr [rax+rax+00h]
0x1400aaa36  test    rax, rax
0x1400aaa39  jnz     short loc_1400AAA42
0x1400aaa3b  mov     ebx, 0C000009Ah
0x1400aaa40  jmp     short loc_1400AAA85
0x1400aaa42  lea     r14, [rbp+28E8h]
0x1400aaa49  mov     rcx, r14
0x1400aaa4c  call    VidObjectLockAcquireExclusive
0x1400aaa51  cmp     qword ptr [rbp+2A08h], 0
0x1400aaa59  jz      short loc_1400AAA62
0x1400aaa5b  mov     ebx, 0C000000Dh
0x1400aaa60  jmp     short loc_1400AAA78
0x1400aaa62  mov     rax, [rsp+88h+arg_30]
0x1400aaa6a  xor     ebx, ebx
0x1400aaa6c  mov     [rbp+2A08h], rdi
0x1400aaa73  xor     edi, edi
0x1400aaa75  mov     [rax], rsi
0x1400aaa78  mov     rcx, r14
0x1400aaa7b  call    VidObjectLockRelease
0x1400aaa80  test    rdi, rdi
0x1400aaa83  jz      short loc_1400AAA8D
0x1400aaa85  mov     rdx, rdi
0x1400aaa88  call    VsmmEpfpContextFree
0x1400aaa8d  mov     rdx, [rsp+88h+var_48]
0x1400aaa92  test    rdx, rdx
0x1400aaa95  jz      short loc_1400AAAA6
0x1400aaa97  xor     r8d, r8d
0x1400aaa9a  call    VsmmGpaRangeRelease
0x1400aaa9f  jmp     short loc_1400AAAA6
0x1400aaaa1  mov     ebx, 0C000000Dh
0x1400aaaa6  mov     eax, ebx
0x1400aaaa8  add     rsp, 58h
0x1400aaaac  pop     r15
0x1400aaaae  pop     r14
0x1400aaab0  pop     rdi
0x1400aaab1  pop     rsi
0x1400aaab2  pop     rbp
0x1400aaab3  pop     rbx
0x1400aaab4  retn
```
