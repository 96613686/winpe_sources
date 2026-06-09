# midiDereferenceDevInterfaceById

- ea: `0x1800077ec`
- end: `0x1800078eb`
- name: `midiDereferenceDevInterfaceById`
- size: `255`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1800087a0`
- `0x180009160`
- `0x18000e860`
- `0x180018bb0`
- `0x1800194d0`
- `0x180019740`
- `0x180019bc0`

## callees

- `0x18000233c`
- `0x180002558`
- `0x180007560`
- `0x1800077ec`
- `0x180007d70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000783c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000783c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000787c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000787c`

## pseudocode

```c
void __fastcall midiDereferenceDevInterfaceById(__int64 *a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // rsi
  __int64 v4; // rbx
  int v5; // ebp
  __int64 v6; // rcx
  __int64 v7; // rcx

  v2 = a2;
  if ( a1 == &midioutdrvZ && ValidateHandle(a2, 3) || a1 == &midiindrvZ && ValidateHandle(v2, 4) )
  {
    v7 = *(_QWORD *)(*(_QWORD *)v2 + 96LL);
    if ( v7 )
      wdmDevInterfaceDec(v7);
    return;
  }
  if ( (_DWORD)v2 == -1 )
    MidiMapperInit();
  EnterCriticalSection(&NumDevsCritSec);
  v4 = *a1;
  v5 = 2;
  if ( (_DWORD)v2 == -1 )
  {
    while ( (__int64 *)v4 != a1 )
    {
      if ( (*(_BYTE *)(v4 + 112) & 2) != 0 )
        goto LABEL_13;
      v4 = *(_QWORD *)v4;
    }
  }
  else if ( (__int64 *)v4 != a1 )
  {
    do
    {
      if ( (*(_BYTE *)(v4 + 112) & 2) == 0 )
      {
        if ( *(_DWORD *)(v4 + 88) > (unsigned int)v2 )
          break;
        LODWORD(v2) = v2 - *(_DWORD *)(v4 + 88);
      }
      v4 = *(_QWORD *)v4;
    }
    while ( (__int64 *)v4 != a1 );
    if ( (__int64 *)v4 != a1 )
    {
LABEL_13:
      _InterlockedIncrement((volatile signed __int32 *)(v4 + 92));
      v5 = 0;
      goto LABEL_14;
    }
  }
  v4 = 0;
LABEL_14:
  LeaveCriticalSection(&NumDevsCritSec);
  if ( !v5 )
  {
    v6 = *(_QWORD *)(v4 + 96);
    if ( v6 )
      wdmDevInterfaceDec(v6);
    mregDecUsagePtr((struct _MMDRV *)v4);
  }
}

```

## disassembly

```asm
0x1800077ec  push    rbx
0x1800077ee  push    rbp
0x1800077ef  push    rsi
0x1800077f0  push    rdi
0x1800077f1  sub     rsp, 28h
0x1800077f5  lea     rax, midioutdrvZ
0x1800077fc  mov     rsi, rdx
0x1800077ff  mov     rdi, rcx
0x180007802  cmp     rcx, rax
0x180007805  jz      loc_1800078C3
0x18000780b  lea     rax, midiindrvZ
0x180007812  cmp     rdi, rax
0x180007815  jnz     short loc_18000782C
0x180007817  mov     edx, 4
0x18000781c  mov     rcx, rsi
0x18000781f  call    ValidateHandle
0x180007824  test    eax, eax
0x180007826  jnz     loc_1800078D8
0x18000782c  cmp     esi, 0FFFFFFFFh
0x18000782f  jz      loc_1800078B9
0x180007835  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000783c  call    cs:__imp_EnterCriticalSection
0x180007842  mov     rbx, [rdi]
0x180007845  mov     ebp, 2
0x18000784a  cmp     esi, 0FFFFFFFFh
0x18000784d  jz      short loc_1800078A9
0x18000784f  cmp     rbx, rdi
0x180007852  jz      short loc_1800078AE
0x180007854  test    [rbx+70h], bpl
0x180007858  jnz     short loc_180007862
0x18000785a  cmp     [rbx+58h], esi
0x18000785d  ja      short loc_18000786A
0x18000785f  sub     esi, [rbx+58h]
0x180007862  mov     rbx, [rbx]
0x180007865  cmp     rbx, rdi
0x180007868  jnz     short loc_180007854
0x18000786a  cmp     rbx, rdi
0x18000786d  jz      short loc_1800078AE
0x18000786f  lock inc dword ptr [rbx+5Ch]
0x180007873  xor     ebp, ebp
0x180007875  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000787c  call    cs:__imp_LeaveCriticalSection
0x180007882  test    ebp, ebp
0x180007884  jnz     short loc_180007897
0x180007886  mov     rcx, [rbx+60h]
0x18000788a  test    rcx, rcx
0x18000788d  jnz     short loc_1800078B2
0x18000788f  mov     rcx, rbx; struct _MMDRV *
0x180007892  call    mregDecUsagePtr
0x180007897  add     rsp, 28h
0x18000789b  pop     rdi
0x18000789c  pop     rsi
0x18000789d  pop     rbp
0x18000789e  pop     rbx
0x18000789f  retn
0x1800078a0  test    [rbx+70h], bpl
0x1800078a4  jnz     short loc_18000786F
0x1800078a6  mov     rbx, [rbx]
0x1800078a9  cmp     rbx, rdi
0x1800078ac  jnz     short loc_1800078A0
0x1800078ae  xor     ebx, ebx
0x1800078b0  jmp     short loc_180007875
0x1800078b2  call    wdmDevInterfaceDec
0x1800078b7  jmp     short loc_18000788F
0x1800078b9  call    MidiMapperInit
0x1800078be  jmp     loc_180007835
0x1800078c3  mov     edx, 3
0x1800078c8  mov     rcx, rsi
0x1800078cb  call    ValidateHandle
0x1800078d0  test    eax, eax
0x1800078d2  jz      loc_18000780B
0x1800078d8  mov     rax, [rsi]
0x1800078db  mov     rcx, [rax+60h]
0x1800078df  test    rcx, rcx
0x1800078e2  jz      short loc_180007897
0x1800078e4  call    wdmDevInterfaceDec
0x1800078e9  jmp     short loc_180007897
```
