# AERTAllocate(unsigned __int64,void *)

- ea: `0x140010660`
- end: `0x140010818`
- name: `?AERTAllocate@@YAPEAX_KPEAX@Z`
- size: `440`
- prototype: `void *(unsigned __int64, void *)`
- caller_count: `18`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400102b8`
- `0x140010b34`
- `0x140011ea8`
- `0x140029680`
- `0x140038070`
- `0x14003e9c0`
- `0x1400453b8`
- `0x140047b5c`
- `0x1400541c8`
- `0x140070c00`
- `0x1400771b0`
- `0x1400797f4`
- `0x1400798fc`
- `0x14009d2d0`
- `0x14009d3a0`
- `0x14009d470`
- `0x14009d650`
- `0x14009ecb0`

## callees

- `0x140010660`
- `0x140011020`
- `0x14005d0e0`
- `0x14005d7bc`
- `0x140083ec0`

## import_xrefs

- `ntdll!RtlAllocateMemoryBlockLookaside` at `0x1400106b0`
- `ntdll!RtlAllocateMemoryBlockLookaside` at `0x14001080d`
- `ntdll!RtlAllocateMemoryBlockLookaside` at `0x1400106b0`
- `ntdll!RtlAllocateMemoryBlockLookaside` at `0x14001080d`

## pseudocode

```c
void *__fastcall AERTAllocate(unsigned __int64 a1, void *a2, __int64 a3)
{
  int v5; // eax
  unsigned __int64 v7; // rdx
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  int v9; // [rsp+38h] [rbp-C8h] BYREF
  int v10; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+48h] [rbp-B8h] BYREF
  int v12; // [rsp+50h] [rbp-B0h] BYREF
  int v13; // [rsp+58h] [rbp-A8h] BYREF
  int v14; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h] BYREF
  __int64 v16; // [rsp+70h] [rbp-90h] BYREF
  void *v17; // [rsp+78h] [rbp-88h] BYREF
  char v18[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v19; // [rsp+90h] [rbp-70h]
  __int64 v20; // [rsp+98h] [rbp-68h]
  int *v21; // [rsp+A0h] [rbp-60h]
  __int64 v22; // [rsp+A8h] [rbp-58h]
  void **v23; // [rsp+B0h] [rbp-50h]
  __int64 v24; // [rsp+B8h] [rbp-48h]
  int *v25; // [rsp+C0h] [rbp-40h]
  __int64 v26; // [rsp+C8h] [rbp-38h]
  int *v27; // [rsp+D0h] [rbp-30h]
  __int64 v28; // [rsp+D8h] [rbp-28h]
  int *v29; // [rsp+E0h] [rbp-20h]
  __int64 v30; // [rsp+E8h] [rbp-18h]
  int *v31; // [rsp+F0h] [rbp-10h]
  __int64 v32; // [rsp+F8h] [rbp-8h]
  int *v33; // [rsp+100h] [rbp+0h]
  __int64 v34; // [rsp+108h] [rbp+8h]
  int *v35; // [rsp+110h] [rbp+10h]
  __int64 v36; // [rsp+118h] [rbp+18h]

  if ( g_bSkipRTHeap )
    return operator new[](a1);
  v15 = 0;
  if ( a2 )
  {
    v5 = RtlAllocateMemoryBlockLookaside(a2, a1, &v15);
    if ( v5 == -1073741670 )
    {
      v7 = 0x100000;
      if ( a1 > 0x100000 )
        v7 = (a1 + 0x2000) & 0xFFFFFFFFFFFFE000uLL;
      AERTAddMemoryToHeap(a2, v7);
      v5 = RtlAllocateMemoryBlockLookaside(a2, a1, &v15);
    }
  }
  else
  {
    v5 = -1073741670;
  }
  if ( (byte_1400E7E41 & 4) != 0 )
  {
    v14 = v5;
    v13 = 0;
    v19 = &v16;
    v12 = 0;
    v21 = &v8;
    v23 = &v17;
    v25 = &v9;
    v27 = &v10;
    v29 = &v11;
    v31 = &v12;
    v33 = &v13;
    v35 = &v14;
    v11 = 0;
    v10 = 0;
    v9 = a1;
    v17 = a2;
    v8 = 6;
    v16 = 0;
    v20 = 8;
    v22 = 4;
    v24 = 8;
    v26 = 4;
    v28 = 4;
    v30 = 4;
    v32 = 4;
    v34 = 4;
    v36 = 4;
    McGenEventWrite_EventWriteTransfer(a1, AudioCore_AEMemory, a3, 10, v18);
  }
  return (void *)v15;
}

