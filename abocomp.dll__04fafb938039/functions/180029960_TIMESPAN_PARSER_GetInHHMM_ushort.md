# TIMESPAN_PARSER::GetInHHMM(ushort * *)

- ea: `0x180029960`
- end: `0x180029af2`
- name: `?GetInHHMM@TIMESPAN_PARSER@@QEAAJPEAPEAG@Z`
- size: `402`
- prototype: `__int64 __fastcall(TIMESPAN_PARSER *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020dd0`

## callees

- `0x180029960`
- `0x180029f54`

## import_xrefs

- `msvcrt!_itow` at `0x1800299f5`
- `msvcrt!_itow` at `0x180029add`
- `msvcrt!_itow` at `0x1800299f5`
- `msvcrt!_itow` at `0x180029add`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029997`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029986`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029986`

## pseudocode

```c
__int64 __fastcall TIMESPAN_PARSER::GetInHHMM(TIMESPAN_PARSER *this, unsigned __int16 **a2)
{
  signed int v4; // r8d
  unsigned __int16 *v5; // rax
  signed int LastError; // eax
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rbx
  unsigned __int16 *v9; // r11
  __int64 v10; // rdx
  unsigned __int16 *v11; // rax
  __int64 v12; // r10
  __int64 v13; // r9
  const wchar_t *v14; // rcx
  unsigned __int16 *v15; // r10
  __int64 i; // rax
  unsigned __int16 *v17; // rdx
  int v18; // ebx
  unsigned __int16 *v19; // rcx
  __int64 v20; // rax

  if ( a2 )
  {
    v5 = (unsigned __int16 *)CoTaskMemAlloc(0x30u);
    *a2 = v5;
    if ( v5 )
    {
      v7 = (__int64)((unsigned __int128)(*(__int64 *)this * (__int128)0x1CA213D840BAF7D5LL) >> 64) >> 26;
      v8 = (v7 >> 63) + v7;
      _itow((int)v8 / 60, v5, 10);
      v9 = *a2;
      v10 = 24;
      v11 = *a2;
      do
      {
        if ( !*v11 )
          break;
        ++v11;
        --v10;
      }
      while ( v10 );
      v4 = v10 == 0 ? 0x80070057 : 0;
      v12 = (24 - v10) & -(__int64)(v10 != 0);
      if ( v10 )
      {
        v13 = 24 - v12;
        v14 = L":";
        v15 = &v9[v12];
        for ( i = 2147483646; v13; --v13 )
        {
          if ( !i )
            break;
          if ( !*v14 )
            break;
          *v15++ = *v14++;
          --i;
        }
        v17 = v15 - 1;
        v4 = v13 == 0 ? 0x8007007A : 0;
        if ( v13 )
          v17 = v15;
        *v17 = 0;
        if ( v13 )
        {
          v18 = (int)v8 % 60;
          if ( v18 >= 10 || (v4 = StringCchCatW(v9, (unsigned __int64)v17, L"0"), v4 >= 0) )
          {
            v19 = *a2;
            v20 = -1;
            do
              ++v20;
            while ( v19[v20] );
            _itow(v18, &v19[v20], 10);
            return 0;
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180029960  push    rbx
0x180029962  push    rbp
0x180029963  push    rsi
0x180029964  push    rdi
0x180029965  sub     rsp, 28h
0x180029969  xor     ebp, ebp
0x18002996b  mov     rdi, rdx
0x18002996e  mov     rbx, rcx
0x180029971  test    rdx, rdx
0x180029974  jnz     short loc_180029981
0x180029976  mov     r8d, 80070057h
0x18002997c  jmp     loc_180029AE6
0x180029981  mov     ecx, 30h ; '0'; cb
0x180029986  call    cs:__imp_CoTaskMemAlloc
0x18002998c  mov     [rdi], rax
0x18002998f  mov     rcx, rax
0x180029992  test    rax, rax
0x180029995  jnz     short loc_1800299B8
0x180029997  call    cs:__imp_GetLastError
0x18002999d  mov     r8d, eax
0x1800299a0  test    eax, eax
0x1800299a2  jle     loc_180029AE6
0x1800299a8  movzx   r8d, ax
0x1800299ac  or      r8d, 80070000h
0x1800299b3  jmp     loc_180029AE6
0x1800299b8  mov     rax, 1CA213D840BAF7D5h
0x1800299c2  mov     r8d, 0Ah; Radix
0x1800299c8  imul    qword ptr [rbx]
0x1800299cb  mov     rbx, rdx
0x1800299ce  sar     rbx, 1Ah
0x1800299d2  mov     rax, rbx
0x1800299d5  shr     rax, 3Fh
0x1800299d9  add     rbx, rax
0x1800299dc  mov     eax, 88888889h
0x1800299e1  imul    ebx
0x1800299e3  lea     esi, [rbx+rdx]
0x1800299e6  mov     rdx, rcx; Buffer
0x1800299e9  sar     esi, 5
0x1800299ec  mov     eax, esi
0x1800299ee  shr     eax, 1Fh
0x1800299f1  add     esi, eax
0x1800299f3  mov     ecx, esi; Value
0x1800299f5  call    cs:__imp__itow
0x1800299fb  mov     r11, [rdi]
0x1800299fe  mov     r9d, 18h
0x180029a04  mov     edx, r9d
0x180029a07  mov     rax, r11
0x180029a0a  cmp     [rax], bp
0x180029a0d  jz      short loc_180029A19
0x180029a0f  add     rax, 2
0x180029a13  sub     rdx, 1
0x180029a17  jnz     short loc_180029A0A
0x180029a19  mov     rax, rdx
0x180029a1c  mov     r8d, 80070057h
0x180029a22  neg     rax
0x180029a25  mov     rax, rdx
0x180029a28  sbb     ecx, ecx
0x180029a2a  not     ecx
0x180029a2c  and     r8d, ecx
0x180029a2f  mov     rcx, r9
0x180029a32  sub     rcx, rdx
0x180029a35  neg     rax
0x180029a38  sbb     r10, r10
0x180029a3b  and     r10, rcx
0x180029a3e  test    rdx, rdx
0x180029a41  jz      loc_180029AE6
0x180029a47  sub     r9, r10
0x180029a4a  lea     rcx, asc_180032CE8; ":"
0x180029a51  lea     r10, [r11+r10*2]
0x180029a55  mov     eax, 7FFFFFFEh
0x180029a5a  jz      short loc_180029A7E
0x180029a5c  test    rax, rax
0x180029a5f  jz      short loc_180029A7E
0x180029a61  movzx   edx, word ptr [rcx]
0x180029a64  test    dx, dx
0x180029a67  jz      short loc_180029A7E
0x180029a69  mov     [r10], dx
0x180029a6d  add     rcx, 2
0x180029a71  add     r10, 2
0x180029a75  dec     rax
0x180029a78  sub     r9, 1
0x180029a7c  jnz     short loc_180029A5C
0x180029a7e  mov     rax, r9
0x180029a81  lea     rdx, [r10-2]
0x180029a85  neg     rax
0x180029a88  sbb     r8d, r8d
0x180029a8b  not     r8d
0x180029a8e  and     r8d, 8007007Ah
0x180029a95  test    r9, r9
0x180029a98  cmovnz  rdx, r10; unsigned __int64
0x180029a9c  mov     [rdx], bp
0x180029a9f  jz      short loc_180029AE6
0x180029aa1  imul    eax, esi, 3Ch ; '<'
0x180029aa4  sub     ebx, eax
0x180029aa6  cmp     ebx, 0Ah
0x180029aa9  jge     short loc_180029AC1
0x180029aab  lea     r8, a0; "0"
0x180029ab2  mov     rcx, r11; unsigned __int16 *
0x180029ab5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180029aba  mov     r8d, eax
0x180029abd  test    eax, eax
0x180029abf  js      short loc_180029AE6
0x180029ac1  mov     rcx, [rdi]
0x180029ac4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029ac8  inc     rax
0x180029acb  cmp     [rcx+rax*2], bp
0x180029acf  jnz     short loc_180029AC8
0x180029ad1  lea     rdx, [rcx+rax*2]; Buffer
0x180029ad5  mov     r8d, 0Ah; Radix
0x180029adb  mov     ecx, ebx; Value
0x180029add  call    cs:__imp__itow
0x180029ae3  mov     r8d, ebp
0x180029ae6  mov     eax, r8d
0x180029ae9  add     rsp, 28h
0x180029aed  pop     rdi
0x180029aee  pop     rsi
0x180029aef  pop     rbp
0x180029af0  pop     rbx
0x180029af1  retn
```
