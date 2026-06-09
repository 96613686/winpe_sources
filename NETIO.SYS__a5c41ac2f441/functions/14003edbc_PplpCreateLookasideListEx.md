# PplpCreateLookasideListEx

- ea: `0x14003edbc`
- end: `0x14003ef1e`
- name: `PplpCreateLookasideListEx`
- size: `354`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, SIZE_T, ULONG, __int16, ULONG)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14003ed58`

## callees

- `0x14003edbc`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x14003ee07`
- `ntoskrnl!ExAllocatePool3` at `0x14003ee07`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003eea6`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003eea6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ef0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ef0e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003ee53`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003ee53`

## pseudocode

```c
_DWORD *__fastcall PplpCreateLookasideListEx(
        int a1,
        ALLOCATE_FUNCTION_EX *a2,
        __int64 a3,
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
  char *v13; // rdi
  _DWORD *result; // rax
  _QWORD v15[11]; // [rsp+40h] [rbp-58h] BYREF

  v15[1] = 0;
  v15[0] = 1;
  v10 = a1 + 1;
  Pool3 = (_DWORD *)ExAllocatePool3(72, ((unsigned __int64)(unsigned int)(a1 + 1) << 7) + 64, a10, v15, 1);
  if ( !Pool3 )
    return 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= v10 )
    {
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
    v13 = (char *)&Pool3[32 * (__int64)i];
    KeInitializeSpinLock((PKSPIN_LOCK)v13 + 21);
    if ( i )
    {
      v13[176] = 0;
      *((_QWORD *)v13 + 20) = Pool3 + 16;
      continue;
    }
    if ( ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(v13 + 64), a2, 0, (POOL_TYPE)512, 0, Size, Tag, Depth) < 0 )
      break;
    *((_QWORD *)v13 + 20) = 0;
    v13[176] = 1;
  }
  ExFreePoolWithTag(Pool3, a10);
  return 0;
}

```

## disassembly

```asm
0x14003edbc  mov     r11, rsp
0x14003edbf  mov     [r11+10h], rdx
0x14003edc3  push    rbx
0x14003edc4  push    rbp
0x14003edc5  push    rsi
0x14003edc6  push    rdi
0x14003edc7  push    r12
0x14003edc9  push    r13
0x14003edcb  push    r14
0x14003edcd  push    r15
0x14003edcf  sub     rsp, 58h
0x14003edd3  mov     r14d, [rsp+98h+arg_48]
0x14003eddb  lea     r9, [r11-58h]
0x14003eddf  mov     eax, 1
0x14003ede4  mov     qword ptr [r11-50h], 0
0x14003edec  mov     r8d, r14d
0x14003edef  mov     [r11-58h], rax
0x14003edf3  mov     [rsp+98h+Flags], eax
0x14003edf7  lea     ebp, [rax+rcx]
0x14003edfa  mov     edx, ebp
0x14003edfc  lea     ecx, [rax+47h]
0x14003edff  shl     rdx, 7
0x14003ee03  add     rdx, 40h ; '@'
0x14003ee07  call    cs:__imp_ExAllocatePool3
0x14003ee0e  nop     dword ptr [rax+rax+00h]
0x14003ee13  mov     rbx, rax
0x14003ee16  test    rax, rax
0x14003ee19  jz      loc_14003EF1A
0x14003ee1f  movzx   r15d, [rsp+98h+arg_40]
0x14003ee28  xor     esi, esi
0x14003ee2a  mov     r12d, [rsp+98h+arg_38]
0x14003ee32  mov     r13, [rsp+98h+arg_30]
0x14003ee3a  cmp     esi, ebp
0x14003ee3c  jge     loc_14003EECA
0x14003ee42  movsxd  rdi, esi
0x14003ee45  shl     rdi, 7
0x14003ee49  add     rdi, rbx
0x14003ee4c  lea     rcx, [rdi+0A8h]; SpinLock
0x14003ee53  call    cs:__imp_KeInitializeSpinLock
0x14003ee5a  nop     dword ptr [rax+rax+00h]
0x14003ee5f  test    esi, esi
0x14003ee61  jz      short loc_14003EE79
0x14003ee63  lea     rax, [rbx+40h]
0x14003ee67  mov     byte ptr [rdi+0B0h], 0
0x14003ee6e  mov     [rdi+0A0h], rax
0x14003ee75  inc     esi
0x14003ee77  jmp     short loc_14003EE3A
0x14003ee79  mov     rdx, [rsp+98h+Allocate]; Allocate
0x14003ee81  lea     rcx, [rdi+40h]; Lookaside
0x14003ee85  mov     [rsp+98h+Depth], r15w; Depth
0x14003ee8b  mov     r9d, 200h; PoolType
0x14003ee91  mov     [rsp+98h+Tag], r12d; Tag
0x14003ee96  xor     r8d, r8d; Free
0x14003ee99  mov     [rsp+98h+Size], r13; Size
0x14003ee9e  mov     [rsp+98h+Flags], 0; Flags
0x14003eea6  call    cs:__imp_ExInitializeLookasideListEx
0x14003eead  nop     dword ptr [rax+rax+00h]
0x14003eeb2  test    eax, eax
0x14003eeb4  js      short loc_14003EF08
0x14003eeb6  mov     qword ptr [rdi+0A0h], 0
0x14003eec1  mov     byte ptr [rdi+0B0h], 1
0x14003eec8  jmp     short loc_14003EE75
0x14003eeca  mov     [rbx], ebp
0x14003eecc  mov     rax, rbx
0x14003eecf  mov     dword ptr [rbx+4], 0
0x14003eed6  mov     [rbx+8], r12d
0x14003eeda  mov     [rbx+0Ch], r14d
0x14003eede  mov     [rbx+10h], r13
0x14003eee2  mov     dword ptr [rbx+20h], 200h
0x14003eee9  mov     [rbx+24h], r15w
0x14003eeee  mov     qword ptr [rbx+18h], 0
0x14003eef6  add     rsp, 58h
0x14003eefa  pop     r15
0x14003eefc  pop     r14
0x14003eefe  pop     r13
0x14003ef00  pop     r12
0x14003ef02  pop     rdi
0x14003ef03  pop     rsi
0x14003ef04  pop     rbp
0x14003ef05  pop     rbx
0x14003ef06  retn
0x14003ef08  mov     edx, r14d; Tag
0x14003ef0b  mov     rcx, rbx; P
0x14003ef0e  call    cs:__imp_ExFreePoolWithTag
0x14003ef15  nop     dword ptr [rax+rax+00h]
0x14003ef1a  xor     eax, eax
0x14003ef1c  jmp     short loc_14003EEF6
```
