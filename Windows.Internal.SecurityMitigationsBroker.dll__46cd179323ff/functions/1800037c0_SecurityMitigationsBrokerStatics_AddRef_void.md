# SecurityMitigationsBrokerStatics::AddRef(void)

- ea: `0x1800037c0`
- end: `0x180003815`
- name: `?AddRef@SecurityMitigationsBrokerStatics@@UEAAKXZ`
- size: `85`
- prototype: `unsigned int __fastcall(SecurityMitigationsBrokerStatics *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003820`

## callees

- `0x1800037c0`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall SecurityMitigationsBrokerStatics::AddRef(SecurityMitigationsBrokerStatics *this)
{
  unsigned int v1; // ebx
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *((_DWORD *)this + 5);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)this + 5, v2 + 1, v2) )
    {
      v1 = v2 + 1;
      break;
    }
  }
  if ( (*((_BYTE *)this + 40) & 4) == 0 && v1 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return v1;
}

```

## disassembly

```asm
0x1800037c0  push    rbx
0x1800037c2  sub     rsp, 20h
0x1800037c6  mov     ebx, 7FFFFFFFh
0x1800037cb  jmp     short loc_1800037DB
0x1800037cd  lea     edx, [r8+1]
0x1800037d1  mov     eax, r8d
0x1800037d4  lock cmpxchg [rcx+14h], edx
0x1800037d9  jz      short loc_1800037E6
0x1800037db  mov     r8d, [rcx+14h]
0x1800037df  cmp     r8d, ebx
0x1800037e2  jnz     short loc_1800037CD
0x1800037e4  jmp     short loc_1800037EA
0x1800037e6  lea     ebx, [r8+1]
0x1800037ea  test    byte ptr [rcx+28h], 4
0x1800037ee  jnz     short loc_18000380D
0x1800037f0  cmp     ebx, 2
0x1800037f3  jnz     short loc_18000380D
0x1800037f5  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800037fc  test    rcx, rcx
0x1800037ff  jz      short loc_18000380D
0x180003801  mov     rdx, [rcx]
0x180003804  mov     rax, [rdx+8]
0x180003808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000380d  mov     eax, ebx
0x18000380f  add     rsp, 20h
0x180003813  pop     rbx
0x180003814  retn
```
