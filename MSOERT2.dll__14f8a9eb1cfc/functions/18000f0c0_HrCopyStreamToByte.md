# HrCopyStreamToByte

- ea: `0x18000f0c0`
- end: `0x18000f195`
- name: `HrCopyStreamToByte`
- size: `213`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000f0c0`
- `0x180012f82`
- `0x180012fc0`
- `0x180013050`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall HrCopyStreamToByte(__int64 a1, __int64 a2, unsigned __int64 a3, unsigned int *a4)
{
  unsigned int v8; // esi
  int v9; // edi
  int v10; // ebx
  size_t Size[2]; // [rsp+30h] [rbp-1058h] BYREF
  _BYTE Src[4096]; // [rsp+40h] [rbp-1048h] BYREF

  LODWORD(Size[0]) = 0;
  v8 = 0;
  do
  {
    v9 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, size_t *))(*(_QWORD *)a1 + 24LL))(a1, Src, 4096, Size);
    if ( v9 < 0 )
      break;
    v10 = Size[0];
    if ( !LODWORD(Size[0]) )
      break;
    if ( v8 + LODWORD(Size[0]) > a3 )
    {
      v9 = -2147024774;
      break;
    }
    memcpy_0((void *)(a2 + v8), Src, LODWORD(Size[0]));
    v8 += v10;
  }
  while ( v10 == 4096 );
  if ( a4 )
    *a4 = v8;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000f0c0  mov     [rsp+arg_10], rbx
0x18000f0c5  push    rbp
0x18000f0c6  push    rsi
0x18000f0c7  push    rdi
0x18000f0c8  push    r12
0x18000f0ca  push    r13
0x18000f0cc  push    r14
0x18000f0ce  push    r15
0x18000f0d0  mov     eax, 1050h
0x18000f0d5  call    _alloca_probe
0x18000f0da  sub     rsp, rax
0x18000f0dd  mov     rax, cs:__security_cookie
0x18000f0e4  xor     rax, rsp
0x18000f0e7  mov     [rsp+1088h+var_48], rax
0x18000f0ef  mov     r14, r9
0x18000f0f2  mov     dword ptr [rsp+1088h+Size], 0
0x18000f0fa  mov     r15, r8
0x18000f0fd  mov     r13, rdx
0x18000f100  mov     r12, rcx
0x18000f103  xor     esi, esi
0x18000f105  mov     rax, [r12]
0x18000f109  lea     r9, [rsp+1088h+Size]
0x18000f10e  mov     r8d, 1000h
0x18000f114  lea     rdx, [rsp+1088h+Src]
0x18000f119  mov     rcx, r12
0x18000f11c  mov     rax, [rax+18h]
0x18000f120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f125  mov     edi, eax
0x18000f127  test    eax, eax
0x18000f129  js      short loc_18000F160
0x18000f12b  mov     ebx, dword ptr [rsp+1088h+Size]
0x18000f12f  test    ebx, ebx
0x18000f131  jz      short loc_18000F160
0x18000f133  lea     ebp, [rsi+rbx]
0x18000f136  mov     ecx, ebp
0x18000f138  cmp     rcx, r15
0x18000f13b  ja      short loc_18000F15B
0x18000f13d  mov     ecx, esi
0x18000f13f  lea     rdx, [rsp+1088h+Src]; Src
0x18000f144  add     rcx, r13; void *
0x18000f147  mov     r8d, ebx; Size
0x18000f14a  call    memcpy_0
0x18000f14f  mov     esi, ebp
0x18000f151  cmp     ebx, 1000h
0x18000f157  jz      short loc_18000F105
0x18000f159  jmp     short loc_18000F160
0x18000f15b  mov     edi, 8007007Ah
0x18000f160  test    r14, r14
0x18000f163  jz      short loc_18000F168
0x18000f165  mov     [r14], esi
0x18000f168  mov     eax, edi
0x18000f16a  mov     rcx, [rsp+1088h+var_48]
0x18000f172  xor     rcx, rsp; StackCookie
0x18000f175  call    __security_check_cookie
0x18000f17a  mov     rbx, [rsp+1088h+arg_10]
0x18000f182  add     rsp, 1050h
0x18000f189  pop     r15
0x18000f18b  pop     r14
0x18000f18d  pop     r13
0x18000f18f  pop     r12
0x18000f191  pop     rdi
0x18000f192  pop     rsi
0x18000f193  pop     rbp
0x18000f194  retn
```
