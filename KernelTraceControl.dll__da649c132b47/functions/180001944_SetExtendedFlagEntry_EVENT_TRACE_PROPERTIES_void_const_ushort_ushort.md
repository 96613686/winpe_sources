# SetExtendedFlagEntry(_EVENT_TRACE_PROPERTIES *,void const *,ushort,ushort)

- ea: `0x180001944`
- end: `0x180001a10`
- name: `?SetExtendedFlagEntry@@YAKPEAU_EVENT_TRACE_PROPERTIES@@PEBXGG@Z`
- size: `204`
- prototype: `__int64 __fastcall(struct _EVENT_TRACE_PROPERTIES *, const void *, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180001a10`

## callees

- `0x180001944`
- `0x1800278f0`

## pseudocode

```c
__int64 __fastcall SetExtendedFlagEntry(
        struct _EVENT_TRACE_PROPERTIES *a1,
        const void *a2,
        unsigned __int16 a3,
        unsigned __int16 a4)
{
  __int16 v4; // r11
  unsigned __int16 *v5; // r10
  unsigned __int16 *v8; // rbx
  unsigned __int16 *v9; // rcx
  __int16 v10; // dx
  unsigned __int16 v11; // di
  char *v12; // rcx

  HIBYTE(v4) = 0;
  v5 = (unsigned __int16 *)((char *)a1 + a1->Wnode.BufferSize);
  if ( (a1->EnableFlags & 0x80000000) == 0 || !LOWORD(a1->EnableFlags) )
    return 1004;
  v8 = (unsigned __int16 *)((char *)a1 + LOWORD(a1->EnableFlags));
  if ( v8 > v5 )
    return 24;
  v9 = v8 + 2;
  if ( v8 + 2 > v5 )
    return 24;
  v10 = 0;
  if ( v8[1] )
  {
    while ( *v9 )
    {
      v9 += 2 * *v9;
      if ( v9 > v5 )
        return 24;
      if ( (unsigned __int16)++v10 >= v8[1] )
        goto LABEL_11;
    }
    return 1004;
  }
LABEL_11:
  v9[1] = a4;
  LOBYTE(v4) = (a3 & 3) != 0;
  v11 = v4 + (((unsigned __int64)a3 + 4) >> 2);
  *v9 = v11;
  v12 = (char *)(v9 + 2);
  if ( v12 > (char *)v5 )
    return 24;
  memcpy_0(v12, a2, a3);
  *v8 += v11;
  ++v8[1];
  return 0;
}

```

## disassembly

```asm
0x180001944  mov     [rsp+arg_0], rbx
0x180001949  mov     [rsp+arg_8], rbp
0x18000194e  mov     [rsp+arg_10], rsi
0x180001953  push    rdi
0x180001954  sub     rsp, 20h
0x180001958  mov     r10d, [rcx]
0x18000195b  xor     r11d, r11d
0x18000195e  add     r10, rcx
0x180001961  movzx   esi, r8w
0x180001965  mov     rbp, rdx
0x180001968  cmp     [rcx+48h], r11d
0x18000196c  jl      short loc_180001978
0x18000196e  mov     eax, 3ECh
0x180001973  jmp     loc_1800019FB
0x180001978  cmp     [rcx+48h], r11w
0x18000197d  jz      short loc_18000196E
0x18000197f  movzx   ebx, word ptr [rcx+48h]
0x180001983  add     rbx, rcx
0x180001986  cmp     rbx, r10
0x180001989  jbe     short loc_180001992
0x18000198b  mov     eax, 18h
0x180001990  jmp     short loc_1800019FB
0x180001992  lea     rcx, [rbx+4]
0x180001996  cmp     rcx, r10
0x180001999  ja      short loc_18000198B
0x18000199b  movzx   edx, r11w
0x18000199f  cmp     r11w, [rbx+2]
0x1800019a4  jnb     short loc_1800019C1
0x1800019a6  cmp     [rcx], r11w
0x1800019aa  jz      short loc_18000196E
0x1800019ac  movzx   eax, word ptr [rcx]
0x1800019af  lea     rcx, [rcx+rax*4]
0x1800019b3  cmp     rcx, r10
0x1800019b6  ja      short loc_18000198B
0x1800019b8  inc     dx
0x1800019bb  cmp     dx, [rbx+2]
0x1800019bf  jb      short loc_1800019A6
0x1800019c1  movzx   r8d, si; Size
0x1800019c5  mov     [rcx+2], r9w
0x1800019ca  lea     rdi, [r8+4]
0x1800019ce  shr     rdi, 2
0x1800019d2  test    sil, 3
0x1800019d6  setnz   r11b
0x1800019da  add     di, r11w
0x1800019de  mov     [rcx], di
0x1800019e1  add     rcx, 4; void *
0x1800019e5  cmp     rcx, r10
0x1800019e8  ja      short loc_18000198B
0x1800019ea  mov     rdx, rbp; Src
0x1800019ed  call    memcpy_0
0x1800019f2  add     [rbx], di
0x1800019f5  inc     word ptr [rbx+2]
0x1800019f9  xor     eax, eax
0x1800019fb  mov     rbx, [rsp+28h+arg_0]
0x180001a00  mov     rbp, [rsp+28h+arg_8]
0x180001a05  mov     rsi, [rsp+28h+arg_10]
0x180001a0a  add     rsp, 20h
0x180001a0e  pop     rdi
0x180001a0f  retn
```
