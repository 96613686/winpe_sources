# Windows::Internal::GitPtr::GitPtr(void)

- ea: `0x140002514`
- end: `0x1400025d6`
- name: `??0GitPtr@Internal@Windows@@QEAA@XZ`
- size: `194`
- prototype: `Windows::Internal::GitPtr *__fastcall(Windows::Internal::GitPtr *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001e98`

## callees

- `0x140002514`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000256e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000256e`

## pseudocode

```c
Windows::Internal::GitPtr *__fastcall Windows::Internal::GitPtr::GitPtr(Windows::Internal::GitPtr *this)
{
  HRESULT v2; // edi
  LPVOID v3; // rcx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable';
  if ( qword_14000C868 )
  {
    v2 = 0;
    _InterlockedIncrement((volatile signed __int32 *)&Windows::Internal::Details::_git);
  }
  else
  {
    ppv = 0;
    v2 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
    if ( v2 >= 0 )
    {
      if ( !_InterlockedCompareExchange64(&qword_14000C868, (signed __int64)ppv, 0) )
        ppv = 0;
      _InterlockedIncrement((volatile signed __int32 *)&Windows::Internal::Details::_git);
    }
    v3 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v3 + 16LL))(v3);
    }
  }
  *((_DWORD *)this + 3) = v2;
  *(_QWORD *)this = &Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable';
  return this;
}

```

## disassembly

```asm
0x140002514  mov     [rsp+arg_8], rbx
0x140002519  push    rdi
0x14000251a  sub     rsp, 30h
0x14000251e  lea     rax, ??_7?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable'
0x140002525  mov     dword ptr [rcx+8], 0
0x14000252c  mov     [rcx], rax
0x14000252f  mov     rbx, rcx
0x140002532  cmp     cs:qword_14000C868, 0
0x14000253a  jz      short loc_140002547
0x14000253c  xor     edi, edi
0x14000253e  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x140002545  jmp     short loc_1400025BB
0x140002547  xor     edx, edx; pUnkOuter
0x140002549  mov     [rsp+38h+arg_0], 0
0x140002552  lea     rax, [rsp+38h+arg_0]
0x140002557  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x14000255e  mov     [rsp+38h+ppv], rax; ppv
0x140002563  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x14000256a  lea     r8d, [rdx+1]; dwClsContext
0x14000256e  call    cs:__imp_CoCreateInstance
0x140002574  mov     edi, eax
0x140002576  test    eax, eax
0x140002578  js      short loc_14000259C
0x14000257a  mov     rcx, [rsp+38h+arg_0]
0x14000257f  xor     eax, eax
0x140002581  lock cmpxchg cs:qword_14000C868, rcx
0x14000258a  jnz     short loc_140002595
0x14000258c  mov     [rsp+38h+arg_0], 0
0x140002595  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x14000259c  mov     rcx, [rsp+38h+arg_0]
0x1400025a1  test    rcx, rcx
0x1400025a4  jz      short loc_1400025BB
0x1400025a6  mov     [rsp+38h+arg_0], 0
0x1400025af  mov     rax, [rcx]
0x1400025b2  mov     rax, [rax+10h]
0x1400025b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025bb  lea     rax, ??_7?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::`vftable'
0x1400025c2  mov     [rbx+0Ch], edi
0x1400025c5  mov     [rbx], rax
0x1400025c8  mov     rax, rbx
0x1400025cb  mov     rbx, [rsp+38h+arg_8]
0x1400025d0  add     rsp, 30h
0x1400025d4  pop     rdi
0x1400025d5  retn
```
