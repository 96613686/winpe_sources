# MpFsCtlQueryProcessInformation

- ea: `0x140080e40`
- end: `0x14008103b`
- name: `MpFsCtlQueryProcessInformation`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400448f0`

## callees

- `0x14000da88`
- `0x140011900`
- `0x140030060`
- `0x14003a1b0`
- `0x140064160`
- `0x140080e40`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140080e87`
- `ntoskrnl!ProbeForRead` at `0x140080e87`
- `ntoskrnl!ProbeForWrite` at `0x140080fd9`
- `ntoskrnl!ProbeForWrite` at `0x140080fd9`
- `ntoskrnl!IoGetCurrentProcess` at `0x140080ea7`
- `ntoskrnl!IoGetCurrentProcess` at `0x140080ea7`

## pseudocode

```c
__int64 __fastcall MpFsCtlQueryProcessInformation(__int64 a1)
{
  void *v2; // rbx
  struct _KPROCESS *CurrentProcess; // rax
  __int64 result; // rax
  volatile signed __int32 *v5; // r15
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // r9d
  int v9; // r10d
  __int64 v10; // r11
  __int64 v11; // rdi
  int v12; // ecx
  unsigned int v13; // r12d
  __int64 v14; // rax
  volatile void *v15; // rdi
  __int128 Src; // [rsp+58h] [rbp-50h] BYREF
  __int128 v17; // [rsp+68h] [rbp-40h]
  __int128 v18; // [rsp+78h] [rbp-30h]
  volatile signed __int32 *v19; // [rsp+B8h] [rbp+10h] BYREF

  Src = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  ProbeForRead(*(volatile void **)(*(_QWORD *)(a1 + 16) + 48LL), 8u, 4u);
  v2 = (void *)*(unsigned int *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 48LL) + 4LL);
  if ( (_DWORD)v2 == -1 )
  {
    CurrentProcess = IoGetCurrentProcess();
    result = MpGetProcessContextByObject(CurrentProcess, &v19);
  }
  else
  {
    result = MpGetProcessContextById(v2, &v19);
  }
  if ( (int)result >= 0 )
  {
    v5 = v19;
    v6 = *((unsigned int *)v19 + 13);
    DWORD1(Src) = *((_DWORD *)v19 + 13);
    v7 = *((unsigned int *)v19 + 14);
    DWORD2(Src) = *((_DWORD *)v19 + 14);
    v8 = *((_DWORD *)v19 + 24);
    HIDWORD(Src) = v8;
    v9 = *((_DWORD *)v19 + 25);
    LODWORD(v17) = v9;
    v10 = *((_QWORD *)v19 + 8);
    *((_QWORD *)&v17 + 1) = v10;
    v11 = *((_QWORD *)v19 + 9);
    *(_QWORD *)&v18 = v11;
    DWORD2(v18) = *((_DWORD *)v19 + 15);
    v12 = *((_DWORD *)v19 + 72);
    BYTE12(v18) = (v12 & 8) != 0;
    BYTE13(v18) = (v12 & 0x10) != 0;
    BYTE14(v18) = (v12 & 0x20) != 0;
    v13 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
    if ( v13 > 0x30 )
      v13 = 48;
    LODWORD(Src) = v13;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      _mm_lfence();
      WPP_SF_dDDddii(WPP_GLOBAL_Control->AttachedDevice, v6, v7, (unsigned int)v2, v6, v7, v8, v9, v10, v11);
    }
    v14 = *(_QWORD *)(a1 + 16);
    v15 = *(volatile void **)(v14 + 56);
    ProbeForWrite(v15, *(unsigned int *)(v14 + 24), 4u);
    memmove((void *)v15, &Src, v13);
    *(_QWORD *)(a1 + 32) = v13;
    MpReleaseProcessContext(v5);
    return 0;
  }
  else
  {
    _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x140080e40  mov     rax, rsp
0x140080e43  mov     [rax+8], rbx
0x140080e47  mov     [rax+18h], rsi
0x140080e4b  mov     [rax+20h], rdi
0x140080e4f  mov     [rax+10h], rdx
0x140080e53  push    r12
0x140080e55  push    r14
0x140080e57  push    r15
0x140080e59  sub     rsp, 90h
0x140080e60  mov     r14, rcx
0x140080e63  xorps   xmm0, xmm0
0x140080e66  movups  xmmword ptr [rax-50h], xmm0
0x140080e6a  movups  xmmword ptr [rax-40h], xmm0
0x140080e6e  movups  xmmword ptr [rax-30h], xmm0
0x140080e72  xor     esi, esi
0x140080e74  mov     [rax+10h], rsi
0x140080e78  mov     rcx, [rcx+10h]
0x140080e7c  lea     edx, [rsi+8]; Length
0x140080e7f  lea     r8d, [rsi+4]; Alignment
0x140080e83  mov     rcx, [rcx+30h]; Address
0x140080e87  call    cs:__imp_ProbeForRead
0x140080e8e  nop     dword ptr [rax+rax+00h]
0x140080e93  mov     rax, [r14+10h]
0x140080e97  mov     rcx, [rax+30h]
0x140080e9b  mov     ebx, [rcx+4]
0x140080e9e  mov     [rsp+0A8h+var_54], ebx
0x140080ea2  cmp     ebx, 0FFFFFFFFh
0x140080ea5  jnz     short loc_140080EC5
0x140080ea7  call    cs:__imp_IoGetCurrentProcess
0x140080eae  nop     dword ptr [rax+rax+00h]
0x140080eb3  mov     rcx, rax; Process
0x140080eb6  lea     rdx, [rsp+0A8h+arg_8]
0x140080ebe  call    MpGetProcessContextByObject
0x140080ec3  jmp     short loc_140080ED5
0x140080ec5  mov     rcx, rbx
0x140080ec8  lea     rdx, [rsp+0A8h+arg_8]
0x140080ed0  call    MpGetProcessContextById
0x140080ed5  test    eax, eax
0x140080ed7  jns     short loc_140080EE1
0x140080ed9  lfence
0x140080edc  jmp     loc_14008101C
0x140080ee1  mov     r15, [rsp+0A8h+arg_8]
0x140080ee9  mov     edx, [r15+34h]
0x140080eed  mov     [rsp+0A8h+var_4C], edx
0x140080ef1  mov     r8d, [r15+38h]
0x140080ef5  mov     [rsp+0A8h+var_48], r8d
0x140080efa  mov     r9d, [r15+60h]
0x140080efe  mov     [rsp+0A8h+var_44], r9d
0x140080f03  mov     r10d, [r15+64h]
0x140080f07  mov     [rsp+0A8h+var_40], r10d
0x140080f0c  mov     r11, [r15+40h]
0x140080f10  mov     [rsp+0A8h+var_38], r11
0x140080f15  mov     rdi, [r15+48h]
0x140080f19  mov     [rsp+0A8h+var_30], rdi
0x140080f1e  mov     eax, [r15+3Ch]
0x140080f22  mov     [rsp+0A8h+var_28], eax
0x140080f29  mov     ecx, [r15+120h]
0x140080f30  mov     al, cl
0x140080f32  shr     al, 3
0x140080f35  mov     r12b, 1
0x140080f38  and     al, r12b
0x140080f3b  mov     [rsp+0A8h+var_24], al
0x140080f42  mov     al, cl
0x140080f44  shr     al, 4
0x140080f47  and     al, r12b
0x140080f4a  mov     [rsp+0A8h+var_23], al
0x140080f51  shr     cl, 5
0x140080f54  and     cl, r12b
0x140080f57  mov     [rsp+0A8h+var_22], cl
0x140080f5e  mov     rax, [r14+10h]
0x140080f62  mov     r12d, [rax+18h]
0x140080f66  mov     eax, 30h ; '0'
0x140080f6b  cmp     r12d, eax
0x140080f6e  cmova   r12d, eax
0x140080f72  mov     [rsp+0A8h+Src], r12d
0x140080f77  lea     rcx, WPP_GLOBAL_Control
0x140080f7e  mov     rax, cs:WPP_GLOBAL_Control
0x140080f85  cmp     rax, rcx
0x140080f88  jz      short loc_140080FC5
0x140080f8a  mov     eax, [rax+2Ch]
0x140080f8d  test    al, 4
0x140080f8f  jz      short loc_140080FC5
0x140080f91  lfence
0x140080f94  mov     [rsp+0A8h+var_60], rdi
0x140080f99  mov     [rsp+0A8h+var_68], r11
0x140080f9e  mov     [rsp+0A8h+var_70], r10d
0x140080fa3  mov     [rsp+0A8h+var_78], r9d
0x140080fa8  mov     [rsp+0A8h+var_80], r8d
0x140080fad  mov     [rsp+0A8h+var_88], edx
0x140080fb1  mov     r9d, ebx
0x140080fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x140080fbb  mov     rcx, [rcx+18h]
0x140080fbf  call    WPP_SF_dDDddii
0x140080fc4  nop
0x140080fc5  mov     rax, [r14+10h]
0x140080fc9  mov     rdi, [rax+38h]
0x140080fcd  mov     edx, [rax+18h]; Length
0x140080fd0  mov     r8d, 4; Alignment
0x140080fd6  mov     rcx, rdi; Address
0x140080fd9  call    cs:__imp_ProbeForWrite
0x140080fe0  nop     dword ptr [rax+rax+00h]
0x140080fe5  mov     ebx, r12d
0x140080fe8  mov     r8d, r12d; Size
0x140080feb  lea     rdx, [rsp+0A8h+Src]; Src
0x140080ff0  mov     rcx, rdi; void *
0x140080ff3  call    memmove
0x140080ff8  mov     [r14+20h], rbx
0x140080ffc  mov     [rsp+0A8h+var_58], esi
0x140081000  jmp     short loc_140081010
0x140081002  mov     esi, eax
0x140081004  mov     [rsp+0A8h+var_58], eax
0x140081008  mov     r15, [rsp+0A8h+arg_8]
0x140081010  mov     rcx, r15
0x140081013  call    MpReleaseProcessContext
0x140081018  mov     eax, esi
0x14008101a  jmp     short $+2
0x14008101c  lea     r11, [rsp+0A8h+var_18]
0x140081024  mov     rbx, [r11+20h]
0x140081028  mov     rsi, [r11+30h]
0x14008102c  mov     rdi, [r11+38h]
0x140081030  mov     rsp, r11
0x140081033  pop     r15
0x140081035  pop     r14
0x140081037  pop     r12
0x140081039  retn
```
