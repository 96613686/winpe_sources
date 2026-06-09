# __wmainCRTStartup

- ea: `0x1400012c0`
- end: `0x14000151f`
- name: `__wmainCRTStartup`
- size: `607`
- prototype: `int()`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001530`

## callees

- `0x1400012c0`
- `0x1400016ce`
- `0x140001780`
- `0x1400017e0`
- `0x140001947`
- `0x14000195f`
- `0x140003eb4`
- `0x140006bd0`

## import_xrefs

- `msvcrt!_wcmdln` at `0x140001424`
- `msvcrt!_cexit` at `0x1400014b1`
- `msvcrt!_cexit` at `0x140001502`
- `msvcrt!_cexit` at `0x1400014b1`
- `msvcrt!_cexit` at `0x140001502`
- `msvcrt!_exit` at `0x1400014f2`
- `msvcrt!_exit` at `0x1400014f2`
- `msvcrt!exit` at `0x1400014a2`
- `msvcrt!exit` at `0x1400014a2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000132a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000132a`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x1400012f2`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x1400012f2`

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
    result = wWinMain((HINSTANCE)0x140000000LL, 0, v7, wShowWindow);
    dword_14000C140 = result;
    if ( !dword_14000C160 )
      exit(result);
    if ( !dword_14000C144 )
    {
      _cexit();
      return dword_14000C140;
    }
    return result;
  }
  if ( _native_startup_state )
  {
    dword_14000C144 = 1;
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
0x1400012c0  push    rbx
0x1400012c2  push    rsi
0x1400012c3  push    rdi
0x1400012c4  push    r12
0x1400012c6  push    r14
0x1400012c8  push    r15
0x1400012ca  sub     rsp, 0B8h
0x1400012d1  xor     eax, eax
0x1400012d3  mov     dword ptr [rsp+0E8h+StartupInfo+4], eax
0x1400012d7  xor     edx, edx; Val
0x1400012d9  lea     r8d, [rax+64h]; Size
0x1400012dd  lea     rcx, [rsp+0E8h+StartupInfo]; void *
0x1400012e2  call    memset_0
0x1400012e7  xor     r15d, r15d
0x1400012ea  mov     esi, r15d
0x1400012ed  lea     rcx, [rsp+0E8h+StartupInfo]; lpStartupInfo
0x1400012f2  call    cs:__imp_GetStartupInfoW
0x1400012f8  nop
0x1400012f9  mov     rax, gs:30h
0x140001302  mov     rbx, [rax+8]
0x140001306  mov     r14d, r15d
0x140001309  xor     eax, eax
0x14000130b  lock cmpxchg cs:__native_startup_lock, rbx
0x140001314  jz      short loc_140001332
0x140001316  cmp     rax, rbx
0x140001319  jnz     short loc_140001325
0x14000131b  mov     ebx, 1
0x140001320  mov     r14d, ebx
0x140001323  jmp     short loc_140001337
0x140001325  mov     ecx, 3E8h; dwMilliseconds
0x14000132a  call    cs:__imp_Sleep
0x140001330  jmp     short loc_140001309
0x140001332  mov     ebx, 1
0x140001337  mov     eax, cs:__native_startup_state
0x14000133d  cmp     eax, ebx
0x14000133f  jnz     short loc_14000134F
0x140001341  mov     edi, 1Fh
0x140001346  mov     ecx, edi
0x140001348  call    _amsg_exit_0
0x14000134d  jmp     short loc_1400013BB
0x14000134f  mov     eax, cs:__native_startup_state
0x140001355  test    eax, eax
0x140001357  jnz     short loc_1400013B0
0x140001359  mov     cs:__native_startup_state, ebx
0x14000135f  lea     r12, __xi_z
0x140001366  lea     rdi, __xi_a
0x14000136d  mov     [rsp+0E8h+var_B0], rdi
0x140001372  mov     eax, r15d
0x140001375  mov     [rsp+0E8h+var_C8], eax
0x140001379  cmp     rdi, r12
0x14000137c  jnb     short loc_1400013A2
0x14000137e  test    eax, eax
0x140001380  jnz     short loc_1400013A6
0x140001382  cmp     [rdi], r15
0x140001385  jz      short loc_140001397
0x140001387  mov     rax, [rdi]
0x14000138a  mov     rcx, cs:__guard_dispatch_icall_fptr
0x140001391  call    rcx ; _guard_dispatch_icall_nop
0x140001393  mov     [rsp+0E8h+var_C8], eax
0x140001397  add     rdi, 8
0x14000139b  mov     [rsp+0E8h+var_B0], rdi
0x1400013a0  jmp     short loc_140001379
0x1400013a2  test    eax, eax
0x1400013a4  jz      short loc_1400013B6
0x1400013a6  mov     eax, 0FFh
0x1400013ab  jmp     loc_14000150E
0x1400013b0  mov     cs:dword_14000C144, ebx
0x1400013b6  mov     edi, 1Fh
0x1400013bb  mov     eax, cs:__native_startup_state
0x1400013c1  cmp     eax, ebx
0x1400013c3  jnz     short loc_1400013E2
0x1400013c5  lea     rdx, __xc_z; Last
0x1400013cc  lea     rcx, __xc_a; First
0x1400013d3  call    _initterm_0
0x1400013d8  mov     cs:__native_startup_state, 2
0x1400013e2  test    r14d, r14d
0x1400013e5  jnz     short loc_1400013F1
0x1400013e7  mov     rax, r15
0x1400013ea  xchg    rax, cs:__native_startup_lock
0x1400013f1  cmp     cs:__dyn_tls_init_callback, r15
0x1400013f8  jz      short loc_140001424
0x1400013fa  lea     rcx, __dyn_tls_init_callback
0x140001401  call    _IsNonwritableInCurrentImage
0x140001406  test    eax, eax
0x140001408  jz      short loc_140001424
0x14000140a  xor     r8d, r8d
0x14000140d  lea     edx, [r8+2]
0x140001411  xor     ecx, ecx
0x140001413  mov     rax, cs:__dyn_tls_init_callback
0x14000141a  mov     r9, cs:__guard_dispatch_icall_fptr
0x140001421  call    r9 ; _guard_dispatch_icall_nop
0x140001424  mov     rax, cs:__imp__wcmdln
0x14000142b  mov     rcx, [rax]
0x14000142e  test    rcx, rcx
0x140001431  jnz     short loc_14000143D
0x140001433  mov     eax, 0FFh
0x140001438  jmp     loc_14000150E
0x14000143d  mov     [rsp+0E8h+var_C0], rcx
0x140001442  movzx   eax, word ptr [rcx]
0x140001445  cmp     ax, 20h ; ' '
0x140001449  ja      short loc_1400014BF
0x14000144b  test    ax, ax
0x14000144e  jz      short loc_140001454
0x140001450  test    esi, esi
0x140001452  jnz     short loc_1400014BF
0x140001454  sub     ax, bx
0x140001457  cmp     ax, di
0x14000145a  ja      short loc_14000146A
0x14000145c  add     rcx, 2
0x140001460  mov     [rsp+0E8h+var_C0], rcx
0x140001465  movzx   eax, word ptr [rcx]
0x140001468  jmp     short loc_140001454
0x14000146a  test    byte ptr [rsp+0E8h+StartupInfo.dwFlags], bl
0x14000146e  movzx   eax, [rsp+0E8h+StartupInfo.wShowWindow]
0x140001476  mov     r9d, 0Ah
0x14000147c  cmovnz  r9d, eax; nShowCmd
0x140001480  mov     r8, rcx; lpCmdLine
0x140001483  xor     edx, edx; hPrevInstance
0x140001485  lea     rcx, cs:140000000h; hInstance
0x14000148c  call    wWinMain
0x140001491  mov     cs:dword_14000C140, eax
0x140001497  cmp     cs:dword_14000C160, r15d
0x14000149e  jnz     short loc_1400014A8
0x1400014a0  mov     ecx, eax; Code
0x1400014a2  call    cs:__imp_exit
0x1400014a8  cmp     cs:dword_14000C144, r15d
0x1400014af  jnz     short loc_1400014BD
0x1400014b1  call    cs:__imp__cexit
0x1400014b7  mov     eax, cs:dword_14000C140
0x1400014bd  jmp     short loc_14000150E
0x1400014bf  cmp     ax, 22h ; '"'
0x1400014c3  jnz     short loc_1400014D3
0x1400014c5  mov     eax, r15d
0x1400014c8  test    esi, esi
0x1400014ca  setz    al
0x1400014cd  mov     esi, eax
0x1400014cf  mov     [rsp+0E8h+var_B8], eax
0x1400014d3  add     rcx, 2
0x1400014d7  mov     [rsp+0E8h+var_C0], rcx
0x1400014dc  jmp     loc_140001442
0x1400014e1  mov     cs:dword_14000C140, eax
0x1400014e7  cmp     cs:dword_14000C160, 0
0x1400014ee  jnz     short loc_1400014F9
0x1400014f0  mov     ecx, eax; Code
0x1400014f2  call    cs:__imp__exit
0x1400014f9  cmp     cs:dword_14000C144, 0
0x140001500  jnz     short loc_14000150E
0x140001502  call    cs:__imp__cexit
0x140001508  mov     eax, cs:dword_14000C140
0x14000150e  add     rsp, 0B8h
0x140001515  pop     r15
0x140001517  pop     r14
0x140001519  pop     r12
0x14000151b  pop     rdi
0x14000151c  pop     rsi
0x14000151d  pop     rbx
0x14000151e  retn
0x140006ca0  push    rbp
0x140006ca2  sub     rsp, 20h
0x140006ca6  mov     rbp, rdx
0x140006ca9  mov     rdx, rcx
0x140006cac  mov     rcx, [rcx]
0x140006caf  mov     ecx, [rcx]
0x140006cb1  call    _XcptFilter_0
0x140006cb6  nop
0x140006cb7  add     rsp, 20h
0x140006cbb  pop     rbp
0x140006cbc  retn
```
