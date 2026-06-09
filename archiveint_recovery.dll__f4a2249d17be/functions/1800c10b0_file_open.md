# file_open

- ea: `0x1800c10b0`
- end: `0x1800c12ab`
- name: `file_open`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800c1360`

## callees

- `0x180006c00`
- `0x1800bb790`
- `0x1800c10b0`
- `0x1800eef10`
- `0x1800ef164`
- `0x1800ef3f8`
- `0x1800ef5d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c114d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c1187`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c11c0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c11d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c114d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c1187`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c11c0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c11d9`
- `api-ms-win-crt-private-l1-1-0!_o__setmode` at `0x1800c10fb`
- `api-ms-win-crt-private-l1-1-0!_o__setmode` at `0x1800c10fb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c11b2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c11b2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800c1246`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800c1246`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x1800c1271`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x1800c1271`

## string_xrefs

- `0x1800c1153`: `Failed to open '%s'`
- `0x1800c11c6`: `Failed to open '%ls'`

## pseudocode

```c
__int64 __fastcall file_open(__int64 a1, __int64 a2, __int16 a3)
{
  const WCHAR *v3; // r12
  int v6; // edi
  const WCHAR *v7; // r15
  __int64 v8; // rcx
  const char *v9; // rbx
  const WCHAR *v10; // rsi
  const CHAR *v11; // rcx
  __int64 v12; // rcx
  unsigned int *v13; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  wchar_t *v17; // rax
  __int16 v18; // r8
  wchar_t *v19; // r13
  unsigned int *v20; // rax
  unsigned int *v21; // rax
  void *v22; // rax

  v3 = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 36) = 0;
  if ( !*(_DWORD *)(a2 + 44) )
  {
    v6 = 0;
    _setmode(0, 0x8000);
    v7 = (const WCHAR *)&unk_18012277F;
    goto LABEL_3;
  }
  v10 = (const WCHAR *)(a2 + 48);
  v11 = (const CHAR *)(a2 + 48);
  if ( *(_DWORD *)(a2 + 44) == 1 )
  {
    v6 = _la_open(v11, 0x8000u, a3);
    if ( v6 < 0 )
    {
      v13 = (unsigned int *)_o__errno(v12);
      archive_set_error(a1, *v13, "Failed to open '%s'", v10);
      return 4294967266LL;
    }
    v7 = v10;
  }
  else
  {
    v7 = 0;
    v3 = (const WCHAR *)(a2 + 48);
    v6 = _la_wopen((LPCWSTR)v11, 0x8000u, a3);
    if ( v6 < 0 )
    {
      if ( *(_DWORD *)_o__errno(v15) != 2
        || (v17 = _la_win_permissive_name_w(v10), (v19 = v17) == 0)
        || (v6 = _la_wopen(v17, 0x8000u, v18), free(v19), v6 < 0) )
      {
        v20 = (unsigned int *)_o__errno(v16);
        archive_set_error(a1, *v20, "Failed to open '%ls'", v10);
        return 4294967266LL;
      }
    }
  }
LABEL_3:
  if ( (unsigned int)_la_seek_fstat(v6) )
  {
    if ( *(_DWORD *)(a2 + 44) == 2 )
    {
      v9 = "Can't stat '%ls'";
    }
    else
    {
      v9 = "Can't stat '%s'";
      v3 = v7;
    }
    v21 = (unsigned int *)_o__errno(v8);
    archive_set_error(a1, *v21, v9, v3, 0);
    goto LABEL_20;
  }
  v22 = malloc(*(_QWORD *)(a2 + 8));
  if ( !v22 )
  {
    archive_set_error(a1, 12, "No memory");
LABEL_20:
    if ( (unsigned int)(v6 + 1) > 1 )
      _o__close((unsigned int)v6);
    return 4294967266LL;
  }
  *(_QWORD *)(a2 + 16) = v22;
  *(_DWORD *)a2 = v6;
  *(_WORD *)(a2 + 24) = 0;
  return 0;
}

```

