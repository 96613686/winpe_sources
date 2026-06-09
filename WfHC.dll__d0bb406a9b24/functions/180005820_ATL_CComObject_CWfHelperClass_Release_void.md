# ATL::CComObject<CWfHelperClass>::Release(void)

- ea: `0x180005820`
- end: `0x1800058b2`
- name: `?Release@?$CComObject@VCWfHelperClass@@@ATL@@UEAAKXZ`
- size: `146`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800058c0`
- `0x1800058d0`

## callees

- `0x180005820`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWfHelperClass>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 16); i != 0x7FFFFFFF; i = *((_DWORD *)a1 + 16) )
  {
    if ( i == _InterlockedCompareExchange(a1 + 16, i - 1, i) )
      break;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 168LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180005820  mov     [rsp+arg_0], rbx
0x180005825  push    rdi
0x180005826  sub     rsp, 20h
0x18000582a  mov     r8d, [rcx+40h]
0x18000582e  mov     rbx, rcx
0x180005831  cmp     r8d, 7FFFFFFFh
0x180005838  jz      short loc_18000585B
0x18000583a  nop     word ptr [rax+rax+00h]
0x180005840  lea     edx, [r8-1]
0x180005844  mov     eax, r8d
0x180005847  lock cmpxchg [rcx+40h], edx
0x18000584c  jz      short loc_18000585B
0x18000584e  mov     r8d, [rcx+40h]
0x180005852  cmp     r8d, 7FFFFFFFh
0x180005859  jnz     short loc_180005840
0x18000585b  lea     edi, [r8-1]
0x18000585f  test    edi, edi
0x180005861  jnz     short loc_1800058A5
0x180005863  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000586a  mov     rax, [rcx]
0x18000586d  mov     rax, [rax+8]
0x180005871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005876  test    rbx, rbx
0x180005879  jz      short loc_180005892
0x18000587b  mov     rax, [rbx]
0x18000587e  mov     edx, 1
0x180005883  mov     rcx, rbx
0x180005886  mov     rax, [rax+0A8h]
0x18000588d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005892  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005899  mov     rdx, [rcx]
0x18000589c  mov     rax, [rdx+10h]
0x1800058a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058a5  mov     rbx, [rsp+28h+arg_0]
0x1800058aa  mov     eax, edi
0x1800058ac  add     rsp, 20h
0x1800058b0  pop     rdi
0x1800058b1  retn
```
