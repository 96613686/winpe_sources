# JsonHelpersInternal::JsonReader::ReadJsonValueAlloc(JsonValue * *)

- ea: `0x18001ff90`
- end: `0x180020436`
- name: `?ReadJsonValueAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAUJsonValue@@@Z`
- size: `1190`
- prototype: `__int64 __fastcall(JsonHelpersInternal::JsonReader *__hidden this, struct JsonValue **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001faec`
- `0x18002043c`

## callees

- `0x18001a3d0`
- `0x18001a474`
- `0x18001a510`
- `0x18001f814`
- `0x18001faec`
- `0x18001ff90`
- `0x18002043c`
- `0x1800209f8`
- `0x180022f34`
- `0x180032310`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002025b`
- `msvcrt!_wcsicmp` at `0x1800202a0`
- `msvcrt!_wcsicmp` at `0x180020305`
- `msvcrt!_wcsicmp` at `0x18002025b`
- `msvcrt!_wcsicmp` at `0x1800202a0`
- `msvcrt!_wcsicmp` at `0x180020305`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020092`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800200cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800201b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020274`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800202b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020322`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020368`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800203af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020092`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800200cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800201b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020274`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800202b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020322`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020368`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800203af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020083`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800200be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800200e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800200fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800201a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020265`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800202aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020313`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020359`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800203a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800203fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020083`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800200be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800200e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800200fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800201a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020265`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800202aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020313`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020359`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800203a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800203fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800200f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020109`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002040a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800200f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020109`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002040a`

## pseudocode

