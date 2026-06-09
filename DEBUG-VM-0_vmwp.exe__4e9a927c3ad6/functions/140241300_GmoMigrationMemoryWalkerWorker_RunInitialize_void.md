# GmoMigrationMemoryWalkerWorker::RunInitialize(void)

- ea: `0x140241300`
- end: `0x1402413dd`
- name: `?RunInitialize@GmoMigrationMemoryWalkerWorker@@MEAAXXZ`
- size: `221`
- prototype: `void __fastcall(GmoMigrationMemoryWalkerWorker *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140042240`
- `0x1400549dc`
- `0x140111070`
- `0x140132940`
- `0x140241300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14024136f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14024136f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140241335`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140241335`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x14024134c`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x14024134c`

## pseudocode

```c
void __fastcall GmoMigrationMemoryWalkerWorker::RunInitialize(GmoMigrationMemoryWalkerWorker *this)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  GROUP_AFFINITY GroupAffinity; // [rsp+30h] [rbp-28h] BYREF

  GroupAffinity = *(GROUP_AFFINITY *)(*((_QWORD *)this + 35) + 160LL);
  if ( GroupAffinity.Mask )
  {
    CurrentThread = GetCurrentThread();
    if ( !SetThreadGroupAffinity(CurrentThread, &GroupAffinity, 0) )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
      {
        LastError = GetLastError();
        VmlDebugTraceWithError(16866, &off_1402DB658, LastError);
      }
    }
  }
  else if ( (unsigned int)VmlIsDebugTraceEnabled(33250) )
  {
    VmlDebugTraceEx(33250, &off_1402DB640);
  }
}

```

## disassembly

```asm
0x140241300  push    rbx
0x140241302  sub     rsp, 50h
0x140241306  mov     rax, cs:__security_cookie
0x14024130d  xor     rax, rsp
0x140241310  mov     [rsp+58h+var_18], rax
0x140241315  mov     rax, [rcx+118h]
0x14024131c  mov     rbx, rcx
0x14024131f  movups  xmm0, xmmword ptr [rax+0A0h]
0x140241326  movq    rax, xmm0
0x14024132b  movups  xmmword ptr [rsp+58h+GroupAffinity.Mask], xmm0
0x140241330  test    rax, rax
0x140241333  jz      short loc_14024139E
0x140241335  call    cs:__imp_GetCurrentThread
0x14024133c  nop     dword ptr [rax+rax+00h]
0x140241341  xor     r8d, r8d; PreviousGroupAffinity
0x140241344  lea     rdx, [rsp+58h+GroupAffinity]; GroupAffinity
0x140241349  mov     rcx, rax; hThread
0x14024134c  call    cs:__imp_SetThreadGroupAffinity
0x140241353  nop     dword ptr [rax+rax+00h]
0x140241358  test    eax, eax
0x14024135a  jnz     short loc_1402413C9
0x14024135c  mov     ecx, 41E2h
0x140241361  call    VmlIsDebugTraceEnabled
0x140241366  test    eax, eax
0x140241368  jz      short loc_1402413C9
0x14024136a  movzx   ebx, [rsp+58h+GroupAffinity.Group]
0x14024136f  call    cs:__imp_GetLastError
0x140241376  nop     dword ptr [rax+rax+00h]
0x14024137b  mov     r9d, ebx
0x14024137e  lea     rdx, off_1402DB658; "Failed to set thread affinity group:0x'"...
0x140241385  mov     r8d, eax
0x140241388  mov     ecx, 41E2h
0x14024138d  mov     rax, [rsp+58h+GroupAffinity.Mask]
0x140241392  mov     [rsp+58h+var_38], rax
0x140241397  call    VmlDebugTraceWithError
0x14024139c  jmp     short loc_1402413C9
0x14024139e  mov     ecx, 81E2h
0x1402413a3  call    VmlIsDebugTraceEnabled
0x1402413a8  test    eax, eax
0x1402413aa  jz      short loc_1402413C9
0x1402413ac  mov     rax, [rbx+118h]
0x1402413b3  lea     rdx, off_1402DB640; "Found CPU less NUMA node '%u'."
0x1402413ba  mov     ecx, 81E2h
0x1402413bf  movzx   r8d, byte ptr [rax+78h]
0x1402413c4  call    VmlDebugTraceEx
0x1402413c9  mov     rcx, [rsp+58h+var_18]
0x1402413ce  xor     rcx, rsp; StackCookie
0x1402413d1  call    __security_check_cookie
0x1402413d6  add     rsp, 50h
0x1402413da  pop     rbx
0x1402413db  retn
```
