# _archive_write_free

- ea: `0x1800efed0`
- end: `0x1800efff6`
- name: `_archive_write_free`
- size: `294`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000523c`
- `0x18000e7ec`
- `0x180015810`
- `0x1800eec10`
- `0x1800efb50`
- `0x1800efed0`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eff4c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eff66`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eff9c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800effcd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800effde`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eff4c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eff66`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eff9c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800effcd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800effde`

## string_xrefs

- `0x1800efeee`: `archive_write_free`

## pseudocode

```c
__int64 __fastcall archive_write_free(void **Block)
{
  __int64 result; // rax
  unsigned int close; // esi
  __int64 (__fastcall *v4)(void *); // rax
  int v5; // eax
  void *v6; // rcx
  _BYTE *v7; // rcx
  size_t v8; // r8
  _QWORD *v9; // rcx
  _QWORD *v10; // rbx
  void *v11; // rcx

  if ( !Block )
    return 0;
  result = _archive_check_magic(Block, 2965749982LL, 0xFFFF, "archive_write_free");
  if ( (_DWORD)result != -30 )
  {
    close = 0;
    if ( *((_DWORD *)Block + 1) != 0x8000 )
      close = archive_read_close(Block);
    v4 = (__int64 (__fastcall *)(void *))Block[39];
    if ( v4 )
    {
      v5 = v4(Block);
      if ( v5 < (int)close )
        close = v5;
    }
    _archive_write_filters_free(Block);
    free(Block[21]);
    v6 = Block[6];
    Block[7] = 0;
    Block[8] = 0;
    free(v6);
    Block[6] = 0;
    v7 = Block[40];
    if ( v7 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v7[v8] );
      memset_0(v7, 0, v8);
      free(Block[40]);
    }
    *(_DWORD *)Block = 0;
    v9 = Block[11];
    if ( v9 )
    {
      do
      {
        v10 = (_QWORD *)*v9;
        free_sconv_object();
        v9 = v10;
      }
      while ( v10 );
    }
    v11 = Block[9];
    Block[11] = 0;
    free(v11);
    Block[9] = 0;
    free(Block);
    return close;
  }
  return result;
}

```

## disassembly

```asm
0x1800efed0  mov     [rsp+arg_0], rbx
0x1800efed5  mov     [rsp+arg_8], rsi
0x1800efeda  push    rdi
0x1800efedb  sub     rsp, 20h
0x1800efedf  mov     rdi, rcx
0x1800efee2  test    rcx, rcx
0x1800efee5  jnz     short loc_1800EFEEE
0x1800efee7  xor     eax, eax
0x1800efee9  jmp     loc_1800EFFE6
0x1800efeee  lea     r9, aArchiveWriteFr_0; "archive_write_free"
0x1800efef5  mov     edx, 0B0C5C0DEh
0x1800efefa  mov     r8d, 0FFFFh
0x1800eff00  call    __archive_check_magic
0x1800eff05  cmp     eax, 0FFFFFFE2h
0x1800eff08  jnz     short loc_1800EFF0F
0x1800eff0a  jmp     loc_1800EFFE6
0x1800eff0f  xor     esi, esi
0x1800eff11  cmp     dword ptr [rdi+4], 8000h
0x1800eff18  jz      short loc_1800EFF24
0x1800eff1a  mov     rcx, rdi
0x1800eff1d  call    archive_read_close
0x1800eff22  mov     esi, eax
0x1800eff24  mov     rax, [rdi+138h]
0x1800eff2b  test    rax, rax
0x1800eff2e  jz      short loc_1800EFF3D
0x1800eff30  mov     rcx, rdi
0x1800eff33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eff38  cmp     eax, esi
0x1800eff3a  cmovl   esi, eax
0x1800eff3d  mov     rcx, rdi
0x1800eff40  call    __archive_write_filters_free
0x1800eff45  mov     rcx, [rdi+0A8h]; Block
0x1800eff4c  call    cs:__imp_free
0x1800eff52  mov     rcx, [rdi+30h]; Block
0x1800eff56  mov     qword ptr [rdi+38h], 0
0x1800eff5e  mov     qword ptr [rdi+40h], 0
0x1800eff66  call    cs:__imp_free
0x1800eff6c  mov     qword ptr [rdi+30h], 0
0x1800eff74  mov     rcx, [rdi+140h]; void *
0x1800eff7b  test    rcx, rcx
0x1800eff7e  jz      short loc_1800EFFA2
0x1800eff80  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800eff84  inc     r8; Size
0x1800eff87  cmp     byte ptr [rcx+r8], 0
0x1800eff8c  jnz     short loc_1800EFF84
0x1800eff8e  xor     edx, edx; Val
0x1800eff90  call    memset_0
0x1800eff95  mov     rcx, [rdi+140h]; Block
0x1800eff9c  call    cs:__imp_free
0x1800effa2  mov     dword ptr [rdi], 0
0x1800effa8  mov     rcx, [rdi+58h]
0x1800effac  test    rcx, rcx
0x1800effaf  jz      short loc_1800EFFC1
0x1800effb1  mov     rbx, [rcx]
0x1800effb4  call    free_sconv_object
0x1800effb9  mov     rcx, rbx
0x1800effbc  test    rbx, rbx
0x1800effbf  jnz     short loc_1800EFFB1
0x1800effc1  mov     rcx, [rdi+48h]; Block
0x1800effc5  mov     qword ptr [rdi+58h], 0
0x1800effcd  call    cs:__imp_free
0x1800effd3  mov     rcx, rdi; Block
0x1800effd6  mov     qword ptr [rdi+48h], 0
0x1800effde  call    cs:__imp_free
0x1800effe4  mov     eax, esi
0x1800effe6  mov     rbx, [rsp+28h+arg_0]
0x1800effeb  mov     rsi, [rsp+28h+arg_8]
0x1800efff0  add     rsp, 20h
0x1800efff4  pop     rdi
0x1800efff5  retn
```
