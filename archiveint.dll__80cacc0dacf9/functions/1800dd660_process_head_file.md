# process_head_file

- ea: `0x1800dd660`
- end: `0x1800ddcb8`
- name: `process_head_file`
- size: `1624`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, installer_update`

## callers

- `0x1800dd350`

## callees

- `0x180005608`
- `0x1800056c0`
- `0x1800057bc`
- `0x1800057f8`
- `0x180005c00`
- `0x180006c00`
- `0x18000be54`
- `0x18000bec4`
- `0x18000e920`
- `0x18000ed50`
- `0x180013fc0`
- `0x180014fc0`
- `0x180015000`
- `0x180015810`
- `0x1800aba00`
- `0x1800aba54`
- `0x1800b1580`
- `0x1800dd660`
- `0x1800ddcc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ddaf4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ddaf4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800dda84`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800dda84`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800dd9b3`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800dd9b3`

## string_xrefs

- `0x1800dd844`: `directory entries cannot have any data`
- `0x1800dd852`: `no data found in file/service block`

## pseudocode

```c
__int64 __fastcall process_head_file(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  __int64 v8; // r12
  _QWORD *v9; // rsi
  int v10; // r14d
  char v11; // r13
  const char *v12; // r8
  __int64 v13; // rdx
  __int64 result; // rax
  __int64 v15; // r12
  int v16; // r13d
  char v17; // dl
  char v18; // r10
  int v19; // r9d
  __int64 v20; // rsi
  int v21; // edx
  char v22; // r10
  char v23; // al
  __int64 v24; // rax
  __int64 v25; // rax
  char v26; // al
  char v27; // r14
  __int16 v28; // ax
  _QWORD *v29; // rax
  void *v30; // rsi
  _QWORD *v31; // rcx
  __int16 v32; // ax
  size_t v33; // rsi
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  bool v37; // zf
  __int64 v38; // rcx
  __int64 v39; // rax
  char v40; // al
  unsigned int v41; // [rsp+20h] [rbp-E0h] BYREF
  int v42; // [rsp+24h] [rbp-DCh] BYREF
  unsigned int v43; // [rsp+28h] [rbp-D8h]
  int v44; // [rsp+2Ch] [rbp-D4h]
  __int64 v45; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v46; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v47; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v48; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  intmax_t v51; // [rsp+60h] [rbp-A0h] BYREF
  size_t Size; // [rsp+68h] [rbp-98h] BYREF
  void *Src; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v54[8192]; // [rsp+80h] [rbp-80h] BYREF

  v45 = 0;
  v43 = 0;
  v41 = 0;
  v44 = 0;
  v42 = 0;
  v8 = 0;
  v48 = 0;
  v49 = 0;
  v47 = 0;
  v50 = 0;
  v51 = 0;
  Size = 0;
  v46 = 0;
  Src = 0;
  archive_entry_clear((void *)a3);
  v9 = (_QWORD *)(a2 + 19376);
  if ( (*(_BYTE *)(a2 + 56) & 4) == 0 )
  {
    memset_0((void *)(a2 + 19376), 0, 0x770u);
    blake2sp_init(a2 + 19496);
    if ( (*(_BYTE *)(a2 + 44) & 1) != 0 )
      *(_QWORD *)(a2 + 144) += *(_QWORD *)(a2 + 120);
    else
      *(_QWORD *)(a2 + 144) = 0;
    *(_QWORD *)(a2 + 120) = 0;
    *(_QWORD *)(a2 + 128) = 0;
    *(_QWORD *)(a2 + 136) = 0;
    *(_QWORD *)(a2 + 21256) = 0;
    *(_QWORD *)(a2 + 21264) = 0;
    free_filters(a2);
  }
  if ( (a4 & 1) != 0 )
  {
    v45 = 0;
    if ( !(unsigned int)read_var(a1, &v45, 0) )
      return 1;
  }
  v10 = a4 & 2;
  if ( v10 )
  {
    if ( !(unsigned int)read_var_sized(a1, &v48, 0) )
      return 1;
    v8 = v48;
    *v9 = v48;
  }
  else
  {
    *v9 = 0;
  }
  if ( !(unsigned int)read_var_sized(a1, &v49, 0) || !(unsigned int)read_var(a1, &v46, 0) )
    return 1;
  v11 = v49;
  if ( (v49 & 8) != 0 )
  {
    v12 = "Files with unknown unpacked size are not supported";
LABEL_16:
    v13 = 22;
LABEL_17:
    archive_set_error(a1, v13, v12);
    return 4294967266LL;
  }
  *(_BYTE *)(a2 + 19408) &= ~8u;
  *(_BYTE *)(a2 + 19408) |= (v11 & 1) != 0 ? 8 : 0;
  if ( (v11 & 1) != 0 )
  {
    if ( v46 || v8 )
    {
      v12 = "directory entries cannot have any data";
LABEL_25:
      v13 = 42;
      goto LABEL_17;
    }
  }
  else if ( !v10 )
  {
    v12 = "no data found in file/service block";
    goto LABEL_25;
  }
  if ( !(unsigned int)read_var_sized(a1, &v47, 0) )
    return 1;
  v15 = v11 & 2;
  if ( (v11 & 2) != 0 )
  {
    if ( !(unsigned __int8)read_u32(a1, &v41) )
      return 1;
    v43 = v41;
  }
  v16 = v11 & 4;
  if ( v16 )
  {
    if ( (unsigned __int8)read_u32(a1, &v42) )
    {
      v44 = v42;
      goto LABEL_33;
    }
    return 1;
  }
LABEL_33:
  if ( !(unsigned int)read_var_sized(a1, &v50, 0) )
    return 1;
  v17 = v50;
  v18 = *(_BYTE *)(a2 + 19408);
  v19 = v50 & 0x3F;
  if ( (v18 & 8) != 0 )
    v20 = 0;
  else
    v20 = 0x20000LL << ((v50 >> 10) & 0xF);
  *(_DWORD *)(a2 + 68) = (v50 >> 7) & 7;
  v21 = v17 & 0x40;
  *(_DWORD *)(a2 + 72) = v19 + 50;
  v22 = v18 & 0xFE;
  v23 = v22 | (v21 != 0);
  *(_BYTE *)(a2 + 19408) = v23;
  if ( v21 && (*(_BYTE *)(a2 + 56) & 0x10) == 0 && !*(_QWORD *)(a2 + 88) )
  {
    v12 = "Declared solid file, but no window buffer initialized yet.";
    goto LABEL_25;
  }
  if ( (unsigned __int64)v20 > 0x4000000 || (v23 & 8) == 0 && !v20 )
  {
    v12 = "Declared dictionary size is not supported.";
    goto LABEL_25;
  }
  if ( v22 & 1 | (v21 != 0) )
  {
    v24 = *(_QWORD *)(a2 + 21272);
    if ( v24 > 0 && v24 != v20 )
    {
      v12 = "Window size for this solid file doesn't match the window size used in previous solid file. ";
      goto LABEL_25;
    }
  }
  else
  {
    *(_BYTE *)(a2 + 56) &= ~0x10u;
  }
  if ( *(_QWORD *)(a2 + 80) < v20 && *(_QWORD *)(a2 + 88) )
  {
    memset_0((void *)(a2 + 19312), 0, 0x40u);
    v25 = _o_realloc(*(_QWORD *)(a2 + 88), v20);
    if ( !v25 )
    {
      v12 = "Not enough memory when trying to realloc the window buffer.";
      goto LABEL_16;
    }
    *(_QWORD *)(a2 + 88) = v25;
  }
  v26 = *(_BYTE *)(a2 + 19408);
  *(_QWORD *)(a2 + 80) = v20;
  if ( (v26 & 1) != 0 && !*(_QWORD *)(a2 + 21272) )
    *(_QWORD *)(a2 + 21272) = v20;
  if ( v20 )
    --v20;
  *(_QWORD *)(a2 + 112) = v20;
  *(_BYTE *)(a2 + 19408) = v26 & 0xFD;
  if ( !(unsigned int)read_var_sized(a1, &v51, 0) )
    return 1;
  if ( v51 )
  {
    if ( v51 != 1 )
    {
      archive_set_error(a1, 42, "Unsupported Host OS: 0x%jx", v51);
      return 4294967266LL;
    }
    v32 = v47;
    *(_DWORD *)(a3 + 160) |= 0x600u;
    *(_WORD *)(a3 + 1032) = v32;
    *(_DWORD *)(a3 + 16) = 0;
  }
  else
  {
    v27 = v47;
    if ( (v47 & 0x10) != 0 )
    {
      v28 = ~((_WORD)v47 << 7) & 0x80 | 0x416D;
    }
    else
    {
      v28 = -32476;
      if ( (v47 & 1) == 0 )
        v28 = -32348;
    }
    *(_DWORD *)(a3 + 160) |= 0x600u;
    *(_DWORD *)(a3 + 16) = 0;
    *(_WORD *)(a3 + 1032) = v28;
    if ( (v27 & 7) != 0 )
    {
      v29 = malloc(0x16u);
      v30 = v29;
      if ( v29 )
      {
        if ( (v27 & 1) != 0 )
        {
          v31 = (_QWORD *)((char *)v29 + 7);
          *v29 = 0x796C6E6F64722CLL;
        }
        else
        {
          v31 = v29;
        }
        if ( (v27 & 2) != 0 )
        {
          *v31 = 0x6E65646469682CLL;
          v31 = (_QWORD *)((char *)v31 + 7);
        }
        if ( (v27 & 4) != 0 )
        {
          *v31 = 0x6D65747379732CLL;
          v31 = (_QWORD *)((char *)v31 + 7);
        }
        if ( v31 > v29 )
          archive_entry_copy_fflags_text(a3, (char *)v29 + 1);
        free(v30);
      }
    }
  }
  if ( !(unsigned int)read_var_sized(a1, &Size, 0) )
    return 1;
  v33 = Size;
  if ( Size > 0x7FF )
  {
    v12 = "Filename is too long";
    goto LABEL_25;
  }
  if ( !Size )
  {
    archive_set_error(a1, 42, "No filename specified");
    return 4294967266LL;
  }
  if ( !(unsigned int)read_ahead(a1, Size, &Src) )
    return 1;
  memcpy_0(v54, Src, v33);
  if ( v33 >= 0x2000 )
    _report_rangecheckfailure(v35, v34, v36);
  v54[v33] = 0;
  if ( (unsigned int)consume(a1, v33) )
    return 1;
  archive_entry_update_pathname_utf8(a3, v54);
  if ( v45 <= 0 || (result = process_head_file_extra(a1, a3, a2, v45), !(_DWORD)result) )
  {
    v37 = *(_QWORD *)(a2 + 21256) == 0;
    v38 = v46;
    *(_QWORD *)(a2 + 19384) = v46;
    if ( v37 )
    {
      v39 = 0;
      *(_DWORD *)(a3 + 16) = 0;
      if ( v38 >= 0 )
        v39 = v38;
      *(_DWORD *)(a3 + 160) |= 0x40u;
      *(_QWORD *)(a3 + 112) = v39;
    }
    if ( v15 )
      archive_entry_set_mtime(a3, v43, 0);
    if ( v16 )
      *(_DWORD *)(a2 + 19452) = v44;
    v40 = *(_BYTE *)(a2 + 56);
    if ( (v40 & 4) == 0 )
      *(_BYTE *)(a2 + 56) = v40 & 0xF4 | 0xA;
    return (*(_BYTE *)(a2 + 32) & 2) != 0 ? 0xFFFFFFF6 : 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800dd660  mov     [rsp-8+arg_18], rbx
0x1800dd665  push    rbp
0x1800dd666  push    rsi
0x1800dd667  push    rdi
0x1800dd668  push    r12
0x1800dd66a  push    r13
0x1800dd66c  push    r14
0x1800dd66e  push    r15
0x1800dd670  lea     rbp, [rsp-1F90h]
0x1800dd678  mov     eax, 2090h
0x1800dd67d  call    _alloca_probe
0x1800dd682  sub     rsp, rax
0x1800dd685  mov     rax, cs:__security_cookie
0x1800dd68c  xor     rax, rsp
0x1800dd68f  mov     [rbp+1FC0h+var_40], rax
0x1800dd696  xor     r13d, r13d
0x1800dd699  mov     rdi, rcx
0x1800dd69c  mov     eax, r13d
0x1800dd69f  mov     [rsp+20C0h+var_2090], r13
0x1800dd6a4  mov     rcx, r8; void *
0x1800dd6a7  mov     [rsp+20C0h+var_2098], eax
0x1800dd6ab  mov     [rsp+20C0h+var_20A0], eax
0x1800dd6af  mov     r14, r9
0x1800dd6b2  mov     [rsp+20C0h+var_2094], eax
0x1800dd6b6  mov     r15, r8
0x1800dd6b9  mov     [rsp+20C0h+var_209C], eax
0x1800dd6bd  mov     rbx, rdx
0x1800dd6c0  mov     r12d, r13d
0x1800dd6c3  mov     [rsp+20C0h+var_2078], r13
0x1800dd6c8  mov     [rsp+20C0h+var_2070], r13
0x1800dd6cd  mov     [rsp+20C0h+var_2080], r13
0x1800dd6d2  mov     [rsp+20C0h+var_2068], r13
0x1800dd6d7  mov     [rsp+20C0h+var_2060], r13
0x1800dd6dc  mov     [rsp+20C0h+Size], r13
0x1800dd6e1  mov     [rsp+20C0h+var_2088], r13
0x1800dd6e6  mov     [rsp+20C0h+Src], r13
0x1800dd6eb  call    archive_entry_clear
0x1800dd6f0  test    byte ptr [rbx+38h], 4
0x1800dd6f4  lea     rsi, [rbx+4BB0h]
0x1800dd6fb  jnz     short loc_1800DD75B
0x1800dd6fd  xor     edx, edx; Val
0x1800dd6ff  mov     r8d, 770h; Size
0x1800dd705  mov     rcx, rsi; void *
0x1800dd708  call    memset_0
0x1800dd70d  lea     rcx, [rbx+4C28h]
0x1800dd714  call    blake2sp_init
0x1800dd719  test    byte ptr [rbx+2Ch], 1
0x1800dd71d  jz      short loc_1800DD72C
0x1800dd71f  mov     rax, [rbx+78h]
0x1800dd723  add     [rbx+90h], rax
0x1800dd72a  jmp     short loc_1800DD733
0x1800dd72c  mov     [rbx+90h], r13
0x1800dd733  mov     rcx, rbx
0x1800dd736  mov     [rbx+78h], r13
0x1800dd73a  mov     [rbx+80h], r13
0x1800dd741  mov     [rbx+88h], r13
0x1800dd748  mov     [rbx+5308h], r13
0x1800dd74f  mov     [rbx+5310h], r13
0x1800dd756  call    free_filters
0x1800dd75b  test    r14b, 1
0x1800dd75f  jz      short loc_1800DD788
0x1800dd761  xor     r8d, r8d
0x1800dd764  mov     [rsp+20C0h+var_2090], r13
0x1800dd769  lea     rdx, [rsp+20C0h+var_2090]
0x1800dd76e  mov     rcx, rdi
0x1800dd771  call    read_var
0x1800dd776  test    eax, eax
0x1800dd778  jz      loc_1800DDC89
0x1800dd77e  mov     rax, [rsp+20C0h+var_2090]
0x1800dd783  mov     [rsp+20C0h+var_2090], rax
0x1800dd788  and     r14d, 2
0x1800dd78c  jz      short loc_1800DD7B0
0x1800dd78e  xor     r8d, r8d
0x1800dd791  lea     rdx, [rsp+20C0h+var_2078]
0x1800dd796  mov     rcx, rdi
0x1800dd799  call    read_var_sized
0x1800dd79e  test    eax, eax
0x1800dd7a0  jz      loc_1800DDC89
0x1800dd7a6  mov     r12, [rsp+20C0h+var_2078]
0x1800dd7ab  mov     [rsi], r12
0x1800dd7ae  jmp     short loc_1800DD7B3
0x1800dd7b0  mov     [rsi], r13
0x1800dd7b3  xor     r8d, r8d
0x1800dd7b6  lea     rdx, [rsp+20C0h+var_2070]
0x1800dd7bb  mov     rcx, rdi
0x1800dd7be  call    read_var_sized
0x1800dd7c3  test    eax, eax
0x1800dd7c5  jz      loc_1800DDC89
0x1800dd7cb  xor     r8d, r8d
0x1800dd7ce  lea     rdx, [rsp+20C0h+var_2088]
0x1800dd7d3  mov     rcx, rdi
0x1800dd7d6  call    read_var
0x1800dd7db  test    eax, eax
0x1800dd7dd  jz      loc_1800DDC89
0x1800dd7e3  mov     r13, [rsp+20C0h+var_2070]
0x1800dd7e8  mov     sil, 8
0x1800dd7eb  test    sil, r13b
0x1800dd7ee  jz      short loc_1800DD80E
0x1800dd7f0  lea     r8, aFilesWithUnkno; "Files with unknown unpacked size are no"...
0x1800dd7f7  mov     edx, 16h
0x1800dd7fc  mov     rcx, rdi
0x1800dd7ff  call    archive_set_error
0x1800dd804  mov     eax, 0FFFFFFE2h
0x1800dd809  jmp     loc_1800DDC8E
0x1800dd80e  and     byte ptr [rbx+4BD0h], 0F7h
0x1800dd815  xor     eax, eax
0x1800dd817  mov     rcx, r13
0x1800dd81a  and     ecx, 1
0x1800dd81d  cmp     rax, rcx
0x1800dd820  sbb     al, al
0x1800dd822  and     al, sil
0x1800dd825  or      [rbx+4BD0h], al
0x1800dd82b  mov     rax, [rsp+20C0h+var_2088]
0x1800dd830  mov     [rsp+20C0h+var_2088], rax
0x1800dd835  test    rcx, rcx
0x1800dd838  jz      short loc_1800DD84D
0x1800dd83a  test    rax, rax
0x1800dd83d  jnz     short loc_1800DD844
0x1800dd83f  test    r12, r12
0x1800dd842  jz      short loc_1800DD860
0x1800dd844  lea     r8, aDirectoryEntri; "directory entries cannot have any data"
0x1800dd84b  jmp     short loc_1800DD859
0x1800dd84d  test    r14, r14
0x1800dd850  jnz     short loc_1800DD860
0x1800dd852  lea     r8, aNoDataFoundInF; "no data found in file/service block"
0x1800dd859  mov     edx, 2Ah ; '*'
0x1800dd85e  jmp     short loc_1800DD7FC
0x1800dd860  xor     r8d, r8d
0x1800dd863  lea     rdx, [rsp+20C0h+var_2080]
0x1800dd868  mov     rcx, rdi
0x1800dd86b  call    read_var_sized
0x1800dd870  test    eax, eax
0x1800dd872  jz      loc_1800DDC89
0x1800dd878  mov     r12, r13
0x1800dd87b  and     r12d, 2
0x1800dd87f  jz      short loc_1800DD89E
0x1800dd881  lea     rdx, [rsp+20C0h+var_20A0]
0x1800dd886  mov     rcx, rdi
0x1800dd889  call    read_u32
0x1800dd88e  test    al, al
0x1800dd890  jz      loc_1800DDC89
0x1800dd896  mov     eax, [rsp+20C0h+var_20A0]
0x1800dd89a  mov     [rsp+20C0h+var_2098], eax
0x1800dd89e  and     r13d, 4
0x1800dd8a2  jz      short loc_1800DD8C1
0x1800dd8a4  lea     rdx, [rsp+20C0h+var_209C]
0x1800dd8a9  mov     rcx, rdi
0x1800dd8ac  call    read_u32
0x1800dd8b1  test    al, al
0x1800dd8b3  jz      loc_1800DDC89
0x1800dd8b9  mov     eax, [rsp+20C0h+var_209C]
0x1800dd8bd  mov     [rsp+20C0h+var_2094], eax
0x1800dd8c1  xor     r8d, r8d
0x1800dd8c4  lea     rdx, [rsp+20C0h+var_2068]
0x1800dd8c9  mov     rcx, rdi
0x1800dd8cc  call    read_var_sized
0x1800dd8d1  test    eax, eax
0x1800dd8d3  jz      loc_1800DDC89
0x1800dd8d9  mov     rdx, [rsp+20C0h+var_2068]
0x1800dd8de  mov     r10b, [rbx+4BD0h]
0x1800dd8e5  mov     r8, rdx
0x1800dd8e8  shr     r8, 7
0x1800dd8ec  mov     r9d, edx
0x1800dd8ef  and     r8d, 7
0x1800dd8f3  and     r9d, 3Fh
0x1800dd8f7  test    sil, r10b
0x1800dd8fa  jbe     short loc_1800DD900
0x1800dd8fc  xor     esi, esi
0x1800dd8fe  jmp     short loc_1800DD912
0x1800dd900  mov     rcx, rdx
0x1800dd903  mov     esi, 20000h
0x1800dd908  shr     rcx, 0Ah
0x1800dd90c  and     cl, 0Fh
0x1800dd90f  shl     rsi, cl
0x1800dd912  lea     eax, [r9+32h]
0x1800dd916  mov     [rbx+44h], r8d
0x1800dd91a  and     edx, 40h
0x1800dd91d  mov     [rbx+48h], eax
0x1800dd920  setnbe  al
0x1800dd923  and     r10b, 0FEh
0x1800dd927  or      al, r10b
0x1800dd92a  mov     [rbx+4BD0h], al
0x1800dd930  test    rdx, rdx
0x1800dd933  jz      short loc_1800DD94E
0x1800dd935  test    byte ptr [rbx+38h], 10h
0x1800dd939  jnz     short loc_1800DD94E
0x1800dd93b  cmp     qword ptr [rbx+58h], 0
0x1800dd940  jnz     short loc_1800DD94E
0x1800dd942  lea     r8, aDeclaredSolidF; "Declared solid file, but no window buff"...
0x1800dd949  jmp     loc_1800DD859
0x1800dd94e  cmp     rsi, 4000000h
0x1800dd955  ja      loc_1800DDC7D
0x1800dd95b  test    al, 8
0x1800dd95d  jnz     short loc_1800DD968
0x1800dd95f  test    rsi, rsi
0x1800dd962  jz      loc_1800DDC7D
0x1800dd968  test    al, 1
0x1800dd96a  jbe     short loc_1800DD989
0x1800dd96c  mov     rax, [rbx+5318h]
0x1800dd973  test    rax, rax
0x1800dd976  jle     short loc_1800DD98D
0x1800dd978  cmp     rax, rsi
0x1800dd97b  jz      short loc_1800DD98D
0x1800dd97d  lea     r8, aWindowSizeForT; "Window size for this solid file doesn't"...
0x1800dd984  jmp     loc_1800DD859
0x1800dd989  and     byte ptr [rbx+38h], 0EFh
0x1800dd98d  cmp     [rbx+50h], rsi
0x1800dd991  jge     short loc_1800DD9CE
0x1800dd993  cmp     qword ptr [rbx+58h], 0
0x1800dd998  jz      short loc_1800DD9CE
0x1800dd99a  xor     edx, edx; Val
0x1800dd99c  lea     rcx, [rbx+4B70h]; void *
0x1800dd9a3  lea     r8d, [rdx+40h]; Size
0x1800dd9a7  call    memset_0
0x1800dd9ac  mov     rcx, [rbx+58h]
0x1800dd9b0  mov     rdx, rsi
0x1800dd9b3  call    cs:__imp__o_realloc
0x1800dd9b9  test    rax, rax
0x1800dd9bc  jnz     short loc_1800DD9CA
0x1800dd9be  lea     r8, aNotEnoughMemor; "Not enough memory when trying to reallo"...
0x1800dd9c5  jmp     loc_1800DD7F7
0x1800dd9ca  mov     [rbx+58h], rax
0x1800dd9ce  mov     al, [rbx+4BD0h]
0x1800dd9d4  mov     [rbx+50h], rsi
0x1800dd9d8  test    al, 1
0x1800dd9da  jbe     short loc_1800DD9ED
0x1800dd9dc  cmp     qword ptr [rbx+5318h], 0
0x1800dd9e4  jnz     short loc_1800DD9ED
0x1800dd9e6  mov     [rbx+5318h], rsi
0x1800dd9ed  test    rsi, rsi
0x1800dd9f0  jz      short loc_1800DD9F5
0x1800dd9f2  dec     rsi
0x1800dd9f5  and     al, 0FDh
0x1800dd9f7  mov     [rbx+70h], rsi
0x1800dd9fb  xor     r8d, r8d
0x1800dd9fe  mov     [rbx+4BD0h], al
0x1800dda04  lea     rdx, [rsp+20C0h+var_2060]
0x1800dda09  mov     rcx, rdi
0x1800dda0c  call    read_var_sized
0x1800dda11  test    eax, eax
0x1800dda13  jz      loc_1800DDC89
0x1800dda19  mov     r9, [rsp+20C0h+var_2060]
0x1800dda1e  test    r9, r9
0x1800dda21  jnz     loc_1800DDAFC
0x1800dda27  mov     r14, [rsp+20C0h+var_2080]
0x1800dda2c  test    r14b, 10h
0x1800dda30  jz      short loc_1800DDA4A
0x1800dda32  mov     rax, r14
0x1800dda35  mov     ecx, 80h
0x1800dda3a  shl     rax, 7
0x1800dda3e  not     ax
0x1800dda41  and     ax, cx
0x1800dda44  or      ax, 416Dh
0x1800dda48  jmp     short loc_1800DDA5A
0x1800dda4a  mov     eax, 8124h
0x1800dda4f  test    r14b, 1
0x1800dda53  jnz     short loc_1800DDA5A
0x1800dda55  mov     eax, 81A4h
0x1800dda5a  or      dword ptr [r15+0A0h], 600h
0x1800dda65  mov     dword ptr [r15+10h], 0
0x1800dda6d  mov     [r15+408h], ax
0x1800dda75  test    r14b, 7
0x1800dda79  jz      loc_1800DDB26
0x1800dda7f  mov     ecx, 16h; Size
0x1800dda84  call    cs:__imp_malloc
0x1800dda8a  mov     rsi, rax
0x1800dda8d  test    rax, rax
0x1800dda90  jz      loc_1800DDB26
0x1800dda96  test    r14b, 1
0x1800dda9a  jz      short loc_1800DDAAF
0x1800dda9c  mov     rax, 796C6E6F64722Ch
0x1800ddaa6  lea     rcx, [rsi+7]
0x1800ddaaa  mov     [rsi], rax
0x1800ddaad  jmp     short loc_1800DDAB2
0x1800ddaaf  mov     rcx, rsi
0x1800ddab2  test    r14b, 2
0x1800ddab6  jz      short loc_1800DDAC9
0x1800ddab8  mov     rax, 6E65646469682Ch
0x1800ddac2  mov     [rcx], rax
0x1800ddac5  add     rcx, 7
0x1800ddac9  test    r14b, 4
0x1800ddacd  jz      short loc_1800DDAE0
0x1800ddacf  mov     rax, 6D65747379732Ch
0x1800ddad9  mov     [rcx], rax
0x1800ddadc  add     rcx, 7
0x1800ddae0  cmp     rcx, rsi
0x1800ddae3  jbe     short loc_1800DDAF1
0x1800ddae5  lea     rdx, [rsi+1]
0x1800ddae9  mov     rcx, r15
0x1800ddaec  call    archive_entry_copy_fflags_text
0x1800ddaf1  mov     rcx, rsi; Block
0x1800ddaf4  call    cs:__imp_free
0x1800ddafa  jmp     short loc_1800DDB26
0x1800ddafc  cmp     r9, 1
0x1800ddb00  jnz     loc_1800DDC64
0x1800ddb06  movzx   eax, word ptr [rsp+20C0h+var_2080]
0x1800ddb0b  or      dword ptr [r15+0A0h], 600h
0x1800ddb16  mov     [r15+408h], ax
0x1800ddb1e  mov     dword ptr [r15+10h], 0
0x1800ddb26  xor     r8d, r8d
  ... truncated ...
```
