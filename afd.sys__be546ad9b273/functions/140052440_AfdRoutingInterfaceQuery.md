# AfdRoutingInterfaceQuery

- ea: `0x140052440`
- end: `0x14005266e`
- name: `AfdRoutingInterfaceQuery`
- size: `558`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140001bb4`
- `0x1400325d4`
- `0x1400445d8`
- `0x140052440`
- `0x140052674`
- `0x140072840`
- `0x140072870`
- `0x140092008`
- `0x140094900`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140052612`
- `ntoskrnl!ExRaiseStatus` at `0x140052612`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052638`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052638`
- `ntoskrnl!ExAllocatePool2` at `0x1400524f4`
- `ntoskrnl!ExAllocatePool2` at `0x1400524f4`
- `ntoskrnl!ProbeForWrite` at `0x1400525c4`
- `ntoskrnl!ProbeForWrite` at `0x1400525c4`

## pseudocode

```c
__int64 __fastcall AfdRoutingInterfaceQuery(
        __int64 a1,
        __int64 a2,
        char a3,
        void *a4,
        unsigned int Size,
        volatile void *Address,
        unsigned int Length,
        _QWORD *a8)
{
  unsigned __int16 *Pool2; // rdi
  int v12; // ebx
  unsigned __int16 v13; // ax
  int v14; // eax
  size_t v15; // r8
  void *v16; // rdx
  unsigned int v18; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int16 *v19; // [rsp+38h] [rbp-60h]
  _BYTE v20[40]; // [rsp+40h] [rbp-58h] BYREF

  v18 = 0;
  *a8 = 0;
  Pool2 = (unsigned __int16 *)v20;
  v19 = (unsigned __int16 *)v20;
  if ( Size >= 0xC )
  {
    if ( Size > 0x22 )
    {
      Pool2 = (unsigned __int16 *)ExAllocatePool2(289, Size, 1902405185);
      v19 = Pool2;
    }
    if ( a3 )
      RtlCopyFromUser(Pool2, a4, Size);
    else
      RtlCopyVolatileMemory(Pool2, a4, Size);
    if ( *(_DWORD *)Pool2 != 1 || Size < (unsigned int)Pool2[2] + 8 )
      ExRaiseStatus(-1073741811);
    v12 = AfdQueryCompartmentId(*(__int16 **)(a1 + 24), &v18);
    if ( v12 >= 0 )
    {
      v13 = Pool2[3];
      if ( v13 == 2 )
      {
        v14 = AfdTcpRoutingQuery(Pool2 + 2, Pool2 + 2, v18);
      }
      else
      {
        if ( v13 != 23 )
        {
          v12 = -1073741637;
          goto LABEL_28;
        }
        v14 = AfdTcp6RoutingQuery(Pool2 + 2, Pool2 + 2, v18);
      }
      v12 = v14;
      if ( v14 >= 0 )
      {
        if ( (unsigned __int64)Pool2[2] + 2 > Length )
        {
          v12 = -2147483643;
        }
        else
        {
          if ( a3 )
            ProbeForWrite(Address, Length, 1u);
          v15 = Pool2[2] + 2LL;
          v16 = Pool2 + 3;
          if ( a3 )
            RtlCopyToUser((void *)Address, v16, v15);
          else
            RtlCopyVolatileMemory((void *)Address, v16, v15);
        }
        *a8 = Pool2[2] + 2LL;
      }
    }
  }
  else
  {
    if ( (BYTE10(xmmword_1400875E0) & 1) != 0 )
      WPP_SF_qqD(1296, 10, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids, *(_QWORD *)(a1 + 24), a4, Size);
    v12 = -1073741811;
  }
LABEL_28:
  if ( Pool2 != (unsigned __int16 *)v20 )
    ExFreePoolWithTag(Pool2, 0x71646641u);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140052440  mov     r11, rsp
0x140052443  mov     [r11+10h], rbx
0x140052447  mov     [r11+18h], rsi
0x14005244b  push    rdi
0x14005244c  push    r12
0x14005244e  push    r13
0x140052450  push    r14
0x140052452  push    r15
0x140052454  sub     rsp, 70h
0x140052458  mov     rax, cs:__security_cookie
0x14005245f  xor     rax, rsp
0x140052462  mov     [rsp+98h+var_30], rax
0x140052467  mov     rsi, r9
0x14005246a  mov     r15b, r8b
0x14005246d  mov     r14, rcx
0x140052470  mov     ebx, dword ptr [rsp+98h+Size]
0x140052477  mov     r12, [rsp+98h+Address]
0x14005247f  mov     r13, [rsp+98h+arg_38]
0x140052487  mov     qword ptr [r11-60h], 0
0x14005248f  mov     [rsp+98h+var_68], 0
0x140052497  mov     qword ptr [r13+0], 0
0x14005249f  lea     rdi, [r11-58h]
0x1400524a3  mov     [r11-60h], rdi
0x1400524a7  cmp     ebx, 0Ch
0x1400524aa  jnb     short loc_1400524E1
0x1400524ac  test    byte ptr cs:xmmword_1400875E0+0Ah, 1
0x1400524b3  jz      short loc_1400524D7
0x1400524b5  mov     edx, 0Ah
0x1400524ba  mov     ecx, 510h
0x1400524bf  mov     [rsp+98h+var_70], ebx
0x1400524c3  mov     [r11-78h], r9
0x1400524c7  mov     r9, [r14+18h]
0x1400524cb  lea     r8, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids
0x1400524d2  call    WPP_SF_qqD
0x1400524d7  mov     ebx, 0C000000Dh
0x1400524dc  jmp     loc_140052626
0x1400524e1  cmp     ebx, 22h ; '"'
0x1400524e4  jbe     short loc_140052508
0x1400524e6  mov     rdx, rbx
0x1400524e9  mov     ecx, 121h
0x1400524ee  mov     r8d, 71646641h
0x1400524f4  call    cs:__imp_ExAllocatePool2
0x1400524fb  nop     dword ptr [rax+rax+00h]
0x140052500  mov     rdi, rax
0x140052503  mov     [rsp+98h+var_60], rax
0x140052508  mov     r8, rbx; Size
0x14005250b  mov     rdx, rsi; Src
0x14005250e  mov     rcx, rdi; void *
0x140052511  test    r15b, r15b
0x140052514  jz      short loc_14005251D
0x140052516  call    RtlCopyFromUser
0x14005251b  jmp     short loc_140052522
0x14005251d  call    RtlCopyVolatileMemory
0x140052522  cmp     dword ptr [rdi], 1
0x140052525  jnz     loc_14005260D
0x14005252b  movzx   eax, word ptr [rdi+4]
0x14005252f  add     eax, 8
0x140052532  cmp     ebx, eax
0x140052534  jb      loc_14005260D
0x14005253a  lea     rdx, [rsp+98h+var_68]
0x14005253f  mov     rcx, [r14+18h]
0x140052543  call    AfdQueryCompartmentId
0x140052548  mov     ebx, eax
0x14005254a  test    eax, eax
0x14005254c  js      loc_140052626
0x140052552  lea     rsi, [rdi+6]
0x140052556  movzx   eax, word ptr [rsi]
0x140052559  mov     r14d, 2
0x14005255f  cmp     ax, r14w
0x140052563  jz      short loc_140052588
0x140052565  cmp     ax, 17h
0x140052569  jz      short loc_140052575
0x14005256b  mov     ebx, 0C00000BBh
0x140052570  jmp     loc_140052626
0x140052575  lea     rcx, [rdi+4]
0x140052579  mov     r8d, [rsp+98h+var_68]
0x14005257e  mov     rdx, rcx
0x140052581  call    AfdTcp6RoutingQuery
0x140052586  jmp     short loc_140052599
0x140052588  lea     rcx, [rdi+4]
0x14005258c  mov     r8d, [rsp+98h+var_68]
0x140052591  mov     rdx, rcx
0x140052594  call    AfdTcpRoutingQuery
0x140052599  mov     ebx, eax
0x14005259b  test    eax, eax
0x14005259d  js      loc_140052626
0x1400525a3  mov     edx, dword ptr [rsp+98h+Length]; Length
0x1400525aa  movzx   eax, word ptr [rdi+4]
0x1400525ae  add     rax, r14
0x1400525b1  cmp     rax, rdx
0x1400525b4  ja      short loc_1400525FB
0x1400525b6  test    r15b, r15b
0x1400525b9  jz      short loc_1400525D0
0x1400525bb  mov     r8d, 1; Alignment
0x1400525c1  mov     rcx, r12; Address
0x1400525c4  call    cs:__imp_ProbeForWrite
0x1400525cb  nop     dword ptr [rax+rax+00h]
0x1400525d0  movzx   r8d, word ptr [rdi+4]
0x1400525d5  add     r8, 2; Size
0x1400525d9  mov     rdx, rsi; Src
0x1400525dc  mov     rcx, r12; void *
0x1400525df  test    r15b, r15b
0x1400525e2  jz      short loc_1400525EB
0x1400525e4  call    RtlCopyToUser
0x1400525e9  jmp     short loc_1400525F0
0x1400525eb  call    RtlCopyVolatileMemory
0x1400525f0  jmp     short loc_140052600
0x1400525f2  mov     ebx, eax
0x1400525f4  mov     rdi, [rsp+98h+var_60]
0x1400525f9  jmp     short loc_140052626
0x1400525fb  mov     ebx, 80000005h
0x140052600  movzx   eax, word ptr [rdi+4]
0x140052604  add     rax, r14
0x140052607  mov     [r13+0], rax
0x14005260b  jmp     short loc_140052626
0x14005260d  mov     ecx, 0C000000Dh; Status
0x140052612  call    cs:__imp_ExRaiseStatus
0x14005261f  mov     ebx, eax
0x140052621  mov     rdi, [rsp+98h+var_60]
0x140052626  lea     rax, [rsp+98h+var_58]
0x14005262b  cmp     rdi, rax
0x14005262e  jz      short loc_140052644
0x140052630  mov     edx, 71646641h; Tag
0x140052635  mov     rcx, rdi; P
0x140052638  call    cs:__imp_ExFreePoolWithTag
0x14005263f  nop     dword ptr [rax+rax+00h]
0x140052644  mov     eax, ebx
0x140052646  mov     rcx, [rsp+98h+var_30]
0x14005264b  xor     rcx, rsp; StackCookie
0x14005264e  call    __security_check_cookie
0x140052653  lea     r11, [rsp+98h+var_28]
0x140052658  mov     rbx, [r11+38h]
0x14005265c  mov     rsi, [r11+40h]
0x140052660  mov     rsp, r11
0x140052663  pop     r15
0x140052665  pop     r14
0x140052667  pop     r13
0x140052669  pop     r12
0x14005266b  pop     rdi
0x14005266c  retn
```
