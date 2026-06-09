# JsonHelpersInternal::JsonReader::ReadJsonValueListAlloc(RtlArray<JsonValue *> * *)

- ea: `0x18002043c`
- end: `0x180020720`
- name: `?ReadJsonValueListAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAV?$RtlArray@PEAUJsonValue@@@@@Z`
- size: `740`
- prototype: `__int64 __fastcall(JsonHelpersInternal::JsonReader *this, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001ff90`

## callees

- `0x180001784`
- `0x18001a474`
- `0x18001a510`
- `0x18001ff90`
- `0x18002043c`
- `0x1800322d2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18002061d`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18002061d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800205fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800205fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020488`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800204a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020488`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800204a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JsonHelpersInternal::JsonReader::ReadJsonValueListAlloc(
        JsonHelpersInternal::JsonReader *this,
        __int64 *a2)
{
  _OWORD *v4; // rax
  __int64 v5; // rbx
  __int64 v6; // r10
  __int64 v7; // r8
  __int16 v8; // r9
  __int64 v9; // rdx
  int v10; // edi
  __int16 v11; // r8
  unsigned __int64 v12; // r15
  unsigned __int64 v13; // rcx
  __int64 v14; // r14
  unsigned __int64 v15; // r14
  unsigned __int128 v16; // rax
  size_t v17; // r12
  void *v18; // r8
  void *v19; // rcx
  void *v20; // rax
  LPVOID v21; // rdi
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rcx
  __int64 v24; // r9
  __int64 v25; // rdx
  __int16 v26; // r8
  __int16 v27; // cx
  __int64 v29; // [rsp+80h] [rbp+50h] BYREF
  struct JsonValue *v30; // [rsp+88h] [rbp+58h] BYREF

  v29 = 0;
  v30 = 0;
  v4 = operator new(0x30u);
  v5 = (__int64)v4;
  if ( !v4 )
  {
    v10 = -2147024882;
    goto LABEL_54;
  }
  *v4 = 0;
  v4[1] = 0;
  v4[2] = 0;
  GetProcessHeap();
  *(_OWORD *)v5 = 0;
  *(_OWORD *)(v5 + 16) = 0;
  *(_OWORD *)(v5 + 32) = 0;
  *(_QWORD *)v5 = GetProcessHeap();
  *(_QWORD *)(v5 + 32) = 16;
  *(_QWORD *)(v5 + 16) = 0;
  *(_QWORD *)(v5 + 24) = 0;
  *(_QWORD *)(v5 + 40) = 0;
  *(_QWORD *)(v5 + 8) = 8;
  v6 = *((_QWORD *)this + 1);
  v29 = v5;
  while ( 1 )
  {
    v7 = *(_QWORD *)this;
    v8 = *(_WORD *)(v6 + 2LL * *(_QWORD *)this);
    if ( v8 != 9
      && *(_WORD *)(v6 + 2LL * *(_QWORD *)this) != 10
      && *(_WORD *)(v6 + 2LL * *(_QWORD *)this) != 13
      && *(_WORD *)(v6 + 2LL * *(_QWORD *)this) != 32 )
    {
      break;
    }
    *(_QWORD *)this = v7 + 1;
    if ( !v8 )
      *(_QWORD *)this = v7;
  }
  v9 = v7 + 1;
  *(_QWORD *)this = v7 + 1;
  if ( !v8 )
  {
    *(_QWORD *)this = v7;
LABEL_12:
    v10 = -2147024883;
    goto LABEL_54;
  }
  if ( v8 != 91 )
    goto LABEL_12;
  while ( 1 )
  {
    v11 = *(_WORD *)(v6 + 2 * v9);
    if ( v11 != 9 && *(_WORD *)(v6 + 2 * v9) != 10 && *(_WORD *)(v6 + 2 * v9) != 13 && *(_WORD *)(v6 + 2 * v9) != 32 )
      break;
    *(_QWORD *)this = v9 + 1;
    if ( v11 )
      ++v9;
    else
      *(_QWORD *)this = v9;
  }
  if ( v11 == 93 )
  {
    *(_QWORD *)this = v9 + 1;
LABEL_22:
    *a2 = v5;
    v10 = 0;
    v29 = 0;
  }
  else
  {
    while ( 1 )
    {
      v10 = JsonHelpersInternal::JsonReader::ReadJsonValueAlloc(this, &v30);
      if ( v10 < 0 )
        break;
      v12 = *(_QWORD *)(v5 + 16);
      if ( v12 >= *(_QWORD *)(v5 + 24) )
      {
        v13 = v12 + 1;
        if ( v12 + 1 <= *(_QWORD *)(v5 + 24) )
        {
          v10 = -2147024809;
          break;
        }
        v14 = *(_QWORD *)(v5 + 32) - 1LL;
        if ( v14 + v13 < v13
          || !is_mul_ok(*(_QWORD *)(v5 + 24), *(_QWORD *)(v5 + 8))
          || (v15 = (v14 + v13) & ~v14,
              v16 = v15 * (unsigned __int128)*(unsigned __int64 *)(v5 + 8),
              v17 = v15 * *(_QWORD *)(v5 + 8),
              !is_mul_ok(v15, *(_QWORD *)(v5 + 8))) )
        {
          v10 = -2147483637;
          break;
        }
        v18 = *(void **)(v5 + 40);
        v19 = *(void **)v5;
        if ( v18 )
        {
          v21 = HeapReAlloc(v19, DWORD2(v16), v18, v15 * *(_QWORD *)(v5 + 8));
        }
        else
        {
          v20 = HeapAlloc(v19, DWORD2(v16), v15 * *(_QWORD *)(v5 + 8));
          v21 = v20;
          if ( v20 )
            memset_0(v20, 0, v17);
        }
        if ( !v21 )
        {
          v10 = -2147024882;
          break;
        }
        *(_QWORD *)(v5 + 40) = v21;
        *(_QWORD *)(v5 + 24) = v15;
      }
      v22 = *(_QWORD *)(v5 + 8) * v12;
      if ( !is_mul_ok(*(_QWORD *)(v5 + 8), v12) || (v23 = *(_QWORD *)(v5 + 40), v23 + v22 < v23) )
      {
        v10 = -2147483637;
        break;
      }
      *(_QWORD *)(v23 + v22) = v30;
      ++*(_QWORD *)(v5 + 16);
      v24 = *((_QWORD *)this + 1);
      v30 = 0;
      while ( 1 )
      {
        v25 = *(_QWORD *)this;
        v26 = *(_WORD *)(v24 + 2LL * *(_QWORD *)this);
        if ( v26 != 9
          && *(_WORD *)(v24 + 2LL * *(_QWORD *)this) != 10
          && *(_WORD *)(v24 + 2LL * *(_QWORD *)this) != 13
          && *(_WORD *)(v24 + 2LL * *(_QWORD *)this) != 32 )
        {
          break;
        }
        *(_QWORD *)this = v25 + 1;
        if ( !v26 )
          *(_QWORD *)this = v25;
      }
      v27 = *(_WORD *)(v24 + 2 * v25);
      *(_QWORD *)this = v25 + 1;
      if ( !v27 )
      {
        *(_QWORD *)this = v25;
        goto LABEL_12;
      }
      if ( v27 != 44 )
      {
        if ( v27 != 93 )
          goto LABEL_12;
        goto LABEL_22;
      }
    }
  }
LABEL_54:
  CleanupJsonValueList(&v29);
  CleanupJsonValue(&v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002043c  mov     [rsp-38h+arg_0], rbx
0x180020441  push    rbp
0x180020442  push    rsi
0x180020443  push    rdi
0x180020444  push    r12
0x180020446  push    r13
0x180020448  push    r14
0x18002044a  push    r15
0x18002044c  mov     rbp, rsp
0x18002044f  sub     rsp, 30h
0x180020453  xor     r12d, r12d
0x180020456  mov     rsi, rcx
0x180020459  mov     r13, rdx
0x18002045c  mov     [rbp+arg_10], r12
0x180020460  mov     [rbp+arg_18], r12
0x180020464  lea     ecx, [r12+30h]; Size
0x180020469  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002046e  mov     rbx, rax
0x180020471  test    rax, rax
0x180020474  jz      loc_1800206F2
0x18002047a  xorps   xmm0, xmm0
0x18002047d  movups  xmmword ptr [rax], xmm0
0x180020480  movups  xmmword ptr [rax+10h], xmm0
0x180020484  movups  xmmword ptr [rax+20h], xmm0
0x180020488  call    cs:__imp_GetProcessHeap
0x18002048e  xorps   xmm0, xmm0
0x180020491  lea     edi, [r12+10h]
0x180020496  movups  xmmword ptr [rbx], xmm0
0x180020499  lea     r14d, [r12+8]
0x18002049e  movups  xmmword ptr [rbx+10h], xmm0
0x1800204a2  movups  xmmword ptr [rbx+20h], xmm0
0x1800204a6  call    cs:__imp_GetProcessHeap
0x1800204ac  mov     [rbx], rax
0x1800204af  mov     [rbx+20h], rdi
0x1800204b3  mov     [rbx+10h], r12
0x1800204b7  mov     [rbx+18h], r12
0x1800204bb  mov     [rbx+28h], r12
0x1800204bf  mov     [rbx+8], r14
0x1800204c3  mov     r10, [rsi+8]
0x1800204c7  mov     [rbp+arg_10], rbx
0x1800204cb  mov     r8, [rsi]
0x1800204ce  movzx   r9d, word ptr [r10+r8*2]
0x1800204d3  mov     ecx, r9d
0x1800204d6  sub     ecx, 9
0x1800204d9  jz      short loc_1800204EA
0x1800204db  sub     ecx, 1
0x1800204de  jz      short loc_1800204EA
0x1800204e0  sub     ecx, 3
0x1800204e3  jz      short loc_1800204EA
0x1800204e5  cmp     ecx, 13h
0x1800204e8  jnz     short loc_1800204FC
0x1800204ea  lea     rax, [r8+1]
0x1800204ee  mov     [rsi], rax
0x1800204f1  cmp     r12w, r9w
0x1800204f5  jnz     short loc_1800204CB
0x1800204f7  mov     [rsi], r8
0x1800204fa  jmp     short loc_1800204CB
0x1800204fc  lea     rdx, [r8+1]
0x180020500  mov     [rsi], rdx
0x180020503  cmp     r12w, r9w
0x180020507  jnz     short loc_18002050E
0x180020509  mov     [rsi], r8
0x18002050c  jmp     short loc_180020519
0x18002050e  mov     eax, 5Bh ; '['
0x180020513  cmp     ax, r9w
0x180020517  jz      short loc_180020523
0x180020519  mov     edi, 8007000Dh
0x18002051e  jmp     loc_1800206F7
0x180020523  movzx   r8d, word ptr [r10+rdx*2]
0x180020528  mov     ecx, r8d
0x18002052b  sub     ecx, 9
0x18002052e  jz      short loc_18002053F
0x180020530  sub     ecx, 1
0x180020533  jz      short loc_18002053F
0x180020535  sub     ecx, 3
0x180020538  jz      short loc_18002053F
0x18002053a  cmp     ecx, 13h
0x18002053d  jnz     short loc_180020556
0x18002053f  lea     rcx, [rdx+1]
0x180020543  mov     [rsi], rcx
0x180020546  cmp     r12w, r8w
0x18002054a  jnz     short loc_180020551
0x18002054c  mov     [rsi], rdx
0x18002054f  jmp     short loc_180020523
0x180020551  mov     rdx, rcx
0x180020554  jmp     short loc_180020523
0x180020556  mov     eax, 5Dh ; ']'
0x18002055b  cmp     ax, r8w
0x18002055f  jnz     short loc_180020578
0x180020561  lea     rax, [rdx+1]
0x180020565  mov     [rsi], rax
0x180020568  mov     [r13+0], rbx
0x18002056c  mov     edi, r12d
0x18002056f  mov     [rbp+arg_10], r12
0x180020573  jmp     loc_1800206F7
0x180020578  lea     rdx, [rbp+arg_18]; struct JsonValue **
0x18002057c  mov     rcx, rsi; this
0x18002057f  call    ?ReadJsonValueAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAUJsonValue@@@Z; JsonHelpersInternal::JsonReader::ReadJsonValueAlloc(JsonValue * *)
0x180020584  mov     edi, eax
0x180020586  test    eax, eax
0x180020588  js      loc_1800206F7
0x18002058e  mov     r15, [rbx+10h]
0x180020592  cmp     r15, [rbx+18h]
0x180020596  jb      loc_18002063D
0x18002059c  lea     rcx, [r15+1]
0x1800205a0  cmp     rcx, [rbx+18h]
0x1800205a4  ja      short loc_1800205B0
0x1800205a6  mov     edi, 80070057h
0x1800205ab  jmp     loc_1800206AA
0x1800205b0  mov     r14, [rbx+20h]
0x1800205b4  dec     r14
0x1800205b7  lea     r8, [r14+rcx]
0x1800205bb  cmp     r8, rcx
0x1800205be  jb      loc_1800206A5
0x1800205c4  mov     rax, [rbx+8]
0x1800205c8  mul     qword ptr [rbx+18h]
0x1800205cc  test    rdx, rdx
0x1800205cf  jnz     loc_1800206A5
0x1800205d5  mov     rax, [rbx+8]
0x1800205d9  not     r14
0x1800205dc  and     r14, r8
0x1800205df  mul     r14
0x1800205e2  mov     r12, rax
0x1800205e5  test    rdx, rdx
0x1800205e8  jnz     loc_1800206A2
0x1800205ee  mov     r8, [rbx+28h]; lpMem
0x1800205f2  mov     rcx, [rbx]; hHeap
0x1800205f5  test    r8, r8
0x1800205f8  jnz     short loc_18002061A
0x1800205fa  mov     r8, rax; dwBytes
0x1800205fd  call    cs:__imp_HeapAlloc
0x180020603  mov     rdi, rax
0x180020606  test    rax, rax
0x180020609  jz      short loc_180020626
0x18002060b  mov     r8, r12; Size
0x18002060e  xor     edx, edx; Val
0x180020610  mov     rcx, rax; void *
0x180020613  call    memset_0
0x180020618  jmp     short loc_180020626
0x18002061a  mov     r9, r12; dwBytes
0x18002061d  call    cs:__imp_HeapReAlloc
0x180020623  mov     rdi, rax
0x180020626  xor     r12d, r12d
0x180020629  test    rdi, rdi
0x18002062c  jnz     short loc_180020635
0x18002062e  mov     edi, 8007000Eh
0x180020633  jmp     short loc_1800206AA
0x180020635  mov     [rbx+28h], rdi
0x180020639  mov     [rbx+18h], r14
0x18002063d  mov     rax, r15
0x180020640  mul     qword ptr [rbx+8]
0x180020644  test    rdx, rdx
0x180020647  jnz     loc_1800206EB
0x18002064d  mov     rcx, [rbx+28h]
0x180020651  lea     rdx, [rcx+rax]
0x180020655  cmp     rdx, rcx
0x180020658  jb      loc_1800206EB
0x18002065e  mov     rax, [rbp+arg_18]
0x180020662  mov     [rdx], rax
0x180020665  inc     qword ptr [rbx+10h]
0x180020669  mov     r9, [rsi+8]
0x18002066d  mov     [rbp+arg_18], r12
0x180020671  mov     rdx, [rsi]
0x180020674  movzx   r8d, word ptr [r9+rdx*2]
0x180020679  mov     ecx, r8d
0x18002067c  sub     ecx, 9
0x18002067f  jz      short loc_180020690
0x180020681  sub     ecx, 1
0x180020684  jz      short loc_180020690
0x180020686  sub     ecx, 3
0x180020689  jz      short loc_180020690
0x18002068b  cmp     ecx, 13h
0x18002068e  jnz     short loc_1800206B0
0x180020690  lea     rax, [rdx+1]
0x180020694  mov     [rsi], rax
0x180020697  cmp     r12w, r8w
0x18002069b  jnz     short loc_180020671
0x18002069d  mov     [rsi], rdx
0x1800206a0  jmp     short loc_180020671
0x1800206a2  xor     r12d, r12d
0x1800206a5  mov     edi, 8000000Bh
0x1800206aa  test    edi, edi
0x1800206ac  js      short loc_1800206F7
0x1800206ae  jmp     short loc_180020669
0x1800206b0  movzx   ecx, word ptr [r9+rdx*2]
0x1800206b5  lea     rax, [rdx+1]
0x1800206b9  mov     [rsi], rax
0x1800206bc  cmp     r12w, cx
0x1800206c0  jz      short loc_1800206E3
0x1800206c2  mov     eax, 2Ch ; ','
0x1800206c7  cmp     ax, cx
0x1800206ca  jz      loc_180020578
0x1800206d0  mov     eax, 5Dh ; ']'
0x1800206d5  cmp     ax, cx
0x1800206d8  jnz     loc_180020519
0x1800206de  jmp     loc_180020568
0x1800206e3  mov     [rsi], rdx
0x1800206e6  jmp     loc_180020519
0x1800206eb  mov     edi, 8000000Bh
0x1800206f0  jmp     short loc_1800206F7
0x1800206f2  mov     edi, 8007000Eh
0x1800206f7  lea     rcx, [rbp+arg_10]
0x1800206fb  call    ?CleanupJsonValueList@@YAXPEAPEAV?$RtlArray@PEAUJsonValue@@@@@Z; CleanupJsonValueList(RtlArray<JsonValue *> * *)
0x180020700  lea     rcx, [rbp+arg_18]; struct JsonValue **
0x180020704  call    ?CleanupJsonValue@@YAXPEAPEAUJsonValue@@@Z; CleanupJsonValue(JsonValue * *)
0x180020709  mov     rbx, [rsp+30h+arg_0]
0x18002070e  mov     eax, edi
0x180020710  add     rsp, 30h
0x180020714  pop     r15
0x180020716  pop     r14
0x180020718  pop     r13
0x18002071a  pop     r12
0x18002071c  pop     rdi
0x18002071d  pop     rsi
0x18002071e  pop     rbp
0x18002071f  retn
```
