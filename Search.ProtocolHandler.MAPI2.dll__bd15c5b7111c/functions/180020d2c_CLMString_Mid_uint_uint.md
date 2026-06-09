# CLMString::Mid(uint,uint)

- ea: `0x180020d2c`
- end: `0x180020d7c`
- name: `?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a0d0`
- `0x18001afa8`
- `0x180026f00`
- `0x1800282e8`
- `0x18002a560`

## callees

- `0x180020d2c`
- `0x180021b04`
- `0x180022670`

## string_xrefs

- `0x180020d51`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
__int64 __fastcall CLMString::Mid(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  unsigned __int64 v4; // r11
  __int64 result; // rax
  unsigned int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = a3 + (unsigned __int64)a4;
  if ( v4 < a3 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
  if ( v4 > *(unsigned int *)(a1 + 20) )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x40C,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
      (const char *)0xCE,
      v6);
  *(_DWORD *)a2 = a3;
  result = a2;
  *(_DWORD *)(a2 + 4) = a4;
  *(_QWORD *)(a2 + 8) = a1;
  return result;
}

```

## disassembly

```asm
0x180020d2c  sub     rsp, 28h
0x180020d30  mov     r10d, r8d
0x180020d33  mov     r11d, r9d
0x180020d36  add     r11, r10
0x180020d39  cmp     r11, r10
0x180020d3c  jnb     short loc_180020D44
0x180020d3e  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180020d44  mov     eax, [rcx+14h]
0x180020d47  cmp     r11, rax
0x180020d4a  jbe     short loc_180020D69
0x180020d4c  mov     rcx, [rsp+28h]; this
0x180020d51  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180020d58  mov     r9d, 0CEh; char *
0x180020d5e  mov     edx, 40Ch; void *
0x180020d63  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180020d69  mov     [rdx], r8d
0x180020d6c  mov     rax, rdx
0x180020d6f  mov     [rdx+4], r9d
0x180020d73  mov     [rdx+8], rcx
0x180020d77  add     rsp, 28h
0x180020d7b  retn
```
