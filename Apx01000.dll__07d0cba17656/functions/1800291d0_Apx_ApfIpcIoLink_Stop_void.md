# Apx::ApfIpcIoLink::Stop(void)

- ea: `0x1800291d0`
- end: `0x1800292e5`
- name: `?Stop@ApfIpcIoLink@Apx@@UEAAXXZ`
- size: `277`
- prototype: `void __fastcall(Apx::ApfIpcIoLink *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180002100`
- `0x18000a12c`
- `0x180027754`
- `0x1800291d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029246`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029246`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029236`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800292a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029236`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800292a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029219`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002924f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029219`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002924f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002922d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002922d`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLink::Stop(Apx::ApfIpcIoLink *this)
{
  void *v2; // rcx
  void **v3; // rdi
  char *v4; // rbx
  void **v5; // rax
  const struct std::nothrow_t *v6; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = (void *)*((_QWORD *)this + 52);
  *((_BYTE *)this + 432) = 1;
  SetEvent(v2);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  WaitForSingleObject(*((HANDLE *)this + 53), 0xFFFFFFFF);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v3 = (void **)((char *)this + 400);
  while ( 1 )
  {
    v4 = (char *)*v3;
    if ( *v3 == v3 )
      break;
    if ( *((void ***)v4 + 1) != v3 || (v5 = *(void ***)v4, *(char **)(*(_QWORD *)v4 + 8LL) != v4) )
      __fastfail(3u);
    *v3 = v5;
    v5[1] = v3;
    Apx::ApfIpcIoLink::ApfLogEventResult(
      this,
      (struct APF_MESSAGE_EVENT *)(v4 + 16),
      -2147467260,
      "event not sent, queue is in rundown state");
    operator delete(v4, v6);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
  }
}

```

## disassembly

```asm
0x1800291d0  push    rbx
0x1800291d2  push    rbp
0x1800291d3  push    rsi
0x1800291d4  push    rdi
0x1800291d5  push    r14
0x1800291d7  sub     rsp, 20h
0x1800291db  mov     rsi, rcx
0x1800291de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800291e5  lea     r14, WPP_GLOBAL_Control
0x1800291ec  cmp     rcx, r14
0x1800291ef  jz      short loc_180029212
0x1800291f1  test    byte ptr [rcx+1Ch], 1
0x1800291f5  jz      short loc_180029212
0x1800291f7  cmp     byte ptr [rcx+19h], 5
0x1800291fb  jb      short loc_180029212
0x1800291fd  mov     rcx, [rcx+10h]
0x180029201  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180029208  mov     edx, 1Eh
0x18002920d  call    WPP_SF_
0x180029212  lea     rbp, [rsi+10h]
0x180029216  mov     rcx, rbp; lpCriticalSection
0x180029219  call    cs:__imp_EnterCriticalSection
0x18002921f  mov     rcx, [rsi+1A0h]; hEvent
0x180029226  mov     byte ptr [rsi+1B0h], 1
0x18002922d  call    cs:__imp_SetEvent
0x180029233  mov     rcx, rbp; lpCriticalSection
0x180029236  call    cs:__imp_LeaveCriticalSection
0x18002923c  mov     rcx, [rsi+1A8h]; hHandle
0x180029243  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180029246  call    cs:__imp_WaitForSingleObject
0x18002924c  mov     rcx, rbp; lpCriticalSection
0x18002924f  call    cs:__imp_EnterCriticalSection
0x180029255  lea     rdi, [rsi+190h]
0x18002925c  mov     rbx, [rdi]
0x18002925f  cmp     rbx, rdi
0x180029262  jz      short loc_1800292A4
0x180029264  cmp     [rbx+8], rdi
0x180029268  jnz     short loc_18002929D
0x18002926a  mov     rax, [rbx]
0x18002926d  cmp     [rax+8], rbx
0x180029271  jnz     short loc_18002929D
0x180029273  mov     [rdi], rax
0x180029276  lea     rdx, [rbx+10h]; struct APF_MESSAGE_EVENT *
0x18002927a  lea     r9, aEventNotSentQu; "event not sent, queue is in rundown sta"...
0x180029281  mov     [rax+8], rdi
0x180029285  mov     r8d, 80004004h; int
0x18002928b  mov     rcx, rsi; this
0x18002928e  call    ?ApfLogEventResult@ApfIpcIoLink@Apx@@AEAAXPEAUAPF_MESSAGE_EVENT@@JPEBD@Z; Apx::ApfIpcIoLink::ApfLogEventResult(APF_MESSAGE_EVENT *,long,char const *)
0x180029293  mov     rcx, rbx; void *
0x180029296  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002929b  jmp     short loc_18002925C
0x18002929d  mov     ecx, 3
0x1800292a2  int     29h; Win8: RtlFailFast(ecx)
0x1800292a4  mov     rcx, rbp; lpCriticalSection
0x1800292a7  call    cs:__imp_LeaveCriticalSection
0x1800292ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800292b4  cmp     rcx, r14
0x1800292b7  jz      short loc_1800292DA
0x1800292b9  test    byte ptr [rcx+1Ch], 1
0x1800292bd  jz      short loc_1800292DA
0x1800292bf  cmp     byte ptr [rcx+19h], 5
0x1800292c3  jb      short loc_1800292DA
0x1800292c5  mov     rcx, [rcx+10h]
0x1800292c9  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x1800292d0  mov     edx, 1Fh
0x1800292d5  call    WPP_SF_
0x1800292da  add     rsp, 20h
0x1800292de  pop     r14
0x1800292e0  pop     rdi
0x1800292e1  pop     rsi
0x1800292e2  pop     rbp
0x1800292e3  pop     rbx
0x1800292e4  retn
```
