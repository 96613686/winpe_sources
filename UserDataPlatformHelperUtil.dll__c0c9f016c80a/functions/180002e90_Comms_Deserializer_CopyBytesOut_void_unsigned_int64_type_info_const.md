# Comms::Deserializer::CopyBytesOut(void *,unsigned __int64,type_info const &)

- ea: `0x180002e90`
- end: `0x180002f5b`
- name: `?CopyBytesOut@Deserializer@Comms@@QEAA_NPEAX_KAEBVtype_info@@@Z`
- size: `203`
- prototype: `char __fastcall(Comms::Deserializer *this, void *, size_t, const struct type_info *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800028c0`
- `0x180002980`
- `0x180002f70`
- `0x180003050`

## callees

- `0x180002e90`
- `0x18000a142`

## import_xrefs

- `msvcrt!?raw_name@type_info@@QEBAPEBDXZ` at `0x180002ed1`
- `msvcrt!?raw_name@type_info@@QEBAPEBDXZ` at `0x180002ed1`

## pseudocode

```c
char __fastcall Comms::Deserializer::CopyBytesOut(
        Comms::Deserializer *this,
        void *a2,
        size_t a3,
        const struct type_info *a4)
{
  char v7; // bp
  int *v8; // rcx
  int v9; // ebx
  const char *v10; // rcx
  __int64 v11; // rax
  __int16 v12; // dx
  const char *v13; // r8

  v7 = 1;
  if ( !*((_BYTE *)this + 16) )
    goto LABEL_14;
  v8 = *(int **)this;
  if ( *((_QWORD *)this + 1) - (_QWORD)v8 < 4u )
    return 0;
  v9 = *v8;
  *(_QWORD *)this = v8 + 1;
  v10 = type_info::raw_name(a4);
  if ( a3 > 0xFFFF )
  {
    if ( (_WORD)v9 != 0xFFFF )
      return 0;
    goto LABEL_7;
  }
  if ( (_WORD)a3 != (_WORD)v9 )
    return 0;
LABEL_7:
  v11 = -1;
  do
    ++v11;
  while ( v10[v11] );
  v12 = -25147;
  v13 = &v10[v11];
  while ( v10 != v13 )
    v12 = *v10++ ^ (unsigned __int16)(403 * v12);
  if ( v12 != HIWORD(v9) )
    return 0;
LABEL_14:
  if ( *((_QWORD *)this + 1) - *(_QWORD *)this < a3 )
    return 0;
  memcpy_0(a2, *(const void **)this, a3);
  *(_QWORD *)this += a3;
  return v7;
}

```

## disassembly

```asm
0x180002e90  push    rbx
0x180002e92  push    rbp
0x180002e93  push    rsi
0x180002e94  push    rdi
0x180002e95  push    r14
0x180002e97  push    r15
0x180002e99  sub     rsp, 28h
0x180002e9d  cmp     byte ptr [rcx+10h], 0
0x180002ea1  mov     rsi, r8
0x180002ea4  mov     r15, rdx
0x180002ea7  mov     rdi, rcx
0x180002eaa  mov     ebp, 1
0x180002eaf  jz      short loc_180002F29
0x180002eb1  mov     rcx, [rcx]
0x180002eb4  mov     rax, [rdi+8]
0x180002eb8  sub     rax, rcx
0x180002ebb  cmp     rax, 4
0x180002ebf  jb      short loc_180002F25
0x180002ec1  mov     ebx, [rcx]
0x180002ec3  lea     rax, [rcx+4]
0x180002ec7  mov     rcx, r9
0x180002eca  mov     [rdi], rax
0x180002ecd  mov     [rsp+58h+arg_0], ebx
0x180002ed1  call    cs:__imp_?raw_name@type_info@@QEBAPEBDXZ; type_info::raw_name(void)
0x180002ed7  mov     rcx, rax
0x180002eda  mov     eax, 0FFFFh
0x180002edf  cmp     rsi, rax
0x180002ee2  jbe     short loc_180002EEB
0x180002ee4  cmp     bx, ax
0x180002ee7  jz      short loc_180002EF0
0x180002ee9  jmp     short loc_180002F25
0x180002eeb  cmp     si, bx
0x180002eee  jnz     short loc_180002F25
0x180002ef0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002ef4  inc     rax
0x180002ef7  cmp     byte ptr [rcx+rax], 0
0x180002efb  jnz     short loc_180002EF4
0x180002efd  mov     edx, 811C9DC5h
0x180002f02  lea     r8, [rax+rcx]
0x180002f06  jmp     short loc_180002F19
0x180002f08  movsx   rax, byte ptr [rcx]
0x180002f0c  imul    rdx, 1000193h
0x180002f13  xor     rdx, rax
0x180002f16  add     rcx, rbp
0x180002f19  cmp     rcx, r8
0x180002f1c  jnz     short loc_180002F08
0x180002f1e  cmp     dx, word ptr [rsp+58h+arg_0+2]
0x180002f23  jz      short loc_180002F29
0x180002f25  xor     al, al
0x180002f27  jmp     short loc_180002F4E
0x180002f29  mov     rax, [rdi+8]
0x180002f2d  sub     rax, [rdi]
0x180002f30  cmp     rax, rsi
0x180002f33  jnb     short loc_180002F3A
0x180002f35  xor     bpl, bpl
0x180002f38  jmp     short loc_180002F4B
0x180002f3a  mov     rdx, [rdi]; Src
0x180002f3d  mov     r8, rsi; Size
0x180002f40  mov     rcx, r15; void *
0x180002f43  call    memcpy_0
0x180002f48  add     [rdi], rsi
0x180002f4b  mov     al, bpl
0x180002f4e  add     rsp, 28h
0x180002f52  pop     r15
0x180002f54  pop     r14
0x180002f56  pop     rdi
0x180002f57  pop     rsi
0x180002f58  pop     rbp
0x180002f59  pop     rbx
0x180002f5a  retn
```
