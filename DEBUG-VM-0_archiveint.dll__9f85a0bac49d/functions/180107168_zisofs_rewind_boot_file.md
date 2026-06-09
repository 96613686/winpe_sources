# zisofs_rewind_boot_file

- ea: `0x180107168`
- end: `0x1801073f2`
- name: `zisofs_rewind_boot_file`
- size: `650`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800ffae0`

## callees

- `0x180006c00`
- `0x18000eafc`
- `0x180015810`
- `0x180105460`
- `0x180106980`
- `0x180107168`
- `0x1801172fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801073d4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801073d4`
- `api-ms-win-crt-private-l1-1-0!_o__lseeki64` at `0x18010727d`
- `api-ms-win-crt-private-l1-1-0!_o__lseeki64` at `0x18010729a`
- `api-ms-win-crt-private-l1-1-0!_o__lseeki64` at `0x1801072db`
- `api-ms-win-crt-private-l1-1-0!_o__lseeki64` at `0x18010727d`
- `api-ms-win-crt-private-l1-1-0!_o__lseeki64` at `0x18010729a`
- `api-ms-win-crt-private-l1-1-0!_o__lseeki64` at `0x1801072db`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180107381`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010738c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180107381`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010738c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18010722f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18010722f`

## string_xrefs

- `0x1801073aa`: `Failed to clean up compressor`
- `0x1801073dd`: `Can't read temporary file(%jd)`

## pseudocode

```c
__int64 __fastcall zisofs_rewind_boot_file(__int64 a1)
{
  __int64 v1; // r13
  __int64 v3; // rdi
  unsigned __int64 v5; // r14
  __int64 v6; // r12
  size_t v7; // rax
  void *v8; // r15
  unsigned int v9; // ebx
  unsigned __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // r15
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  unsigned int *v17; // rax
  __int64 v18; // [rsp+20h] [rbp-108h]
  __int64 v19; // [rsp+28h] [rbp-100h]
  _DWORD v20[2]; // [rsp+30h] [rbp-F8h] BYREF
  __int64 v21; // [rsp+38h] [rbp-F0h]
  void *v22; // [rsp+50h] [rbp-D8h]
  _BYTE v23[88]; // [rsp+78h] [rbp-B0h] BYREF
  int v24; // [rsp+D0h] [rbp-58h]
  int FileHandle; // [rsp+130h] [rbp+8h]
  __int64 Offset; // [rsp+138h] [rbp+10h]
  void *Block; // [rsp+140h] [rbp+18h]
  size_t v28; // [rsp+148h] [rbp+20h]

  v1 = *(_QWORD *)(a1 + 248);
  v20[1] = 0;
  memset_0(v20, 0, 0xA4u);
  v3 = *(_QWORD *)(*(_QWORD *)(v1 + 66344) + 24LL);
  if ( !*(_BYTE *)(v3 + 192) )
    return 0;
  memset_0(v20, 0, 0xA8u);
  v21 = *(unsigned int *)(v3 + 196);
  v20[0] = *(unsigned __int8 *)(v3 + 193);
  v5 = *(_QWORD *)(v3 + 152);
  v6 = *(_QWORD *)(v1 + 66264);
  FileHandle = *(_DWORD *)(v1 + 8);
  v19 = *(_QWORD *)(v1 + 66248);
  Offset = *(_QWORD *)(v3 + 144);
  v7 = v5;
  if ( v5 > 0x8000 )
    v7 = 0x8000;
  v28 = v7;
  Block = malloc(v7);
  v8 = Block;
  if ( Block )
  {
    v9 = 0;
    while ( v5 )
    {
      v18 = _lseeki64(FileHandle, 0, 1);
      _lseeki64(FileHandle, Offset, 0);
      v10 = v5;
      if ( v28 <= v5 )
        v10 = v28;
      v12 = _la_read(*(_DWORD *)(v1 + 8), v8, v10);
      if ( v12 <= 0 )
      {
        v17 = (unsigned int *)_o__errno(v11);
        archive_set_error(a1, *v17, "Can't read temporary file(%jd)", v12);
        v9 = -30;
        goto LABEL_17;
      }
      _lseeki64(FileHandle, v18, 0);
      v13 = zisofs_extract(a1, (__int64)v20, (__int64)Block, v12);
      if ( v13 < 0 )
      {
        v9 = v13;
        if ( (_DWORD)v13 )
          goto LABEL_17;
        break;
      }
      v5 -= v12;
      Offset += v12;
      v8 = Block;
    }
    v14 = *(unsigned int *)(v3 + 196);
    v15 = *(_QWORD *)(v3 + 32);
    *(_QWORD *)(v3 + 152) = v14;
    *(_QWORD *)(v3 + 144) = v6 - v19 + 0x10000;
    *(_DWORD *)(v15 + 160) |= 0x40u;
    *(_DWORD *)(v15 + 16) = 0;
    *(_QWORD *)(v15 + 112) = v14;
    v16 = *(_QWORD *)(v3 + 152);
    *(_WORD *)(v3 + 192) = 0;
    *(_DWORD *)(v3 + 196) = 0;
    if ( (int)wb_write_padding_to_temp(a1, v16) < 0 )
      v9 = -30;
LABEL_17:
    free(Block);
    free(v22);
    if ( v24 )
    {
      if ( (unsigned int)inflateEnd(v23) )
      {
        archive_set_error(a1, 0xFFFFFFFFLL, "Failed to clean up compressor");
        return (unsigned int)-30;
      }
    }
    return v9;
  }
  else
  {
    archive_set_error(a1, 12, "Can't allocate memory");
    return 4294967266LL;
  }
}

```

