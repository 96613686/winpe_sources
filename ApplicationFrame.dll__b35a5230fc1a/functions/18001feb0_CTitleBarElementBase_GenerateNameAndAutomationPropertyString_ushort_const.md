# CTitleBarElementBase::_GenerateNameAndAutomationPropertyString(ushort const *)

- ea: `0x18001feb0`
- end: `0x1800206e0`
- name: `?_GenerateNameAndAutomationPropertyString@CTitleBarElementBase@@IEAAXPEBG@Z`
- size: `2096`
- prototype: `void __fastcall(CTitleBarElementBase *__hidden this, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e294`
- `0x18001e580`
- `0x18001e5d0`
- `0x18001f5b4`
- `0x18001f780`
- `0x18001fb9c`
- `0x18001fdd8`
- `0x180020cb4`

## callees

- `0x1800116c0`
- `0x18001feb0`
- `0x1800206e8`
- `0x1800209a0`
- `0x18002e020`
- `0x1800532a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180020081`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180020081`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18002006c`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18002006c`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180020093`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180020093`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180020362`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800203cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002043c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002055b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180020362`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800203cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002043c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002055b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ff32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ffd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002014a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800201c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020487`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ff32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ffd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002014a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800201c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020487`

## pseudocode

```c
void __fastcall CTitleBarElementBase::_GenerateNameAndAutomationPropertyString(
        CTitleBarElementBase *this,
        const unsigned __int16 *a2)
{
  int v2; // eax
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r9
  __int64 v7; // rdi
  _WORD *v8; // rax
  _WORD *v9; // r8
  const wchar_t *v10; // rdx
  __int64 v11; // rcx
  _WORD *v12; // rcx
  unsigned int v13; // esi
  __int64 v14; // r8
  unsigned __int64 v15; // r9
  __int64 v16; // rdi
  _WORD *v17; // rax
  _WORD *v18; // r8
  const wchar_t *v19; // rax
  __int64 v20; // rdx
  _WORD *v21; // rcx
  _WORD *v22; // rcx
  void *v23; // r14
  HRSRC Resource; // rax
  HGLOBAL v25; // rax
  unsigned __int16 *v26; // rdi
  unsigned int i; // ecx
  unsigned __int64 v28; // rax
  const WCHAR *v29; // rdi
  unsigned __int64 v30; // rsi
  int v31; // r8d
  _WORD *v32; // rcx
  _WORD *v33; // rax
  _WORD *v34; // rdx
  unsigned __int64 v35; // r9
  __int64 v36; // rdi
  _WORD *v37; // rax
  _WORD *v38; // r8
  const wchar_t *v39; // rdx
  __int64 v40; // rcx
  _WORD *v41; // rcx
  _WORD *v42; // r8
  const wchar_t *v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r9
  _WORD *v46; // rcx
  _WORD *v47; // rdx
  const wchar_t *v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rdi
  _WORD *v51; // rcx
  __int64 v52; // r9
  unsigned __int64 v53; // rsi
  LPVOID v54; // rax
  __int64 v55; // r9
  unsigned __int64 v56; // rsi
  LPVOID v57; // rax
  __int64 v58; // r9
  unsigned __int64 v59; // rsi
  LPVOID v60; // rax
  _WORD *v61; // rax
  _WORD *v62; // r8
  const wchar_t *v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // rdi
  unsigned __int64 v66; // r9
  __int64 v67; // r9
  unsigned __int64 v68; // rsi
  LPVOID v69; // rax
  unsigned __int64 v70; // [rsp+70h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 12);
  v5 = -1;
  if ( v2 == 8 )
  {
    v15 = *((_QWORD *)this + 14);
    if ( v15 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount((char *)this + 96);
      if ( *((_QWORD *)this + 12) )
        v15 = *((_QWORD *)this + 13) + 1LL;
      else
        v15 = 0;
      *((_QWORD *)this + 14) = v15;
    }
    v16 = 9;
    if ( v15 )
    {
      if ( v15 < 9 )
      {
        v70 = 0;
        if ( (int)ULongLongMult(v15, 2u, &v70) < 0 )
          goto LABEL_29;
        v53 = v70;
        if ( v70 - v52 > 0x800 )
          v53 = v52 + 2048;
        if ( v53 < 9 )
          v53 = 9;
        v54 = CoTaskMemRealloc(*((LPVOID *)this + 12), 2 * v53);
        if ( !v54 )
          goto LABEL_29;
        *((_QWORD *)this + 14) = v53;
        *((_QWORD *)this + 12) = v54;
      }
    }
    else
    {
      if ( !is_mul_ok(9u, 2u) || (v17 = CoTaskMemAlloc(0x12u)) == 0 )
      {
LABEL_29:
        v13 = 4;
LABEL_34:
        v14 = 564;
        goto LABEL_35;
      }
      *((_QWORD *)this + 14) = 9;
      *((_QWORD *)this + 12) = v17;
      *v17 = 0;
    }
    v18 = (_WORD *)*((_QWORD *)this + 12);
    v19 = L"Maximize";
    v20 = 8;
    do
    {
      if ( !v20 )
        break;
      if ( !*v19 )
        break;
      *v18++ = *v19++;
      --v20;
      --v16;
    }
    while ( v16 );
    v21 = v18 - 1;
    if ( v16 )
      v21 = v18;
    *v21 = 0;
    *((_QWORD *)this + 13) = 8;
    goto LABEL_29;
  }
  if ( v2 == 2 )
  {
LABEL_33:
    v13 = 2;
    goto LABEL_34;
  }
  switch ( v2 )
  {
    case 1:
      v66 = *((_QWORD *)this + 14);
      if ( v66 == -1 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount((char *)this + 96);
        if ( *((_QWORD *)this + 12) )
          v66 = *((_QWORD *)this + 13) + 1LL;
        else
          v66 = 0;
        *((_QWORD *)this + 14) = v66;
      }
      v65 = 14;
      if ( !v66 )
      {
        if ( !is_mul_ok(0xEu, 2u) )
          goto LABEL_33;
        v61 = CoTaskMemAlloc(0x1Cu);
        if ( !v61 )
          goto LABEL_33;
        *((_QWORD *)this + 14) = 14;
        *((_QWORD *)this + 12) = v61;
        *v61 = 0;
        goto LABEL_124;
      }
      if ( v66 >= 0xE )
        goto LABEL_124;
      v70 = 0;
      if ( (int)ULongLongMult(v66, 2u, &v70) >= 0 )
      {
        v68 = v70;
        if ( v70 - v67 > 0x800 )
          v68 = v67 + 2048;
        if ( v68 < 0xE )
          v68 = 14;
        v69 = CoTaskMemRealloc(*((LPVOID *)this + 12), 2 * v68);
        if ( v69 )
        {
          *((_QWORD *)this + 14) = v68;
          *((_QWORD *)this + 12) = v69;
LABEL_124:
          v62 = (_WORD *)*((_QWORD *)this + 12);
          v63 = L"SystemMenuBar";
          v64 = 13;
          do
          {
            if ( !v64 )
              break;
            if ( !*v63 )
              break;
            *v62++ = *v63++;
            --v64;
            --v65;
          }
          while ( v65 );
          v22 = v62 - 1;
          if ( v65 )
            v22 = v62;
          *v22 = 0;
          *((_QWORD *)this + 13) = 13;
          goto LABEL_33;
        }
      }
      goto LABEL_33;
    case 3:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        (char *)this + 96,
        L"Actions",
        -1);
      v13 = 3;
      goto LABEL_34;
    case 4:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        (char *)this + 96,
        L"EnterFullScreen",
        -1);
      v13 = 7;
      goto LABEL_34;
    case 5:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        (char *)this + 96,
        L"ExitFullScreen",
        -1);
      v13 = 9;
      goto LABEL_34;
    case 6:
      v35 = *((_QWORD *)this + 14);
      if ( v35 == -1 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount((char *)this + 96);
        if ( *((_QWORD *)this + 12) )
          v35 = *((_QWORD *)this + 13) + 1LL;
        else
          v35 = 0;
        *((_QWORD *)this + 14) = v35;
      }
      v36 = 9;
      if ( !v35 )
      {
        if ( !is_mul_ok(9u, 2u) )
          goto LABEL_76;
        v37 = CoTaskMemAlloc(0x12u);
        if ( !v37 )
          goto LABEL_76;
        *((_QWORD *)this + 14) = 9;
        *((_QWORD *)this + 12) = v37;
        *v37 = 0;
        goto LABEL_69;
      }
      if ( v35 >= 9 )
        goto LABEL_69;
      v70 = 0;
      if ( (int)ULongLongMult(v35, 2u, &v70) >= 0 )
      {
        v59 = v70;
        if ( v70 - v58 > 0x800 )
          v59 = v58 + 2048;
        if ( v59 < 9 )
          v59 = 9;
        v60 = CoTaskMemRealloc(*((LPVOID *)this + 12), 2 * v59);
        if ( v60 )
        {
          *((_QWORD *)this + 14) = v59;
          *((_QWORD *)this + 12) = v60;
LABEL_69:
          v38 = (_WORD *)*((_QWORD *)this + 12);
          v39 = L"Minimize";
          v40 = 8;
          do
          {
            if ( !v40 )
              break;
            if ( !*v39 )
              break;
            *v38++ = *v39++;
            --v40;
            --v36;
          }
          while ( v36 );
          v41 = v38 - 1;
          if ( v36 )
            v41 = v38;
          *v41 = 0;
          *((_QWORD *)this + 13) = 8;
        }
      }
