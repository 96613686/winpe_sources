# sub_18001FFFC

- ea: `0x18001fffc`
- end: `0x1800200af`
- name: `sub_18001FFFC`
- size: `179`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d64c`
- `0x18001d79c`
- `0x18001d91c`
- `0x18001f9c8`
- `0x18001fa58`
- `0x18001fae8`
- `0x18001fb78`
- `0x180030e2c`
- `0x1800317f0`
- `0x180031880`
- `0x1800321e0`
- `0x180032404`
- `0x18003b3a4`
- `0x18003b904`
- `0x18003c448`
- `0x18003c57c`
- `0x18004a794`
- `0x18004a8c8`

## callees

- `0x18001fffc`
- `0x180031f5c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002003d`
- `KERNEL32!GetCurrentThreadId` at `0x18002004e`
- `KERNEL32!GetCurrentThreadId` at `0x18002003d`
- `KERNEL32!GetCurrentThreadId` at `0x18002004e`

## pseudocode

```c
__int64 __fastcall sub_18001FFFC(__int64 a1)
{
  volatile signed __int32 *v2; // rbx
  signed __int32 v3; // edx
  DWORD v4; // eax
  signed __int32 v5; // edx
  signed __int32 v6; // r9d

  if ( !*(_BYTE *)a1 )
  {
    v2 = *(volatile signed __int32 **)(a1 + 8);
    *(_BYTE *)a1 = 1;
    if ( !*((_DWORD *)v2 + 1) && !(unsigned __int16)*v2 )
    {
      v3 = *v2;
      if ( v3 == _InterlockedCompareExchange(v2, (v3 + 0x10000) | 0xFFFF, v3) )
      {
        v4 = GetCurrentThreadId() & 0xFFFFFFFC | 1;
LABEL_6:
        _InterlockedExchange(v2 + 1, v4);
        return a1;
      }
    }
    if ( ((GetCurrentThreadId() ^ *((_DWORD *)v2 + 1)) & 0xFFFFFFFC) == 0 )
    {
      v4 = *((_DWORD *)v2 + 1) + 1;
      goto LABEL_6;
    }
    v5 = *v2;
    if ( v5 != _InterlockedCompareExchange(v2, v5 + 0x10000, v5) )
    {
      _m_prefetchw((const void *)v2);
      do
        v6 = *v2;
      while ( v6 != _InterlockedCompareExchange(v2, v6 + 0x10000, v6) );
    }
    sub_180031F5C(v2, 1);
  }
  return a1;
}

```

## disassembly

```asm
0x18001fffc  mov     [rsp+arg_0], rbx
0x180020001  push    rdi
0x180020002  sub     rsp, 20h
0x180020006  cmp     byte ptr [rcx], 0
0x180020009  mov     rdi, rcx
0x18002000c  jnz     loc_1800200A1
0x180020012  mov     rbx, [rcx+8]
0x180020016  mov     byte ptr [rcx], 1
0x180020019  mov     eax, [rbx+4]
0x18002001c  test    eax, eax
0x18002001e  jnz     short loc_18002004E
0x180020020  mov     edx, [rbx]
0x180020022  test    dx, dx
0x180020025  jnz     short loc_18002004E
0x180020027  lea     ecx, [rdx+10000h]
0x18002002d  mov     eax, edx
0x18002002f  or      ecx, 0FFFFh
0x180020035  lock cmpxchg [rbx], ecx
0x180020039  cmp     edx, eax
0x18002003b  jnz     short loc_18002004E
0x18002003d  call    cs:GetCurrentThreadId
0x180020043  and     eax, 0FFFFFFFDh
0x180020046  or      eax, 1
0x180020049  xchg    eax, [rbx+4]
0x18002004c  jmp     short loc_1800200A1
0x18002004e  call    cs:GetCurrentThreadId
0x180020054  mov     ecx, [rbx+4]
0x180020057  xor     ecx, eax
0x180020059  test    ecx, 0FFFFFFFCh
0x18002005f  jnz     short loc_180020068
0x180020061  mov     eax, [rbx+4]
0x180020064  inc     eax
0x180020066  jmp     short loc_180020049
0x180020068  mov     edx, [rbx]
0x18002006a  mov     eax, edx
0x18002006c  lea     ecx, [rdx+10000h]
0x180020072  lock cmpxchg [rbx], ecx
0x180020076  cmp     edx, eax
0x180020078  jz      short loc_180020094
0x18002007a  prefetchw byte ptr [rbx]
0x18002007d  mov     r9d, [rbx]
0x180020080  mov     eax, r9d
0x180020083  lea     r8d, [r9+10000h]
0x18002008a  lock cmpxchg [rbx], r8d
0x18002008f  cmp     r9d, eax
0x180020092  jnz     short loc_18002007D
0x180020094  mov     edx, 1
0x180020099  mov     rcx, rbx
0x18002009c  call    sub_180031F5C
0x1800200a1  mov     rax, rdi
0x1800200a4  mov     rbx, [rsp+28h+arg_0]
0x1800200a9  add     rsp, 20h
0x1800200ad  pop     rdi
0x1800200ae  retn
```
