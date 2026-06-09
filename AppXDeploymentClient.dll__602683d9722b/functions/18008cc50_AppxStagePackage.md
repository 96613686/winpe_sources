# AppxStagePackage

- ea: `0x18008cc50`
- end: `0x18008d6c3`
- name: `AppxStagePackage`
- size: `2675`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, int, __int64, char, int)`
- caller_count: `0`
- callee_count: `21`
- tags: ``

## callees

- `0x180008a1c`
- `0x18000b614`
- `0x18000b644`
- `0x18001056c`
- `0x180010dd8`
- `0x1800110ac`
- `0x180011684`
- `0x180023e8c`
- `0x1800292b0`
- `0x18002e224`
- `0x180030d44`
- `0x1800310dc`
- `0x18003112c`
- `0x180031168`
- `0x1800311ac`
- `0x180051870`
- `0x180081ef0`
- `0x18008b0f4`
- `0x18008cc50`
- `0x18008d6d0`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008ce2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008ce9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008cf12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d03d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d055`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d0d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d0eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d155`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d18f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d1a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d2f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d311`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d3ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d3e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d423`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d5be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d5d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d67c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008ce2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008ce9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008cf12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d03d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d055`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d0d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d0eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d155`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d18f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d1a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d2f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d311`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d3ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d3e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d423`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d5be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d5d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d67c`

## pseudocode

