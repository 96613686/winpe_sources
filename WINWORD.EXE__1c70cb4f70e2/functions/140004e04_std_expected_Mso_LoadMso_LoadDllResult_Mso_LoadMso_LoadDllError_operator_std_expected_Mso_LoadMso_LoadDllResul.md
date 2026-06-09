# std::expected<Mso::LoadMso::LoadDllResult,Mso::LoadMso::LoadDllError>::operator=(std::expected<Mso::LoadMso::LoadDllResult,Mso::LoadMso::LoadDllError> &&)

- ea: `0x140004e04`
- end: `0x140004ed8`
- name: `??4?$expected@ULoadDllResult@LoadMso@Mso@@ULoadDllError@23@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `212`
- prototype: `__int64 __fastcall(Mso::LoadMso::LoadDllError *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140004fe0`

## callees

- `0x140004c2c`
- `0x140004e04`
- `0x140004fb0`

## pseudocode

```c
Mso::LoadMso::LoadDllError *__fastcall std::expected<Mso::LoadMso::LoadDllResult,Mso::LoadMso::LoadDllError>::operator=(
        Mso::LoadMso::LoadDllError *this,
        __int64 a2)
{
  char v2; // al
  int v5; // eax

  v2 = *(_BYTE *)(a2 + 48);
  if ( !*((_BYTE *)this + 48) )
  {
    if ( v2 )
    {
      Mso::LoadMso::LoadDllError::`scalar deleting destructor'(this, a2);
      *(_OWORD *)this = *(_OWORD *)a2;
      goto LABEL_11;
    }
    if ( this != (Mso::LoadMso::LoadDllError *)a2 )
    {
      std::wstring::_Tidy_deallocate(this);
      *(_OWORD *)this = *(_OWORD *)a2;
      *((_OWORD *)this + 1) = *(_OWORD *)(a2 + 16);
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 7;
      *(_WORD *)a2 = 0;
    }
    *((_DWORD *)this + 8) = *(_DWORD *)(a2 + 32);
    *((_DWORD *)this + 9) = *(_DWORD *)(a2 + 36);
    v5 = *(_DWORD *)(a2 + 40);
LABEL_10:
    *((_DWORD *)this + 10) = v5;
    goto LABEL_11;
  }
  if ( !v2 )
  {
    *(_OWORD *)this = 0;
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
    *(_OWORD *)this = *(_OWORD *)a2;
    *((_OWORD *)this + 1) = *(_OWORD *)(a2 + 16);
    *(_WORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 7;
    *((_DWORD *)this + 8) = *(_DWORD *)(a2 + 32);
    *((_DWORD *)this + 9) = *(_DWORD *)(a2 + 36);
    v5 = *(_DWORD *)(a2 + 40);
    goto LABEL_10;
  }
  *(_OWORD *)this = *(_OWORD *)a2;
LABEL_11:
  *((_BYTE *)this + 48) = *(_BYTE *)(a2 + 48);
  return this;
}

```

## disassembly

```asm
0x140004e04  mov     [rsp+arg_0], rbx
0x140004e09  push    rdi
0x140004e0a  sub     rsp, 20h
0x140004e0e  movzx   eax, byte ptr [rdx+30h]
0x140004e12  mov     rdi, rcx
0x140004e15  movzx   ecx, byte ptr [rcx+30h]
0x140004e19  mov     rbx, rdx
0x140004e1c  test    cl, cl
0x140004e1e  jz      short loc_140004E71
0x140004e20  test    al, al
0x140004e22  jz      short loc_140004E2F
0x140004e24  movups  xmm0, xmmword ptr [rdx]
0x140004e27  movups  xmmword ptr [rdi], xmm0
0x140004e2a  jmp     loc_140004EC3
0x140004e2f  test    cl, cl
0x140004e31  jz      short loc_140004E71
0x140004e33  xor     eax, eax
0x140004e35  xorps   xmm0, xmm0
0x140004e38  movups  xmmword ptr [rdi], xmm0
0x140004e3b  mov     [rdi+10h], rax
0x140004e3f  mov     [rdi+18h], rax
0x140004e43  movups  xmm0, xmmword ptr [rdx]
0x140004e46  movups  xmmword ptr [rdi], xmm0
0x140004e49  movups  xmm1, xmmword ptr [rdx+10h]
0x140004e4d  movups  xmmword ptr [rdi+10h], xmm1
0x140004e51  mov     [rdx], ax
0x140004e54  mov     [rdx+10h], rax
0x140004e58  mov     qword ptr [rdx+18h], 7
0x140004e60  mov     eax, [rdx+20h]
0x140004e63  mov     [rdi+20h], eax
0x140004e66  mov     eax, [rdx+24h]
0x140004e69  mov     [rdi+24h], eax
0x140004e6c  mov     eax, [rdx+28h]
0x140004e6f  jmp     short loc_140004EC0
0x140004e71  test    al, al
0x140004e73  jz      short loc_140004E85
0x140004e75  mov     rcx, rdi; this
0x140004e78  call    ??_GLoadDllError@LoadMso@Mso@@QEAAPEAXI@Z; Mso::LoadMso::LoadDllError::`scalar deleting destructor'(uint)
0x140004e7d  movups  xmm0, xmmword ptr [rbx]
0x140004e80  movups  xmmword ptr [rdi], xmm0
0x140004e83  jmp     short loc_140004EC3
0x140004e85  cmp     rdi, rbx
0x140004e88  jz      short loc_140004EB1
0x140004e8a  mov     rcx, rdi
0x140004e8d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140004e92  movups  xmm0, xmmword ptr [rbx]
0x140004e95  xor     eax, eax
0x140004e97  movups  xmmword ptr [rdi], xmm0
0x140004e9a  movups  xmm1, xmmword ptr [rbx+10h]
0x140004e9e  movups  xmmword ptr [rdi+10h], xmm1
0x140004ea2  mov     [rbx+10h], rax
0x140004ea6  mov     qword ptr [rbx+18h], 7
0x140004eae  mov     [rbx], ax
0x140004eb1  mov     eax, [rbx+20h]
0x140004eb4  mov     [rdi+20h], eax
0x140004eb7  mov     eax, [rbx+24h]
0x140004eba  mov     [rdi+24h], eax
0x140004ebd  mov     eax, [rbx+28h]
0x140004ec0  mov     [rdi+28h], eax
0x140004ec3  movzx   eax, byte ptr [rbx+30h]
0x140004ec7  mov     rbx, [rsp+28h+arg_0]
0x140004ecc  mov     [rdi+30h], al
0x140004ecf  mov     rax, rdi
0x140004ed2  add     rsp, 20h
0x140004ed6  pop     rdi
0x140004ed7  retn
```
