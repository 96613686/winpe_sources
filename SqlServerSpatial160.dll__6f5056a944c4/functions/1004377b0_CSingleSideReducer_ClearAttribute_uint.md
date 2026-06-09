# CSingleSideReducer::ClearAttribute(uint)

- ea: `0x1004377b0`
- end: `0x1004377fb`
- name: `?ClearAttribute@CSingleSideReducer@@UEAAJI@Z`
- size: `75`
- prototype: `__int64 __fastcall(CSingleSideReducer *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1004377b0`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::ClearAttribute(CSingleSideReducer *this, unsigned int a2)
{
  __int64 result; // rax

  result = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 6) + 16LL))((char *)this + 48);
  if ( (int)result < 0 || a2 == 4 )
  {
    _mm_lfence();
  }
  else
  {
    _mm_lfence();
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 16LL))(*((_QWORD *)this + 5), a2);
  }
  return result;
}

```

## disassembly

```asm
0x1004377b0  mov     [rsp+arg_0], rbx
0x1004377b5  push    rdi
0x1004377b6  sub     rsp, 20h
0x1004377ba  mov     rax, [rcx+30h]
0x1004377be  mov     rdi, rcx
0x1004377c1  add     rcx, 30h ; '0'
0x1004377c5  mov     ebx, edx
0x1004377c7  call    qword ptr [rax+10h]
0x1004377ca  test    eax, eax
0x1004377cc  js      short loc_1004377ED
0x1004377ce  cmp     ebx, 4
0x1004377d1  jz      short loc_1004377ED
0x1004377d3  lfence
0x1004377d6  mov     rcx, [rdi+28h]
0x1004377da  mov     edx, ebx
0x1004377dc  mov     rax, [rcx]
0x1004377df  mov     rbx, [rsp+28h+arg_0]
0x1004377e4  add     rsp, 20h
0x1004377e8  pop     rdi
0x1004377e9  jmp     qword ptr [rax+10h]
0x1004377ed  lfence
0x1004377f0  mov     rbx, [rsp+28h+arg_0]
0x1004377f5  add     rsp, 20h
0x1004377f9  pop     rdi
0x1004377fa  retn
```
