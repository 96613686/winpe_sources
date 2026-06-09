# DrainCompletionNode

- ea: `0x1800188d0`
- end: `0x180018b14`
- name: `DrainCompletionNode`
- size: `580`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800143a0`
- `0x180018690`

## callees

- `0x1800188d0`
- `0x180018b20`
- `0x18001f0a0`
- `0x180024800`
- `0x1800248e0`
- `0x180024c40`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1800189b6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1800189b6`
- `ntoskrnl!ObfDereferenceObject` at `0x180018ac9`
- `ntoskrnl!ObfDereferenceObject` at `0x180018ac9`
- `ntoskrnl!ObfReferenceObject` at `0x1800189a3`
- `ntoskrnl!ObfReferenceObject` at `0x1800189a3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180018ade`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180018ade`

## string_xrefs

- `0x180018a73`: `DrainCompletionNode`

## pseudocode

```c
void __fastcall DrainCompletionNode(__int64 a1, __int64 a2, struct _KLOCK_QUEUE_HANDLE *a3)
{
  __int64 v6; // rax
  void *v7; // rbx
  __int128 v8; // xmm1
  __int128 v9; // xmm2
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  char v15; // di
  PCHAR IrpName; // rax
  __int128 v17; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v18; // [rsp+50h] [rbp-B0h]
  __int128 v19; // [rsp+60h] [rbp-A0h]
  _OWORD v20[33]; // [rsp+70h] [rbp-90h] BYREF

  memset(v20, 0, sizeof(v20));
  v6 = *(_QWORD *)(a2 + 32);
  v17 = 0;
  v18 = 0;
  v19 = 0;
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v6 + 40) + 4LL));
  *(_WORD *)(a2 + 120) |= 0x10u;
  v7 = *(void **)(a2 + 56);
  v8 = *(_OWORD *)(a2 + 16);
  v9 = *(_OWORD *)(a2 + 48);
  v20[0] = *(_OWORD *)a2;
  v10 = *(_OWORD *)(a2 + 32);
  v20[1] = v8;
  v11 = *(_OWORD *)(a2 + 80);
  v20[2] = v10;
  v12 = *(_OWORD *)(a2 + 64);
  v20[5] = v11;
  v13 = *(_OWORD *)(a2 + 112);
  v20[4] = v12;
  v14 = *(_OWORD *)(a2 + 96);
  v20[3] = v9;
  v20[6] = v14;
  v20[7] = v13;
  if ( v7 )
  {
    if ( BYTE4(v20[3]) == 2 )
      v7 = 0;
    else
      ObfReferenceObject(v7);
  }
  *(_QWORD *)(a2 + 64) = 0;
  KeReleaseInStackQueuedSpinLock(a3);
  if ( (BYTE8(v20[7]) & 0x40) == 0 )
  {
    *(_QWORD *)((char *)&v20[8] + 4) = 0;
    memset((char *)&v20[8] + 13, 0, 0xDBu);
    *(_QWORD *)((char *)&v20[22] + 12) = 0;
    DWORD1(v20[23]) = 0;
    memset((char *)&v20[24] + 4, 0, 0x8Cu);
    v15 = BYTE4(v20[3]);
    *((_QWORD *)&v20[23] + 1) = &v20[3];
    *((_QWORD *)&v17 + 1) = *(_QWORD *)(a1 + 72);
    *(_QWORD *)&v18 = *(_QWORD *)(a1 + 64);
    LODWORD(v20[8]) = 26276100;
    BYTE12(v20[8]) = BYTE4(v20[3]);
    LODWORD(v20[24]) = -1071906807;
    DWORD2(v20[22]) = 786432;
    LODWORD(v17) = 48;
    *((_QWORD *)&v18 + 1) = a1;
    v19 = (unsigned __int64)v7;
    if ( (byte_180040A41 & 0x20) != 0 )
    {
      IrpName = FltGetIrpName(BYTE4(v20[3]));
      McTemplateU0sddsp_EtwWriteTransfer(
        v20[0],
        (unsigned int)"2",
        (unsigned int)"DrainCompletionNode",
        v15,
        SBYTE5(v20[3]),
        (__int64)IrpName,
        v20[0]);
    }
    (*(void (__fastcall **)(char *, __int128 *, _QWORD, __int64))(*((_QWORD *)&v20[0] + 1) + 32LL))(
      (char *)&v20[22] + 8,
      &v17,
      *((_QWORD *)&v20[2] + 1),
      1);
  }
  if ( v7 )
    ObfDereferenceObject(v7);
  ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 56), 1u);
}

