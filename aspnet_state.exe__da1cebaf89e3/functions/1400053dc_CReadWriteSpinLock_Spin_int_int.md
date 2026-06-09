# CReadWriteSpinLock::_Spin(int,int)

- ea: `0x1400053dc`
- end: `0x1400054c6`
- name: `?_Spin@CReadWriteSpinLock@@AEAAXHH@Z`
- size: `234`
- prototype: `void __fastcall(CReadWriteSpinLock *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140005294`
- `0x1400052d0`

## callees

- `0x1400053b8`
- `0x1400053dc`
- `0x1400054c8`
- `0x1400054f8`

## pseudocode

```c
void __fastcall CReadWriteSpinLock::_Spin(CReadWriteSpinLock *this, int a2, int a3)
{
  int v4; // r14d
  int v6; // ebx
  int v8; // eax
  int v10; // eax
  int v12; // eax
  int v13; // eax
  int v14; // [rsp+48h] [rbp+10h] BYREF

  v14 = 0;
  v4 = CReadWriteSpinLock::s_disableBusyWaiting;
  v6 = 100;
  v8 = (int)(*(double *)&qword_140007BA0[a3 % 13] * 4000.0);
  if ( v8 >= 10000 )
    v8 = 10000;
  if ( v8 >= 100 )
    v6 = v8;
  while ( !(a2
          ? CReadWriteSpinLock::_TryAcquireReaderLock(this, a3)
          : (unsigned int)CReadWriteSpinLock::_TryAcquireWriterLock(this, a3, 1)) )
  {
    if ( v4 )
    {
      SwitchOrSleep(&v14);
    }
    else
    {
LABEL_11:
      v10 = v6;
      while ( !(a2 ? (*(_DWORD *)this & 0x7FFF0000) == 0 : (*(_DWORD *)this & 0xBFFFFFFF) == 0) )
      {
        if ( --v10 < 0 )
        {
          SwitchOrSleep(&v14);
          v12 = v6;
          v6 = 100;
          v13 = v12 / 2;
          if ( v13 >= 100 )
            v6 = v13;
          goto LABEL_11;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1400053dc  mov     [rsp+arg_0], rbx
0x1400053e1  mov     [rsp+arg_10], rbp
0x1400053e6  push    rsi
0x1400053e7  push    rdi
0x1400053e8  push    r14
0x1400053ea  sub     rsp, 20h
0x1400053ee  and     [rsp+38h+arg_8], 0
0x1400053f3  mov     rdi, rcx
0x1400053f6  mov     r14d, cs:?s_disableBusyWaiting@CReadWriteSpinLock@@0HA; int CReadWriteSpinLock::s_disableBusyWaiting
0x1400053fd  mov     ebp, edx
0x1400053ff  mov     eax, 4EC4EC4Fh
0x140005404  mov     ecx, r8d
0x140005407  imul    r8d
0x14000540a  mov     ebx, 64h ; 'd'
0x14000540f  mov     esi, r8d
0x140005412  sar     edx, 2
0x140005415  mov     eax, edx
0x140005417  shr     eax, 1Fh
0x14000541a  add     edx, eax
0x14000541c  imul    eax, edx, 0Dh
0x14000541f  sub     ecx, eax
0x140005421  movsxd  rax, ecx
0x140005424  lea     rcx, qword_140007BA0
0x14000542b  movsd   xmm0, qword ptr [rcx+rax*8]
0x140005430  mov     ecx, 2710h
0x140005435  mulsd   xmm0, cs:__real@40af400000000000
0x14000543d  cvttsd2si eax, xmm0
0x140005441  cmp     eax, ecx
0x140005443  cmovge  eax, ecx
0x140005446  cmp     eax, ebx
0x140005448  cmovge  ebx, eax
0x14000544b  mov     edx, esi; int
0x14000544d  mov     rcx, rdi; this
0x140005450  test    ebp, ebp
0x140005452  jz      short loc_14000545B
0x140005454  call    ?_TryAcquireReaderLock@CReadWriteSpinLock@@AEAAHH@Z; CReadWriteSpinLock::_TryAcquireReaderLock(int)
0x140005459  jmp     short loc_140005466
0x14000545b  mov     r8d, 1; int
0x140005461  call    ?_TryAcquireWriterLock@CReadWriteSpinLock@@AEAAHHH@Z; CReadWriteSpinLock::_TryAcquireWriterLock(int,int)
0x140005466  test    eax, eax
0x140005468  jnz     short loc_1400054B3
0x14000546a  test    r14d, r14d
0x14000546d  jz      short loc_14000547B
0x14000546f  lea     rcx, [rsp+38h+arg_8]; int *
0x140005474  call    ?SwitchOrSleep@@YAXAEAH@Z; SwitchOrSleep(int &)
0x140005479  jmp     short loc_14000544B
0x14000547b  mov     eax, ebx
0x14000547d  test    ebp, ebp
0x14000547f  jz      short loc_140005489
0x140005481  test    dword ptr [rdi], 7FFF0000h
0x140005487  jmp     short loc_14000548F
0x140005489  test    dword ptr [rdi], 0BFFFFFFFh
0x14000548f  jz      short loc_14000544B
0x140005491  sub     eax, 1
0x140005494  jns     short loc_14000547D
0x140005496  lea     rcx, [rsp+38h+arg_8]; int *
0x14000549b  call    ?SwitchOrSleep@@YAXAEAH@Z; SwitchOrSleep(int &)
0x1400054a0  mov     eax, ebx
0x1400054a2  mov     ebx, 64h ; 'd'
0x1400054a7  cdq
0x1400054a8  sub     eax, edx
0x1400054aa  sar     eax, 1
0x1400054ac  cmp     eax, ebx
0x1400054ae  cmovge  ebx, eax
0x1400054b1  jmp     short loc_14000547B
0x1400054b3  mov     rbx, [rsp+38h+arg_0]
0x1400054b8  mov     rbp, [rsp+38h+arg_10]
0x1400054bd  add     rsp, 20h
0x1400054c1  pop     r14
0x1400054c3  pop     rdi
0x1400054c4  pop     rsi
0x1400054c5  retn
```
