# AslPathToSystemPath

- ea: `0x140040310`
- end: `0x1400403c4`
- name: `AslPathToSystemPath`
- size: `180`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14004506c`

## callees

- `0x1400079f0`
- `0x14003e364`
- `0x14003e76c`
- `0x140040310`
- `0x1400403cc`

## string_xrefs

- `0x14004039e`: `AslPathToSystemPath`
- `0x140040391`: `AslPathToSystemPathBuf failed [%x]`
- `0x1400403b5`: `Failed to allocate path string [%x]`

## pseudocode

```c
__int64 __fastcall AslPathToSystemPath(_QWORD *a1, __int64 a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  const char *v6; // r9
  __int64 v7; // r8
  int v8; // [rsp+20h] [rbp-238h]
  _WORD v9[264]; // [rsp+30h] [rbp-228h] BYREF

  *a1 = 0;
  v9[0] = 0;
  v3 = AslPathToSystemPathBuf(v9, 260, a2);
  v4 = v3;
  if ( v3 < 0 )
  {
    v6 = "AslPathToSystemPathBuf failed [%x]";
    v7 = 1537;
LABEL_6:
    v8 = v3;
    AslLogCallPrintf(1, "AslPathToSystemPath", v7, v6, v8);
    return v4;
  }
  v3 = AslStringDuplicate(a1, v9);
  v4 = v3;
  if ( v3 < 0 )
  {
    v6 = "Failed to allocate path string [%x]";
    v7 = 1543;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x140040310  mov     [rsp+arg_10], rbx
0x140040315  push    rdi
0x140040316  sub     rsp, 250h
0x14004031d  mov     rax, cs:__security_cookie
0x140040324  xor     rax, rsp
0x140040327  mov     [rsp+258h+var_18], rax
0x14004032f  mov     rdi, rcx
0x140040332  mov     qword ptr [rcx], 0
0x140040339  xor     eax, eax
0x14004033b  lea     rcx, [rsp+258h+var_228]
0x140040340  mov     r8, rdx
0x140040343  mov     [rsp+258h+var_228], ax
0x140040348  mov     edx, 104h
0x14004034d  call    AslPathToSystemPathBuf
0x140040352  mov     ebx, eax
0x140040354  test    eax, eax
0x140040356  js      short loc_140040391
0x140040358  lea     rdx, [rsp+258h+var_228]
0x14004035d  mov     rcx, rdi
0x140040360  call    AslStringDuplicate
0x140040365  mov     ebx, eax
0x140040367  test    eax, eax
0x140040369  js      short loc_1400403B5
0x14004036b  xor     ebx, ebx
0x14004036d  mov     eax, ebx
0x14004036f  mov     rcx, [rsp+258h+var_18]
0x140040377  xor     rcx, rsp; StackCookie
0x14004037a  call    __security_check_cookie
0x14004037f  mov     rbx, [rsp+258h+arg_10]
0x140040387  add     rsp, 250h
0x14004038e  pop     rdi
0x14004038f  retn
0x140040391  lea     r9, aAslpathtosyste; "AslPathToSystemPathBuf failed [%x]"
0x140040398  mov     r8d, 601h
0x14004039e  lea     rdx, aAslpathtosyste_1; "AslPathToSystemPath"
0x1400403a5  mov     [rsp+258h+var_238], eax
0x1400403a9  mov     ecx, 1
0x1400403ae  call    AslLogCallPrintf
0x1400403b3  jmp     short loc_14004036D
0x1400403b5  lea     r9, aFailedToAlloca_9; "Failed to allocate path string [%x]"
0x1400403bc  mov     r8d, 607h
0x1400403c2  jmp     short loc_14004039E
```
