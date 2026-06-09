# __mainCRTStartup

- ea: `0x140001ad8`
- end: `0x140001d1a`
- name: `__mainCRTStartup`
- size: `578`
- prototype: `int()`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001ac0`

## callees

- `0x140001ad8`
- `0x140001f2e`
- `0x140001fe0`
- `0x140002050`
- `0x1400021b7`
- `0x1400021cf`
- `0x140003cf8`
- `0x1400043d0`

## import_xrefs

- `msvcrt!_acmdln` at `0x140001c27`
- `msvcrt!_ismbblead` at `0x140001cc1`
- `msvcrt!_ismbblead` at `0x140001cc1`
- `msvcrt!_cexit` at `0x140001ca1`
- `msvcrt!_cexit` at `0x140001d01`
- `msvcrt!_cexit` at `0x140001ca1`
- `msvcrt!_cexit` at `0x140001d01`
- `msvcrt!_exit` at `0x140001cf1`
- `msvcrt!_exit` at `0x140001cf1`
- `msvcrt!exit` at `0x140001c92`
- `msvcrt!exit` at `0x140001c92`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140001b49`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140001b49`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001b02`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001b02`

## pseudocode

```c
int _mainCRTStartup()
{
  BOOL v0; // edi
  PVOID StackBase; // rbx
  int v2; // esi
  signed __int64 v3; // rax
  int v4; // eax
  __int64 *j; // rbx
  int result; // eax
  char *i; // rbx
  unsigned int v8; // ecx
  int wShowWindow; // r9d
  _STARTUPINFOW StartupInfo; // [rsp+40h] [rbp-98h] BYREF

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
    for ( i = _acmdln; ; ++i )
    {
      v8 = (unsigned __int8)*i;
      if ( (unsigned __int8)v8 <= 0x20u && (!(_BYTE)v8 || !v0) )
        break;
      if ( (_BYTE)v8 == 34 )
        v0 = !v0;
      if ( _ismbblead(v8) )
        ++i;
    }
    while ( (unsigned __int8)(v8 - 1) <= 0x1Fu )
      LOBYTE(v8) = *++i;
    wShowWindow = 10;
    if ( (StartupInfo.dwFlags & 1) != 0 )
      wShowWindow = StartupInfo.wShowWindow;
    result = WinMain(&_ImageBase, 0, i, wShowWindow);
    dword_14000C20C = result;
    if ( !dword_14000C230 )
      exit(result);
    if ( !dword_14000C210 )
    {
      _cexit();
      return dword_14000C20C;
    }
    return result;
  }
  v4 = _native_startup_state;
  if ( _native_startup_state )
  {
    dword_14000C210 = 1;
    goto LABEL_18;
  }
  _native_startup_state = 1;
  for ( j = &_xi_a; j < &_xi_z; ++j )
  {
    if ( v4 )
      return 255;
    if ( *j )
      v4 = _guard_dispatch_icall_fptr();
  }
  if ( !v4 )
    goto LABEL_18;
  return 255;
}

