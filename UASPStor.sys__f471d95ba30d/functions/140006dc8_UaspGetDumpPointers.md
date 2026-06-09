# UaspGetDumpPointers

- ea: `0x140006dc8`
- end: `0x140006fff`
- name: `UaspGetDumpPointers`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140002320`

## callees

- `0x1400052b8`
- `0x140005d64`
- `0x1400069a0`
- `0x140006dc8`
- `0x14000d7f0`
- `0x14000dc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006fc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006fc4`

## pseudocode

```c
void __fastcall UaspGetDumpPointers(__int64 a1, __int64 a2)
{
  wchar_t *v2; // rbx
  char v5; // di
  __int64 v6; // rcx
  __int64 Pool; // rax
  __int64 v8; // rsi
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax

  v2 = *(wchar_t **)(a2 + 24);
  memset(v2, 0, 0x70u);
  *(_DWORD *)v2 = 7340288;
  *((_DWORD *)v2 + 20) = 81920;
  *((_DWORD *)v2 + 14) = 0x10000;
  *((_DWORD *)v2 + 21) = -1;
  *((_DWORD *)v2 + 22) = 3;
  v5 = 1;
  *((_DWORD *)v2 + 26) = 16843009;
  RtlStringCbPrintfW(v2 + 2, 0x1Eu, L"uaspstor.sys");
  Pool = UaspAllocatePool(v6, 1104);
  v8 = Pool;
  if ( !Pool )
    goto LABEL_5;
  *(_DWORD *)Pool = 72352848;
  v9 = Pool + 80;
  v10 = Pool + 56;
  *(_DWORD *)(Pool + 4) = *(_DWORD *)(a1 + 992);
  v11 = *(_QWORD *)(a1 + 1104);
  *(_OWORD *)(Pool + 80) = *(_OWORD *)v11;
  *(_QWORD *)(Pool + 96) = *(_QWORD *)(v11 + 16);
  v12 = *(_QWORD *)(a1 + 1096);
  *(_OWORD *)v10 = *(_OWORD *)v12;
  *(_QWORD *)(v10 + 16) = *(_QWORD *)(v12 + 16);
  v13 = *(_QWORD *)(a1 + 80);
  *(_OWORD *)(v8 + 8) = *(_OWORD *)v13;
  *(_QWORD *)(v8 + 24) = *(_QWORD *)(v13 + 16);
  v14 = *(_QWORD *)(a1 + 88);
  *(_OWORD *)(v8 + 32) = *(_OWORD *)v14;
  *(_QWORD *)(v8 + 48) = *(_QWORD *)(v14 + 16);
  *(_QWORD *)(v8 + 88) = v9;
  *(_QWORD *)(v8 + 64) = v10;
  *(_QWORD *)(v8 + 16) = v8 + 8;
  *(_QWORD *)(v8 + 40) = v8 + 32;
  *(_BYTE *)(v8 + 1097) = *(_BYTE *)(a1 + 985);
  *(_BYTE *)(v8 + 1098) = *(_BYTE *)(a1 + 986);
  *(_DWORD *)(v8 + 1088) = 3120;
  if ( (int)UaspInternalDeviceIoControl(*(PDEVICE_OBJECT *)(a1 + 16), v8 + 1008, 88) < 0 )
  {
    ExFreePoolWithTag((PVOID)v8, 0);
LABEL_5:
    v5 = 4;
    goto LABEL_6;
  }
  *((_QWORD *)v2 + 8) = v8;
LABEL_6:
  *(_BYTE *)(a2 + 3) = v5;
}

