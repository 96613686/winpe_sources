# midiIDMessage

- ea: `0x1800078f4`
- end: `0x180007af9`
- name: `midiIDMessage`
- size: `517`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int16 *, unsigned __int64)`
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x180009160`
- `0x180009250`
- `0x1800096f0`
- `0x18000e860`
- `0x180018bb0`
- `0x1800194d0`
- `0x180019740`
- `0x180019bc0`

## callees

- `0x18000233c`
- `0x180007560`
- `0x1800078f4`
- `0x180007d70`
- `0x180007dd0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000792b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000792b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007977`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007977`

## pseudocode

```c
__int64 __fastcall midiIDMessage(
        __int64 *a1,
        unsigned int a2,
        unsigned __int64 a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned __int64 a6)
{
  unsigned __int64 v7; // rdi
  __int64 v9; // rbx
  unsigned int v10; // ebp
  int v11; // edx
  unsigned __int64 v12; // rsi
  unsigned __int16 *v13; // rbp
  unsigned int v14; // edi
  __int64 v16; // [rsp+88h] [rbp+10h] BYREF

  v7 = a3;
  if ( a3 >= a2 && a3 != 0xFFFFFFFF )
  {
    if ( a1 == &midioutdrvZ && ValidateHandle(a3, 3) || a1 == &midiindrvZ && ValidateHandle(v7, 4) )
      return (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned __int16 *, unsigned __int64))(*(_QWORD *)v7 + 80LL))(
               *(unsigned int *)(v7 + 8),
               a4,
               *(_QWORD *)(v7 + 16),
               a5,
               a6);
    else
      return 2;
  }
  if ( (_DWORD)a3 == -1 )
    MidiMapperInit();
  EnterCriticalSection(&NumDevsCritSec);
  v9 = *a1;
  v10 = 2;
  if ( (_DWORD)v7 == -1 )
  {
    LODWORD(v7) = 0;
    while ( (__int64 *)v9 != a1 )
    {
      if ( (*(_BYTE *)(v9 + 112) & 2) != 0 )
        goto LABEL_11;
      v9 = *(_QWORD *)v9;
    }
  }
  else if ( (__int64 *)v9 != a1 )
  {
    do
    {
      if ( (*(_BYTE *)(v9 + 112) & 2) == 0 )
      {
        if ( *(_DWORD *)(v9 + 88) > (unsigned int)v7 )
          break;
        LODWORD(v7) = v7 - *(_DWORD *)(v9 + 88);
      }
      v9 = *(_QWORD *)v9;
    }
    while ( (__int64 *)v9 != a1 );
    if ( (__int64 *)v9 != a1 )
    {
LABEL_11:
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 92));
      v10 = 0;
      goto LABEL_12;
    }
  }
  v9 = 0;
  LODWORD(v7) = 0;
LABEL_12:
  LeaveCriticalSection(&NumDevsCritSec);
  LODWORD(v16) = v10;
  if ( v10 )
    return v10;
  if ( a1 == &midiindrvZ )
  {
    v11 = 4;
  }
  else
  {
    v11 = 0;
    if ( a1 == &midioutdrvZ )
      v11 = 3;
  }
  if ( !*(_QWORD *)(v9 + 80) )
    return 6;
  v12 = a6;
  v13 = a5;
  if ( (unsigned int)mregHandleInternalMessages((struct _MMDRV *)v9, v11, v7, a4, a5, a6, (int *)&v16) )
    v14 = v16;
  else
    v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned __int16 *, unsigned __int64))(v9 + 80))(
            (unsigned int)v7,
            a4,
            0,
            v13,
            v12);
  mregDecUsagePtr((struct _MMDRV *)v9);
  return v14;
}

