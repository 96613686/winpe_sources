# DMUI_GetUserEditFieldInput

- ea: `0x180007880`
- end: `0x180007a39`
- name: `DMUI_GetUserEditFieldInput`
- size: `441`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const unsigned __int16 *, __int64, unsigned __int16 *, unsigned __int16 *, __int64, _DWORD *, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800019b8`
- `0x180005384`
- `0x18000743c`
- `0x1800074dc`
- `0x180007814`
- `0x180007880`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800079fd`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800079fd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800078ad`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800078ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a10`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007a1f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007a1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800078bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000792b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800078bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000792b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800079d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800079d1`

## pseudocode

```c
__int64 __fastcall DMUI_GetUserEditFieldInput(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        __int64 a7,
        _DWORD *a8,
        _DWORD *a9,
        _QWORD *a10)
{
  unsigned __int64 v10; // rsi
  int v13; // ebp
  int CommandLine; // ebx
  unsigned __int64 v15; // rdx
  int v16; // eax
  unsigned __int64 v17; // rax
  unsigned __int16 *v18; // rax
  __int64 v19; // r11
  unsigned __int16 *v20; // rcx
  unsigned __int16 *i; // rax
  unsigned __int64 v23; // [rsp+30h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-30h] BYREF

  hMem = 0;
  v10 = 0;
  v23 = 0;
  v13 = 0;
  InitializeCriticalSection(&g_csDmUi);
  EnterCriticalSection(&g_csDmUi);
  g_fUserAccepted = 0;
  LeaveCriticalSection(&g_csDmUi);
  CommandLine = CreateCommandLine(a2, a3, a5, a6, 1, (unsigned __int16 **)&hMem);
  if ( CommandLine >= 0 )
  {
    CommandLine = LaunchDmDesktopUI((LPWSTR)hMem);
    if ( CommandLine >= 0 )
    {
      EnterCriticalSection(&g_csDmUi);
      v13 = 1;
      if ( g_pszUserPin )
      {
        v16 = StringCchLengthW(g_pszUserPin, v15, &v23);
        v10 = v23;
        CommandLine = v16;
        if ( v16 >= 0 )
        {
          v10 = v23 + 1;
          v17 = 2 * (v23 + 1);
          if ( !is_mul_ok(v23 + 1, 2u) )
            v17 = -1;
          v18 = (unsigned __int16 *)operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
          if ( v18 )
          {
            CommandLine = StringCchCopyW(v18, v10, g_pszUserPin);
            if ( CommandLine >= 0 )
            {
              *a10 = v19;
              *a9 = g_fUserAccepted;
            }
          }
          else
          {
            CommandLine = -2147024882;
          }
        }
      }
      else
      {
        *a8 = 0;
      }
    }
  }
  LocalFree(hMem);
  v20 = g_pszUserPin;
  if ( g_pszUserPin )
  {
    for ( i = g_pszUserPin; v10; --v10 )
    {
      *(_BYTE *)i = 0;
      i = (unsigned __int16 *)((char *)i + 1);
    }
    operator delete(v20);
  }
  if ( v13 )
    LeaveCriticalSection(&g_csDmUi);
  DeleteCriticalSection(&g_csDmUi);
  return (unsigned int)CommandLine;
}

