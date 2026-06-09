# xar_write_header

- ea: `0x180113000`
- end: `0x18011328d`
- name: `xar_write_header`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180006c00`
- `0x180006f5c`
- `0x1800b1ce0`
- `0x1800e38b4`
- `0x1800ed47c`
- `0x1801108e8`
- `0x1801109c4`
- `0x180110e08`
- `0x180110f14`
- `0x180111004`
- `0x1801114e0`
- `0x1801123bc`
- `0x1801128e8`
- `0x180113000`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180113138`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180113175`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180113138`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180113175`
- `api-ms-win-crt-private-l1-1-0!_o__lseeki64` at `0x18011316a`
- `api-ms-win-crt-private-l1-1-0!_o__lseeki64` at `0x18011316a`

## string_xrefs

- `0x18011313e`: `Couldn't create temporary file`

## pseudocode

```c
__int64 __fastcall xar_write_header(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  bool v5; // zf
  __int64 v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  __int64 v9; // rcx
  const char *v10; // r8
  __int64 v11; // rdx
  __int64 result; // rax
  unsigned int v13; // ebp
  __int64 v14; // r14
  __int64 v15; // rcx
  _QWORD *v16; // rbx
  int v17; // eax
  __int64 v18; // rcx
  unsigned int *v19; // rax
  int v20; // eax
  int v21; // r9d
  __int64 v22; // r14
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rdx
  unsigned int inited; // eax
  _QWORD *v27; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 248);
  v5 = *(_QWORD *)(v2 + 344) == 0;
  *(_QWORD *)(v2 + 64) = 0;
  *(_QWORD *)(v2 + 72) = 0;
  if ( v5 )
  {
    v6 = archive_string_conversion_to_charset(a1, "UTF-8", 1);
    *(_QWORD *)(v2 + 344) = v6;
    if ( !v6 )
      return 4294967266LL;
  }
  v7 = (_QWORD *)file_new_1(a1, a2);
  v27 = v7;
  v8 = v7;
  v9 = a1;
  if ( !v7 )
  {
    v10 = "Can't allocate data";
    v11 = 12;
LABEL_5:
    archive_set_error(v9, v11, v10);
    return 4294967266LL;
  }
  v13 = file_gen_utility_names(a1, v7);
  if ( (int)v13 < -20 )
    return v13;
  if ( !v8[15] && !v8[18] )
  {
    file_free_2(v8);
    return v13;
  }
  v14 = v8[4];
  result = file_tree(a1, &v27);
  if ( (_DWORD)result )
    return result;
  v16 = v27;
  if ( v27[4] != v14 )
    return v13;
  if ( !*((_DWORD *)v27 + 6) )
  {
    v15 = (__int64)(v27 + 7);
    *((_DWORD *)v27 + 6) = (*(_DWORD *)(v2 + 16))++;
    v16[7] = 0;
    **(_QWORD **)(v2 + 66032) = v16;
    *(_QWORD *)(v2 + 66032) = v16 + 7;
  }
  if ( (v16[45] & 1) != 0 )
    return v13;
  if ( *(_DWORD *)v2 == -1 )
  {
    *(_QWORD *)(v2 + 8) = 0;
    v17 = _archive_mktempx(v15, 0);
    *(_DWORD *)v2 = v17;
    if ( v17 < 0 )
    {
      v19 = (unsigned int *)_o__errno(v18);
      v10 = "Couldn't create temporary file";
LABEL_19:
      v11 = *v19;
      v9 = a1;
      goto LABEL_5;
    }
    v20 = getalgsize(*(unsigned int *)(v2 + 128));
    if ( v20 > 0 )
    {
      v22 = v20;
      if ( _lseeki64(v21, v20, 0) < 0 )
      {
        v19 = (unsigned int *)_o__errno(v23);
        v10 = "lseek failed";
        goto LABEL_19;
      }
      *(_QWORD *)(v2 + 8) = v22;
    }
  }
  if ( !archive_entry_hardlink(v16[4]) && (unsigned int)save_xattrs(a1, v16) )
    return 4294967266LL;
  if ( (*(_WORD *)(v16[4] + 1032LL) & 0xF000) == 0x8000 )
  {
    *(_QWORD *)(v2 + 64) = v16;
    if ( *(_DWORD *)(v16[4] + 104LL) <= 1u )
      goto LABEL_31;
    result = file_register_hardlink(a1, v16);
    if ( (_DWORD)result )
      return result;
    if ( archive_entry_hardlink(v16[4]) )
    {
      v24 = v16[4];
      *(_DWORD *)(v24 + 160) &= ~0x40u;
      *(_DWORD *)(v24 + 16) = 0;
      *(_QWORD *)(v24 + 112) = 0;
    }
    else
    {
LABEL_31:
      v16[28] = *(_QWORD *)(v2 + 8);
      v16[30] = *(_QWORD *)(v16[4] + 112LL);
      *((_DWORD *)v16 + 62) = *(_DWORD *)(v2 + 136);
      v25 = *(unsigned int *)(v2 + 132);
      *(_QWORD *)(v2 + 72) = *(_QWORD *)(v16[4] + 112LL);
      checksum_init(v2 + 152, v25);
      checksum_init(v2 + 208, *(unsigned int *)(v2 + 132));
      inited = xar_compression_init_encoder(a1);
      if ( inited )
        return inited;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180113000  mov     [rsp+arg_8], rbx
0x180113005  mov     [rsp+arg_10], rbp
0x18011300a  push    rsi
0x18011300b  push    rdi
0x18011300c  push    r14
0x18011300e  sub     rsp, 20h
0x180113012  mov     rdi, [rcx+0F8h]
0x180113019  mov     rbx, rdx
0x18011301c  mov     rsi, rcx
0x18011301f  cmp     qword ptr [rdi+158h], 0
0x180113027  mov     qword ptr [rdi+40h], 0
0x18011302f  mov     qword ptr [rdi+48h], 0
0x180113037  jnz     short loc_180113057
0x180113039  mov     r8d, 1
0x18011303f  lea     rdx, Str2; "UTF-8"
0x180113046  call    archive_string_conversion_to_charset
0x18011304b  mov     [rdi+158h], rax
0x180113052  test    rax, rax
0x180113055  jz      short loc_180113081
0x180113057  mov     rdx, rbx
0x18011305a  mov     rcx, rsi
0x18011305d  call    file_new_1
0x180113062  mov     [rsp+38h+arg_0], rax
0x180113067  mov     rbx, rax
0x18011306a  mov     rcx, rsi
0x18011306d  test    rax, rax
0x180113070  jnz     short loc_18011308B
0x180113072  lea     r8, aCanTAllocateDa_4; "Can't allocate data"
0x180113079  lea     edx, [rax+0Ch]
0x18011307c  call    archive_set_error
0x180113081  mov     eax, 0FFFFFFE2h
0x180113086  jmp     loc_18011327A
0x18011308b  mov     rdx, rbx
0x18011308e  call    file_gen_utility_names
0x180113093  mov     ebp, eax
0x180113095  cmp     eax, 0FFFFFFECh
0x180113098  jl      loc_180113278
0x18011309e  cmp     qword ptr [rbx+78h], 0
0x1801130a3  jnz     short loc_1801130BC
0x1801130a5  cmp     qword ptr [rbx+90h], 0
0x1801130ad  jnz     short loc_1801130BC
0x1801130af  mov     rcx, rbx
0x1801130b2  call    file_free_2
0x1801130b7  jmp     loc_180113278
0x1801130bc  mov     r14, [rbx+20h]
0x1801130c0  lea     rdx, [rsp+38h+arg_0]
0x1801130c5  mov     rcx, rsi
0x1801130c8  call    file_tree
0x1801130cd  test    eax, eax
0x1801130cf  jnz     loc_18011327A
0x1801130d5  mov     rbx, [rsp+38h+arg_0]
0x1801130da  cmp     [rbx+20h], r14
0x1801130de  jnz     loc_180113278
0x1801130e4  cmp     [rbx+18h], eax
0x1801130e7  jnz     short loc_18011310E
0x1801130e9  mov     eax, [rdi+10h]
0x1801130ec  lea     rcx, [rbx+38h]
0x1801130f0  mov     [rbx+18h], eax
0x1801130f3  inc     dword ptr [rdi+10h]
0x1801130f6  mov     qword ptr [rcx], 0
0x1801130fd  mov     rax, [rdi+101F0h]
0x180113104  mov     [rax], rbx
0x180113107  mov     [rdi+101F0h], rcx
0x18011310e  test    byte ptr [rbx+168h], 1
0x180113115  jnz     loc_180113278
0x18011311b  cmp     dword ptr [rdi], 0FFFFFFFFh
0x18011311e  jnz     short loc_180113188
0x180113120  xor     edx, edx
0x180113122  mov     qword ptr [rdi+8], 0
0x18011312a  call    __archive_mktempx
0x18011312f  mov     [rdi], eax
0x180113131  mov     r9d, eax
0x180113134  test    eax, eax
0x180113136  jns     short loc_18011314F
0x180113138  call    cs:__imp__o__errno
0x18011313e  lea     r8, aCouldnTCreateT; "Couldn't create temporary file"
0x180113145  mov     edx, [rax]
0x180113147  mov     rcx, rsi
0x18011314a  jmp     loc_18011307C
0x18011314f  mov     ecx, [rdi+80h]
0x180113155  call    getalgsize
0x18011315a  test    eax, eax
0x18011315c  jle     short loc_180113188
0x18011315e  movsxd  r14, eax
0x180113161  xor     r8d, r8d; Origin
0x180113164  mov     rdx, r14; Offset
0x180113167  mov     ecx, r9d; FileHandle
0x18011316a  call    cs:__imp__lseeki64
0x180113170  test    rax, rax
0x180113173  jns     short loc_180113184
0x180113175  call    cs:__imp__o__errno
0x18011317b  lea     r8, aLseekFailed; "lseek failed"
0x180113182  jmp     short loc_180113145
0x180113184  mov     [rdi+8], r14
0x180113188  mov     rcx, [rbx+20h]
0x18011318c  call    archive_entry_hardlink
0x180113191  test    rax, rax
0x180113194  jnz     short loc_1801131A9
0x180113196  mov     rdx, rbx
0x180113199  mov     rcx, rsi
0x18011319c  call    save_xattrs
0x1801131a1  test    eax, eax
0x1801131a3  jnz     loc_180113081
0x1801131a9  mov     rax, [rbx+20h]
0x1801131ad  movzx   ecx, word ptr [rax+408h]
0x1801131b4  mov     eax, 0F000h
0x1801131b9  and     cx, ax
0x1801131bc  mov     eax, 8000h
0x1801131c1  cmp     cx, ax
0x1801131c4  jnz     loc_180113278
0x1801131ca  mov     [rdi+40h], rbx
0x1801131ce  mov     rax, [rbx+20h]
0x1801131d2  cmp     dword ptr [rax+68h], 1
0x1801131d6  jbe     short loc_180113215
0x1801131d8  mov     rdx, rbx
0x1801131db  mov     rcx, rsi
0x1801131de  call    file_register_hardlink
0x1801131e3  test    eax, eax
0x1801131e5  jnz     loc_18011327A
0x1801131eb  mov     rcx, [rbx+20h]
0x1801131ef  call    archive_entry_hardlink
0x1801131f4  test    rax, rax
0x1801131f7  jz      short loc_180113215
0x1801131f9  mov     rax, [rbx+20h]
0x1801131fd  and     dword ptr [rax+0A0h], 0FFFFFFBFh
0x180113204  mov     dword ptr [rax+10h], 0
0x18011320b  mov     qword ptr [rax+70h], 0
0x180113213  jmp     short loc_180113278
0x180113215  mov     rax, [rdi+8]
0x180113219  mov     [rbx+0E0h], rax
0x180113220  mov     rax, [rbx+20h]
0x180113224  mov     rcx, [rax+70h]
0x180113228  mov     [rbx+0F0h], rcx
0x18011322f  mov     eax, [rdi+88h]
0x180113235  mov     [rbx+0F8h], eax
0x18011323b  mov     rax, [rbx+20h]
0x18011323f  mov     edx, [rdi+84h]
0x180113245  mov     rcx, [rax+70h]
0x180113249  mov     [rdi+48h], rcx
0x18011324d  lea     rcx, [rdi+98h]
0x180113254  call    checksum_init
0x180113259  mov     edx, [rdi+84h]
0x18011325f  lea     rcx, [rdi+0D0h]
0x180113266  call    checksum_init
0x18011326b  mov     rcx, rsi
0x18011326e  call    xar_compression_init_encoder
0x180113273  test    eax, eax
0x180113275  cmovnz  ebp, eax
0x180113278  mov     eax, ebp
0x18011327a  mov     rbx, [rsp+38h+arg_8]
0x18011327f  mov     rbp, [rsp+38h+arg_10]
0x180113284  add     rsp, 20h
0x180113288  pop     r14
0x18011328a  pop     rdi
0x18011328b  pop     rsi
0x18011328c  retn
```
