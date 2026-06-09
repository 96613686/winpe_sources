# waveIDMessage(_MMDRV *,uint,unsigned __int64,uint,unsigned __int64,unsigned __int64)

- ea: `0x180007b00`
- end: `0x180007d67`
- name: `?waveIDMessage@@YAIPEAU_MMDRV@@I_KI11@Z`
- size: `615`
- prototype: `unsigned int __fastcall(struct _MMDRV *, unsigned int, unsigned __int64, unsigned int, unsigned __int16 *, unsigned __int64)`
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x180007640`
- `0x180008530`
- `0x180009760`
- `0x18000a790`
- `0x18000ec90`
- `0x18000ed70`
- `0x18000eff0`
- `0x18001da90`

## callees

- `0x180004534`
- `0x180007560`
- `0x180007b00`
- `0x180007d70`
- `0x180007dd0`
- `0x180012d30`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b3f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007cc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b3f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007cc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007b7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007b7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c18`

## pseudocode

```c
__int64 __fastcall waveIDMessage(
        struct _MMDRV *a1,
        unsigned int a2,
        unsigned __int64 a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned __int64 a6)
{
  unsigned __int64 v8; // rsi
  int v9; // ebp
  struct _MMDRV *v10; // rbx
  unsigned int v11; // eax
  unsigned __int64 v12; // rdi
  unsigned __int16 *v13; // r14
  unsigned int v14; // edi
  unsigned int v16; // edi
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v8 = a3;
  v9 = 2;
  if ( a3 != 0xFFFFFFFF && a3 >= a2 )
  {
    if ( (a1 != (struct _MMDRV *)&waveoutdrvZ || !ValidateHandle(a3, 1))
      && (a1 != (struct _MMDRV *)&waveindrvZ || !ValidateHandle(v8, 2)) )
    {
      return 2;
    }
    if ( (*(_DWORD *)(*(_QWORD *)v8 + 112LL) & 1) != 0 )
      return 6;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d3341913caf93b06366119208946103b_Traceguids, v8);
    }
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned __int16 *, unsigned __int64))(*(_QWORD *)v8 + 80LL))(
             *(unsigned int *)(v8 + 8),
             a4,
             *(_QWORD *)(v8 + 16),
             a5,
             a6);
  }
  if ( (_DWORD)a3 == -1 )
  {
    WaveMapperInit();
    EnterCriticalSection(&NumDevsCritSec);
    v10 = *(struct _MMDRV **)a1;
    LODWORD(v8) = 0;
    if ( *(struct _MMDRV **)a1 == a1 )
      goto LABEL_14;
    while ( (*((_BYTE *)v10 + 112) & 2) == 0 )
    {
      v10 = *(struct _MMDRV **)v10;
      if ( v10 == a1 )
        goto LABEL_14;
    }
LABEL_7:
    _InterlockedIncrement((volatile signed __int32 *)v10 + 23);
    LeaveCriticalSection(&NumDevsCritSec);
    LODWORD(v17) = 0;
    if ( a1 != (struct _MMDRV *)&waveindrvZ )
      v9 = a1 == (struct _MMDRV *)&waveoutdrvZ;
    if ( *((_QWORD *)v10 + 10) )
    {
      v12 = a6;
      v13 = a5;
      if ( !(unsigned int)mregHandleInternalMessages(v10, v9, v8, a4, a5, a6, (int *)&v17) )
      {
        v16 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned __int16 *, unsigned __int64))v10 + 10))(
                (unsigned int)v8,
                a4,
                0,
                v13,
                v12);
        mregDecUsagePtr(v10);
        return v16;
      }
      v14 = v17;
    }
    else
    {
      v14 = 6;
    }
    mregDecUsagePtr(v10);
    return v14;
  }
  EnterCriticalSection(&NumDevsCritSec);
  v10 = *(struct _MMDRV **)a1;
  if ( *(struct _MMDRV **)a1 == a1 )
    goto LABEL_14;
  while ( (*((_BYTE *)v10 + 112) & 2) != 0 )
  {
LABEL_13:
    v10 = *(struct _MMDRV **)v10;
    if ( v10 == a1 )
      goto LABEL_14;
  }
  v11 = *((_DWORD *)v10 + 22);
  if ( v11 <= (unsigned int)v8 )
  {
    LODWORD(v8) = v8 - v11;
    goto LABEL_13;
  }
  if ( v10 != a1 )
    goto LABEL_7;
LABEL_14:
  LeaveCriticalSection(&NumDevsCritSec);
  return 2;
}

```