## disassembly

```asm
0x180107168  push    rbx
0x18010716a  push    rbp
0x18010716b  push    rsi
0x18010716c  push    rdi
0x18010716d  push    r12
0x18010716f  push    r13
0x180107171  push    r14
0x180107173  push    r15
0x180107175  sub     rsp, 0E8h
0x18010717c  mov     r13, [rcx+0F8h]
0x180107183  mov     rsi, rcx
0x180107186  xor     eax, eax
0x180107188  lea     rcx, [rsp+128h+var_F8]; void *
0x18010718d  xor     edx, edx; Val
0x18010718f  mov     [rsp+128h+var_F4], eax
0x180107193  mov     r8d, 0A4h; Size
0x180107199  call    memset_0
0x18010719e  mov     rax, [r13+10328h]
0x1801071a5  mov     rdi, [rax+18h]
0x1801071a9  cmp     byte ptr [rdi+0C0h], 0
0x1801071b0  jnz     short loc_1801071B9
0x1801071b2  xor     eax, eax
0x1801071b4  jmp     loc_1801073C0
0x1801071b9  xor     edx, edx; Val
0x1801071bb  lea     rcx, [rsp+128h+var_F8]; void *
0x1801071c0  mov     r8d, 0A8h; Size
0x1801071c6  call    memset_0
0x1801071cb  mov     eax, [rdi+0C4h]
0x1801071d1  mov     ecx, 8000h
0x1801071d6  mov     [rsp+128h+var_F0], rax
0x1801071db  movzx   eax, byte ptr [rdi+0C1h]
0x1801071e2  mov     [rsp+128h+var_F8], eax
0x1801071e6  mov     eax, [r13+8]
0x1801071ea  mov     r14, [rdi+98h]
0x1801071f1  mov     r12, [r13+102D8h]
0x1801071f8  cmp     r14, rcx
0x1801071fb  mov     [rsp+128h+FileHandle], eax
0x180107202  mov     rax, [r13+102C8h]
0x180107209  mov     [rsp+128h+var_100], rax
0x18010720e  mov     rax, [rdi+90h]
0x180107215  mov     [rsp+128h+Offset], rax
0x18010721d  mov     rax, r14
0x180107220  cmova   rax, rcx
0x180107224  mov     rcx, rax; Size
0x180107227  mov     [rsp+128h+arg_18], rax
0x18010722f  call    cs:__imp_malloc
0x180107235  mov     [rsp+128h+Block], rax
0x18010723d  mov     r15, rax
0x180107240  test    rax, rax
0x180107243  jnz     short loc_180107260
0x180107245  lea     r8, aCanTAllocateMe_30; "Can't allocate memory"
0x18010724c  mov     rcx, rsi
0x18010724f  lea     edx, [rax+0Ch]
0x180107252  call    archive_set_error
0x180107257  lea     eax, [r15-1Eh]
0x18010725b  jmp     loc_1801073C0
0x180107260  xor     ebx, ebx
0x180107262  mov     ebp, 0FFFFFFE2h
0x180107267  test    r14, r14
0x18010726a  jz      loc_18010731C
0x180107270  mov     ecx, [rsp+128h+FileHandle]; FileHandle
0x180107277  lea     r8d, [rbp+1Fh]; Origin
0x18010727b  xor     edx, edx; Offset
0x18010727d  call    cs:__imp__lseeki64
0x180107283  mov     rdx, [rsp+128h+Offset]; Offset
0x18010728b  xor     r8d, r8d; Origin
0x18010728e  mov     ecx, [rsp+128h+FileHandle]; FileHandle
0x180107295  mov     [rsp+128h+var_108], rax
0x18010729a  call    cs:__imp__lseeki64
0x1801072a0  cmp     [rsp+128h+arg_18], r14
0x1801072a8  mov     r8, r14
0x1801072ab  mov     ecx, [r13+8]
0x1801072af  mov     rdx, r15
0x1801072b2  cmovbe  r8, [rsp+128h+arg_18]
0x1801072bb  call    __la_read
0x1801072c0  mov     r15, rax
0x1801072c3  test    rax, rax
0x1801072c6  jle     loc_1801073D4
0x1801072cc  mov     rdx, [rsp+128h+var_108]; Offset
0x1801072d1  xor     r8d, r8d; Origin
0x1801072d4  mov     ecx, [rsp+128h+FileHandle]; FileHandle
0x1801072db  call    cs:__imp__lseeki64
0x1801072e1  mov     r8, [rsp+128h+Block]
0x1801072e9  lea     rdx, [rsp+128h+var_F8]
0x1801072ee  mov     r9, r15
0x1801072f1  mov     rcx, rsi
0x1801072f4  call    zisofs_extract
0x1801072f9  test    rax, rax
0x1801072fc  js      short loc_180107316
0x1801072fe  sub     r14, r15
0x180107301  add     [rsp+128h+Offset], r15
0x180107309  mov     r15, [rsp+128h+Block]
0x180107311  jmp     loc_180107262
0x180107316  mov     ebx, eax
0x180107318  test    eax, eax
0x18010731a  jnz     short loc_180107379
0x18010731c  mov     eax, [rdi+0C4h]
0x180107322  mov     rcx, [rdi+20h]
0x180107326  sub     r12, [rsp+128h+var_100]
0x18010732b  mov     [rdi+98h], rax
0x180107332  add     r12, 10000h
0x180107339  mov     [rdi+90h], r12
0x180107340  or      dword ptr [rcx+0A0h], 40h
0x180107347  mov     dword ptr [rcx+10h], 0
0x18010734e  mov     [rcx+70h], rax
0x180107352  mov     rcx, rsi
0x180107355  mov     rdx, [rdi+98h]
0x18010735c  mov     word ptr [rdi+0C0h], 0
0x180107365  mov     dword ptr [rdi+0C4h], 0
0x18010736f  call    wb_write_padding_to_temp
0x180107374  test    eax, eax
0x180107376  cmovs   ebx, ebp
0x180107379  mov     rcx, [rsp+128h+Block]; Block
0x180107381  call    cs:__imp_free
0x180107387  mov     rcx, [rsp+128h+var_D8]; Block
0x18010738c  call    cs:__imp_free
0x180107392  cmp     [rsp+128h+var_58], 0
0x18010739a  jz      short loc_1801073BE
0x18010739c  lea     rcx, [rsp+128h+var_B0]
0x1801073a1  call    inflateEnd
0x1801073a6  test    eax, eax
0x1801073a8  jz      short loc_1801073BE
0x1801073aa  lea     r8, aFailedToCleanU_1; "Failed to clean up compressor"
0x1801073b1  or      edx, 0FFFFFFFFh
0x1801073b4  mov     rcx, rsi
0x1801073b7  call    archive_set_error
0x1801073bc  mov     ebx, ebp
0x1801073be  mov     eax, ebx
0x1801073c0  add     rsp, 0E8h
0x1801073c7  pop     r15
0x1801073c9  pop     r14
0x1801073cb  pop     r13
0x1801073cd  pop     r12
0x1801073cf  pop     rdi
0x1801073d0  pop     rsi
0x1801073d1  pop     rbp
0x1801073d2  pop     rbx
0x1801073d3  retn
0x1801073d4  call    cs:__imp__o__errno
0x1801073da  mov     r9, r15
0x1801073dd  lea     r8, aCanTReadTempor; "Can't read temporary file(%jd)"
0x1801073e4  mov     rcx, rsi
0x1801073e7  mov     edx, [rax]
0x1801073e9  call    archive_set_error
0x1801073ee  mov     ebx, ebp
0x1801073f0  jmp     short loc_180107379
```
