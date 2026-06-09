# ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(void)

- ea: `0x140006220`
- end: `0x140006297`
- name: `?Release@?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `119`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001f64`
- `0x140006220`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140006277`
- `KERNEL32!DeleteCriticalSection` at `0x140006277`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(char *Block)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)Block + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)Block + 2, i - 1, i);
        i = *((_DWORD *)Block + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 && Block )
  {
    *((_DWORD *)Block + 2) = -1073741823;
    *(_QWORD *)Block = &ATL::CComClassFactory::`vftable';
    if ( Block[56] != (_BYTE)v3 )
    {
      Block[56] = v3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
    }
    operator delete(Block);
  }
  return v3;
}

```

## disassembly

```asm
0x140006220  mov     [rsp+arg_0], rbx
0x140006225  push    rdi
0x140006226  sub     rsp, 20h
0x14000622a  mov     rbx, rcx
0x14000622d  mov     r8d, 7FFFFFFFh
0x140006233  mov     ecx, [rcx+8]
0x140006236  jmp     short loc_140006247
0x140006238  lea     edx, [rcx-1]
0x14000623b  mov     eax, ecx
0x14000623d  lock cmpxchg [rbx+8], edx
0x140006242  jz      short loc_14000624C
0x140006244  mov     ecx, [rbx+8]
0x140006247  cmp     ecx, r8d
0x14000624a  jnz     short loc_140006238
0x14000624c  lea     edi, [rcx-1]
0x14000624f  test    edi, edi
0x140006251  jnz     short loc_14000628A
0x140006253  test    rbx, rbx
0x140006256  jz      short loc_14000628A
0x140006258  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x14000625f  mov     dword ptr [rbx+8], 0C0000001h
0x140006266  lea     rcx, [rbx+10h]; lpCriticalSection
0x14000626a  mov     [rbx], rax
0x14000626d  cmp     [rcx+28h], dil
0x140006271  jz      short loc_14000627D
0x140006273  mov     [rcx+28h], dil
0x140006277  call    cs:__imp_DeleteCriticalSection
0x14000627d  mov     edx, 48h ; 'H'
0x140006282  mov     rcx, rbx; Block
0x140006285  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000628a  mov     rbx, [rsp+28h+arg_0]
0x14000628f  mov     eax, edi
0x140006291  add     rsp, 20h
0x140006295  pop     rdi
0x140006296  retn
```
