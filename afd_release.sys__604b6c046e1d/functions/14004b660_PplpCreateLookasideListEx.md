# PplpCreateLookasideListEx

- ea: `0x14004b660`
- end: `0x14004b7d4`
- name: `PplpCreateLookasideListEx`
- size: `372`
- prototype: `_DWORD *__fastcall(int, ALLOCATE_FUNCTION_EX *, FREE_FUNCTION_EX *, __int64, int, int, SIZE_T Size, ULONG Tag, USHORT Depth, ULONG)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14004b580`

## callees

- `0x14004b660`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x14004b6b2`
- `ntoskrnl!ExAllocatePool3` at `0x14004b6b2`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004b6fe`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004b6fe`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14004b73c`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14004b73c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b77f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b77f`

## pseudocode

```c
_DWORD *__fastcall PplpCreateLookasideListEx(
        int a1,
        ALLOCATE_FUNCTION_EX *a2,
        FREE_FUNCTION_EX *a3,
        __int64 a4,
        int a5,
        int a6,
        SIZE_T Size,
        ULONG Tag,
        USHORT Depth,
        ULONG a10)
{
  int v10; // ebp
  _DWORD *Pool3; // rbx
  int i; // esi
  _DWORD *v13; // rdi
  _DWORD *result; // rax
  _QWORD v15[9]; // [rsp+40h] [rbp-48h] BYREF

  v15[1] = 0;
  v15[0] = 1;
  v10 = a1 + 1;
  Pool3 = (_DWORD *)ExAllocatePool3(72, ((unsigned __int64)(unsigned int)(a1 + 1) << 7) + 64, a10, v15, 1);
  if ( !Pool3 )
    return 0;
  for ( i = 0; i < v10; ++i )
  {
    v13 = &Pool3[32 * (__int64)i];
    KeInitializeSpinLock((PKSPIN_LOCK)v13 + 21);
    if ( i )
    {
      *((_BYTE *)v13 + 176) = 0;
      *((_QWORD *)v13 + 20) = Pool3 + 16;
    }
    else
    {
      if ( ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(v13 + 16), a2, a3, (POOL_TYPE)512, 0, Size, Tag, Depth) < 0 )
      {
        ExFreePoolWithTag(Pool3, a10);
        return 0;
      }
      *((_QWORD *)v13 + 20) = 0;
      *((_BYTE *)v13 + 176) = 1;
    }
  }
  *Pool3 = v10;
  result = Pool3;
  Pool3[1] = 0;
  Pool3[2] = Tag;
  Pool3[3] = a10;
  *((_QWORD *)Pool3 + 2) = Size;
  Pool3[8] = 512;
  *((_WORD *)Pool3 + 18) = Depth;
  *((_QWORD *)Pool3 + 3) = 0;
  return result;
}

```

## disassembly

```asm
0x14004b660  mov     r11, rsp
0x14004b663  mov     [r11+8], rbx
0x14004b667  mov     [r11+18h], r8
0x14004b66b  mov     [r11+10h], rdx
0x14004b66f  push    rbp
0x14004b670  push    rsi
0x14004b671  push    rdi
0x14004b672  push    r12
0x14004b674  push    r13
0x14004b676  push    r14
0x14004b678  push    r15
0x14004b67a  sub     rsp, 50h
0x14004b67e  mov     r14d, [rsp+88h+arg_48]
0x14004b686  lea     r9, [r11-48h]
0x14004b68a  mov     eax, 1
0x14004b68f  mov     qword ptr [r11-40h], 0
0x14004b697  mov     r8d, r14d
0x14004b69a  mov     [r11-48h], rax
0x14004b69e  mov     [rsp+88h+Flags], eax
0x14004b6a2  lea     ebp, [rax+rcx]
0x14004b6a5  mov     edx, ebp
0x14004b6a7  lea     ecx, [rax+47h]
0x14004b6aa  shl     rdx, 7
0x14004b6ae  add     rdx, 40h ; '@'
0x14004b6b2  call    cs:__imp_ExAllocatePool3
0x14004b6b9  nop     dword ptr [rax+rax+00h]
0x14004b6be  mov     rbx, rax
0x14004b6c1  test    rax, rax
0x14004b6c4  jz      loc_14004B78B
0x14004b6ca  movzx   r15d, [rsp+88h+arg_40]
0x14004b6d3  xor     esi, esi
0x14004b6d5  mov     r12d, [rsp+88h+arg_38]
0x14004b6dd  mov     r13, [rsp+88h+arg_30]
0x14004b6e5  cmp     esi, ebp
0x14004b6e7  jge     loc_14004B7A6
0x14004b6ed  movsxd  rdi, esi
0x14004b6f0  shl     rdi, 7
0x14004b6f4  add     rdi, rbx
0x14004b6f7  lea     rcx, [rdi+0A8h]; SpinLock
0x14004b6fe  call    cs:__imp_KeInitializeSpinLock
0x14004b705  nop     dword ptr [rax+rax+00h]
0x14004b70a  test    esi, esi
0x14004b70c  jnz     short loc_14004B760
0x14004b70e  mov     r8, [rsp+88h+Free]; Free
0x14004b716  lea     rcx, [rdi+40h]; Lookaside
0x14004b71a  mov     rdx, [rsp+88h+Allocate]; Allocate
0x14004b722  mov     r9d, 200h; PoolType
0x14004b728  mov     [rsp+88h+Depth], r15w; Depth
0x14004b72e  mov     [rsp+88h+Tag], r12d; Tag
0x14004b733  mov     [rsp+88h+Size], r13; Size
0x14004b738  mov     [rsp+88h+Flags], esi; Flags
0x14004b73c  call    cs:__imp_ExInitializeLookasideListEx
0x14004b743  nop     dword ptr [rax+rax+00h]
0x14004b748  test    eax, eax
0x14004b74a  js      short loc_14004B779
0x14004b74c  mov     qword ptr [rdi+0A0h], 0
0x14004b757  mov     byte ptr [rdi+0B0h], 1
0x14004b75e  jmp     short loc_14004B772
0x14004b760  lea     rax, [rbx+40h]
0x14004b764  mov     byte ptr [rdi+0B0h], 0
0x14004b76b  mov     [rdi+0A0h], rax
0x14004b772  inc     esi
0x14004b774  jmp     loc_14004B6E5
0x14004b779  mov     edx, r14d; Tag
0x14004b77c  mov     rcx, rbx; P
0x14004b77f  call    cs:__imp_ExFreePoolWithTag
0x14004b786  nop     dword ptr [rax+rax+00h]
0x14004b78b  xor     eax, eax
0x14004b78d  mov     rbx, [rsp+88h+arg_0]
0x14004b795  add     rsp, 50h
0x14004b799  pop     r15
0x14004b79b  pop     r14
0x14004b79d  pop     r13
0x14004b79f  pop     r12
0x14004b7a1  pop     rdi
0x14004b7a2  pop     rsi
0x14004b7a3  pop     rbp
0x14004b7a4  retn
0x14004b7a6  mov     [rbx], ebp
0x14004b7a8  mov     rax, rbx
0x14004b7ab  mov     dword ptr [rbx+4], 0
0x14004b7b2  mov     [rbx+8], r12d
0x14004b7b6  mov     [rbx+0Ch], r14d
0x14004b7ba  mov     [rbx+10h], r13
0x14004b7be  mov     dword ptr [rbx+20h], 200h
0x14004b7c5  mov     [rbx+24h], r15w
0x14004b7ca  mov     qword ptr [rbx+18h], 0
0x14004b7d2  jmp     short loc_14004B78D
```