LABEL_76:
      v13 = 1;
      goto LABEL_34;
    case 7:
      if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                  (char *)this + 96,
                  8) >= 0 )
      {
        v47 = (_WORD *)*((_QWORD *)this + 12);
        v48 = L"Maximize";
        v49 = 8;
        v50 = 9;
        do
        {
          if ( !v49 )
            break;
          if ( !*v48 )
            break;
          *v47++ = *v48++;
          --v49;
          --v50;
        }
        while ( v50 );
        v51 = v47 - 1;
        if ( v50 )
          v51 = v47;
        *v51 = 0;
        *((_QWORD *)this + 13) = 8;
      }
      v13 = 5;
      goto LABEL_34;
    case 11:
      if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                  (char *)this + 96,
                  5) >= 0 )
      {
        v42 = (_WORD *)*((_QWORD *)this + 12);
        v43 = L"Close";
        v44 = 5;
        v45 = 6;
        do
        {
          if ( !v44 )
            break;
          if ( !*v43 )
            break;
          *v42++ = *v43++;
          --v44;
          --v45;
        }
        while ( v45 );
        v46 = v42 - 1;
        if ( v45 )
          v46 = v42;
        *v46 = 0;
        *((_QWORD *)this + 13) = 5;
      }
      v13 = 0;
      goto LABEL_34;
    case 12:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        (char *)this + 96,
        L"Annotate",
        -1);
      v13 = 6;
      goto LABEL_34;
    case 13:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        (char *)this + 96,
        L"TitleBarLeftButtons",
        -1);
      v14 = 563;
      v13 = 15;
      break;
    case 14:
      v6 = *((_QWORD *)this + 14);
      if ( v6 == -1 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount((char *)this + 96);
        if ( *((_QWORD *)this + 12) )
          v6 = *((_QWORD *)this + 13) + 1LL;
        else
          v6 = 0;
        *((_QWORD *)this + 14) = v6;
      }
      v7 = 9;
      if ( !v6 )
      {
        if ( !is_mul_ok(9u, 2u) )
          goto LABEL_16;
        v8 = CoTaskMemAlloc(0x12u);
        if ( !v8 )
          goto LABEL_16;
        *((_QWORD *)this + 14) = 9;
        *((_QWORD *)this + 12) = v8;
        *v8 = 0;
        goto LABEL_9;
      }
      if ( v6 >= 9 )
        goto LABEL_9;
      v70 = 0;
      if ( (int)ULongLongMult(v6, 2u, &v70) >= 0 )
      {
        v56 = v70;
        if ( v70 - v55 > 0x800 )
          v56 = v55 + 2048;
        if ( v56 < 9 )
          v56 = 9;
        v57 = CoTaskMemRealloc(*((LPVOID *)this + 12), 2 * v56);
        if ( v57 )
        {
          *((_QWORD *)this + 14) = v56;
          *((_QWORD *)this + 12) = v57;
LABEL_9:
          v9 = (_WORD *)*((_QWORD *)this + 12);
          v10 = L"TitleBar";
          v11 = 8;
          do
          {
            if ( !v11 )
              break;
            if ( !*v10 )
              break;
            *v9++ = *v10++;
            --v11;
            --v7;
          }
          while ( v7 );
          v12 = v9 - 1;
          if ( v7 )
            v12 = v9;
          *v12 = 0;
          *((_QWORD *)this + 13) = 8;
        }
      }
