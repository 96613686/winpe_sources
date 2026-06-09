# FwppGetCompartmentBfeState

- ea: `0x180009e58`
- end: `0x180009fe2`
- name: `FwppGetCompartmentBfeState`
- size: `394`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009e00`
- `0x180052440`
- `0x180067a78`
- `0x180067c98`

## callees

- `0x180008480`
- `0x18000891c`
- `0x180009e58`
- `0x18000e1c4`
- `0x1800205c0`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!KeIsExecutingDpc` at `0x180009e79`
- `ntoskrnl!KeIsExecutingDpc` at `0x180009e79`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x180009e99`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x180009e99`

## pseudocode

```c
__int64 __fastcall FwppGetCompartmentBfeState(__int64 a1, int a2)
{
  int v3; // r8d
  unsigned int ThreadObjectCompartmentId; // edi
  __int64 v5; // rbx
  __int64 v6; // rsi
  const void *v7; // r13
  __int64 v8; // rbp
  char *v9; // r14
  __int64 v10; // r15
  __int64 v11; // rcx
  char *v12; // rax
  void *v14; // [rsp+90h] [rbp+18h] BYREF
  PVOID v15; // [rsp+98h] [rbp+20h] BYREF

  v14 = 0;
  if ( (unsigned int)KeIsExecutingDpc() )
    ThreadObjectCompartmentId = 1;
  else
    ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
  v5 = (unsigned int)xmmword_180048880;
  if ( ThreadObjectCompartmentId < (unsigned int)xmmword_180048880 )
    goto LABEL_12;
  v6 = 0;
  if ( a2 )
  {
    v7 = (const void *)*((_QWORD *)&xmmword_180048880 + 1);
    v8 = ThreadObjectCompartmentId + 5;
    v15 = (PVOID)*((_QWORD *)&xmmword_180048880 + 1);
    if ( WfpPoolAllocNonPaged(40 * v8, 1886418758, &v14) )
      goto LABEL_13;
    v9 = (char *)v14;
    memset(v14, 0, 40 * v8);
    v10 = (unsigned int)v5;
    memmove(v9, v7, 40 * v5);
    while ( (unsigned int)v5 < (unsigned int)v8 )
    {
      v11 = 5 * v10;
      LODWORD(v5) = v5 + 1;
      *(_DWORD *)&v9[8 * v11] = 0;
      v12 = &v9[40 * v10++ + 8];
      *((_QWORD *)v12 + 1) = v12;
      *(_QWORD *)v12 = v12;
      *(_QWORD *)&v9[8 * v11 + 24] = 0;
    }
    *((_QWORD *)&xmmword_180048880 + 1) = v9;
    LODWORD(xmmword_180048880) = ThreadObjectCompartmentId + 5;
    WfpNamedPoolFree(v11, &v15);
  }
  if ( ThreadObjectCompartmentId < (unsigned int)xmmword_180048880 )
LABEL_12:
    v6 = *((_QWORD *)&xmmword_180048880 + 1) + 40LL * ThreadObjectCompartmentId;
LABEL_13:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    WPP_SF_DDlq(
      WPP_GLOBAL_Control->AttachedDevice,
      xmmword_180048880,
      v3,
      ThreadObjectCompartmentId,
      xmmword_180048880,
      a2,
      v6);
  }
  return v6;
}

```

## disassembly

