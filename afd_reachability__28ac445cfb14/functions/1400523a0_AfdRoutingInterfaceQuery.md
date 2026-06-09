# AfdRoutingInterfaceQuery

- ea: `0x1400523a0`
- end: `0x1400525ce`
- name: `AfdRoutingInterfaceQuery`
- size: `558`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140001bb4`
- `0x1400325b4`
- `0x1400445b8`
- `0x1400523a0`
- `0x1400525d4`
- `0x1400726a0`
- `0x1400726d0`
- `0x140092008`
- `0x140094900`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140052572`
- `ntoskrnl!ExRaiseStatus` at `0x140052572`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052598`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052598`
- `ntoskrnl!ExAllocatePool2` at `0x140052454`
- `ntoskrnl!ExAllocatePool2` at `0x140052454`
- `ntoskrnl!ProbeForWrite` at `0x140052524`
- `ntoskrnl!ProbeForWrite` at `0x140052524`

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
  __int64 v13; // r8
  unsigned __int16 v14; // ax
  int v15; // eax
  size_t v16; // r8
  void *v17; // rdx
  unsigned int v19; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int16 *v20; // [rsp+38h] [rbp-60h]
  _BYTE v21[40]; // [rsp+40h] [rbp-58h] BYREF

  v19 = 0;
  *a8 = 0;
  Pool2 = (unsigned __int16 *)v21;
  v20 = (unsigned __int16 *)v21;
  if ( Size >= 0xC )
  {
    if ( Size > 0x22 )
    {
      Pool2 = (unsigned __int16 *)ExAllocatePool2(289, Size, 1902405185);
      v20 = Pool2;
    }
    if ( a3 )
      RtlCopyFromUser(Pool2, a4, Size);
    else
      RtlCopyVolatileMemory(Pool2, a4, Size);
    if ( *(_DWORD *)Pool2 != 1 || Size < (unsigned int)Pool2[2] + 8 )
      ExRaiseStatus(-1073741811);
    v12 = AfdQueryCompartmentId(*(_QWORD *)(a1 + 24), &v19, v13);
    if ( v12 >= 0 )
    {
      v14 = Pool2[3];
      if ( v14 == 2 )
      {
        v15 = AfdTcpRoutingQuery(Pool2 + 2, Pool2 + 2, v19);
      }
      else
      {
        if ( v14 != 23 )
        {
          v12 = -1073741637;
          goto LABEL_28;
        }
        v15 = AfdTcp6RoutingQuery(Pool2 + 2, Pool2 + 2, v19);
      }
      v12 = v15;
      if ( v15 >= 0 )
      {
        if ( (unsigned __int64)Pool2[2] + 2 > Length )
        {
          v12 = -2147483643;
        }
        else
        {
          if ( a3 )
            ProbeForWrite(Address, Length, 1u);
          v16 = Pool2[2] + 2LL;
          v17 = Pool2 + 3;
          if ( a3 )
            RtlCopyToUser((void *)Address, v17, v16);
          else
            RtlCopyVolatileMemory((void *)Address, v17, v16);
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
  if ( Pool2 != (unsigned __int16 *)v21 )
    ExFreePoolWithTag(Pool2, 0x71646641u);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400523a0  mov     r11, rsp
0x1400523a3  mov     [r11+10h], rbx
0x1400523a7  mov     [r11+18h], rsi
0x1400523ab  push    rdi
0x1400523ac  push    r12
0x1400523ae  push    r13
0x1400523b0  push    r14
0x1400523b2  push    r15
0x1400523b4  sub     rsp, 70h
0x1400523b8  mov     rax, cs:__security_cookie
0x1400523bf  xor     rax, rsp
0x1400523c2  mov     [rsp+98h+var_30], rax
0x1400523c7  mov     rsi, r9
0x1400523ca  mov     r15b, r8b
0x1400523cd  mov     r14, rcx
0x1400523d0  mov     ebx, dword ptr [rsp+98h+Size]
0x1400523d7  mov     r12, [rsp+98h+Address]
0x1400523df  mov     r13, [rsp+98h+arg_38]
0x1400523e7  mov     qword ptr [r11-60h], 0
0x1400523ef  mov     [rsp+98h+var_68], 0
0x1400523f7  mov     qword ptr [r13+0], 0
0x1400523ff  lea     rdi, [r11-58h]
0x140052403  mov     [r11-60h], rdi
0x140052407  cmp     ebx, 0Ch
0x14005240a  jnb     short loc_140052441
0x14005240c  test    byte ptr cs:xmmword_1400875E0+0Ah, 1
0x140052413  jz      short loc_140052437
0x140052415  mov     edx, 0Ah
0x14005241a  mov     ecx, 510h
0x14005241f  mov     [rsp+98h+var_70], ebx
0x140052423  mov     [r11-78h], r9
0x140052427  mov     r9, [r14+18h]
0x14005242b  lea     r8, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids
0x140052432  call    WPP_SF_qqD
0x140052437  mov     ebx, 0C000000Dh
0x14005243c  jmp     loc_140052586
0x140052441  cmp     ebx, 22h ; '"'
0x140052444  jbe     short loc_140052468
0x140052446  mov     rdx, rbx
0x140052449  mov     ecx, 121h
0x14005244e  mov     r8d, 71646641h
0x140052454  call    cs:__imp_ExAllocatePool2
0x14005245b  nop     dword ptr [rax+rax+00h]
0x140052460  mov     rdi, rax
0x140052463  mov     [rsp+98h+var_60], rax
0x140052468  mov     r8, rbx; Size
0x14005246b  mov     rdx, rsi; Src
0x14005246e  mov     rcx, rdi; void *
0x140052471  test    r15b, r15b
0x140052474  jz      short loc_14005247D
0x140052476  call    RtlCopyFromUser
0x14005247b  jmp     short loc_140052482
0x14005247d  call    RtlCopyVolatileMemory
0x140052482  cmp     dword ptr [rdi], 1
0x140052485  jnz     loc_14005256D
0x14005248b  movzx   eax, word ptr [rdi+4]
0x14005248f  add     eax, 8
0x140052492  cmp     ebx, eax
0x140052494  jb      loc_14005256D
0x14005249a  lea     rdx, [rsp+98h+var_68]
0x14005249f  mov     rcx, [r14+18h]
0x1400524a3  call    AfdQueryCompartmentId
0x1400524a8  mov     ebx, eax
0x1400524aa  test    eax, eax
0x1400524ac  js      loc_140052586
0x1400524b2  lea     rsi, [rdi+6]
0x1400524b6  movzx   eax, word ptr [rsi]
0x1400524b9  mov     r14d, 2
0x1400524bf  cmp     ax, r14w
0x1400524c3  jz      short loc_1400524E8
0x1400524c5  cmp     ax, 17h
0x1400524c9  jz      short loc_1400524D5
0x1400524cb  mov     ebx, 0C00000BBh
0x1400524d0  jmp     loc_140052586
0x1400524d5  lea     rcx, [rdi+4]
0x1400524d9  mov     r8d, [rsp+98h+var_68]
0x1400524de  mov     rdx, rcx
0x1400524e1  call    AfdTcp6RoutingQuery
0x1400524e6  jmp     short loc_1400524F9
0x1400524e8  lea     rcx, [rdi+4]
0x1400524ec  mov     r8d, [rsp+98h+var_68]
0x1400524f1  mov     rdx, rcx
0x1400524f4  call    AfdTcpRoutingQuery
0x1400524f9  mov     ebx, eax
0x1400524fb  test    eax, eax
0x1400524fd  js      loc_140052586
0x140052503  mov     edx, dword ptr [rsp+98h+Length]; Length
0x14005250a  movzx   eax, word ptr [rdi+4]
0x14005250e  add     rax, r14
0x140052511  cmp     rax, rdx
0x140052514  ja      short loc_14005255B
0x140052516  test    r15b, r15b
0x140052519  jz      short loc_140052530
0x14005251b  mov     r8d, 1; Alignment
0x140052521  mov     rcx, r12; Address
0x140052524  call    cs:__imp_ProbeForWrite
0x14005252b  nop     dword ptr [rax+rax+00h]
0x140052530  movzx   r8d, word ptr [rdi+4]
0x140052535  add     r8, 2; Size
0x140052539  mov     rdx, rsi; Src
0x14005253c  mov     rcx, r12; void *
0x14005253f  test    r15b, r15b
0x140052542  jz      short loc_14005254B
0x140052544  call    RtlCopyToUser
0x140052549  jmp     short loc_140052550
0x14005254b  call    RtlCopyVolatileMemory
0x140052550  jmp     short loc_140052560
0x140052552  mov     ebx, eax
0x140052554  mov     rdi, [rsp+98h+var_60]
0x140052559  jmp     short loc_140052586
0x14005255b  mov     ebx, 80000005h
0x140052560  movzx   eax, word ptr [rdi+4]
0x140052564  add     rax, r14
0x140052567  mov     [r13+0], rax
0x14005256b  jmp     short loc_140052586
0x14005256d  mov     ecx, 0C000000Dh; Status
0x140052572  call    cs:__imp_ExRaiseStatus
0x14005257f  mov     ebx, eax
0x140052581  mov     rdi, [rsp+98h+var_60]
0x140052586  lea     rax, [rsp+98h+var_58]
0x14005258b  cmp     rdi, rax
0x14005258e  jz      short loc_1400525A4
0x140052590  mov     edx, 71646641h; Tag
0x140052595  mov     rcx, rdi; P
0x140052598  call    cs:__imp_ExFreePoolWithTag
0x14005259f  nop     dword ptr [rax+rax+00h]
0x1400525a4  mov     eax, ebx
0x1400525a6  mov     rcx, [rsp+98h+var_30]
0x1400525ab  xor     rcx, rsp; StackCookie
0x1400525ae  call    __security_check_cookie
0x1400525b3  lea     r11, [rsp+98h+var_28]
0x1400525b8  mov     rbx, [r11+38h]
0x1400525bc  mov     rsi, [r11+40h]
0x1400525c0  mov     rsp, r11
0x1400525c3  pop     r15
0x1400525c5  pop     r14
0x1400525c7  pop     r13
0x1400525c9  pop     r12
0x1400525cb  pop     rdi
0x1400525cc  retn
```
