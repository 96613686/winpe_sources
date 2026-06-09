# SBC::ConfigDecode(SBC_CONFIG const &)

- ea: `0x140017fe8`
- end: `0x14001808b`
- name: `?ConfigDecode@SBC@@QEAAJAEBUSBC_CONFIG@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(SBC *__hidden this, const struct SBC_CONFIG *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400186b0`

## callees

- `0x140017f88`
- `0x140017fe8`
- `0x140018634`
- `0x14001b2c0`

## pseudocode

```c
__int64 __fastcall SBC::ConfigDecode(SBC *this, const struct SBC_CONFIG *a2)
{
  unsigned int v4; // r11d

  memset((char *)this + 4136, 0, 0x500u);
  *((_QWORD *)this + 8) = 0;
  if ( SBC::IsConfigValid(a2) )
  {
    *((_DWORD *)this + 1) = *(_DWORD *)a2;
    *((_DWORD *)this + 6) = *((_DWORD *)a2 + 1);
    *((_DWORD *)this + 2) = *((_DWORD *)a2 + 3);
    *((_DWORD *)this + 3) = *((_DWORD *)a2 + 5);
    *((_DWORD *)this + 7) = *((_DWORD *)a2 + 2);
    *((_DWORD *)this + 8) = *((_DWORD *)a2 + 6);
    *((_DWORD *)this + 5) = (*((_DWORD *)a2 + 3) != 0) + 1;
    *(_DWORD *)this = *((_BYTE *)a2 + 28) != 0 ? 173 : 156;
    *((_DWORD *)this + 16) = SBC::SbcControl::CalculateSbcFrameLength(this);
    *((_DWORD *)this + 17) = 512;
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v4;
}

```

## disassembly

```asm
0x140017fe8  mov     [rsp+arg_0], rbx
0x140017fed  push    rdi
0x140017fee  sub     rsp, 20h
0x140017ff2  mov     rdi, rdx
0x140017ff5  mov     rbx, rcx
0x140017ff8  add     rcx, 1028h; void *
0x140017fff  xor     edx, edx; Val
0x140018001  mov     r8d, 500h; Size
0x140018007  call    memset
0x14001800c  xor     r11d, r11d
0x14001800f  mov     rcx, rdi; struct SBC_CONFIG *
0x140018012  mov     [rbx+40h], r11
0x140018016  call    ?IsConfigValid@SBC@@SA_NAEBUSBC_CONFIG@@@Z; SBC::IsConfigValid(SBC_CONFIG const &)
0x14001801b  test    al, al
0x14001801d  jnz     short loc_140018027
0x14001801f  mov     r11d, 0C000000Dh
0x140018025  jmp     short loc_14001807C
0x140018027  mov     eax, [rdi]
0x140018029  mov     [rbx+4], eax
0x14001802c  mov     eax, [rdi+4]
0x14001802f  mov     [rbx+18h], eax
0x140018032  mov     eax, [rdi+0Ch]
0x140018035  mov     [rbx+8], eax
0x140018038  mov     eax, [rdi+14h]
0x14001803b  mov     [rbx+0Ch], eax
0x14001803e  mov     eax, [rdi+8]
0x140018041  mov     [rbx+1Ch], eax
0x140018044  mov     eax, [rdi+18h]
0x140018047  mov     [rbx+20h], eax
0x14001804a  mov     eax, [rdi+0Ch]
0x14001804d  neg     eax
0x14001804f  sbb     ecx, ecx
0x140018051  neg     ecx
0x140018053  inc     ecx
0x140018055  mov     [rbx+14h], ecx
0x140018058  mov     cl, [rdi+1Ch]
0x14001805b  neg     cl
0x14001805d  mov     rcx, rbx; this
0x140018060  sbb     edx, edx
0x140018062  and     edx, 11h
0x140018065  add     edx, 9Ch
0x14001806b  mov     [rbx], edx
0x14001806d  call    ?CalculateSbcFrameLength@SbcControl@SBC@@QEBAHXZ; SBC::SbcControl::CalculateSbcFrameLength(void)
0x140018072  mov     [rbx+40h], eax
0x140018075  mov     dword ptr [rbx+44h], 200h
0x14001807c  mov     rbx, [rsp+28h+arg_0]
0x140018081  mov     eax, r11d
0x140018084  add     rsp, 20h
0x140018088  pop     rdi
0x140018089  retn
```
