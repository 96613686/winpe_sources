# CompareRuleHitCountsById(void const *,void const *)

- ea: `0x140003040`
- end: `0x140003097`
- name: `?CompareRuleHitCountsById@@YAHPEBX0@Z`
- size: `87`
- prototype: `int __fastcall(char *, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003040`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140003065`
- `msvcrt!_wcsnicmp` at `0x14000307c`
- `msvcrt!_wcsnicmp` at `0x140003065`
- `msvcrt!_wcsnicmp` at `0x14000307c`

## pseudocode

```c
int __fastcall CompareRuleHitCountsById(char *a1, _DWORD *a2)
{
  unsigned int v2; // eax
  __int64 v5; // rcx
  int result; // eax

  v2 = *((_DWORD *)a1 + 1);
  v5 = *(unsigned int *)a1;
  if ( v2 == a2[1] )
    return _wcsnicmp((const wchar_t *)&a1[v5], (const wchar_t *)((char *)a2 + (unsigned int)*a2), v2);
  if ( v2 >= a2[1] )
    v2 = a2[1];
  result = _wcsnicmp((const wchar_t *)&a1[v5], (const wchar_t *)((char *)a2 + (unsigned int)*a2), v2);
  if ( !result )
    return *((_DWORD *)a1 + 1) - a2[1];
  return result;
}

```

## disassembly

```asm
0x140003040  mov     [rsp+arg_0], rbx
0x140003045  push    rdi
0x140003046  sub     rsp, 20h
0x14000304a  mov     eax, [rcx+4]
0x14000304d  mov     rdi, rcx
0x140003050  mov     rbx, rdx
0x140003053  mov     ecx, [rcx]
0x140003055  cmp     eax, [rdx+4]
0x140003058  jnz     short loc_14000306D
0x14000305a  mov     edx, [rdx]
0x14000305c  mov     r8d, eax; MaxCount
0x14000305f  add     rdx, rbx; String2
0x140003062  add     rcx, rdi; String1
0x140003065  call    cs:__imp__wcsnicmp
0x14000306b  jmp     short loc_14000308C
0x14000306d  cmovnb  eax, [rdx+4]
0x140003071  add     rcx, rdi; String1
0x140003074  mov     edx, [rdx]
0x140003076  add     rdx, rbx; String2
0x140003079  mov     r8d, eax; MaxCount
0x14000307c  call    cs:__imp__wcsnicmp
0x140003082  test    eax, eax
0x140003084  jnz     short loc_14000308C
0x140003086  mov     eax, [rdi+4]
0x140003089  sub     eax, [rbx+4]
0x14000308c  mov     rbx, [rsp+28h+arg_0]
0x140003091  add     rsp, 20h
0x140003095  pop     rdi
0x140003096  retn
```
