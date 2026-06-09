# ATL::CComObject<CALACDecMFT>::Release(void)

- ea: `0x1800068e0`
- end: `0x18000696d`
- name: `?Release@?$CComObject@VCALACDecMFT@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CALACDecMFT>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 38);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 38, i - 1, i);
        i = *((_DWORD *)a1 + 38) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 368LL))(a1, v3 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800068e0  mov     [rsp+arg_0], rbx
0x1800068e5  push    rdi
0x1800068e6  sub     rsp, 20h
0x1800068ea  mov     r8d, [rcx+98h]
0x1800068f1  mov     rbx, rcx
0x1800068f4  mov     ecx, 7FFFFFFFh
0x1800068f9  jmp     short loc_180006913
0x1800068fb  lea     edx, [r8-1]
0x1800068ff  mov     eax, r8d
0x180006902  lock cmpxchg [rbx+98h], edx
0x18000690a  jz      short loc_180006918
0x18000690c  mov     r8d, [rbx+98h]
0x180006913  cmp     r8d, ecx
0x180006916  jnz     short loc_1800068FB
0x180006918  lea     edi, [r8-1]
0x18000691c  test    edi, edi
0x18000691e  jnz     short loc_180006960
0x180006920  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006927  mov     rax, [rcx]
0x18000692a  mov     rax, [rax+8]
0x18000692e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006933  test    rbx, rbx
0x180006936  jz      short loc_18000694D
0x180006938  mov     rax, [rbx]
0x18000693b  lea     edx, [rdi+1]
0x18000693e  mov     rcx, rbx
0x180006941  mov     rax, [rax+170h]
0x180006948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000694d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006954  mov     rdx, [rcx]
0x180006957  mov     rax, [rdx+10h]
0x18000695b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006960  mov     rbx, [rsp+28h+arg_0]
0x180006965  mov     eax, edi
0x180006967  add     rsp, 20h
0x18000696b  pop     rdi
0x18000696c  retn
```
