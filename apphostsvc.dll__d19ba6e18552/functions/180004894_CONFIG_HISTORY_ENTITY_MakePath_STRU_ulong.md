# CONFIG_HISTORY_ENTITY::MakePath(STRU *,ulong)

- ea: `0x180004894`
- end: `0x1800048f4`
- name: `?MakePath@CONFIG_HISTORY_ENTITY@@QEAAJPEAVSTRU@@K@Z`
- size: `96`
- prototype: `__int64 __fastcall(CONFIG_HISTORY_ENTITY *this, struct STRU *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004b0c`
- `0x180004d98`
- `0x180005110`

## callees

- `0x180004894`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800048d0`
- `msvcrt!swprintf_s` at `0x1800048d0`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800048e6`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800048e6`

## pseudocode

```c
__int64 __fastcall CONFIG_HISTORY_ENTITY::MakePath(CONFIG_HISTORY_ENTITY *this, struct STRU *a2, int a3)
{
  signed int v4; // eax

  **((_WORD **)a2 + 4) = 0;
  *((_DWORD *)a2 + 12) = 0;
  v4 = swprintf_s(
         *((wchar_t *const *)a2 + 4),
         (unsigned __int64)*((unsigned int *)a2 + 10) >> 1,
         L"%s\\%s%010u",
         *((_QWORD *)this + 5),
         L"CFGHISTORY_",
         a3);
  if ( v4 < 0 )
    return 2147942487LL;
  STRU::SetLen(a2, v4);
  return 0;
}

```

## disassembly

```asm
0x180004894  push    rbx
0x180004896  sub     rsp, 30h
0x18000489a  mov     r9, [rdx+20h]
0x18000489e  xor     eax, eax
0x1800048a0  mov     rbx, rdx
0x1800048a3  mov     [rsp+38h+var_10], r8d
0x1800048a8  lea     r8, aSS010u; "%s\\%s%010u"
0x1800048af  mov     [r9], ax
0x1800048b3  mov     [rdx+30h], eax
0x1800048b6  lea     rax, aCfghistory; "CFGHISTORY_"
0x1800048bd  mov     edx, [rdx+28h]
0x1800048c0  mov     r9, [rcx+28h]
0x1800048c4  mov     rcx, [rbx+20h]; Buffer
0x1800048c8  shr     rdx, 1; BufferCount
0x1800048cb  mov     [rsp+38h+var_18], rax
0x1800048d0  call    cs:__imp_swprintf_s
0x1800048d6  test    eax, eax
0x1800048d8  jns     short loc_1800048E1
0x1800048da  mov     eax, 80070057h
0x1800048df  jmp     short loc_1800048EE
0x1800048e1  mov     edx, eax
0x1800048e3  mov     rcx, rbx
0x1800048e6  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x1800048ec  xor     eax, eax
0x1800048ee  add     rsp, 30h
0x1800048f2  pop     rbx
0x1800048f3  retn
```
