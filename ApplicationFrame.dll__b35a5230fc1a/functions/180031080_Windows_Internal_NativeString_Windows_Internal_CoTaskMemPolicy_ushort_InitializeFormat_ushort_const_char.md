# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,char *)

- ea: `0x180031080`
- end: `0x180031291`
- name: `?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGPEAD@Z`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180063684`

## callees

- `0x18001e260`
- `0x18002e020`
- `0x180031080`
- `0x180044708`
- `0x1800532a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x180031216`
- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x180031216`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x180031136`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x180031136`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800311e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800311e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031108`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031108`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
        __int64 a1,
        const wchar_t *a2,
        va_list a3)
{
  unsigned __int64 v5; // rcx
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // r9
  int v9; // ebx
  _WORD *v11; // rax
  unsigned __int64 v12; // rsi
  wchar_t *v13; // r14
  size_t v14; // rsi
  int v15; // eax
  __int64 v16; // r9
  unsigned __int64 v17; // rbx
  LPVOID v18; // rax
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // [rsp+78h] [rbp+20h] BYREF

  v5 = 32;
  while ( 1 )
  {
    v7 = v5 + 1;
    if ( v5 + 1 < v5 )
    {
LABEL_6:
      v9 = -2147024362;
      goto LABEL_8;
    }
    v8 = *(_QWORD *)(a1 + 16);
    if ( v8 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a1);
      if ( *(_QWORD *)a1 )
        v8 = *(_QWORD *)(a1 + 8) + 1LL;
      else
        v8 = 0;
      *(_QWORD *)(a1 + 16) = v8;
    }
    if ( v8 )
      break;
    v20 = 0;
    if ( !is_mul_ok(v7, 2u) )
      goto LABEL_6;
    v11 = CoTaskMemAlloc(2 * v7);
    if ( v11 )
    {
      v9 = 0;
      *(_QWORD *)(a1 + 16) = v7;
      *(_QWORD *)a1 = v11;
      *v11 = 0;
    }
    else
    {
      v9 = -2147024882;
    }
    if ( v9 < 0 )
      goto LABEL_33;
LABEL_14:
    v12 = *(_QWORD *)(a1 + 16);
    v13 = *(wchar_t **)a1;
    _o__set_errno(0);
    if ( v12 )
    {
      if ( v12 > 0x7FFFFFFF )
      {
        *v13 = 0;
LABEL_40:
        v9 = -2147024809;
        goto LABEL_8;
      }
      v14 = v12 - 1;
      v15 = vsnwprintf(v13, v14, a2, a3);
      if ( v15 < 0 || v15 > v14 )
      {
        v9 = -2147024774;
        v13[v14] = 0;
      }
      else
      {
        v9 = 0;
        if ( v15 == v14 )
          v13[v14] = 0;
      }
    }
    else
    {
      v9 = -2147024809;
    }
    if ( v9 != -2147024774 )
      goto LABEL_8;
    LODWORD(v20) = 0;
    _o__get_errno(&v20);
    if ( (_DWORD)v20 == 22 )
      goto LABEL_40;
    v19 = *(_QWORD *)(a1 + 16);
    v5 = v19 + 32;
    if ( v19 + 32 < v19 )
    {
      v9 = -2147024362;
      goto LABEL_33;
    }
  }
  if ( v7 <= v8 )
    goto LABEL_14;
  v20 = 0;
  v9 = ULongLongMult(v8, 2u, &v20);
  if ( v9 < 0 )
    goto LABEL_8;
  v17 = v20;
  if ( v20 - v16 > 0x800 )
    v17 = v16 + 2048;
  if ( v7 > v17 )
    v17 = v7;
  v18 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v17);
  if ( v18 )
  {
    *(_QWORD *)(a1 + 16) = v17;
    *(_QWORD *)a1 = v18;
    goto LABEL_14;
  }
  v9 = -2147024882;
LABEL_8:
  if ( v9 >= 0 )
  {
    *(_QWORD *)(a1 + 8) = -1;
    return (unsigned int)v9;
  }
