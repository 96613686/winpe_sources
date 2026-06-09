# Sqm::SqmSession::Instance(void)

- ea: `0x1800047e4`
- end: `0x18000484b`
- name: `?Instance@SqmSession@Sqm@@SAPEAV12@XZ`
- size: `103`
- prototype: `struct Sqm::SqmSession *(void)`
- caller_count: `26`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003010`
- `0x180003070`
- `0x1800030a0`
- `0x1800030e0`
- `0x180003120`
- `0x180003160`
- `0x1800033f0`
- `0x180003520`
- `0x1800036a0`
- `0x180003800`
- `0x180003840`
- `0x180003ab0`
- `0x180003ba0`
- `0x180003bf0`
- `0x1800044d0`
- `0x180004860`
- `0x180004880`
- `0x180004f70`
- `0x180005510`
- `0x180006260`
- `0x1800065e0`
- `0x180006640`
- `0x1800066a0`
- `0x180006850`
- `0x1800069c0`
- `0x180006af0`

## callees

- `0x180001938`
- `0x180001a70`
- `0x180001ad8`
- `0x180002a24`
- `0x1800047e4`

## pseudocode

```c
struct Sqm::SqmSession *Sqm::SqmSession::Instance(void)
{
  Sqm::SqmSession *v1; // rcx

  if ( dword_18000D350 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18000D350);
    if ( dword_18000D350 == -1 )
    {
      Sqm::SqmSession::SqmSession(v1);
      atexit(Sqm::SqmSession::Instance_::_2_::_dynamic_atexit_destructor_for__inst__);
      Init_thread_footer(&dword_18000D350);
    }
  }
  return (struct Sqm::SqmSession *)&qword_18000D360;
}

```

## disassembly

```asm
0x1800047e4  sub     rsp, 28h
0x1800047e8  mov     ecx, cs:_tls_index
0x1800047ee  mov     rax, gs:58h
0x1800047f7  mov     edx, 4
0x1800047fc  mov     rax, [rax+rcx*8]
0x180004800  mov     eax, [rdx+rax]
0x180004803  cmp     cs:dword_18000D350, eax
0x180004809  jg      short loc_180004817
0x18000480b  lea     rax, qword_18000D360
0x180004812  add     rsp, 28h
0x180004816  retn
0x180004817  lea     rcx, dword_18000D350
0x18000481e  call    _Init_thread_header
0x180004823  cmp     cs:dword_18000D350, 0FFFFFFFFh
0x18000482a  jnz     short loc_18000480B
0x18000482c  call    ??0SqmSession@Sqm@@AEAA@XZ; Sqm::SqmSession::SqmSession(void)
0x180004831  lea     rcx, _Sqm__SqmSession__Instance____2____dynamic_atexit_destructor_for__inst__; void (__cdecl *)()
0x180004838  call    atexit
0x18000483d  lea     rcx, dword_18000D350
0x180004844  call    _Init_thread_footer
0x180004849  jmp     short loc_18000480B
```
