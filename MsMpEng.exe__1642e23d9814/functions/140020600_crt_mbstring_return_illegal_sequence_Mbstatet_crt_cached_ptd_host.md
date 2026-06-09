# __crt_mbstring::return_illegal_sequence(_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x140020600`
- end: `0x140020614`
- name: `?return_illegal_sequence@__crt_mbstring@@YA_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `20`
- prototype: `unsigned __int64 __fastcall(__crt_mbstring *__hidden this, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14001abe0`
- `0x14001ada0`
- `0x140020554`

## pseudocode

```c
unsigned __int64 __fastcall __crt_mbstring::return_illegal_sequence(
        __crt_mbstring *this,
        struct _Mbstatet *a2,
        struct __crt_cached_ptd_host *a3)
{
  unsigned __int64 result; // rax

  *(_QWORD *)this = 0;
  result = -1;
  LOBYTE(a2[6]._Wchar) = 1;
  *(_DWORD *)&a2[5]._Byte = 42;
  return result;
}

```

## disassembly

```asm
0x140020600  and     qword ptr [rcx], 0
0x140020604  or      rax, 0FFFFFFFFFFFFFFFFh
0x140020608  mov     byte ptr [rdx+30h], 1
0x14002060c  mov     dword ptr [rdx+2Ch], 2Ah ; '*'
0x140020613  retn
```
