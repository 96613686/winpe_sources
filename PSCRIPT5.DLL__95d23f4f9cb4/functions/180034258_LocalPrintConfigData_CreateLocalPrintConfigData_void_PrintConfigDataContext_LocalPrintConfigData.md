# LocalPrintConfigData::CreateLocalPrintConfigData(void *,PrintConfigDataContext &,LocalPrintConfigData * *)

- ea: `0x180034258`
- end: `0x180034313`
- name: `?CreateLocalPrintConfigData@LocalPrintConfigData@@SAJPEAXAEAVPrintConfigDataContext@@PEAPEAV1@@Z`
- size: `187`
- prototype: `__int64 __fastcall(void *, struct PrintConfigDataContext *, struct LocalPrintConfigData **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003431c`

## callees

- `0x18000298c`
- `0x180033ecc`
- `0x180034258`
- `0x18005d010`

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
  v7 = (LocalPrintConfigData *)operator new(0xD20u, (const struct std::nothrow_t *)byte_18006C430);
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
0x180034258  mov     [rsp+arg_0], rbx
0x18003425d  mov     [rsp+arg_8], rsi
0x180034262  push    rdi
0x180034263  sub     rsp, 20h
0x180034267  mov     rdi, r8
0x18003426a  mov     rbx, rdx
0x18003426d  mov     rsi, rcx
0x180034270  test    r8, r8
0x180034273  jnz     short loc_18003427F
0x180034275  mov     eax, 80070057h
0x18003427a  jmp     loc_180034303
0x18003427f  lea     rdx, byte_18006C430; struct std::nothrow_t *
0x180034286  mov     qword ptr [r8], 0
0x18003428d  mov     ecx, 0D20h; unsigned __int64
0x180034292  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180034297  test    rax, rax
0x18003429a  jz      short loc_1800342F5
0x18003429c  mov     r8, rsi; void *
0x18003429f  mov     rdx, rbx; struct PrintConfigDataContext *
0x1800342a2  mov     rcx, rax; this
0x1800342a5  call    ??0LocalPrintConfigData@@AEAA@AEAVPrintConfigDataContext@@PEAX@Z; LocalPrintConfigData::LocalPrintConfigData(PrintConfigDataContext &,void *)
0x1800342aa  mov     [rdi], rax
0x1800342ad  mov     rcx, rax
0x1800342b0  test    rax, rax
0x1800342b3  jz      short loc_1800342FC
0x1800342b5  mov     ebx, [rax+0D18h]
0x1800342bb  xor     eax, eax
0x1800342bd  test    ebx, ebx
0x1800342bf  cmovns  ebx, eax
0x1800342c2  test    ebx, ebx
0x1800342c4  js      short loc_1800342DB
0x1800342c6  mov     rax, [rcx+8]
0x1800342ca  cmp     dword ptr [rax], 4
0x1800342cd  jb      short loc_180034301
0x1800342cf  cmp     qword ptr [rcx+60h], 0
0x1800342d4  jnz     short loc_180034301
0x1800342d6  mov     ebx, 80070490h
0x1800342db  mov     rax, [rcx]
0x1800342de  mov     edx, 1
0x1800342e3  mov     rax, [rax+20h]
0x1800342e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342ec  mov     qword ptr [rdi], 0
0x1800342f3  jmp     short loc_180034301
0x1800342f5  mov     qword ptr [rdi], 0
0x1800342fc  mov     ebx, 8007000Eh
0x180034301  mov     eax, ebx
0x180034303  mov     rbx, [rsp+28h+arg_0]
0x180034308  mov     rsi, [rsp+28h+arg_8]
0x18003430d  add     rsp, 20h
0x180034311  pop     rdi
0x180034312  retn
```