## disassembly

```asm
0x1800c10b0  push    rbx
0x1800c10b2  push    rbp
0x1800c10b3  push    rsi
0x1800c10b4  push    rdi
0x1800c10b5  push    r12
0x1800c10b7  push    r13
0x1800c10b9  push    r14
0x1800c10bb  push    r15
0x1800c10bd  sub     rsp, 58h
0x1800c10c1  xor     r12d, r12d
0x1800c10c4  xorps   xmm0, xmm0
0x1800c10c7  mov     [rcx+38h], r12
0x1800c10cb  mov     rbx, rdx
0x1800c10ce  mov     [rcx+28h], r12
0x1800c10d2  mov     rbp, rcx
0x1800c10d5  mov     [rcx+24h], r12d
0x1800c10d9  mov     r14d, 8000h
0x1800c10df  movups  [rsp+98h+var_78], xmm0
0x1800c10e4  movups  [rsp+98h+var_68], xmm0
0x1800c10e9  movups  [rsp+98h+var_58], xmm0
0x1800c10ee  cmp     [rdx+2Ch], r12d
0x1800c10f2  jnz     short loc_1800C1132
0x1800c10f4  xor     edi, edi
0x1800c10f6  mov     edx, r14d; Mode
0x1800c10f9  xor     ecx, ecx; FileHandle
0x1800c10fb  call    cs:__imp__setmode
0x1800c1101  lea     r15, unk_18012277F
0x1800c1108  lea     rdx, [rsp+98h+var_78]
0x1800c110d  mov     ecx, edi; FileHandle
0x1800c110f  call    __la_seek_fstat
0x1800c1114  test    eax, eax
0x1800c1116  jz      loc_1800C11F1
0x1800c111c  cmp     dword ptr [rbx+2Ch], 2
0x1800c1120  jnz     loc_1800C11CF
0x1800c1126  lea     rbx, aCanTStatLs; "Can't stat '%ls'"
0x1800c112d  jmp     loc_1800C11D9
0x1800c1132  cmp     dword ptr [rdx+2Ch], 1
0x1800c1136  lea     rsi, [rdx+30h]
0x1800c113a  mov     rcx, rsi; lpFileName
0x1800c113d  mov     edx, r14d
0x1800c1140  jnz     short loc_1800C1176
0x1800c1142  call    __la_open
0x1800c1147  mov     edi, eax
0x1800c1149  test    eax, eax
0x1800c114b  jns     short loc_1800C1171
0x1800c114d  call    cs:__imp__o__errno
0x1800c1153  lea     r8, aFailedToOpenS; "Failed to open '%s'"
0x1800c115a  mov     edx, [rax]
0x1800c115c  mov     r9, rsi
0x1800c115f  mov     rcx, rbp
0x1800c1162  call    archive_set_error
0x1800c1167  mov     eax, 0FFFFFFE2h
0x1800c116c  jmp     loc_1800C129A
0x1800c1171  mov     r15, rsi
0x1800c1174  jmp     short loc_1800C1108
0x1800c1176  xor     r15d, r15d
0x1800c1179  mov     r12, rsi
0x1800c117c  call    __la_wopen
0x1800c1181  mov     edi, eax
0x1800c1183  test    eax, eax
0x1800c1185  jns     short loc_1800C1108
0x1800c1187  call    cs:__imp__o__errno
0x1800c118d  cmp     dword ptr [rax], 2
0x1800c1190  jnz     short loc_1800C11C0
0x1800c1192  mov     rcx, rsi; lpFileName
0x1800c1195  call    __la_win_permissive_name_w
0x1800c119a  mov     r13, rax
0x1800c119d  test    rax, rax
0x1800c11a0  jz      short loc_1800C11C0
0x1800c11a2  mov     edx, r14d
0x1800c11a5  mov     rcx, rax; lpFileName
0x1800c11a8  call    __la_wopen
0x1800c11ad  mov     rcx, r13; Block
0x1800c11b0  mov     edi, eax
0x1800c11b2  call    cs:__imp_free
0x1800c11b8  test    edi, edi
0x1800c11ba  jns     loc_1800C1108
0x1800c11c0  call    cs:__imp__o__errno
0x1800c11c6  lea     r8, aFailedToOpenLs; "Failed to open '%ls'"
0x1800c11cd  jmp     short loc_1800C115A
0x1800c11cf  lea     rbx, aCanTStatS; "Can't stat '%s'"
0x1800c11d6  mov     r12, r15
0x1800c11d9  call    cs:__imp__o__errno
0x1800c11df  mov     r9, r12
0x1800c11e2  mov     r8, rbx
0x1800c11e5  mov     rcx, rbp
0x1800c11e8  mov     edx, [rax]
0x1800c11ea  call    archive_set_error
0x1800c11ef  jmp     short loc_1800C1263
0x1800c11f1  movzx   esi, word ptr [rsp+98h+var_78+0Ah]
0x1800c11f6  mov     ecx, 0F000h
0x1800c11fb  movzx   eax, si
0x1800c11fe  xor     r15d, r15d
0x1800c1201  and     ax, cx
0x1800c1204  cmp     ax, r14w
0x1800c1208  jnz     short loc_1800C1242
0x1800c120a  movzx   r8d, word ptr [rsp+98h+var_78+8]
0x1800c1210  mov     rcx, rbp
0x1800c1213  mov     edx, dword ptr [rsp+98h+var_58+4]
0x1800c1217  call    archive_read_extract_set_skip_file
0x1800c121c  mov     eax, 10000h
0x1800c1221  mov     r15d, 1
0x1800c1227  cmp     [rbx+8], rax
0x1800c122b  jbe     short loc_1800C123E
0x1800c122d  cmp     rax, 4000000h
0x1800c1233  jnb     short loc_1800C123E
0x1800c1235  add     rax, rax
0x1800c1238  cmp     rax, [rbx+8]
0x1800c123c  jb      short loc_1800C122D
0x1800c123e  mov     [rbx+8], rax
0x1800c1242  mov     rcx, [rbx+8]; Size
0x1800c1246  call    cs:__imp_malloc
0x1800c124c  test    rax, rax
0x1800c124f  jnz     short loc_1800C127C
0x1800c1251  lea     r8, aNoMemory_0; "No memory"
0x1800c1258  mov     rcx, rbp
0x1800c125b  lea     edx, [rax+0Ch]
0x1800c125e  call    archive_set_error
0x1800c1263  lea     eax, [rdi+1]
0x1800c1266  cmp     eax, 1
0x1800c1269  jbe     loc_1800C1167
0x1800c126f  mov     ecx, edi
0x1800c1271  call    cs:__imp__o__close
0x1800c1277  jmp     loc_1800C1167
0x1800c127c  mov     [rbx+10h], rax
0x1800c1280  mov     [rbx], edi
0x1800c1282  mov     [rbx+18h], si
0x1800c1286  test    r15d, r15d
0x1800c1289  jz      short loc_1800C1298
0x1800c128b  mov     rax, qword ptr [rsp+98h+var_68+8]
0x1800c1290  mov     [rbx+20h], rax
0x1800c1294  mov     byte ptr [rbx+28h], 1
0x1800c1298  xor     eax, eax
0x1800c129a  add     rsp, 58h
0x1800c129e  pop     r15
0x1800c12a0  pop     r14
0x1800c12a2  pop     r13
0x1800c12a4  pop     r12
0x1800c12a6  pop     rdi
0x1800c12a7  pop     rsi
0x1800c12a8  pop     rbp
0x1800c12a9  pop     rbx
0x1800c12aa  retn
```
