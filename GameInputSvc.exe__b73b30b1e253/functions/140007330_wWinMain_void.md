# _wWinMain(void)

- ea: `0x140007330`
- end: `0x140007482`
- name: `?_wWinMain@@YAHXZ`
- size: `338`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007660`

## callees

- `0x140005cb8`
- `0x140006b74`
- `0x140006de4`
- `0x14000704c`
- `0x140007330`
- `0x140007588`
- `0x140007735`
- `0x140007750`
- `0x140008010`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x1400073ba`
- `ntdll!EtwEventRegister` at `0x1400073ba`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x14000744a`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x14000744a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400073ec`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400073ec`

## pseudocode

```c
__int64 _wWinMain(void)
{
  __int64 result; // rax
  LPWSTR CommandLineW; // rbx
  WCHAR v2; // ax
  bool v3; // cl
  HINSTANCE v4; // rdx
  HINSTANCE v5; // rcx
  int v6; // r9d
  unsigned int v7; // ebx
  struct _STARTUPINFOW StartupInfo; // [rsp+30h] [rbp-98h] BYREF
  __int128 v9; // [rsp+A0h] [rbp-28h] BYREF

  result = InitPlatformInfo();
  if ( (int)result >= 0 )
  {
    LoadDllImports();
    result = ConstructStatics();
    if ( (int)result >= 0 )
    {
      v9 = *(_OWORD *)&(*off_14000E008)[-16];
      if ( qword_14000E020 )
        __fastfail(5u);
      xmmword_14000E028 = 0;
      if ( !(unsigned int)EtwEventRegister(&v9, tlgEnableCallback, &dword_14000E000, &qword_14000E020)
        && qword_14000E660 )
      {
        qword_14000E660(qword_14000E020, 2, (char *)off_14000E008, *(unsigned __int16 *)off_14000E008);
      }
      CommandLineW = GetCommandLineW();
      v2 = *CommandLineW;
      if ( *CommandLineW )
      {
        v3 = 0;
        do
        {
          if ( v2 <= 0x20u && !v3 )
            break;
          if ( v2 == 34 )
            v3 = !v3;
          v2 = *++CommandLineW;
        }
        while ( *CommandLineW );
      }
      while ( *CommandLineW && *CommandLineW <= 0x20u )
        ++CommandLineW;
      memset_0(&StartupInfo, 0, sizeof(StartupInfo));
      GetStartupInfoW(&StartupInfo);
      v7 = wWinMain(v5, v4, CommandLineW, v6);
      GameInputUninitialize();
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140007330  mov     [rsp+arg_0], rbx
0x140007335  push    rdi
0x140007336  sub     rsp, 0C0h
0x14000733d  mov     rax, cs:__security_cookie
0x140007344  xor     rax, rsp
0x140007347  mov     [rsp+0C8h+var_18], rax
0x14000734f  call    InitPlatformInfo
0x140007354  xor     edi, edi
0x140007356  test    eax, eax
0x140007358  js      loc_140007461
0x14000735e  call    LoadDllImports
0x140007363  call    ConstructStatics
0x140007368  test    eax, eax
0x14000736a  js      loc_140007461
0x140007370  cmp     cs:qword_14000E020, rdi
0x140007377  mov     rax, cs:off_14000E008
0x14000737e  movups  xmm0, xmmword ptr [rax-10h]
0x140007382  movdqu  [rsp+0C8h+var_28], xmm0
0x14000738b  jz      short loc_140007392
0x14000738d  lea     ecx, [rdi+5]
0x140007390  int     29h; Win8: RtlFailFast(ecx)
0x140007392  xorps   xmm0, xmm0
0x140007395  lea     r9, qword_14000E020
0x14000739c  lea     r8, dword_14000E000
0x1400073a3  lea     rdx, _tlgEnableCallback
0x1400073aa  lea     rcx, [rsp+0C8h+var_28]
0x1400073b2  movdqu  cs:xmmword_14000E028, xmm0
0x1400073ba  call    cs:__imp_EtwEventRegister
0x1400073c0  test    eax, eax
0x1400073c2  jnz     short loc_1400073EC
0x1400073c4  mov     rax, cs:qword_14000E660
0x1400073cb  test    rax, rax
0x1400073ce  jz      short loc_1400073EC
0x1400073d0  mov     r8, cs:off_14000E008
0x1400073d7  mov     edx, 2
0x1400073dc  mov     rcx, cs:qword_14000E020
0x1400073e3  movzx   r9d, word ptr [r8]
0x1400073e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400073ec  call    cs:__imp_GetCommandLineW
0x1400073f2  mov     rbx, rax
0x1400073f5  movzx   eax, word ptr [rax]
0x1400073f8  test    ax, ax
0x1400073fb  jz      short loc_14000742D
0x1400073fd  mov     cl, dil
0x140007400  cmp     ax, 20h ; ' '
0x140007404  ja      short loc_14000740A
0x140007406  test    cl, cl
0x140007408  jz      short loc_14000742D
0x14000740a  cmp     ax, 22h ; '"'
0x14000740e  jnz     short loc_140007415
0x140007410  test    cl, cl
0x140007412  setz    cl
0x140007415  add     rbx, 2
0x140007419  movzx   eax, word ptr [rbx]
0x14000741c  test    ax, ax
0x14000741f  jnz     short loc_140007400
0x140007421  jmp     short loc_14000742D
0x140007423  cmp     ax, 20h ; ' '
0x140007427  ja      short loc_140007435
0x140007429  add     rbx, 2
0x14000742d  movzx   eax, word ptr [rbx]
0x140007430  test    ax, ax
0x140007433  jnz     short loc_140007423
0x140007435  xor     edx, edx; Val
0x140007437  lea     rcx, [rsp+0C8h+StartupInfo]; void *
0x14000743c  lea     r8d, [rdx+68h]; Size
0x140007440  call    memset_0
0x140007445  lea     rcx, [rsp+0C8h+StartupInfo]; lpStartupInfo
0x14000744a  call    cs:__imp_GetStartupInfoW
0x140007450  mov     r8, rbx; lpCmdLine
0x140007453  call    wWinMain
0x140007458  mov     ebx, eax
0x14000745a  call    GameInputUninitialize
0x14000745f  mov     eax, ebx
0x140007461  mov     rcx, [rsp+0C8h+var_18]
0x140007469  xor     rcx, rsp; StackCookie
0x14000746c  call    __security_check_cookie
0x140007471  mov     rbx, [rsp+0C8h+arg_0]
0x140007479  add     rsp, 0C0h
0x140007480  pop     rdi
0x140007481  retn
```
