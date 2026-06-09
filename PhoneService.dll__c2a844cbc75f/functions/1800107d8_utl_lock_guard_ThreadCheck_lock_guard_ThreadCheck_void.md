# utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>(void)

- ea: `0x1800107d8`
- end: `0x180010844`
- name: `??1?$lock_guard@VThreadCheck@@@utl@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(volatile __int32 **)`
- caller_count: `48`
- callee_count: `2`
- tags: ``

## callers

- `0x180011f70`
- `0x180011ff0`
- `0x1800123e0`
- `0x180012610`
- `0x180012ae0`
- `0x180012cb0`
- `0x180012d40`
- `0x180012e40`
- `0x180016510`
- `0x1800167e0`
- `0x180017070`
- `0x180025a10`
- `0x18002bc80`
- `0x180034b10`
- `0x180034e08`
- `0x18003541c`
- `0x18003a744`
- `0x1800404a0`
- `0x180043c58`
- `0x180048a68`
- `0x18004a790`
- `0x180051ca4`
- `0x180051e44`
- `0x180052008`
- `0x180052338`
- `0x180052424`
- `0x1800524c8`
- `0x1800525f8`
- `0x180052778`
- `0x18005292c`
- `0x180052a58`
- `0x180052abc`
- `0x180052b5c`
- `0x180052bf4`
- `0x180052ca8`
- `0x180052d3c`
- `0x180053040`
- `0x180053254`
- `0x18005337c`
- `0x18005354c`
- `0x1800536ac`
- `0x180053718`
- `0x1800539a8`
- `0x180056d30`
- `0x180057060`
- `0x180065c04`
- `0x180068d60`
- `0x18006b2c0`

## callees

- `0x1800107d8`
- `0x180010f8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010811`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010811`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800107eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800107eb`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x18001081a`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x18001081a`

## string_xrefs

- `0x1800107fb`: `onecoreuap\internal\net\inc\ThreadCheck.h`
- `0x18001082b`: `onecoreuap\internal\net\inc\ThreadCheck.h`

## pseudocode

```c
void __fastcall utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>(volatile __int32 **a1)
{
  volatile __int32 *v1; // rbx
  __int64 v3; // rcx
  DWORD CurrentThreadId; // edi
  HANDLE CurrentThread; // rax
  __int64 v6; // rcx

  v1 = *a1;
  if ( (*((_DWORD *)*a1 + 1))-- == 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    if ( !CurrentThreadId )
    {
      Log_AssertionEvent_1(v3, "onecoreuap\\internal\\net\\inc\\ThreadCheck.h", 64);
      __int2c();
    }
    if ( _InterlockedExchange(v1, 0) != CurrentThreadId )
    {
      CurrentThread = GetCurrentThread();
      if ( SuspendThread(CurrentThread) == -1 )
      {
        Log_AssertionEvent_1(v6, "onecoreuap\\internal\\net\\inc\\ThreadCheck.h", 76);
        __int2c();
      }
    }
  }
}

```

## disassembly

```asm
0x1800107d8  mov     [rsp+arg_8], rbx
0x1800107dd  push    rdi
0x1800107de  sub     rsp, 20h
0x1800107e2  mov     rbx, [rcx]
0x1800107e5  add     dword ptr [rbx+4], 0FFFFFFFFh
0x1800107e9  jnz     short loc_180010839
0x1800107eb  call    cs:__imp_GetCurrentThreadId
0x1800107f1  mov     edi, eax
0x1800107f3  test    eax, eax
0x1800107f5  jnz     short loc_180010809
0x1800107f7  lea     r8d, [rax+40h]
0x1800107fb  lea     rdx, aOnecoreuapInte_4; "onecoreuap\\internal\\net\\inc\\ThreadC"...
0x180010802  call    Log_AssertionEvent_1
0x180010807  int     2Ch; Windows NT - assertion failure
0x180010809  xor     ecx, ecx
0x18001080b  xchg    ecx, [rbx]
0x18001080d  cmp     ecx, edi
0x18001080f  jz      short loc_180010839
0x180010811  call    cs:__imp_GetCurrentThread
0x180010817  mov     rcx, rax; hThread
0x18001081a  call    cs:__imp_SuspendThread
0x180010820  cmp     eax, 0FFFFFFFFh
0x180010823  jnz     short loc_180010839
0x180010825  mov     r8d, 4Ch ; 'L'
0x18001082b  lea     rdx, aOnecoreuapInte_4; "onecoreuap\\internal\\net\\inc\\ThreadC"...
0x180010832  call    Log_AssertionEvent_1
0x180010837  int     2Ch; Windows NT - assertion failure
0x180010839  mov     rbx, [rsp+28h+arg_8]
0x18001083e  add     rsp, 20h
0x180010842  pop     rdi
0x180010843  retn
```