LABEL_16:
      v13 = 15;
      v14 = 563;
      break;
    case 15:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        (char *)this + 96,
        L"Back",
        -1);
      v13 = 8;
      goto LABEL_34;
    default:
      return;
  }
LABEL_35:
  v23 = 0;
  Resource = FindResourceExW(&_ImageBase, (LPCWSTR)6, (LPCWSTR)v14, 0);
  if ( Resource )
  {
    v25 = LoadResource(&_ImageBase, Resource);
    if ( v25 )
    {
      v26 = (unsigned __int16 *)LockResource(v25);
      if ( v26 )
      {
        for ( i = 0; i < v13; v26 += *v26 + 1 )
          ++i;
        v28 = *v26;
        if ( (_WORD)v28 )
          v29 = v26 + 1;
        else
          v29 = &pszDefault;
        if ( !v29 )
          goto LABEL_52;
        do
          ++v5;
        while ( v29[v5] );
        v30 = v28 + 1;
        if ( v28 < v5 )
          v5 = v28;
        if ( v30 >= v28 && is_mul_ok(v30, 2u) )
        {
          v33 = CoTaskMemAlloc(2 * v30);
          if ( v33 )
          {
            *v33 = 0;
            v23 = v33;
            v31 = 0;
            if ( v5 > 0x7FFFFFFE )
            {
              *v33 = 0;
            }
            else
            {
              v34 = v33;
              do
              {
                if ( !v5 )
                  break;
                if ( !*v29 )
                  break;
                *v34++ = *v29++;
                --v5;
                --v30;
              }
              while ( v30 );
              v32 = v34 - 1;
              if ( v30 )
                v32 = v34;
              *v32 = 0;
            }
          }
          else
          {
            v31 = -2147024882;
          }
        }
        else
        {
          v31 = -2147024362;
        }
        if ( v31 >= 0 )
LABEL_52:
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            (char *)this + 72,
            v23,
            a2);
        if ( v23 )
          CoTaskMemFree(v23);
      }
    }
  }
}

