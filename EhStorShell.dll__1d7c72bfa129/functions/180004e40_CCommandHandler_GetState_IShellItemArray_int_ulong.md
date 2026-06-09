# CCommandHandler::GetState(IShellItemArray *,int,ulong *)

- ea: `0x180004e40`
- end: `0x180004e9a`
- name: `?GetState@CCommandHandler@@UEAAJPEAUIShellItemArray@@HPEAK@Z`
- size: `90`
- prototype: `__int64 __fastcall(CCommandHandler *this, struct IShellItemArray *, __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004e40`
- `0x18000adb4`

## pseudocode

```c
__int64 __fastcall CCommandHandler::GetState(
        CCommandHandler *this,
        struct IShellItemArray *a2,
        __int64 a3,
        unsigned int *a4)
{
  __int64 result; // rax
  bool v7; // zf

  result = 0;
  *a4 = 3;
  if ( *((_QWORD *)this + 5)
    || (result = CCommandHandler::InitializeFromShellItem(
                   (CCommandHandler *)((char *)this - 16),
                   *((struct IShellItem **)this + 4)),
        (int)result >= 0) )
  {
    if ( *((_DWORD *)this + 16) == 1 )
    {
      v7 = *((_BYTE *)this + 48) == 1;
    }
    else
    {
      if ( *((_DWORD *)this + 16) != 2 )
        return result;
      v7 = *((_BYTE *)this + 48) == 0;
    }
    if ( v7 )
      *a4 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004e40  mov     [rsp+arg_0], rbx
0x180004e45  push    rdi
0x180004e46  sub     rsp, 20h
0x180004e4a  xor     eax, eax
0x180004e4c  mov     dword ptr [r9], 3
0x180004e53  mov     rdi, r9
0x180004e56  mov     rbx, rcx
0x180004e59  cmp     [rcx+28h], rax
0x180004e5d  jnz     short loc_180004E70
0x180004e5f  mov     rdx, [rcx+20h]; struct IShellItem *
0x180004e63  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x180004e67  call    ?InitializeFromShellItem@CCommandHandler@@AEAAJPEAUIShellItem@@@Z; CCommandHandler::InitializeFromShellItem(IShellItem *)
0x180004e6c  test    eax, eax
0x180004e6e  js      short loc_180004E8F
0x180004e70  mov     edx, [rbx+40h]
0x180004e73  sub     edx, 1
0x180004e76  jz      short loc_180004E83
0x180004e78  cmp     edx, 1
0x180004e7b  jnz     short loc_180004E8F
0x180004e7d  cmp     byte ptr [rbx+30h], 0
0x180004e81  jmp     short loc_180004E87
0x180004e83  cmp     byte ptr [rbx+30h], 1
0x180004e87  jnz     short loc_180004E8F
0x180004e89  mov     dword ptr [rdi], 0
0x180004e8f  mov     rbx, [rsp+28h+arg_0]
0x180004e94  add     rsp, 20h
0x180004e98  pop     rdi
0x180004e99  retn
```
