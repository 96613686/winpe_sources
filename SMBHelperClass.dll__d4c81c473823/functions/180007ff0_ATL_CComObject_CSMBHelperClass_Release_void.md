# ATL::CComObject<CSMBHelperClass>::Release(void)

- ea: `0x180007ff0`
- end: `0x180008074`
- name: `?Release@?$CComObject@VCSMBHelperClass@@@ATL@@UEAAKXZ`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008080`
- `0x180008090`

## callees

- `0x180007ff0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSMBHelperClass>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 16);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 16, i - 1, i);
        i = *((_DWORD *)a1 + 16) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 168LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180007ff0  mov     [rsp+arg_0], rbx
0x180007ff5  push    rdi
0x180007ff6  sub     rsp, 20h
0x180007ffa  mov     r8d, [rcx+40h]
0x180007ffe  mov     rbx, rcx
0x180008001  mov     ecx, 7FFFFFFFh
0x180008006  jmp     short loc_18000801A
0x180008008  lea     edx, [r8-1]
0x18000800c  mov     eax, r8d
0x18000800f  lock cmpxchg [rbx+40h], edx
0x180008014  jz      short loc_18000801F
0x180008016  mov     r8d, [rbx+40h]
0x18000801a  cmp     r8d, ecx
0x18000801d  jnz     short loc_180008008
0x18000801f  lea     edi, [r8-1]
0x180008023  test    edi, edi
0x180008025  jnz     short loc_180008067
0x180008027  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000802e  mov     rax, [rcx]
0x180008031  mov     rax, [rax+8]
0x180008035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000803a  test    rbx, rbx
0x18000803d  jz      short loc_180008054
0x18000803f  mov     rax, [rbx]
0x180008042  lea     edx, [rdi+1]
0x180008045  mov     rcx, rbx
0x180008048  mov     rax, [rax+0A8h]
0x18000804f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008054  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000805b  mov     rdx, [rcx]
0x18000805e  mov     rax, [rdx+10h]
0x180008062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008067  mov     rbx, [rsp+28h+arg_0]
0x18000806c  mov     eax, edi
0x18000806e  add     rsp, 20h
0x180008072  pop     rdi
0x180008073  retn
```