```

## disassembly

```asm
0x18001feb0  push    rbx
0x18001feb2  push    rbp
0x18001feb3  push    rsi
0x18001feb4  push    rdi
0x18001feb5  push    r12
0x18001feb7  push    r13
0x18001feb9  push    r14
0x18001febb  push    r15
0x18001febd  sub     rsp, 28h
0x18001fec1  mov     eax, [rcx+30h]
0x18001fec4  lea     r12, __ImageBase
0x18001fecb  xor     r13d, r13d
0x18001fece  mov     r15, rdx
0x18001fed1  mov     rbp, rcx
0x18001fed4  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001fedb  cmp     eax, 8
0x18001fede  jz      loc_18001FFA5
0x18001fee4  cmp     eax, 2
0x18001fee7  jz      loc_180020053
0x18001feed  dec     eax; switch 15 cases
0x18001feef  cmp     eax, 0Eh
0x18001fef2  ja      def_18001FF05; jumptable 000000018001FF05 default case, cases 2,8-10
0x18001fef8  cdqe
0x18001fefa  mov     ecx, ds:(jpt_18001FF05 - 180000000h)[r12+rax*4]
0x18001ff02  add     rcx, r12
0x18001ff05  jmp     rcx; switch jump
0x18001ff07  mov     r9, [rbp+70h]; jumptable 000000018001FF05 case 14
0x18001ff0b  cmp     r9, rbx
0x18001ff0e  jz      loc_180020577
0x18001ff14  mov     edi, 9
0x18001ff19  test    r9, r9
0x18001ff1c  jnz     loc_18002037E
0x18001ff22  mov     eax, 2
0x18001ff27  mul     rdi
0x18001ff2a  test    rdx, rdx
0x18001ff2d  jnz     short loc_18001FF95
0x18001ff2f  mov     rcx, rax; cb
0x18001ff32  call    cs:__imp_CoTaskMemAlloc
0x18001ff38  test    rax, rax
0x18001ff3b  jz      short loc_18001FF95
0x18001ff3d  mov     [rbp+70h], rdi
0x18001ff41  mov     [rbp+60h], rax
0x18001ff45  mov     [rax], r13w
0x18001ff49  mov     r8, [rbp+60h]
0x18001ff4d  lea     rdx, aTitlebar; "TitleBar"
0x18001ff54  mov     esi, 8
0x18001ff59  mov     ecx, esi
0x18001ff5b  nop     dword ptr [rax+rax+00h]
0x18001ff60  test    rcx, rcx
0x18001ff63  jz      short loc_18001FF82
0x18001ff65  movzx   eax, word ptr [rdx]
0x18001ff68  test    ax, ax
0x18001ff6b  jz      short loc_18001FF82
0x18001ff6d  mov     [r8], ax
0x18001ff71  add     rdx, 2
0x18001ff75  add     r8, 2
0x18001ff79  dec     rcx
0x18001ff7c  sub     rdi, 1
0x18001ff80  jnz     short loc_18001FF60
0x18001ff82  test    rdi, rdi
0x18001ff85  lea     rcx, [r8-2]
0x18001ff89  cmovnz  rcx, r8
0x18001ff8d  mov     [rcx], r13w
0x18001ff91  mov     [rbp+68h], rsi
0x18001ff95  mov     esi, 0Fh
0x18001ff9a  mov     r8d, 233h
0x18001ffa0  jmp     loc_18002005E
0x18001ffa5  mov     r9, [rcx+70h]
0x18001ffa9  cmp     r9, rbx
0x18001ffac  jz      loc_180020674
0x18001ffb2  mov     edi, 9
0x18001ffb7  test    r9, r9
0x18001ffba  jnz     loc_180020311
0x18001ffc0  mov     eax, 2
0x18001ffc5  mul     rdi
0x18001ffc8  test    rdx, rdx
0x18001ffcb  jnz     short loc_180020035
0x18001ffcd  mov     rcx, rax; cb
0x18001ffd0  call    cs:__imp_CoTaskMemAlloc
0x18001ffd6  test    rax, rax
0x18001ffd9  jz      short loc_180020035
0x18001ffdb  mov     [rbp+70h], rdi
0x18001ffdf  mov     [rbp+60h], rax
0x18001ffe3  mov     [rax], r13w
0x18001ffe7  mov     r8, [rbp+60h]
0x18001ffeb  lea     rax, aMaximize; "Maximize"
0x18001fff2  mov     esi, 8
0x18001fff7  mov     edx, esi
0x18001fff9  nop     dword ptr [rax+00000000h]
0x180020000  test    rdx, rdx
0x180020003  jz      short loc_180020022
0x180020005  movzx   ecx, word ptr [rax]
0x180020008  test    cx, cx
0x18002000b  jz      short loc_180020022
0x18002000d  mov     [r8], cx
0x180020011  add     rax, 2
0x180020015  add     r8, 2
0x180020019  dec     rdx
0x18002001c  sub     rdi, 1
0x180020020  jnz     short loc_180020000
0x180020022  test    rdi, rdi
0x180020025  lea     rcx, [r8-2]
0x180020029  cmovnz  rcx, r8
0x18002002d  mov     [rcx], r13w
0x180020031  mov     [rbp+68h], rsi
0x180020035  mov     esi, 4
0x18002003a  jmp     short loc_180020058
0x18002003c  test    rdi, rdi
0x18002003f  lea     rcx, [r8-2]
0x180020043  cmovnz  rcx, r8
0x180020047  mov     [rcx], r13w
0x18002004b  mov     qword ptr [rbp+68h], 0Dh
0x180020053  mov     esi, 2
0x180020058  mov     r8d, 234h; lpName
0x18002005e  xor     r9d, r9d; wLanguage
0x180020061  mov     edx, 6; lpType
0x180020066  mov     rcx, r12; hModule
0x180020069  mov     r14, r13
0x18002006c  call    cs:__imp_FindResourceExW
0x180020072  test    rax, rax
0x180020075  jz      def_18001FF05; jumptable 000000018001FF05 default case, cases 2,8-10
0x18002007b  mov     rdx, rax; hResInfo
0x18002007e  mov     rcx, r12; hModule
0x180020081  call    cs:__imp_LoadResource
0x180020087  test    rax, rax
0x18002008a  jz      def_18001FF05; jumptable 000000018001FF05 default case, cases 2,8-10
0x180020090  mov     rcx, rax; hResData
0x180020093  call    cs:__imp_LockResource
0x180020099  mov     rdi, rax
0x18002009c  test    rax, rax
0x18002009f  jz      def_18001FF05; jumptable 000000018001FF05 default case, cases 2,8-10
0x1800200a5  mov     ecx, r13d
0x1800200a8  test    esi, esi
0x1800200aa  jz      short loc_1800200C1
0x1800200ac  nop     dword ptr [rax+00h]
0x1800200b0  movzx   eax, word ptr [rdi]
0x1800200b3  inc     ecx
0x1800200b5  lea     rdi, [rdi+rax*2]
0x1800200b9  add     rdi, 2
0x1800200bd  cmp     ecx, esi
0x1800200bf  jb      short loc_1800200B0
0x1800200c1  movzx   eax, word ptr [rdi]
0x1800200c4  test    ax, ax
0x1800200c7  jz      loc_180020698
0x1800200cd  add     rdi, 2
0x1800200d1  test    rdi, rdi
0x1800200d4  jz      short loc_18002010C
0x1800200d6  inc     rbx
0x1800200d9  cmp     [rdi+rbx*2], r13w
0x1800200de  jnz     short loc_1800200D6
0x1800200e0  cmp     rax, rbx
0x1800200e3  lea     rsi, [rax+1]
0x1800200e7  cmovb   rbx, rax
0x1800200eb  cmp     rsi, rax
0x1800200ee  jnb     short loc_18002013A
0x1800200f0  mov     r8d, 80070216h
0x1800200f6  jmp     short loc_180020107
0x1800200f8  test    rsi, rsi
0x1800200fb  lea     rcx, [rdx-2]
0x1800200ff  cmovnz  rcx, rdx
0x180020103  mov     [rcx], r13w
0x180020107  test    r8d, r8d
0x18002010a  js      short loc_18002011B
0x18002010c  lea     rcx, [rbp+48h]
0x180020110  mov     r8, r15
0x180020113  mov     rdx, r14
0x180020116  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002011b  test    r14, r14
0x18002011e  jz      short def_18001FF05; jumptable 000000018001FF05 default case, cases 2,8-10
0x180020120  mov     rcx, r14; pv
0x180020123  call    cs:__imp_CoTaskMemFree
0x180020129  add     rsp, 28h; jumptable 000000018001FF05 default case, cases 2,8-10
0x18002012d  pop     r15
0x18002012f  pop     r14
0x180020131  pop     r13
0x180020133  pop     r12
0x180020135  pop     rdi
0x180020136  pop     rsi
0x180020137  pop     rbp
0x180020138  pop     rbx
0x180020139  retn
0x18002013a  mov     eax, 2
0x18002013f  mul     rsi
0x180020142  test    rdx, rdx
0x180020145  jnz     short loc_1800200F0
0x180020147  mov     rcx, rax; cb
0x18002014a  call    cs:__imp_CoTaskMemAlloc
0x180020150  test    rax, rax
0x180020153  jz      loc_180020299
0x180020159  mov     [rax], r13w
0x18002015d  mov     r14, rax
0x180020160  mov     r8d, r13d
0x180020163  cmp     rbx, 7FFFFFFEh
0x18002016a  ja      loc_18002047B
0x180020170  mov     rdx, rax
0x180020173  test    rbx, rbx
0x180020176  jz      short loc_1800200F8
0x180020178  movzx   eax, word ptr [rdi]
0x18002017b  test    ax, ax
0x18002017e  jz      loc_1800200F8
0x180020184  mov     [rdx], ax
0x180020187  add     rdi, 2
0x18002018b  add     rdx, 2
0x18002018f  dec     rbx
0x180020192  sub     rsi, 1
0x180020196  jnz     short loc_180020173
0x180020198  jmp     loc_1800200F8
0x18002019d  mov     r9, [rbp+70h]; jumptable 000000018001FF05 case 6
0x1800201a1  cmp     r9, rbx
0x1800201a4  jz      loc_18002059B
0x1800201aa  mov     edi, 9
0x1800201af  test    r9, r9
0x1800201b2  jnz     loc_1800203EB
0x1800201b8  mov     eax, 2
0x1800201bd  mul     rdi
0x1800201c0  test    rdx, rdx
0x1800201c3  jnz     short loc_180020226
0x1800201c5  mov     rcx, rax; cb
0x1800201c8  call    cs:__imp_CoTaskMemAlloc
0x1800201ce  test    rax, rax
0x1800201d1  jz      short loc_180020226
0x1800201d3  mov     [rbp+70h], rdi
0x1800201d7  mov     [rbp+60h], rax
0x1800201db  mov     [rax], r13w
0x1800201df  mov     r8, [rbp+60h]
0x1800201e3  lea     rdx, aMinimize; "Minimize"
0x1800201ea  mov     esi, 8
0x1800201ef  mov     ecx, esi
0x1800201f1  test    rcx, rcx
0x1800201f4  jz      short loc_180020213
0x1800201f6  movzx   eax, word ptr [rdx]
0x1800201f9  test    ax, ax
0x1800201fc  jz      short loc_180020213
0x1800201fe  mov     [r8], ax
0x180020202  add     rdx, 2
0x180020206  add     r8, 2
0x18002020a  dec     rcx
0x18002020d  sub     rdi, 1
0x180020211  jnz     short loc_1800201F1
0x180020213  test    rdi, rdi
0x180020216  lea     rcx, [r8-2]
0x18002021a  cmovnz  rcx, r8
0x18002021e  mov     [rcx], r13w
0x180020222  mov     [rbp+68h], rsi
0x180020226  mov     esi, 1
0x18002022b  jmp     loc_180020058
0x180020230  mov     edx, 5; jumptable 000000018001FF05 case 11
0x180020235  lea     rcx, [rbp+60h]
0x180020239  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18002023e  test    eax, eax
0x180020240  js      short loc_180020291
0x180020242  mov     r8, [rbp+60h]
0x180020246  lea     rdx, aClose; "Close"
0x18002024d  mov     ecx, 5
0x180020252  mov     r9d, 6
0x180020258  test    rcx, rcx
0x18002025b  jz      short loc_18002027A
0x18002025d  movzx   eax, word ptr [rdx]
0x180020260  test    ax, ax
0x180020263  jz      short loc_18002027A
0x180020265  mov     [r8], ax
0x180020269  add     rdx, 2
0x18002026d  add     r8, 2
0x180020271  dec     rcx
0x180020274  sub     r9, 1
0x180020278  jnz     short loc_180020258
0x18002027a  test    r9, r9
0x18002027d  lea     rcx, [r8-2]
0x180020281  cmovnz  rcx, r8
0x180020285  mov     [rcx], r13w
0x180020289  mov     qword ptr [rbp+68h], 5
0x180020291  mov     esi, r13d
0x180020294  jmp     loc_180020058
0x180020299  mov     r8d, 8007000Eh
0x18002029f  jmp     loc_180020107
0x1800202a4  mov     esi, 8; jumptable 000000018001FF05 case 7
0x1800202a9  lea     rcx, [rbp+60h]
0x1800202ad  mov     edx, esi
0x1800202af  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800202b4  test    eax, eax
0x1800202b6  js      short loc_180020307
0x1800202b8  mov     rdx, [rbp+60h]
0x1800202bc  lea     rax, aMaximize; "Maximize"
0x1800202c3  mov     ecx, esi
0x1800202c5  mov     edi, 9
0x1800202ca  nop     word ptr [rax+rax+00h]
0x1800202d0  test    rcx, rcx
0x1800202d3  jz      short loc_1800202F4
0x1800202d5  movzx   r8d, word ptr [rax]
0x1800202d9  test    r8w, r8w
0x1800202dd  jz      short loc_1800202F4
0x1800202df  mov     [rdx], r8w
0x1800202e3  add     rax, 2
0x1800202e7  add     rdx, 2
0x1800202eb  dec     rcx
0x1800202ee  sub     rdi, 1
0x1800202f2  jnz     short loc_1800202D0
0x1800202f4  test    rdi, rdi
0x1800202f7  lea     rcx, [rdx-2]
0x1800202fb  cmovnz  rcx, rdx
  ... truncated ...
```
