# ipx::mtf::CMtfSuggestionClient::AdviseNotifySink(IMtfSuggestionNotify *)

- ea: `0x180015c00`
- end: `0x180015cd4`
- name: `?AdviseNotifySink@CMtfSuggestionClient@mtf@ipx@@UEAAJPEAUIMtfSuggestionNotify@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this, struct IMtfSuggestionNotify *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006074`
- `0x180015c00`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015cbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015cbb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015c17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015c17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015c28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015c28`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::AdviseNotifySink(
        ipx::mtf::CMtfSuggestionClient *this,
        __int64 (***a2)(void))
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  int v5; // ebx
  DWORD CurrentThreadId; // eax
  __int64 result; // rax
  unsigned int v8; // ebx
  const char *v9; // r9
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v5 = *((_DWORD *)this + 50);
  CurrentThreadId = GetCurrentThreadId();
  if ( v5 == CurrentThreadId )
  {
    if ( a2 )
    {
      if ( *((_QWORD *)this + 15) )
      {
        if ( v4 )
          LeaveCriticalSection(v4);
        return 2147549183LL;
      }
      else
      {
        try
        {
          v8 = (**a2)();
          if ( v4 )
            LeaveCriticalSection(v4);
          result = v8;
        }
        catch ( ... )
        {
          return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0x161,
                                 (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                                 v9);
        }
      }
    }
    else
    {
      if ( v4 )
        LeaveCriticalSection(v4);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14F,
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
0x180015c00  push    rbx
0x180015c02  push    rsi
0x180015c03  push    rdi
0x180015c04  push    r14
0x180015c06  sub     rsp, 28h
0x180015c0a  mov     r14, rdx
0x180015c0d  mov     rsi, rcx
0x180015c10  lea     rdi, [rcx+40h]
0x180015c14  mov     rcx, rdi; lpCriticalSection
0x180015c17  call    cs:__imp_EnterCriticalSection
0x180015c1d  mov     [rsp+48h+arg_0], rdi
0x180015c22  mov     ebx, [rsi+0C8h]
0x180015c28  call    cs:__imp_GetCurrentThreadId
0x180015c2e  cmp     ebx, eax
0x180015c30  jz      short loc_180015C63
0x180015c32  mov     rcx, [rsp+48h]; this
0x180015c37  mov     ebx, 8001010Eh
0x180015c3c  mov     r9d, ebx; char *
0x180015c3f  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180015c46  mov     edx, 14Fh; void *
0x180015c4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015c50  nop
0x180015c51  test    rdi, rdi
0x180015c54  jz      short loc_180015C5F
0x180015c56  mov     rcx, rdi; lpCriticalSection
0x180015c59  call    cs:__imp_LeaveCriticalSection
0x180015c5f  mov     eax, ebx
0x180015c61  jmp     short loc_180015CC9
0x180015c63  test    r14, r14
0x180015c66  jnz     short loc_180015C7D
0x180015c68  test    rdi, rdi
0x180015c6b  jz      short loc_180015C76
0x180015c6d  mov     rcx, rdi; lpCriticalSection
0x180015c70  call    cs:__imp_LeaveCriticalSection
0x180015c76  mov     eax, 80070057h
0x180015c7b  jmp     short loc_180015CC9
0x180015c7d  lea     r8, [rsi+78h]
0x180015c81  cmp     qword ptr [r8], 0
0x180015c85  jz      short loc_180015C9C
0x180015c87  test    rdi, rdi
0x180015c8a  jz      short loc_180015C95
0x180015c8c  mov     rcx, rdi; lpCriticalSection
0x180015c8f  call    cs:__imp_LeaveCriticalSection
0x180015c95  mov     eax, 8000FFFFh
0x180015c9a  jmp     short loc_180015CC9
0x180015c9c  mov     rax, [r14]
0x180015c9f  lea     rdx, IID_IMtfSuggestionNotify
0x180015ca6  mov     rcx, r14
0x180015ca9  mov     rax, [rax]
0x180015cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cb1  mov     ebx, eax
0x180015cb3  test    rdi, rdi
0x180015cb6  jz      short loc_180015CC1
0x180015cb8  mov     rcx, rdi; lpCriticalSection
0x180015cbb  call    cs:__imp_LeaveCriticalSection
0x180015cc1  mov     eax, ebx
0x180015cc3  jmp     short loc_180015CC9
0x180015cc5  mov     eax, dword ptr [rsp+48h+arg_0]
0x180015cc9  add     rsp, 28h
0x180015ccd  pop     r14
0x180015ccf  pop     rdi
0x180015cd0  pop     rsi
0x180015cd1  pop     rbx
0x180015cd2  retn
```
