# LocalPrintConfigData::CreateLocalPrintConfigData(void *,PrintConfigDataContext &,LocalPrintConfigData * *)

- ea: `0x180035968`
- end: `0x180035a24`
- name: `?CreateLocalPrintConfigData@LocalPrintConfigData@@SAJPEAXAEAVPrintConfigDataContext@@PEAPEAV1@@Z`
- size: `188`
- prototype: `__int64 __fastcall(void *, struct PrintConfigDataContext *, struct LocalPrintConfigData **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180035a2c`

## callees

- `0x1800029ec`
- `0x1800355d0`
- `0x180035968`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall LocalPrintConfigData::CreateLocalPrintConfigData(
        void *a1,
        struct PrintConfigDataContext *a2,
        struct LocalPrintConfigData **a3)
{
  LocalPrintConfigData *v7; // rax
  LocalPrintConfigData *v8; // rax
  int v9; // ebx

  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  v7 = (LocalPrintConfigData *)operator new(0xD20u, (const struct std::nothrow_t *)byte_18006E400);
  if ( !v7 )
  {
    *a3 = 0;
    return (unsigned int)-2147024882;
  }
  v8 = LocalPrintConfigData::LocalPrintConfigData(v7, a2, a1);
  *a3 = v8;
  if ( !v8 )
    return (unsigned int)-2147024882;
  v9 = *((_DWORD *)v8 + 838);
  if ( v9 >= 0 )
    v9 = 0;
  if ( v9 >= 0 )
  {
    if ( **((_DWORD **)v8 + 1) < 4u || *((_QWORD *)v8 + 12) )
      return (unsigned int)v9;
    v9 = -2147023728;
  }
  (*(void (__fastcall **)(LocalPrintConfigData *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
  *a3 = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180035968  mov     [rsp+arg_0], rbx
0x18003596d  mov     [rsp+arg_8], rsi
0x180035972  push    rdi
0x180035973  sub     rsp, 20h
0x180035977  mov     rdi, r8
0x18003597a  mov     rbx, rdx
0x18003597d  mov     rsi, rcx
0x180035980  test    r8, r8
0x180035983  jnz     short loc_18003598F
0x180035985  mov     eax, 80070057h
0x18003598a  jmp     loc_180035A13
0x18003598f  lea     rdx, byte_18006E400; struct std::nothrow_t *
0x180035996  mov     qword ptr [r8], 0
0x18003599d  mov     ecx, 0D20h; unsigned __int64
0x1800359a2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800359a7  test    rax, rax
0x1800359aa  jz      short loc_180035A05
0x1800359ac  mov     r8, rsi; void *
0x1800359af  mov     rdx, rbx; struct PrintConfigDataContext *
0x1800359b2  mov     rcx, rax; this
0x1800359b5  call    ??0LocalPrintConfigData@@AEAA@AEAVPrintConfigDataContext@@PEAX@Z; LocalPrintConfigData::LocalPrintConfigData(PrintConfigDataContext &,void *)
0x1800359ba  mov     [rdi], rax
0x1800359bd  mov     rcx, rax
0x1800359c0  test    rax, rax
0x1800359c3  jz      short loc_180035A0C
0x1800359c5  mov     ebx, [rax+0D18h]
0x1800359cb  xor     eax, eax
0x1800359cd  test    ebx, ebx
0x1800359cf  cmovns  ebx, eax
0x1800359d2  test    ebx, ebx
0x1800359d4  js      short loc_1800359EB
0x1800359d6  mov     rax, [rcx+8]
0x1800359da  cmp     dword ptr [rax], 4
0x1800359dd  jb      short loc_180035A11
0x1800359df  cmp     qword ptr [rcx+60h], 0
0x1800359e4  jnz     short loc_180035A11
0x1800359e6  mov     ebx, 80070490h
0x1800359eb  mov     rax, [rcx]
0x1800359ee  mov     edx, 1
0x1800359f3  mov     rax, [rax+20h]
0x1800359f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359fc  mov     qword ptr [rdi], 0
0x180035a03  jmp     short loc_180035A11
0x180035a05  mov     qword ptr [rdi], 0
0x180035a0c  mov     ebx, 8007000Eh
0x180035a11  mov     eax, ebx
0x180035a13  mov     rbx, [rsp+28h+arg_0]
0x180035a18  mov     rsi, [rsp+28h+arg_8]
0x180035a1d  add     rsp, 20h
0x180035a21  pop     rdi
0x180035a22  retn
```