```

## disassembly

```asm
0x1800188d0  push    rbp
0x1800188d2  push    rbx
0x1800188d3  push    rsi
0x1800188d4  push    rdi
0x1800188d5  push    r12
0x1800188d7  push    r14
0x1800188d9  push    r15
0x1800188db  lea     rbp, [rsp-190h]
0x1800188e3  sub     rsp, 290h
0x1800188ea  mov     rax, cs:__security_cookie
0x1800188f1  xor     rax, rsp
0x1800188f4  mov     [rbp+1C0h+var_40], rax
0x1800188fb  mov     r14, r8
0x1800188fe  mov     rdi, rdx
0x180018901  mov     rsi, rcx
0x180018904  xor     edx, edx; Val
0x180018906  mov     r8d, 80h; Size
0x18001890c  lea     rcx, [rsp+2C0h+var_250]; void *
0x180018911  call    memset
0x180018916  xor     edx, edx; Val
0x180018918  lea     rcx, [rbp+1C0h+var_1D0]; void *
0x18001891c  mov     r8d, 190h; Size
0x180018922  call    memset
0x180018927  mov     rax, [rdi+20h]
0x18001892b  xorps   xmm0, xmm0
0x18001892e  movups  [rsp+2C0h+var_280], xmm0
0x180018933  movups  [rsp+2C0h+var_270], xmm0
0x180018938  movups  [rsp+2C0h+var_260], xmm0
0x18001893d  mov     rcx, [rax+28h]
0x180018941  lock inc dword ptr [rcx+4]
0x180018945  or      word ptr [rdi+78h], 10h
0x18001894a  xor     r15d, r15d
0x18001894d  movups  xmm0, xmmword ptr [rdi]
0x180018950  mov     rbx, [rdi+38h]
0x180018954  movups  xmm1, xmmword ptr [rdi+10h]
0x180018958  movups  xmm2, xmmword ptr [rdi+30h]
0x18001895c  movups  [rsp+2C0h+var_250], xmm0
0x180018961  movups  xmm0, xmmword ptr [rdi+20h]
0x180018965  movups  [rbp+1C0h+var_240], xmm1
0x180018969  movups  xmm1, xmmword ptr [rdi+50h]
0x18001896d  movups  [rbp+1C0h+var_230], xmm0
0x180018971  movups  xmm0, xmmword ptr [rdi+40h]
0x180018975  movups  [rbp+1C0h+var_200], xmm1
0x180018979  movups  xmm1, xmmword ptr [rdi+70h]
0x18001897d  movups  [rbp+1C0h+var_210], xmm0
0x180018981  movups  xmm0, xmmword ptr [rdi+60h]
0x180018985  movups  [rbp+1C0h+var_220], xmm2
0x180018989  movups  [rbp+1C0h+var_1F0], xmm0
0x18001898d  movups  [rbp+1C0h+var_1E0], xmm1
0x180018991  test    rbx, rbx
0x180018994  jz      short loc_1800189AF
0x180018996  cmp     byte ptr [rbp+1C0h+var_220+4], 2
0x18001899a  jz      loc_180018B0C
0x1800189a0  mov     rcx, rbx; Object
0x1800189a3  call    cs:__imp_ObfReferenceObject
0x1800189aa  nop     dword ptr [rax+rax+00h]
0x1800189af  mov     rcx, r14; LockHandle
0x1800189b2  mov     [rdi+40h], r15
0x1800189b6  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1800189bd  nop     dword ptr [rax+rax+00h]
0x1800189c2  test    byte ptr [rbp+1C0h+var_1E0+8], 40h
0x1800189c6  jnz     loc_180018AC1
0x1800189cc  xor     eax, eax
0x1800189ce  lea     rcx, [rbp+1C0h+var_1C3]; void *
0x1800189d2  xor     edx, edx; Val
0x1800189d4  mov     [rbp+1C0h+var_1CC], rax
0x1800189d8  mov     r8d, 0DBh; Size
0x1800189de  call    memset
0x1800189e3  xor     eax, eax
0x1800189e5  lea     rcx, [rbp+1C0h+var_CC]; void *
0x1800189ec  xor     edx, edx; Val
0x1800189ee  mov     [rbp+1C0h+var_E4], rax
0x1800189f5  mov     r8d, 8Ch; Size
0x1800189fb  mov     [rbp+1C0h+var_DC], eax
0x180018a01  call    memset
0x180018a06  test    cs:byte_180040A41, 20h
0x180018a0d  lea     rax, [rbp+1C0h+var_220]
0x180018a11  mov     rdi, qword ptr [rbp+1C0h+var_220+4]
0x180018a15  mov     [rbp+1C0h+var_D8], rax
0x180018a1c  mov     rax, [rsi+48h]
0x180018a20  mov     qword ptr [rsp+2C0h+var_280+8], rax
0x180018a25  mov     rax, [rsi+40h]
0x180018a29  mov     qword ptr [rsp+2C0h+var_270], rax
0x180018a2e  mov     [rbp+1C0h+var_1D0], 190F104h
0x180018a35  mov     [rbp+1C0h+var_1C4], dil
0x180018a39  mov     [rbp+1C0h+var_D0], 0C01C0009h
0x180018a43  mov     [rbp+1C0h+var_E8], 0C0000h
0x180018a4d  mov     dword ptr [rsp+2C0h+var_280], 30h ; '0'
0x180018a55  mov     qword ptr [rsp+2C0h+var_270+8], rsi
0x180018a5a  mov     qword ptr [rsp+2C0h+var_260], rbx
0x180018a5f  mov     qword ptr [rsp+2C0h+var_260+8], r15
0x180018a64  jz      short loc_180018A9D
0x180018a66  movzx   ecx, dil; IrpMajorCode
0x180018a6a  call    FltGetIrpName
0x180018a6f  movsx   edx, byte ptr [rbp+1C0h+var_220+5]
0x180018a73  lea     r8, aDraincompletio; "DrainCompletionNode"
0x180018a7a  mov     rcx, qword ptr [rsp+2C0h+var_250]
0x180018a7f  mov     [rsp+2C0h+var_290], rcx
0x180018a84  mov     [rsp+2C0h+var_298], rax
0x180018a89  mov     [rsp+2C0h+var_2A0], edx
0x180018a8d  lea     rdx, CompletionNodeSup_c965; "2"
0x180018a94  movsx   r9d, dil
0x180018a98  call    McTemplateU0sddsp_EtwWriteTransfer
0x180018a9d  mov     rax, qword ptr [rsp+2C0h+var_250+8]
0x180018aa2  lea     rdx, [rsp+2C0h+var_280]
0x180018aa7  mov     r8, qword ptr [rbp+1C0h+var_230+8]
0x180018aab  lea     rcx, [rbp+1C0h+var_E8]
0x180018ab2  mov     r9d, 1
0x180018ab8  mov     rax, [rax+20h]
0x180018abc  call    _guard_dispatch_icall
0x180018ac1  test    rbx, rbx
0x180018ac4  jz      short loc_180018AD5
0x180018ac6  mov     rcx, rbx; Object
0x180018ac9  call    cs:__imp_ObfDereferenceObject
0x180018ad0  nop     dword ptr [rax+rax+00h]
0x180018ad5  mov     rcx, [rsi+38h]; RunRef
0x180018ad9  mov     edx, 1; Count
0x180018ade  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x180018ae5  nop     dword ptr [rax+rax+00h]
0x180018aea  mov     rcx, [rbp+1C0h+var_40]
0x180018af1  xor     rcx, rsp; StackCookie
0x180018af4  call    __security_check_cookie
0x180018af9  add     rsp, 290h
0x180018b00  pop     r15
0x180018b02  pop     r14
0x180018b04  pop     r12
0x180018b06  pop     rdi
0x180018b07  pop     rsi
0x180018b08  pop     rbx
0x180018b09  pop     rbp
0x180018b0a  retn
0x180018b0c  mov     rbx, r15
0x180018b0f  jmp     loc_1800189AF
```