LABEL_33:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180031080  push    rbx
0x180031082  push    rbp
0x180031083  push    rsi
0x180031084  push    rdi
0x180031085  push    r14
0x180031087  push    r15
0x180031089  sub     rsp, 28h
0x18003108d  mov     rdi, rcx
0x180031090  mov     rbp, r8
0x180031093  mov     ecx, 20h ; ' '
0x180031098  mov     r15, rdx
0x18003109b  lea     rsi, [rcx+1]
0x18003109f  cmp     rsi, rcx
0x1800310a2  jb      short loc_1800310CC
0x1800310a4  mov     r9, [rdi+10h]
0x1800310a8  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1800310ac  jz      loc_180031246
0x1800310b2  test    r9, r9
0x1800310b5  jnz     loc_180031192
0x1800310bb  lea     eax, [r9+2]
0x1800310bf  mov     [rsp+58h+arg_18], r9
0x1800310c4  mul     rsi
0x1800310c7  test    rdx, rdx
0x1800310ca  jz      short loc_180031105
0x1800310cc  mov     ebx, 80070216h
0x1800310d1  jmp     short loc_1800310E6
0x1800310d3  xor     eax, eax
0x1800310d5  mov     [r14+rsi*2], ax
0x1800310da  cmp     ebx, 8007007Ah
0x1800310e0  jz      loc_180031209
0x1800310e6  test    ebx, ebx
0x1800310e8  js      loc_180031239
0x1800310ee  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x1800310f6  mov     eax, ebx
0x1800310f8  add     rsp, 28h
0x1800310fc  pop     r15
0x1800310fe  pop     r14
0x180031100  pop     rdi
0x180031101  pop     rsi
0x180031102  pop     rbp
0x180031103  pop     rbx
0x180031104  retn
0x180031105  mov     rcx, rax; cb
0x180031108  call    cs:__imp_CoTaskMemAlloc
0x18003110e  test    rax, rax
0x180031111  jz      loc_1800311FF
0x180031117  xor     ebx, ebx
0x180031119  mov     [rdi+10h], rsi
0x18003111d  xor     ecx, ecx
0x18003111f  mov     [rdi], rax
0x180031122  mov     [rax], cx
0x180031125  test    ebx, ebx
0x180031127  js      loc_180031239
0x18003112d  mov     rsi, [rdi+10h]
0x180031131  xor     ecx, ecx
0x180031133  mov     r14, [rdi]
0x180031136  call    cs:__imp__o__set_errno
0x18003113c  test    rsi, rsi
0x18003113f  jz      loc_180031269
0x180031145  cmp     rsi, 7FFFFFFFh
0x18003114c  ja      loc_180031277
0x180031152  dec     rsi
0x180031155  mov     r9, rbp; Args
0x180031158  mov     rdx, rsi; BufferCount
0x18003115b  mov     r8, r15; Format
0x18003115e  mov     rcx, r14; Buffer
0x180031161  call    _vsnwprintf
0x180031166  test    eax, eax
0x180031168  js      short loc_180031181
0x18003116a  cdqe
0x18003116c  cmp     rax, rsi
0x18003116f  ja      short loc_180031181
0x180031171  xor     ebx, ebx
0x180031173  cmp     rax, rsi
0x180031176  jnz     loc_1800310DA
0x18003117c  jmp     loc_1800310D3
0x180031181  xor     eax, eax
0x180031183  mov     ebx, 8007007Ah
0x180031188  mov     [r14+rsi*2], ax
0x18003118d  jmp     loc_1800310DA
0x180031192  cmp     rsi, r9
0x180031195  jbe     short loc_18003112D
0x180031197  lea     r8, [rsp+58h+arg_18]; unsigned __int64 *
0x18003119c  mov     [rsp+58h+arg_18], 0
0x1800311a5  mov     edx, 2; unsigned __int64
0x1800311aa  mov     rcx, r9; unsigned __int64
0x1800311ad  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800311b2  mov     ebx, eax
0x1800311b4  test    eax, eax
0x1800311b6  js      loc_1800310E6
0x1800311bc  mov     rbx, [rsp+58h+arg_18]
0x1800311c1  mov     rax, rbx
0x1800311c4  sub     rax, r9
0x1800311c7  cmp     rax, 800h
0x1800311cd  jbe     short loc_1800311D6
0x1800311cf  lea     rbx, [r9+800h]
0x1800311d6  mov     rcx, [rdi]; pv
0x1800311d9  cmp     rsi, rbx
0x1800311dc  cmova   rbx, rsi
0x1800311e0  lea     rdx, [rbx+rbx]; cb
0x1800311e4  call    cs:__imp_CoTaskMemRealloc
0x1800311ea  test    rax, rax
0x1800311ed  jz      loc_180031287
0x1800311f3  mov     [rdi+10h], rbx
0x1800311f7  mov     [rdi], rax
0x1800311fa  jmp     loc_18003112D
0x1800311ff  mov     ebx, 8007000Eh
0x180031204  jmp     loc_180031125
0x180031209  lea     rcx, [rsp+58h+arg_18]
0x18003120e  mov     dword ptr [rsp+58h+arg_18], 0
0x180031216  call    cs:__imp__o__get_errno
0x18003121c  cmp     dword ptr [rsp+58h+arg_18], 16h
0x180031221  jz      short loc_18003127D
0x180031223  mov     rax, [rdi+10h]
0x180031227  lea     rcx, [rax+20h]
0x18003122b  cmp     rcx, rax
0x18003122e  jnb     loc_18003109B
0x180031234  mov     ebx, 80070216h
0x180031239  mov     rcx, rdi
0x18003123c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031241  jmp     loc_1800310F6
0x180031246  mov     rcx, rdi
0x180031249  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18003124e  cmp     qword ptr [rdi], 0
0x180031252  jz      short loc_18003125D
0x180031254  mov     r9, [rdi+8]
0x180031258  inc     r9
0x18003125b  jmp     short loc_180031260
0x18003125d  xor     r9d, r9d
0x180031260  mov     [rdi+10h], r9
0x180031264  jmp     loc_1800310B2
0x180031269  mov     ebx, 80070057h
0x18003126e  test    rsi, rsi
0x180031271  jz      loc_1800310DA
0x180031277  xor     eax, eax
0x180031279  mov     [r14], ax
0x18003127d  mov     ebx, 80070057h
0x180031282  jmp     loc_1800310E6
0x180031287  mov     ebx, 8007000Eh
0x18003128c  jmp     loc_1800310E6
```