```c
__int64 __fastcall AppxStagePackage(
        LPCWSTR lpFileName,
        HSTRING a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        char a7,
        int a8)
{
  HSTRING v10; // r12
  unsigned int v12; // r13d
  int v13; // eax
  unsigned int v14; // ebx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  unsigned int *v19; // rcx
  unsigned int *v20; // rdi
  int v21; // eax
  __int64 v22; // r14
  __int64 (__fastcall *v23)(__int64, HSTRING, __int64 *); // rsi
  HSTRING v24; // rbx
  int v25; // eax
  unsigned int v26; // esi
  int v27; // eax
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // r14
  int v31; // eax
  unsigned int v32; // edi
  int v33; // eax
  __int64 v34; // r12
  __int64 (__fastcall *v35)(__int64, HSTRING, __int64 *); // r15
  HSTRING v36; // rsi
  int v37; // eax
  int v38; // r15d
  __int64 v39; // rdx
  __int64 v40; // rcx
  int v41; // eax
  unsigned int v42; // r13d
  __int64 v43; // r14
  int v44; // eax
  int v45; // eax
  __int64 v46; // r12
  __int64 (__fastcall *v47)(__int64, HSTRING, __int64 *); // r15
  HSTRING v48; // rsi
  int v49; // eax
  __int64 v50; // rsi
  __int64 v51; // r14
  __int64 v52; // rax
  __int64 v53; // rdx
  int v54; // eax
  int v55; // eax
  int v56; // eax
  int v57; // ecx
  int v58; // r8d
  int v59; // r9d
  unsigned int v60; // r14d
  __int64 v61; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v62; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v63; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v64; // [rsp+68h] [rbp-98h] BYREF
  __int64 v65; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v66; // [rsp+78h] [rbp-88h] BYREF
  __int64 v67; // [rsp+80h] [rbp-80h] BYREF
  HSTRING string; // [rsp+88h] [rbp-78h] BYREF
  unsigned int *v69; // [rsp+90h] [rbp-70h]
  HSTRING v70; // [rsp+98h] [rbp-68h] BYREF
  __int64 v71; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v72; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING v73; // [rsp+B0h] [rbp-50h]
  __int64 v74; // [rsp+B8h] [rbp-48h]
  __int64 v75; // [rsp+C0h] [rbp-40h]
  _QWORD v76[16]; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING v77; // [rsp+150h] [rbp+50h] BYREF
  void *retaddr; // [rsp+1C8h] [rbp+C8h]

  v74 = a4;
  v75 = a6;
  v10 = a2;
  LODWORD(v67) = a3;
  v73 = a2;
  v12 = 0;
  if ( !(unsigned __int8)sub_18008B0F4(qword_180153E70) )
  {
    if ( !lpFileName )
      return 2147942487LL;
    sub_1800311AC(&v77);
    v62 = 0;
    v16 = sub_18003112C(v77, &v62);
    v14 = v16;
    if ( v16 < 0 )
    {
      sub_18000B614(retaddr, 581, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v16);
LABEL_10:
      sub_18000B644(&v62);
      return v14;
    }
    v61 = 0;
    v17 = sub_1800310DC(&v62, &v61);
    v14 = v17;
    if ( v17 < 0 )
    {
      sub_18000B614(retaddr, 584, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v17);
LABEL_13:
      sub_18000B644(&v61);
      goto LABEL_10;
    }
    v69 = 0;
    v18 = sub_180030D44(lpFileName);
    v14 = v18;
    if ( v18 < 0 )
    {
      sub_18000B614(retaddr, 588, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v18);
      v19 = v69;
LABEL_16:
      sub_180081EF0(v19);
      goto LABEL_13;
    }
    v20 = v69;
    string = 0;
    v21 = sub_180031168(&string, *((_QWORD *)v69 + 1), *v69);
    v14 = v21;
    if ( v21 < 0 )
    {
      sub_18000B614(retaddr, 591, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v21);
      if ( string )
        WindowsDeleteString(string);
      v19 = v20;
      goto LABEL_16;
    }
    v22 = v61;
    v63 = 0;
    v23 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v61 + 48LL);
    sub_18000B644(&v63);
    v24 = string;
    v25 = v23(v22, string, &v63);
    v26 = v25;
    if ( v25 < 0 )
    {
      sub_18000B614(retaddr, 594, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v25);
LABEL_23:
      sub_18000B644(&v63);
      if ( v24 )
        WindowsDeleteString(v24);
      sub_180081EF0(v20);
      sub_18000B644(&v61);
      sub_18000B644(&v62);
      return v26;
    }
    v66 = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v63 + 48LL))(v63, &v66);
    v26 = v27;
    if ( v27 < 0 )
    {
      sub_18000B614(retaddr, 597, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v27);
      goto LABEL_28;
    }
    v65 = 0;
    sub_180010DD8(&v65);
    v29 = sub_1800110AC(v28, &v65);
    v26 = v29;
    if ( v29 < 0 )
    {
      sub_18000B614(retaddr, 601, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v29);
LABEL_32:
      sub_180010DD8(&v65);
LABEL_28:
      if ( v66 )
        WindowsDeleteString(v66);
      goto LABEL_23;
    }
    if ( a3 )
    {
      v30 = v65;
      while ( 1 )
      {
        v31 = sub_180030D44(*((LPCWSTR *)v10 + v12));
        v32 = v31;
        if ( v31 < 0 )
          break;
        v20 = v69;
        v70 = 0;
        v33 = sub_180031168(&v70, *((_QWORD *)v69 + 1), *v69);
        v26 = v33;
        if ( v33 < 0 )
        {
          sub_18000B614(
            retaddr,
            608,
            "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
            (unsigned int)v33);
          if ( v70 )
            WindowsDeleteString(v70);
          goto LABEL_32;
        }
        v34 = v61;
        v64 = 0;
        v35 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v61 + 48LL);
        sub_18000B644(&v64);
        v36 = v70;
        v37 = v35(v34, v70, &v64);
        v38 = v37;
        if ( v37 < 0 )
        {
          sub_18000B614(
            retaddr,
            611,
            "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
            (unsigned int)v37);
          goto LABEL_51;
        }
        string = 0;
        v38 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v64 + 48LL))(v64, &string);
        if ( v38 < 0 )
        {
          v39 = 614;
          goto LABEL_47;
        }
        v38 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v30 + 104LL))(v30, string);
        if ( v38 < 0 )
        {
          v39 = 616;
LABEL_47:
          sub_18000B614(
            retaddr,
            v39,
            "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
            (unsigned int)v38);
          if ( string )
            WindowsDeleteString(string);
LABEL_51:
          sub_18000B644(&v64);
          if ( v36 )
            WindowsDeleteString(v36);
          goto LABEL_53;
        }
        if ( string )
          WindowsDeleteString(string);
        sub_18000B644(&v64);
        if ( v36 )
          WindowsDeleteString(v36);
        if ( ++v12 >= (unsigned int)v67 )
          goto LABEL_66;
        v10 = v73;
      }
      sub_18000B614(retaddr, 605, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v31);
LABEL_61:
      sub_180010DD8(&v65);
      if ( v66 )
        WindowsDeleteString(v66);
      sub_18000B644(&v63);
      if ( v24 )
        WindowsDeleteString(v24);
      sub_180081EF0(v69);
      sub_18000B644(&v61);
      sub_18000B644(&v62);
      return v32;
    }
LABEL_66:
    v67 = 0;
    sub_180010DD8(&v67);
    v41 = sub_1800110AC(v40, &v67);
    v26 = v41;
    if ( v41 < 0 )
    {
      sub_18000B614(retaddr, 621, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v41);
LABEL_68:
      sub_180010DD8(&v67);
      goto LABEL_32;
    }
    v42 = 0;
    if ( a5 )
    {
      v43 = v67;
      while ( 1 )
      {
        v44 = sub_180030D44(*(LPCWSTR *)(v74 + 8LL * v42));
        v32 = v44;
        if ( v44 < 0 )
        {
          sub_18000B614(
            retaddr,
            625,
            "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
            (unsigned int)v44);
          sub_180010DD8(&v67);
          goto LABEL_61;
        }
        v20 = v69;
        v70 = 0;
        v45 = sub_180031168(&v70, *((_QWORD *)v69 + 1), *v69);
        v26 = v45;
        if ( v45 < 0 )
          break;
        v64 = 0;
        v46 = v61;
        v47 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v61 + 48LL);
        sub_18000B644(&v64);
        v48 = v70;
        v49 = v47(v46, v70, &v64);
        v38 = v49;
        if ( v49 < 0 )
        {
          sub_18000B614(
            retaddr,
            631,
            "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
            (unsigned int)v49);
          goto LABEL_93;
        }
        string = 0;
        v38 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v64 + 48LL))(v64, &string);
        if ( v38 < 0 )
        {
          v53 = 634;
          goto LABEL_89;
        }
        v38 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v43 + 104LL))(v43, string);
        if ( v38 < 0 )
        {
          v53 = 636;
LABEL_89:
          sub_18000B614(
            retaddr,
            v53,
            "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
            (unsigned int)v38);
          if ( string )
            WindowsDeleteString(string);
LABEL_93:
          sub_18000B644(&v64);
          if ( v48 )
            WindowsDeleteString(v48);
          goto LABEL_95;
        }
        if ( string )
          WindowsDeleteString(string);
        sub_18000B644(&v64);
        if ( v48 )
          WindowsDeleteString(v48);
        if ( ++v42 >= a5 )
          goto LABEL_81;
      }
      sub_18000B614(retaddr, 628, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v45);
      if ( v70 )
        WindowsDeleteString(v70);
      goto LABEL_68;
    }
LABEL_81:
    sub_180011684(&v64);
    v50 = v64;
    if ( !v64 )
    {
      sub_1800292B0(&v64);
      sub_180010DD8(&v67);
      sub_180010DD8(&v65);
      if ( v66 )
        WindowsDeleteString(v66);
      sub_18000B644(&v63);
      if ( v24 )
        WindowsDeleteString(v24);
      sub_180081EF0(v20);
      sub_18000B644(&v61);
      sub_18000B644(&v62);
      return 2147942414LL;
    }
    v51 = 0;
    if ( a7 )
      v51 = 0x200000000000000LL;
    switch ( a8 )
    {
      case 1:
        v52 = 0x40000000000000LL;
        break;
      case 2:
        v52 = 0x80000000000000LL;
        break;
      case 3:
        v52 = 0x100000000000000LL;
        break;
      default:
        goto LABEL_102;
    }
    v51 |= v52;
LABEL_102:
    v71 = 0;
    v54 = sub_18002E224(&v65, &v71);
    v38 = v54;
    if ( v54 >= 0 )
    {
      v72 = 0;
      v55 = sub_18002E224(&v67, &v72);
      v38 = v55;
      if ( v55 >= 0 )
      {
        v76[3] = v66;
        v76[4] = v71;
        v76[6] = v72;
        v76[12] = v75;
        v76[0] = 4;
        v76[2] = 3;
        v76[5] = 0;
        memset(&v76[7], 0, 32);
        v76[11] = 1;
        v76[13] = 0;
        v76[14] = 0;
        v76[1] = v51;
        v56 = sub_18001056C(v50, v76);
        v60 = v56;
        if ( v56 < 0 )
        {
          sub_18000B614(
            retaddr,
            683,
            "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
            (unsigned int)v56);
          sub_18000B644(&v72);
          sub_18000B644(&v71);
          sub_1800292B0(&v64);
          sub_180010DD8(&v67);
          sub_180010DD8(&v65);
          if ( v66 )
            WindowsDeleteString(v66);
          sub_18000B644(&v63);
          if ( v24 )
            WindowsDeleteString(v24);
          sub_180081EF0(v20);
          sub_18000B644(&v61);
          sub_18000B644(&v62);
          return v60;
        }
        v26 = sub_180023E8C(v57, v50 != 0 ? v50 + 224 : 0, v58, v59, 0);
        sub_18000B644(&v72);
        sub_18000B644(&v71);
        sub_1800292B0(&v64);
        goto LABEL_68;
      }
      sub_18000B614(retaddr, 672, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v55);
      sub_18000B644(&v72);
    }
    else
    {
      sub_18000B614(retaddr, 669, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v54);
    }
    sub_18000B644(&v71);
    sub_1800292B0(&v64);
LABEL_95:
    sub_180010DD8(&v67);
LABEL_53:
    sub_180010DD8(&v65);
    if ( v66 )
      WindowsDeleteString(v66);
    sub_18000B644(&v63);
    if ( v24 )
      WindowsDeleteString(v24);
    sub_180081EF0(v20);
    sub_18000B644(&v61);
    sub_18000B644(&v62);
    return (unsigned int)v38;
  }
  v13 = AppxStagePackage2(lpFileName, v10, a3, a4, a5, a6, a7, a8, 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    sub_180008A1C(retaddr, 568, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v13);
    return v14;
  }
  return 0;
}

```

