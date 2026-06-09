# CVideoObjectDecoder::CopyToPostProc(OutputFrame *)

- ea: `0x180025294`
- end: `0x1800253db`
- name: `?CopyToPostProc@CVideoObjectDecoder@@AEAAXPEAUOutputFrame@@@Z`
- size: `327`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this, struct OutputFrame *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012114`

## callees

- `0x180012a08`
- `0x180025294`

## import_xrefs

- `mfperfhelper!__imp_ippiCopy_8u_C1R` at `0x180025334`
- `mfperfhelper!__imp_ippiCopy_8u_C1R` at `0x180025373`
- `mfperfhelper!__imp_ippiCopy_8u_C1R` at `0x180025389`
- `mfperfhelper!__imp_ippiCopy_8u_C1R` at `0x180025334`
- `mfperfhelper!__imp_ippiCopy_8u_C1R` at `0x180025373`
- `mfperfhelper!__imp_ippiCopy_8u_C1R` at `0x180025389`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::CopyToPostProc(CVideoObjectDecoder *this, struct OutputFrame *a2)
{
  __int64 v4; // rbx
  __int64 v5; // r15
  __int64 v6; // rsi
  __int64 v7; // rbp
  __int64 v8; // r14
  __int64 v9; // rcx
  unsigned int v10; // edi
  unsigned __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // [rsp+60h] [rbp+8h]

  if ( g_petwPro )
    ETWWrite(this, MP4SDECD_CopyPostProc_Notification_Start, 0, 0);
  v4 = *((int *)this + 346);
  v5 = v4 + *((_QWORD *)a2 + 2);
  v6 = v4 + *((_QWORD *)this + 671);
  v7 = *((_QWORD *)a2 + 1);
  v8 = v4 + *((_QWORD *)this + 672);
  HIDWORD(v13) = 16 * *((_DWORD *)this + 223);
  LODWORD(v13) = *((_DWORD *)this + 1887) / 16;
  ippiCopy_8u_C1R(
    *((int *)this + 345) + *(_QWORD *)a2,
    (unsigned int)v13,
    *((int *)this + 345) + *((_QWORD *)this + 670),
    (unsigned int)v13,
    v13);
  v9 = v4 + v7;
  v10 = *((_DWORD *)this + 1888) / 8;
  v11 = __PAIR64__(8 * *((_DWORD *)this + 223), v10);
  ippiCopy_8u_C1R(v9, v10, v6, v10, __PAIR64__(8 * *((_DWORD *)this + 223), v10));
  ippiCopy_8u_C1R(v5, v10, v8, v10, v11);
  if ( g_petwPro )
    ETWWrite(v12, MP4SDECD_CopyPostProc_Notification_Stop, 0, 0);
}

```

## disassembly

```asm
0x180025294  mov     [rsp+arg_8], rbx
0x180025299  mov     [rsp+arg_10], rbp
0x18002529e  push    rsi
0x18002529f  push    rdi
0x1800252a0  push    r13
0x1800252a2  push    r14
0x1800252a4  push    r15
0x1800252a6  sub     rsp, 30h
0x1800252aa  cmp     cs:g_petwPro, 0
0x1800252b2  mov     rdi, rdx
0x1800252b5  mov     r13, rcx
0x1800252b8  jnz     loc_1800253B0
0x1800252be  mov     eax, [r13+1D7Ch]
0x1800252c5  mov     ecx, 10h
0x1800252ca  movsxd  rbx, dword ptr [r13+568h]
0x1800252d1  cdq
0x1800252d2  mov     r8, [r13+14F0h]
0x1800252d9  mov     r15, [rdi+10h]
0x1800252dd  mov     rsi, [r13+14F8h]
0x1800252e4  add     r15, rbx
0x1800252e7  mov     r14, [r13+1500h]
0x1800252ee  add     rsi, rbx
0x1800252f1  mov     rbp, [rdi+8]
0x1800252f5  add     r14, rbx
0x1800252f8  idiv    ecx
0x1800252fa  movsxd  rdx, dword ptr [r13+564h]
0x180025301  mov     ecx, [r13+37Ch]
0x180025308  add     r8, rdx
0x18002530b  shl     ecx, 4
0x18002530e  mov     r9d, eax
0x180025311  mov     [rsp+58h+arg_0], 0
0x18002531a  mov     dword ptr [rsp+58h+arg_0+4], ecx
0x18002531e  mov     rcx, [rdi]
0x180025321  add     rcx, rdx
0x180025324  mov     dword ptr [rsp+58h+arg_0], eax
0x180025328  mov     rdx, [rsp+58h+arg_0]
0x18002532d  mov     [rsp+58h+var_38], rdx
0x180025332  mov     edx, eax
0x180025334  call    cs:__imp_ippiCopy_8u_C1R
0x18002533a  mov     eax, [r13+1D80h]
0x180025341  mov     ecx, 8
0x180025346  cdq
0x180025347  mov     r8, rsi
0x18002534a  idiv    ecx
0x18002534c  mov     edx, [r13+37Ch]
0x180025353  lea     rcx, [rbx+rbp]
0x180025357  shl     edx, 3
0x18002535a  mov     r9d, eax
0x18002535d  mov     dword ptr [rsp+58h+arg_0+4], edx
0x180025361  mov     edi, eax
0x180025363  mov     dword ptr [rsp+58h+arg_0], eax
0x180025367  mov     edx, eax
0x180025369  mov     rbx, [rsp+58h+arg_0]
0x18002536e  mov     [rsp+58h+var_38], rbx
0x180025373  call    cs:__imp_ippiCopy_8u_C1R
0x180025379  mov     r9d, edi
0x18002537c  mov     [rsp+58h+var_38], rbx
0x180025381  mov     r8, r14
0x180025384  mov     edx, edi
0x180025386  mov     rcx, r15
0x180025389  call    cs:__imp_ippiCopy_8u_C1R
0x18002538f  cmp     cs:g_petwPro, 0
0x180025397  jnz     short loc_1800253C7
0x180025399  mov     rbx, [rsp+58h+arg_8]
0x18002539e  mov     rbp, [rsp+58h+arg_10]
0x1800253a3  add     rsp, 30h
0x1800253a7  pop     r15
0x1800253a9  pop     r14
0x1800253ab  pop     r13
0x1800253ad  pop     rdi
0x1800253ae  pop     rsi
0x1800253af  retn
0x1800253b0  xor     r9d, r9d
0x1800253b3  lea     rdx, MP4SDECD_CopyPostProc_Notification_Start
0x1800253ba  xor     r8d, r8d
0x1800253bd  call    ETWWrite
0x1800253c2  jmp     loc_1800252BE
0x1800253c7  xor     r9d, r9d
0x1800253ca  lea     rdx, MP4SDECD_CopyPostProc_Notification_Stop
0x1800253d1  xor     r8d, r8d
0x1800253d4  call    ETWWrite
0x1800253d9  jmp     short loc_180025399
```
