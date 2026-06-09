# JsonHelpersInternal::JsonReader::ReadJsonValueAlloc(JsonValue * *)

- ea: `0x1800454bc`
- end: `0x180045962`
- name: `?ReadJsonValueAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAUJsonValue@@@Z`
- size: `1190`
- prototype: `__int64 __fastcall(JsonHelpersInternal::JsonReader *__hidden this, struct JsonValue **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180045018`
- `0x180045968`

## callees

- `0x18001c548`
- `0x180040f28`
- `0x180040fcc`
- `0x180041068`
- `0x180044d40`
- `0x180045018`
- `0x1800454bc`
- `0x180045968`
- `0x180045f24`
- `0x180050300`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180045787`
- `msvcrt!_wcsicmp` at `0x1800457cc`
- `msvcrt!_wcsicmp` at `0x180045831`
- `msvcrt!_wcsicmp` at `0x180045787`
- `msvcrt!_wcsicmp` at `0x1800457cc`
- `msvcrt!_wcsicmp` at `0x180045831`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800455af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800455ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004560e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045627`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800456cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045791`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800457d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004583f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045885`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800458cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045928`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800455af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800455ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004560e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045627`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800456cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045791`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800457d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004583f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045885`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800458cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045928`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800455be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800455f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800456de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800457a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800457e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004584e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045894`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800458db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800455be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800455f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800456de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800457a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800457e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004584e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045894`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800458db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004561c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045635`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045936`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004561c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045635`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045936`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JsonHelpersInternal::JsonReader::ReadJsonValueAlloc(
        JsonHelpersInternal::JsonReader *this,
        struct JsonValue **a2)
{
  __int64 v2; // r9
  unsigned __int16 *v3; // r12
  __int64 v6; // r8
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  int StringFromStreamAlloc; // ebx
  HANDLE v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rsi
  __int64 v18; // rax
  unsigned __int64 v19; // r15
  SIZE_T v20; // rbx
  HANDLE v21; // rax
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // r14
  HANDLE v24; // rax
  HANDLE v25; // rax
  struct JsonValue *v26; // rdi
  __int64 v27; // rbx
  HANDLE v28; // rax
  struct JsonValue *v29; // rax
  __int64 v30; // r8
  wchar_t v31; // dx
  wchar_t v32; // dx
  wchar_t v33; // cx
  HANDLE v34; // rax
  struct JsonValue *v35; // rax
  HANDLE v36; // rax
  struct JsonValue *v37; // rax
  __int64 v38; // rcx
  __int16 v39; // dx
  HANDLE v40; // rax
  struct JsonValue *v41; // rax
  HANDLE v42; // rax
  struct JsonValue *v43; // rax
  HANDLE ProcessHeap; // rax
  struct JsonValue *v45; // rax
  HANDLE v46; // rax
  __int64 v48; // [rsp+20h] [rbp-40h] BYREF
  __int64 v49; // [rsp+28h] [rbp-38h] BYREF
  unsigned __int16 *v50; // [rsp+30h] [rbp-30h] BYREF
  double v51; // [rsp+38h] [rbp-28h] BYREF
  struct JsonValue *v52; // [rsp+40h] [rbp-20h] BYREF
  wchar_t String1[4]; // [rsp+48h] [rbp-18h] BYREF
  __int16 v54; // [rsp+50h] [rbp-10h]
  __int16 v55; // [rsp+52h] [rbp-Eh]

  v2 = *((_QWORD *)this + 1);
  v52 = 0;
  v51 = 0.0;
  v48 = 0;
  v3 = 0;
  v49 = 0;
  v50 = 0;
  while ( 1 )
  {
    v6 = *(_QWORD *)this;
    v7 = *(unsigned __int16 *)(v2 + 2LL * *(_QWORD *)this);
    if ( v7 != 9
      && *(_WORD *)(v2 + 2LL * *(_QWORD *)this) != 10
      && *(_WORD *)(v2 + 2LL * *(_QWORD *)this) != 13
      && *(_WORD *)(v2 + 2LL * *(_QWORD *)this) != 32 )
    {
      break;
    }
    *(_QWORD *)this = v6 + 1;
    if ( !(_WORD)v7 )
      *(_QWORD *)this = v6;
  }
  if ( v7 <= 0x36 )
  {
    if ( v7 == 54 )
      goto LABEL_64;
    v8 = v7 - 34;
    if ( v8 )
    {
      v9 = v8 - 11;
      if ( v9 )
      {
        v10 = v9 - 3;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( v12 )
            {
              v13 = v12 - 1;
              if ( v13 )
              {
                if ( v13 - 1 >= 2 )
                  goto LABEL_17;
              }
            }
          }
        }
      }
LABEL_64:
      StringFromStreamAlloc = JsonHelpersInternal::JsonReader::ReadJsonNumber(this, &v51);
      if ( StringFromStreamAlloc < 0 )
        goto LABEL_68;
      ProcessHeap = GetProcessHeap();
      v45 = (struct JsonValue *)HeapAlloc(ProcessHeap, 0, 0x10u);
      v26 = v45;
      if ( v45 )
      {
        *((double *)v45 + 1) = v51;
        *(_DWORD *)v45 = 1;
        goto LABEL_67;
      }
LABEL_40:
      StringFromStreamAlloc = -2147024882;
      goto LABEL_68;
    }
    StringFromStreamAlloc = JsonHelpersInternal::JsonReader::ReadStringFromStreamAlloc(
                              this,
                              (const unsigned __int16 **)&v50);
    if ( StringFromStreamAlloc < 0 )
    {
      v3 = v50;
      goto LABEL_68;
    }
    v15 = GetProcessHeap();
    v16 = HeapAlloc(v15, 0, 0x10u);
    v3 = v50;
    v17 = v16;
    if ( !v16 )
      goto LABEL_40;
    v18 = -1;
    do
      ++v18;
    while ( v50[v18] );
    v19 = v18 + 1;
    v20 = 2 * (v18 + 1);
    v21 = GetProcessHeap();
    v22 = (unsigned __int16 *)HeapAlloc(v21, 0, v20);
    v23 = v22;
    if ( !v22 )
    {
      StringFromStreamAlloc = -2147024882;
      goto LABEL_24;
    }
    StringFromStreamAlloc = StringCchCopyW(v22, v19, v3);
    if ( StringFromStreamAlloc < 0 )
    {
LABEL_24:
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v17);
      if ( v23 )
      {
        v25 = GetProcessHeap();
        HeapFree(v25, 0, v23);
      }
      goto LABEL_68;
    }
    *(_DWORD *)v17 = 0;
    v26 = (struct JsonValue *)v17;
    v17[1] = v23;
LABEL_67:
    *a2 = v26;
    StringFromStreamAlloc = 0;
    v52 = 0;
    goto LABEL_68;
  }
  switch ( v7 )
  {
    case '7':
    case '8':
    case '9':
      goto LABEL_64;
    case '[':
      StringFromStreamAlloc = JsonHelpersInternal::JsonReader::ReadJsonValueListAlloc(this);
      if ( StringFromStreamAlloc < 0 )
        goto LABEL_68;
      v42 = GetProcessHeap();
      v43 = (struct JsonValue *)HeapAlloc(v42, 0, 0x10u);
      v26 = v43;
      if ( !v43 )
        goto LABEL_40;
      *(_DWORD *)v43 = 4;
      *((_QWORD *)v43 + 1) = v49;
      v49 = 0;
      goto LABEL_67;
    case 'f':
    case 'n':
    case 't':
      *(_QWORD *)this = v6 + 1;
      v30 = v6 + 1;
      String1[0] = v7;
      v31 = *(_WORD *)(v2 + 2 * v30);
      *(_QWORD *)this = v30 + 1;
      if ( v31 )
        ++v30;
      else
        *(_QWORD *)this = v30;
      String1[1] = v31;
      v32 = *(_WORD *)(v2 + 2 * v30);
      *(_QWORD *)this = v30 + 1;
      if ( v32 )
        ++v30;
      else
        *(_QWORD *)this = v30;
      String1[2] = v32;
      v33 = *(_WORD *)(v2 + 2 * v30);
      *(_QWORD *)this = v30 + 1;
      if ( !v33 )
        *(_QWORD *)this = v30;
      String1[3] = v33;
      v54 = 0;
      if ( _wcsicmp(String1, L"true") )
      {
        if ( _wcsicmp(String1, L"null") )
        {
          v38 = *(_QWORD *)this;
          v39 = *(_WORD *)(*((_QWORD *)this + 1) + 2LL * (*(_QWORD *)this)++);
          if ( !v39 )
            *(_QWORD *)this = v38;
          v54 = v39;
          v55 = 0;
          if ( _wcsicmp(String1, L"false") )
            goto LABEL_17;
          v40 = GetProcessHeap();
          v41 = (struct JsonValue *)HeapAlloc(v40, 0, 0x10u);
          v26 = v41;
          if ( !v41 )
            goto LABEL_40;
          *(_DWORD *)v41 = 2;
          *((_BYTE *)v41 + 8) = 0;
        }
        else
        {
          v36 = GetProcessHeap();
          v37 = (struct JsonValue *)HeapAlloc(v36, 0, 0x10u);
          v26 = v37;
          if ( !v37 )
            goto LABEL_40;
          *(_DWORD *)v37 = 3;
        }
      }
      else
      {
        v34 = GetProcessHeap();
        v35 = (struct JsonValue *)HeapAlloc(v34, 0, 0x10u);
        v26 = v35;
        if ( !v35 )
          goto LABEL_40;
        *(_DWORD *)v35 = 2;
        *((_BYTE *)v35 + 8) = 1;
      }
      goto LABEL_67;
  }
  if ( v7 != 123 )
  {
LABEL_17:
    StringFromStreamAlloc = -2147024883;
    goto LABEL_68;
  }
  StringFromStreamAlloc = JsonHelpersInternal::JsonReader::ReadJsonObjectAlloc(this, &v48);
  if ( StringFromStreamAlloc >= 0 )
  {
    v27 = v48;
    v28 = GetProcessHeap();
    v29 = (struct JsonValue *)HeapAlloc(v28, 0, 0x10u);
    v26 = v29;
    if ( !v29 )
      goto LABEL_40;
    *(_DWORD *)v29 = 5;
    *((_QWORD *)v29 + 1) = v27;
    v48 = 0;
    goto LABEL_67;
  }
LABEL_68:
  CleanupJsonValue(&v52);
  CleanupJsonObject(&v48);
  CleanupJsonValueList(&v49);
  if ( v3 )
  {
    v46 = GetProcessHeap();
    HeapFree(v46, 0, v3);
  }
  return (unsigned int)StringFromStreamAlloc;
}

```

