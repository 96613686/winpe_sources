# SetMultiStringValue(tagPROPVARIANT * *,ulong,wchar_t const * *)

- ea: `0x1800289a4`
- end: `0x180028ad1`
- name: `?SetMultiStringValue@@YAJPEAPEAUtagPROPVARIANT@@KPEAPEB_W@Z`
- size: `301`
- prototype: `__int64 __fastcall(LPVOID *, unsigned int, const wchar_t **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023ba0`
- `0x180026f00`

## callees

- `0x18000306c`
- `0x180008a9c`
- `0x1800289a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800289c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800289f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028a44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800289c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800289f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028a44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028a86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028a95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028a9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028a86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028a95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028a9e`

## pseudocode

```c
__int64 __fastcall SetMultiStringValue(LPVOID *a1, unsigned int a2, const wchar_t **a3)
{
  __int64 v4; // rbp
  struct tagPROPVARIANT *v6; // rax
  BYTE *v8; // rax
  BYTE *v9; // r14
  unsigned int v10; // ebx
  unsigned int v11; // esi
  __int64 v12; // r15
  __int64 v13; // rax
  unsigned __int64 v14; // rbx
  wchar_t *v15; // rax
  int v16; // eax
  __int64 v17; // r11
  unsigned int i; // esi
  void *v19; // rcx

  v4 = a2;
  v6 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
  *a1 = v6;
  if ( !v6 )
    return 2147942414LL;
  *(_OWORD *)&v6->vt = 0;
  v6->bstrblobVal.pData = 0;
  v8 = (BYTE *)CoTaskMemAlloc(8 * v4);
  v9 = v8;
  if ( v8 )
  {
    v10 = 0;
    memset_0(v8, 0, 8 * v4);
    v11 = 0;
    while ( 1 )
    {
      if ( v11 >= (unsigned int)v4 )
      {
        *(_WORD *)*a1 = 4127;
        *((_DWORD *)*a1 + 2) = v4;
        *((_QWORD *)*a1 + 2) = v9;
        return v10;
      }
      v12 = v11;
      v13 = -1;
      do
        ++v13;
      while ( a3[v11][v13] );
      v14 = (int)v13 + 1;
      v15 = (wchar_t *)CoTaskMemAlloc(2 * v14);
      if ( !v15 )
        break;
      v16 = StringCchCopyW(v15, v14, a3[v11++]);
      *(_QWORD *)&v9[8 * v12] = v17;
      v10 = v16;
      if ( v16 < 0 )
        goto LABEL_13;
    }
    v10 = -2147024882;
LABEL_13:
    for ( i = 0; i < (unsigned int)v4; ++i )
    {
      v19 = *(void **)&v9[8 * i];
      if ( v19 )
        CoTaskMemFree(v19);
    }
    CoTaskMemFree(v9);
  }
  else
  {
    v10 = -2147024882;
  }
  CoTaskMemFree(*a1);
  *a1 = 0;
  return v10;
}

```

## disassembly

```asm
0x1800289a4  push    rbx
0x1800289a6  push    rbp
0x1800289a7  push    rsi
0x1800289a8  push    rdi
0x1800289a9  push    r12
0x1800289ab  push    r13
0x1800289ad  push    r14
0x1800289af  push    r15
0x1800289b1  sub     rsp, 28h
0x1800289b5  mov     rdi, rcx
0x1800289b8  mov     ebp, edx
0x1800289ba  mov     ecx, 18h; cb
0x1800289bf  mov     r12, r8
0x1800289c2  call    cs:__imp_CoTaskMemAlloc
0x1800289c8  xor     r13d, r13d
0x1800289cb  mov     [rdi], rax
0x1800289ce  test    rax, rax
0x1800289d1  jnz     short loc_1800289DD
0x1800289d3  mov     eax, 8007000Eh
0x1800289d8  jmp     loc_180028AC0
0x1800289dd  xor     ecx, ecx
0x1800289df  xorps   xmm0, xmm0
0x1800289e2  movups  xmmword ptr [rax], xmm0
0x1800289e5  mov     [rax+10h], rcx
0x1800289e9  mov     rsi, rbp
0x1800289ec  shl     rsi, 3
0x1800289f0  mov     rcx, rsi; cb
0x1800289f3  call    cs:__imp_CoTaskMemAlloc
0x1800289f9  mov     r14, rax
0x1800289fc  test    rax, rax
0x1800289ff  jnz     short loc_180028A0B
0x180028a01  mov     ebx, 8007000Eh
0x180028a06  jmp     loc_180028A9B
0x180028a0b  mov     r8, rsi; Size
0x180028a0e  xor     edx, edx; Val
0x180028a10  mov     rcx, r14; void *
0x180028a13  mov     ebx, r13d
0x180028a16  call    memset_0
0x180028a1b  mov     esi, r13d
0x180028a1e  cmp     esi, ebp
0x180028a20  jnb     loc_180028AA9
0x180028a26  mov     r15d, esi
0x180028a29  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028a2d  mov     rcx, [r12+r15*8]
0x180028a31  inc     rax
0x180028a34  cmp     [rcx+rax*2], r13w
0x180028a39  jnz     short loc_180028A31
0x180028a3b  inc     eax
0x180028a3d  movsxd  rbx, eax
0x180028a40  lea     rcx, [rbx+rbx]; cb
0x180028a44  call    cs:__imp_CoTaskMemAlloc
0x180028a4a  mov     r11, rax
0x180028a4d  test    rax, rax
0x180028a50  jz      short loc_180028A6F
0x180028a52  mov     r8, [r12+r15*8]; wchar_t *
0x180028a56  mov     rdx, rbx; unsigned __int64
0x180028a59  mov     rcx, rax; wchar_t *
0x180028a5c  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180028a61  inc     esi
0x180028a63  mov     [r14+r15*8], r11
0x180028a67  mov     ebx, eax
0x180028a69  test    eax, eax
0x180028a6b  jns     short loc_180028A1E
0x180028a6d  jmp     short loc_180028A74
0x180028a6f  mov     ebx, 8007000Eh
0x180028a74  mov     esi, r13d
0x180028a77  test    ebp, ebp
0x180028a79  jz      short loc_180028A92
0x180028a7b  mov     eax, esi
0x180028a7d  mov     rcx, [r14+rax*8]; pv
0x180028a81  test    rcx, rcx
0x180028a84  jz      short loc_180028A8C
0x180028a86  call    cs:__imp_CoTaskMemFree
0x180028a8c  inc     esi
0x180028a8e  cmp     esi, ebp
0x180028a90  jb      short loc_180028A7B
0x180028a92  mov     rcx, r14; pv
0x180028a95  call    cs:__imp_CoTaskMemFree
0x180028a9b  mov     rcx, [rdi]; pv
0x180028a9e  call    cs:__imp_CoTaskMemFree
0x180028aa4  mov     [rdi], r13
0x180028aa7  jmp     short loc_180028ABE
0x180028aa9  mov     rcx, [rdi]
0x180028aac  mov     word ptr [rcx], 101Fh
0x180028ab1  mov     rcx, [rdi]
0x180028ab4  mov     [rcx+8], ebp
0x180028ab7  mov     rcx, [rdi]
0x180028aba  mov     [rcx+10h], r14
0x180028abe  mov     eax, ebx
0x180028ac0  add     rsp, 28h
0x180028ac4  pop     r15
0x180028ac6  pop     r14
0x180028ac8  pop     r13
0x180028aca  pop     r12
0x180028acc  pop     rdi
0x180028acd  pop     rsi
0x180028ace  pop     rbp
0x180028acf  pop     rbx
0x180028ad0  retn
```
