# _AppPrioritizationUserSession::GetProcessNameFromProcessId_::_1_::dtor$3

- ea: `0x18000c4b9`
- end: `0x18000c4df`
- name: `_AppPrioritizationUserSession::GetProcessNameFromProcessId_::_1_::dtor$3`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x18000887c`
- `0x18000c4b9`

## pseudocode

```c
__int64 __fastcall AppPrioritizationUserSession::GetProcessNameFromProcessId_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 64) & 2;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~2u;
    return std::wstring::~wstring(a2 + 72);
  }
  return result;
}

```

## disassembly

```asm
0x18000c4b9  push    rbp
0x18000c4bb  sub     rsp, 20h
0x18000c4bf  mov     rbp, rdx
0x18000c4c2  mov     eax, [rbp+40h]
0x18000c4c5  and     eax, 2
0x18000c4c8  test    eax, eax
0x18000c4ca  jz      short loc_18000C4D9
0x18000c4cc  and     dword ptr [rbp+40h], 0FFFFFFFDh
0x18000c4d0  lea     rcx, [rbp+48h]
0x18000c4d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c4d9  add     rsp, 20h
0x18000c4dd  pop     rbp
0x18000c4de  retn
```
