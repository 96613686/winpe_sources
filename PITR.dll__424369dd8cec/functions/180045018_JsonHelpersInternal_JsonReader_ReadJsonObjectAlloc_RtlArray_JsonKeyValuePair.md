# JsonHelpersInternal::JsonReader::ReadJsonObjectAlloc(RtlArray<JsonKeyValuePair *> * *)

- ea: `0x180045018`
- end: `0x1800454b4`
- name: `?ReadJsonObjectAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z`
- size: `1180`
- prototype: `__int64 __fastcall(JsonHelpersInternal::JsonReader *this, __int64 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800444a0`
- `0x1800454bc`

## callees

- `0x180001914`
- `0x180040eac`
- `0x180040f28`
- `0x180040fcc`
- `0x180045018`
- `0x1800454bc`
- `0x180045f24`
- `0x1800502c2`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800452f9`
- `msvcrt!wcscpy_s` at `0x1800452f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004506f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004508b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045216`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045275`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800452b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800452ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004506f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004508b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045216`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045275`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800452b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800452ce`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18004539e`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18004539e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045284`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800452c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004537e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045284`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800452c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004537e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045224`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800452dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045224`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800452dc`

## pseudocode

```c
__int64 __fastcall JsonHelpersInternal::JsonReader::ReadJsonObjectAlloc(
        JsonHelpersInternal::JsonReader *this,
        __int64 *a2)
{
  _QWORD *v4; // r15
  _OWORD *v5; // rax
  __int64 v6; // rdi
  __int64 v7; // r9
  __int64 v8; // rdx
  __int16 v9; // r8
  __int64 v10; // rcx
  int v11; // ebx
  __int16 v12; // r8
  __int64 v13; // r9
  __int16 v14; // r8
  int StringFromStreamAlloc; // eax
  wchar_t *v16; // r12
  __int64 v17; // r9
  __int64 v18; // rdx
  __int16 v19; // r8
  HANDLE v20; // rax
  unsigned __int64 v21; // r13
  unsigned __int64 v22; // rcx
  HANDLE ProcessHeap; // rax
  _QWORD *v24; // r14
  __int64 v25; // rax
  rsize_t v26; // r15
  SIZE_T v27; // rbx
  HANDLE v28; // rax
  wchar_t *v29; // rax
  wchar_t *v30; // rbx
  HANDLE v31; // rax
  struct JsonValue *v32; // rax
  __int64 v33; // r14
  unsigned __int128 v34; // rax
  unsigned __int64 v35; // kr00_8
  unsigned __int64 v36; // kr10_8
  unsigned __int64 v37; // r14
  unsigned __int128 v38; // rax
  unsigned __int64 v39; // kr20_8
  size_t v40; // r15
  void *v41; // r8
  void *v42; // rcx
  void *v43; // rax
  LPVOID v44; // rbx
  _QWORD *v45; // rax
  __int64 v46; // r9
  __int64 v47; // r8
  __int16 v48; // dx
  __int64 v50; // [rsp+20h] [rbp-20h] BYREF
  struct JsonKeyValuePair *v51; // [rsp+28h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-10h] BYREF
  struct JsonKeyValuePair *v53; // [rsp+38h] [rbp-8h] BYREF
  struct JsonValue *v55; // [rsp+90h] [rbp+50h] BYREF
  _QWORD *v56; // [rsp+98h] [rbp+58h]

  v50 = 0;
  v4 = 0;
  v56 = 0;
  v51 = 0;
  v5 = operator new(0x30u);
  v6 = (__int64)v5;
  if ( !v5 )
  {
    v11 = -2147024882;
    goto LABEL_84;
  }
  *v5 = 0;
  v5[1] = 0;
  v5[2] = 0;
  GetProcessHeap();
  *(_OWORD *)v6 = 0;
  *(_OWORD *)(v6 + 16) = 0;
  *(_OWORD *)(v6 + 32) = 0;
  *(_QWORD *)v6 = GetProcessHeap();
  *(_QWORD *)(v6 + 32) = 16;
  *(_QWORD *)(v6 + 16) = 0;
  *(_QWORD *)(v6 + 24) = 0;
  *(_QWORD *)(v6 + 40) = 0;
  *(_QWORD *)(v6 + 8) = 8;
  v7 = *((_QWORD *)this + 1);
  v50 = v6;
  while ( 1 )
  {
    v8 = *(_QWORD *)this;
    v9 = *(_WORD *)(v7 + 2LL * *(_QWORD *)this);
    if ( v9 != 9
      && *(_WORD *)(v7 + 2LL * *(_QWORD *)this) != 10
      && *(_WORD *)(v7 + 2LL * *(_QWORD *)this) != 13
      && *(_WORD *)(v7 + 2LL * *(_QWORD *)this) != 32 )
    {
      break;
    }
    *(_QWORD *)this = v8 + 1;
    if ( !v9 )
      *(_QWORD *)this = v8;
  }
  v10 = v8 + 1;
  *(_QWORD *)this = v8 + 1;
  if ( !v9 )
  {
    *(_QWORD *)this = v8;
LABEL_12:
    v11 = -2147024883;
    goto LABEL_84;
  }
  if ( v9 != 123 )
    goto LABEL_12;
  while ( 1 )
  {
    v12 = *(_WORD *)(v7 + 2 * v10);
    if ( v12 != 9 && *(_WORD *)(v7 + 2 * v10) != 10 && *(_WORD *)(v7 + 2 * v10) != 13 && *(_WORD *)(v7 + 2 * v10) != 32 )
      break;
    *(_QWORD *)this = v10 + 1;
    if ( v12 )
      ++v10;
    else
      *(_QWORD *)this = v10;
  }
  if ( v12 == 125 )
  {
    *a2 = v6;
    *(_QWORD *)this = v10 + 1;
    goto LABEL_22;
  }
  do
  {
    v13 = *((_QWORD *)this + 1);
    v53 = 0;
    v55 = 0;
    lpMem = 0;
    while ( 1 )
    {
      v14 = *(_WORD *)(v13 + 2 * v10);
      if ( v14 != 9
        && *(_WORD *)(v13 + 2 * v10) != 10
        && *(_WORD *)(v13 + 2 * v10) != 13
        && *(_WORD *)(v13 + 2 * v10) != 32 )
      {
        break;
      }
      *(_QWORD *)this = v10 + 1;
      if ( v14 )
        ++v10;
      else
        *(_QWORD *)this = v10;
    }
    StringFromStreamAlloc = JsonHelpersInternal::JsonReader::ReadStringFromStreamAlloc(
                              this,
                              (const unsigned __int16 **)&lpMem);
    v16 = (wchar_t *)lpMem;
    v11 = StringFromStreamAlloc;
    if ( StringFromStreamAlloc >= 0 )
    {
      v17 = *((_QWORD *)this + 1);
      while ( 1 )
      {
        v18 = *(_QWORD *)this;
        v19 = *(_WORD *)(v17 + 2LL * *(_QWORD *)this);
        if ( v19 != 9
          && *(_WORD *)(v17 + 2LL * *(_QWORD *)this) != 10
          && *(_WORD *)(v17 + 2LL * *(_QWORD *)this) != 13
          && *(_WORD *)(v17 + 2LL * *(_QWORD *)this) != 32 )
        {
          break;
        }
        *(_QWORD *)this = v18 + 1;
        if ( !v19 )
          *(_QWORD *)this = v18;
      }
      *(_QWORD *)this = v18 + 1;
      if ( !v19 )
      {
        *(_QWORD *)this = v18;
LABEL_41:
        v11 = -2147024883;
        goto LABEL_42;
      }
      if ( v19 != 58 )
        goto LABEL_41;
      v11 = JsonHelpersInternal::JsonReader::ReadJsonValueAlloc(this, &v55);
      if ( v11 >= 0 )
      {
        ProcessHeap = GetProcessHeap();
        v24 = HeapAlloc(ProcessHeap, 0, 0x10u);
        if ( v24 )
        {
          v25 = -1;
          do
            ++v25;
          while ( v16[v25] );
          v26 = v25 + 1;
          v27 = 2 * (v25 + 1);
          v28 = GetProcessHeap();
          v29 = (wchar_t *)HeapAlloc(v28, 0, v27);
          v30 = v29;
          if ( v29 )
          {
            wcscpy_s(v29, v26, v16);
            v32 = v55;
            v4 = v24;
            *v24 = v30;
            v11 = 0;
            v24[1] = v32;
            v56 = v24;
            v55 = 0;
            v51 = (struct JsonKeyValuePair *)v24;
            v53 = 0;
          }
          else
          {
            v31 = GetProcessHeap();
            HeapFree(v31, 0, v24);
            v4 = v56;
            v11 = -2147024882;
          }
        }
        else
        {
          v11 = -2147024882;
        }
      }
    }
LABEL_42:
    CleanupJsonKeyValuePair((void ***)&v53);
    CleanupJsonValue(&v55);
    if ( v16 )
    {
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v16);
    }
    if ( v11 < 0 )
      goto LABEL_84;
    v21 = *(_QWORD *)(v6 + 16);
    if ( v21 >= *(_QWORD *)(v6 + 24) )
    {
      v22 = v21 + 1;
      if ( v21 + 1 <= *(_QWORD *)(v6 + 24) )
      {
        v11 = -2147024809;
        goto LABEL_84;
      }
      v33 = *(_QWORD *)(v6 + 32) - 1LL;
      if ( v33 + v22 < v22 )
        goto LABEL_76;
      v35 = *(_QWORD *)(v6 + 24);
      v36 = *(_QWORD *)(v6 + 8);
      v34 = v35 * (unsigned __int128)v36;
      v55 = 0;
      if ( !is_mul_ok(v35, v36)
        || (*(_QWORD *)&v34 = *(_QWORD *)(v6 + 8),
            v37 = (v33 + v22) & ~v33,
            v55 = (struct JsonValue *)*((_QWORD *)&v34 + 1),
            v39 = v34,
            v38 = v37 * (unsigned __int128)(unsigned __int64)v34,
            v40 = v38,
            !is_mul_ok(v37, v39)) )
      {
LABEL_76:
        v11 = -2147483637;
        goto LABEL_84;
      }
      v41 = *(void **)(v6 + 40);
      v42 = *(void **)v6;
      if ( v41 )
      {
        v44 = HeapReAlloc(v42, DWORD2(v38), v41, v38);
      }
      else
      {
        v43 = HeapAlloc(v42, DWORD2(v38), v38);
        v44 = v43;
        if ( v43 )
          memset_0(v43, 0, v40);
      }
      if ( !v44 )
      {
        v11 = -2147024882;
        goto LABEL_84;
      }
      v4 = v56;
      *(_QWORD *)(v6 + 40) = v44;
      *(_QWORD *)(v6 + 24) = v37;
    }
    v55 = 0;
    if ( !is_mul_ok(*(_QWORD *)(v6 + 8), v21)
      || (v45 = (_QWORD *)(*(_QWORD *)(v6 + 40) + *(_QWORD *)(v6 + 8) * v21),
          (unsigned __int64)v45 < *(_QWORD *)(v6 + 40)) )
    {
      v11 = -2147483637;
      goto LABEL_84;
    }
    *v45 = v4;
    ++*(_QWORD *)(v6 + 16);
    v46 = *((_QWORD *)this + 1);
    v4 = 0;
    v56 = 0;
    v51 = 0;
    while ( 1 )
    {
      v47 = *(_QWORD *)this;
      v48 = *(_WORD *)(v46 + 2LL * *(_QWORD *)this);
      if ( v48 != 9
        && *(_WORD *)(v46 + 2LL * *(_QWORD *)this) != 10
        && *(_WORD *)(v46 + 2LL * *(_QWORD *)this) != 13
        && *(_WORD *)(v46 + 2LL * *(_QWORD *)this) != 32 )
      {
        break;
      }
      *(_QWORD *)this = v47 + 1;
      if ( !v48 )
        *(_QWORD *)this = v47;
    }
    v10 = v47 + 1;
    *(_QWORD *)this = v47 + 1;
    if ( !v48 )
    {
      *(_QWORD *)this = v47;
      goto LABEL_12;
    }
  }
  while ( v48 == 44 );
  if ( v48 != 125 )
    goto LABEL_12;
  *a2 = v6;
