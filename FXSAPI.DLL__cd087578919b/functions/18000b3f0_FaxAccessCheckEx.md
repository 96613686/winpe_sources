# FaxAccessCheckEx

- ea: `0x18000b3f0`
- end: `0x18000b46a`
- name: `FaxAccessCheckEx`
- size: `122`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000b250`

## callees

- `0x18000abe4`
- `0x18000af98`
- `0x18000b3f0`

## pseudocode

```c
__int64 __fastcall FaxAccessCheckEx(_DWORD *a1, int a2, unsigned int *a3)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  return FaxAccessCheckExInternal(a1, a2, a3, 0x20000u, 0xF30E07FF);
}

```

## disassembly

```asm
0x18000b3f0  mov     [rsp+arg_0], rbx
0x18000b3f5  mov     [rsp+arg_8], rsi
0x18000b3fa  push    rdi
0x18000b3fb  sub     rsp, 30h
0x18000b3ff  mov     rbx, r8
0x18000b402  mov     edi, edx
0x18000b404  mov     rsi, rcx
0x18000b407  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b40e  lea     rax, WPP_GLOBAL_Control
0x18000b415  cmp     rcx, rax
0x18000b418  jz      short loc_18000B43E
0x18000b41a  test    dword ptr [rcx+1Ch], 1000h
0x18000b421  jz      short loc_18000B43E
0x18000b423  cmp     byte ptr [rcx+19h], 5
0x18000b427  jb      short loc_18000B43E
0x18000b429  mov     rcx, [rcx+10h]
0x18000b42d  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000b434  mov     edx, 61h ; 'a'
0x18000b439  call    WPP_SF_
0x18000b43e  mov     r9d, 20000h; unsigned int
0x18000b444  mov     [rsp+38h+var_18], 0F30E07FFh; unsigned int
0x18000b44c  mov     r8, rbx; unsigned int *
0x18000b44f  mov     edx, edi; unsigned int
0x18000b451  mov     rcx, rsi; void *
0x18000b454  call    ?FaxAccessCheckExInternal@@YAHPEAXKPEAKKK@Z; FaxAccessCheckExInternal(void *,ulong,ulong *,ulong,ulong)
0x18000b459  mov     rbx, [rsp+38h+arg_0]
0x18000b45e  mov     rsi, [rsp+38h+arg_8]
0x18000b463  add     rsp, 30h
0x18000b467  pop     rdi
0x18000b468  retn
```