```

## disassembly

```asm
0x1800078f4  push    rbx
0x1800078f6  push    rbp
0x1800078f7  push    rsi
0x1800078f8  push    rdi
0x1800078f9  push    r14
0x1800078fb  push    r15
0x1800078fd  sub     rsp, 48h
0x180007901  mov     eax, edx
0x180007903  mov     r14d, r9d
0x180007906  mov     rdi, r8
0x180007909  mov     rsi, rcx
0x18000790c  mov     r15d, 0FFFFFFFFh
0x180007912  cmp     r8, rax
0x180007915  jnb     loc_180007A32
0x18000791b  cmp     edi, r15d
0x18000791e  jz      loc_180007ACE
0x180007924  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000792b  call    cs:__imp_EnterCriticalSection
0x180007931  mov     rbx, [rsi]
0x180007934  mov     ebp, 2
0x180007939  cmp     edi, r15d
0x18000793c  jz      loc_180007AEB
0x180007942  cmp     rbx, rsi
0x180007945  jz      loc_180007AC5
0x18000794b  test    [rbx+70h], bpl
0x18000794f  jnz     short loc_180007959
0x180007951  cmp     [rbx+58h], edi
0x180007954  ja      short loc_180007961
0x180007956  sub     edi, [rbx+58h]
0x180007959  mov     rbx, [rbx]
0x18000795c  cmp     rbx, rsi
0x18000795f  jnz     short loc_18000794B
0x180007961  cmp     rbx, rsi
0x180007964  jz      loc_180007AC5
0x18000796a  lock inc dword ptr [rbx+5Ch]
0x18000796e  xor     ebp, ebp
0x180007970  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180007977  call    cs:__imp_LeaveCriticalSection
0x18000797d  mov     dword ptr [rsp+78h+arg_8], ebp
0x180007984  test    ebp, ebp
0x180007986  jnz     loc_180007AD8
0x18000798c  lea     rax, midiindrvZ
0x180007993  cmp     rsi, rax
0x180007996  jz      loc_180007A28
0x18000799c  xor     edx, edx
0x18000799e  lea     rax, midioutdrvZ
0x1800079a5  cmp     rsi, rax
0x1800079a8  lea     ecx, [rbp+3]
0x1800079ab  cmovz   edx, ecx
0x1800079ae  cmp     qword ptr [rbx+50h], 0
0x1800079b3  jz      loc_180007AA9
0x1800079b9  mov     rsi, [rsp+78h+arg_28]
0x1800079c1  lea     rax, [rsp+78h+arg_8]
0x1800079c9  mov     rbp, [rsp+78h+arg_20]
0x1800079d1  mov     r9d, r14d
0x1800079d4  mov     [rsp+78h+var_48], rax; __int64
0x1800079d9  mov     r8d, edi
0x1800079dc  mov     [rsp+78h+var_50], rsi; unsigned __int64
0x1800079e1  mov     rcx, rbx; struct _MMDRV *
0x1800079e4  mov     [rsp+78h+var_58], rbp; unsigned __int16 *
0x1800079e9  call    mregHandleInternalMessages
0x1800079ee  test    eax, eax
0x1800079f0  jnz     loc_180007ADF
0x1800079f6  mov     rax, [rbx+50h]
0x1800079fa  mov     r9, rbp
0x1800079fd  xor     r8d, r8d
0x180007a00  mov     [rsp+78h+var_58], rsi
0x180007a05  mov     edx, r14d
0x180007a08  mov     ecx, edi
0x180007a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a0f  mov     edi, eax
0x180007a11  mov     rcx, rbx; struct _MMDRV *
0x180007a14  call    mregDecUsagePtr
0x180007a19  mov     eax, edi
0x180007a1b  add     rsp, 48h
0x180007a1f  pop     r15
0x180007a21  pop     r14
0x180007a23  pop     rdi
0x180007a24  pop     rsi
0x180007a25  pop     rbp
0x180007a26  pop     rbx
0x180007a27  retn
0x180007a28  mov     edx, 4
0x180007a2d  jmp     loc_1800079AE
0x180007a32  cmp     rdi, r15
0x180007a35  jz      loc_18000791B
0x180007a3b  lea     rax, midioutdrvZ
0x180007a42  cmp     rsi, rax
0x180007a45  jnz     short loc_180007A58
0x180007a47  mov     edx, 3
0x180007a4c  mov     rcx, rdi
0x180007a4f  call    ValidateHandle
0x180007a54  test    eax, eax
0x180007a56  jnz     short loc_180007A79
0x180007a58  lea     rax, midiindrvZ
0x180007a5f  cmp     rsi, rax
0x180007a62  jnz     loc_180007AEF
0x180007a68  mov     edx, 4
0x180007a6d  mov     rcx, rdi
0x180007a70  call    ValidateHandle
0x180007a75  test    eax, eax
0x180007a77  jz      short loc_180007AEF
0x180007a79  mov     rcx, [rsp+78h+arg_28]
0x180007a81  mov     edx, r14d
0x180007a84  mov     rax, [rdi]
0x180007a87  mov     r9, [rsp+78h+arg_20]
0x180007a8f  mov     r8, [rdi+10h]
0x180007a93  mov     [rsp+78h+var_58], rcx
0x180007a98  mov     rax, [rax+50h]
0x180007a9c  mov     ecx, [rdi+8]
0x180007a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aa4  jmp     loc_180007A1B
0x180007aa9  mov     eax, 6
0x180007aae  jmp     loc_180007A1B
0x180007ab3  test    [rbx+70h], bpl
0x180007ab7  jnz     loc_18000796A
0x180007abd  mov     rbx, [rbx]
0x180007ac0  cmp     rbx, rsi
0x180007ac3  jnz     short loc_180007AB3
0x180007ac5  xor     ebx, ebx
0x180007ac7  xor     edi, edi
0x180007ac9  jmp     loc_180007970
0x180007ace  call    MidiMapperInit
0x180007ad3  jmp     loc_180007924
0x180007ad8  mov     eax, ebp
0x180007ada  jmp     loc_180007A1B
0x180007adf  mov     edi, dword ptr [rsp+78h+arg_8]
0x180007ae6  jmp     loc_180007A11
0x180007aeb  xor     edi, edi
0x180007aed  jmp     short loc_180007AC0
0x180007aef  mov     eax, 2
0x180007af4  jmp     loc_180007A1B
```
