# ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(void)

- ea: `0x1400108c0`
- end: `0x140010933`
- name: `?Release@?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400108c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140010920`
- `msvcrt!??3@YAXPEAX@Z` at `0x140010920`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140010917`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140010917`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(char *a1)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 && a1 )
  {
    *((_DWORD *)a1 + 2) = -1073741823;
    *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
    if ( a1[56] != (_BYTE)v3 )
    {
      a1[56] = v3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    }
    operator delete(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x1400108c0  mov     [rsp+arg_0], rbx
0x1400108c5  push    rdi
0x1400108c6  sub     rsp, 20h
0x1400108ca  mov     rbx, rcx
0x1400108cd  mov     r8d, 7FFFFFFFh
0x1400108d3  mov     ecx, [rcx+8]
0x1400108d6  jmp     short loc_1400108E7
0x1400108d8  lea     edx, [rcx-1]
0x1400108db  mov     eax, ecx
0x1400108dd  lock cmpxchg [rbx+8], edx
0x1400108e2  jz      short loc_1400108EC
0x1400108e4  mov     ecx, [rbx+8]
0x1400108e7  cmp     ecx, r8d
0x1400108ea  jnz     short loc_1400108D8
0x1400108ec  lea     edi, [rcx-1]
0x1400108ef  test    edi, edi
0x1400108f1  jnz     short loc_140010926
0x1400108f3  test    rbx, rbx
0x1400108f6  jz      short loc_140010926
0x1400108f8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1400108ff  mov     dword ptr [rbx+8], 0C0000001h
0x140010906  lea     rcx, [rbx+10h]; lpCriticalSection
0x14001090a  mov     [rbx], rax
0x14001090d  cmp     [rcx+28h], dil
0x140010911  jz      short loc_14001091D
0x140010913  mov     [rcx+28h], dil
0x140010917  call    cs:__imp_DeleteCriticalSection
0x14001091d  mov     rcx, rbx
0x140010920  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140010926  mov     rbx, [rsp+28h+arg_0]
0x14001092b  mov     eax, edi
0x14001092d  add     rsp, 20h
0x140010931  pop     rdi
0x140010932  retn
```
