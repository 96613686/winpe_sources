# LibRaw::stread(char *,unsigned __int64,LibRaw_abstract_datastream *)

- ea: `0x180009b20`
- end: `0x180009b70`
- name: `?stread@LibRaw@@KAHPEAD_KPEAVLibRaw_abstract_datastream@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(char *, unsigned __int64, struct LibRaw_abstract_datastream *)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x180060640`
- `0x180061a90`
- `0x180062810`
- `0x180065900`
- `0x18006c0e0`
- `0x180076530`
- `0x180077760`
- `0x180082210`
- `0x180082a00`
- `0x180088f80`
- `0x18008c470`
- `0x18008d140`
- `0x18008ed30`
- `0x18008ffb0`
- `0x1800906a0`
- `0x180090ec0`
- `0x180090f80`
- `0x1800922a0`

## callees

- `0x180009b20`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall LibRaw::stread(char *a1, __int64 a2, struct LibRaw_abstract_datastream *a3)
{
  __int64 result; // rax

  if ( !a2 )
    return 0;
  result = (*(__int64 (__fastcall **)(struct LibRaw_abstract_datastream *, char *, __int64, __int64))(*(_QWORD *)a3 + 16LL))(
             a3,
             a1,
             a2,
             1);
  a1[a2 - 1] = 0;
  return result;
}

```

## disassembly

```asm
0x180009b20  mov     [rsp+arg_0], rbx
0x180009b25  push    rdi
0x180009b26  sub     rsp, 30h
0x180009b2a  mov     r10, r8
0x180009b2d  mov     rbx, rdx
0x180009b30  mov     rdi, rcx
0x180009b33  test    rdx, rdx
0x180009b36  jz      short loc_180009B63
0x180009b38  mov     rax, [r8]
0x180009b3b  mov     r9d, 1
0x180009b41  mov     r8, rdx
0x180009b44  mov     rdx, rcx
0x180009b47  mov     rcx, r10
0x180009b4a  mov     rax, [rax+10h]
0x180009b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b53  mov     byte ptr [rdi+rbx-1], 0
0x180009b58  mov     rbx, [rsp+38h+arg_0]
0x180009b5d  add     rsp, 30h
0x180009b61  pop     rdi
0x180009b62  retn
0x180009b63  mov     rbx, [rsp+38h+arg_0]
0x180009b68  xor     eax, eax
0x180009b6a  add     rsp, 30h
0x180009b6e  pop     rdi
0x180009b6f  retn
```
