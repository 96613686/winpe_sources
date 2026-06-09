# GetHttpHeaderFromRawHttpHeaders(ushort const *,ushort const *,ushort * *)

- ea: `0x18007cd60`
- end: `0x18007ce5e`
- name: `?GetHttpHeaderFromRawHttpHeaders@@YAJPEBG0PEAPEAG@Z`
- size: `254`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180040da8`
- `0x180042800`
- `0x1800467c8`

## callees

- `0x18007cd60`
- `0x18007ce64`
- `0x18007cf84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18007cdf1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18007cdf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007ce1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007ce1c`

## pseudocode

```c
__int64 __fastcall GetHttpHeaderFromRawHttpHeaders(char *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v3; // rdi
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rax
  const unsigned __int16 *v8; // r8
  _WORD *v9; // r8
  const unsigned __int16 *v10; // rbp
  wchar_t *v11; // rax
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rsi
  unsigned __int16 *v14; // rcx
  unsigned __int16 **v16; // [rsp+20h] [rbp-58h]
  unsigned __int64 *v17; // [rsp+28h] [rbp-50h]
  unsigned int v18; // [rsp+30h] [rbp-48h]

  v3 = -1;
  v6 = -2147023728;
  do
    ++v3;
  while ( a2[v3] );
  while ( 1 )
  {
    v7 = (const unsigned __int16 *)StrStrI();
    if ( !v7 )
      break;
    v8 = &v7[v3];
    if ( *v8 == 58 )
    {
      v9 = v8 + 1;
      if ( v7 == (const unsigned __int16 *)a1
        || (__int64)(((char *)v7 - a1) & 0xFFFFFFFFFFFFFFFEuLL) >= 4 && *(v7 - 2) == 13 && *(v7 - 1) == 10 )
      {
        v10 = v9 + 1;
        v11 = wcsstr(v9 + 1, L"\r\n");
        *a3 = 0;
        v12 = v11 - v10;
        v13 = v12 + 1;
        if ( v12 + 1 >= v12 && is_mul_ok(v13, 2u) )
        {
          v14 = (unsigned __int16 *)CoTaskMemAlloc(2 * v13);
          *a3 = v14;
          v6 = v14 == 0 ? 0x8007000E : 0;
          if ( v14 )
            StringCchCopyNExW(v14, v12 + 1, v10, v12, v16, v17, v18);
        }
        else
        {
          return (unsigned int)-2147024362;
        }
        return v6;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18007cd60  push    rbx
0x18007cd62  push    rbp
0x18007cd63  push    rsi
0x18007cd64  push    rdi
0x18007cd65  push    r14
0x18007cd67  push    r15
0x18007cd69  sub     rsp, 48h
0x18007cd6d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007cd71  mov     r14, r8
0x18007cd74  xor     r15d, r15d
0x18007cd77  mov     rbp, rdx
0x18007cd7a  mov     rsi, rcx
0x18007cd7d  mov     ebx, 80070490h
0x18007cd82  inc     rdi
0x18007cd85  cmp     [rdx+rdi*2], r15w
0x18007cd8a  jnz     short loc_18007CD82
0x18007cd8c  call    _StrStrI
0x18007cd91  mov     rcx, rax
0x18007cd94  test    rax, rax
0x18007cd97  jz      loc_18007CE4F
0x18007cd9d  lea     r8, [rax+rdi*2]
0x18007cda1  mov     eax, 3Ah ; ':'
0x18007cda6  cmp     ax, [r8]
0x18007cdaa  jnz     short loc_18007CDDB
0x18007cdac  add     r8, 2
0x18007cdb0  cmp     rcx, rsi
0x18007cdb3  jz      short loc_18007CDE3
0x18007cdb5  mov     rax, rcx
0x18007cdb8  sub     rax, rsi
0x18007cdbb  and     rax, 0FFFFFFFFFFFFFFFEh
0x18007cdbf  cmp     rax, 4
0x18007cdc3  jl      short loc_18007CDDB
0x18007cdc5  mov     eax, 0Dh
0x18007cdca  cmp     ax, [rcx-4]
0x18007cdce  jnz     short loc_18007CDDB
0x18007cdd0  mov     eax, 0Ah
0x18007cdd5  cmp     ax, [rcx-2]
0x18007cdd9  jz      short loc_18007CDE3
0x18007cddb  mov     rdx, rbp
0x18007cdde  mov     rcx, r8
0x18007cde1  jmp     short loc_18007CD8C
0x18007cde3  lea     rbp, [r8+2]
0x18007cde7  mov     rcx, rbp; Str
0x18007cdea  lea     rdx, SubStr; "\r\n"
0x18007cdf1  call    cs:__imp_wcsstr
0x18007cdf7  mov     rdi, rax
0x18007cdfa  mov     [r14], r15
0x18007cdfd  sub     rdi, rbp
0x18007ce00  sar     rdi, 1
0x18007ce03  lea     rsi, [rdi+1]
0x18007ce07  cmp     rsi, rdi
0x18007ce0a  jb      short loc_18007CE4A
0x18007ce0c  mov     eax, 2
0x18007ce11  mul     rsi
0x18007ce14  test    rdx, rdx
0x18007ce17  jnz     short loc_18007CE4A
0x18007ce19  mov     rcx, rax; cb
0x18007ce1c  call    cs:__imp_CoTaskMemAlloc
0x18007ce22  mov     rcx, rax; unsigned __int16 *
0x18007ce25  mov     [r14], rax
0x18007ce28  neg     rax
0x18007ce2b  sbb     ebx, ebx
0x18007ce2d  not     ebx
0x18007ce2f  and     ebx, 8007000Eh
0x18007ce35  test    rcx, rcx
0x18007ce38  jz      short loc_18007CE4F
0x18007ce3a  mov     r9, rdi; unsigned __int64
0x18007ce3d  mov     r8, rbp; unsigned __int16 *
0x18007ce40  mov     rdx, rsi; unsigned __int64
0x18007ce43  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18007ce48  jmp     short loc_18007CE4F
0x18007ce4a  mov     ebx, 80070216h
0x18007ce4f  mov     eax, ebx
0x18007ce51  add     rsp, 48h
0x18007ce55  pop     r15
0x18007ce57  pop     r14
0x18007ce59  pop     rdi
0x18007ce5a  pop     rsi
0x18007ce5b  pop     rbp
0x18007ce5c  pop     rbx
0x18007ce5d  retn
```
