# VidExoVppCreate

- ea: `0x140085a04`
- end: `0x140085cbc`
- name: `VidExoVppCreate`
- size: `696`
- prototype: `__int64 __usercall@<rax>(PVOID DeferredContext@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x1400852bc`

## callees

- `0x140021e00`
- `0x1400248f4`
- `0x1400386a0`
- `0x140085a04`
- `0x140085cc4`
- `0x140085e88`
- `0x140085fd4`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x140085af9`
- `ntoskrnl!KeInitializeDpc` at `0x140085af9`
- `ntoskrnl!ExAllocatePool2` at `0x140085a31`
- `ntoskrnl!ExAllocatePool2` at `0x140085a31`
- `winhvr!WinHvSetDispatchNotificationEvent` at `0x140085c34`
- `winhvr!WinHvSetDispatchNotificationEvent` at `0x140085c34`
- `winhvr!WinHvCreateVp` at `0x140085b2d`
- `winhvr!WinHvCreateVp` at `0x140085b2d`

## string_xrefs

- `0x140085a52`: `VidExoVppCreate`
- `0x140085c53`: `VidExoVppCreate`
- `0x140085c8d`: `VidExoVppCreate`

## pseudocode

```c
__int64 __fastcall VidExoVppCreate(
        PVOID DeferredContext,
        unsigned int a2,
        unsigned int a3,
        _OWORD *a4,
        _QWORD *a5,
        unsigned int **a6)
{
  unsigned int *Pool2; // rax
  unsigned int *v10; // rdi
  int Vp; // ebx
  __int64 v12; // rcx
  __int64 v13; // r8
  _DWORD *v14; // rax
  int v16; // [rsp+20h] [rbp-68h]
  int v17; // [rsp+20h] [rbp-68h]
  _OWORD v18[5]; // [rsp+30h] [rbp-58h] BYREF

  Pool2 = (unsigned int *)ExAllocatePool2(64, 416, 1917084758);
  v10 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = a2;
    memset(Pool2 + 26, 0, 0x48u);
    *((_QWORD *)v10 + 19) = v10 + 36;
    *((_QWORD *)v10 + 18) = v10 + 36;
    memset(v10 + 44, 0, 0x48u);
    *((_QWORD *)v10 + 28) = v10 + 54;
    *((_QWORD *)v10 + 27) = v10 + 54;
    memset(v10 + 62, 0, 0x48u);
    *((_QWORD *)v10 + 37) = v10 + 72;
    *((_QWORD *)v10 + 36) = v10 + 72;
    memset(v10 + 82, 0, 0x48u);
    *((_QWORD *)v10 + 47) = v10 + 92;
    *((_QWORD *)v10 + 46) = v10 + 92;
    KeInitializeDpc((PRKDPC)(v10 + 2), VidExoVppInterceptDpcRoutine, DeferredContext);
    v12 = *((_QWORD *)DeferredContext + 81);
    v18[0] = *a4;
    Vp = WinHvCreateVp(v12, a3, v18, a2, 0);
    if ( Vp >= 0 )
    {
      *((_BYTE *)v10 + 408) = 1;
      Vp = VidExoVppMapStatsPage((_DWORD)DeferredContext, a2, 0, (int)v10 + 104, (__int64)(v10 + 20));
      if ( Vp >= 0 )
      {
        Vp = VidExoVppMapStatsPage((_DWORD)DeferredContext, a2, 1, (int)v10 + 176, (__int64)(v10 + 22));
        if ( Vp >= 0 )
        {
          Vp = VidExoVppMapStatePage((_DWORD)DeferredContext, a2, (int)v10 + 248, 0, v16, (__int64)(v10 + 80));
          if ( Vp >= 0 )
          {
            Vp = VidExoVppMapStatePage((_DWORD)DeferredContext, a2, (int)v10 + 328, 1, v17, (__int64)(v10 + 100));
            if ( Vp >= 0 )
            {
              *((_QWORD *)v10 + 9) = *a5;
              v14 = VidDeviceExtension;
              *a5 = 0;
              if ( (v14[162] & 0x20) == 0
                || (Vp = WinHvSetDispatchNotificationEvent(*((_QWORD *)DeferredContext + 81), a2, *((_QWORD *)v10 + 9)),
                    Vp >= 0) )
              {
                Vp = 0;
                *a6 = v10;
                return (unsigned int)Vp;
              }
              v13 = 978;
            }
            else
            {
              v13 = 960;
            }
          }
          else
          {
            v13 = 947;
          }
        }
        else
        {
          v13 = 931;
        }
      }
      else
      {
        v13 = 919;
      }
    }
    else
    {
      v13 = 902;
    }
    VidTraceErrorInternal0("VidExoVppCreate", "onecore\\vm\\vid\\sys\\driver\\videxovp.c", v13);
    VidExoVppDelete(DeferredContext, v10, 0);
  }
  else
  {
    VidTraceErrorInternal0("VidExoVppCreate", "onecore\\vm\\vid\\sys\\driver\\videxovp.c", 879);
    Vp = -1073741670;
  }
  VidTraceErrorStatusPartitionInternal0(
    (unsigned int)"VidExoVppCreate",
    (unsigned int)"onecore\\vm\\vid\\sys\\driver\\videxovp.c",
    994,
    Vp,
    (__int64)DeferredContext + 656);
  return (unsigned int)Vp;
}

