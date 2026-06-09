# ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(ATL::CAutoPtr<ATL::CDacl::CAccessAce> *,unsigned __int64)

- ea: `0x140012fc0`
- end: `0x140013016`
- name: `?CallDestructors@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@CAXPEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@2@_K@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140012710`
- `0x140012930`
- `0x140013018`

## callees

- `0x140012fc0`
- `0x140014c70`

## pseudocode

```c
__int64 __fastcall ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 i; // rbx
  __int64 (__fastcall ***v5)(_QWORD, __int64); // rcx
  __int64 result; // rax

  if ( a2 )
  {
    for ( i = 0; i < a2; ++i )
    {
      v5 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a1 + 8 * i);
      if ( v5 )
        result = (**v5)(v5, 1);
      *(_QWORD *)(a1 + 8 * i) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140012fc0  test    rdx, rdx
0x140012fc3  jz      short locret_140013015
0x140012fc5  mov     [rsp+arg_0], rbx
0x140012fca  mov     [rsp+arg_8], rsi
0x140012fcf  push    rdi
0x140012fd0  sub     rsp, 20h
0x140012fd4  mov     rdi, rdx
0x140012fd7  mov     rsi, rcx
0x140012fda  xor     ebx, ebx
0x140012fdc  mov     rcx, [rsi+rbx*8]
0x140012fe0  test    rcx, rcx
0x140012fe3  jz      short loc_140012FF6
0x140012fe5  mov     rax, [rcx]
0x140012fe8  mov     edx, 1
0x140012fed  mov     rax, [rax]
0x140012ff0  call    cs:__guard_dispatch_icall_fptr
0x140012ff6  mov     qword ptr [rsi+rbx*8], 0
0x140012ffe  inc     rbx
0x140013001  cmp     rbx, rdi
0x140013004  jb      short loc_140012FDC
0x140013006  mov     rbx, [rsp+28h+arg_0]
0x14001300b  mov     rsi, [rsp+28h+arg_8]
0x140013010  add     rsp, 20h
0x140013014  pop     rdi
0x140013015  retn
```