## disassembly

```asm
0x180007b00  mov     [rsp+arg_10], rbx
0x180007b05  mov     [rsp+arg_18], rbp
0x180007b0a  push    rsi
0x180007b0b  push    rdi
0x180007b0c  push    r15
0x180007b0e  sub     rsp, 40h
0x180007b12  mov     rdi, rcx
0x180007b15  mov     eax, edx
0x180007b17  mov     ecx, 0FFFFFFFFh
0x180007b1c  mov     r15d, r9d
0x180007b1f  mov     rsi, r8
0x180007b22  mov     ebp, 2
0x180007b27  cmp     r8, rcx
0x180007b2a  jnz     loc_180007C33
0x180007b30  cmp     esi, ecx
0x180007b32  jz      loc_180007CB4
0x180007b38  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180007b3f  call    cs:__imp_EnterCriticalSection
0x180007b45  mov     rbx, [rdi]
0x180007b48  cmp     rbx, rdi
0x180007b4b  jz      loc_180007C11
0x180007b51  test    [rbx+70h], bpl
0x180007b55  jnz     loc_180007C05
0x180007b5b  mov     eax, [rbx+58h]
0x180007b5e  cmp     eax, esi
0x180007b60  jbe     loc_180007D56
0x180007b66  cmp     rbx, rdi
0x180007b69  jz      loc_180007C11
0x180007b6f  lock inc dword ptr [rbx+5Ch]
0x180007b73  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180007b7a  call    cs:__imp_LeaveCriticalSection
0x180007b80  lea     rax, waveindrvZ
0x180007b87  mov     dword ptr [rsp+58h+arg_8], 0
0x180007b8f  cmp     rdi, rax
0x180007b92  jz      short loc_180007BA4
0x180007b94  xor     ebp, ebp
0x180007b96  lea     rax, waveoutdrvZ
0x180007b9d  cmp     rdi, rax
0x180007ba0  setz    bpl
0x180007ba4  cmp     qword ptr [rbx+50h], 0
0x180007ba9  jz      loc_180007D5D
0x180007baf  mov     rdi, [rsp+58h+arg_28]
0x180007bb7  lea     rax, [rsp+58h+arg_8]
0x180007bbc  mov     [rsp+58h+var_28], rax; __int64
0x180007bc1  mov     r9d, r15d
0x180007bc4  mov     [rsp+58h+arg_0], r14
0x180007bc9  mov     r8d, esi
0x180007bcc  mov     r14, [rsp+58h+arg_20]
0x180007bd4  mov     edx, ebp
0x180007bd6  mov     [rsp+58h+var_30], rdi; unsigned __int64
0x180007bdb  mov     rcx, rbx; struct _MMDRV *
0x180007bde  mov     [rsp+58h+var_38], r14; unsigned __int16 *
0x180007be3  call    mregHandleInternalMessages
0x180007be8  test    eax, eax
0x180007bea  jz      loc_180007C85
0x180007bf0  mov     edi, dword ptr [rsp+58h+arg_8]
0x180007bf4  mov     r14, [rsp+58h+arg_0]
0x180007bf9  mov     rcx, rbx; struct _MMDRV *
0x180007bfc  call    mregDecUsagePtr
0x180007c01  mov     eax, edi
0x180007c03  jmp     short loc_180007C20
0x180007c05  mov     rbx, [rbx]
0x180007c08  cmp     rbx, rdi
0x180007c0b  jnz     loc_180007B51
0x180007c11  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180007c18  call    cs:__imp_LeaveCriticalSection
0x180007c1e  mov     eax, ebp
0x180007c20  mov     rbx, [rsp+58h+arg_10]
0x180007c25  mov     rbp, [rsp+58h+arg_18]
0x180007c2a  add     rsp, 40h
0x180007c2e  pop     r15
0x180007c30  pop     rdi
0x180007c31  pop     rsi
0x180007c32  retn
0x180007c33  cmp     r8, rax
0x180007c36  jb      loc_180007B30
0x180007c3c  lea     rax, waveoutdrvZ
0x180007c43  cmp     rdi, rax
0x180007c46  jnz     short loc_180007C59
0x180007c48  mov     edx, 1
0x180007c4d  mov     rcx, rsi
0x180007c50  call    ValidateHandle
0x180007c55  test    eax, eax
0x180007c57  jnz     short loc_180007C73
0x180007c59  lea     rax, waveindrvZ
0x180007c60  cmp     rdi, rax
0x180007c63  jnz     short loc_180007C1E
0x180007c65  mov     edx, ebp
0x180007c67  mov     rcx, rsi
0x180007c6a  call    ValidateHandle
0x180007c6f  test    eax, eax
0x180007c71  jz      short loc_180007C1E
0x180007c73  mov     rax, [rsi]
0x180007c76  mov     ecx, [rax+70h]
0x180007c79  test    cl, 1
0x180007c7c  jz      short loc_180007CEC
0x180007c7e  mov     eax, 6
0x180007c83  jmp     short loc_180007C20
0x180007c85  mov     rax, [rbx+50h]
0x180007c89  mov     r9, r14
0x180007c8c  xor     r8d, r8d
0x180007c8f  mov     [rsp+58h+var_38], rdi
0x180007c94  mov     edx, r15d
0x180007c97  mov     ecx, esi
0x180007c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c9e  mov     r14, [rsp+58h+arg_0]
0x180007ca3  mov     rcx, rbx; struct _MMDRV *
0x180007ca6  mov     edi, eax
0x180007ca8  call    mregDecUsagePtr
0x180007cad  mov     eax, edi
0x180007caf  jmp     loc_180007C20
0x180007cb4  call    WaveMapperInit
0x180007cb9  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180007cc0  call    cs:__imp_EnterCriticalSection
0x180007cc6  mov     rbx, [rdi]
0x180007cc9  xor     esi, esi
0x180007ccb  cmp     rbx, rdi
0x180007cce  jz      loc_180007C11
0x180007cd4  test    [rbx+70h], bpl
0x180007cd8  jnz     loc_180007B6F
0x180007cde  mov     rbx, [rbx]
0x180007ce1  cmp     rbx, rdi
0x180007ce4  jz      loc_180007C11
0x180007cea  jmp     short loc_180007CD4
0x180007cec  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cf3  lea     rax, WPP_GLOBAL_Control
0x180007cfa  cmp     rcx, rax
0x180007cfd  jz      short loc_180007D26
0x180007cff  test    dword ptr [rcx+1Ch], 400000h
0x180007d06  jz      short loc_180007D26
0x180007d08  cmp     byte ptr [rcx+19h], 4
0x180007d0c  jb      short loc_180007D26
0x180007d0e  mov     rcx, [rcx+10h]
0x180007d12  lea     r8, WPP_d3341913caf93b06366119208946103b_Traceguids
0x180007d19  mov     edx, 0Ah
0x180007d1e  mov     r9, rsi
0x180007d21  call    WPP_SF_P
0x180007d26  mov     rcx, [rsp+58h+arg_28]
0x180007d2e  mov     edx, r15d
0x180007d31  mov     rax, [rsi]
0x180007d34  mov     r9, [rsp+58h+arg_20]
0x180007d3c  mov     r8, [rsi+10h]
0x180007d40  mov     [rsp+58h+var_38], rcx
0x180007d45  mov     rax, [rax+50h]
0x180007d49  mov     ecx, [rsi+8]
0x180007d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d51  jmp     loc_180007C20
0x180007d56  sub     esi, eax
0x180007d58  jmp     loc_180007C05
0x180007d5d  mov     edi, 6
0x180007d62  jmp     loc_180007BF9
```