## disassembly

```asm
0x18008cc50  push    rbp
0x18008cc52  push    rbx
0x18008cc53  push    rsi
0x18008cc54  push    rdi
0x18008cc55  push    r12
0x18008cc57  push    r13
0x18008cc59  push    r14
0x18008cc5b  push    r15
0x18008cc5d  lea     rbp, [rsp-88h]
0x18008cc65  sub     rsp, 188h
0x18008cc6c  mov     rax, cs:__security_cookie
0x18008cc73  xor     rax, rsp
0x18008cc76  mov     [rbp+0C0h+var_50], rax
0x18008cc7a  mov     rsi, [rbp+0C0h+arg_28]
0x18008cc81  mov     rbx, r9
0x18008cc84  mov     [rbp+0C0h+var_108], rbx
0x18008cc88  mov     r15d, r8d
0x18008cc8b  mov     [rbp+0C0h+var_100], rsi
0x18008cc8f  mov     r12, rdx
0x18008cc92  mov     dword ptr [rbp+0C0h+var_140], r8d
0x18008cc96  mov     rdi, rcx
0x18008cc99  mov     [rbp+0C0h+var_110], rdx
0x18008cc9d  lea     rcx, qword_180153E70
0x18008cca4  call    sub_18008B0F4
0x18008cca9  xor     r13d, r13d
0x18008ccac  test    al, al
0x18008ccae  jz      short loc_18008CD18
0x18008ccb0  mov     eax, [rbp+0C0h+arg_38]
0x18008ccb6  mov     r9, rbx
0x18008ccb9  mov     [rsp+1C0h+var_180], r13; __int64
0x18008ccbe  mov     r8d, r15d
0x18008ccc1  mov     [rsp+1C0h+var_188], eax; int
0x18008ccc5  mov     rdx, r12
0x18008ccc8  mov     al, [rbp+0C0h+arg_30]
0x18008ccce  mov     rcx, rdi; lpFileName
0x18008ccd1  mov     [rsp+1C0h+var_190], al; char
0x18008ccd5  mov     eax, [rbp+0C0h+arg_20]
0x18008ccdb  mov     [rsp+1C0h+var_198], rsi; __int64
0x18008cce0  mov     [rsp+1C0h+var_1A0], eax; int
0x18008cce4  call    AppxStagePackage2
0x18008cce9  mov     ebx, eax
0x18008cceb  test    eax, eax
0x18008cced  jns     short loc_18008CD11
0x18008ccef  mov     rcx, [rbp+0C8h]
0x18008ccf6  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008ccfd  mov     r9d, eax
0x18008cd00  mov     edx, 238h
0x18008cd05  call    sub_180008A1C
0x18008cd0a  mov     eax, ebx
0x18008cd0c  jmp     loc_18008D6A3
0x18008cd11  xor     eax, eax
0x18008cd13  jmp     loc_18008D6A3
0x18008cd18  test    rdi, rdi
0x18008cd1b  jnz     short loc_18008CD27
0x18008cd1d  mov     eax, 80070057h
0x18008cd22  jmp     loc_18008D6A3
0x18008cd27  lea     rcx, [rbp+0C0h+var_70]; string
0x18008cd2b  call    sub_1800311AC
0x18008cd30  mov     rcx, [rbp+0C0h+var_70]
0x18008cd34  lea     rdx, [rsp+1C0h+var_168]
0x18008cd39  mov     [rsp+1C0h+var_168], r13
0x18008cd3e  call    sub_18003112C
0x18008cd43  mov     ebx, eax
0x18008cd45  test    eax, eax
0x18008cd47  jns     short loc_18008CD70
0x18008cd49  mov     rcx, [rbp+0C8h]
0x18008cd50  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008cd57  mov     r9d, eax
0x18008cd5a  mov     edx, 245h
0x18008cd5f  call    sub_18000B614
0x18008cd64  lea     rcx, [rsp+1C0h+var_168]
0x18008cd69  call    sub_18000B644
0x18008cd6e  jmp     short loc_18008CD0A
0x18008cd70  lea     rdx, [rsp+1C0h+var_170]
0x18008cd75  mov     [rsp+1C0h+var_170], r13
0x18008cd7a  lea     rcx, [rsp+1C0h+var_168]
0x18008cd7f  call    sub_1800310DC
0x18008cd84  mov     ebx, eax
0x18008cd86  test    eax, eax
0x18008cd88  jns     short loc_18008CDB1
0x18008cd8a  mov     rcx, [rbp+0C8h]
0x18008cd91  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008cd98  mov     r9d, eax
0x18008cd9b  mov     edx, 248h
0x18008cda0  call    sub_18000B614
0x18008cda5  lea     rcx, [rsp+1C0h+var_170]
0x18008cdaa  call    sub_18000B644
0x18008cdaf  jmp     short loc_18008CD64
0x18008cdb1  lea     rdx, [rbp+0C0h+var_130]
0x18008cdb5  mov     [rbp+0C0h+var_130], r13
0x18008cdb9  mov     rcx, rdi; lpFileName
0x18008cdbc  call    sub_180030D44
0x18008cdc1  mov     ebx, eax
0x18008cdc3  test    eax, eax
0x18008cdc5  jns     short loc_18008CDED
0x18008cdc7  mov     rcx, [rbp+0C8h]
0x18008cdce  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008cdd5  mov     r9d, eax
0x18008cdd8  mov     edx, 24Ch
0x18008cddd  call    sub_18000B614
0x18008cde2  mov     rcx, [rbp+0C0h+var_130]
0x18008cde6  call    sub_180081EF0
0x18008cdeb  jmp     short loc_18008CDA5
0x18008cded  mov     rdi, [rbp+0C0h+var_130]
0x18008cdf1  lea     rcx, [rbp+0C0h+string]
0x18008cdf5  mov     [rbp+0C0h+string], r13
0x18008cdf9  mov     r8d, [rdi]
0x18008cdfc  mov     rdx, [rdi+8]
0x18008ce00  call    sub_180031168
0x18008ce05  mov     ebx, eax
0x18008ce07  test    eax, eax
0x18008ce09  jns     short loc_18008CE3A
0x18008ce0b  mov     rcx, [rbp+0C8h]
0x18008ce12  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008ce19  mov     r9d, eax
0x18008ce1c  mov     edx, 24Fh
0x18008ce21  call    sub_18000B614
0x18008ce26  mov     rcx, [rbp+0C0h+string]; string
0x18008ce2a  test    rcx, rcx
0x18008ce2d  jz      short loc_18008CE35
0x18008ce2f  call    cs:WindowsDeleteString
0x18008ce35  mov     rcx, rdi
0x18008ce38  jmp     short loc_18008CDE6
0x18008ce3a  mov     r14, [rsp+1C0h+var_170]
0x18008ce3f  lea     rcx, [rsp+1C0h+var_160]
0x18008ce44  mov     [rsp+1C0h+var_160], r13
0x18008ce49  mov     rax, [r14]
0x18008ce4c  mov     rsi, [rax+30h]
0x18008ce50  call    sub_18000B644
0x18008ce55  mov     rbx, [rbp+0C0h+string]
0x18008ce59  lea     r8, [rsp+1C0h+var_160]
0x18008ce5e  mov     rdx, rbx
0x18008ce61  mov     rcx, r14
0x18008ce64  mov     rax, rsi
0x18008ce67  call    j__guard_dispatch_icall
0x18008ce6c  mov     esi, eax
0x18008ce6e  test    eax, eax
0x18008ce70  jns     short loc_18008CEC8
0x18008ce72  mov     rcx, [rbp+0C8h]
0x18008ce79  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008ce80  mov     r9d, eax
0x18008ce83  mov     edx, 252h
0x18008ce88  call    sub_18000B614
0x18008ce8d  lea     rcx, [rsp+1C0h+var_160]
0x18008ce92  call    sub_18000B644
0x18008ce97  test    rbx, rbx
0x18008ce9a  jz      short loc_18008CEA5
0x18008ce9c  mov     rcx, rbx; string
0x18008ce9f  call    cs:WindowsDeleteString
0x18008cea5  mov     rcx, rdi
0x18008cea8  call    sub_180081EF0
0x18008cead  lea     rcx, [rsp+1C0h+var_170]
0x18008ceb2  call    sub_18000B644
0x18008ceb7  lea     rcx, [rsp+1C0h+var_168]
0x18008cebc  call    sub_18000B644
0x18008cec1  mov     eax, esi
0x18008cec3  jmp     loc_18008D6A3
0x18008cec8  mov     rcx, [rsp+1C0h+var_160]
0x18008cecd  lea     rdx, [rsp+1C0h+var_148]
0x18008ced2  mov     [rsp+1C0h+var_148], r13
0x18008ced7  mov     rax, [rcx]
0x18008ceda  mov     rax, [rax+30h]
0x18008cede  call    j__guard_dispatch_icall
0x18008cee3  mov     esi, eax
0x18008cee5  test    eax, eax
0x18008cee7  jns     short loc_18008CF1D
0x18008cee9  mov     rcx, [rbp+0C8h]
0x18008cef0  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008cef7  mov     r9d, eax
0x18008cefa  mov     edx, 255h
0x18008ceff  call    sub_18000B614
0x18008cf04  mov     rcx, [rsp+1C0h+var_148]; string
0x18008cf09  test    rcx, rcx
0x18008cf0c  jz      loc_18008CE8D
0x18008cf12  call    cs:WindowsDeleteString
0x18008cf18  jmp     loc_18008CE8D
0x18008cf1d  lea     rcx, [rsp+1C0h+var_150]
0x18008cf22  mov     [rsp+1C0h+var_150], r13
0x18008cf27  call    sub_180010DD8
0x18008cf2c  lea     rdx, [rsp+1C0h+var_150]
0x18008cf31  call    sub_1800110AC
0x18008cf36  mov     esi, eax
0x18008cf38  test    eax, eax
0x18008cf3a  jns     short loc_18008CF63
0x18008cf3c  mov     rcx, [rbp+0C8h]
0x18008cf43  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008cf4a  mov     r9d, eax
0x18008cf4d  mov     edx, 259h
0x18008cf52  call    sub_18000B614
0x18008cf57  lea     rcx, [rsp+1C0h+var_150]
0x18008cf5c  call    sub_180010DD8
0x18008cf61  jmp     short loc_18008CF04
0x18008cf63  test    r15d, r15d
0x18008cf66  jz      loc_18008D1D1
0x18008cf6c  mov     r14, [rsp+1C0h+var_150]
0x18008cf71  mov     ecx, r13d
0x18008cf74  lea     rdx, [rbp+0C0h+var_130]
0x18008cf78  mov     rcx, [r12+rcx*8]; lpFileName
0x18008cf7c  call    sub_180030D44
0x18008cf81  mov     edi, eax
0x18008cf83  test    eax, eax
0x18008cf85  js      loc_18008D160
0x18008cf8b  mov     rdi, [rbp+0C0h+var_130]
0x18008cf8f  lea     rcx, [rbp+0C0h+var_128]
0x18008cf93  mov     [rbp+0C0h+var_128], 0
0x18008cf9b  mov     r8d, [rdi]
0x18008cf9e  mov     rdx, [rdi+8]
0x18008cfa2  call    sub_180031168
0x18008cfa7  mov     esi, eax
0x18008cfa9  test    eax, eax
0x18008cfab  js      loc_18008D12D
0x18008cfb1  mov     r12, [rsp+1C0h+var_170]
0x18008cfb6  lea     rcx, [rsp+1C0h+var_158]
0x18008cfbb  mov     [rsp+1C0h+var_158], 0
0x18008cfc4  mov     rax, [r12]
0x18008cfc8  mov     r15, [rax+30h]
0x18008cfcc  call    sub_18000B644
0x18008cfd1  mov     rsi, [rbp+0C0h+var_128]
0x18008cfd5  lea     r8, [rsp+1C0h+var_158]
0x18008cfda  mov     rdx, rsi
0x18008cfdd  mov     rcx, r12
0x18008cfe0  mov     rax, r15
0x18008cfe3  call    j__guard_dispatch_icall
0x18008cfe8  xor     r12d, r12d
0x18008cfeb  mov     r15d, eax
0x18008cfee  test    eax, eax
0x18008cff0  js      loc_18008D0A4
0x18008cff6  mov     rcx, [rsp+1C0h+var_158]
0x18008cffb  lea     rdx, [rbp+0C0h+string]
0x18008cfff  mov     [rbp+0C0h+string], r12
0x18008d003  mov     rax, [rcx]
0x18008d006  mov     rax, [rax+30h]
0x18008d00a  call    j__guard_dispatch_icall
0x18008d00f  mov     r15d, eax
0x18008d012  test    eax, eax
0x18008d014  js      loc_18008D09D
0x18008d01a  mov     rax, [r14]
0x18008d01d  mov     rcx, r14
0x18008d020  mov     rdx, [rbp+0C0h+string]
0x18008d024  mov     rax, [rax+68h]
0x18008d028  call    j__guard_dispatch_icall
0x18008d02d  mov     r15d, eax
0x18008d030  test    eax, eax
0x18008d032  js      short loc_18008D071
0x18008d034  mov     rcx, [rbp+0C0h+string]; string
0x18008d038  test    rcx, rcx
0x18008d03b  jz      short loc_18008D043
0x18008d03d  call    cs:WindowsDeleteString
0x18008d043  lea     rcx, [rsp+1C0h+var_158]
0x18008d048  call    sub_18000B644
0x18008d04d  test    rsi, rsi
0x18008d050  jz      short loc_18008D05B
0x18008d052  mov     rcx, rsi; string
0x18008d055  call    cs:WindowsDeleteString
0x18008d05b  inc     r13d
0x18008d05e  cmp     r13d, dword ptr [rbp+0C0h+var_140]
0x18008d062  jnb     loc_18008D1D4
0x18008d068  mov     r12, [rbp+0C0h+var_110]
0x18008d06c  jmp     loc_18008CF71
0x18008d071  mov     edx, 268h
0x18008d076  mov     rcx, [rbp+0C8h]
0x18008d07d  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008d084  mov     r9d, r15d
0x18008d087  call    sub_18000B614
0x18008d08c  mov     rcx, [rbp+0C0h+string]; string
0x18008d090  test    rcx, rcx
0x18008d093  jz      short loc_18008D0BF
0x18008d095  call    cs:WindowsDeleteString
0x18008d09b  jmp     short loc_18008D0BF
0x18008d09d  mov     edx, 266h
0x18008d0a2  jmp     short loc_18008D076
0x18008d0a4  mov     rcx, [rbp+0C8h]
0x18008d0ab  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008d0b2  mov     r9d, r15d
0x18008d0b5  mov     edx, 263h
0x18008d0ba  call    sub_18000B614
0x18008d0bf  lea     rcx, [rsp+1C0h+var_158]
0x18008d0c4  call    sub_18000B644
0x18008d0c9  test    rsi, rsi
0x18008d0cc  jz      short loc_18008D0D7
0x18008d0ce  mov     rcx, rsi; string
0x18008d0d1  call    cs:WindowsDeleteString
0x18008d0d7  lea     rcx, [rsp+1C0h+var_150]
0x18008d0dc  call    sub_180010DD8
0x18008d0e1  mov     rcx, [rsp+1C0h+var_148]; string
0x18008d0e6  test    rcx, rcx
0x18008d0e9  jz      short loc_18008D0F1
0x18008d0eb  call    cs:WindowsDeleteString
0x18008d0f1  lea     rcx, [rsp+1C0h+var_160]
0x18008d0f6  call    sub_18000B644
0x18008d0fb  test    rbx, rbx
0x18008d0fe  jz      short loc_18008D109
0x18008d100  mov     rcx, rbx; string
0x18008d103  call    cs:WindowsDeleteString
0x18008d109  mov     rcx, rdi
0x18008d10c  call    sub_180081EF0
0x18008d111  lea     rcx, [rsp+1C0h+var_170]
0x18008d116  call    sub_18000B644
0x18008d11b  lea     rcx, [rsp+1C0h+var_168]
0x18008d120  call    sub_18000B644
  ... truncated ...
```
