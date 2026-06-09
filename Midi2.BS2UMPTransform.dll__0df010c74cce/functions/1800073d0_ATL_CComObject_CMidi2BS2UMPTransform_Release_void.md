# ATL::CComObject<CMidi2BS2UMPTransform>::Release(void)

- ea: `0x1800073d0`
- end: `0x180007451`
- name: `?Release@?$CComObject@VCMidi2BS2UMPTransform@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800073d0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMidi2BS2UMPTransform>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800073d0  mov     [rsp+arg_0], rbx
0x1800073d5  push    rdi
0x1800073d6  sub     rsp, 20h
0x1800073da  mov     r8d, [rcx+8]
0x1800073de  mov     rbx, rcx
0x1800073e1  mov     ecx, 7FFFFFFFh
0x1800073e6  jmp     short loc_1800073FA
0x1800073e8  lea     edx, [r8-1]
0x1800073ec  mov     eax, r8d
0x1800073ef  lock cmpxchg [rbx+8], edx
0x1800073f4  jz      short loc_1800073FF
0x1800073f6  mov     r8d, [rbx+8]
0x1800073fa  cmp     r8d, ecx
0x1800073fd  jnz     short loc_1800073E8
0x1800073ff  lea     edi, [r8-1]
0x180007403  test    edi, edi
0x180007405  jnz     short loc_180007444
0x180007407  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000740e  mov     rax, [rcx]
0x180007411  mov     rax, [rax+8]
0x180007415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000741a  test    rbx, rbx
0x18000741d  jz      short loc_180007431
0x18000741f  mov     rax, [rbx]
0x180007422  lea     edx, [rdi+1]
0x180007425  mov     rcx, rbx
0x180007428  mov     rax, [rax+20h]
0x18000742c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007431  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007438  mov     rdx, [rcx]
0x18000743b  mov     rax, [rdx+10h]
0x18000743f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007444  mov     rbx, [rsp+28h+arg_0]
0x180007449  mov     eax, edi
0x18000744b  add     rsp, 20h
0x18000744f  pop     rdi
0x180007450  retn
```
