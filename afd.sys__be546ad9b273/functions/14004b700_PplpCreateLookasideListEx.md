# PplpCreateLookasideListEx

- ea: `0x14004b700`
- end: `0x14004b874`
- name: `PplpCreateLookasideListEx`
- size: `372`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, SIZE_T, ULONG, __int16, ULONG)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14004b620`

## callees

- `0x14004b700`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x14004b752`
- `ntoskrnl!ExAllocatePool3` at `0x14004b752`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004b79e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004b79e`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14004b7dc`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14004b7dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b81f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b81f`

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
0x14004b700  mov     r11, rsp
0x14004b703  mov     [r11+8], rbx
0x14004b707  mov     [r11+18h], r8
0x14004b70b  mov     [r11+10h], rdx
0x14004b70f  push    rbp
0x14004b710  push    rsi
0x14004b711  push    rdi
0x14004b712  push    r12
0x14004b714  push    r13
0x14004b716  push    r14
0x14004b718  push    r15
0x14004b71a  sub     rsp, 50h
0x14004b71e  mov     r14d, [rsp+88h+arg_48]
0x14004b726  lea     r9, [r11-48h]
0x14004b72a  mov     eax, 1
0x14004b72f  mov     qword ptr [r11-40h], 0
0x14004b737  mov     r8d, r14d
0x14004b73a  mov     [r11-48h], rax
0x14004b73e  mov     [rsp+88h+Flags], eax
0x14004b742  lea     ebp, [rax+rcx]
0x14004b745  mov     edx, ebp
0x14004b747  lea     ecx, [rax+47h]
0x14004b74a  shl     rdx, 7
0x14004b74e  add     rdx, 40h ; '@'
0x14004b752  call    cs:__imp_ExAllocatePool3
0x14004b759  nop     dword ptr [rax+rax+00h]
0x14004b75e  mov     rbx, rax
0x14004b761  test    rax, rax
0x14004b764  jz      loc_14004B82B
0x14004b76a  movzx   r15d, [rsp+88h+arg_40]
0x14004b773  xor     esi, esi
0x14004b775  mov     r12d, [rsp+88h+arg_38]
0x14004b77d  mov     r13, [rsp+88h+arg_30]
0x14004b785  cmp     esi, ebp
0x14004b787  jge     loc_14004B846
0x14004b78d  movsxd  rdi, esi
0x14004b790  shl     rdi, 7
0x14004b794  add     rdi, rbx
0x14004b797  lea     rcx, [rdi+0A8h]; SpinLock
0x14004b79e  call    cs:__imp_KeInitializeSpinLock
0x14004b7a5  nop     dword ptr [rax+rax+00h]
0x14004b7aa  test    esi, esi
0x14004b7ac  jnz     short loc_14004B800
0x14004b7ae  mov     r8, [rsp+88h+Free]; Free
0x14004b7b6  lea     rcx, [rdi+40h]; Lookaside
0x14004b7ba  mov     rdx, [rsp+88h+Allocate]; Allocate
0x14004b7c2  mov     r9d, 200h; PoolType
0x14004b7c8  mov     [rsp+88h+Depth], r15w; Depth
0x14004b7ce  mov     [rsp+88h+Tag], r12d; Tag
0x14004b7d3  mov     [rsp+88h+Size], r13; Size
0x14004b7d8  mov     [rsp+88h+Flags], esi; Flags
0x14004b7dc  call    cs:__imp_ExInitializeLookasideListEx
0x14004b7e3  nop     dword ptr [rax+rax+00h]
0x14004b7e8  test    eax, eax
0x14004b7ea  js      short loc_14004B819
0x14004b7ec  mov     qword ptr [rdi+0A0h], 0
0x14004b7f7  mov     byte ptr [rdi+0B0h], 1
0x14004b7fe  jmp     short loc_14004B812
0x14004b800  lea     rax, [rbx+40h]
0x14004b804  mov     byte ptr [rdi+0B0h], 0
0x14004b80b  mov     [rdi+0A0h], rax
0x14004b812  inc     esi
0x14004b814  jmp     loc_14004B785
0x14004b819  mov     edx, r14d; Tag
0x14004b81c  mov     rcx, rbx; P
0x14004b81f  call    cs:__imp_ExFreePoolWithTag
0x14004b826  nop     dword ptr [rax+rax+00h]
0x14004b82b  xor     eax, eax
0x14004b82d  mov     rbx, [rsp+88h+arg_0]
0x14004b835  add     rsp, 50h
0x14004b839  pop     r15
0x14004b83b  pop     r14
0x14004b83d  pop     r13
0x14004b83f  pop     r12
0x14004b841  pop     rdi
0x14004b842  pop     rsi
0x14004b843  pop     rbp
0x14004b844  retn
0x14004b846  mov     [rbx], ebp
0x14004b848  mov     rax, rbx
0x14004b84b  mov     dword ptr [rbx+4], 0
0x14004b852  mov     [rbx+8], r12d
0x14004b856  mov     [rbx+0Ch], r14d
0x14004b85a  mov     [rbx+10h], r13
0x14004b85e  mov     dword ptr [rbx+20h], 200h
0x14004b865  mov     [rbx+24h], r15w
0x14004b86a  mov     qword ptr [rbx+18h], 0
0x14004b872  jmp     short loc_14004B82D
```
