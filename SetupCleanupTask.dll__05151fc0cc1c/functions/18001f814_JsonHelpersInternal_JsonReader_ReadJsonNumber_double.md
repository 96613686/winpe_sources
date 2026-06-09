# JsonHelpersInternal::JsonReader::ReadJsonNumber(double *)

- ea: `0x18001f814`
- end: `0x18001fae6`
- name: `?ReadJsonNumber@JsonReader@JsonHelpersInternal@@QEAAJPEAN@Z`
- size: `722`
- prototype: `__int64 __fastcall(JsonHelpersInternal::JsonReader *__hidden this, double *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001ff90`

## callees

- `0x18001f814`
- `0x18002443c`
- `0x1800246f8`

## import_xrefs

- `msvcrt!_wtof` at `0x18001faa3`
- `msvcrt!_wtof` at `0x18001faa3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f833`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f839`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f833`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f839`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fac5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fac5`

## pseudocode

```c
__int64 __fastcall JsonHelpersInternal::JsonReader::ReadJsonNumber(JsonHelpersInternal::JsonReader *this, double *a2)
{
  __int64 v4; // r9
  unsigned __int64 v5; // r8
  __int16 v6; // cx
  int v7; // ebx
  __int64 v8; // rdx
  const unsigned __int16 *v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // rcx
  bool v12; // zf
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // r8
  __int64 v15; // rcx
  unsigned __int16 v16; // r8
  unsigned __int64 v17; // r8
  HANDLE hHeap; // [rsp+20h] [rbp-30h] BYREF
  __int128 v20; // [rsp+28h] [rbp-28h]
  __int64 v21; // [rsp+38h] [rbp-18h]
  wchar_t *String[2]; // [rsp+40h] [rbp-10h]
  __int16 v23; // [rsp+90h] [rbp+40h] BYREF

  GetProcessHeap();
  v21 = 4096;
  hHeap = GetProcessHeap();
  v20 = 0;
  *(_OWORD *)String = 0;
  v4 = *((_QWORD *)this + 1);
  while ( 1 )
  {
    v5 = *(_QWORD *)this;
    v6 = *(_WORD *)(v4 + 2LL * *(_QWORD *)this);
    if ( v6 != 9
      && *(_WORD *)(v4 + 2LL * *(_QWORD *)this) != 10
      && *(_WORD *)(v4 + 2LL * *(_QWORD *)this) != 13
      && *(_WORD *)(v4 + 2LL * *(_QWORD *)this) != 32 )
    {
      break;
    }
    *(_QWORD *)this = v5 + 1;
    if ( !v6 )
      *(_QWORD *)this = v5;
  }
  v23 = *(_WORD *)(v4 + 2LL * *(_QWORD *)this);
  *(_QWORD *)this = v5 + 1;
  if ( v6 )
  {
    if ( v6 == 45 )
    {
      v7 = RtlMemoryStream::Write((RtlMemoryStream *)&hHeap, &v23, v5);
      if ( v7 < 0 )
        goto LABEL_45;
      v8 = *(_QWORD *)this;
      v6 = *(_WORD *)(*((_QWORD *)this + 1) + 2LL * (*(_QWORD *)this)++);
      if ( !v6 )
        *(_QWORD *)this = v8;
      v23 = v6;
    }
  }
  else
  {
    *(_QWORD *)this = v5;
  }
  if ( (unsigned __int16)(v6 - 48) > 9u )
    goto LABEL_44;
  v7 = RtlMemoryStream::Write((RtlMemoryStream *)&hHeap, &v23, v5);
  if ( v7 < 0 )
    goto LABEL_45;
  if ( v23 == 48 && *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(_QWORD *)this) != 46 )
  {
LABEL_42:
    v7 = RtlMemoryStream::WriteString((RtlMemoryStream *)&hHeap, v9, (const unsigned __int16 *)v10);
    if ( v7 >= 0 )
    {
      *a2 = _wtof(String[1]);
      v7 = 0;
    }
    goto LABEL_45;
  }
  while ( 1 )
  {
    v11 = *(_QWORD *)this;
    v9 = (const unsigned __int16 *)*((_QWORD *)this + 1);
    v10 = v9[*(_QWORD *)this];
    if ( (unsigned __int16)(v10 - 48) > 9u )
      break;
    *(_QWORD *)this = v11 + 1;
    if ( !(_WORD)v10 )
      *(_QWORD *)this = v11;
    v23 = v10;
    v7 = RtlMemoryStream::Write((RtlMemoryStream *)&hHeap, &v23, v10);
    if ( v7 < 0 )
      goto LABEL_45;
  }
  if ( (_WORD)v10 != 46 )
  {
    LOWORD(v10) = v10 - 69;
    v12 = (v10 & 0xFFDF) == 0;
LABEL_32:
    if ( v12 )
    {
LABEL_33:
      v14 = v9[v11];
      *(_QWORD *)this = v11 + 1;
      if ( !(_WORD)v14 )
        *(_QWORD *)this = v11;
      v23 = v14;
      v7 = RtlMemoryStream::Write((RtlMemoryStream *)&hHeap, &v23, v14);
      if ( v7 < 0 )
        goto LABEL_45;
      v15 = *(_QWORD *)this;
      v9 = (const unsigned __int16 *)*((_QWORD *)this + 1);
      v16 = v9[*(_QWORD *)this];
      if ( (unsigned __int16)(v16 - 48) <= 9u || ((v16 - 43) & 0xFFFD) == 0 )
      {
        while ( 1 )
        {
          v17 = v9[v15];
          *(_QWORD *)this = v15 + 1;
          if ( !(_WORD)v17 )
            *(_QWORD *)this = v15;
          v23 = v17;
          v7 = RtlMemoryStream::Write((RtlMemoryStream *)&hHeap, &v23, v17);
          if ( v7 < 0 )
            goto LABEL_45;
          v15 = *(_QWORD *)this;
          v9 = (const unsigned __int16 *)*((_QWORD *)this + 1);
          if ( (unsigned __int16)(v9[*(_QWORD *)this] - 48) > 9u )
            goto LABEL_42;
        }
      }
LABEL_44:
      v7 = -2147024883;
      goto LABEL_45;
    }
    goto LABEL_42;
  }
  while ( 1 )
  {
    v13 = v9[v11];
    *(_QWORD *)this = v11 + 1;
    if ( !(_WORD)v13 )
      *(_QWORD *)this = v11;
    v23 = v13;
    v7 = RtlMemoryStream::Write((RtlMemoryStream *)&hHeap, &v23, v13);
    if ( v7 < 0 )
      break;
    v11 = *(_QWORD *)this;
    v9 = (const unsigned __int16 *)*((_QWORD *)this + 1);
    if ( (unsigned __int16)(v9[*(_QWORD *)this] - 48) > 9u )
    {
      if ( v9[v11] == 69 )
        goto LABEL_33;
      v12 = v9[v11] == 101;
      goto LABEL_32;
    }
  }
LABEL_45:
  if ( String[1] )
    HeapFree(hHeap, 0, String[1]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001f814  mov     [rsp-28h+arg_0], rbx
0x18001f819  mov     [rsp-28h+arg_8], rsi
0x18001f81e  push    rbp
0x18001f81f  push    rdi
0x18001f820  push    r12
0x18001f822  push    r14
0x18001f824  push    r15
0x18001f826  mov     rbp, rsp
0x18001f829  sub     rsp, 50h
0x18001f82d  mov     rsi, rdx
0x18001f830  mov     rdi, rcx
0x18001f833  call    cs:__imp_GetProcessHeap
0x18001f839  call    cs:__imp_GetProcessHeap
0x18001f83f  xorps   xmm0, xmm0
0x18001f842  mov     [rbp+var_18], 1000h
0x18001f84a  xorps   xmm1, xmm1
0x18001f84d  mov     [rbp+hHeap], rax
0x18001f851  movdqu  [rbp+var_28], xmm0
0x18001f856  movdqu  xmmword ptr [rbp+String], xmm1
0x18001f85b  mov     r9, [rdi+8]
0x18001f85f  mov     r12d, 9
0x18001f865  mov     r8, [rdi]; unsigned __int64
0x18001f868  movzx   ecx, word ptr [r9+r8*2]
0x18001f86d  mov     edx, ecx
0x18001f86f  sub     edx, r12d
0x18001f872  jz      short loc_18001F883
0x18001f874  sub     edx, 1
0x18001f877  jz      short loc_18001F883
0x18001f879  sub     edx, 3
0x18001f87c  jz      short loc_18001F883
0x18001f87e  cmp     edx, 13h
0x18001f881  jnz     short loc_18001F896
0x18001f883  lea     rax, [r8+1]
0x18001f887  mov     [rdi], rax
0x18001f88a  xor     eax, eax
0x18001f88c  cmp     ax, cx
0x18001f88f  jnz     short loc_18001F865
0x18001f891  mov     [rdi], r8
0x18001f894  jmp     short loc_18001F865
0x18001f896  lea     rax, [r8+1]
0x18001f89a  mov     [rbp+arg_10], cx
0x18001f89e  mov     [rdi], rax
0x18001f8a1  xor     eax, eax
0x18001f8a3  cmp     ax, cx
0x18001f8a6  jnz     short loc_18001F8AD
0x18001f8a8  mov     [rdi], r8
0x18001f8ab  jmp     short loc_18001F8EE
0x18001f8ad  mov     eax, 2Dh ; '-'
0x18001f8b2  cmp     ax, cx
0x18001f8b5  jnz     short loc_18001F8EE
0x18001f8b7  lea     rdx, [rbp+arg_10]; void *
0x18001f8bb  lea     rcx, [rbp+hHeap]; this
0x18001f8bf  call    ?Write@RtlMemoryStream@@QEAAJPEBX_K@Z; RtlMemoryStream::Write(void const *,unsigned __int64)
0x18001f8c4  mov     ebx, eax
0x18001f8c6  test    eax, eax
0x18001f8c8  js      loc_18001FAB6
0x18001f8ce  mov     rdx, [rdi]
0x18001f8d1  mov     rax, [rdi+8]
0x18001f8d5  movzx   ecx, word ptr [rax+rdx*2]
0x18001f8d9  lea     rax, [rdx+1]
0x18001f8dd  mov     [rdi], rax
0x18001f8e0  xor     eax, eax
0x18001f8e2  cmp     ax, cx
0x18001f8e5  jnz     short loc_18001F8EA
0x18001f8e7  mov     [rdi], rdx
0x18001f8ea  mov     [rbp+arg_10], cx
0x18001f8ee  mov     r14d, 30h ; '0'
0x18001f8f4  sub     cx, r14w
0x18001f8f8  cmp     cx, r12w
0x18001f8fc  ja      loc_18001FAB1
0x18001f902  lea     rdx, [rbp+arg_10]; void *
0x18001f906  lea     rcx, [rbp+hHeap]; this
0x18001f90a  call    ?Write@RtlMemoryStream@@QEAAJPEBX_K@Z; RtlMemoryStream::Write(void const *,unsigned __int64)
0x18001f90f  mov     ebx, eax
0x18001f911  test    eax, eax
0x18001f913  js      loc_18001FAB6
0x18001f919  lea     r15d, [r14-2]
0x18001f91d  cmp     r14w, [rbp+arg_10]
0x18001f922  jnz     short loc_18001F936
0x18001f924  mov     rcx, [rdi]
0x18001f927  mov     rax, [rdi+8]
0x18001f92b  cmp     r15w, [rax+rcx*2]
0x18001f930  jnz     loc_18001FA90
0x18001f936  mov     rcx, [rdi]
0x18001f939  mov     rdx, [rdi+8]
0x18001f93d  movzx   r8d, word ptr [rdx+rcx*2]; unsigned __int64
0x18001f942  movzx   eax, r8w
0x18001f946  sub     ax, r14w
0x18001f94a  cmp     ax, r12w
0x18001f94e  ja      short loc_18001F97F
0x18001f950  lea     rax, [rcx+1]
0x18001f954  mov     [rdi], rax
0x18001f957  xor     eax, eax
0x18001f959  cmp     ax, r8w
0x18001f95d  jnz     short loc_18001F962
0x18001f95f  mov     [rdi], rcx
0x18001f962  lea     rdx, [rbp+arg_10]; void *
0x18001f966  mov     [rbp+arg_10], r8w
0x18001f96b  lea     rcx, [rbp+hHeap]; this
0x18001f96f  call    ?Write@RtlMemoryStream@@QEAAJPEBX_K@Z; RtlMemoryStream::Write(void const *,unsigned __int64)
0x18001f974  mov     ebx, eax
0x18001f976  test    eax, eax
0x18001f978  jns     short loc_18001F936
0x18001f97a  jmp     loc_18001FAB6
0x18001f97f  cmp     r8w, r15w
0x18001f983  jz      short loc_18001F995
0x18001f985  sub     r8w, 45h ; 'E'
0x18001f98a  mov     eax, 0FFDFh
0x18001f98f  test    ax, r8w
0x18001f993  jmp     short loc_18001F9E9
0x18001f995  movzx   r8d, word ptr [rdx+rcx*2]; unsigned __int64
0x18001f99a  lea     rax, [rcx+1]
0x18001f99e  mov     [rdi], rax
0x18001f9a1  xor     eax, eax
0x18001f9a3  cmp     ax, r8w
0x18001f9a7  jnz     short loc_18001F9AC
0x18001f9a9  mov     [rdi], rcx
0x18001f9ac  lea     rdx, [rbp+arg_10]; void *
0x18001f9b0  mov     [rbp+arg_10], r8w
0x18001f9b5  lea     rcx, [rbp+hHeap]; this
0x18001f9b9  call    ?Write@RtlMemoryStream@@QEAAJPEBX_K@Z; RtlMemoryStream::Write(void const *,unsigned __int64)
0x18001f9be  mov     ebx, eax
0x18001f9c0  test    eax, eax
0x18001f9c2  js      loc_18001FAB6
0x18001f9c8  mov     rcx, [rdi]
0x18001f9cb  mov     rdx, [rdi+8]
0x18001f9cf  movzx   eax, word ptr [rdx+rcx*2]
0x18001f9d3  sub     ax, r14w
0x18001f9d7  cmp     ax, r12w
0x18001f9db  jbe     short loc_18001F995
0x18001f9dd  cmp     word ptr [rdx+rcx*2], 45h ; 'E'
0x18001f9e2  jz      short loc_18001F9EF
0x18001f9e4  cmp     word ptr [rdx+rcx*2], 65h ; 'e'
0x18001f9e9  jnz     loc_18001FA90
0x18001f9ef  movzx   r8d, word ptr [rdx+rcx*2]; unsigned __int64
0x18001f9f4  lea     rax, [rcx+1]
0x18001f9f8  mov     [rdi], rax
0x18001f9fb  xor     eax, eax
0x18001f9fd  cmp     ax, r8w
0x18001fa01  jnz     short loc_18001FA06
0x18001fa03  mov     [rdi], rcx
0x18001fa06  lea     rdx, [rbp+arg_10]; void *
0x18001fa0a  mov     [rbp+arg_10], r8w
0x18001fa0f  lea     rcx, [rbp+hHeap]; this
0x18001fa13  call    ?Write@RtlMemoryStream@@QEAAJPEBX_K@Z; RtlMemoryStream::Write(void const *,unsigned __int64)
0x18001fa18  mov     ebx, eax
0x18001fa1a  test    eax, eax
0x18001fa1c  js      loc_18001FAB6
0x18001fa22  mov     rcx, [rdi]
0x18001fa25  mov     rdx, [rdi+8]
0x18001fa29  movzx   r8d, word ptr [rdx+rcx*2]
0x18001fa2e  movzx   eax, r8w
0x18001fa32  sub     ax, r14w
0x18001fa36  cmp     ax, r12w
0x18001fa3a  jbe     short loc_18001FA4C
0x18001fa3c  sub     r8w, 2Bh ; '+'
0x18001fa41  mov     eax, 0FFFDh
0x18001fa46  test    ax, r8w
0x18001fa4a  jnz     short loc_18001FAB1
0x18001fa4c  movzx   r8d, word ptr [rdx+rcx*2]; unsigned __int64
0x18001fa51  lea     rax, [rcx+1]
0x18001fa55  mov     [rdi], rax
0x18001fa58  xor     eax, eax
0x18001fa5a  cmp     ax, r8w
0x18001fa5e  jnz     short loc_18001FA63
0x18001fa60  mov     [rdi], rcx
0x18001fa63  lea     rdx, [rbp+arg_10]; void *
0x18001fa67  mov     [rbp+arg_10], r8w
0x18001fa6c  lea     rcx, [rbp+hHeap]; this
0x18001fa70  call    ?Write@RtlMemoryStream@@QEAAJPEBX_K@Z; RtlMemoryStream::Write(void const *,unsigned __int64)
0x18001fa75  mov     ebx, eax
0x18001fa77  test    eax, eax
0x18001fa79  js      short loc_18001FAB6
0x18001fa7b  mov     rcx, [rdi]
0x18001fa7e  mov     rdx, [rdi+8]; unsigned __int16 *
0x18001fa82  movzx   eax, word ptr [rdx+rcx*2]
0x18001fa86  sub     ax, r14w
0x18001fa8a  cmp     ax, r12w
0x18001fa8e  jbe     short loc_18001FA4C
0x18001fa90  lea     rcx, [rbp+hHeap]; this
0x18001fa94  call    ?WriteString@RtlMemoryStream@@QEAAJPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x18001fa99  mov     ebx, eax
0x18001fa9b  test    eax, eax
0x18001fa9d  js      short loc_18001FAB6
0x18001fa9f  mov     rcx, [rbp+String+8]; String
0x18001faa3  call    cs:__imp__wtof
0x18001faa9  movsd   qword ptr [rsi], xmm0
0x18001faad  xor     ebx, ebx
0x18001faaf  jmp     short loc_18001FAB6
0x18001fab1  mov     ebx, 8007000Dh
0x18001fab6  mov     r8, [rbp+String+8]; lpMem
0x18001faba  test    r8, r8
0x18001fabd  jz      short loc_18001FACB
0x18001fabf  mov     rcx, [rbp+hHeap]; hHeap
0x18001fac3  xor     edx, edx; dwFlags
0x18001fac5  call    cs:__imp_HeapFree
0x18001facb  lea     r11, [rsp+50h+var_s0]
0x18001fad0  mov     eax, ebx
0x18001fad2  mov     rbx, [r11+30h]
0x18001fad6  mov     rsi, [r11+38h]
0x18001fada  mov     rsp, r11
0x18001fadd  pop     r15
0x18001fadf  pop     r14
0x18001fae1  pop     r12
0x18001fae3  pop     rdi
0x18001fae4  pop     rbp
0x18001fae5  retn
```
