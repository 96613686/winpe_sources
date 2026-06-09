# Microsoft::Windows::Performance::CEventTraceExtenderBase::OnComplete(long)

- ea: `0x180003330`
- end: `0x18000339f`
- name: `?OnComplete@CEventTraceExtenderBase@Performance@Windows@Microsoft@@UEAAJJ@Z`
- size: `111`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceExtenderBase *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003330`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceExtenderBase::OnComplete(
        Microsoft::Windows::Performance::CEventTraceExtenderBase *this,
        unsigned int a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    a2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 104LL))(v4);
    v5 = *((_QWORD *)this + 1);
    if ( v5 )
    {
      *((_QWORD *)this + 1) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  v6 = *((_QWORD *)this + 2);
  if ( v6 )
  {
    *((_QWORD *)this + 2) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return a2;
}

```

## disassembly

```asm
0x180003330  mov     [rsp+arg_0], rbx
0x180003335  push    rdi
0x180003336  sub     rsp, 20h
0x18000333a  mov     edi, edx
0x18000333c  mov     rbx, rcx
0x18000333f  mov     rcx, [rcx+8]
0x180003343  test    rcx, rcx
0x180003346  jz      short loc_180003374
0x180003348  mov     rax, [rcx]
0x18000334b  mov     rax, [rax+68h]
0x18000334f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003354  mov     edi, eax
0x180003356  mov     rcx, [rbx+8]
0x18000335a  test    rcx, rcx
0x18000335d  jz      short loc_180003374
0x18000335f  mov     qword ptr [rbx+8], 0
0x180003367  mov     rax, [rcx]
0x18000336a  mov     rax, [rax+10h]
0x18000336e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003373  nop
0x180003374  mov     rcx, [rbx+10h]
0x180003378  test    rcx, rcx
0x18000337b  jz      short loc_180003392
0x18000337d  mov     qword ptr [rbx+10h], 0
0x180003385  mov     rax, [rcx]
0x180003388  mov     rax, [rax+10h]
0x18000338c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003391  nop
0x180003392  mov     eax, edi
0x180003394  mov     rbx, [rsp+28h+arg_0]
0x180003399  add     rsp, 20h
0x18000339d  pop     rdi
0x18000339e  retn
```
