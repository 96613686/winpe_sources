# CHangReport::Lock(wchar_t const *)

- ea: `0x1400207c4`
- end: `0x140020869`
- name: `?Lock@CHangReport@@IEAA?AV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEB_W@Z`
- size: `165`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x14001eafc`
- `0x14001ecd0`
- `0x14001f2dc`
- `0x1400210a8`
- `0x1400214f0`
- `0x140024220`
- `0x140024c90`
- `0x140025bd0`

## callees

- `0x140015138`
- `0x1400207c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002083d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002083d`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1400207e4`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1400207e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002084d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002084d`

## pseudocode

```c
__int64 __fastcall CHangReport::Lock(__int64 a1, __int64 a2, int a3)
{
  _BYTE *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rcx

  v4 = (_BYTE *)(a2 + 8);
  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  *(_BYTE *)(a2 + 8) = 0;
  *(_QWORD *)a2 = v5;
  if ( !TryEnterCriticalSection(v5) )
  {
    *v4 = 0;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        (unsigned int)WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
        a3,
        *(_DWORD *)(a1 + 56));
    }
    if ( !*(_QWORD *)a2 || *v4 )
      __int2c();
    EnterCriticalSection(*(LPCRITICAL_SECTION *)a2);
  }
  *v4 = 1;
  *(_DWORD *)(a1 + 56) = GetCurrentThreadId();
  return a2;
}

```

## disassembly

```asm
0x1400207c4  push    rbx
0x1400207c6  push    rbp
0x1400207c7  push    rsi
0x1400207c8  push    rdi
0x1400207c9  sub     rsp, 38h
0x1400207cd  mov     rsi, rcx
0x1400207d0  lea     rbx, [rdx+8]
0x1400207d4  add     rcx, 10h; lpCriticalSection
0x1400207d8  mov     byte ptr [rbx], 0
0x1400207db  mov     [rdx], rcx
0x1400207de  mov     rbp, r8
0x1400207e1  mov     rdi, rdx
0x1400207e4  call    cs:__imp_TryEnterCriticalSection
0x1400207eb  nop     dword ptr [rax+rax+00h]
0x1400207f0  test    eax, eax
0x1400207f2  jnz     short loc_140020849
0x1400207f4  mov     [rbx], al
0x1400207f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400207fd  lea     rax, WPP_GLOBAL_Control
0x140020804  cmp     rcx, rax
0x140020807  jz      short loc_14002082E
0x140020809  test    byte ptr [rcx+1Ch], 4
0x14002080d  jz      short loc_14002082E
0x14002080f  mov     eax, [rsi+38h]
0x140020812  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140020819  mov     rcx, [rcx+10h]
0x14002081d  mov     edx, 4Fh ; 'O'
0x140020822  mov     r9, rbp
0x140020825  mov     [rsp+58h+var_38], eax
0x140020829  call    WPP_SF_Sd
0x14002082e  mov     rcx, [rdi]; lpCriticalSection
0x140020831  test    rcx, rcx
0x140020834  jz      short loc_14002083B
0x140020836  cmp     byte ptr [rbx], 0
0x140020839  jz      short loc_14002083D
0x14002083b  int     2Ch; Windows NT - assertion failure
0x14002083d  call    cs:__imp_EnterCriticalSection
0x140020844  nop     dword ptr [rax+rax+00h]
0x140020849  mov     al, 1
0x14002084b  mov     [rbx], al
0x14002084d  call    cs:__imp_GetCurrentThreadId
0x140020854  nop     dword ptr [rax+rax+00h]
0x140020859  mov     [rsi+38h], eax
0x14002085c  mov     rax, rdi
0x14002085f  add     rsp, 38h
0x140020863  pop     rdi
0x140020864  pop     rsi
0x140020865  pop     rbp
0x140020866  pop     rbx
0x140020867  retn
```
