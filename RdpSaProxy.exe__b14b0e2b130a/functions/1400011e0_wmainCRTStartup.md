# __wmainCRTStartup

- ea: `0x1400011e0`
- end: `0x14000143f`
- name: `__wmainCRTStartup`
- size: `607`
- prototype: `int()`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001450`

## callees

- `0x1400011e0`
- `0x1400015ce`
- `0x140001680`
- `0x1400016f0`
- `0x140001857`
- `0x14000186f`
- `0x140002944`
- `0x140005730`

## import_xrefs

- `msvcrt!_cexit` at `0x1400013d1`
- `msvcrt!_cexit` at `0x140001422`
- `msvcrt!_cexit` at `0x1400013d1`
- `msvcrt!_cexit` at `0x140001422`
- `msvcrt!_exit` at `0x140001412`
- `msvcrt!_exit` at `0x140001412`
- `msvcrt!exit` at `0x1400013c2`
- `msvcrt!exit` at `0x1400013c2`
- `msvcrt!_wcmdln` at `0x140001344`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000124a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000124a`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001212`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001212`

## pseudocode

```c
int _wmainCRTStartup()
{
  BOOL v0; // esi
  PVOID StackBase; // rbx
  int v2; // r14d
  signed __int64 v3; // rax
  __int64 *v4; // rdi
  int v5; // eax
  int result; // eax
  wchar_t *v7; // rcx
  WCHAR v8; // ax
  int wShowWindow; // r9d
  _STARTUPINFOW StartupInfo; // [rsp+40h] [rbp-A8h] BYREF

  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo, 0, 0x64u);
  v0 = 0;
  GetStartupInfoW(&StartupInfo);
  StackBase = NtCurrentTeb()->NtTib.StackBase;
  v2 = 0;
  while ( 1 )
  {
    v3 = _InterlockedCompareExchange64(&_native_startup_lock, (signed __int64)StackBase, 0);
    if ( !v3 )
      break;
    if ( (PVOID)v3 == StackBase )
    {
      v2 = 1;
      break;
    }
    Sleep(0x3E8u);
  }
  if ( _native_startup_state == 1 )
  {
    amsg_exit_0(31);
LABEL_18:
    if ( _native_startup_state == 1 )
    {
      initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
      _native_startup_state = 2;
    }
    if ( !v2 )
      _InterlockedExchange64(&_native_startup_lock, 0);
    if ( _dyn_tls_init_callback && (unsigned int)IsNonwritableInCurrentImage(&_dyn_tls_init_callback) )
      _guard_dispatch_icall_fptr();
    v7 = _wcmdln;
    if ( !_wcmdln )
      return 255;
    while ( 1 )
    {
      v8 = *v7;
      if ( *v7 <= 0x20u && (!v8 || !v0) )
        break;
      if ( v8 == 34 )
        v0 = !v0;
      ++v7;
    }
    while ( (unsigned __int16)(v8 - 1) <= 0x1Fu )
      v8 = *++v7;
    wShowWindow = 10;
    if ( (StartupInfo.dwFlags & 1) != 0 )
      wShowWindow = StartupInfo.wShowWindow;
    result = wWinMain(&_ImageBase, 0, v7, wShowWindow);
    dword_14000B1E0 = result;
    if ( !dword_14000B200 )
      exit(result);
    if ( !dword_14000B1E4 )
    {
      _cexit();
      return dword_14000B1E0;
    }
    return result;
  }
  if ( _native_startup_state )
  {
    dword_14000B1E4 = 1;
    goto LABEL_18;
  }
  _native_startup_state = 1;
  v4 = &_xi_a;
  v5 = 0;
  while ( v4 < &_xi_z )
  {
    if ( v5 )
      return 255;
    if ( *v4 )
      v5 = _guard_dispatch_icall_fptr();
    ++v4;
  }
  if ( !v5 )
    goto LABEL_18;
  return 255;
}

```

## disassembly