```c
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
0x18001ff90  mov     [rsp-38h+arg_10], rbx
0x18001ff95  push    rbp
0x18001ff96  push    rsi
0x18001ff97  push    rdi
0x18001ff98  push    r12
0x18001ff9a  push    r13
0x18001ff9c  push    r14
0x18001ff9e  push    r15
0x18001ffa0  mov     rbp, rsp
0x18001ffa3  sub     rsp, 60h
0x18001ffa7  mov     rax, cs:__security_cookie
0x18001ffae  xor     rax, rsp
0x18001ffb1  mov     [rbp+var_8], rax
0x18001ffb5  mov     r9, [rcx+8]
0x18001ffb9  xor     r15d, r15d
0x18001ffbc  xorps   xmm0, xmm0
0x18001ffbf  mov     [rbp+var_20], r15
0x18001ffc3  movsd   [rbp+var_28], xmm0
0x18001ffc8  mov     edi, r15d
0x18001ffcb  mov     [rbp+var_40], r15
0x18001ffcf  mov     r12d, r15d
0x18001ffd2  mov     [rbp+var_38], r15
0x18001ffd6  mov     r13, rdx
0x18001ffd9  mov     [rbp+var_30], r15
0x18001ffdd  mov     rbx, rcx
0x18001ffe0  mov     r8, [rbx]
0x18001ffe3  movzx   ecx, word ptr [r9+r8*2]
0x18001ffe8  mov     edx, ecx
0x18001ffea  sub     edx, 9
0x18001ffed  jz      short loc_18001FFFE
0x18001ffef  sub     edx, 1
0x18001fff2  jz      short loc_18001FFFE
0x18001fff4  sub     edx, 3
0x18001fff7  jz      short loc_18001FFFE
0x18001fff9  cmp     edx, 13h
0x18001fffc  jnz     short loc_180020010
0x18001fffe  lea     rax, [r8+1]
0x180020002  mov     [rbx], rax
0x180020005  cmp     r15w, cx
0x180020009  jnz     short loc_18001FFE0
0x18002000b  mov     [rbx], r8
0x18002000e  jmp     short loc_18001FFE0
0x180020010  cmp     ecx, 36h ; '6'
0x180020013  ja      loc_18002014B
0x180020019  jz      loc_18002038E
0x18002001f  sub     ecx, 22h ; '"'
0x180020022  jz      short loc_18002006D
0x180020024  sub     ecx, 0Bh
0x180020027  jz      loc_18002038E
0x18002002d  sub     ecx, 3
0x180020030  jz      loc_18002038E
0x180020036  sub     ecx, 1
0x180020039  jz      loc_18002038E
0x18002003f  sub     ecx, 1
0x180020042  jz      loc_18002038E
0x180020048  sub     ecx, 1
0x18002004b  jz      loc_18002038E
0x180020051  sub     ecx, 1
0x180020054  jz      loc_18002038E
0x18002005a  cmp     ecx, 1
0x18002005d  jz      loc_18002038E
0x180020063  mov     ebx, 8007000Dh
0x180020068  jmp     loc_1800203DC
0x18002006d  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x180020071  mov     rcx, rbx; this
0x180020074  call    ?ReadStringFromStreamAlloc@JsonReader@JsonHelpersInternal@@AEAAJPEAPEBG@Z; JsonHelpersInternal::JsonReader::ReadStringFromStreamAlloc(ushort const * *)
0x180020079  mov     ebx, eax
0x18002007b  test    eax, eax
0x18002007d  js      loc_180020142
0x180020083  call    cs:__imp_GetProcessHeap
0x180020089  xor     edx, edx; dwFlags
0x18002008b  mov     rcx, rax; hHeap
0x18002008e  lea     r8d, [rdx+10h]; dwBytes
0x180020092  call    cs:__imp_HeapAlloc
0x180020098  mov     r12, [rbp+var_30]
0x18002009c  mov     rsi, rax
0x18002009f  test    rax, rax
0x1800200a2  jz      loc_1800201C0
0x1800200a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800200ac  inc     rax
0x1800200af  cmp     [r12+rax*2], r15w
0x1800200b4  jnz     short loc_1800200AC
0x1800200b6  lea     r15, [rax+1]
0x1800200ba  lea     rbx, [r15+r15]
0x1800200be  call    cs:__imp_GetProcessHeap
0x1800200c4  mov     r8, rbx; dwBytes
0x1800200c7  xor     edx, edx; dwFlags
0x1800200c9  mov     rcx, rax; hHeap
0x1800200cc  call    cs:__imp_HeapAlloc
0x1800200d2  mov     r14, rax
0x1800200d5  test    rax, rax
0x1800200d8  jnz     short loc_18002011C
0x1800200da  mov     ebx, 8007000Eh
0x1800200df  xor     r15d, r15d
0x1800200e2  call    cs:__imp_GetProcessHeap
0x1800200e8  mov     r8, rsi; lpMem
0x1800200eb  xor     edx, edx; dwFlags
0x1800200ed  mov     rcx, rax; hHeap
0x1800200f0  call    cs:__imp_HeapFree
0x1800200f6  test    r14, r14
0x1800200f9  jz      short loc_18002010F
0x1800200fb  call    cs:__imp_GetProcessHeap
0x180020101  mov     r8, r14; lpMem
0x180020104  xor     edx, edx; dwFlags
0x180020106  mov     rcx, rax; hHeap
0x180020109  call    cs:__imp_HeapFree
0x18002010f  test    ebx, ebx
0x180020111  jns     loc_1800203D1
0x180020117  jmp     loc_1800203DC
0x18002011c  mov     r8, r12; unsigned __int16 *
0x18002011f  mov     rdx, r15; unsigned __int64
0x180020122  mov     rcx, r14; unsigned __int16 *
0x180020125  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002012a  xor     r15d, r15d
0x18002012d  mov     ebx, eax
0x18002012f  test    eax, eax
0x180020131  js      short loc_1800200E2
0x180020133  mov     [rsi], r15d
0x180020136  mov     rdi, rsi
0x180020139  mov     [rsi+8], r14
0x18002013d  jmp     loc_1800203D1
0x180020142  mov     r12, [rbp+var_30]
0x180020146  jmp     loc_1800203DC
0x18002014b  mov     edx, ecx
0x18002014d  sub     edx, 37h ; '7'
0x180020150  jz      loc_18002038E
0x180020156  sub     edx, 1
0x180020159  jz      loc_18002038E
0x18002015f  sub     edx, 1
0x180020162  jz      loc_18002038E
0x180020168  sub     edx, 22h ; '"'
0x18002016b  jz      loc_180020343
0x180020171  sub     edx, 0Bh
0x180020174  jz      short loc_1800201DD
0x180020176  sub     edx, 8
0x180020179  jz      short loc_1800201DD
0x18002017b  sub     edx, 6
0x18002017e  jz      short loc_1800201DD
0x180020180  cmp     edx, 7
0x180020183  jnz     loc_180020063
0x180020189  lea     rdx, [rbp+var_40]
0x18002018d  mov     rcx, rbx; this
0x180020190  call    ?ReadJsonObjectAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; JsonHelpersInternal::JsonReader::ReadJsonObjectAlloc(RtlArray<JsonKeyValuePair *> * *)
0x180020195  mov     ebx, eax
0x180020197  test    eax, eax
0x180020199  js      loc_1800203DC
0x18002019f  mov     rbx, [rbp+var_40]
0x1800201a3  call    cs:__imp_GetProcessHeap
0x1800201a9  xor     edx, edx; dwFlags
0x1800201ab  mov     rcx, rax; hHeap
0x1800201ae  lea     r8d, [rdx+10h]; dwBytes
0x1800201b2  call    cs:__imp_HeapAlloc
0x1800201b8  mov     rdi, rax
0x1800201bb  test    rax, rax
0x1800201be  jnz     short loc_1800201CA
0x1800201c0  mov     ebx, 8007000Eh
0x1800201c5  jmp     loc_1800203DC
0x1800201ca  mov     dword ptr [rax], 5
0x1800201d0  mov     [rax+8], rbx
0x1800201d4  mov     [rbp+var_40], r15
0x1800201d8  jmp     loc_1800203D1
0x1800201dd  lea     rdx, [r8+1]
0x1800201e1  mov     [rbx], rdx
0x1800201e4  cmp     r15w, cx
0x1800201e8  jnz     short loc_1800201EF
0x1800201ea  mov     [rbx], r8
0x1800201ed  jmp     short loc_1800201F2
0x1800201ef  mov     r8, rdx
0x1800201f2  mov     [rbp+String1], cx
0x1800201f6  lea     rcx, [r8+1]
0x1800201fa  movzx   edx, word ptr [r9+r8*2]
0x1800201ff  mov     [rbx], rcx
0x180020202  cmp     r15w, dx
0x180020206  jnz     short loc_18002020D
0x180020208  mov     [rbx], r8
0x18002020b  jmp     short loc_180020210
0x18002020d  mov     r8, rcx
0x180020210  mov     [rbp+var_16], dx
0x180020214  lea     rcx, [r8+1]
0x180020218  movzx   edx, word ptr [r9+r8*2]
0x18002021d  mov     [rbx], rcx
0x180020220  cmp     r15w, dx
0x180020224  jnz     short loc_18002022B
0x180020226  mov     [rbx], r8
0x180020229  jmp     short loc_18002022E
0x18002022b  mov     r8, rcx
0x18002022e  mov     [rbp+var_14], dx
0x180020232  lea     rax, [r8+1]
0x180020236  movzx   ecx, word ptr [r9+r8*2]
0x18002023b  mov     [rbx], rax
0x18002023e  cmp     r15w, cx
0x180020242  jnz     short loc_180020247
0x180020244  mov     [rbx], r8
0x180020247  mov     [rbp+var_12], cx
0x18002024b  lea     rdx, aTrue; "true"
0x180020252  lea     rcx, [rbp+String1]; String1
0x180020256  mov     [rbp+var_10], r15w
0x18002025b  call    cs:__imp__wcsicmp
0x180020261  test    eax, eax
0x180020263  jnz     short loc_180020295
0x180020265  call    cs:__imp_GetProcessHeap
0x18002026b  xor     edx, edx; dwFlags
0x18002026d  mov     rcx, rax; hHeap
0x180020270  lea     r8d, [rdx+10h]; dwBytes
0x180020274  call    cs:__imp_HeapAlloc
0x18002027a  mov     rdi, rax
0x18002027d  test    rax, rax
0x180020280  jz      loc_1800201C0
0x180020286  mov     dword ptr [rax], 2
0x18002028c  mov     byte ptr [rax+8], 1
0x180020290  jmp     loc_1800203D1
0x180020295  lea     rdx, aNull_0; "null"
0x18002029c  lea     rcx, [rbp+String1]; String1
0x1800202a0  call    cs:__imp__wcsicmp
0x1800202a6  test    eax, eax
0x1800202a8  jnz     short loc_1800202D6
0x1800202aa  call    cs:__imp_GetProcessHeap
0x1800202b0  xor     edx, edx; dwFlags
0x1800202b2  mov     rcx, rax; hHeap
0x1800202b5  lea     r8d, [rdx+10h]; dwBytes
0x1800202b9  call    cs:__imp_HeapAlloc
0x1800202bf  mov     rdi, rax
0x1800202c2  test    rax, rax
0x1800202c5  jz      loc_1800201C0
0x1800202cb  mov     dword ptr [rax], 3
0x1800202d1  jmp     loc_1800203D1
0x1800202d6  mov     rcx, [rbx]
0x1800202d9  mov     rax, [rbx+8]
0x1800202dd  movzx   edx, word ptr [rax+rcx*2]
0x1800202e1  lea     rax, [rcx+1]
0x1800202e5  mov     [rbx], rax
0x1800202e8  cmp     r15w, dx
0x1800202ec  jnz     short loc_1800202F1
0x1800202ee  mov     [rbx], rcx
0x1800202f1  mov     [rbp+var_10], dx
0x1800202f5  lea     rcx, [rbp+String1]; String1
0x1800202f9  lea     rdx, aFalse; "false"
0x180020300  mov     [rbp+var_E], r15w
0x180020305  call    cs:__imp__wcsicmp
0x18002030b  test    eax, eax
0x18002030d  jnz     loc_180020063
0x180020313  call    cs:__imp_GetProcessHeap
0x180020319  xor     edx, edx; dwFlags
0x18002031b  mov     rcx, rax; hHeap
0x18002031e  lea     r8d, [rdx+10h]; dwBytes
0x180020322  call    cs:__imp_HeapAlloc
0x180020328  mov     rdi, rax
0x18002032b  test    rax, rax
0x18002032e  jz      loc_1800201C0
0x180020334  mov     dword ptr [rax], 2
0x18002033a  mov     [rax+8], r15b
0x18002033e  jmp     loc_1800203D1
0x180020343  lea     rdx, [rbp+var_38]
0x180020347  mov     rcx, rbx; this
0x18002034a  call    ?ReadJsonValueListAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAV?$RtlArray@PEAUJsonValue@@@@@Z; JsonHelpersInternal::JsonReader::ReadJsonValueListAlloc(RtlArray<JsonValue *> * *)
0x18002034f  mov     ebx, eax
0x180020351  test    eax, eax
0x180020353  js      loc_1800203DC
0x180020359  call    cs:__imp_GetProcessHeap
0x18002035f  xor     edx, edx; dwFlags
0x180020361  mov     rcx, rax; hHeap
0x180020364  lea     r8d, [rdx+10h]; dwBytes
0x180020368  call    cs:__imp_HeapAlloc
0x18002036e  mov     rdi, rax
0x180020371  test    rax, rax
0x180020374  jz      loc_1800201C0
0x18002037a  mov     dword ptr [rax], 4
0x180020380  mov     rax, [rbp+var_38]
0x180020384  mov     [rdi+8], rax
0x180020388  mov     [rbp+var_38], r15
0x18002038c  jmp     short loc_1800203D1
0x18002038e  lea     rdx, [rbp+var_28]; double *
0x180020392  mov     rcx, rbx; this
0x180020395  call    ?ReadJsonNumber@JsonReader@JsonHelpersInternal@@QEAAJPEAN@Z; JsonHelpersInternal::JsonReader::ReadJsonNumber(double *)
0x18002039a  mov     ebx, eax
0x18002039c  test    eax, eax
0x18002039e  js      short loc_1800203DC
0x1800203a0  call    cs:__imp_GetProcessHeap
0x1800203a6  xor     edx, edx; dwFlags
0x1800203a8  mov     rcx, rax; hHeap
0x1800203ab  lea     r8d, [rdx+10h]; dwBytes
0x1800203af  call    cs:__imp_HeapAlloc
0x1800203b5  mov     rdi, rax
0x1800203b8  test    rax, rax
0x1800203bb  jz      loc_1800201C0
0x1800203c1  movsd   xmm0, [rbp+var_28]
0x1800203c6  movsd   qword ptr [rax+8], xmm0
0x1800203cb  mov     dword ptr [rax], 1
0x1800203d1  mov     [r13+0], rdi
0x1800203d5  mov     ebx, r15d
0x1800203d8  mov     [rbp+var_20], r15
0x1800203dc  lea     rcx, [rbp+var_20]; struct JsonValue **
0x1800203e0  call    ?CleanupJsonValue@@YAXPEAPEAUJsonValue@@@Z; CleanupJsonValue(JsonValue * *)
0x1800203e5  lea     rcx, [rbp+var_40]
0x1800203e9  call    ?CleanupJsonObject@@YAXPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; CleanupJsonObject(RtlArray<JsonKeyValuePair *> * *)
0x1800203ee  lea     rcx, [rbp+var_38]
0x1800203f2  call    ?CleanupJsonValueList@@YAXPEAPEAV?$RtlArray@PEAUJsonValue@@@@@Z; CleanupJsonValueList(RtlArray<JsonValue *> * *)
0x1800203f7  test    r12, r12
0x1800203fa  jz      short loc_180020410
0x1800203fc  call    cs:__imp_GetProcessHeap
  ... truncated ...
```
