# sub_1801CDCC0

- ea: `0x1801cdcc0`
- end: `0x1801cdd91`
- name: `sub_1801CDCC0`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1801cdba8`
- `0x1801cdcc0`
- `0x1801ceaa4`
- `0x1801ceb0c`
- `0x1801ceb60`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_stricmp` at `0x1801cdd14`
- `api-ms-win-crt-string-l1-1-0!_stricmp` at `0x1801cdd30`
- `api-ms-win-crt-string-l1-1-0!_stricmp` at `0x1801cdd4c`
- `api-ms-win-crt-string-l1-1-0!_stricmp` at `0x1801cdd68`
- `api-ms-win-crt-string-l1-1-0!_stricmp` at `0x1801cdd14`
- `api-ms-win-crt-string-l1-1-0!_stricmp` at `0x1801cdd30`
- `api-ms-win-crt-string-l1-1-0!_stricmp` at `0x1801cdd4c`
- `api-ms-win-crt-string-l1-1-0!_stricmp` at `0x1801cdd68`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x1801cdd06`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x1801cdd06`

## string_xrefs

- `0x1801cdd61`: `cpprestsdk.dll`
- `0x1801cdd45`: `aceerr.dll`
- `0x1801cdd29`: `acecore.dll`
- `0x1801cdd0d`: `acewstr.dll`

## pseudocode

```c
__int64 __fastcall sub_1801CDCC0(int a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rcx

  if ( a1 == 1 )
  {
    v3 = 0;
    if ( (unsigned __int8)sub_1801CEB0C(*(char **)(a2 + 24)) )
    {
      v3 = sub_1801CEB60(*(char **)(a2 + 24));
      if ( !v3 )
      {
        sub_1801CEAA4();
        Mso20Win32Client_21217(0, 0);
        __debugbreak();
      }
      return v3;
    }
    if ( !stricmp("acewstr.dll", *(const char **)(a2 + 24)) )
    {
      v4 = 0x80000;
    }
    else if ( !stricmp("acecore.dll", *(const char **)(a2 + 24)) )
    {
      v4 = 524291;
    }
    else if ( !stricmp("aceerr.dll", *(const char **)(a2 + 24)) )
    {
      v4 = 524290;
    }
    else
    {
      if ( stricmp("cpprestsdk.dll", *(const char **)(a2 + 24)) )
        return v3;
      v4 = 524297;
    }
    return sub_1801CDBA8(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x1801cdcc0  mov     [rsp+arg_0], rbx
0x1801cdcc5  push    rdi
0x1801cdcc6  sub     rsp, 20h
0x1801cdcca  mov     rdi, rdx
0x1801cdccd  cmp     ecx, 1
0x1801cdcd0  jnz     loc_1801CDD84
0x1801cdcd6  mov     rcx, [rdx+18h]; String2
0x1801cdcda  xor     ebx, ebx
0x1801cdcdc  call    sub_1801CEB0C
0x1801cdce1  mov     rdx, [rdi+18h]; String2
0x1801cdce5  test    al, al
0x1801cdce7  jz      short loc_1801CDD0D
0x1801cdce9  mov     rcx, rdx; String2
0x1801cdcec  call    sub_1801CEB60
0x1801cdcf1  mov     rbx, rax
0x1801cdcf4  test    rax, rax
0x1801cdcf7  jnz     loc_1801CDD7F
0x1801cdcfd  call    sub_1801CEAA4
0x1801cdd02  xor     edx, edx
0x1801cdd04  xor     ecx, ecx
0x1801cdd06  call    cs:Mso20Win32Client_21217
0x1801cdd0c  int     3; Trap to Debugger
0x1801cdd0d  lea     rcx, aAcewstrDll_0; "acewstr.dll"
0x1801cdd14  call    cs:_stricmp
0x1801cdd1a  test    eax, eax
0x1801cdd1c  jnz     short loc_1801CDD25
0x1801cdd1e  mov     ecx, 80000h
0x1801cdd23  jmp     short loc_1801CDD77
0x1801cdd25  mov     rdx, [rdi+18h]; String2
0x1801cdd29  lea     rcx, aAcecoreDll_1; "acecore.dll"
0x1801cdd30  call    cs:_stricmp
0x1801cdd36  test    eax, eax
0x1801cdd38  jnz     short loc_1801CDD41
0x1801cdd3a  mov     ecx, 80003h
0x1801cdd3f  jmp     short loc_1801CDD77
0x1801cdd41  mov     rdx, [rdi+18h]; String2
0x1801cdd45  lea     rcx, aAceerrDll_0; "aceerr.dll"
0x1801cdd4c  call    cs:_stricmp
0x1801cdd52  test    eax, eax
0x1801cdd54  jnz     short loc_1801CDD5D
0x1801cdd56  mov     ecx, 80002h
0x1801cdd5b  jmp     short loc_1801CDD77
0x1801cdd5d  mov     rdx, [rdi+18h]; String2
0x1801cdd61  lea     rcx, aCpprestsdkDll; "cpprestsdk.dll"
0x1801cdd68  call    cs:_stricmp
0x1801cdd6e  test    eax, eax
0x1801cdd70  jnz     short loc_1801CDD7F
0x1801cdd72  mov     ecx, 80009h
0x1801cdd77  call    sub_1801CDBA8
0x1801cdd7c  mov     rbx, rax
0x1801cdd7f  mov     rax, rbx
0x1801cdd82  jmp     short loc_1801CDD86
0x1801cdd84  xor     eax, eax
0x1801cdd86  mov     rbx, [rsp+28h+arg_0]
0x1801cdd8b  add     rsp, 20h
0x1801cdd8f  pop     rdi
0x1801cdd90  retn
```
