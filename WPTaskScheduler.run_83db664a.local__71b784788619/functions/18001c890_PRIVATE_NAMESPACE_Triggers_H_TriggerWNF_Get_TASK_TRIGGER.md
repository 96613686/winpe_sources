# PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::Get(_TASK_TRIGGER *)

- ea: `0x18001c890`
- end: `0x18001c942`
- name: `?Get@TriggerWNF@PRIVATE_NAMESPACE_Triggers_H@@EEAAJPEAU_TASK_TRIGGER@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerWNF *__hidden this, struct _TASK_TRIGGER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000cc50`
- `0x18001c2d8`
- `0x18001c890`

## import_xrefs

- `msvcrt!malloc` at `0x18001c8b2`
- `msvcrt!malloc` at `0x18001c8b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c8e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c8e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c929`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c929`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::Get(
        struct _RTL_CRITICAL_SECTION *this,
        struct _TASK_TRIGGER *a2)
{
  int v4; // ebx
  _OWORD *v5; // rdi
  unsigned __int8 *LockSemaphore; // rcx
  unsigned __int8 *v8; // rax
  int v9; // edx

  if ( a2 )
  {
    v5 = malloc(0x20u);
    if ( v5 )
    {
      v4 = 0;
      EnterCriticalSection(this + 3);
      *v5 = *(_OWORD *)&this[5].LockCount;
      v5[1] = *(_OWORD *)&this[5].LockSemaphore;
      LockSemaphore = (unsigned __int8 *)this[5].LockSemaphore;
      if ( LockSemaphore )
      {
        v8 = Duplicate(LockSemaphore, HIDWORD(this[5].OwningThread));
        v9 = 0;
        *((_QWORD *)v5 + 2) = v8;
        if ( !v8 )
          v9 = -2147024882;
        v4 = v9;
      }
      LeaveCriticalSection(this + 3);
      if ( v4 >= 0 )
      {
        *(_DWORD *)&a2->cbTriggerSize = this[4].DebugInfo;
        *(_QWORD *)&a2->wBeginDay = v5;
        return (unsigned int)v4;
      }
    }
    else
    {
      v4 = -2147024882;
    }
    FreeWnfTrigger((struct _TASK_TRIGGER_WNFSTATE *)v5);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001c890  push    rbx
0x18001c892  push    rbp
0x18001c893  push    rsi
0x18001c894  push    rdi
0x18001c895  push    r14
0x18001c897  sub     rsp, 20h
0x18001c89b  mov     r14, rdx
0x18001c89e  mov     rsi, rcx
0x18001c8a1  test    rdx, rdx
0x18001c8a4  jnz     short loc_18001C8AD
0x18001c8a6  mov     ebx, 80004003h
0x18001c8ab  jmp     short loc_18001C8CD
0x18001c8ad  mov     ecx, 20h ; ' '; Size
0x18001c8b2  call    cs:__imp_malloc
0x18001c8b8  mov     rdi, rax
0x18001c8bb  test    rax, rax
0x18001c8be  jnz     short loc_18001C8DA
0x18001c8c0  mov     ebx, 8007000Eh
0x18001c8c5  mov     rcx, rdi; Block
0x18001c8c8  call    ?FreeWnfTrigger@@YAXPEAU_TASK_TRIGGER_WNFSTATE@@@Z; FreeWnfTrigger(_TASK_TRIGGER_WNFSTATE *)
0x18001c8cd  mov     eax, ebx
0x18001c8cf  add     rsp, 20h
0x18001c8d3  pop     r14
0x18001c8d5  pop     rdi
0x18001c8d6  pop     rsi
0x18001c8d7  pop     rbp
0x18001c8d8  pop     rbx
0x18001c8d9  retn
0x18001c8da  lea     rcx, [rsi+78h]; lpCriticalSection
0x18001c8de  xor     ebx, ebx
0x18001c8e0  call    cs:__imp_EnterCriticalSection
0x18001c8e6  movups  xmm0, xmmword ptr [rsi+0D0h]
0x18001c8ed  movups  xmmword ptr [rdi], xmm0
0x18001c8f0  movups  xmm1, xmmword ptr [rsi+0E0h]
0x18001c8f7  movups  xmmword ptr [rdi+10h], xmm1
0x18001c8fb  mov     rcx, [rsi+0E0h]; Src
0x18001c902  test    rcx, rcx
0x18001c905  jz      short loc_18001C925
0x18001c907  mov     edx, [rsi+0DCh]; Size
0x18001c90d  call    ?Duplicate@@YAPEAEPEAE_K@Z; Duplicate(uchar *,unsigned __int64)
0x18001c912  mov     edx, ebx
0x18001c914  mov     [rdi+10h], rax
0x18001c918  mov     ebx, 8007000Eh
0x18001c91d  test    rax, rax
0x18001c920  cmovz   edx, ebx
0x18001c923  mov     ebx, edx
0x18001c925  lea     rcx, [rsi+78h]; lpCriticalSection
0x18001c929  call    cs:__imp_LeaveCriticalSection
0x18001c92f  test    ebx, ebx
0x18001c931  js      short loc_18001C8C5
0x18001c933  mov     eax, [rsi+0A0h]
0x18001c939  mov     [r14], eax
0x18001c93c  mov     [r14+8], rdi
0x18001c940  jmp     short loc_18001C8CD
```
