# ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(void)

- ea: `0x140003dc0`
- end: `0x140003e32`
- name: `?Release@?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `114`
- prototype: `__int64 __fastcall(char *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001a00`
- `0x140003dc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003e17`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003e17`

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
0x140003dc0  mov     [rsp+arg_0], rbx
0x140003dc5  push    rdi
0x140003dc6  sub     rsp, 20h
0x140003dca  mov     rbx, rcx
0x140003dcd  mov     r8d, 7FFFFFFFh
0x140003dd3  mov     ecx, [rcx+8]
0x140003dd6  jmp     short loc_140003DE7
0x140003dd8  lea     edx, [rcx-1]
0x140003ddb  mov     eax, ecx
0x140003ddd  lock cmpxchg [rbx+8], edx
0x140003de2  jz      short loc_140003DEC
0x140003de4  mov     ecx, [rbx+8]
0x140003de7  cmp     ecx, r8d
0x140003dea  jnz     short loc_140003DD8
0x140003dec  lea     edi, [rcx-1]
0x140003def  test    edi, edi
0x140003df1  jnz     short loc_140003E25
0x140003df3  test    rbx, rbx
0x140003df6  jz      short loc_140003E25
0x140003df8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x140003dff  mov     dword ptr [rbx+8], 0C0000001h
0x140003e06  lea     rcx, [rbx+10h]; lpCriticalSection
0x140003e0a  mov     [rbx], rax
0x140003e0d  cmp     [rcx+28h], dil
0x140003e11  jz      short loc_140003E1D
0x140003e13  mov     [rcx+28h], dil
0x140003e17  call    cs:__imp_DeleteCriticalSection
0x140003e1d  mov     rcx, rbx; Block
0x140003e20  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003e25  mov     rbx, [rsp+28h+arg_0]
0x140003e2a  mov     eax, edi
0x140003e2c  add     rsp, 20h
0x140003e30  pop     rdi
0x140003e31  retn
```
