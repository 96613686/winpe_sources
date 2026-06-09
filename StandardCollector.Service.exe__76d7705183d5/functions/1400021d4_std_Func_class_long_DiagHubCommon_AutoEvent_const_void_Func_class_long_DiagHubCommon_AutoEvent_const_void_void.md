# std::_Func_class<long,DiagHubCommon::AutoEvent const &,void *>::~_Func_class<long,DiagHubCommon::AutoEvent const &,void *>(void)

- ea: `0x1400021d4`
- end: `0x140002207`
- name: `??1?$_Func_class@JAEBVAutoEvent@DiagHubCommon@@PEAX@std@@QEAA@XZ`
- size: `51`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140014f42`
- `0x140014f8a`
- `0x140015164`
- `0x140015170`

## callees

- `0x1400021d4`
- `0x140014c70`

## pseudocode

```c
__int64 __fastcall std::_Func_class<long,DiagHubCommon::AutoEvent const &,void *>::~_Func_class<long,DiagHubCommon::AutoEvent const &,void *>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 result; // rax

  v3 = *(_QWORD *)(a1 + 56);
  if ( v3 )
  {
    LOBYTE(a2) = v3 != a1;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, a2);
    *(_QWORD *)(a1 + 56) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400021d4  push    rbx
0x1400021d6  sub     rsp, 20h
0x1400021da  mov     rbx, rcx
0x1400021dd  mov     rcx, [rcx+38h]
0x1400021e1  test    rcx, rcx
0x1400021e4  jz      short loc_140002201
0x1400021e6  mov     rax, [rcx]
0x1400021e9  cmp     rcx, rbx
0x1400021ec  setnz   dl
0x1400021ef  mov     rax, [rax+20h]
0x1400021f3  call    cs:__guard_dispatch_icall_fptr
0x1400021f9  mov     qword ptr [rbx+38h], 0
0x140002201  add     rsp, 20h
0x140002205  pop     rbx
0x140002206  retn
```
