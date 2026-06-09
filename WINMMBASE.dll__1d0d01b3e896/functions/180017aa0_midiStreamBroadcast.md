# midiStreamBroadcast

- ea: `0x180017aa0`
- end: `0x180017b14`
- name: `midiStreamBroadcast`
- size: `116`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180009250`
- `0x180018680`
- `0x180018730`
- `0x1800187a0`
- `0x180018930`
- `0x1800191b0`
- `0x180019270`
- `0x180019b30`
- `0x180019bc0`

## callees

- `0x180017aa0`
- `0x180017cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017ac2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017ac2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017afd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017afd`

## pseudocode

```c
__int64 __fastcall midiStreamBroadcast(__int64 a1, UINT a2, unsigned __int8 *a3, __int64 a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  unsigned int v9; // esi
  __int64 v10; // rdi
  int i; // ebx
  unsigned int v12; // eax

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 - 40);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 - 40));
  v9 = 0;
  v10 = a1 + 32;
  for ( i = *(_DWORD *)(a1 + 28); i; --i )
  {
    if ( (*(_BYTE *)(v10 + 32) & 2) != 0 )
    {
      v12 = midiStreamMessage(v10, a2, a3, a4);
      if ( v12 )
        v9 = v12;
    }
    v10 += 80;
  }
  LeaveCriticalSection(v4);
  return v9;
}

```

## disassembly

```asm
0x180017aa0  push    rbx
0x180017aa2  push    rbp
0x180017aa3  push    rsi
0x180017aa4  push    rdi
0x180017aa5  push    r12
0x180017aa7  push    r14
0x180017aa9  push    r15
0x180017aab  sub     rsp, 20h
0x180017aaf  lea     rbp, [rcx-28h]
0x180017ab3  mov     rbx, rcx
0x180017ab6  mov     rcx, rbp; lpCriticalSection
0x180017ab9  mov     r14, r9
0x180017abc  mov     r15, r8
0x180017abf  mov     r12d, edx
0x180017ac2  call    cs:__imp_EnterCriticalSection
0x180017ac8  xor     esi, esi
0x180017aca  lea     rdi, [rbx+20h]
0x180017ace  mov     ebx, [rbx+1Ch]
0x180017ad1  test    ebx, ebx
0x180017ad3  jz      short loc_180017AFA
0x180017ad5  test    byte ptr [rdi+20h], 2
0x180017ad9  jz      short loc_180017AF1
0x180017adb  mov     r9, r14
0x180017ade  mov     r8, r15
0x180017ae1  mov     edx, r12d
0x180017ae4  mov     rcx, rdi
0x180017ae7  call    midiStreamMessage
0x180017aec  test    eax, eax
0x180017aee  cmovnz  esi, eax
0x180017af1  add     rdi, 50h ; 'P'
0x180017af5  add     ebx, 0FFFFFFFFh
0x180017af8  jnz     short loc_180017AD5
0x180017afa  mov     rcx, rbp; lpCriticalSection
0x180017afd  call    cs:__imp_LeaveCriticalSection
0x180017b03  mov     eax, esi
0x180017b05  add     rsp, 20h
0x180017b09  pop     r15
0x180017b0b  pop     r14
0x180017b0d  pop     r12
0x180017b0f  pop     rdi
0x180017b10  pop     rsi
0x180017b11  pop     rbp
0x180017b12  pop     rbx
0x180017b13  retn
```
