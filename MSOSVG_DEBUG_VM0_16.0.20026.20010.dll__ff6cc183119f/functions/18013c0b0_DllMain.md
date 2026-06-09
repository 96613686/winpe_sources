# DllMain

- ea: `0x18013c0b0`
- end: `0x18013c1f2`
- name: `DllMain`
- size: `322`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18013d4e4`

## callees

- `0x18013c0b0`
- `0x18013c1f4`
- `0x18013c418`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x18013c133`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18013c133`
- `KERNEL32!GetModuleFileNameW` at `0x18013c10a`
- `KERNEL32!GetModuleFileNameW` at `0x18013c10a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18013c1b3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18013c1c1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18013c1cf`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18013c1dd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18013c1eb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18013c1b3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18013c1c1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18013c1cf`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18013c1dd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18013c1eb`
- `VCRUNTIME140!wcsrchr` at `0x18013c122`
- `VCRUNTIME140!wcsrchr` at `0x18013c122`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  wchar_t *v4; // rax
  __int64 v6; // [rsp+20h] [rbp-60h] BYREF
  bool v7; // [rsp+28h] [rbp-58h]
  __int64 v8; // [rsp+30h] [rbp-50h]
  _OWORD v9[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v10; // [rsp+60h] [rbp-20h]
  const wchar_t *v11; // [rsp+68h] [rbp-18h]
  int v12; // [rsp+70h] [rbp-10h]
  int v13; // [rsp+74h] [rbp-Ch]
  int v14; // [rsp+78h] [rbp-8h]

  if ( fdwReason == 1 )
  {
    if ( !hinstDLL )
      goto LABEL_12;
    if ( qword_180194DE8 )
    {
      CrashWithRecovery(0x7CB448u, 0);
    }
    else
    {
      qword_180194DE8 = (__int64)hinstDLL;
      if ( !Str[0] )
      {
        if ( !GetModuleFileNameW(hinstDLL, Str, 0x104u) )
        {
          CrashWithRecovery(0x7CB44Cu, 0);
          JUMPOUT(0x18013C1F1LL);
        }
        v4 = wcsrchr(Str, 0x5Cu);
        if ( v4 )
        {
          *v4 = 0;
          DisableThreadLibraryCalls(hinstDLL);
          memset(v9, 0, sizeof(v9));
          v10 = 0;
          v11 = L"Office";
          v12 = 0;
          v13 = 2;
          v14 = -2;
          Mso::LibletAPI::InitLiblets(v9);
          return 1;
        }
        CrashWithRecovery(0x7CB44Du, 0);
LABEL_12:
        CrashWithRecovery(0x7CB447u, 0);
        __debugbreak();
      }
    }
    CrashWithRecovery(0x7CB44Bu, 0);
    __debugbreak();
  }
  if ( !fdwReason )
  {
    v6 = 0;
    v8 = 0;
    v7 = lpvReserved != 0;
    Mso::LibletAPI::UninitLiblets(&v6);
  }
  return 1;
}

```

## disassembly

```asm
0x18013c0b0  mov     [rsp-8+arg_0], rbx
0x18013c0b5  mov     [rsp-8+arg_8], rdi
0x18013c0ba  push    rbp
0x18013c0bb  mov     rbp, rsp
0x18013c0be  sub     rsp, 80h
0x18013c0c5  mov     rdi, rcx
0x18013c0c8  cmp     edx, 1
0x18013c0cb  jnz     loc_18013C174
0x18013c0d1  xor     ebx, ebx
0x18013c0d3  test    rcx, rcx
0x18013c0d6  jz      loc_18013C1BA
0x18013c0dc  cmp     cs:qword_180194DE8, rbx
0x18013c0e3  jnz     loc_18013C1C8
0x18013c0e9  mov     cs:qword_180194DE8, rcx
0x18013c0f0  cmp     cs:Str, bx
0x18013c0f7  jnz     loc_18013C1D6
0x18013c0fd  mov     r8d, 104h; nSize
0x18013c103  lea     rdx, Str; lpFilename
0x18013c10a  call    cs:__imp_GetModuleFileNameW
0x18013c110  test    eax, eax
0x18013c112  jz      loc_18013C1E4
0x18013c118  lea     edx, [rbx+5Ch]; Ch
0x18013c11b  lea     rcx, Str; Str
0x18013c122  call    cs:__imp_wcsrchr
0x18013c128  test    rax, rax
0x18013c12b  jz      short loc_18013C1AC
0x18013c12d  mov     [rax], bx
0x18013c130  mov     rcx, rdi; hLibModule
0x18013c133  call    cs:__imp_DisableThreadLibraryCalls
0x18013c139  xorps   xmm0, xmm0
0x18013c13c  movdqa  [rbp+var_40], xmm0
0x18013c141  xorps   xmm1, xmm1
0x18013c144  movdqa  [rbp+var_30], xmm1
0x18013c149  mov     [rbp+var_20], rbx
0x18013c14d  lea     rax, aOffice; "Office"
0x18013c154  mov     [rbp+var_18], rax
0x18013c158  mov     [rbp+var_10], ebx
0x18013c15b  mov     [rbp+var_C], 2
0x18013c162  mov     [rbp+var_8], 0FFFFFFFEh
0x18013c169  lea     rcx, [rbp+var_40]
0x18013c16d  call    ?InitLiblets@LibletAPI@Mso@@YAXAEAUInitData@12@W4InitIteration@12@@Z; Mso::LibletAPI::InitLiblets(Mso::LibletAPI::InitData &,Mso::LibletAPI::InitIteration)
0x18013c172  jmp     short loc_18013C192
0x18013c174  xor     ebx, ebx
0x18013c176  test    edx, edx
0x18013c178  jnz     short loc_18013C192
0x18013c17a  mov     [rbp+var_60], rbx
0x18013c17e  mov     [rbp+var_50], rbx
0x18013c182  test    r8, r8
0x18013c185  setnz   [rbp+var_58]
0x18013c189  lea     rcx, [rbp+var_60]
0x18013c18d  call    ?UninitLiblets@LibletAPI@Mso@@YAXAEAUUninitData@12@W4InitIteration@12@@Z; Mso::LibletAPI::UninitLiblets(Mso::LibletAPI::UninitData &,Mso::LibletAPI::InitIteration)
0x18013c192  mov     eax, 1
0x18013c197  lea     r11, [rsp+80h+var_s0]
0x18013c19f  mov     rbx, [r11+10h]
0x18013c1a3  mov     rdi, [r11+18h]
0x18013c1a7  mov     rsp, r11
0x18013c1aa  pop     rbp
0x18013c1ab  retn
0x18013c1ac  xor     edx, edx
0x18013c1ae  mov     ecx, 7CB44Dh
0x18013c1b3  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18013c1b9  nop
0x18013c1ba  xor     edx, edx
0x18013c1bc  mov     ecx, 7CB447h
0x18013c1c1  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18013c1c7  int     3; Trap to Debugger
0x18013c1c8  xor     edx, edx
0x18013c1ca  mov     ecx, 7CB448h
0x18013c1cf  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18013c1d5  nop
0x18013c1d6  xor     edx, edx
0x18013c1d8  mov     ecx, 7CB44Bh
0x18013c1dd  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18013c1e3  int     3; Trap to Debugger
0x18013c1e4  xor     edx, edx
0x18013c1e6  mov     ecx, 7CB44Ch
0x18013c1eb  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
