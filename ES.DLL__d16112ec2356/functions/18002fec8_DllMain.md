# DllMain

- ea: `0x18002fec8`
- end: `0x18002ffcd`
- name: `DllMain`
- size: `261`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d464`

## callees

- `0x1800023b0`
- `0x180023978`
- `0x180025198`
- `0x18002fec8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ff6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ff77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ff9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ff6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ff77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ff9c`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18002fef4`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18002ff14`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18002fef4`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18002ff14`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002ff43`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002ff50`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002ff5d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002ff43`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002ff50`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002ff5d`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v4; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned __int64 v8; // rdi
  void *v9; // rcx

  if ( fdwReason )
  {
    v4 = 1;
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      g_moduleHandle = hinstDLL;
      if ( (int)InitSecurity() < 0 )
        return 0;
      DisableThreadLibraryCalls(hinstDLL);
      SafeAllocaInitialize();
      DllMainHelper::s_fOutOfDllMain = 1;
      g_hinst = hinstDLL;
      return DllMainHelper::s_fFailLoad == 0;
    }
  }
  else
  {
    FreeSid(pSid);
    FreeSid(SidToCheck);
    FreeSid(pSid2);
    LocalFree(hMem);
    LocalFree(qword_180064668);
    v8 = 0;
    v4 = 1;
    do
    {
      v9 = (void *)*(&off_180063990)[2 * v8];
      if ( v9 )
      {
        LocalFree(v9);
        *(&off_180063990)[2 * v8] = 0;
      }
      ++v8;
    }
    while ( v8 < 3 );
    g_fProcessDetach = 1;
    StopWorkerQueues(v9, v6, v7);
  }
  return v4;
}

```

## disassembly

```asm
0x18002fec8  push    rbx
0x18002feca  push    rbp
0x18002fecb  push    rsi
0x18002fecc  push    rdi
0x18002fecd  sub     rsp, 28h
0x18002fed1  mov     rdi, rcx
0x18002fed4  mov     eax, edx
0x18002fed6  test    edx, edx
0x18002fed8  jz      short loc_18002FF3C
0x18002feda  mov     ebx, 1
0x18002fedf  cmp     eax, ebx
0x18002fee1  jz      short loc_18002FEF4
0x18002fee3  cmp     edx, ebx
0x18002fee5  jz      short loc_18002FF1F
0x18002fee7  test    edx, edx
0x18002fee9  jnz     loc_18002FFC2
0x18002feef  jmp     loc_18002FFB7
0x18002fef4  call    cs:__imp_DisableThreadLibraryCalls
0x18002fefa  mov     cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_moduleHandle
0x18002ff01  call    ?InitSecurity@@YAJXZ; InitSecurity(void)
0x18002ff06  test    eax, eax
0x18002ff08  jns     short loc_18002FF11
0x18002ff0a  xor     eax, eax
0x18002ff0c  jmp     loc_18002FFC4
0x18002ff11  mov     rcx, rdi; hLibModule
0x18002ff14  call    cs:__imp_DisableThreadLibraryCalls
0x18002ff1a  call    SafeAllocaInitialize
0x18002ff1f  mov     cs:?s_fOutOfDllMain@DllMainHelper@@0HA, ebx; int DllMainHelper::s_fOutOfDllMain
0x18002ff25  xor     ebx, ebx
0x18002ff27  cmp     cs:?s_fFailLoad@DllMainHelper@@0HA, ebx; int DllMainHelper::s_fFailLoad
0x18002ff2d  mov     cs:?g_hinst@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hinst
0x18002ff34  setz    bl
0x18002ff37  jmp     loc_18002FFC2
0x18002ff3c  mov     rcx, cs:pSid; pSid
0x18002ff43  call    cs:__imp_FreeSid
0x18002ff49  mov     rcx, cs:SidToCheck; pSid
0x18002ff50  call    cs:__imp_FreeSid
0x18002ff56  mov     rcx, cs:pSid2; pSid
0x18002ff5d  call    cs:__imp_FreeSid
0x18002ff63  mov     rcx, cs:hMem; hMem
0x18002ff6a  call    cs:__imp_LocalFree
0x18002ff70  mov     rcx, cs:qword_180064668; hMem
0x18002ff77  call    cs:__imp_LocalFree
0x18002ff7d  xor     edi, edi
0x18002ff7f  lea     ebx, [rdi+1]
0x18002ff82  mov     rsi, rdi
0x18002ff85  lea     rbp, off_180063990
0x18002ff8c  add     rsi, rsi
0x18002ff8f  mov     rax, [rbp+rsi*8+0]
0x18002ff94  mov     rcx, [rax]; hMem
0x18002ff97  test    rcx, rcx
0x18002ff9a  jz      short loc_18002FFAE
0x18002ff9c  call    cs:__imp_LocalFree
0x18002ffa2  mov     rax, [rbp+rsi*8+0]
0x18002ffa7  mov     qword ptr [rax], 0
0x18002ffae  add     rdi, rbx
0x18002ffb1  cmp     rdi, 3
0x18002ffb5  jb      short loc_18002FF82
0x18002ffb7  mov     cs:?g_fProcessDetach@@3HA, ebx; int g_fProcessDetach
0x18002ffbd  call    StopWorkerQueues
0x18002ffc2  mov     eax, ebx
0x18002ffc4  add     rsp, 28h
0x18002ffc8  pop     rdi
0x18002ffc9  pop     rsi
0x18002ffca  pop     rbp
0x18002ffcb  pop     rbx
0x18002ffcc  retn
```