```

## disassembly

```asm
0x140085a04  mov     [rsp+arg_10], r8d
0x140085a09  push    rbx
0x140085a0a  push    rbp
0x140085a0b  push    rsi
0x140085a0c  push    rdi
0x140085a0d  push    r12
0x140085a0f  push    r13
0x140085a11  push    r14
0x140085a13  push    r15
0x140085a15  sub     rsp, 48h
0x140085a19  mov     ebp, edx
0x140085a1b  mov     rsi, rcx
0x140085a1e  mov     edx, 1A0h
0x140085a23  mov     ecx, 40h ; '@'
0x140085a28  mov     r8d, 72446456h
0x140085a2e  mov     rbx, r9
0x140085a31  call    cs:__imp_ExAllocatePool2
0x140085a38  nop     dword ptr [rax+rax+00h]
0x140085a3d  mov     rdi, rax
0x140085a40  test    rax, rax
0x140085a43  jnz     short loc_140085A68
0x140085a45  mov     r8d, 36Fh
0x140085a4b  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x140085a52  lea     rcx, aVidexovppcreat; "VidExoVppCreate"
0x140085a59  call    VidTraceErrorInternal0
0x140085a5e  mov     ebx, 0C000009Ah
0x140085a63  jmp     loc_140085C71
0x140085a68  mov     r12d, 48h ; 'H'
0x140085a6e  mov     [rax], ebp
0x140085a70  mov     r8d, r12d; Size
0x140085a73  lea     rcx, [rax+68h]; void *
0x140085a77  xor     edx, edx; Val
0x140085a79  call    memset
0x140085a7e  lea     rax, [rdi+90h]
0x140085a85  mov     r8d, r12d; Size
0x140085a88  lea     r15, [rdi+0B0h]
0x140085a8f  mov     [rax+8], rax
0x140085a93  mov     rcx, r15; void *
0x140085a96  mov     [rax], rax
0x140085a99  xor     edx, edx; Val
0x140085a9b  call    memset
0x140085aa0  lea     rax, [r15+28h]
0x140085aa4  mov     r8d, r12d; Size
0x140085aa7  lea     r13, [rdi+0F8h]
0x140085aae  mov     [rax+8], rax
0x140085ab2  mov     rcx, r13; void *
0x140085ab5  mov     [rax], rax
0x140085ab8  xor     edx, edx; Val
0x140085aba  call    memset
0x140085abf  lea     rax, [r13+28h]
0x140085ac3  xor     edx, edx; Val
0x140085ac5  lea     r12, [rdi+148h]
0x140085acc  mov     [rax+8], rax
0x140085ad0  mov     rcx, r12; void *
0x140085ad3  mov     [rax], rax
0x140085ad6  lea     r8d, [rdx+48h]; Size
0x140085ada  call    memset
0x140085adf  lea     rax, [r12+28h]
0x140085ae4  mov     r8, rsi; DeferredContext
0x140085ae7  lea     rcx, [rdi+8]; Dpc
0x140085aeb  mov     [rax+8], rax
0x140085aef  lea     rdx, VidExoVppInterceptDpcRoutine; DeferredRoutine
0x140085af6  mov     [rax], rax
0x140085af9  call    cs:__imp_KeInitializeDpc
0x140085b00  nop     dword ptr [rax+rax+00h]
0x140085b05  movups  xmm0, xmmword ptr [rbx]
0x140085b08  mov     edx, [rsp+88h+arg_10]
0x140085b0f  lea     r8, [rsp+88h+var_58]
0x140085b14  mov     rcx, [rsi+288h]
0x140085b1b  mov     r9d, ebp
0x140085b1e  movdqu  [rsp+88h+var_58], xmm0
0x140085b24  mov     [rsp+88h+var_68], 0
0x140085b2d  call    cs:__imp_WinHvCreateVp
0x140085b34  nop     dword ptr [rax+rax+00h]
0x140085b39  mov     ebx, eax
0x140085b3b  test    eax, eax
0x140085b3d  jns     short loc_140085B4A
0x140085b3f  mov     r8d, 386h
0x140085b45  jmp     loc_140085C4C
0x140085b4a  lea     rax, [rdi+50h]
0x140085b4e  mov     byte ptr [rdi+198h], 1
0x140085b55  lea     r9, [rdi+68h]
0x140085b59  mov     [rsp+88h+var_68], rax
0x140085b5e  xor     r8d, r8d
0x140085b61  mov     edx, ebp
0x140085b63  mov     rcx, rsi
0x140085b66  call    VidExoVppMapStatsPage
0x140085b6b  mov     ebx, eax
0x140085b6d  test    eax, eax
0x140085b6f  jns     short loc_140085B7C
0x140085b71  mov     r8d, 397h
0x140085b77  jmp     loc_140085C4C
0x140085b7c  lea     rax, [rdi+58h]
0x140085b80  mov     r14d, 1
0x140085b86  mov     r8d, r14d
0x140085b89  mov     [rsp+88h+var_68], rax
0x140085b8e  mov     r9, r15
0x140085b91  mov     edx, ebp
0x140085b93  mov     rcx, rsi
0x140085b96  call    VidExoVppMapStatsPage
0x140085b9b  mov     ebx, eax
0x140085b9d  test    eax, eax
0x140085b9f  jns     short loc_140085BAC
0x140085ba1  mov     r8d, 3A3h
0x140085ba7  jmp     loc_140085C4C
0x140085bac  lea     rax, [rdi+140h]
0x140085bb3  xor     r9d, r9d
0x140085bb6  mov     r8, r13
0x140085bb9  mov     [rsp+88h+var_60], rax
0x140085bbe  mov     edx, ebp
0x140085bc0  mov     rcx, rsi
0x140085bc3  call    VidExoVppMapStatePage
0x140085bc8  mov     ebx, eax
0x140085bca  test    eax, eax
0x140085bcc  jns     short loc_140085BD6
0x140085bce  mov     r8d, 3B3h
0x140085bd4  jmp     short loc_140085C4C
0x140085bd6  lea     rax, [rdi+190h]
0x140085bdd  mov     r9d, r14d
0x140085be0  mov     r8, r12
0x140085be3  mov     [rsp+88h+var_60], rax
0x140085be8  mov     edx, ebp
0x140085bea  mov     rcx, rsi
0x140085bed  call    VidExoVppMapStatePage
0x140085bf2  mov     ebx, eax
0x140085bf4  test    eax, eax
0x140085bf6  jns     short loc_140085C00
0x140085bf8  mov     r8d, 3C0h
0x140085bfe  jmp     short loc_140085C4C
0x140085c00  mov     rcx, [rsp+88h+arg_20]
0x140085c08  mov     rax, [rcx]
0x140085c0b  mov     [rdi+48h], rax
0x140085c0f  mov     rax, cs:VidDeviceExtension
0x140085c16  mov     qword ptr [rcx], 0
0x140085c1d  mov     eax, [rax+288h]
0x140085c23  test    al, 20h
0x140085c25  jz      short loc_140085C9B
0x140085c27  mov     r8, [rdi+48h]
0x140085c2b  mov     edx, ebp
0x140085c2d  mov     rcx, [rsi+288h]
0x140085c34  call    cs:__imp_WinHvSetDispatchNotificationEvent
0x140085c3b  nop     dword ptr [rax+rax+00h]
0x140085c40  mov     ebx, eax
0x140085c42  test    eax, eax
0x140085c44  jns     short loc_140085C9B
0x140085c46  mov     r8d, 3D2h
0x140085c4c  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x140085c53  lea     rcx, aVidexovppcreat; "VidExoVppCreate"
0x140085c5a  call    VidTraceErrorInternal0
0x140085c5f  xor     r8d, r8d
0x140085c62  mov     rdx, rdi
0x140085c65  mov     rcx, rsi
0x140085c68  call    VidExoVppDelete
0x140085c6d  test    ebx, ebx
0x140085c6f  jns     short loc_140085CA8
0x140085c71  lea     rax, [rsi+290h]
0x140085c78  mov     r9d, ebx
0x140085c7b  mov     r8d, 3E2h
0x140085c81  mov     [rsp+88h+var_68], rax
0x140085c86  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x140085c8d  lea     rcx, aVidexovppcreat; "VidExoVppCreate"
0x140085c94  call    VidTraceErrorStatusPartitionInternal0
0x140085c99  jmp     short loc_140085CA8
0x140085c9b  mov     rax, [rsp+88h+arg_28]
0x140085ca3  xor     ebx, ebx
0x140085ca5  mov     [rax], rdi
0x140085ca8  mov     eax, ebx
0x140085caa  add     rsp, 48h
0x140085cae  pop     r15
0x140085cb0  pop     r14
0x140085cb2  pop     r13
0x140085cb4  pop     r12
0x140085cb6  pop     rdi
0x140085cb7  pop     rsi
0x140085cb8  pop     rbp
0x140085cb9  pop     rbx
0x140085cba  retn
```
