# __mainCRTStartup

- ea: `0x140001168`
- end: `0x1400013aa`
- name: `__mainCRTStartup`
- size: `578`
- prototype: `int()`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001150`

## callees

- `0x140001168`
- `0x14000145e`
- `0x140001510`
- `0x140001580`
- `0x1400016e7`
- `0x1400016f3`
- `0x140004200`
- `0x1400044a0`

## import_xrefs

- `msvcrt!exit` at `0x140001322`
- `msvcrt!exit` at `0x140001322`
- `msvcrt!_exit` at `0x140001381`
- `msvcrt!_exit` at `0x140001381`
- `msvcrt!_cexit` at `0x140001331`
- `msvcrt!_cexit` at `0x140001391`
- `msvcrt!_cexit` at `0x140001331`
- `msvcrt!_cexit` at `0x140001391`
- `msvcrt!_ismbblead` at `0x140001351`
- `msvcrt!_ismbblead` at `0x140001351`
- `msvcrt!_acmdln` at `0x1400012b7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400011d9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400011d9`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001192`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001192`

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
    result = WinMain((HINSTANCE)0x140000000LL, 0, i, wShowWindow);
    dword_1400090A0 = result;
    if ( !dword_1400090C0 )
      exit(result);
    if ( !dword_1400090A4 )
    {
      _cexit();
      return dword_1400090A0;
    }
    return result;
  }
  v4 = _native_startup_state;
  if ( _native_startup_state )
  {
    dword_1400090A4 = 1;
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
0x140001168  push    rbx
0x14000116a  push    rsi
0x14000116b  push    rdi
0x14000116c  push    r15
0x14000116e  sub     rsp, 0B8h
0x140001175  xor     eax, eax
0x140001177  mov     dword ptr [rsp+0D8h+StartupInfo+4], eax
0x14000117b  xor     edx, edx; Val
0x14000117d  lea     r8d, [rax+64h]; Size
0x140001181  lea     rcx, [rsp+0D8h+StartupInfo]; void *
0x140001186  call    memset_0
0x14000118b  xor     edi, edi
0x14000118d  lea     rcx, [rsp+0D8h+StartupInfo]; lpStartupInfo
0x140001192  call    cs:__imp_GetStartupInfoW
0x140001198  nop
0x140001199  mov     rax, gs:30h
0x1400011a2  mov     rbx, [rax+8]
0x1400011a6  xor     esi, esi
0x1400011a8  xor     eax, eax
0x1400011aa  lock cmpxchg cs:__native_startup_lock, rbx
0x1400011b3  jz      short loc_1400011BF
0x1400011b5  cmp     rax, rbx
0x1400011b8  jnz     short loc_1400011D4
0x1400011ba  mov     esi, 1
0x1400011bf  mov     eax, cs:__native_startup_state
0x1400011c5  cmp     eax, 1
0x1400011c8  jnz     short loc_1400011E1
0x1400011ca  lea     ecx, [rax+1Eh]
0x1400011cd  call    _amsg_exit_0
0x1400011d2  jmp     short loc_14000124E
0x1400011d4  mov     ecx, 3E8h; dwMilliseconds
0x1400011d9  call    cs:__imp_Sleep
0x1400011df  jmp     short loc_1400011A8
0x1400011e1  mov     eax, cs:__native_startup_state
0x1400011e7  test    eax, eax
0x1400011e9  jnz     short loc_140001244
0x1400011eb  mov     cs:__native_startup_state, 1
0x1400011f5  lea     r15, __xi_z
0x1400011fc  lea     rbx, __xi_a
0x140001203  mov     [rsp+0D8h+var_A0], rbx
0x140001208  mov     [rsp+0D8h+var_B8], eax
0x14000120c  cmp     rbx, r15
0x14000120f  jnb     short loc_140001236
0x140001211  test    eax, eax
0x140001213  jnz     short loc_14000123A
0x140001215  cmp     qword ptr [rbx], 0
0x140001219  jz      short loc_14000122B
0x14000121b  mov     rax, [rbx]
0x14000121e  mov     rcx, cs:__guard_dispatch_icall_fptr
0x140001225  call    rcx ; _guard_dispatch_icall_nop
0x140001227  mov     [rsp+0D8h+var_B8], eax
0x14000122b  add     rbx, 8
0x14000122f  mov     [rsp+0D8h+var_A0], rbx
0x140001234  jmp     short loc_14000120C
0x140001236  test    eax, eax
0x140001238  jz      short loc_14000124E
0x14000123a  mov     eax, 0FFh
0x14000123f  jmp     loc_14000139D
0x140001244  mov     cs:dword_1400090A4, 1
0x14000124e  mov     eax, cs:__native_startup_state
0x140001254  cmp     eax, 1
0x140001257  jnz     short loc_140001276
0x140001259  lea     rdx, __xc_z; Last
0x140001260  lea     rcx, __xc_a; First
0x140001267  call    _initterm_0
0x14000126c  mov     cs:__native_startup_state, 2
0x140001276  test    esi, esi
0x140001278  jnz     short loc_140001283
0x14000127a  xor     eax, eax
0x14000127c  xchg    rax, cs:__native_startup_lock
0x140001283  cmp     cs:__dyn_tls_init_callback, 0
0x14000128b  jz      short loc_1400012B7
0x14000128d  lea     rcx, __dyn_tls_init_callback
0x140001294  call    _IsNonwritableInCurrentImage
0x140001299  test    eax, eax
0x14000129b  jz      short loc_1400012B7
0x14000129d  xor     r8d, r8d
0x1400012a0  lea     edx, [r8+2]
0x1400012a4  xor     ecx, ecx
0x1400012a6  mov     rax, cs:__dyn_tls_init_callback
0x1400012ad  mov     r9, cs:__guard_dispatch_icall_fptr
0x1400012b4  call    r9 ; _guard_dispatch_icall_nop
0x1400012b7  mov     rax, cs:__imp__acmdln
0x1400012be  mov     rbx, [rax]
0x1400012c1  mov     [rsp+0D8h+var_B0], rbx
0x1400012c6  movzx   ecx, byte ptr [rbx]; Ch
0x1400012c9  cmp     cl, 20h ; ' '
0x1400012cc  ja      short loc_14000133F
0x1400012ce  test    cl, cl
0x1400012d0  jz      short loc_1400012D6
0x1400012d2  test    edi, edi
0x1400012d4  jnz     short loc_14000133F
0x1400012d6  dec     cl
0x1400012d8  cmp     cl, 1Fh
0x1400012db  ja      short loc_1400012E9
0x1400012dd  inc     rbx
0x1400012e0  mov     [rsp+0D8h+var_B0], rbx
0x1400012e5  mov     cl, [rbx]
0x1400012e7  jmp     short loc_1400012D6
0x1400012e9  test    byte ptr [rsp+0D8h+StartupInfo.dwFlags], 1
0x1400012ee  movzx   eax, [rsp+0D8h+StartupInfo.wShowWindow]
0x1400012f6  mov     r9d, 0Ah
0x1400012fc  cmovnz  r9d, eax; nShowCmd
0x140001300  mov     r8, rbx; lpCmdLine
0x140001303  xor     edx, edx; hPrevInstance
0x140001305  lea     rcx, cs:140000000h; hInstance
0x14000130c  call    WinMain
0x140001311  mov     cs:dword_1400090A0, eax
0x140001317  cmp     cs:dword_1400090C0, 0
0x14000131e  jnz     short loc_140001328
0x140001320  mov     ecx, eax; Code
0x140001322  call    cs:__imp_exit
0x140001328  cmp     cs:dword_1400090A4, 0
0x14000132f  jnz     short loc_14000133D
0x140001331  call    cs:__imp__cexit
0x140001337  mov     eax, cs:dword_1400090A0
0x14000133d  jmp     short loc_14000139D
0x14000133f  cmp     cl, 22h ; '"'
0x140001342  jnz     short loc_140001351
0x140001344  xor     eax, eax
0x140001346  test    edi, edi
0x140001348  setz    al
0x14000134b  mov     edi, eax
0x14000134d  mov     [rsp+0D8h+var_A8], eax
0x140001351  call    cs:__imp__ismbblead
0x140001357  test    eax, eax
0x140001359  jz      short loc_140001363
0x14000135b  inc     rbx
0x14000135e  mov     [rsp+0D8h+var_B0], rbx
0x140001363  inc     rbx
0x140001366  mov     [rsp+0D8h+var_B0], rbx
0x14000136b  jmp     loc_1400012C6
0x140001370  mov     cs:dword_1400090A0, eax
0x140001376  cmp     cs:dword_1400090C0, 0
0x14000137d  jnz     short loc_140001388
0x14000137f  mov     ecx, eax; Code
0x140001381  call    cs:__imp__exit
0x140001388  cmp     cs:dword_1400090A4, 0
0x14000138f  jnz     short loc_14000139D
0x140001391  call    cs:__imp__cexit
0x140001397  mov     eax, cs:dword_1400090A0
0x14000139d  add     rsp, 0B8h
0x1400013a4  pop     r15
0x1400013a6  pop     rdi
0x1400013a7  pop     rsi
0x1400013a8  pop     rbx
0x1400013a9  retn
0x140004510  push    rbp
0x140004512  sub     rsp, 20h
0x140004516  mov     rbp, rdx
0x140004519  mov     rdx, rcx
0x14000451c  mov     rcx, [rcx]
0x14000451f  mov     ecx, [rcx]
0x140004521  call    _XcptFilter_0
0x140004526  nop
0x140004527  add     rsp, 20h
0x14000452b  pop     rbp
0x14000452c  retn
```
