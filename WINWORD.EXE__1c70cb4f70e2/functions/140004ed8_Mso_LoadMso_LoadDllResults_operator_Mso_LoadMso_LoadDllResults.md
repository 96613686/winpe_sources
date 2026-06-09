# Mso::LoadMso::LoadDllResults::operator=(Mso::LoadMso::LoadDllResults &&)

- ea: `0x140004ed8`
- end: `0x140004fac`
- name: `??4LoadDllResults@LoadMso@Mso@@QEAAAEAU012@$$QEAU012@@Z`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400055d4`

## callees

- `0x140004c2c`
- `0x140004ed8`

## pseudocode

```c
__int64 __fastcall Mso::LoadMso::LoadDllResults::operator=(__int64 a1, __int64 a2)
{
  _OWORD *v2; // r14
  _OWORD *v3; // rsi
  _OWORD *v6; // r14

  v2 = (_OWORD *)(a2 + 16);
  v3 = (_OWORD *)(a1 + 16);
  *(_OWORD *)a1 = *(_OWORD *)a2;
  if ( a1 + 16 != a2 + 16 )
  {
    std::wstring::_Tidy_deallocate(a1 + 16);
    *v3 = *v2;
    v3[1] = v2[1];
    *(_QWORD *)(a2 + 32) = 0;
    *(_QWORD *)(a2 + 40) = 7;
    *(_WORD *)v2 = 0;
  }
  v6 = (_OWORD *)(a2 + 64);
  *(_DWORD *)(a1 + 48) = *(_DWORD *)(a2 + 48);
  *(_DWORD *)(a1 + 52) = *(_DWORD *)(a2 + 52);
  *(_DWORD *)(a1 + 56) = *(_DWORD *)(a2 + 56);
  if ( a1 + 64 != a2 + 64 )
  {
    std::wstring::_Tidy_deallocate(a1 + 64);
    *(_OWORD *)(a1 + 64) = *v6;
    *(_OWORD *)(a1 + 80) = *(_OWORD *)(a2 + 80);
    *(_QWORD *)(a2 + 80) = 0;
    *(_QWORD *)(a2 + 88) = 7;
    *(_WORD *)v6 = 0;
  }
  *(_DWORD *)(a1 + 96) = *(_DWORD *)(a2 + 96);
  *(_DWORD *)(a1 + 100) = *(_DWORD *)(a2 + 100);
  *(_DWORD *)(a1 + 104) = *(_DWORD *)(a2 + 104);
  return a1;
}

```

## disassembly

```asm
0x140004ed8  mov     [rsp+arg_0], rbx
0x140004edd  mov     [rsp+arg_8], rbp
0x140004ee2  mov     [rsp+arg_10], rsi
0x140004ee7  mov     [rsp+arg_18], rdi
0x140004eec  push    r14
0x140004eee  sub     rsp, 20h
0x140004ef2  movups  xmm0, xmmword ptr [rdx]
0x140004ef5  lea     r14, [rdx+10h]
0x140004ef9  xor     ebp, ebp
0x140004efb  lea     rsi, [rcx+10h]
0x140004eff  mov     rbx, rdx
0x140004f02  mov     rdi, rcx
0x140004f05  movups  xmmword ptr [rcx], xmm0
0x140004f08  cmp     rsi, r14
0x140004f0b  jz      short loc_140004F35
0x140004f0d  mov     rcx, rsi
0x140004f10  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140004f15  movups  xmm0, xmmword ptr [r14]
0x140004f19  movups  xmmword ptr [rsi], xmm0
0x140004f1c  movups  xmm1, xmmword ptr [r14+10h]
0x140004f21  movups  xmmword ptr [rsi+10h], xmm1
0x140004f25  mov     [rbx+20h], rbp
0x140004f29  mov     qword ptr [rbx+28h], 7
0x140004f31  mov     [r14], bp
0x140004f35  mov     eax, [rbx+30h]
0x140004f38  lea     r14, [rbx+40h]
0x140004f3c  mov     [rdi+30h], eax
0x140004f3f  lea     rsi, [rdi+40h]
0x140004f43  mov     eax, [rbx+34h]
0x140004f46  mov     [rdi+34h], eax
0x140004f49  mov     eax, [rbx+38h]
0x140004f4c  mov     [rdi+38h], eax
0x140004f4f  cmp     rsi, r14
0x140004f52  jz      short loc_140004F7C
0x140004f54  mov     rcx, rsi
0x140004f57  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140004f5c  movups  xmm0, xmmword ptr [r14]
0x140004f60  movups  xmmword ptr [rsi], xmm0
0x140004f63  movups  xmm1, xmmword ptr [r14+10h]
0x140004f68  movups  xmmword ptr [rsi+10h], xmm1
0x140004f6c  mov     [rbx+50h], rbp
0x140004f70  mov     qword ptr [rbx+58h], 7
0x140004f78  mov     [r14], bp
0x140004f7c  mov     eax, [rbx+60h]
0x140004f7f  mov     rbp, [rsp+28h+arg_8]
0x140004f84  mov     rsi, [rsp+28h+arg_10]
0x140004f89  mov     [rdi+60h], eax
0x140004f8c  mov     eax, [rbx+64h]
0x140004f8f  mov     [rdi+64h], eax
0x140004f92  mov     eax, [rbx+68h]
0x140004f95  mov     rbx, [rsp+28h+arg_0]
0x140004f9a  mov     [rdi+68h], eax
0x140004f9d  mov     rax, rdi
0x140004fa0  mov     rdi, [rsp+28h+arg_18]
0x140004fa5  add     rsp, 20h
0x140004fa9  pop     r14
0x140004fab  retn
```