LABEL_22:
  v50 = 0;
  v11 = 0;
LABEL_84:
  CleanupJsonObject(&v50);
  CleanupJsonKeyValuePair((void ***)&v51);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180045018  mov     [rsp-38h+arg_0], rbx
0x18004501d  mov     [rsp-38h+arg_8], rdx
0x180045022  push    rbp
0x180045023  push    rsi
0x180045024  push    rdi
0x180045025  push    r12
0x180045027  push    r13
0x180045029  push    r14
0x18004502b  push    r15
0x18004502d  mov     rbp, rsp
0x180045030  sub     rsp, 40h
0x180045034  xor     r13d, r13d
0x180045037  mov     rsi, rcx
0x18004503a  mov     rbx, rdx
0x18004503d  mov     [rbp+var_20], r13
0x180045041  mov     r15d, r13d
0x180045044  mov     [rbp+arg_18], r13
0x180045048  mov     [rbp+var_18], r13
0x18004504c  lea     ecx, [r13+30h]; Size
0x180045050  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045055  mov     rdi, rax
0x180045058  test    rax, rax
0x18004505b  jz      loc_180045483
0x180045061  xorps   xmm0, xmm0
0x180045064  movups  xmmword ptr [rax], xmm0
0x180045067  movups  xmmword ptr [rax+10h], xmm0
0x18004506b  movups  xmmword ptr [rax+20h], xmm0
0x18004506f  call    cs:__imp_GetProcessHeap
0x180045075  xorps   xmm0, xmm0
0x180045078  lea     r12d, [r13+10h]
0x18004507c  movups  xmmword ptr [rdi], xmm0
0x18004507f  lea     r14d, [r13+8]
0x180045083  movups  xmmword ptr [rdi+10h], xmm0
0x180045087  movups  xmmword ptr [rdi+20h], xmm0
0x18004508b  call    cs:__imp_GetProcessHeap
0x180045091  mov     [rdi], rax
0x180045094  mov     [rdi+20h], r12
0x180045098  mov     [rdi+10h], r13
0x18004509c  mov     [rdi+18h], r13
0x1800450a0  mov     [rdi+28h], r13
0x1800450a4  mov     [rdi+8], r14
0x1800450a8  mov     r9, [rsi+8]
0x1800450ac  mov     [rbp+var_20], rdi
0x1800450b0  mov     rdx, [rsi]
0x1800450b3  movzx   r8d, word ptr [r9+rdx*2]
0x1800450b8  mov     ecx, r8d
0x1800450bb  sub     ecx, 9
0x1800450be  jz      short loc_1800450CF
0x1800450c0  sub     ecx, 1
0x1800450c3  jz      short loc_1800450CF
0x1800450c5  sub     ecx, 3
0x1800450c8  jz      short loc_1800450CF
0x1800450ca  cmp     ecx, 13h
0x1800450cd  jnz     short loc_1800450E1
0x1800450cf  lea     rax, [rdx+1]
0x1800450d3  mov     [rsi], rax
0x1800450d6  cmp     r13w, r8w
0x1800450da  jnz     short loc_1800450B0
0x1800450dc  mov     [rsi], rdx
0x1800450df  jmp     short loc_1800450B0
0x1800450e1  lea     rcx, [rdx+1]
0x1800450e5  mov     [rsi], rcx
0x1800450e8  cmp     r13w, r8w
0x1800450ec  jnz     short loc_1800450F3
0x1800450ee  mov     [rsi], rdx
0x1800450f1  jmp     short loc_1800450FE
0x1800450f3  mov     eax, 7Bh ; '{'
0x1800450f8  cmp     ax, r8w
0x1800450fc  jz      short loc_180045108
0x1800450fe  mov     ebx, 8007000Dh
0x180045103  jmp     loc_180045488
0x180045108  movzx   r8d, word ptr [r9+rcx*2]
0x18004510d  mov     edx, r8d
0x180045110  sub     edx, 9
0x180045113  jz      short loc_180045124
0x180045115  sub     edx, 1
0x180045118  jz      short loc_180045124
0x18004511a  sub     edx, 3
0x18004511d  jz      short loc_180045124
0x18004511f  cmp     edx, 13h
0x180045122  jnz     short loc_18004513B
0x180045124  lea     rdx, [rcx+1]
0x180045128  mov     [rsi], rdx
0x18004512b  cmp     r13w, r8w
0x18004512f  jnz     short loc_180045136
0x180045131  mov     [rsi], rcx
0x180045134  jmp     short loc_180045108
0x180045136  mov     rcx, rdx
0x180045139  jmp     short loc_180045108
0x18004513b  mov     eax, 7Dh ; '}'
0x180045140  cmp     ax, r8w
0x180045144  jnz     short loc_18004515C
0x180045146  lea     rax, [rcx+1]
0x18004514a  mov     [rbx], rdi
0x18004514d  mov     [rsi], rax
0x180045150  mov     [rbp+var_20], r13
0x180045154  mov     ebx, r13d
0x180045157  jmp     loc_180045488
0x18004515c  mov     r9, [rsi+8]
0x180045160  mov     [rbp+var_8], r13
0x180045164  mov     [rbp+arg_10], r13
0x180045168  mov     [rbp+lpMem], r13
0x18004516c  movzx   r8d, word ptr [r9+rcx*2]
0x180045171  mov     edx, r8d
0x180045174  sub     edx, 9
0x180045177  jz      short loc_180045188
0x180045179  sub     edx, 1
0x18004517c  jz      short loc_180045188
0x18004517e  sub     edx, 3
0x180045181  jz      short loc_180045188
0x180045183  cmp     edx, 13h
0x180045186  jnz     short loc_18004519F
0x180045188  lea     rdx, [rcx+1]
0x18004518c  mov     [rsi], rdx
0x18004518f  cmp     r13w, r8w
0x180045193  jnz     short loc_18004519A
0x180045195  mov     [rsi], rcx
0x180045198  jmp     short loc_18004516C
0x18004519a  mov     rcx, rdx
0x18004519d  jmp     short loc_18004516C
0x18004519f  lea     rdx, [rbp+lpMem]; unsigned __int16 **
0x1800451a3  mov     rcx, rsi; this
0x1800451a6  call    ?ReadStringFromStreamAlloc@JsonReader@JsonHelpersInternal@@AEAAJPEAPEBG@Z; JsonHelpersInternal::JsonReader::ReadStringFromStreamAlloc(ushort const * *)
0x1800451ab  mov     r12, [rbp+lpMem]
0x1800451af  mov     ebx, eax
0x1800451b1  test    eax, eax
0x1800451b3  js      short loc_1800451FF
0x1800451b5  mov     r9, [rsi+8]
0x1800451b9  mov     rdx, [rsi]
0x1800451bc  movzx   r8d, word ptr [r9+rdx*2]
0x1800451c1  mov     ecx, r8d
0x1800451c4  sub     ecx, 9
0x1800451c7  jz      short loc_1800451D8
0x1800451c9  sub     ecx, 1
0x1800451cc  jz      short loc_1800451D8
0x1800451ce  sub     ecx, 3
0x1800451d1  jz      short loc_1800451D8
0x1800451d3  cmp     ecx, 13h
0x1800451d6  jnz     short loc_1800451EA
0x1800451d8  lea     rax, [rdx+1]
0x1800451dc  mov     [rsi], rax
0x1800451df  cmp     r13w, r8w
0x1800451e3  jnz     short loc_1800451B9
0x1800451e5  mov     [rsi], rdx
0x1800451e8  jmp     short loc_1800451B9
0x1800451ea  lea     rax, [rdx+1]
0x1800451ee  mov     [rsi], rax
0x1800451f1  cmp     r13w, r8w
0x1800451f5  jnz     short loc_180045258
0x1800451f7  mov     [rsi], rdx
0x1800451fa  mov     ebx, 8007000Dh
0x1800451ff  lea     rcx, [rbp+var_8]; struct JsonKeyValuePair **
0x180045203  call    ?CleanupJsonKeyValuePair@@YAXPEAPEAUJsonKeyValuePair@@@Z; CleanupJsonKeyValuePair(JsonKeyValuePair * *)
0x180045208  lea     rcx, [rbp+arg_10]; struct JsonValue **
0x18004520c  call    ?CleanupJsonValue@@YAXPEAPEAUJsonValue@@@Z; CleanupJsonValue(JsonValue * *)
0x180045211  test    r12, r12
0x180045214  jz      short loc_18004522A
0x180045216  call    cs:__imp_GetProcessHeap
0x18004521c  mov     r8, r12; lpMem
0x18004521f  xor     edx, edx; dwFlags
0x180045221  mov     rcx, rax; hHeap
0x180045224  call    cs:__imp_HeapFree
0x18004522a  test    ebx, ebx
0x18004522c  js      loc_180045488
0x180045232  mov     r13, [rdi+10h]
0x180045236  cmp     r13, [rdi+18h]
0x18004523a  jb      loc_1800453C2
0x180045240  lea     rcx, [r13+1]
0x180045244  cmp     rcx, [rdi+18h]
0x180045248  ja      loc_180045325
0x18004524e  mov     ebx, 80070057h
0x180045253  jmp     loc_180045436
0x180045258  mov     eax, 3Ah ; ':'
0x18004525d  cmp     ax, r8w
0x180045261  jnz     short loc_1800451FA
0x180045263  lea     rdx, [rbp+arg_10]; struct JsonValue **
0x180045267  mov     rcx, rsi; this
0x18004526a  call    ?ReadJsonValueAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAUJsonValue@@@Z; JsonHelpersInternal::JsonReader::ReadJsonValueAlloc(JsonValue * *)
0x18004526f  mov     ebx, eax
0x180045271  test    eax, eax
0x180045273  js      short loc_1800451FF
0x180045275  call    cs:__imp_GetProcessHeap
0x18004527b  xor     edx, edx; dwFlags
0x18004527d  mov     rcx, rax; hHeap
0x180045280  lea     r8d, [rdx+10h]; dwBytes
0x180045284  call    cs:__imp_HeapAlloc
0x18004528a  mov     r14, rax
0x18004528d  test    rax, rax
0x180045290  jnz     short loc_18004529C
0x180045292  mov     ebx, 8007000Eh
0x180045297  jmp     loc_1800451FF
0x18004529c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800452a0  inc     rax
0x1800452a3  cmp     [r12+rax*2], r13w
0x1800452a8  jnz     short loc_1800452A0
0x1800452aa  lea     r15, [rax+1]
0x1800452ae  lea     rbx, [r15+r15]
0x1800452b2  call    cs:__imp_GetProcessHeap
0x1800452b8  mov     r8, rbx; dwBytes
0x1800452bb  xor     edx, edx; dwFlags
0x1800452bd  mov     rcx, rax; hHeap
0x1800452c0  call    cs:__imp_HeapAlloc
0x1800452c6  mov     rbx, rax
0x1800452c9  test    rax, rax
0x1800452cc  jnz     short loc_1800452F0
0x1800452ce  call    cs:__imp_GetProcessHeap
0x1800452d4  mov     r8, r14; lpMem
0x1800452d7  xor     edx, edx; dwFlags
0x1800452d9  mov     rcx, rax; hHeap
0x1800452dc  call    cs:__imp_HeapFree
0x1800452e2  mov     r15, [rbp+arg_18]
0x1800452e6  mov     ebx, 8007000Eh
0x1800452eb  jmp     loc_1800451FF
0x1800452f0  mov     r8, r12; Source
0x1800452f3  mov     rdx, r15; SizeInWords
0x1800452f6  mov     rcx, rbx; Destination
0x1800452f9  call    cs:__imp_wcscpy_s
0x1800452ff  mov     rax, [rbp+arg_10]
0x180045303  mov     r15, r14
0x180045306  mov     [r14], rbx
0x180045309  mov     ebx, r13d
0x18004530c  mov     [r14+8], rax
0x180045310  mov     [rbp+arg_18], r14
0x180045314  mov     [rbp+arg_10], r13
0x180045318  mov     [rbp+var_18], r14
0x18004531c  mov     [rbp+var_8], r13
0x180045320  jmp     loc_1800451FF
0x180045325  mov     r14, [rdi+20h]
0x180045329  dec     r14
0x18004532c  lea     r8, [r14+rcx]
0x180045330  cmp     r8, rcx
0x180045333  jb      loc_180045431
0x180045339  mov     rax, [rdi+8]
0x18004533d  mul     qword ptr [rdi+18h]
0x180045341  mov     [rbp+arg_10], 0
0x180045349  test    rdx, rdx
0x18004534c  jnz     loc_180045431
0x180045352  mov     rax, [rdi+8]
0x180045356  not     r14
0x180045359  and     r14, r8
0x18004535c  mov     [rbp+arg_10], rdx
0x180045360  mul     r14
0x180045363  mov     r15, rax
0x180045366  test    rdx, rdx
0x180045369  jnz     loc_180045431
0x18004536f  mov     r8, [rdi+28h]; lpMem
0x180045373  mov     rcx, [rdi]; hHeap
0x180045376  test    r8, r8
0x180045379  jnz     short loc_18004539B
0x18004537b  mov     r8, rax; dwBytes
0x18004537e  call    cs:__imp_HeapAlloc
0x180045384  mov     rbx, rax
0x180045387  test    rax, rax
0x18004538a  jz      short loc_1800453A7
0x18004538c  mov     r8, r15; Size
0x18004538f  xor     edx, edx; Val
0x180045391  mov     rcx, rax; void *
0x180045394  call    memset_0
0x180045399  jmp     short loc_1800453A7
0x18004539b  mov     r9, r15; dwBytes
0x18004539e  call    cs:__imp_HeapReAlloc
0x1800453a4  mov     rbx, rax
0x1800453a7  test    rbx, rbx
0x1800453aa  jnz     short loc_1800453B6
0x1800453ac  mov     ebx, 8007000Eh
0x1800453b1  jmp     loc_180045436
0x1800453b6  mov     r15, [rbp+arg_18]
0x1800453ba  mov     [rdi+28h], rbx
0x1800453be  mov     [rdi+18h], r14
0x1800453c2  mov     rax, r13
0x1800453c5  mov     [rbp+arg_10], 0
0x1800453cd  mul     qword ptr [rdi+8]
0x1800453d1  xor     r13d, r13d
0x1800453d4  test    rdx, rdx
0x1800453d7  jnz     loc_18004547C
0x1800453dd  add     rax, [rdi+28h]
0x1800453e1  cmp     rax, [rdi+28h]
0x1800453e5  jb      loc_18004547C
0x1800453eb  mov     [rax], r15
0x1800453ee  inc     qword ptr [rdi+10h]
0x1800453f2  mov     r9, [rsi+8]
0x1800453f6  mov     r15, r13
0x1800453f9  mov     [rbp+arg_18], r13
0x1800453fd  mov     [rbp+var_18], r13
0x180045401  mov     r8, [rsi]
0x180045404  movzx   edx, word ptr [r9+r8*2]
0x180045409  mov     ecx, edx
0x18004540b  sub     ecx, 9
0x18004540e  jz      short loc_18004541F
0x180045410  sub     ecx, 1
0x180045413  jz      short loc_18004541F
0x180045415  sub     ecx, 3
0x180045418  jz      short loc_18004541F
0x18004541a  cmp     ecx, 13h
0x18004541d  jnz     short loc_18004543F
0x18004541f  lea     rax, [r8+1]
0x180045423  mov     [rsi], rax
0x180045426  cmp     r13w, dx
0x18004542a  jnz     short loc_180045401
0x18004542c  mov     [rsi], r8
  ... truncated ...
```
