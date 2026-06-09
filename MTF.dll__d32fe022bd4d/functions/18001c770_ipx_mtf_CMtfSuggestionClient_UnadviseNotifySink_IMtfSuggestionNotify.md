# ipx::mtf::CMtfSuggestionClient::UnadviseNotifySink(IMtfSuggestionNotify *)

- ea: `0x18001c770`
- end: `0x18001c82c`
- name: `?UnadviseNotifySink@CMtfSuggestionClient@mtf@ipx@@UEAAJPEAUIMtfSuggestionNotify@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this, struct IMtfSuggestionNotify *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006074`
- `0x18001c770`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c7c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c7fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c810`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c7c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c7fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c810`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c787`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c787`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c798`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c798`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::UnadviseNotifySink(
        ipx::mtf::CMtfSuggestionClient *this,
        struct IMtfSuggestionNotify *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  int v5; // ebx
  DWORD CurrentThreadId; // eax
  const char *v7; // r9
  __int64 result; // rax
  struct IMtfSuggestionNotify *v9; // rcx
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v5 = *((_DWORD *)this + 50);
  CurrentThreadId = GetCurrentThreadId();
  if ( v5 == CurrentThreadId )
  {
    try
    {
      v9 = (struct IMtfSuggestionNotify *)*((_QWORD *)this + 15);
      if ( v9 && v9 == a2 )
      {
        *((_QWORD *)this + 15) = 0;
        (*(void (__fastcall **)(struct IMtfSuggestionNotify *))(*(_QWORD *)v9 + 16LL))(v9);
        if ( v4 )
          LeaveCriticalSection(v4);
        result = 0;
      }
      else
      {
        if ( v4 )
          LeaveCriticalSection(v4);
        result = 2147942487LL;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x182,
                             (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                             v7);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x175,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)0x8001010ELL,
      v10);
    if ( v4 )
      LeaveCriticalSection(v4);
    return 2147549454LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001c770  push    rbx
0x18001c772  push    rsi
0x18001c773  push    rdi
0x18001c774  push    r14
0x18001c776  sub     rsp, 28h
0x18001c77a  mov     r14, rdx
0x18001c77d  mov     rsi, rcx
0x18001c780  lea     rdi, [rcx+40h]
0x18001c784  mov     rcx, rdi; lpCriticalSection
0x18001c787  call    cs:__imp_EnterCriticalSection
0x18001c78d  mov     [rsp+48h+arg_0], rdi
0x18001c792  mov     ebx, [rsi+0C8h]
0x18001c798  call    cs:__imp_GetCurrentThreadId
0x18001c79e  cmp     ebx, eax
0x18001c7a0  jz      short loc_18001C7D3
0x18001c7a2  mov     rcx, [rsp+48h]; this
0x18001c7a7  mov     ebx, 8001010Eh
0x18001c7ac  mov     r9d, ebx; char *
0x18001c7af  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001c7b6  mov     edx, 175h; void *
0x18001c7bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c7c0  nop
0x18001c7c1  test    rdi, rdi
0x18001c7c4  jz      short loc_18001C7CF
0x18001c7c6  mov     rcx, rdi; lpCriticalSection
0x18001c7c9  call    cs:__imp_LeaveCriticalSection
0x18001c7cf  mov     eax, ebx
0x18001c7d1  jmp     short loc_18001C821
0x18001c7d3  mov     rcx, [rsi+78h]
0x18001c7d7  test    rcx, rcx
0x18001c7da  jz      short loc_18001C808
0x18001c7dc  cmp     rcx, r14
0x18001c7df  jnz     short loc_18001C808
0x18001c7e1  mov     qword ptr [rsi+78h], 0
0x18001c7e9  mov     rax, [rcx]
0x18001c7ec  mov     rax, [rax+10h]
0x18001c7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7f5  nop
0x18001c7f6  test    rdi, rdi
0x18001c7f9  jz      short loc_18001C804
0x18001c7fb  mov     rcx, rdi; lpCriticalSection
0x18001c7fe  call    cs:__imp_LeaveCriticalSection
0x18001c804  xor     eax, eax
0x18001c806  jmp     short loc_18001C821
0x18001c808  test    rdi, rdi
0x18001c80b  jz      short loc_18001C816
0x18001c80d  mov     rcx, rdi; lpCriticalSection
0x18001c810  call    cs:__imp_LeaveCriticalSection
0x18001c816  mov     eax, 80070057h
0x18001c81b  jmp     short loc_18001C821
0x18001c81d  mov     eax, dword ptr [rsp+48h+arg_0]
0x18001c821  add     rsp, 28h
0x18001c825  pop     r14
0x18001c827  pop     rdi
0x18001c828  pop     rsi
0x18001c829  pop     rbx
0x18001c82a  retn
```
