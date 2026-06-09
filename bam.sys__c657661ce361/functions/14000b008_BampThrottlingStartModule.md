# BampThrottlingStartModule

- ea: `0x14000b008`
- end: `0x14000b206`
- name: `BampThrottlingStartModule`
- size: `510`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140016078`

## callees

- `0x14000b008`
- `0x14000b20c`
- `0x14000b238`
- `0x14000baac`
- `0x14001022c`
- `0x1400113a0`
- `0x1400113f0`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x14000b1b7`
- `ntoskrnl!PsCreateSystemThread` at `0x14000b1b7`

## pseudocode

```c
NTSTATUS BampThrottlingStartModule()
{
  __int64 v0; // rbx
  char *v1; // r8
  char v2; // cl
  unsigned __int64 v3; // rcx
  char v4; // dl
  __int64 v5; // rdi
  __int64 v6; // r9
  _QWORD *v7; // rsi
  _QWORD *v8; // r10
  __int64 v9; // rdx
  PVOID v10; // rcx
  NTSTATUS result; // eax
  struct _CLIENT_ID ClientId; // [rsp+40h] [rbp-38h] BYREF
  __int64 v13; // [rsp+80h] [rbp+8h]

  v0 = (unsigned int)(2 * (HIDWORD(BampThrottledProcessTable) >> 5));
  ClientId = 0;
  if ( (unsigned int)BampThrottledProcessTable >= (unsigned int)v0 )
  {
    if ( (unsigned int)v0 < 4 )
      v0 = 4;
    v1 = (char *)BampAllocateForHashTable(8LL * (unsigned int)v0, 0);
    if ( v1 )
    {
      if ( (((_DWORD)v0 - 1) & (unsigned int)v0) != 0 )
      {
        v2 = -1;
        do
        {
          ++v2;
          LODWORD(v0) = (unsigned int)v0 >> 1;
        }
        while ( (_DWORD)v0 );
        v0 = (unsigned int)(1 << v2);
      }
      if ( (unsigned int)v0 > 0x4000000 )
        v0 = 0x4000000;
      v3 = (unsigned int)v0;
      if ( v1 > &v1[8 * v0] )
        v3 = 0;
      if ( v3 )
        memset64(v1, (unsigned __int64)&BampThrottledProcessTable + 1, v3);
      v4 = BYTE4(BampThrottledProcessTable);
      v5 = 0;
      v6 = -1LL << (BYTE4(BampThrottledProcessTable) & 0x1F);
      if ( (BampThrottledProcessTable & 0xFFFFFFE000000000uLL) != 0 )
      {
        do
        {
          v7 = P;
          while ( 1 )
          {
            v8 = (_QWORD *)v7[v5];
            if ( ((unsigned __int8)v8 & 1) != 0 )
              break;
            v7[v5] = *v8;
            v13 = v6 & v8[1];
            v9 = ((_DWORD)v0 - 1)
               & (HIBYTE(v13)
                + 37
                * (BYTE6(v13)
                 + 37
                 * (BYTE5(v13)
                  + 37
                  * (BYTE4(v13)
                   + 37
                   * (BYTE3(v13)
                    + 37 * (BYTE2(v13) + 37 * (BYTE1(v13) + 37 * ((unsigned int)(unsigned __int8)v13 + 11623883))))))));
            *v8 = *(_QWORD *)&v1[8 * v9];
            *(_QWORD *)&v1[8 * v9] = v8;
          }
          v4 = BYTE4(BampThrottledProcessTable);
          v5 = (unsigned int)(v5 + 1);
        }
        while ( (unsigned int)v5 < HIDWORD(BampThrottledProcessTable) >> 5 );
      }
      v10 = P;
      P = v1;
      HIDWORD(BampThrottledProcessTable) = (32 * v0) | v4 & 0x1F;
      if ( v10 )
        BampFreeForHashTable(v10, 0);
    }
    else if ( (BampThrottledProcessTable & 0xFFFFFFE000000000uLL) == 0 )
    {
      return -1073741801;
    }
  }
  result = PsCreateSystemThread(&Handle, 0x1FFFFFu, 0, 0, &ClientId, BampThrottlingWorker, 0);
  if ( result >= 0 )
  {
    qword_140007580 = (__int64)ClientId.UniqueThread;
    BampReadGlobalThrottlingSettings();
    BampAcquireThrottlingWorkerLock();
    BampQueueGlobalSettingsActionItem();
    BampReleaseThrottlingWorkerLock();
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000b008  push    rbx
0x14000b00a  push    rbp
0x14000b00b  push    rsi
0x14000b00c  push    rdi
0x14000b00d  sub     rsp, 58h
0x14000b011  mov     ebx, dword ptr cs:BampThrottledProcessTable+4
0x14000b017  xorps   xmm0, xmm0
0x14000b01a  shr     ebx, 5
0x14000b01d  add     ebx, ebx
0x14000b01f  cmp     dword ptr cs:BampThrottledProcessTable, ebx
0x14000b025  movups  xmmword ptr [rsp+78h+var_38.UniqueProcess], xmm0
0x14000b02a  jb      loc_14000B186
0x14000b030  mov     eax, 4
0x14000b035  cmp     ebx, eax
0x14000b037  cmovb   ebx, eax
0x14000b03a  xor     edx, edx
0x14000b03c  mov     ecx, ebx
0x14000b03e  shl     rcx, 3
0x14000b042  call    BampAllocateForHashTable
0x14000b047  mov     r8, rax
0x14000b04a  test    rax, rax
0x14000b04d  jz      loc_14000B1F3
0x14000b053  lea     ecx, [rbx-1]
0x14000b056  test    ebx, ecx
0x14000b058  jz      short loc_14000B06E
0x14000b05a  or      ecx, 0FFFFFFFFh
0x14000b05d  test    ebx, ebx
0x14000b05f  jz      short loc_14000B067
0x14000b061  inc     ecx
0x14000b063  shr     ebx, 1
0x14000b065  jnz     short loc_14000B061
0x14000b067  mov     ebx, 1
0x14000b06c  shl     ebx, cl
0x14000b06e  mov     eax, 4000000h
0x14000b073  cmp     ebx, eax
0x14000b075  cmova   ebx, eax
0x14000b078  xor     edx, edx
0x14000b07a  lea     rax, BampThrottledProcessTable
0x14000b081  mov     ecx, ebx
0x14000b083  or      rax, 1
0x14000b087  lea     rdi, [r8+rbx*8]
0x14000b08b  cmp     r8, rdi
0x14000b08e  cmova   ecx, edx
0x14000b091  test    rcx, rcx
0x14000b094  jz      short loc_14000B09C
0x14000b096  mov     rdi, r8
0x14000b099  rep stosq
0x14000b09c  mov     edx, dword ptr cs:BampThrottledProcessTable+4
0x14000b0a2  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000b0a6  mov     ecx, edx
0x14000b0a8  xor     edi, edi
0x14000b0aa  and     ecx, 1Fh
0x14000b0ad  shl     r9, cl
0x14000b0b0  test    edx, 0FFFFFFE0h
0x14000b0b6  jbe     loc_14000B15E
0x14000b0bc  mov     rsi, cs:P
0x14000b0c3  mov     r10, [rsi+rdi*8]
0x14000b0c7  test    r10b, 1
0x14000b0cb  jnz     short loc_14000B149
0x14000b0cd  mov     rax, [r10]
0x14000b0d0  lea     rbp, [rsp+78h+arg_0]
0x14000b0d8  mov     [rsi+rdi*8], rax
0x14000b0dc  mov     rax, [r10+8]
0x14000b0e0  and     rax, r9
0x14000b0e3  mov     [rsp+78h+arg_0], rax
0x14000b0eb  movzx   eax, byte ptr [rbp+0]
0x14000b0ef  add     eax, 0B15DCBh
0x14000b0f4  imul    ecx, eax, 25h ; '%'
0x14000b0f7  movzx   eax, byte ptr [rbp+1]
0x14000b0fb  add     ecx, eax
0x14000b0fd  movzx   eax, byte ptr [rbp+2]
0x14000b101  imul    edx, ecx, 25h ; '%'
0x14000b104  add     edx, eax
0x14000b106  movzx   eax, byte ptr [rbp+3]
0x14000b10a  imul    ecx, edx, 25h ; '%'
0x14000b10d  add     ecx, eax
0x14000b10f  movzx   eax, byte ptr [rbp+4]
0x14000b113  imul    edx, ecx, 25h ; '%'
0x14000b116  add     edx, eax
0x14000b118  movzx   eax, byte ptr [rbp+5]
0x14000b11c  imul    ecx, edx, 25h ; '%'
0x14000b11f  add     ecx, eax
0x14000b121  movzx   eax, byte ptr [rbp+6]
0x14000b125  imul    edx, ecx, 25h ; '%'
0x14000b128  lea     ecx, [rbx-1]
0x14000b12b  add     edx, eax
0x14000b12d  movzx   eax, byte ptr [rbp+7]
0x14000b131  imul    edx, 25h ; '%'
0x14000b134  add     edx, eax
0x14000b136  and     rdx, rcx
0x14000b139  mov     rax, [r8+rdx*8]
0x14000b13d  mov     [r10], rax
0x14000b140  mov     [r8+rdx*8], r10
0x14000b144  jmp     loc_14000B0C3
0x14000b149  mov     edx, dword ptr cs:BampThrottledProcessTable+4
0x14000b14f  inc     edi
0x14000b151  mov     eax, edx
0x14000b153  shr     eax, 5
0x14000b156  cmp     edi, eax
0x14000b158  jb      loc_14000B0BC
0x14000b15e  mov     rcx, cs:P
0x14000b165  and     edx, 1Fh
0x14000b168  shl     ebx, 5
0x14000b16b  or      edx, ebx
0x14000b16d  mov     cs:P, r8
0x14000b174  mov     dword ptr cs:BampThrottledProcessTable+4, edx
0x14000b17a  test    rcx, rcx
0x14000b17d  jz      short loc_14000B186
0x14000b17f  xor     edx, edx
0x14000b181  call    BampFreeForHashTable
0x14000b186  lea     rax, BampThrottlingWorker
0x14000b18d  mov     [rsp+78h+StartContext], 0; StartContext
0x14000b196  mov     [rsp+78h+StartRoutine], rax; StartRoutine
0x14000b19b  lea     rcx, Handle; ThreadHandle
0x14000b1a2  lea     rax, [rsp+78h+var_38]
0x14000b1a7  xor     r9d, r9d; ProcessHandle
0x14000b1aa  xor     r8d, r8d; ObjectAttributes
0x14000b1ad  mov     [rsp+78h+ClientId], rax; ClientId
0x14000b1b2  mov     edx, 1FFFFFh; DesiredAccess
0x14000b1b7  call    cs:__imp_PsCreateSystemThread
0x14000b1be  nop     dword ptr [rax+rax+00h]
0x14000b1c3  test    eax, eax
0x14000b1c5  js      short loc_14000B1E9
0x14000b1c7  mov     rax, [rsp+78h+var_38.UniqueThread]
0x14000b1cc  mov     cs:qword_140007580, rax
0x14000b1d3  call    BampReadGlobalThrottlingSettings
0x14000b1d8  call    BampAcquireThrottlingWorkerLock
0x14000b1dd  call    BampQueueGlobalSettingsActionItem
0x14000b1e2  call    BampReleaseThrottlingWorkerLock
0x14000b1e7  xor     eax, eax
0x14000b1e9  add     rsp, 58h
0x14000b1ed  pop     rdi
0x14000b1ee  pop     rsi
0x14000b1ef  pop     rbp
0x14000b1f0  pop     rbx
0x14000b1f1  retn
0x14000b1f3  test    dword ptr cs:BampThrottledProcessTable+4, 0FFFFFFE0h
0x14000b1fd  jnz     short loc_14000B186
0x14000b1ff  mov     eax, 0C0000017h
0x14000b204  jmp     short loc_14000B1E9
```
