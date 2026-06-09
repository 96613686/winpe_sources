# BampRemoveThrottledProcessFromTable

- ea: `0x140010308`
- end: `0x140010443`
- name: `BampRemoveThrottledProcessFromTable`
- size: `315`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14000c83c`
- `0x140012450`

## callees

- `0x140010308`
- `0x140010760`
- `0x1400107a0`
- `0x1400107f0`
- `0x140011160`
- `0x1400113a0`
- `0x1400113f0`
- `0x140013c7c`

## pseudocode

```c
__int64 __fastcall BampRemoveThrottledProcessFromTable(_WORD *P)
{
  _QWORD *i; // r8
  __int64 v4; // [rsp+30h] [rbp+8h]

  BampAcquireThrottledProcessLock(P);
  P[138] &= ~1u;
  BampAcquireThrottlingWorkerLock();
  BampQueueThrottledProcessActionItem((__int64)P, 1, 0, 1);
  if ( (P[124] & 1) != 0 )
    BampCancelThrottledProcessActionItem(P);
  BampReleaseThrottlingWorkerLock();
  BampReleaseThrottledProcessLock(P);
  v4 = *((_QWORD *)P + 1) & (-1LL << (BYTE4(BampThrottledProcessTable) & 0x1F));
  for ( i = (char *)::P
          + 8
          * (((HIDWORD(BampThrottledProcessTable) >> 5) - 1)
           & (HIBYTE(v4)
            + 37
            * (BYTE6(v4)
             + 37
             * (BYTE5(v4)
              + 37
              * (BYTE4(v4)
               + 37 * (BYTE3(v4) + 37 * (BYTE2(v4) + 37 * (BYTE1(v4) + 37 * ((unsigned __int8)v4 + 11623883)))))))));
        (*i & 1) == 0;
        i = (_QWORD *)*i )
  {
    if ( (_WORD *)*i == P )
    {
      *i = *(_QWORD *)P;
      LODWORD(BampThrottledProcessTable) = BampThrottledProcessTable - 1;
      *(_QWORD *)P |= 0x8000000000000002uLL;
      return BampDereferenceThrottledProcessInformation(P);
    }
  }
  return BampDereferenceThrottledProcessInformation(P);
}

```

## disassembly

```asm
0x140010308  push    rbx
0x14001030a  sub     rsp, 20h
0x14001030e  mov     rbx, rcx
0x140010311  call    BampAcquireThrottledProcessLock
0x140010316  mov     eax, 0FFFEh
0x14001031b  and     [rbx+114h], ax
0x140010322  call    BampAcquireThrottlingWorkerLock
0x140010327  mov     r9d, 1
0x14001032d  xor     r8d, r8d
0x140010330  mov     edx, r9d
0x140010333  mov     rcx, rbx
0x140010336  call    BampQueueThrottledProcessActionItem
0x14001033b  test    byte ptr [rbx+0F8h], 1
0x140010342  jnz     loc_14001042F
0x140010348  call    BampReleaseThrottlingWorkerLock
0x14001034d  mov     rcx, rbx
0x140010350  call    BampReleaseThrottledProcessLock
0x140010355  mov     r8d, dword ptr cs:BampThrottledProcessTable+4
0x14001035c  lea     r9, [rsp+28h+arg_0]
0x140010361  or      rax, 0FFFFFFFFFFFFFFFFh
0x140010365  mov     ecx, r8d
0x140010368  and     ecx, 1Fh
0x14001036b  shr     r8d, 5
0x14001036f  shl     rax, cl
0x140010372  and     rax, [rbx+8]
0x140010376  mov     [rsp+28h+arg_0], rax
0x14001037b  movzx   eax, byte ptr [r9]
0x14001037f  add     eax, 0B15DCBh
0x140010384  imul    ecx, eax, 25h ; '%'
0x140010387  movzx   eax, byte ptr [r9+1]
0x14001038c  add     ecx, eax
0x14001038e  movzx   eax, byte ptr [r9+2]
0x140010393  imul    edx, ecx, 25h ; '%'
0x140010396  add     edx, eax
0x140010398  movzx   eax, byte ptr [r9+3]
0x14001039d  imul    ecx, edx, 25h ; '%'
0x1400103a0  add     ecx, eax
0x1400103a2  movzx   eax, byte ptr [r9+4]
0x1400103a7  imul    edx, ecx, 25h ; '%'
0x1400103aa  add     edx, eax
0x1400103ac  movzx   eax, byte ptr [r9+5]
0x1400103b1  imul    ecx, edx, 25h ; '%'
0x1400103b4  add     ecx, eax
0x1400103b6  movzx   eax, byte ptr [r9+6]
0x1400103bb  imul    edx, ecx, 25h ; '%'
0x1400103be  add     edx, eax
0x1400103c0  movzx   eax, byte ptr [r9+7]
0x1400103c5  imul    edx, 25h ; '%'
0x1400103c8  add     edx, eax
0x1400103ca  lea     eax, [r8-1]
0x1400103ce  and     rdx, rax
0x1400103d1  mov     rax, cs:P
0x1400103d8  lea     r8, [rax+rdx*8]
0x1400103dc  mov     rax, [rbx]
0x1400103df  mov     rdx, 8000000000000002h
0x1400103e9  and     rax, rdx
0x1400103ec  cmp     rax, rdx
0x1400103ef  jz      short loc_14001043C
0x1400103f1  mov     rax, [r8]
0x1400103f4  test    al, 1
0x1400103f6  jnz     short loc_140010423
0x1400103f8  cmp     rax, rbx
0x1400103fb  jnz     short loc_14001042A
0x1400103fd  mov     rax, [rbx]
0x140010400  mov     [r8], rax
0x140010403  mov     eax, dword ptr cs:BampThrottledProcessTable
0x140010409  dec     eax
0x14001040b  mov     dword ptr cs:BampThrottledProcessTable, eax
0x140010411  or      [rbx], rdx
0x140010414  mov     rcx, rbx; P
0x140010417  call    BampDereferenceThrottledProcessInformation
0x14001041c  add     rsp, 20h
0x140010420  pop     rbx
0x140010421  retn
0x140010423  xor     eax, eax
0x140010425  mov     rcx, [rax]
0x140010428  jmp     short loc_140010414
0x14001042a  mov     r8, rax
0x14001042d  jmp     short loc_1400103F1
0x14001042f  mov     rcx, rbx; P
0x140010432  call    BampCancelThrottledProcessActionItem
0x140010437  jmp     loc_140010348
0x14001043c  xor     eax, eax
0x14001043e  mov     rcx, [rax]
0x140010441  jmp     short loc_1400103F1
```
