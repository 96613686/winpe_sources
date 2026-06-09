# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::AddRef(void)

- ea: `0x180003520`
- end: `0x180003575`
- name: `?AddRef@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UEAAKXZ`
- size: `85`
- prototype: `unsigned int __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003580`
- `0x180003590`

## callees

- `0x180003520`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::AddRef(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this)
{
  unsigned int v1; // ebx
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *((_DWORD *)this + 11);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)this + 11, v2 + 1, v2) )
    {
      v1 = v2 + 1;
      break;
    }
  }
  if ( (*((_BYTE *)this + 64) & 4) == 0 && v1 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return v1;
}

```

## disassembly

```asm
0x180003520  push    rbx
0x180003522  sub     rsp, 20h
0x180003526  mov     ebx, 7FFFFFFFh
0x18000352b  jmp     short loc_18000353B
0x18000352d  lea     edx, [r8+1]
0x180003531  mov     eax, r8d
0x180003534  lock cmpxchg [rcx+2Ch], edx
0x180003539  jz      short loc_180003546
0x18000353b  mov     r8d, [rcx+2Ch]
0x18000353f  cmp     r8d, ebx
0x180003542  jnz     short loc_18000352D
0x180003544  jmp     short loc_18000354A
0x180003546  lea     ebx, [r8+1]
0x18000354a  test    byte ptr [rcx+40h], 4
0x18000354e  jnz     short loc_18000356D
0x180003550  cmp     ebx, 2
0x180003553  jnz     short loc_18000356D
0x180003555  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000355c  test    rcx, rcx
0x18000355f  jz      short loc_18000356D
0x180003561  mov     rdx, [rcx]
0x180003564  mov     rax, [rdx+8]
0x180003568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000356d  mov     eax, ebx
0x18000356f  add     rsp, 20h
0x180003573  pop     rbx
0x180003574  retn
```