## disassembly

```asm
0x1800454bc  mov     [rsp-38h+arg_10], rbx
0x1800454c1  push    rbp
0x1800454c2  push    rsi
0x1800454c3  push    rdi
0x1800454c4  push    r12
0x1800454c6  push    r13
0x1800454c8  push    r14
0x1800454ca  push    r15
0x1800454cc  mov     rbp, rsp
0x1800454cf  sub     rsp, 60h
0x1800454d3  mov     rax, cs:__security_cookie
0x1800454da  xor     rax, rsp
0x1800454dd  mov     [rbp+var_8], rax
0x1800454e1  mov     r9, [rcx+8]
0x1800454e5  xor     r15d, r15d
0x1800454e8  xorps   xmm0, xmm0
0x1800454eb  mov     [rbp+var_20], r15
0x1800454ef  movsd   [rbp+var_28], xmm0
0x1800454f4  mov     edi, r15d
0x1800454f7  mov     [rbp+var_40], r15
0x1800454fb  mov     r12d, r15d
0x1800454fe  mov     [rbp+var_38], r15
0x180045502  mov     r13, rdx
0x180045505  mov     [rbp+var_30], r15
0x180045509  mov     rbx, rcx
0x18004550c  mov     r8, [rbx]
0x18004550f  movzx   ecx, word ptr [r9+r8*2]
0x180045514  mov     edx, ecx
0x180045516  sub     edx, 9
0x180045519  jz      short loc_18004552A
0x18004551b  sub     edx, 1
0x18004551e  jz      short loc_18004552A
0x180045520  sub     edx, 3
0x180045523  jz      short loc_18004552A
0x180045525  cmp     edx, 13h
0x180045528  jnz     short loc_18004553C
0x18004552a  lea     rax, [r8+1]
0x18004552e  mov     [rbx], rax
0x180045531  cmp     r15w, cx
0x180045535  jnz     short loc_18004550C
0x180045537  mov     [rbx], r8
0x18004553a  jmp     short loc_18004550C
0x18004553c  cmp     ecx, 36h ; '6'
0x18004553f  ja      loc_180045677
0x180045545  jz      loc_1800458BA
0x18004554b  sub     ecx, 22h ; '"'
0x18004554e  jz      short loc_180045599
0x180045550  sub     ecx, 0Bh
0x180045553  jz      loc_1800458BA
0x180045559  sub     ecx, 3
0x18004555c  jz      loc_1800458BA
0x180045562  sub     ecx, 1
0x180045565  jz      loc_1800458BA
0x18004556b  sub     ecx, 1
0x18004556e  jz      loc_1800458BA
0x180045574  sub     ecx, 1
0x180045577  jz      loc_1800458BA
0x18004557d  sub     ecx, 1
0x180045580  jz      loc_1800458BA
0x180045586  cmp     ecx, 1
0x180045589  jz      loc_1800458BA
0x18004558f  mov     ebx, 8007000Dh
0x180045594  jmp     loc_180045908
0x180045599  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x18004559d  mov     rcx, rbx; this
0x1800455a0  call    ?ReadStringFromStreamAlloc@JsonReader@JsonHelpersInternal@@AEAAJPEAPEBG@Z; JsonHelpersInternal::JsonReader::ReadStringFromStreamAlloc(ushort const * *)
0x1800455a5  mov     ebx, eax
0x1800455a7  test    eax, eax
0x1800455a9  js      loc_18004566E
0x1800455af  call    cs:__imp_GetProcessHeap
0x1800455b5  xor     edx, edx; dwFlags
0x1800455b7  mov     rcx, rax; hHeap
0x1800455ba  lea     r8d, [rdx+10h]; dwBytes
0x1800455be  call    cs:__imp_HeapAlloc
0x1800455c4  mov     r12, [rbp+var_30]
0x1800455c8  mov     rsi, rax
0x1800455cb  test    rax, rax
0x1800455ce  jz      loc_1800456EC
0x1800455d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800455d8  inc     rax
0x1800455db  cmp     [r12+rax*2], r15w
0x1800455e0  jnz     short loc_1800455D8
0x1800455e2  lea     r15, [rax+1]
0x1800455e6  lea     rbx, [r15+r15]
0x1800455ea  call    cs:__imp_GetProcessHeap
0x1800455f0  mov     r8, rbx; dwBytes
0x1800455f3  xor     edx, edx; dwFlags
0x1800455f5  mov     rcx, rax; hHeap
0x1800455f8  call    cs:__imp_HeapAlloc
0x1800455fe  mov     r14, rax
0x180045601  test    rax, rax
0x180045604  jnz     short loc_180045648
0x180045606  mov     ebx, 8007000Eh
0x18004560b  xor     r15d, r15d
0x18004560e  call    cs:__imp_GetProcessHeap
0x180045614  mov     r8, rsi; lpMem
0x180045617  xor     edx, edx; dwFlags
0x180045619  mov     rcx, rax; hHeap
0x18004561c  call    cs:__imp_HeapFree
0x180045622  test    r14, r14
0x180045625  jz      short loc_18004563B
0x180045627  call    cs:__imp_GetProcessHeap
0x18004562d  mov     r8, r14; lpMem
0x180045630  xor     edx, edx; dwFlags
0x180045632  mov     rcx, rax; hHeap
0x180045635  call    cs:__imp_HeapFree
0x18004563b  test    ebx, ebx
0x18004563d  jns     loc_1800458FD
0x180045643  jmp     loc_180045908
0x180045648  mov     r8, r12; unsigned __int16 *
0x18004564b  mov     rdx, r15; unsigned __int64
0x18004564e  mov     rcx, r14; unsigned __int16 *
0x180045651  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180045656  xor     r15d, r15d
0x180045659  mov     ebx, eax
0x18004565b  test    eax, eax
0x18004565d  js      short loc_18004560E
0x18004565f  mov     [rsi], r15d
0x180045662  mov     rdi, rsi
0x180045665  mov     [rsi+8], r14
0x180045669  jmp     loc_1800458FD
0x18004566e  mov     r12, [rbp+var_30]
0x180045672  jmp     loc_180045908
0x180045677  mov     edx, ecx
0x180045679  sub     edx, 37h ; '7'
0x18004567c  jz      loc_1800458BA
0x180045682  sub     edx, 1
0x180045685  jz      loc_1800458BA
0x18004568b  sub     edx, 1
0x18004568e  jz      loc_1800458BA
0x180045694  sub     edx, 22h ; '"'
0x180045697  jz      loc_18004586F
0x18004569d  sub     edx, 0Bh
0x1800456a0  jz      short loc_180045709
0x1800456a2  sub     edx, 8
0x1800456a5  jz      short loc_180045709
0x1800456a7  sub     edx, 6
0x1800456aa  jz      short loc_180045709
0x1800456ac  cmp     edx, 7
0x1800456af  jnz     loc_18004558F
0x1800456b5  lea     rdx, [rbp+var_40]
0x1800456b9  mov     rcx, rbx; this
0x1800456bc  call    ?ReadJsonObjectAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; JsonHelpersInternal::JsonReader::ReadJsonObjectAlloc(RtlArray<JsonKeyValuePair *> * *)
0x1800456c1  mov     ebx, eax
0x1800456c3  test    eax, eax
0x1800456c5  js      loc_180045908
0x1800456cb  mov     rbx, [rbp+var_40]
0x1800456cf  call    cs:__imp_GetProcessHeap
0x1800456d5  xor     edx, edx; dwFlags
0x1800456d7  mov     rcx, rax; hHeap
0x1800456da  lea     r8d, [rdx+10h]; dwBytes
0x1800456de  call    cs:__imp_HeapAlloc
0x1800456e4  mov     rdi, rax
0x1800456e7  test    rax, rax
0x1800456ea  jnz     short loc_1800456F6
0x1800456ec  mov     ebx, 8007000Eh
0x1800456f1  jmp     loc_180045908
0x1800456f6  mov     dword ptr [rax], 5
0x1800456fc  mov     [rax+8], rbx
0x180045700  mov     [rbp+var_40], r15
0x180045704  jmp     loc_1800458FD
0x180045709  lea     rdx, [r8+1]
0x18004570d  mov     [rbx], rdx
0x180045710  cmp     r15w, cx
0x180045714  jnz     short loc_18004571B
0x180045716  mov     [rbx], r8
0x180045719  jmp     short loc_18004571E
0x18004571b  mov     r8, rdx
0x18004571e  mov     [rbp+String1], cx
0x180045722  lea     rcx, [r8+1]
0x180045726  movzx   edx, word ptr [r9+r8*2]
0x18004572b  mov     [rbx], rcx
0x18004572e  cmp     r15w, dx
0x180045732  jnz     short loc_180045739
0x180045734  mov     [rbx], r8
0x180045737  jmp     short loc_18004573C
0x180045739  mov     r8, rcx
0x18004573c  mov     [rbp+var_16], dx
0x180045740  lea     rcx, [r8+1]
0x180045744  movzx   edx, word ptr [r9+r8*2]
0x180045749  mov     [rbx], rcx
0x18004574c  cmp     r15w, dx
0x180045750  jnz     short loc_180045757
0x180045752  mov     [rbx], r8
0x180045755  jmp     short loc_18004575A
0x180045757  mov     r8, rcx
0x18004575a  mov     [rbp+var_14], dx
0x18004575e  lea     rax, [r8+1]
0x180045762  movzx   ecx, word ptr [r9+r8*2]
0x180045767  mov     [rbx], rax
0x18004576a  cmp     r15w, cx
0x18004576e  jnz     short loc_180045773
0x180045770  mov     [rbx], r8
0x180045773  mov     [rbp+var_12], cx
0x180045777  lea     rdx, aTrue; "true"
0x18004577e  lea     rcx, [rbp+String1]; String1
0x180045782  mov     [rbp+var_10], r15w
0x180045787  call    cs:__imp__wcsicmp
0x18004578d  test    eax, eax
0x18004578f  jnz     short loc_1800457C1
0x180045791  call    cs:__imp_GetProcessHeap
0x180045797  xor     edx, edx; dwFlags
0x180045799  mov     rcx, rax; hHeap
0x18004579c  lea     r8d, [rdx+10h]; dwBytes
0x1800457a0  call    cs:__imp_HeapAlloc
0x1800457a6  mov     rdi, rax
0x1800457a9  test    rax, rax
0x1800457ac  jz      loc_1800456EC
0x1800457b2  mov     dword ptr [rax], 2
0x1800457b8  mov     byte ptr [rax+8], 1
0x1800457bc  jmp     loc_1800458FD
0x1800457c1  lea     rdx, aNull; "null"
0x1800457c8  lea     rcx, [rbp+String1]; String1
0x1800457cc  call    cs:__imp__wcsicmp
0x1800457d2  test    eax, eax
0x1800457d4  jnz     short loc_180045802
0x1800457d6  call    cs:__imp_GetProcessHeap
0x1800457dc  xor     edx, edx; dwFlags
0x1800457de  mov     rcx, rax; hHeap
0x1800457e1  lea     r8d, [rdx+10h]; dwBytes
0x1800457e5  call    cs:__imp_HeapAlloc
0x1800457eb  mov     rdi, rax
0x1800457ee  test    rax, rax
0x1800457f1  jz      loc_1800456EC
0x1800457f7  mov     dword ptr [rax], 3
0x1800457fd  jmp     loc_1800458FD
0x180045802  mov     rcx, [rbx]
0x180045805  mov     rax, [rbx+8]
0x180045809  movzx   edx, word ptr [rax+rcx*2]
0x18004580d  lea     rax, [rcx+1]
0x180045811  mov     [rbx], rax
0x180045814  cmp     r15w, dx
0x180045818  jnz     short loc_18004581D
0x18004581a  mov     [rbx], rcx
0x18004581d  mov     [rbp+var_10], dx
0x180045821  lea     rcx, [rbp+String1]; String1
0x180045825  lea     rdx, aFalse; "false"
0x18004582c  mov     [rbp+var_E], r15w
0x180045831  call    cs:__imp__wcsicmp
0x180045837  test    eax, eax
0x180045839  jnz     loc_18004558F
0x18004583f  call    cs:__imp_GetProcessHeap
0x180045845  xor     edx, edx; dwFlags
0x180045847  mov     rcx, rax; hHeap
0x18004584a  lea     r8d, [rdx+10h]; dwBytes
0x18004584e  call    cs:__imp_HeapAlloc
0x180045854  mov     rdi, rax
0x180045857  test    rax, rax
0x18004585a  jz      loc_1800456EC
0x180045860  mov     dword ptr [rax], 2
0x180045866  mov     [rax+8], r15b
0x18004586a  jmp     loc_1800458FD
0x18004586f  lea     rdx, [rbp+var_38]
0x180045873  mov     rcx, rbx; this
0x180045876  call    ?ReadJsonValueListAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAV?$RtlArray@PEAUJsonValue@@@@@Z; JsonHelpersInternal::JsonReader::ReadJsonValueListAlloc(RtlArray<JsonValue *> * *)
0x18004587b  mov     ebx, eax
0x18004587d  test    eax, eax
0x18004587f  js      loc_180045908
0x180045885  call    cs:__imp_GetProcessHeap
0x18004588b  xor     edx, edx; dwFlags
0x18004588d  mov     rcx, rax; hHeap
0x180045890  lea     r8d, [rdx+10h]; dwBytes
0x180045894  call    cs:__imp_HeapAlloc
0x18004589a  mov     rdi, rax
0x18004589d  test    rax, rax
0x1800458a0  jz      loc_1800456EC
0x1800458a6  mov     dword ptr [rax], 4
0x1800458ac  mov     rax, [rbp+var_38]
0x1800458b0  mov     [rdi+8], rax
0x1800458b4  mov     [rbp+var_38], r15
0x1800458b8  jmp     short loc_1800458FD
0x1800458ba  lea     rdx, [rbp+var_28]; double *
0x1800458be  mov     rcx, rbx; this
0x1800458c1  call    ?ReadJsonNumber@JsonReader@JsonHelpersInternal@@QEAAJPEAN@Z; JsonHelpersInternal::JsonReader::ReadJsonNumber(double *)
0x1800458c6  mov     ebx, eax
0x1800458c8  test    eax, eax
0x1800458ca  js      short loc_180045908
0x1800458cc  call    cs:__imp_GetProcessHeap
0x1800458d2  xor     edx, edx; dwFlags
0x1800458d4  mov     rcx, rax; hHeap
0x1800458d7  lea     r8d, [rdx+10h]; dwBytes
0x1800458db  call    cs:__imp_HeapAlloc
0x1800458e1  mov     rdi, rax
0x1800458e4  test    rax, rax
0x1800458e7  jz      loc_1800456EC
0x1800458ed  movsd   xmm0, [rbp+var_28]
0x1800458f2  movsd   qword ptr [rax+8], xmm0
0x1800458f7  mov     dword ptr [rax], 1
0x1800458fd  mov     [r13+0], rdi
0x180045901  mov     ebx, r15d
0x180045904  mov     [rbp+var_20], r15
0x180045908  lea     rcx, [rbp+var_20]; struct JsonValue **
0x18004590c  call    ?CleanupJsonValue@@YAXPEAPEAUJsonValue@@@Z; CleanupJsonValue(JsonValue * *)
0x180045911  lea     rcx, [rbp+var_40]
0x180045915  call    ?CleanupJsonObject@@YAXPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; CleanupJsonObject(RtlArray<JsonKeyValuePair *> * *)
0x18004591a  lea     rcx, [rbp+var_38]
0x18004591e  call    ?CleanupJsonValueList@@YAXPEAPEAV?$RtlArray@PEAUJsonValue@@@@@Z; CleanupJsonValueList(RtlArray<JsonValue *> * *)
0x180045923  test    r12, r12
0x180045926  jz      short loc_18004593C
0x180045928  call    cs:__imp_GetProcessHeap
  ... truncated ...
```
