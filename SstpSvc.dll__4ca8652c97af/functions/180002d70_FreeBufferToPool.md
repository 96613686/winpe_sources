# FreeBufferToPool

- ea: `0x180002d70`
- end: `0x180002dec`
- name: `FreeBufferToPool`
- size: `124`
- prototype: `void __fastcall(__int64, __int64, char)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180001240`
- `0x180001a80`
- `0x180001ee0`
- `0x1800021f0`
- `0x180002908`
- `0x180002e00`
- `0x1800045b0`
- `0x180004bc0`
- `0x180006b64`
- `0x1800093ac`
- `0x180009a00`
- `0x18000a620`
- `0x18000bc78`
- `0x18000cba4`

## callees

- `0x180002d70`
- `0x1800077bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002dcc`

## pseudocode

```c
void __fastcall FreeBufferToPool(__int64 a1, __int64 a2, char a3)
{
  _QWORD *v4; // rdi
  __int64 v6; // rax

  v4 = (_QWORD *)(a2 - 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  if ( (_QWORD *)*v4 == v4 )
  {
    v6 = *(_QWORD *)(a1 + 40);
    *v4 = v6;
    v4[1] = a1 + 40;
    *(_QWORD *)(v6 + 8) = v4;
    *(_QWORD *)(a1 + 40) = v4;
    ++*(_DWORD *)(v4[2] + 28LL);
    if ( a3 )
    {
      if ( ++*(_DWORD *)(a1 + 20) >= *(_DWORD *)(a1 + 16) )
      {
        FreeUnusedBufferPoolBlocks(a1);
        *(_DWORD *)(a1 + 20) = 0;
      }
    }
  }
  else
  {
    ++g_ulDoubleBufferFrees;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
}

```

## disassembly

```asm
0x180002d70  push    rbx
0x180002d72  push    rbp
0x180002d73  push    rsi
0x180002d74  push    rdi
0x180002d75  sub     rsp, 28h
0x180002d79  mov     rbx, rcx
0x180002d7c  lea     rdi, [rdx-18h]
0x180002d80  add     rcx, 40h ; '@'; lpCriticalSection
0x180002d84  movzx   ebp, r8b
0x180002d88  call    cs:__imp_EnterCriticalSection
0x180002d8e  cmp     [rdi], rdi
0x180002d91  jnz     short loc_180002DD3
0x180002d93  mov     rax, [rbx+28h]
0x180002d97  lea     rcx, [rbx+28h]
0x180002d9b  mov     [rdi], rax
0x180002d9e  mov     [rdi+8], rcx
0x180002da2  mov     [rax+8], rdi
0x180002da6  mov     [rcx], rdi
0x180002da9  mov     rax, [rdi+10h]
0x180002dad  inc     dword ptr [rax+1Ch]
0x180002db0  test    bpl, bpl
0x180002db3  jz      short loc_180002DC0
0x180002db5  inc     dword ptr [rbx+14h]
0x180002db8  mov     eax, [rbx+14h]
0x180002dbb  cmp     eax, [rbx+10h]
0x180002dbe  jnb     short loc_180002DDB
0x180002dc0  lea     rcx, [rbx+40h]
0x180002dc4  add     rsp, 28h
0x180002dc8  pop     rdi
0x180002dc9  pop     rsi
0x180002dca  pop     rbp
0x180002dcb  pop     rbx
0x180002dcc  jmp     cs:__imp_LeaveCriticalSection
0x180002dd3  inc     cs:g_ulDoubleBufferFrees
0x180002dd9  jmp     short loc_180002DC0
0x180002ddb  mov     rcx, rbx
0x180002dde  call    FreeUnusedBufferPoolBlocks
0x180002de3  mov     dword ptr [rbx+14h], 0
0x180002dea  jmp     short loc_180002DC0
```
