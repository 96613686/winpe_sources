# CommonUtil::CRefObjectFor<CommonUtil::IEnumFiles>::Release(void)

- ea: `0x140012030`
- end: `0x14001206d`
- name: `?Release@?$CRefObjectFor@UIEnumFiles@CommonUtil@@@CommonUtil@@UEBAJXZ`
- size: `61`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140012030`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall CommonUtil::CRefObjectFor<CommonUtil::IEnumFiles>::Release(volatile signed __int32 *a1)
{
  signed __int32 v1; // eax
  bool v2; // cc
  __int64 result; // rax

  if ( *((_DWORD *)a1 + 2) == 1 )
  {
    *((_DWORD *)a1 + 2) = 0;
  }
  else
  {
    v1 = _InterlockedExchangeAdd(a1 + 2, 0xFFFFFFFF);
    v2 = v1 <= 1;
    result = (unsigned int)(v1 - 1);
    if ( !v2 )
      return result;
  }
  if ( a1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x140012030  sub     rsp, 28h
0x140012034  mov     eax, [rcx+8]
0x140012037  mov     edx, 1
0x14001203c  cmp     eax, edx
0x14001203e  jnz     short loc_140012049
0x140012040  mov     dword ptr [rcx+8], 0
0x140012047  jmp     short loc_140012055
0x140012049  or      eax, 0FFFFFFFFh
0x14001204c  lock xadd [rcx+8], eax
0x140012051  sub     eax, edx
0x140012053  jg      short loc_140012068
0x140012055  test    rcx, rcx
0x140012058  jz      short loc_140012066
0x14001205a  mov     rax, [rcx]
0x14001205d  mov     rax, [rax+10h]
0x140012061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012066  xor     eax, eax
0x140012068  add     rsp, 28h
0x14001206c  retn
```