```asm
0x180009e58  mov     rax, rsp
0x180009e5b  mov     [rax+8], rbx
0x180009e5f  push    rbp
0x180009e60  push    rsi
0x180009e61  push    rdi
0x180009e62  push    r12
0x180009e64  push    r13
0x180009e66  push    r14
0x180009e68  push    r15
0x180009e6a  sub     rsp, 40h
0x180009e6e  mov     r12d, edx
0x180009e71  mov     qword ptr [rax+18h], 0
0x180009e79  call    cs:__imp_KeIsExecutingDpc
0x180009e80  nop     dword ptr [rax+rax+00h]
0x180009e85  test    eax, eax
0x180009e87  jz      short loc_180009E90
0x180009e89  mov     edi, 1
0x180009e8e  jmp     short loc_180009EA7
0x180009e90  mov     rcx, gs:188h
0x180009e99  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x180009ea0  nop     dword ptr [rax+rax+00h]
0x180009ea5  mov     edi, eax
0x180009ea7  mov     ebx, dword ptr cs:xmmword_180048880
0x180009ead  cmp     edi, ebx
0x180009eaf  jb      loc_180009F73
0x180009eb5  xor     esi, esi
0x180009eb7  test    r12d, r12d
0x180009eba  jz      loc_180009F6B
0x180009ec0  mov     r13, qword ptr cs:xmmword_180048880+8
0x180009ec7  lea     ebp, [rdi+5]
0x180009eca  lea     r14, ds:0[rbp*4]
0x180009ed2  mov     [rsp+78h+arg_18], r13
0x180009eda  add     r14, rbp
0x180009edd  lea     r8, [rsp+78h+arg_10]
0x180009ee5  shl     r14, 3
0x180009ee9  mov     edx, 70707746h
0x180009eee  mov     rcx, r14
0x180009ef1  call    WfpPoolAllocNonPaged
0x180009ef6  test    rax, rax
0x180009ef9  jnz     loc_180009F84
0x180009eff  mov     r8, r14; Size
0x180009f02  xor     edx, edx; Val
0x180009f04  mov     r14, [rsp+78h+arg_10]
0x180009f0c  mov     rcx, r14; void *
0x180009f0f  call    memset
0x180009f14  lea     r8, [rbx+rbx*4]
0x180009f18  mov     rdx, r13; Src
0x180009f1b  shl     r8, 3; Size
0x180009f1f  mov     rcx, r14; void *
0x180009f22  mov     r15d, ebx
0x180009f25  call    memmove
0x180009f2a  jmp     short loc_180009F4D
0x180009f2c  lea     rcx, [r15+r15*4]
0x180009f30  inc     ebx
0x180009f32  mov     [r14+rcx*8], esi
0x180009f36  lea     rax, [r14+8]
0x180009f3a  lea     rax, [rax+rcx*8]
0x180009f3e  inc     r15
0x180009f41  mov     [rax+8], rax
0x180009f45  mov     [rax], rax
0x180009f48  mov     [r14+rcx*8+18h], rsi
0x180009f4d  cmp     ebx, ebp
0x180009f4f  jb      short loc_180009F2C
0x180009f51  lea     rdx, [rsp+78h+arg_18]
0x180009f59  mov     qword ptr cs:xmmword_180048880+8, r14
0x180009f60  mov     dword ptr cs:xmmword_180048880, ebp
0x180009f66  call    WfpNamedPoolFree
0x180009f6b  cmp     edi, dword ptr cs:xmmword_180048880
0x180009f71  jnb     short loc_180009F84
0x180009f73  mov     eax, edi
0x180009f75  lea     rcx, [rax+rax*4]
0x180009f79  mov     rax, qword ptr cs:xmmword_180048880+8
0x180009f80  lea     rsi, [rax+rcx*8]
0x180009f84  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f8b  lea     rax, WPP_GLOBAL_Control
0x180009f92  cmp     rcx, rax
0x180009f95  jz      short loc_180009FC6
0x180009f97  cmp     byte ptr [rcx+29h], 4
0x180009f9b  jb      short loc_180009FC6
0x180009f9d  test    dword ptr [rcx+2Ch], 100h
0x180009fa4  jz      short loc_180009FC6
0x180009fa6  mov     edx, dword ptr cs:xmmword_180048880
0x180009fac  mov     r9d, edi
0x180009faf  mov     rcx, [rcx+18h]
0x180009fb3  mov     [rsp+78h+var_48], rsi
0x180009fb8  mov     [rsp+78h+var_50], r12d
0x180009fbd  mov     [rsp+78h+var_58], edx
0x180009fc1  call    WPP_SF_DDlq
0x180009fc6  mov     rbx, [rsp+78h+arg_0]
0x180009fce  mov     rax, rsi
0x180009fd1  add     rsp, 40h
0x180009fd5  pop     r15
0x180009fd7  pop     r14
0x180009fd9  pop     r13
0x180009fdb  pop     r12
0x180009fdd  pop     rdi
0x180009fde  pop     rsi
0x180009fdf  pop     rbp
0x180009fe0  retn
```
