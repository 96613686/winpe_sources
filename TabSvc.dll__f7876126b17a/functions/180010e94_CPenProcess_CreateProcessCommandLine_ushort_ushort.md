# CPenProcess::CreateProcessCommandLine(ushort * *,ushort * *)

- ea: `0x180010e94`
- end: `0x180010f27`
- name: `?CreateProcessCommandLine@CPenProcess@@AEAAHPEAPEAG0@Z`
- size: `147`
- prototype: `__int64 __fastcall(CPenProcess *this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002c3c4`

## callees

- `0x180010e94`
- `0x180010f30`
- `0x18001bc04`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall CPenProcess::CreateProcessCommandLine(
        CPenProcess *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  __int64 v7; // rcx
  const struct std::nothrow_t *v8; // rdx
  _QWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  int v10; // [rsp+30h] [rbp-18h]
  int v11; // [rsp+34h] [rbp-14h]

  if ( StringAllocateAndCopyCore(a2, (unsigned __int16 *)this + 18, (int)a3) )
    return 0;
  v7 = *(_QWORD *)this;
  v9[0] = *((_QWORD *)this + 139);
  v9[1] = *((_QWORD *)this + 140);
  v10 = *((_DWORD *)this + 3);
  v11 = *((_DWORD *)this + 5);
  if ( !(*(unsigned int (__fastcall **)(__int64, unsigned __int16 **, _QWORD *))(*(_QWORD *)v7 + 40LL))(v7, a3, v9) )
  {
    operator delete(*a2, v8);
    *a2 = 0;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180010e94  mov     [rsp+arg_0], rbx
0x180010e99  mov     [rsp+arg_8], rsi
0x180010e9e  push    rdi
0x180010e9f  sub     rsp, 40h
0x180010ea3  mov     rbx, rdx
0x180010ea6  mov     rdi, rcx
0x180010ea9  lea     rdx, [rcx+24h]; unsigned __int16 *
0x180010ead  mov     rsi, r8
0x180010eb0  mov     rcx, rbx; unsigned __int16 **
0x180010eb3  call    ?StringAllocateAndCopyCore@@YAJPEAPEAGPEAGH@Z; StringAllocateAndCopyCore(ushort * *,ushort *,int)
0x180010eb8  test    eax, eax
0x180010eba  jz      short loc_180010EC0
0x180010ebc  xor     eax, eax
0x180010ebe  jmp     short loc_180010F17
0x180010ec0  mov     rax, [rdi+458h]
0x180010ec7  lea     r8, [rsp+48h+var_28]
0x180010ecc  mov     rcx, [rdi]
0x180010ecf  mov     rdx, rsi
0x180010ed2  mov     [rsp+48h+var_28], rax
0x180010ed7  mov     rax, [rdi+460h]
0x180010ede  mov     [rsp+48h+var_20], rax
0x180010ee3  mov     eax, [rdi+0Ch]
0x180010ee6  mov     [rsp+48h+var_18], eax
0x180010eea  mov     eax, [rdi+14h]
0x180010eed  mov     [rsp+48h+var_14], eax
0x180010ef1  mov     rax, [rcx]
0x180010ef4  mov     rax, [rax+28h]
0x180010ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010efd  test    eax, eax
0x180010eff  jnz     short loc_180010F12
0x180010f01  mov     rcx, [rbx]; void *
0x180010f04  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010f09  mov     qword ptr [rbx], 0
0x180010f10  jmp     short loc_180010EBC
0x180010f12  mov     eax, 1
0x180010f17  mov     rbx, [rsp+48h+arg_0]
0x180010f1c  mov     rsi, [rsp+48h+arg_8]
0x180010f21  add     rsp, 40h
0x180010f25  pop     rdi
0x180010f26  retn
```
