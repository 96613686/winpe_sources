# BCryptIumContextManagerGetContext

- ea: `0x1400083a8`
- end: `0x14000849c`
- name: `BCryptIumContextManagerGetContext`
- size: `244`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x140002390`
- `0x140002620`
- `0x140008538`
- `0x14000e070`
- `0x14000e370`
- `0x14000e510`
- `0x14000e830`
- `0x14000ea40`
- `0x14000ec10`
- `0x14000ed50`
- `0x14000ee90`
- `0x14000f0d0`
- `0x14000f300`
- `0x14000f520`
- `0x14000fc50`
- `0x14000fe40`
- `0x1400100d0`
- `0x140010520`
- `0x1400106a0`
- `0x140010b50`
- `0x140010cd0`
- `0x140010ee0`
- `0x140010fc0`
- `0x1400110a0`
- `0x1400113a0`
- `0x140011730`

## callees

- `0x1400083a8`
- `0x14001193c`
- `0x140011964`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140008444`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140008444`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400083ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400083ed`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140008459`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140008459`

## pseudocode

```c
__int64 __fastcall BCryptIumContextManagerGetContext(__int64 a1, struct BCRYPTIUM_CONTEXT **a2)
{
  struct BCRYPTIUM_CONTEXT *v4; // rbx
  struct BCRYPTIUM_CONTEXT *i; // rax
  unsigned int v6; // ebx

  v4 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids);
  AcquireSRWLockShared(&SRWLock);
  for ( i = qword_140052C28; i != (struct BCRYPTIUM_CONTEXT *)&qword_140052C28; i = *(struct BCRYPTIUM_CONTEXT **)i )
  {
    if ( *((_QWORD *)i + 2) == a1 )
    {
      v4 = i;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids);
      break;
    }
  }
  ReleaseSRWLockShared(&SRWLock);
  if ( v4 )
  {
    *a2 = v4;
    v6 = 0;
  }
  else
  {
    v6 = -1073741790;
    Sleep(5u);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1400083a8  push    rbx
0x1400083aa  push    rsi
0x1400083ab  push    rdi
0x1400083ac  push    r14
0x1400083ae  sub     rsp, 28h
0x1400083b2  mov     rsi, rdx
0x1400083b5  mov     rdi, rcx
0x1400083b8  xor     ebx, ebx
0x1400083ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400083c1  lea     r14, WPP_GLOBAL_Control
0x1400083c8  cmp     rcx, r14
0x1400083cb  jz      short loc_1400083E6
0x1400083cd  test    byte ptr [rcx+1Ch], 4
0x1400083d1  jz      short loc_1400083E6
0x1400083d3  mov     rcx, [rcx+10h]
0x1400083d7  lea     edx, [rbx+4Dh]
0x1400083da  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x1400083e1  call    WPP_SF_
0x1400083e6  lea     rcx, SRWLock; SRWLock
0x1400083ed  call    cs:__imp_AcquireSRWLockShared
0x1400083f3  mov     rax, cs:qword_140052C28
0x1400083fa  lea     rcx, qword_140052C28
0x140008401  jmp     short loc_14000840C
0x140008403  cmp     [rax+10h], rdi
0x140008407  jz      short loc_140008413
0x140008409  mov     rax, [rax]
0x14000840c  cmp     rax, rcx
0x14000840f  jnz     short loc_140008403
0x140008411  jmp     short loc_14000843D
0x140008413  mov     rbx, rax
0x140008416  mov     rcx, cs:WPP_GLOBAL_Control
0x14000841d  cmp     rcx, r14
0x140008420  jz      short loc_14000843D
0x140008422  test    byte ptr [rcx+1Ch], 4
0x140008426  jz      short loc_14000843D
0x140008428  mov     rcx, [rcx+10h]
0x14000842c  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x140008433  mov     edx, 4Fh ; 'O'
0x140008438  call    WPP_SF_
0x14000843d  lea     rcx, SRWLock; SRWLock
0x140008444  call    cs:__imp_ReleaseSRWLockShared
0x14000844a  test    rbx, rbx
0x14000844d  jnz     short loc_140008461
0x14000844f  mov     ecx, 5; dwMilliseconds
0x140008454  mov     ebx, 0C0000022h
0x140008459  call    cs:__imp_Sleep
0x14000845f  jmp     short loc_140008466
0x140008461  mov     [rsi], rbx
0x140008464  xor     ebx, ebx
0x140008466  mov     rcx, cs:WPP_GLOBAL_Control
0x14000846d  cmp     rcx, r14
0x140008470  jz      short loc_140008490
0x140008472  test    byte ptr [rcx+1Ch], 4
0x140008476  jz      short loc_140008490
0x140008478  mov     rcx, [rcx+10h]
0x14000847c  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x140008483  mov     edx, 51h ; 'Q'
0x140008488  mov     r9d, ebx
0x14000848b  call    WPP_SF_d
0x140008490  mov     eax, ebx
0x140008492  add     rsp, 28h
0x140008496  pop     r14
0x140008498  pop     rdi
0x140008499  pop     rsi
0x14000849a  pop     rbx
0x14000849b  retn
```
