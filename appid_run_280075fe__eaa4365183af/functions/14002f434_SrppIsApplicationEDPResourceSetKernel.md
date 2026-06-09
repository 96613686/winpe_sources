# SrppIsApplicationEDPResourceSetKernel

- ea: `0x14002f434`
- end: `0x14002f54d`
- name: `SrppIsApplicationEDPResourceSetKernel`
- size: `281`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14002bbf8`
- `0x14002f2a4`

## callees

- `0x140006a20`
- `0x14002f05c`
- `0x14002f21c`
- `0x14002f2f0`
- `0x14002f434`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x14002f4c9`
- `ntoskrnl!KeStackAttachProcess` at `0x14002f4c9`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002f4bf`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14002f509`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14002f509`

## pseudocode

```c
__int64 __fastcall SrppIsApplicationEDPResourceSetKernel(unsigned int a1, void *a2, _BYTE *a3)
{
  int v5; // edi
  int IsApplicationEDPResourceSet; // ebx
  __int64 v7; // r8
  int v9; // [rsp+20h] [rbp-88h]
  _OWORD v10[2]; // [rsp+28h] [rbp-80h] BYREF
  __int64 v11; // [rsp+48h] [rbp-60h]
  struct _KAPC_STATE ApcState; // [rsp+50h] [rbp-58h] BYREF

  memset(v10, 0, sizeof(v10));
  v11 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  if ( !a2 || !a3 )
    return 3221225485LL;
  v5 = 0;
  v9 = 0;
  *a3 = 0;
  IsApplicationEDPResourceSet = SrppMapFileImage(a2, (__int64)v10);
  if ( IsApplicationEDPResourceSet >= 0 )
  {
    if ( !(_BYTE)v11 )
    {
      KeStackAttachProcess(PsInitialSystemProcess, &ApcState);
      v5 = 1;
      v9 = 1;
    }
    IsApplicationEDPResourceSet = SrppIsApplicationEDPResourceSet(
                                    a1,
                                    *((_QWORD *)&v10[0] + 1),
                                    v7,
                                    a3,
                                    v9,
                                    *(_QWORD *)&v10[0]);
  }
  if ( v5 )
    KeUnstackDetachProcess(&ApcState);
  SrppUnmapFileImage(v10);
  return (unsigned int)IsApplicationEDPResourceSet;
}

```

## disassembly

```asm
0x14002f434  mov     [rsp+arg_0], rbx
0x14002f439  push    rsi
0x14002f43a  push    rdi
0x14002f43b  push    r14
0x14002f43d  sub     rsp, 90h
0x14002f444  mov     rax, cs:__security_cookie
0x14002f44b  xor     rax, rsp
0x14002f44e  mov     [rsp+0A8h+var_28], rax
0x14002f456  mov     rsi, r8
0x14002f459  mov     rax, rdx
0x14002f45c  mov     r14d, ecx
0x14002f45f  xorps   xmm0, xmm0
0x14002f462  xor     ecx, ecx
0x14002f464  movups  [rsp+0A8h+var_80], xmm0
0x14002f469  movups  [rsp+0A8h+var_70], xmm0
0x14002f46e  mov     [rsp+0A8h+var_60], rcx
0x14002f473  xorps   xmm1, xmm1
0x14002f476  movups  xmmword ptr [rsp+0A8h+ApcState.ApcListHead.Flink], xmm1
0x14002f47b  movups  xmmword ptr [rsp+0A8h+ApcState.ApcListHead.Flink+10h], xmm1
0x14002f480  movups  xmmword ptr [rsp+0A8h+ApcState.Process], xmm1
0x14002f485  test    rdx, rdx
0x14002f488  jz      loc_14002F523
0x14002f48e  test    r8, r8
0x14002f491  jz      loc_14002F523
0x14002f497  xor     edi, edi
0x14002f499  mov     [rsp+0A8h+var_88], edi
0x14002f49d  mov     [r8], cl
0x14002f4a0  lea     rdx, [rsp+0A8h+var_80]
0x14002f4a5  mov     rcx, rax; FileHandle
0x14002f4a8  call    SrppMapFileImage
0x14002f4ad  mov     ebx, eax
0x14002f4af  test    eax, eax
0x14002f4b1  js      short loc_14002F500
0x14002f4b3  cmp     byte ptr [rsp+0A8h+var_60], dil
0x14002f4b8  jnz     short loc_14002F4DE
0x14002f4ba  lea     rdx, [rsp+0A8h+ApcState]; ApcState
0x14002f4bf  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14002f4c6  mov     rcx, [rcx]; PROCESS
0x14002f4c9  call    cs:__imp_KeStackAttachProcess
0x14002f4d0  nop     dword ptr [rax+rax+00h]
0x14002f4d5  mov     edi, 1
0x14002f4da  mov     [rsp+0A8h+var_88], edi
0x14002f4de  mov     r9, rsi
0x14002f4e1  mov     rdx, qword ptr [rsp+0A8h+var_80+8]
0x14002f4e6  mov     ecx, r14d
0x14002f4e9  call    SrppIsApplicationEDPResourceSet
0x14002f4ee  mov     ebx, eax
0x14002f4f0  mov     [rsp+0A8h+var_84], eax
0x14002f4f4  jmp     short loc_14002F500
0x14002f4f6  mov     ebx, eax
0x14002f4f8  mov     [rsp+0A8h+var_84], eax
0x14002f4fc  mov     edi, [rsp+0A8h+var_88]
0x14002f500  test    edi, edi
0x14002f502  jz      short loc_14002F515
0x14002f504  lea     rcx, [rsp+0A8h+ApcState]; ApcState
0x14002f509  call    cs:__imp_KeUnstackDetachProcess
0x14002f510  nop     dword ptr [rax+rax+00h]
0x14002f515  lea     rcx, [rsp+0A8h+var_80]
0x14002f51a  call    SrppUnmapFileImage
0x14002f51f  mov     eax, ebx
0x14002f521  jmp     short loc_14002F528
0x14002f523  mov     eax, 0C000000Dh
0x14002f528  mov     rcx, [rsp+0A8h+var_28]
0x14002f530  xor     rcx, rsp; StackCookie
0x14002f533  call    __security_check_cookie
0x14002f538  mov     rbx, [rsp+0A8h+arg_0]
0x14002f540  add     rsp, 90h
0x14002f547  pop     r14
0x14002f549  pop     rdi
0x14002f54a  pop     rsi
0x14002f54b  retn
```
