# CACMCmpStream::ReadFormat(long,void *,long *)

- ea: `0x180015cc0`
- end: `0x180015d29`
- name: `?ReadFormat@CACMCmpStream@@UEAAJJPEAXPEAJ@Z`
- size: `105`
- prototype: `int(CACMCmpStream *__hidden this, int, void *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180015cc0`
- `0x180015e7c`
- `0x180017365`

## pseudocode

```c
__int64 __fastcall CACMCmpStream::ReadFormat(CACMCmpStream *this, __int64 a2, void *a3, int *a4)
{
  __int64 result; // rax
  int v8; // eax

  if ( *((_QWORD *)this + 29) || (result = CACMCmpStream::SetUpCompression(this), !(_DWORD)result) )
  {
    if ( a3 )
    {
      v8 = *a4;
      if ( *a4 >= *((_DWORD *)this + 66) )
        v8 = *((_DWORD *)this + 66);
      memmove_0(a3, *((const void **)this + 32), v8);
    }
    *a4 = *((_DWORD *)this + 66);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180015cc0  mov     [rsp+arg_0], rbx
0x180015cc5  mov     [rsp+arg_8], rsi
0x180015cca  push    rdi
0x180015ccb  sub     rsp, 20h
0x180015ccf  cmp     qword ptr [rcx+0E8h], 0
0x180015cd7  mov     rdi, r9
0x180015cda  mov     rsi, r8
0x180015cdd  mov     rbx, rcx
0x180015ce0  jnz     short loc_180015CEB
0x180015ce2  call    ?SetUpCompression@CACMCmpStream@@QEAAJXZ; CACMCmpStream::SetUpCompression(void)
0x180015ce7  test    eax, eax
0x180015ce9  jnz     short loc_180015D19
0x180015ceb  test    rsi, rsi
0x180015cee  jz      short loc_180015D0F
0x180015cf0  mov     ecx, [rbx+108h]
0x180015cf6  mov     eax, [rdi]
0x180015cf8  cmp     eax, ecx
0x180015cfa  mov     rdx, [rbx+100h]; Src
0x180015d01  cmovge  eax, ecx
0x180015d04  mov     rcx, rsi; void *
0x180015d07  movsxd  r8, eax; Size
0x180015d0a  call    memmove_0
0x180015d0f  mov     eax, [rbx+108h]
0x180015d15  mov     [rdi], eax
0x180015d17  xor     eax, eax
0x180015d19  mov     rbx, [rsp+28h+arg_0]
0x180015d1e  mov     rsi, [rsp+28h+arg_8]
0x180015d23  add     rsp, 20h
0x180015d27  pop     rdi
0x180015d28  retn
```
