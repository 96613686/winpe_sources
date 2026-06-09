# JsonHelpersInternal::JsonReader::ReadJsonObjectAlloc(RtlArray<JsonKeyValuePair *> * *)

- ea: `0x18001faec`
- end: `0x18001ff88`
- name: `?ReadJsonObjectAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z`
- size: `1180`
- prototype: `__int64 __fastcall(JsonHelpersInternal::JsonReader *this, __int64 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001ec50`
- `0x18001ff90`

## callees

- `0x180001784`
- `0x18001a354`
- `0x18001a3d0`
- `0x18001a474`
- `0x18001faec`
- `0x18001ff90`
- `0x1800209f8`
- `0x1800322d2`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001fdcd`
- `msvcrt!wcscpy_s` at `0x18001fdcd`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001fe72`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001fe72`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fd58`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fd94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fe52`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fd58`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fd94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fe52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fb43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fb5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fcea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fda2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fb43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fb5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fcea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fda2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fcf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fdb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fcf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fdb0`

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
0x18001faec  mov     [rsp-38h+arg_0], rbx
0x18001faf1  mov     [rsp-38h+arg_8], rdx
0x18001faf6  push    rbp
0x18001faf7  push    rsi
0x18001faf8  push    rdi
0x18001faf9  push    r12
0x18001fafb  push    r13
0x18001fafd  push    r14
0x18001faff  push    r15
0x18001fb01  mov     rbp, rsp
0x18001fb04  sub     rsp, 40h
0x18001fb08  xor     r13d, r13d
0x18001fb0b  mov     rsi, rcx
0x18001fb0e  mov     rbx, rdx
0x18001fb11  mov     [rbp+var_20], r13
0x18001fb15  mov     r15d, r13d
0x18001fb18  mov     [rbp+arg_18], r13
0x18001fb1c  mov     [rbp+var_18], r13
0x18001fb20  lea     ecx, [r13+30h]; Size
0x18001fb24  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fb29  mov     rdi, rax
0x18001fb2c  test    rax, rax
0x18001fb2f  jz      loc_18001FF57
0x18001fb35  xorps   xmm0, xmm0
0x18001fb38  movups  xmmword ptr [rax], xmm0
0x18001fb3b  movups  xmmword ptr [rax+10h], xmm0
0x18001fb3f  movups  xmmword ptr [rax+20h], xmm0
0x18001fb43  call    cs:__imp_GetProcessHeap
0x18001fb49  xorps   xmm0, xmm0
0x18001fb4c  lea     r12d, [r13+10h]
0x18001fb50  movups  xmmword ptr [rdi], xmm0
0x18001fb53  lea     r14d, [r13+8]
0x18001fb57  movups  xmmword ptr [rdi+10h], xmm0
0x18001fb5b  movups  xmmword ptr [rdi+20h], xmm0
0x18001fb5f  call    cs:__imp_GetProcessHeap
0x18001fb65  mov     [rdi], rax
0x18001fb68  mov     [rdi+20h], r12
0x18001fb6c  mov     [rdi+10h], r13
0x18001fb70  mov     [rdi+18h], r13
0x18001fb74  mov     [rdi+28h], r13
0x18001fb78  mov     [rdi+8], r14
0x18001fb7c  mov     r9, [rsi+8]
0x18001fb80  mov     [rbp+var_20], rdi
0x18001fb84  mov     rdx, [rsi]
0x18001fb87  movzx   r8d, word ptr [r9+rdx*2]
0x18001fb8c  mov     ecx, r8d
0x18001fb8f  sub     ecx, 9
0x18001fb92  jz      short loc_18001FBA3
0x18001fb94  sub     ecx, 1
0x18001fb97  jz      short loc_18001FBA3
0x18001fb99  sub     ecx, 3
0x18001fb9c  jz      short loc_18001FBA3
0x18001fb9e  cmp     ecx, 13h
0x18001fba1  jnz     short loc_18001FBB5
0x18001fba3  lea     rax, [rdx+1]
0x18001fba7  mov     [rsi], rax
0x18001fbaa  cmp     r13w, r8w
0x18001fbae  jnz     short loc_18001FB84
0x18001fbb0  mov     [rsi], rdx
0x18001fbb3  jmp     short loc_18001FB84
0x18001fbb5  lea     rcx, [rdx+1]
0x18001fbb9  mov     [rsi], rcx
0x18001fbbc  cmp     r13w, r8w
0x18001fbc0  jnz     short loc_18001FBC7
0x18001fbc2  mov     [rsi], rdx
0x18001fbc5  jmp     short loc_18001FBD2
0x18001fbc7  mov     eax, 7Bh ; '{'
0x18001fbcc  cmp     ax, r8w
0x18001fbd0  jz      short loc_18001FBDC
0x18001fbd2  mov     ebx, 8007000Dh
0x18001fbd7  jmp     loc_18001FF5C
0x18001fbdc  movzx   r8d, word ptr [r9+rcx*2]
0x18001fbe1  mov     edx, r8d
0x18001fbe4  sub     edx, 9
0x18001fbe7  jz      short loc_18001FBF8
0x18001fbe9  sub     edx, 1
0x18001fbec  jz      short loc_18001FBF8
0x18001fbee  sub     edx, 3
0x18001fbf1  jz      short loc_18001FBF8
0x18001fbf3  cmp     edx, 13h
0x18001fbf6  jnz     short loc_18001FC0F
0x18001fbf8  lea     rdx, [rcx+1]
0x18001fbfc  mov     [rsi], rdx
0x18001fbff  cmp     r13w, r8w
0x18001fc03  jnz     short loc_18001FC0A
0x18001fc05  mov     [rsi], rcx
0x18001fc08  jmp     short loc_18001FBDC
0x18001fc0a  mov     rcx, rdx
0x18001fc0d  jmp     short loc_18001FBDC
0x18001fc0f  mov     eax, 7Dh ; '}'
0x18001fc14  cmp     ax, r8w
0x18001fc18  jnz     short loc_18001FC30
0x18001fc1a  lea     rax, [rcx+1]
0x18001fc1e  mov     [rbx], rdi
0x18001fc21  mov     [rsi], rax
0x18001fc24  mov     [rbp+var_20], r13
0x18001fc28  mov     ebx, r13d
0x18001fc2b  jmp     loc_18001FF5C
0x18001fc30  mov     r9, [rsi+8]
0x18001fc34  mov     [rbp+var_8], r13
0x18001fc38  mov     [rbp+arg_10], r13
0x18001fc3c  mov     [rbp+lpMem], r13
0x18001fc40  movzx   r8d, word ptr [r9+rcx*2]
0x18001fc45  mov     edx, r8d
0x18001fc48  sub     edx, 9
0x18001fc4b  jz      short loc_18001FC5C
0x18001fc4d  sub     edx, 1
0x18001fc50  jz      short loc_18001FC5C
0x18001fc52  sub     edx, 3
0x18001fc55  jz      short loc_18001FC5C
0x18001fc57  cmp     edx, 13h
0x18001fc5a  jnz     short loc_18001FC73
0x18001fc5c  lea     rdx, [rcx+1]
0x18001fc60  mov     [rsi], rdx
0x18001fc63  cmp     r13w, r8w
0x18001fc67  jnz     short loc_18001FC6E
0x18001fc69  mov     [rsi], rcx
0x18001fc6c  jmp     short loc_18001FC40
0x18001fc6e  mov     rcx, rdx
0x18001fc71  jmp     short loc_18001FC40
0x18001fc73  lea     rdx, [rbp+lpMem]; unsigned __int16 **
0x18001fc77  mov     rcx, rsi; this
0x18001fc7a  call    ?ReadStringFromStreamAlloc@JsonReader@JsonHelpersInternal@@AEAAJPEAPEBG@Z; JsonHelpersInternal::JsonReader::ReadStringFromStreamAlloc(ushort const * *)
0x18001fc7f  mov     r12, [rbp+lpMem]
0x18001fc83  mov     ebx, eax
0x18001fc85  test    eax, eax
0x18001fc87  js      short loc_18001FCD3
0x18001fc89  mov     r9, [rsi+8]
0x18001fc8d  mov     rdx, [rsi]
0x18001fc90  movzx   r8d, word ptr [r9+rdx*2]
0x18001fc95  mov     ecx, r8d
0x18001fc98  sub     ecx, 9
0x18001fc9b  jz      short loc_18001FCAC
0x18001fc9d  sub     ecx, 1
0x18001fca0  jz      short loc_18001FCAC
0x18001fca2  sub     ecx, 3
0x18001fca5  jz      short loc_18001FCAC
0x18001fca7  cmp     ecx, 13h
0x18001fcaa  jnz     short loc_18001FCBE
0x18001fcac  lea     rax, [rdx+1]
0x18001fcb0  mov     [rsi], rax
0x18001fcb3  cmp     r13w, r8w
0x18001fcb7  jnz     short loc_18001FC8D
0x18001fcb9  mov     [rsi], rdx
0x18001fcbc  jmp     short loc_18001FC8D
0x18001fcbe  lea     rax, [rdx+1]
0x18001fcc2  mov     [rsi], rax
0x18001fcc5  cmp     r13w, r8w
0x18001fcc9  jnz     short loc_18001FD2C
0x18001fccb  mov     [rsi], rdx
0x18001fcce  mov     ebx, 8007000Dh
0x18001fcd3  lea     rcx, [rbp+var_8]; struct JsonKeyValuePair **
0x18001fcd7  call    ?CleanupJsonKeyValuePair@@YAXPEAPEAUJsonKeyValuePair@@@Z; CleanupJsonKeyValuePair(JsonKeyValuePair * *)
0x18001fcdc  lea     rcx, [rbp+arg_10]; struct JsonValue **
0x18001fce0  call    ?CleanupJsonValue@@YAXPEAPEAUJsonValue@@@Z; CleanupJsonValue(JsonValue * *)
0x18001fce5  test    r12, r12
0x18001fce8  jz      short loc_18001FCFE
0x18001fcea  call    cs:__imp_GetProcessHeap
0x18001fcf0  mov     r8, r12; lpMem
0x18001fcf3  xor     edx, edx; dwFlags
0x18001fcf5  mov     rcx, rax; hHeap
0x18001fcf8  call    cs:__imp_HeapFree
0x18001fcfe  test    ebx, ebx
0x18001fd00  js      loc_18001FF5C
0x18001fd06  mov     r13, [rdi+10h]
0x18001fd0a  cmp     r13, [rdi+18h]
0x18001fd0e  jb      loc_18001FE96
0x18001fd14  lea     rcx, [r13+1]
0x18001fd18  cmp     rcx, [rdi+18h]
0x18001fd1c  ja      loc_18001FDF9
0x18001fd22  mov     ebx, 80070057h
0x18001fd27  jmp     loc_18001FF0A
0x18001fd2c  mov     eax, 3Ah ; ':'
0x18001fd31  cmp     ax, r8w
0x18001fd35  jnz     short loc_18001FCCE
0x18001fd37  lea     rdx, [rbp+arg_10]; struct JsonValue **
0x18001fd3b  mov     rcx, rsi; this
0x18001fd3e  call    ?ReadJsonValueAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAUJsonValue@@@Z; JsonHelpersInternal::JsonReader::ReadJsonValueAlloc(JsonValue * *)
0x18001fd43  mov     ebx, eax
0x18001fd45  test    eax, eax
0x18001fd47  js      short loc_18001FCD3
0x18001fd49  call    cs:__imp_GetProcessHeap
0x18001fd4f  xor     edx, edx; dwFlags
0x18001fd51  mov     rcx, rax; hHeap
0x18001fd54  lea     r8d, [rdx+10h]; dwBytes
0x18001fd58  call    cs:__imp_HeapAlloc
0x18001fd5e  mov     r14, rax
0x18001fd61  test    rax, rax
0x18001fd64  jnz     short loc_18001FD70
0x18001fd66  mov     ebx, 8007000Eh
0x18001fd6b  jmp     loc_18001FCD3
0x18001fd70  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fd74  inc     rax
0x18001fd77  cmp     [r12+rax*2], r13w
0x18001fd7c  jnz     short loc_18001FD74
0x18001fd7e  lea     r15, [rax+1]
0x18001fd82  lea     rbx, [r15+r15]
0x18001fd86  call    cs:__imp_GetProcessHeap
0x18001fd8c  mov     r8, rbx; dwBytes
0x18001fd8f  xor     edx, edx; dwFlags
0x18001fd91  mov     rcx, rax; hHeap
0x18001fd94  call    cs:__imp_HeapAlloc
0x18001fd9a  mov     rbx, rax
0x18001fd9d  test    rax, rax
0x18001fda0  jnz     short loc_18001FDC4
0x18001fda2  call    cs:__imp_GetProcessHeap
0x18001fda8  mov     r8, r14; lpMem
0x18001fdab  xor     edx, edx; dwFlags
0x18001fdad  mov     rcx, rax; hHeap
0x18001fdb0  call    cs:__imp_HeapFree
0x18001fdb6  mov     r15, [rbp+arg_18]
0x18001fdba  mov     ebx, 8007000Eh
0x18001fdbf  jmp     loc_18001FCD3
0x18001fdc4  mov     r8, r12; Source
0x18001fdc7  mov     rdx, r15; SizeInWords
0x18001fdca  mov     rcx, rbx; Destination
0x18001fdcd  call    cs:__imp_wcscpy_s
0x18001fdd3  mov     rax, [rbp+arg_10]
0x18001fdd7  mov     r15, r14
0x18001fdda  mov     [r14], rbx
0x18001fddd  mov     ebx, r13d
0x18001fde0  mov     [r14+8], rax
0x18001fde4  mov     [rbp+arg_18], r14
0x18001fde8  mov     [rbp+arg_10], r13
0x18001fdec  mov     [rbp+var_18], r14
0x18001fdf0  mov     [rbp+var_8], r13
0x18001fdf4  jmp     loc_18001FCD3
0x18001fdf9  mov     r14, [rdi+20h]
0x18001fdfd  dec     r14
0x18001fe00  lea     r8, [r14+rcx]
0x18001fe04  cmp     r8, rcx
0x18001fe07  jb      loc_18001FF05
0x18001fe0d  mov     rax, [rdi+8]
0x18001fe11  mul     qword ptr [rdi+18h]
0x18001fe15  mov     [rbp+arg_10], 0
0x18001fe1d  test    rdx, rdx
0x18001fe20  jnz     loc_18001FF05
0x18001fe26  mov     rax, [rdi+8]
0x18001fe2a  not     r14
0x18001fe2d  and     r14, r8
0x18001fe30  mov     [rbp+arg_10], rdx
0x18001fe34  mul     r14
0x18001fe37  mov     r15, rax
0x18001fe3a  test    rdx, rdx
0x18001fe3d  jnz     loc_18001FF05
0x18001fe43  mov     r8, [rdi+28h]; lpMem
0x18001fe47  mov     rcx, [rdi]; hHeap
0x18001fe4a  test    r8, r8
0x18001fe4d  jnz     short loc_18001FE6F
0x18001fe4f  mov     r8, rax; dwBytes
0x18001fe52  call    cs:__imp_HeapAlloc
0x18001fe58  mov     rbx, rax
0x18001fe5b  test    rax, rax
0x18001fe5e  jz      short loc_18001FE7B
0x18001fe60  mov     r8, r15; Size
0x18001fe63  xor     edx, edx; Val
0x18001fe65  mov     rcx, rax; void *
0x18001fe68  call    memset_0
0x18001fe6d  jmp     short loc_18001FE7B
0x18001fe6f  mov     r9, r15; dwBytes
0x18001fe72  call    cs:__imp_HeapReAlloc
0x18001fe78  mov     rbx, rax
0x18001fe7b  test    rbx, rbx
0x18001fe7e  jnz     short loc_18001FE8A
0x18001fe80  mov     ebx, 8007000Eh
0x18001fe85  jmp     loc_18001FF0A
0x18001fe8a  mov     r15, [rbp+arg_18]
0x18001fe8e  mov     [rdi+28h], rbx
0x18001fe92  mov     [rdi+18h], r14
0x18001fe96  mov     rax, r13
0x18001fe99  mov     [rbp+arg_10], 0
0x18001fea1  mul     qword ptr [rdi+8]
0x18001fea5  xor     r13d, r13d
0x18001fea8  test    rdx, rdx
0x18001feab  jnz     loc_18001FF50
0x18001feb1  add     rax, [rdi+28h]
0x18001feb5  cmp     rax, [rdi+28h]
0x18001feb9  jb      loc_18001FF50
0x18001febf  mov     [rax], r15
0x18001fec2  inc     qword ptr [rdi+10h]
0x18001fec6  mov     r9, [rsi+8]
0x18001feca  mov     r15, r13
0x18001fecd  mov     [rbp+arg_18], r13
0x18001fed1  mov     [rbp+var_18], r13
0x18001fed5  mov     r8, [rsi]
0x18001fed8  movzx   edx, word ptr [r9+r8*2]
0x18001fedd  mov     ecx, edx
0x18001fedf  sub     ecx, 9
0x18001fee2  jz      short loc_18001FEF3
0x18001fee4  sub     ecx, 1
0x18001fee7  jz      short loc_18001FEF3
0x18001fee9  sub     ecx, 3
0x18001feec  jz      short loc_18001FEF3
0x18001feee  cmp     ecx, 13h
0x18001fef1  jnz     short loc_18001FF13
0x18001fef3  lea     rax, [r8+1]
0x18001fef7  mov     [rsi], rax
0x18001fefa  cmp     r13w, dx
0x18001fefe  jnz     short loc_18001FED5
0x18001ff00  mov     [rsi], r8
  ... truncated ...
```