```

## disassembly

```asm
0x140006dc8  mov     [rsp-8+arg_10], rbx
0x140006dcd  push    rbp
0x140006dce  push    rsi
0x140006dcf  push    rdi
0x140006dd0  push    r12
0x140006dd2  push    r13
0x140006dd4  push    r14
0x140006dd6  push    r15
0x140006dd8  lea     rbp, [rsp-27h]
0x140006ddd  sub     rsp, 90h
0x140006de4  mov     rax, cs:__security_cookie
0x140006deb  xor     rax, rsp
0x140006dee  mov     [rbp+57h+var_40], rax
0x140006df2  mov     rbx, [rdx+18h]
0x140006df6  xorps   xmm0, xmm0
0x140006df9  xor     eax, eax
0x140006dfb  mov     r14, rdx
0x140006dfe  mov     r15, rcx
0x140006e01  xor     edx, edx; Val
0x140006e03  movups  [rbp+57h+var_80], xmm0
0x140006e07  mov     rcx, rbx; void *
0x140006e0a  lea     r8d, [rax+70h]; Size
0x140006e0e  movups  [rbp+57h+var_80+0Ch], xmm0
0x140006e12  call    memset
0x140006e17  mov     r12d, 14000h
0x140006e1d  mov     dword ptr [rbx], 700100h
0x140006e23  lea     rcx, [rbx+4]; pszDest
0x140006e27  mov     [rbx+50h], r12d
0x140006e2b  lea     r8, aUaspstorSys; "uaspstor.sys"
0x140006e32  mov     dword ptr [rbx+38h], 10000h
0x140006e39  mov     edx, 1Eh; cbDest
0x140006e3e  mov     dword ptr [rbx+54h], 0FFFFFFFFh
0x140006e45  mov     dword ptr [rbx+58h], 3
0x140006e4c  mov     dil, 1
0x140006e4f  mov     dword ptr [rbx+68h], 1010101h
0x140006e56  call    RtlStringCbPrintfW
0x140006e5b  mov     edx, 450h
0x140006e60  call    UaspAllocatePool
0x140006e65  mov     rsi, rax
0x140006e68  test    rax, rax
0x140006e6b  jz      loc_140006FD0
0x140006e71  mov     dword ptr [rax], 4500450h
0x140006e77  lea     r9, [rax+50h]
0x140006e7b  mov     ecx, [r15+3E0h]
0x140006e82  lea     r8, [rax+38h]
0x140006e86  mov     [rax+4], ecx
0x140006e89  lea     rdx, [rsi+8]
0x140006e8d  mov     rcx, [r15+450h]
0x140006e94  mov     [rsp+0C0h+var_98], 58h ; 'X'; int
0x140006e9c  movups  xmm0, xmmword ptr [rcx]
0x140006e9f  movups  xmmword ptr [r9], xmm0
0x140006ea3  movsd   xmm1, qword ptr [rcx+10h]
0x140006ea8  lea     rcx, [rsi+20h]
0x140006eac  movsd   qword ptr [r9+10h], xmm1
0x140006eb2  mov     rax, [r15+448h]
0x140006eb9  movups  xmm0, xmmword ptr [rax]
0x140006ebc  movups  xmmword ptr [r8], xmm0
0x140006ec0  movsd   xmm1, qword ptr [rax+10h]
0x140006ec5  movsd   qword ptr [r8+10h], xmm1
0x140006ecb  mov     rax, [r15+50h]
0x140006ecf  movups  xmm0, xmmword ptr [rax]
0x140006ed2  movups  xmmword ptr [rdx], xmm0
0x140006ed5  movsd   xmm1, qword ptr [rax+10h]
0x140006eda  movsd   qword ptr [rdx+10h], xmm1
0x140006edf  mov     rax, [r15+58h]
0x140006ee3  movups  xmm0, xmmword ptr [rax]
0x140006ee6  movups  xmmword ptr [rcx], xmm0
0x140006ee9  movsd   xmm1, qword ptr [rax+10h]
0x140006eee  xorps   xmm0, xmm0
0x140006ef1  movsd   qword ptr [rcx+10h], xmm1
0x140006ef6  mov     [rsi+58h], r9
0x140006efa  mov     r9d, 20h ; ' '
0x140006f00  mov     [rsi+40h], r8
0x140006f04  lea     r8, [rbp+57h+var_80]
0x140006f08  mov     [rsi+10h], rdx
0x140006f0c  mov     edx, 491404h
0x140006f11  mov     [rsi+28h], rcx
0x140006f15  mov     al, [r15+3D9h]
0x140006f1c  mov     [rsi+449h], al
0x140006f22  mov     al, [r15+3DAh]
0x140006f29  mov     [rsi+44Ah], al
0x140006f2f  mov     rax, [r15+450h]
0x140006f36  movups  [rbp+57h+var_60], xmm0
0x140006f3a  movups  [rbp+57h+var_50], xmm0
0x140006f3e  mov     cl, [rax+2]
0x140006f41  mov     rax, [r15+448h]
0x140006f48  mov     byte ptr [rbp+57h+var_60], cl
0x140006f4b  mov     dword ptr [rbp+57h+var_60+4], r12d
0x140006f4f  mov     cl, [rax+2]
0x140006f52  mov     rax, [r15+50h]
0x140006f56  mov     byte ptr [rbp+57h+var_60+8], cl
0x140006f59  mov     dword ptr [rbp+57h+var_60+0Ch], r12d
0x140006f5d  mov     cl, [rax+2]
0x140006f60  mov     rax, [r15+58h]
0x140006f64  mov     byte ptr [rbp+57h+var_50], cl
0x140006f67  mov     dword ptr [rbp+57h+var_50+4], r12d
0x140006f6b  mov     cl, [rax+2]
0x140006f6e  lea     rax, [rbp+57h+var_60]
0x140006f72  movups  [rbp+57h+var_80], xmm0
0x140006f76  mov     qword ptr [rbp+57h+var_80+8], rax
0x140006f7a  lea     rax, [rsi+3F0h]
0x140006f81  movups  [rbp+57h+var_70], xmm0
0x140006f85  mov     byte ptr [rbp+57h+var_50+8], cl
0x140006f88  mov     dword ptr [rbp+57h+var_50+0Ch], r12d
0x140006f8c  mov     dword ptr [rbp+57h+var_80], 4
0x140006f93  mov     word ptr [rbp+57h+var_70], 1
0x140006f99  mov     byte ptr [rbp+57h+var_70+2], dil
0x140006f9d  mov     dword ptr [rsi+440h], 0C30h
0x140006fa7  mov     rcx, [r15+10h]; DeviceObject
0x140006fab  mov     [rsp+0C0h+var_A0], rax; __int64
0x140006fb0  call    UaspInternalDeviceIoControl
0x140006fb5  test    eax, eax
0x140006fb7  js      short loc_140006FBF
0x140006fb9  mov     [rbx+40h], rsi
0x140006fbd  jmp     short loc_140006FD3
0x140006fbf  xor     edx, edx; Tag
0x140006fc1  mov     rcx, rsi; P
0x140006fc4  call    cs:__imp_ExFreePoolWithTag
0x140006fcb  nop     dword ptr [rax+rax+00h]
0x140006fd0  mov     dil, 4
0x140006fd3  mov     [r14+3], dil
0x140006fd7  mov     rcx, [rbp+57h+var_40]
0x140006fdb  xor     rcx, rsp; StackCookie
0x140006fde  call    __security_check_cookie
0x140006fe3  mov     rbx, [rsp+0C0h+arg_10]
0x140006feb  add     rsp, 90h
0x140006ff2  pop     r15
0x140006ff4  pop     r14
0x140006ff6  pop     r13
0x140006ff8  pop     r12
0x140006ffa  pop     rdi
0x140006ffb  pop     rsi
0x140006ffc  pop     rbp
0x140006ffd  retn
```