```

## disassembly

```asm
0x180007880  push    rbx
0x180007882  push    rbp
0x180007883  push    rsi
0x180007884  push    rdi
0x180007885  push    r15
0x180007887  sub     rsp, 40h
0x18000788b  lea     r15, ?g_csDmUi@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csDmUi
0x180007892  mov     [rsp+68h+hMem], 0
0x18000789b  xor     esi, esi
0x18000789d  mov     rcx, r15; lpCriticalSection
0x1800078a0  mov     rbx, r8
0x1800078a3  mov     [rsp+68h+var_38], rsi
0x1800078a8  mov     rdi, rdx
0x1800078ab  xor     ebp, ebp
0x1800078ad  call    cs:__imp_InitializeCriticalSection
0x1800078b4  nop     dword ptr [rax+rax+00h]
0x1800078b9  mov     rcx, r15; lpCriticalSection
0x1800078bc  call    cs:__imp_EnterCriticalSection
0x1800078c3  nop     dword ptr [rax+rax+00h]
0x1800078c8  mov     rcx, r15; lpCriticalSection
0x1800078cb  mov     cs:?g_fUserAccepted@@3HA, esi; int g_fUserAccepted
0x1800078d1  call    cs:__imp_LeaveCriticalSection
0x1800078d8  nop     dword ptr [rax+rax+00h]
0x1800078dd  mov     r9, [rsp+68h+arg_28]; unsigned __int16 *
0x1800078e5  lea     rax, [rsp+68h+hMem]
0x1800078ea  mov     r8, [rsp+68h+arg_20]; unsigned __int16 *
0x1800078f2  mov     rdx, rbx; unsigned __int16 *
0x1800078f5  mov     [rsp+68h+var_40], rax; unsigned __int16 **
0x1800078fa  mov     rcx, rdi; unsigned __int16 *
0x1800078fd  mov     [rsp+68h+var_48], 1; int
0x180007905  call    ?CreateCommandLine@@YAJPEBG000HPEAPEAG@Z; CreateCommandLine(ushort const *,ushort const *,ushort const *,ushort const *,int,ushort * *)
0x18000790a  mov     ebx, eax
0x18000790c  test    eax, eax
0x18000790e  js      loc_1800079CC
0x180007914  mov     rcx, [rsp+68h+hMem]; lpCommandLine
0x180007919  call    ?LaunchDmDesktopUI@@YAJPEAG@Z; LaunchDmDesktopUI(ushort *)
0x18000791e  mov     ebx, eax
0x180007920  test    eax, eax
0x180007922  js      loc_1800079CC
0x180007928  mov     rcx, r15; lpCriticalSection
0x18000792b  call    cs:__imp_EnterCriticalSection
0x180007932  nop     dword ptr [rax+rax+00h]
0x180007937  mov     rcx, cs:?g_pszUserPin@@3PEAGEA; unsigned __int16 *
0x18000793e  lea     ebp, [rsi+1]
0x180007941  test    rcx, rcx
0x180007944  jz      short loc_1800079C2
0x180007946  lea     r8, [rsp+68h+var_38]; unsigned __int64 *
0x18000794b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180007950  mov     rsi, [rsp+68h+var_38]
0x180007955  mov     ebx, eax
0x180007957  test    eax, eax
0x180007959  js      short loc_1800079CC
0x18000795b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007962  lea     eax, [rbp+1]
0x180007965  inc     rsi
0x180007968  mul     rsi
0x18000796b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007972  cmovb   rax, rcx
0x180007976  mov     rcx, rax; unsigned __int64
0x180007979  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000797e  mov     r11, rax
0x180007981  test    rax, rax
0x180007984  jnz     short loc_18000798D
0x180007986  mov     ebx, 8007000Eh
0x18000798b  jmp     short loc_1800079CC
0x18000798d  mov     r8, cs:?g_pszUserPin@@3PEAGEA; unsigned __int16 *
0x180007994  mov     rdx, rsi; unsigned __int64
0x180007997  mov     rcx, r11; unsigned __int16 *
0x18000799a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000799f  mov     ebx, eax
0x1800079a1  test    eax, eax
0x1800079a3  js      short loc_1800079CC
0x1800079a5  mov     rax, [rsp+68h+arg_48]
0x1800079ad  mov     rcx, [rsp+68h+arg_40]
0x1800079b5  mov     [rax], r11
0x1800079b8  mov     eax, cs:?g_fUserAccepted@@3HA; int g_fUserAccepted
0x1800079be  mov     [rcx], eax
0x1800079c0  jmp     short loc_1800079CC
0x1800079c2  mov     rax, [rsp+68h+arg_38]
0x1800079ca  mov     [rax], esi
0x1800079cc  mov     rcx, [rsp+68h+hMem]; hMem
0x1800079d1  call    cs:__imp_LocalFree
0x1800079d8  nop     dword ptr [rax+rax+00h]
0x1800079dd  mov     rcx, cs:?g_pszUserPin@@3PEAGEA; ushort * g_pszUserPin
0x1800079e4  test    rcx, rcx
0x1800079e7  jz      short loc_180007A09
0x1800079e9  mov     rax, rcx
0x1800079ec  test    rsi, rsi
0x1800079ef  jz      short loc_1800079FD
0x1800079f1  mov     byte ptr [rax], 0
0x1800079f4  inc     rax
0x1800079f7  sub     rsi, 1
0x1800079fb  jnz     short loc_1800079F1
0x1800079fd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007a04  nop     dword ptr [rax+rax+00h]
0x180007a09  test    ebp, ebp
0x180007a0b  jz      short loc_180007A1C
0x180007a0d  mov     rcx, r15; lpCriticalSection
0x180007a10  call    cs:__imp_LeaveCriticalSection
0x180007a17  nop     dword ptr [rax+rax+00h]
0x180007a1c  mov     rcx, r15; lpCriticalSection
0x180007a1f  call    cs:__imp_DeleteCriticalSection
0x180007a26  nop     dword ptr [rax+rax+00h]
0x180007a2b  mov     eax, ebx
0x180007a2d  add     rsp, 40h
0x180007a31  pop     r15
0x180007a33  pop     rdi
0x180007a34  pop     rsi
0x180007a35  pop     rbp
0x180007a36  pop     rbx
0x180007a37  retn
```
