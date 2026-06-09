# DavCopyCertificateIssuerList

- ea: `0x18000306c`
- end: `0x1800031c9`
- name: `DavCopyCertificateIssuerList`
- size: `349`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800045e8`

## callees

- `0x18000306c`
- `0x18000b7dc`
- `0x18002cf56`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030d1`
- `KERNEL32!LocalFree` at `0x18000319b`
- `KERNEL32!LocalFree` at `0x18000319b`
- `KERNEL32!LocalAlloc` at `0x1800030c3`
- `KERNEL32!LocalAlloc` at `0x1800030c3`

## pseudocode

```c
__int64 __fastcall DavCopyCertificateIssuerList(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  int v3; // r10d
  DWORD LastError; // ebx
  unsigned int v7; // r9d
  unsigned int v9; // r10d
  unsigned int i; // ecx
  __int64 v11; // rax
  __int64 v12; // r14
  _DWORD *v13; // rdi
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // r13d
  char *v17; // rbp
  char *v18; // r9
  __int64 v19; // r14
  size_t v20; // r8
  char *v22; // [rsp+70h] [rbp+8h]

  v3 = *(_DWORD *)(a1 + 8);
  LastError = 0;
  *a3 = 0;
  *a2 = 0;
  v7 = *(_DWORD *)(a1 + 8);
  v9 = 16 * v3;
  if ( v7 )
  {
    for ( i = 0; i < v7; ++i )
    {
      v11 = i;
      v9 += *(_DWORD *)(16 * v11 + *(_QWORD *)a1);
    }
    v12 = v9;
    v13 = LocalAlloc(0x40u, v9);
    if ( v13 )
    {
      v16 = 0;
      v17 = (char *)&v13[4 * *(unsigned int *)(a1 + 8)];
      if ( !*(_DWORD *)(a1 + 8) )
      {
LABEL_13:
        *a3 = v13;
        *a2 = *(_DWORD *)(a1 + 8);
        return LastError;
      }
      v18 = (char *)v13 + v12;
      v22 = (char *)v13 + v12;
      while ( 1 )
      {
        v19 = 2LL * v16;
        v13[4 * v16] = *(_DWORD *)(*(_QWORD *)a1 + 16LL * v16);
        v20 = *(unsigned int *)(*(_QWORD *)a1 + 16LL * v16);
        if ( &v17[v20] > v18 )
          break;
        memcpy_0(v17, *(const void **)(*(_QWORD *)a1 + 16LL * v16 + 8), v20);
        v18 = v22;
        ++v16;
        *(_QWORD *)&v13[2 * v19 + 2] = v17;
        v17 += *(unsigned int *)(*(_QWORD *)a1 + 8 * v19);
        if ( v16 >= *(_DWORD *)(a1 + 8) )
          goto LABEL_13;
      }
      LocalFree(v13);
      LastError = 13;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 351;
        goto LABEL_8;
      }
    }
    else
    {
      LastError = GetLastError();
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 350;
LABEL_8:
        WPP_SF_d(v14[2], v15, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18000306c  push    rbx
0x18000306e  push    rbp
0x18000306f  push    rsi
0x180003070  push    rdi
0x180003071  push    r12
0x180003073  push    r13
0x180003075  push    r14
0x180003077  push    r15
0x180003079  sub     rsp, 28h
0x18000307d  mov     r10d, [rcx+8]
0x180003081  xor     ebx, ebx
0x180003083  mov     [r8], rbx
0x180003086  mov     r15, r8
0x180003089  mov     [rdx], ebx
0x18000308b  mov     r12, rdx
0x18000308e  mov     r9d, [rcx+8]
0x180003092  mov     rsi, rcx
0x180003095  shl     r10d, 4
0x180003099  test    r9d, r9d
0x18000309c  jz      loc_180003185
0x1800030a2  mov     rdx, [rsi]
0x1800030a5  xor     ecx, ecx
0x1800030a7  mov     eax, ecx
0x1800030a9  inc     ecx
0x1800030ab  shl     rax, 4
0x1800030af  add     r10d, [rax+rdx]
0x1800030b3  cmp     ecx, r9d
0x1800030b6  jb      short loc_1800030A7
0x1800030b8  mov     edx, r10d; uBytes
0x1800030bb  mov     ecx, 40h ; '@'; uFlags
0x1800030c0  mov     r14d, r10d
0x1800030c3  call    cs:__imp_LocalAlloc
0x1800030c9  mov     rdi, rax
0x1800030cc  test    rax, rax
0x1800030cf  jnz     short loc_180003114
0x1800030d1  call    cs:__imp_GetLastError
0x1800030d7  mov     ebx, eax
0x1800030d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030e0  lea     rax, WPP_GLOBAL_Control
0x1800030e7  cmp     rcx, rax
0x1800030ea  jz      loc_180003185
0x1800030f0  test    byte ptr [rcx+1Ch], 1
0x1800030f4  jz      loc_180003185
0x1800030fa  mov     edx, 15Eh
0x1800030ff  mov     rcx, [rcx+10h]
0x180003103  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000310a  mov     r9d, ebx
0x18000310d  call    WPP_SF_d
0x180003112  jmp     short loc_180003185
0x180003114  mov     eax, [rsi+8]
0x180003117  xor     r13d, r13d
0x18000311a  mov     ebp, eax
0x18000311c  shl     rbp, 4
0x180003120  add     rbp, rdi
0x180003123  test    eax, eax
0x180003125  jz      short loc_18000317B
0x180003127  lea     r9, [r14+rdi]
0x18000312b  mov     [rsp+68h+arg_0], r9
0x180003130  mov     rax, [rsi]
0x180003133  mov     r14d, r13d
0x180003136  add     r14, r14
0x180003139  mov     ecx, [rax+r14*8]
0x18000313d  mov     [rdi+r14*8], ecx
0x180003141  mov     rdx, [rsi]
0x180003144  mov     r8d, [rdx+r14*8]; Size
0x180003148  lea     rax, [r8+rbp]
0x18000314c  cmp     rax, r9
0x18000314f  ja      short loc_180003198
0x180003151  mov     rdx, [rdx+r14*8+8]; Src
0x180003156  mov     rcx, rbp; void *
0x180003159  call    memcpy_0
0x18000315e  mov     r9, [rsp+68h+arg_0]
0x180003163  inc     r13d
0x180003166  mov     [rdi+r14*8+8], rbp
0x18000316b  mov     rax, [rsi]
0x18000316e  mov     ecx, [rax+r14*8]
0x180003172  add     rbp, rcx
0x180003175  cmp     r13d, [rsi+8]
0x180003179  jb      short loc_180003130
0x18000317b  mov     [r15], rdi
0x18000317e  mov     eax, [rsi+8]
0x180003181  mov     [r12], eax
0x180003185  mov     eax, ebx
0x180003187  add     rsp, 28h
0x18000318b  pop     r15
0x18000318d  pop     r14
0x18000318f  pop     r13
0x180003191  pop     r12
0x180003193  pop     rdi
0x180003194  pop     rsi
0x180003195  pop     rbp
0x180003196  pop     rbx
0x180003197  retn
0x180003198  mov     rcx, rdi; hMem
0x18000319b  call    cs:__imp_LocalFree
0x1800031a1  mov     ebx, 0Dh
0x1800031a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031ad  lea     rax, WPP_GLOBAL_Control
0x1800031b4  cmp     rcx, rax
0x1800031b7  jz      short loc_180003185
0x1800031b9  test    byte ptr [rcx+1Ch], 1
0x1800031bd  jz      short loc_180003185
0x1800031bf  mov     edx, 15Fh
0x1800031c4  jmp     loc_1800030FF
```
