# DoDllInst(HINSTANCE__ *,int,ushort const *)

- ea: `0x180005d10`
- end: `0x180005d67`
- name: `?DoDllInst@@YAHPEAUHINSTANCE__@@HPEBG@Z`
- size: `87`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800079c0`

## callees

- `0x180005d10`
- `0x18001c010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180005d38`
- `KERNEL32!GetProcAddress` at `0x180005d38`

## string_xrefs

- `0x180005d2a`: `DllInstall`

## pseudocode

```c
__int64 __fastcall DoDllInst(HINSTANCE a1, unsigned int a2, const unsigned __int16 *a3)
{
  const WCHAR *v4; // rdi
  unsigned int v5; // ebx
  FARPROC ProcAddress; // rax

  v4 = &word_18001DE6C;
  v5 = 0;
  if ( a3 )
    v4 = a3;
  ProcAddress = GetProcAddress(a1, "DllInstall");
  if ( ProcAddress && ((int (__fastcall *)(_QWORD, const WCHAR *))ProcAddress)(a2, v4) >= 0 )
    return 1;
  return v5;
}

```

## disassembly

```asm
0x180005d10  mov     [rsp+arg_0], rbx
0x180005d15  mov     [rsp+arg_8], rsi
0x180005d1a  push    rdi
0x180005d1b  sub     rsp, 20h
0x180005d1f  mov     esi, edx
0x180005d21  lea     rdi, word_18001DE6C
0x180005d28  xor     ebx, ebx
0x180005d2a  lea     rdx, aDllinstall_0; "DllInstall"
0x180005d31  test    r8, r8
0x180005d34  cmovnz  rdi, r8
0x180005d38  call    cs:__imp_GetProcAddress
0x180005d3e  test    rax, rax
0x180005d41  jz      short loc_180005D55
0x180005d43  mov     rdx, rdi
0x180005d46  mov     ecx, esi
0x180005d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d4d  test    eax, eax
0x180005d4f  lea     ecx, [rbx+1]
0x180005d52  cmovns  ebx, ecx
0x180005d55  mov     rsi, [rsp+28h+arg_8]
0x180005d5a  mov     eax, ebx
0x180005d5c  mov     rbx, [rsp+28h+arg_0]
0x180005d61  add     rsp, 20h
0x180005d65  pop     rdi
0x180005d66  retn
```
