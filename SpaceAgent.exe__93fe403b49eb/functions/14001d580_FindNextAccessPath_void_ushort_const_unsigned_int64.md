# FindNextAccessPath(void *,ushort const * *,unsigned __int64 *)

- ea: `0x14001d580`
- end: `0x14001d639`
- name: `?FindNextAccessPath@@YAHPEAXPEAPEBGPEA_K@Z`
- size: `185`
- prototype: `__int64 __fastcall(unsigned __int64 *, const unsigned __int16 **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001cde8`
- `0x14001d420`

## callees

- `0x1400027fc`
- `0x14001d580`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14001d5d7`
- `KERNEL32!SetLastError` at `0x14001d5f3`
- `KERNEL32!SetLastError` at `0x14001d5d7`
- `KERNEL32!SetLastError` at `0x14001d5f3`

## pseudocode

```c
__int64 __fastcall FindNextAccessPath(unsigned __int64 *a1, const unsigned __int16 **a2, unsigned __int64 *a3)
{
  unsigned __int64 v3; // r11
  const unsigned __int16 *v5; // r15
  const unsigned __int16 *v8; // rbp
  int v9; // eax
  __int64 v10; // r11
  DWORD v11; // ecx
  unsigned int v12; // edi
  unsigned __int64 v13; // rbx
  unsigned __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  v3 = *a1;
  v5 = (const unsigned __int16 *)a1[1];
  v15 = 0;
  v8 = 0;
  v9 = StringCchLengthW(v5, v3, &v15);
  v11 = v9;
  if ( v9 >= 0 )
  {
    v13 = v15;
    if ( v15 )
    {
      v12 = 1;
      v8 = v5;
      v13 = v15 + 1;
      *a1 = v10 - (v15 + 1);
      a1[1] = (unsigned __int64)&v5[v13];
    }
    else
    {
      v12 = 0;
      SetLastError(0x12u);
    }
  }
  else
  {
    v12 = 0;
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      v11 = (unsigned __int16)v9;
    SetLastError(v11);
    v13 = v15;
  }
  *a2 = v8;
  if ( a3 )
    *a3 = v13;
  return v12;
}

```

## disassembly

```asm
0x14001d580  mov     rax, rsp
0x14001d583  mov     [rax+10h], rbx
0x14001d587  mov     [rax+18h], rbp
0x14001d58b  push    rsi
0x14001d58c  push    rdi
0x14001d58d  push    r12
0x14001d58f  push    r14
0x14001d591  push    r15
0x14001d593  sub     rsp, 20h
0x14001d597  mov     r11, [rcx]
0x14001d59a  mov     r12, rdx
0x14001d59d  mov     r15, [rcx+8]
0x14001d5a1  mov     r14, rcx
0x14001d5a4  mov     rsi, r8
0x14001d5a7  mov     qword ptr [rax+8], 0
0x14001d5af  mov     rdx, r11; unsigned __int64
0x14001d5b2  lea     r8, [rax+8]; unsigned __int64 *
0x14001d5b6  mov     rcx, r15; unsigned __int16 *
0x14001d5b9  xor     ebp, ebp
0x14001d5bb  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001d5c0  mov     ecx, eax
0x14001d5c2  test    eax, eax
0x14001d5c4  jns     short loc_14001D5E4
0x14001d5c6  xor     edi, edi
0x14001d5c8  and     eax, 1FFF0000h
0x14001d5cd  cmp     eax, 70000h
0x14001d5d2  jnz     short loc_14001D5D7
0x14001d5d4  movzx   ecx, cx; dwErrCode
0x14001d5d7  call    cs:__imp_SetLastError
0x14001d5dd  mov     rbx, [rsp+48h+arg_0]
0x14001d5e2  jmp     short loc_14001D614
0x14001d5e4  mov     rbx, [rsp+48h+arg_0]
0x14001d5e9  test    rbx, rbx
0x14001d5ec  jnz     short loc_14001D5FB
0x14001d5ee  xor     edi, edi
0x14001d5f0  lea     ecx, [rbx+12h]; dwErrCode
0x14001d5f3  call    cs:__imp_SetLastError
0x14001d5f9  jmp     short loc_14001D614
0x14001d5fb  mov     edi, 1
0x14001d600  mov     rbp, r15
0x14001d603  add     rbx, rdi
0x14001d606  sub     r11, rbx
0x14001d609  mov     [r14], r11
0x14001d60c  lea     rcx, [r15+rbx*2]
0x14001d610  mov     [r14+8], rcx
0x14001d614  mov     [r12], rbp
0x14001d618  test    rsi, rsi
0x14001d61b  jz      short loc_14001D620
0x14001d61d  mov     [rsi], rbx
0x14001d620  mov     rbx, [rsp+48h+arg_8]
0x14001d625  mov     eax, edi
0x14001d627  mov     rbp, [rsp+48h+arg_10]
0x14001d62c  add     rsp, 20h
0x14001d630  pop     r15
0x14001d632  pop     r14
0x14001d634  pop     r12
0x14001d636  pop     rdi
0x14001d637  pop     rsi
0x14001d638  retn
```