```

## disassembly

```asm
0x140001ad8  push    rbx
0x140001ada  push    rsi
0x140001adb  push    rdi
0x140001adc  push    r15
0x140001ade  sub     rsp, 0B8h
0x140001ae5  xor     eax, eax
0x140001ae7  mov     dword ptr [rsp+0D8h+StartupInfo+4], eax
0x140001aeb  xor     edx, edx; Val
0x140001aed  lea     r8d, [rax+64h]; Size
0x140001af1  lea     rcx, [rsp+0D8h+StartupInfo]; void *
0x140001af6  call    memset_0
0x140001afb  xor     edi, edi
0x140001afd  lea     rcx, [rsp+0D8h+StartupInfo]; lpStartupInfo
0x140001b02  call    cs:__imp_GetStartupInfoW
0x140001b08  nop
0x140001b09  mov     rax, gs:30h
0x140001b12  mov     rbx, [rax+8]
0x140001b16  xor     esi, esi
0x140001b18  xor     eax, eax
0x140001b1a  lock cmpxchg cs:__native_startup_lock, rbx
0x140001b23  jz      short loc_140001B2F
0x140001b25  cmp     rax, rbx
0x140001b28  jnz     short loc_140001B44
0x140001b2a  mov     esi, 1
0x140001b2f  mov     eax, cs:__native_startup_state
0x140001b35  cmp     eax, 1
0x140001b38  jnz     short loc_140001B51
0x140001b3a  lea     ecx, [rax+1Eh]
0x140001b3d  call    _amsg_exit_0
0x140001b42  jmp     short loc_140001BBE
0x140001b44  mov     ecx, 3E8h; dwMilliseconds
0x140001b49  call    cs:__imp_Sleep
0x140001b4f  jmp     short loc_140001B18
0x140001b51  mov     eax, cs:__native_startup_state
0x140001b57  test    eax, eax
0x140001b59  jnz     short loc_140001BB4
0x140001b5b  mov     cs:__native_startup_state, 1
0x140001b65  lea     r15, __xi_z
0x140001b6c  lea     rbx, __xi_a
0x140001b73  mov     [rsp+0D8h+var_A0], rbx
0x140001b78  mov     [rsp+0D8h+var_B8], eax
0x140001b7c  cmp     rbx, r15
0x140001b7f  jnb     short loc_140001BA6
0x140001b81  test    eax, eax
0x140001b83  jnz     short loc_140001BAA
0x140001b85  cmp     qword ptr [rbx], 0
0x140001b89  jz      short loc_140001B9B
0x140001b8b  mov     rax, [rbx]
0x140001b8e  mov     rcx, cs:__guard_dispatch_icall_fptr
0x140001b95  call    rcx ; _guard_dispatch_icall_nop
0x140001b97  mov     [rsp+0D8h+var_B8], eax
0x140001b9b  add     rbx, 8
0x140001b9f  mov     [rsp+0D8h+var_A0], rbx
0x140001ba4  jmp     short loc_140001B7C
0x140001ba6  test    eax, eax
0x140001ba8  jz      short loc_140001BBE
0x140001baa  mov     eax, 0FFh
0x140001baf  jmp     loc_140001D0D
0x140001bb4  mov     cs:dword_14000C210, 1
0x140001bbe  mov     eax, cs:__native_startup_state
0x140001bc4  cmp     eax, 1
0x140001bc7  jnz     short loc_140001BE6
0x140001bc9  lea     rdx, __xc_z; Last
0x140001bd0  lea     rcx, __xc_a; First
0x140001bd7  call    _initterm_0
0x140001bdc  mov     cs:__native_startup_state, 2
0x140001be6  test    esi, esi
0x140001be8  jnz     short loc_140001BF3
0x140001bea  xor     eax, eax
0x140001bec  xchg    rax, cs:__native_startup_lock
0x140001bf3  cmp     cs:__dyn_tls_init_callback, 0
0x140001bfb  jz      short loc_140001C27
0x140001bfd  lea     rcx, __dyn_tls_init_callback
0x140001c04  call    _IsNonwritableInCurrentImage
0x140001c09  test    eax, eax
0x140001c0b  jz      short loc_140001C27
0x140001c0d  xor     r8d, r8d
0x140001c10  lea     edx, [r8+2]
0x140001c14  xor     ecx, ecx
0x140001c16  mov     rax, cs:__dyn_tls_init_callback
0x140001c1d  mov     r9, cs:__guard_dispatch_icall_fptr
0x140001c24  call    r9 ; _guard_dispatch_icall_nop
0x140001c27  mov     rax, cs:__imp__acmdln
0x140001c2e  mov     rbx, [rax]
0x140001c31  mov     [rsp+0D8h+var_B0], rbx
0x140001c36  movzx   ecx, byte ptr [rbx]; Ch
0x140001c39  cmp     cl, 20h ; ' '
0x140001c3c  ja      short loc_140001CAF
0x140001c3e  test    cl, cl
0x140001c40  jz      short loc_140001C46
0x140001c42  test    edi, edi
0x140001c44  jnz     short loc_140001CAF
0x140001c46  dec     cl
0x140001c48  cmp     cl, 1Fh
0x140001c4b  ja      short loc_140001C59
0x140001c4d  inc     rbx
0x140001c50  mov     [rsp+0D8h+var_B0], rbx
0x140001c55  mov     cl, [rbx]
0x140001c57  jmp     short loc_140001C46
0x140001c59  test    byte ptr [rsp+0D8h+StartupInfo.dwFlags], 1
0x140001c5e  movzx   eax, [rsp+0D8h+StartupInfo.wShowWindow]
0x140001c66  mov     r9d, 0Ah
0x140001c6c  cmovnz  r9d, eax; nShowCmd
0x140001c70  mov     r8, rbx; lpCmdLine
0x140001c73  xor     edx, edx; hPrevInstance
0x140001c75  lea     rcx, __ImageBase; hInstance
0x140001c7c  call    WinMain
0x140001c81  mov     cs:dword_14000C20C, eax
0x140001c87  cmp     cs:dword_14000C230, 0
0x140001c8e  jnz     short loc_140001C98
0x140001c90  mov     ecx, eax; Code
0x140001c92  call    cs:__imp_exit
0x140001c98  cmp     cs:dword_14000C210, 0
0x140001c9f  jnz     short loc_140001CAD
0x140001ca1  call    cs:__imp__cexit
0x140001ca7  mov     eax, cs:dword_14000C20C
0x140001cad  jmp     short loc_140001D0D
0x140001caf  cmp     cl, 22h ; '"'
0x140001cb2  jnz     short loc_140001CC1
0x140001cb4  xor     eax, eax
0x140001cb6  test    edi, edi
0x140001cb8  setz    al
0x140001cbb  mov     edi, eax
0x140001cbd  mov     [rsp+0D8h+var_A8], eax
0x140001cc1  call    cs:__imp__ismbblead
0x140001cc7  test    eax, eax
0x140001cc9  jz      short loc_140001CD3
0x140001ccb  inc     rbx
0x140001cce  mov     [rsp+0D8h+var_B0], rbx
0x140001cd3  inc     rbx
0x140001cd6  mov     [rsp+0D8h+var_B0], rbx
0x140001cdb  jmp     loc_140001C36
0x140001ce0  mov     cs:dword_14000C20C, eax
0x140001ce6  cmp     cs:dword_14000C230, 0
0x140001ced  jnz     short loc_140001CF8
0x140001cef  mov     ecx, eax; Code
0x140001cf1  call    cs:__imp__exit
0x140001cf8  cmp     cs:dword_14000C210, 0
0x140001cff  jnz     short loc_140001D0D
0x140001d01  call    cs:__imp__cexit
0x140001d07  mov     eax, cs:dword_14000C20C
0x140001d0d  add     rsp, 0B8h
0x140001d14  pop     r15
0x140001d16  pop     rdi
0x140001d17  pop     rsi
0x140001d18  pop     rbx
0x140001d19  retn
0x14000447f  push    rbp
0x140004481  sub     rsp, 20h
0x140004485  mov     rbp, rdx
0x140004488  mov     rdx, rcx
0x14000448b  mov     rcx, [rcx]
0x14000448e  mov     ecx, [rcx]
0x140004490  call    _XcptFilter_0
0x140004495  nop
0x140004496  add     rsp, 20h
0x14000449a  pop     rbp
0x14000449b  retn
```