```

## disassembly

```asm
0x140010660  push    rbp
0x140010662  push    rbx
0x140010663  push    rdi
0x140010664  lea     rbp, [rsp-30h]
0x140010669  sub     rsp, 130h
0x140010670  mov     rax, cs:__security_cookie
0x140010677  xor     rax, rsp
0x14001067a  mov     [rbp+40h+var_20], rax
0x14001067e  cmp     cs:?g_bSkipRTHeap@@3_NA, 0; bool g_bSkipRTHeap
0x140010685  mov     rbx, rdx
0x140010688  mov     rdi, rcx
0x14001068b  jnz     short loc_1400106EE
0x14001068d  mov     [rsp+140h+arg_10], rsi
0x140010695  xor     esi, esi
0x140010697  mov     [rsp+140h+var_D8], rsi
0x14001069c  test    rdx, rdx
0x14001069f  jz      loc_1400107D8
0x1400106a5  mov     rdx, rcx
0x1400106a8  lea     r8, [rsp+140h+var_D8]
0x1400106ad  mov     rcx, rbx
0x1400106b0  call    cs:__imp_RtlAllocateMemoryBlockLookaside
0x1400106b6  cmp     eax, 0C000009Ah
0x1400106bb  jz      loc_1400107E2
0x1400106c1  test    cs:byte_1400E7E41, 4
0x1400106c8  jnz     short loc_1400106F5
0x1400106ca  mov     rax, [rsp+140h+var_D8]
0x1400106cf  mov     rsi, [rsp+140h+arg_10]
0x1400106d7  mov     rcx, [rbp+40h+var_20]
0x1400106db  xor     rcx, rsp; StackCookie
0x1400106de  call    __security_check_cookie
0x1400106e3  add     rsp, 130h
0x1400106ea  pop     rdi
0x1400106eb  pop     rbx
0x1400106ec  pop     rbp
0x1400106ed  retn
0x1400106ee  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400106f3  jmp     short loc_1400106D7
0x1400106f5  mov     [rsp+140h+var_E0], eax
0x1400106f9  lea     rdx, AudioCore_AEMemory
0x140010700  lea     rax, [rsp+140h+var_D0]
0x140010705  mov     [rsp+140h+var_E8], esi
0x140010709  mov     [rbp+40h+var_B0], rax
0x14001070d  mov     r9d, 0Ah
0x140010713  lea     rax, [rsp+140h+var_110]
0x140010718  mov     [rsp+140h+var_F0], esi
0x14001071c  mov     [rbp+40h+var_A0], rax
0x140010720  lea     rax, [rsp+140h+var_C8]
0x140010725  mov     [rbp+40h+var_90], rax
0x140010729  lea     rax, [rsp+140h+var_108]
0x14001072e  mov     [rbp+40h+var_80], rax
0x140010732  lea     rax, [rsp+140h+var_100]
0x140010737  mov     [rbp+40h+var_70], rax
0x14001073b  lea     rax, [rsp+140h+var_F8]
0x140010740  mov     [rbp+40h+var_60], rax
0x140010744  lea     rax, [rsp+140h+var_F0]
0x140010749  mov     [rbp+40h+var_50], rax
0x14001074d  lea     rax, [rsp+140h+var_E8]
0x140010752  mov     [rbp+40h+var_40], rax
0x140010756  lea     rax, [rsp+140h+var_E0]
0x14001075b  mov     [rbp+40h+var_30], rax
0x14001075f  lea     rax, [rbp+40h+var_C0]
0x140010763  mov     [rsp+140h+var_120], rax
0x140010768  mov     [rsp+140h+var_F8], esi
0x14001076c  mov     [rsp+140h+var_100], esi
0x140010770  mov     [rsp+140h+var_108], edi
0x140010774  mov     [rsp+140h+var_C8], rbx
0x140010779  mov     [rsp+140h+var_110], 6
0x140010781  mov     [rsp+140h+var_D0], rsi
0x140010786  mov     [rbp+40h+var_A8], 8
0x14001078e  mov     [rbp+40h+var_98], 4
0x140010796  mov     [rbp+40h+var_88], 8
0x14001079e  mov     [rbp+40h+var_78], 4
0x1400107a6  mov     [rbp+40h+var_68], 4
0x1400107ae  mov     [rbp+40h+var_58], 4
0x1400107b6  mov     [rbp+40h+var_48], 4
0x1400107be  mov     [rbp+40h+var_38], 4
0x1400107c6  mov     [rbp+40h+var_28], 4
0x1400107ce  call    McGenEventWrite_EventWriteTransfer
0x1400107d3  jmp     loc_1400106CA
0x1400107d8  mov     eax, 0C000009Ah
0x1400107dd  jmp     loc_1400106C1
0x1400107e2  mov     edx, 100000h
0x1400107e7  cmp     rdi, rdx
0x1400107ea  jbe     short loc_1400107FA
0x1400107ec  lea     rdx, [rdi+2000h]
0x1400107f3  and     rdx, 0FFFFFFFFFFFFE000h; unsigned __int64
0x1400107fa  mov     rcx, rbx; void *
0x1400107fd  call    ?AERTAddMemoryToHeap@@YAXPEAX_K@Z; AERTAddMemoryToHeap(void *,unsigned __int64)
0x140010802  lea     r8, [rsp+140h+var_D8]
0x140010807  mov     rdx, rdi
0x14001080a  mov     rcx, rbx
0x14001080d  call    cs:__imp_RtlAllocateMemoryBlockLookaside
0x140010813  jmp     loc_1400106C1
```
