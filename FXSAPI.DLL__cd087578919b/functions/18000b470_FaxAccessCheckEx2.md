# FaxAccessCheckEx2

- ea: `0x18000b470`
- end: `0x18000b4ea`
- name: `FaxAccessCheckEx2`
- size: `122`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18000abe4`
- `0x18000af98`
- `0x18000b470`

## pseudocode

```c
__int64 __fastcall FaxAccessCheckEx2(_DWORD *a1, int a2, unsigned int *a3)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  return FaxAccessCheckExInternal(a1, a2, a3, 0x30000u, 0xF30E03FF);
}

```

## disassembly

```asm
0x18000b470  mov     [rsp+arg_0], rbx
0x18000b475  mov     [rsp+arg_8], rsi
0x18000b47a  push    rdi
0x18000b47b  sub     rsp, 30h
0x18000b47f  mov     rbx, r8
0x18000b482  mov     edi, edx
0x18000b484  mov     rsi, rcx
0x18000b487  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b48e  lea     rax, WPP_GLOBAL_Control
0x18000b495  cmp     rcx, rax
0x18000b498  jz      short loc_18000B4BE
0x18000b49a  test    dword ptr [rcx+1Ch], 1000h
0x18000b4a1  jz      short loc_18000B4BE
0x18000b4a3  cmp     byte ptr [rcx+19h], 5
0x18000b4a7  jb      short loc_18000B4BE
0x18000b4a9  mov     rcx, [rcx+10h]
0x18000b4ad  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000b4b4  mov     edx, 62h ; 'b'
0x18000b4b9  call    WPP_SF_
0x18000b4be  mov     r9d, 30000h; unsigned int
0x18000b4c4  mov     [rsp+38h+var_18], 0F30E03FFh; unsigned int
0x18000b4cc  mov     r8, rbx; unsigned int *
0x18000b4cf  mov     edx, edi; unsigned int
0x18000b4d1  mov     rcx, rsi; void *
0x18000b4d4  call    ?FaxAccessCheckExInternal@@YAHPEAXKPEAKKK@Z; FaxAccessCheckExInternal(void *,ulong,ulong *,ulong,ulong)
0x18000b4d9  mov     rbx, [rsp+38h+arg_0]
0x18000b4de  mov     rsi, [rsp+38h+arg_8]
0x18000b4e3  add     rsp, 30h
0x18000b4e7  pop     rdi
0x18000b4e8  retn
```
