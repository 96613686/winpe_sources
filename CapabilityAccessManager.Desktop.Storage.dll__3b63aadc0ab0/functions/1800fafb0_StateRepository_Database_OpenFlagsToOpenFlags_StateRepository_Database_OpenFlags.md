# StateRepository::Database::OpenFlagsToOpenFlags(StateRepository::Database::OpenFlags)

- ea: `0x1800fafb0`
- end: `0x1800fb065`
- name: `?OpenFlagsToOpenFlags@Database@StateRepository@@CAHW4OpenFlags@12@@Z`
- size: `181`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800fa944`

## callees

- `0x1800fa588`
- `0x1800fafb0`

## string_xrefs

- `0x1800fafdd`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fb02d`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fafd2`: `Unknown mask_read/write bits, flags=0x%X`
- `0x1800fb022`: `Unknown mask_cache bits, flags=0x%X`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::OpenFlagsToOpenFlags(int a1)
{
  unsigned int v2; // ebx
  int v3; // eax
  char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( (a1 & 3) != 0 )
  {
    if ( (a1 & 3) == 1 )
    {
LABEL_5:
      v2 = 1;
      goto LABEL_8;
    }
    if ( (a1 & 3) != 2 )
    {
      LODWORD(v5) = a1;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xB86,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Unknown mask_read/write bits, flags=0x%X",
        v5);
      goto LABEL_5;
    }
    v2 = 6;
  }
  else
  {
    v2 = 2;
  }
LABEL_8:
  v3 = a1 & 0xC;
  if ( (a1 & 0xC) != 0 )
  {
    if ( v3 == 4 )
    {
      v2 |= 0x20000u;
    }
    else if ( v3 == 8 )
    {
      v2 |= 0x40000u;
    }
    else
    {
      LODWORD(v5) = a1;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xB9C,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Unknown mask_cache bits, flags=0x%X",
        v5);
      v2 |= 1u;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800fafb0  mov     [rsp+arg_0], rbx
0x1800fafb5  push    rdi
0x1800fafb6  sub     rsp, 30h
0x1800fafba  mov     edx, ecx
0x1800fafbc  mov     edi, ecx
0x1800fafbe  and     edx, 3
0x1800fafc1  jz      short loc_1800FB007
0x1800fafc3  sub     edx, 1
0x1800fafc6  jz      short loc_1800FAFF9
0x1800fafc8  cmp     edx, 1
0x1800fafcb  jz      short loc_1800FB000
0x1800fafcd  mov     rcx, [rsp+38h]; this
0x1800fafd2  lea     rax, aUnknownMaskRea; "Unknown mask_read/write bits, flags=0x%"...
0x1800fafd9  mov     dword ptr [rsp+38h+var_10], edi; char *
0x1800fafdd  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fafe4  mov     r9d, 8000FFFFh; char *
0x1800fafea  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800fafef  mov     edx, 0B86h; void *
0x1800faff4  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800faff9  mov     ebx, 1
0x1800faffe  jmp     short loc_1800FB00C
0x1800fb000  mov     ebx, 6
0x1800fb005  jmp     short loc_1800FB00C
0x1800fb007  mov     ebx, 2
0x1800fb00c  mov     eax, edi
0x1800fb00e  and     eax, 0Ch
0x1800fb011  jz      short loc_1800FB058
0x1800fb013  cmp     eax, 4
0x1800fb016  jz      short loc_1800FB054
0x1800fb018  cmp     eax, 8
0x1800fb01b  jz      short loc_1800FB04E
0x1800fb01d  mov     rcx, [rsp+38h]; this
0x1800fb022  lea     rax, aUnknownMaskCac; "Unknown mask_cache bits, flags=0x%X"
0x1800fb029  mov     dword ptr [rsp+38h+var_10], edi; char *
0x1800fb02d  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fb034  mov     r9d, 8000FFFFh; char *
0x1800fb03a  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800fb03f  mov     edx, 0B9Ch; void *
0x1800fb044  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800fb049  or      ebx, 1
0x1800fb04c  jmp     short loc_1800FB058
0x1800fb04e  bts     ebx, 12h
0x1800fb052  jmp     short loc_1800FB058
0x1800fb054  bts     ebx, 11h
0x1800fb058  mov     eax, ebx
0x1800fb05a  mov     rbx, [rsp+38h+arg_0]
0x1800fb05f  add     rsp, 30h
0x1800fb063  pop     rdi
0x1800fb064  retn
```
