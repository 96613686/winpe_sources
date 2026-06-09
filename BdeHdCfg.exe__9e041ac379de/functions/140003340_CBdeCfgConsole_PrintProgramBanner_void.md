# CBdeCfgConsole::PrintProgramBanner(void)

- ea: `0x140003340`
- end: `0x140003433`
- name: `?PrintProgramBanner@CBdeCfgConsole@@QEAAXXZ`
- size: `243`
- prototype: `void __fastcall(CBdeCfgConsole *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140001bf4`
- `0x140002bc4`

## callees

- `0x1400031c4`
- `0x140003340`
- `0x140004460`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x140003377`
- `KERNEL32!GetModuleFileNameW` at `0x140003377`
- `KERNEL32!InitOnceExecuteOnce` at `0x1400033b1`
- `KERNEL32!InitOnceExecuteOnce` at `0x1400033b1`
- `KERNEL32!GetLastError` at `0x140003388`
- `KERNEL32!GetLastError` at `0x140003388`
- `msvcrt!swprintf_s` at `0x1400033f0`
- `msvcrt!swprintf_s` at `0x1400033f0`

## pseudocode

```c
void __fastcall CBdeCfgConsole::PrintProgramBanner(CBdeCfgConsole *this)
{
  DWORD ModuleFileNameW; // eax
  BOOL inited; // eax
  wchar_t *v4; // r8
  WCHAR Filename[264]; // [rsp+30h] [rbp-448h] BYREF
  _RTL_RUN_ONCE InitOnce; // [rsp+240h] [rbp-238h] BYREF
  wchar_t Buffer[264]; // [rsp+250h] [rbp-228h] BYREF

  InitOnce.Ptr = 0;
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( !ModuleFileNameW || ModuleFileNameW == 260 && GetLastError() == 122 )
    Filename[0] = 0;
  inited = InitOnceExecuteOnce(&InitOnce, VersionHelpers::ProductVersionHelper::Initialize, Filename, 0);
  if ( inited )
  {
    swprintf_s(Buffer, 0x104u, L"%u.%u.%u", Filename[260], Filename[261], Filename[262]);
    LOBYTE(inited) = 1;
  }
  v4 = Buffer;
  if ( !inited )
    v4 = L"0.0.0.0";
  CBdeCfgConsole::PrintConsoleMessage(this, 0x40A00033u, v4);
}

```

## disassembly

```asm
0x140003340  push    rbx
0x140003342  sub     rsp, 470h
0x140003349  mov     rax, cs:__security_cookie
0x140003350  xor     rax, rsp
0x140003353  mov     [rsp+478h+var_18], rax
0x14000335b  mov     rbx, rcx
0x14000335e  mov     qword ptr [rsp+478h+InitOnce], 0
0x14000336a  xor     ecx, ecx; hModule
0x14000336c  lea     rdx, [rsp+478h+Filename]; lpFilename
0x140003371  mov     r8d, 104h; nSize
0x140003377  call    cs:__imp_GetModuleFileNameW
0x14000337d  test    eax, eax
0x14000337f  jz      short loc_140003393
0x140003381  cmp     eax, 104h
0x140003386  jnz     short loc_14000339A
0x140003388  call    cs:__imp_GetLastError
0x14000338e  cmp     eax, 7Ah ; 'z'
0x140003391  jnz     short loc_14000339A
0x140003393  xor     eax, eax
0x140003395  mov     [rsp+478h+Filename], ax
0x14000339a  xor     r9d, r9d; Context
0x14000339d  lea     r8, [rsp+478h+Filename]; Parameter
0x1400033a2  lea     rdx, ?Initialize@ProductVersionHelper@VersionHelpers@@CAHPEAT_RTL_RUN_ONCE@@PEAV12@PEAPEAX@Z; InitFn
0x1400033a9  lea     rcx, [rsp+478h+InitOnce]; InitOnce
0x1400033b1  call    cs:__imp_InitOnceExecuteOnce
0x1400033b7  test    eax, eax
0x1400033b9  jz      short loc_1400033F8
0x1400033bb  movzx   ecx, [rsp+478h+var_23E]
0x1400033c3  lea     r8, aUUU; "%u.%u.%u"
0x1400033ca  movzx   eax, [rsp+478h+var_23C]
0x1400033d2  mov     edx, 104h; BufferCount
0x1400033d7  movzx   r9d, [rsp+478h+var_240]
0x1400033e0  mov     [rsp+478h+var_450], eax
0x1400033e4  mov     [rsp+478h+var_458], ecx
0x1400033e8  lea     rcx, [rsp+478h+Buffer]; Buffer
0x1400033f0  call    cs:__imp_swprintf_s
0x1400033f6  mov     al, 1
0x1400033f8  test    al, al
0x1400033fa  lea     rcx, a0000; "0.0.0.0"
0x140003401  lea     r8, [rsp+478h+Buffer]
0x140003409  mov     edx, 40A00033h; int
0x14000340e  cmovz   r8, rcx
0x140003412  mov     rcx, rbx; this
0x140003415  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJJZZ; CBdeCfgConsole::PrintConsoleMessage(long,...)
0x14000341a  mov     rcx, [rsp+478h+var_18]
0x140003422  xor     rcx, rsp; StackCookie
0x140003425  call    __security_check_cookie
0x14000342a  add     rsp, 470h
0x140003431  pop     rbx
0x140003432  retn
```