```asm
0x1400011e0  push    rbx
0x1400011e2  push    rsi
0x1400011e3  push    rdi
0x1400011e4  push    r12
0x1400011e6  push    r14
0x1400011e8  push    r15
0x1400011ea  sub     rsp, 0B8h
0x1400011f1  xor     eax, eax
0x1400011f3  mov     dword ptr [rsp+0E8h+StartupInfo+4], eax
0x1400011f7  xor     edx, edx; Val
0x1400011f9  lea     r8d, [rax+64h]; Size
0x1400011fd  lea     rcx, [rsp+0E8h+StartupInfo]; void *
0x140001202  call    memset_0
0x140001207  xor     r15d, r15d
0x14000120a  mov     esi, r15d
0x14000120d  lea     rcx, [rsp+0E8h+StartupInfo]; lpStartupInfo
0x140001212  call    cs:__imp_GetStartupInfoW
0x140001218  nop
0x140001219  mov     rax, gs:30h
0x140001222  mov     rbx, [rax+8]
0x140001226  mov     r14d, r15d
0x140001229  xor     eax, eax
0x14000122b  lock cmpxchg cs:__native_startup_lock, rbx
0x140001234  jz      short loc_140001252
0x140001236  cmp     rax, rbx
0x140001239  jnz     short loc_140001245
0x14000123b  mov     ebx, 1
0x140001240  mov     r14d, ebx
0x140001243  jmp     short loc_140001257
0x140001245  mov     ecx, 3E8h; dwMilliseconds
0x14000124a  call    cs:__imp_Sleep
0x140001250  jmp     short loc_140001229
0x140001252  mov     ebx, 1
0x140001257  mov     eax, cs:__native_startup_state
0x14000125d  cmp     eax, ebx
0x14000125f  jnz     short loc_14000126F
0x140001261  mov     edi, 1Fh
0x140001266  mov     ecx, edi
0x140001268  call    _amsg_exit_0
0x14000126d  jmp     short loc_1400012DB
0x14000126f  mov     eax, cs:__native_startup_state
0x140001275  test    eax, eax
0x140001277  jnz     short loc_1400012D0
0x140001279  mov     cs:__native_startup_state, ebx
0x14000127f  lea     r12, __xi_z
0x140001286  lea     rdi, __xi_a
0x14000128d  mov     [rsp+0E8h+var_B0], rdi
0x140001292  mov     eax, r15d
0x140001295  mov     [rsp+0E8h+var_C8], eax
0x140001299  cmp     rdi, r12
0x14000129c  jnb     short loc_1400012C2
0x14000129e  test    eax, eax
0x1400012a0  jnz     short loc_1400012C6
0x1400012a2  cmp     [rdi], r15
0x1400012a5  jz      short loc_1400012B7
0x1400012a7  mov     rax, [rdi]
0x1400012aa  mov     rcx, cs:__guard_dispatch_icall_fptr
0x1400012b1  call    rcx ; _guard_dispatch_icall_nop
0x1400012b3  mov     [rsp+0E8h+var_C8], eax
0x1400012b7  add     rdi, 8
0x1400012bb  mov     [rsp+0E8h+var_B0], rdi
0x1400012c0  jmp     short loc_140001299
0x1400012c2  test    eax, eax
0x1400012c4  jz      short loc_1400012D6
0x1400012c6  mov     eax, 0FFh
0x1400012cb  jmp     loc_14000142E
0x1400012d0  mov     cs:dword_14000B1E4, ebx
0x1400012d6  mov     edi, 1Fh
0x1400012db  mov     eax, cs:__native_startup_state
0x1400012e1  cmp     eax, ebx
0x1400012e3  jnz     short loc_140001302
0x1400012e5  lea     rdx, __xc_z; Last
0x1400012ec  lea     rcx, __xc_a; First
0x1400012f3  call    _initterm_0
0x1400012f8  mov     cs:__native_startup_state, 2
0x140001302  test    r14d, r14d
0x140001305  jnz     short loc_140001311
0x140001307  mov     rax, r15
0x14000130a  xchg    rax, cs:__native_startup_lock
0x140001311  cmp     cs:__dyn_tls_init_callback, r15
0x140001318  jz      short loc_140001344
0x14000131a  lea     rcx, __dyn_tls_init_callback
0x140001321  call    _IsNonwritableInCurrentImage
0x140001326  test    eax, eax
0x140001328  jz      short loc_140001344
0x14000132a  xor     r8d, r8d
0x14000132d  lea     edx, [r8+2]
0x140001331  xor     ecx, ecx
0x140001333  mov     rax, cs:__dyn_tls_init_callback
0x14000133a  mov     r9, cs:__guard_dispatch_icall_fptr
0x140001341  call    r9 ; _guard_dispatch_icall_nop
0x140001344  mov     rax, cs:__imp__wcmdln
0x14000134b  mov     rcx, [rax]
0x14000134e  test    rcx, rcx
0x140001351  jnz     short loc_14000135D
0x140001353  mov     eax, 0FFh
0x140001358  jmp     loc_14000142E
0x14000135d  mov     [rsp+0E8h+var_C0], rcx
0x140001362  movzx   eax, word ptr [rcx]
0x140001365  cmp     ax, 20h ; ' '
0x140001369  ja      short loc_1400013DF
0x14000136b  test    ax, ax
0x14000136e  jz      short loc_140001374
0x140001370  test    esi, esi
0x140001372  jnz     short loc_1400013DF
0x140001374  sub     ax, bx
0x140001377  cmp     ax, di
0x14000137a  ja      short loc_14000138A
0x14000137c  add     rcx, 2
0x140001380  mov     [rsp+0E8h+var_C0], rcx
0x140001385  movzx   eax, word ptr [rcx]
0x140001388  jmp     short loc_140001374
0x14000138a  test    byte ptr [rsp+0E8h+StartupInfo.dwFlags], bl
0x14000138e  movzx   eax, [rsp+0E8h+StartupInfo.wShowWindow]
0x140001396  mov     r9d, 0Ah
0x14000139c  cmovnz  r9d, eax; nShowCmd
0x1400013a0  mov     r8, rcx; lpCmdLine
0x1400013a3  xor     edx, edx; hPrevInstance
0x1400013a5  lea     rcx, __ImageBase; hInstance
0x1400013ac  call    wWinMain
0x1400013b1  mov     cs:dword_14000B1E0, eax
0x1400013b7  cmp     cs:dword_14000B200, r15d
0x1400013be  jnz     short loc_1400013C8
0x1400013c0  mov     ecx, eax; Code
0x1400013c2  call    cs:__imp_exit
0x1400013c8  cmp     cs:dword_14000B1E4, r15d
0x1400013cf  jnz     short loc_1400013DD
0x1400013d1  call    cs:__imp__cexit
0x1400013d7  mov     eax, cs:dword_14000B1E0
0x1400013dd  jmp     short loc_14000142E
0x1400013df  cmp     ax, 22h ; '"'
0x1400013e3  jnz     short loc_1400013F3
0x1400013e5  mov     eax, r15d
0x1400013e8  test    esi, esi
0x1400013ea  setz    al
0x1400013ed  mov     esi, eax
0x1400013ef  mov     [rsp+0E8h+var_B8], eax
0x1400013f3  add     rcx, 2
0x1400013f7  mov     [rsp+0E8h+var_C0], rcx
0x1400013fc  jmp     loc_140001362
0x140001401  mov     cs:dword_14000B1E0, eax
0x140001407  cmp     cs:dword_14000B200, 0
0x14000140e  jnz     short loc_140001419
0x140001410  mov     ecx, eax; Code
0x140001412  call    cs:__imp__exit
0x140001419  cmp     cs:dword_14000B1E4, 0
0x140001420  jnz     short loc_14000142E
0x140001422  call    cs:__imp__cexit
0x140001428  mov     eax, cs:dword_14000B1E0
0x14000142e  add     rsp, 0B8h
0x140001435  pop     r15
0x140001437  pop     r14
0x140001439  pop     r12
0x14000143b  pop     rdi
0x14000143c  pop     rsi
0x14000143d  pop     rbx
0x14000143e  retn
0x1400057a0  push    rbp
0x1400057a2  sub     rsp, 20h
0x1400057a6  mov     rbp, rdx
0x1400057a9  mov     rdx, rcx
0x1400057ac  mov     rcx, [rcx]
0x1400057af  mov     ecx, [rcx]
0x1400057b1  call    _XcptFilter_0
0x1400057b6  nop
0x1400057b7  add     rsp, 20h
0x1400057bb  pop     rbp
0x1400057bc  retn
```
