# ATL::CAtlWinModule::ExtractCreateWndData(void)

- ea: `0x180007e8c`
- end: `0x180007f01`
- name: `?ExtractCreateWndData@CAtlWinModule@ATL@@QEAAPEAXXZ`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlWinModule *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800091d0`

## callees

- `0x180007e8c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180007e9d`
- `KERNEL32!EnterCriticalSection` at `0x180007e9d`
- `KERNEL32!LeaveCriticalSection` at `0x180007eed`
- `KERNEL32!LeaveCriticalSection` at `0x180007eed`
- `KERNEL32!GetCurrentThreadId` at `0x180007eb1`
- `KERNEL32!GetCurrentThreadId` at `0x180007eb1`

## pseudocode

```c
__int64 __fastcall ATL::CAtlWinModule::ExtractCreateWndData(ATL::CAtlWinModule *this)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  DWORD CurrentThreadId; // edx
  __int64 v4; // rcx
  __int64 v5; // rax

  EnterCriticalSection(&stru_1800503B8);
  v1 = qword_1800503E0;
  v2 = 0;
  if ( qword_1800503E0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = 0;
    while ( 1 )
    {
      v5 = *(_QWORD *)(v1 + 16);
      if ( *(_DWORD *)(v1 + 8) == CurrentThreadId )
        break;
      v4 = v1;
      v1 = *(_QWORD *)(v1 + 16);
      if ( !v5 )
        goto LABEL_10;
    }
    if ( v4 )
      *(_QWORD *)(v4 + 16) = v5;
    else
      qword_1800503E0 = *(_QWORD *)(v1 + 16);
    v2 = *(_QWORD *)v1;
  }
LABEL_10:
  LeaveCriticalSection(&stru_1800503B8);
  return v2;
}

```

## disassembly

```asm
0x180007e8c  mov     [rsp+arg_0], rbx
0x180007e91  push    rdi
0x180007e92  sub     rsp, 20h
0x180007e96  lea     rcx, stru_1800503B8; lpCriticalSection
0x180007e9d  call    cs:__imp_EnterCriticalSection
0x180007ea3  mov     rbx, cs:qword_1800503E0
0x180007eaa  xor     edi, edi
0x180007eac  test    rbx, rbx
0x180007eaf  jz      short loc_180007EE6
0x180007eb1  call    cs:__imp_GetCurrentThreadId
0x180007eb7  mov     edx, eax
0x180007eb9  xor     ecx, ecx
0x180007ebb  mov     rax, [rbx+10h]
0x180007ebf  cmp     [rbx+8], edx
0x180007ec2  jz      short loc_180007ED1
0x180007ec4  mov     rcx, rbx
0x180007ec7  mov     rbx, rax
0x180007eca  test    rax, rax
0x180007ecd  jnz     short loc_180007EBB
0x180007ecf  jmp     short loc_180007EE6
0x180007ed1  test    rcx, rcx
0x180007ed4  jnz     short loc_180007EDF
0x180007ed6  mov     cs:qword_1800503E0, rax
0x180007edd  jmp     short loc_180007EE3
0x180007edf  mov     [rcx+10h], rax
0x180007ee3  mov     rdi, [rbx]
0x180007ee6  lea     rcx, stru_1800503B8; lpCriticalSection
0x180007eed  call    cs:__imp_LeaveCriticalSection
0x180007ef3  mov     rbx, [rsp+28h+arg_0]
0x180007ef8  mov     rax, rdi
0x180007efb  add     rsp, 20h
0x180007eff  pop     rdi
0x180007f00  retn
```
