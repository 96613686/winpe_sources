# PixLogger::FlushEventBuffer(void)

- ea: `0x18002bd40`
- end: `0x18002bdc5`
- name: `?FlushEventBuffer@PixLogger@@AEAAXXZ`
- size: `133`
- prototype: `void __fastcall(PixLogger *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002bccc`
- `0x18002bdcc`
- `0x18002c260`

## callees

- `0x18002bd40`
- `0x18004c8e0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18002bd9d`
- `ntdll!EtwEventWrite` at `0x18002bd9d`

## pseudocode

```c
void __fastcall PixLogger::FlushEventBuffer(PixLogger *this)
{
  int v2; // eax
  __int64 v3; // rcx
  __int64 v4; // [rsp+20h] [rbp-38h] BYREF
  int v5; // [rsp+28h] [rbp-30h]
  int v6; // [rsp+2Ch] [rbp-2Ch]
  __int128 v7; // [rsp+30h] [rbp-28h] BYREF

  if ( *((_QWORD *)this + 3) )
  {
    if ( *((_BYTE *)this + 48) )
    {
      v4 = *((_QWORD *)this + 2);
      v2 = *((_DWORD *)this + 6);
      v3 = *(_QWORD *)this;
      v7 = 0;
      BYTE2(v7) = 2;
      v5 = v2;
      v6 = 0;
      ((void (__fastcall *)(__int64, __int128 *, __int64, __int64 *))EtwEventWrite)(v3, &v7, 1, &v4);
    }
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x18002bd40  push    rbx
0x18002bd42  sub     rsp, 50h
0x18002bd46  mov     rax, cs:__security_cookie
0x18002bd4d  xor     rax, rsp
0x18002bd50  mov     [rsp+58h+var_18], rax
0x18002bd55  cmp     qword ptr [rcx+18h], 0
0x18002bd5a  mov     rbx, rcx
0x18002bd5d  jz      short loc_18002BDB1
0x18002bd5f  cmp     byte ptr [rcx+30h], 0
0x18002bd63  jz      short loc_18002BDA9
0x18002bd65  mov     rax, [rcx+10h]
0x18002bd69  lea     r9, [rsp+58h+var_38]
0x18002bd6e  mov     [rsp+58h+var_38], rax
0x18002bd73  lea     rdx, [rsp+58h+var_28]
0x18002bd78  mov     eax, [rcx+18h]
0x18002bd7b  xorps   xmm0, xmm0
0x18002bd7e  mov     rcx, [rcx]
0x18002bd81  mov     r8d, 1
0x18002bd87  movups  [rsp+58h+var_28], xmm0
0x18002bd8c  mov     byte ptr [rsp+58h+var_28+2], 2
0x18002bd91  mov     [rsp+58h+var_30], eax
0x18002bd95  mov     [rsp+58h+var_2C], 0
0x18002bd9d  call    cs:__imp_EtwEventWrite
0x18002bda4  nop     dword ptr [rax+rax+00h]
0x18002bda9  mov     qword ptr [rbx+18h], 0
0x18002bdb1  mov     rcx, [rsp+58h+var_18]
0x18002bdb6  xor     rcx, rsp; StackCookie
0x18002bdb9  call    __security_check_cookie
0x18002bdbe  add     rsp, 50h
0x18002bdc2  pop     rbx
0x18002bdc3  retn
```
