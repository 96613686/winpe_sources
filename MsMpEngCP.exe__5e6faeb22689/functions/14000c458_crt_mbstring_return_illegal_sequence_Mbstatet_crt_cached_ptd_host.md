# __crt_mbstring::return_illegal_sequence(_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x14000c458`
- end: `0x14000c46c`
- name: `?return_illegal_sequence@__crt_mbstring@@YA_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `20`
- prototype: `unsigned __int64 __fastcall(__crt_mbstring *__hidden this, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14000a65c`

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
0x14000c458  and     qword ptr [rcx], 0
0x14000c45c  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c460  mov     byte ptr [rdx+30h], 1
0x14000c464  mov     dword ptr [rdx+2Ch], 2Ah ; '*'
0x14000c46b  retn
```
