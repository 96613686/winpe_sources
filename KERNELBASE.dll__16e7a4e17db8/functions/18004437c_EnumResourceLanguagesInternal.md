# EnumResourceLanguagesInternal

- ea: `0x18004437c`
- end: `0x180044e90`
- name: `EnumResourceLanguagesInternal`
- size: `2836`
- prototype: `__int64 __usercall@<rax>(PVOID BaseAddress@<rcx>, __int64, int, __int16, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180044fb0`
- `0x1801243f0`

## callees

- `0x1800134a0`
- `0x180044090`
- `0x1800441cc`
- `0x18004437c`
- `0x180044ea0`
- `0x180044ed0`
- `0x180045130`
- `0x180074bb0`
- `0x1800afc20`
- `0x180175448`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800447bd`
- `ntdll!RtlFreeHeap` at `0x180044dff`
- `ntdll!RtlFreeHeap` at `0x180044e1e`
- `ntdll!RtlFreeHeap` at `0x180044e38`
- `ntdll!RtlFreeHeap` at `0x180189671`
- `ntdll!RtlFreeHeap` at `0x18018969b`
- `ntdll!RtlFreeHeap` at `0x1801896be`
- `ntdll!RtlFreeHeap` at `0x1800447bd`
- `ntdll!RtlFreeHeap` at `0x180044dff`
- `ntdll!RtlFreeHeap` at `0x180044e1e`
- `ntdll!RtlFreeHeap` at `0x180044e38`
- `ntdll!RtlFreeHeap` at `0x180189671`
- `ntdll!RtlFreeHeap` at `0x18018969b`
- `ntdll!RtlFreeHeap` at `0x1801896be`
- `ntdll!LdrResGetRCConfig` at `0x1800447ee`
- `ntdll!LdrResGetRCConfig` at `0x180044a26`
- `ntdll!LdrResGetRCConfig` at `0x180044af0`
- `ntdll!LdrResGetRCConfig` at `0x180044b03`
- `ntdll!LdrResGetRCConfig` at `0x1800447ee`
- `ntdll!LdrResGetRCConfig` at `0x180044a26`
- `ntdll!LdrResGetRCConfig` at `0x180044af0`
- `ntdll!LdrResGetRCConfig` at `0x180044b03`
- `ntdll!LdrpResGetResourceDirectory` at `0x1800445b7`
- `ntdll!LdrpResGetResourceDirectory` at `0x180044c59`
- `ntdll!LdrpResGetResourceDirectory` at `0x1800445b7`
- `ntdll!LdrpResGetResourceDirectory` at `0x180044c59`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180044a99`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180044a99`
- `ntdll!LdrLoadAlternateResourceModule` at `0x180044546`
- `ntdll!LdrLoadAlternateResourceModule` at `0x180044546`
- `ntdll!LdrRscIsTypeExist` at `0x180044a60`
- `ntdll!LdrRscIsTypeExist` at `0x180044ad1`
- `ntdll!LdrRscIsTypeExist` at `0x180044a60`
- `ntdll!LdrRscIsTypeExist` at `0x180044ad1`
- `ntdll!LdrLoadAlternateResourceModuleEx` at `0x1800446c7`
- `ntdll!LdrLoadAlternateResourceModuleEx` at `0x1800446c7`
- `ntdll!LdrpResGetMappingSize` at `0x180044d10`
- `ntdll!LdrpResGetMappingSize` at `0x180044d10`
- `ntdll!RtlAllocateHeap` at `0x180044b52`
- `ntdll!RtlAllocateHeap` at `0x180044b52`

## pseudocode

```c
__int64 __fastcall EnumResourceLanguagesInternal(
        PVOID BaseAddress,
        const WCHAR *a2,
        const WCHAR *a3,
        unsigned int (__fastcall *a4)(PVOID, void *, void *, __int64, __int64),
        __int64 a5,
        int a6,
        unsigned __int16 a7,
        char a8)
{
  unsigned __int64 ImageBaseAddress; // r13
  int v10; // r15d
  int v11; // eax
  __int64 v12; // rsi
  signed int RCConfig; // esi
  unsigned int v14; // r14d
  int v15; // ebx
  __int64 v16; // r9
  __int64 v17; // rbx
  int v18; // ebx
  int i; // ebx
  unsigned __int16 v20; // bx
  unsigned int j; // ecx
  unsigned int v22; // ecx
  void *v23; // r8
  void *v24; // rdx
  int v25; // eax
  unsigned __int16 *v26; // rbx
  unsigned int v27; // edx
  __int64 v28; // r9
  unsigned int k; // ecx
  void *v30; // r8
  void *v31; // rdx
  __int64 v32; // rax
  unsigned __int64 v33; // r13
  unsigned __int64 v34; // rdx
  int v35; // eax
  LANGID *v36; // rbx
  int v38; // [rsp+20h] [rbp-248h]
  int v39; // [rsp+38h] [rbp-230h]
  ULONG Size; // [rsp+3Ch] [rbp-22Ch] BYREF
  int v41; // [rsp+40h] [rbp-228h]
  int v42; // [rsp+44h] [rbp-224h] BYREF
  __int64 v43; // [rsp+48h] [rbp-220h] BYREF
  int v44; // [rsp+50h] [rbp-218h] BYREF
  unsigned int v45; // [rsp+54h] [rbp-214h]
  PVOID P[2]; // [rsp+58h] [rbp-210h] BYREF
  __int64 v47; // [rsp+68h] [rbp-200h]
  PVOID v48; // [rsp+70h] [rbp-1F8h]
  PVOID v49; // [rsp+78h] [rbp-1F0h]
  __int64 v50; // [rsp+80h] [rbp-1E8h] BYREF
  __int64 v51; // [rsp+88h] [rbp-1E0h] BYREF
  unsigned __int64 v52; // [rsp+90h] [rbp-1D8h] BYREF
  WCHAR Buffer[4]; // [rsp+98h] [rbp-1D0h] BYREF
  PVOID v54; // [rsp+A0h] [rbp-1C8h]
  unsigned int (__fastcall *v55)(PVOID, void *, void *, __int64, __int64); // [rsp+A8h] [rbp-1C0h]
  __int64 v56; // [rsp+B0h] [rbp-1B8h]
  __int64 v57; // [rsp+B8h] [rbp-1B0h]
  __int64 v58; // [rsp+C0h] [rbp-1A8h]
  unsigned int v59; // [rsp+C8h] [rbp-1A0h]
  unsigned int v60; // [rsp+CCh] [rbp-19Ch]
  int v61; // [rsp+D0h] [rbp-198h]
  PVOID v62; // [rsp+D8h] [rbp-190h] BYREF
  PCWCH v63; // [rsp+E0h] [rbp-188h]
  PCWCH UnicodeString; // [rsp+E8h] [rbp-180h]
  __int64 v65; // [rsp+F0h] [rbp-178h] BYREF
  __int64 v66; // [rsp+F8h] [rbp-170h] BYREF
  unsigned int v67; // [rsp+100h] [rbp-168h]
  __int64 v68; // [rsp+108h] [rbp-160h] BYREF
  unsigned __int16 *v69; // [rsp+110h] [rbp-158h]
  int v70; // [rsp+118h] [rbp-150h]
  _WORD v71[128]; // [rsp+120h] [rbp-148h]
  int v72; // [rsp+2A8h] [rbp+40h]

  v55 = a4;
  v63 = a3;
  UnicodeString = a2;
  ImageBaseAddress = (unsigned __int64)BaseAddress;
  v54 = BaseAddress;
  Size = 0;
  v52 = 0;
  v62 = 0;
  v68 = 0;
  v65 = 0;
  *(_OWORD *)P = 0;
  v51 = 0;
  v48 = 0;
  *(_DWORD *)Buffer = 0;
  v49 = 0;
  LODWORD(v43) = 0;
  v50 = 0;
  v44 = 0;
  if ( (a6 & 0xFFFFFFE0) != 0 )
    goto LABEL_150;
  LODWORD(v47) = a6 & 8;
  v10 = a6 | 3;
  if ( (a6 & 0x17) != 0 )
    v10 = a6;
  if ( (a6 & 6) == 6 )
    goto LABEL_154;
  if ( (a6 & 0x10) != 0 )
  {
    if ( (a6 & 7) == 0 )
    {
      v10 = v10 & 0xFFFFFFEE | 1;
      goto LABEL_6;
    }
LABEL_154:
    v11 = 0;
    goto LABEL_7;
  }
LABEL_6:
  v11 = 1;
LABEL_7:
  if ( !v11 )
    goto LABEL_150;
  v12 = BaseDllMapResourceIdW(a2);
  v56 = v12;
  if ( v12 == -1 )
    goto LABEL_150;
  v57 = BaseDllMapResourceIdW(a3);
  if ( v57 == -1 )
  {
    BaseDllFreeResourceId(v12);
LABEL_150:
    BaseSetLastNTError(3221225485LL);
    return 0;
  }
  RCConfig = 0;
  v45 = 0;
  v42 = 0;
  v14 = 1;
  v39 = 0;
  v41 = 0;
  if ( !ImageBaseAddress )
    ImageBaseAddress = (unsigned __int64)NtCurrentPeb()->ImageBaseAddress;
  v72 = a8 & 1;
  if ( !v72 )
    goto LABEL_13;
  if ( ((unsigned __int64)UnicodeString & 0xFFFFFFFFFFFF0000uLL) == 0 )
  {
    v48 = (PVOID)UnicodeString;
LABEL_112:
    if ( ((unsigned __int64)v63 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      RCConfig = ConverStringWithHeapAlloc(v63);
      if ( RCConfig < 0 )
        goto LABEL_52;
    }
    else
    {
      v49 = (PVOID)v63;
    }
LABEL_13:
    v15 = v47;
    if ( (a6 & 0x10) != 0 )
      goto LABEL_14;
    if ( (_DWORD)v47 )
    {
      RCConfig = LdrResGetRCConfig(ImageBaseAddress, 0, &v50, 0, 1);
      if ( RCConfig == -1073020925 )
        RCConfig = -1073741701;
    }
    else
    {
      RCConfig = LdrResGetRCConfig(ImageBaseAddress, 0, &v50, 0x2000, 1);
    }
    if ( RCConfig >= 0 )
    {
      RCConfig = LdrRscIsTypeExist(v50, v56, 0, &v44);
      if ( RCConfig < 0 )
        goto LABEL_52;
    }
    else if ( RCConfig == -1073741701 )
    {
      goto LABEL_52;
    }
LABEL_14:
    if ( (v10 & 6) == 0 )
      goto LABEL_18;
    if ( v50 && (*(_BYTE *)(v50 + 16) & 1) != 0 )
    {
      if ( (v44 & 0x20000) == 0 )
      {
        LODWORD(P[0]) = 0;
        Size = 0;
        if ( !a7 )
        {
          P[1] = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x40u);
          if ( P[1] )
          {
            HIDWORD(P[0]) = 32;
            Internal_EnumUILanguages(EnumUILanguagesProcW, 0, P, 1);
            for ( i = v42; ; i = 1 )
            {
              if ( i )
                GetInstalledMUILanguages((PVOID)ImageBaseAddress);
              if ( !LODWORD(P[0]) )
              {
                v36 = (LANGID *)P[1];
                *v36 = GetUserDefaultUILanguage();
LABEL_120:
                LODWORD(P[0]) = 1;
              }
LABEL_37:
              if ( Size < LODWORD(P[0]) )
                break;
              if ( v42 || (v10 & 4) != 0 || a7 )
              {
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
                P[1] = 0;
                v15 = v47;
                goto LABEL_18;
              }
              v42 = 1;
              v70 = 1;
            }
            if ( a7 )
              v20 = a7;
            else
              v20 = *((_WORD *)P[1] + Size);
            for ( j = 0; ; ++j )
            {
              v59 = j;
              if ( j >= v45 )
                break;
              if ( v71[j] == v20 )
                goto LABEL_46;
            }
            if ( (int)LdrLoadAlternateResourceModuleEx(ImageBaseAddress, v20, &v65, 0, 128) < 0 )
            {
              RCConfig = -1073020927;
LABEL_46:
              ++Size;
              goto LABEL_37;
            }
            v58 = v20;
            RCConfig = EnumFindResource(v65, v56, v57, v20, v10, (__int64)&v68);
            if ( RCConfig < 0 )
              goto LABEL_46;
            v41 = 1;
            v22 = v45;
            v71[v45] = v20;
            v45 = v22 + 1;
            v67 = v22 + 1;
            if ( v72 )
            {
              v23 = v49;
              v24 = v48;
            }
            else
            {
              v23 = (void *)v63;
              v24 = (void *)UnicodeString;
            }
            if ( v55(v54, v24, v23, v20, a5) )
              goto LABEL_46;
            RCConfig = -1073020921;
          }
          else
          {
            RCConfig = -1073741801;
          }
          goto LABEL_52;
        }
        if ( (v10 & 4) == 0 || (unsigned int)IsValidInstalledLang(a7) )
          goto LABEL_120;
        RCConfig = -1073020927;
LABEL_18:
        if ( (v10 & 1) == 0 )
          goto LABEL_29;
        *(_QWORD *)Buffer = 0;
        v43 = 0;
        v42 = 0;
        if ( LdrLoadAlternateResourceModule((PVOID)ImageBaseAddress, Buffer) >= 0 )
        {
          ImageBaseAddress = *(_QWORD *)Buffer;
          if ( !*(_QWORD *)Buffer )
            ImageBaseAddress = (unsigned __int64)NtCurrentPeb()->ImageBaseAddress;
          if ( (v10 & 0x10) == 0 )
          {
            LOBYTE(v38) = 1;
            if ( (v10 & 8) != 0 )
            {
              v35 = LdrResGetRCConfig(ImageBaseAddress, 0, &v43, 0, v38);
              if ( v35 == -1073020925 )
                v35 = -1073741701;
            }
            else
            {
              v35 = LdrResGetRCConfig(ImageBaseAddress, 0, &v43, 0x2000, v38);
            }
            if ( v35 >= 0 )
            {
              if ( v56 )
              {
                if ( (int)LdrRscIsTypeExist(v43, v56, 0, &v42) >= 0 )
                {
                  v50 = v43;
                  v44 = v42;
                }
              }
              else
              {
                v50 = v43;
              }
            }
          }
        }
        if ( (v44 & 0x40000) != 0 )
        {
          RCConfig = -1073741686;
          v18 = 0;
          goto LABEL_130;
        }
        if ( v15 )
        {
          LOBYTE(v16) = 1;
          if ( (int)LdrpResGetMappingSize(ImageBaseAddress, &v51, 256, v16) < 0 )
            v51 = 0;
        }
        v17 = v51;
        v66 = 0;
        if ( ImageBaseAddress )
        {
          if ( (v10 & 8) == 0 )
          {
            v62 = RtlImageDirectoryEntryToData((PVOID)ImageBaseAddress, 1u, 2u, &Size);
            RCConfig = v62 == 0 ? 0xC0000089 : 0;
            goto LABEL_27;
          }
          if ( v51 )
          {
            RCConfig = LdrpResGetResourceDirectory(ImageBaseAddress, v51, 4096, &v62, &v66);
            if ( RCConfig == -1073741686 )
              RCConfig = LdrpResGetResourceDirectory(ImageBaseAddress, v17, 0, &v62, &v66);
LABEL_27:
            if ( RCConfig < 0 )
              goto LABEL_29;
            RCConfig = EnumFindResource(ImageBaseAddress, v56, v57, 0, v10 | 0x400u, (__int64)&v52);
            if ( RCConfig < 0 )
              goto LABEL_29;
            v25 = v47;
            if ( (_DWORD)v47 )
            {
              v34 = v52 + 16;
              if ( v52 + 16 < v52
                || v34 < (ImageBaseAddress & 0xFFFFFFFFFFFFFFFCuLL)
                || v34 > v51 + (ImageBaseAddress & 0xFFFFFFFFFFFFFFFCuLL) )
              {
                goto LABEL_82;
              }
              v25 = v47;
            }
            v26 = (unsigned __int16 *)(v52 + 16);
            v69 = (unsigned __int16 *)(v52 + 16);
            if ( *(_WORD *)(v52 + 12) )
            {
              RCConfig = -1073741701;
              goto LABEL_29;
            }
            if ( !v25
              || !*(_WORD *)(v52 + 14)
              || (v47 = 0, v32 = 8LL * *(unsigned __int16 *)(v52 + 14), is_mul_ok(*(unsigned __int16 *)(v52 + 14), 8u))
              && (v33 = ImageBaseAddress & 0xFFFFFFFFFFFFFFFCuLL, v32 + v52 >= v33)
              && v32 + v52 <= v51 + v33 )
            {
              Size = 0;
              v27 = 0;
              while ( 2 )
              {
                if ( v27 >= *(unsigned __int16 *)(v52 + 14) )
                  goto LABEL_29;
                v28 = *v26;
                for ( k = 0; ; ++k )
                {
                  v60 = k;
                  if ( k >= v45 )
                    break;
                  if ( v71[k] == (_WORD)v28 )
                    goto LABEL_70;
                }
                v39 = 1;
                v61 = 1;
                if ( v72 )
                {
                  v30 = v49;
                  v31 = v48;
                }
                else
                {
                  v30 = (void *)v63;
                  v31 = (void *)UnicodeString;
                }
                if ( v55(v54, v31, v30, v28, a5) )
                {
LABEL_70:
                  v26 += 4;
                  v69 = v26;
                  v27 = ++Size;
                  continue;
                }
                break;
              }
              RCConfig = -1073020921;
              goto LABEL_75;
            }
LABEL_82:
            BaseSetLastNTError(3221225595LL);
LABEL_75:
            v14 = 0;
            goto LABEL_29;
          }
        }
        RCConfig = -1073741811;
        goto LABEL_27;
      }
      RCConfig = -1073741686;
    }
    else
    {
      RCConfig = -1073020927;
    }
    v41 = 0;
    goto LABEL_18;
  }
  RCConfig = ConverStringWithHeapAlloc(UnicodeString);
  if ( RCConfig >= 0 )
    goto LABEL_112;
LABEL_52:
  v14 = 0;
LABEL_29:
  v18 = v39;
LABEL_130:
  BaseDllFreeResourceId(v56);
  BaseDllFreeResourceId(v57);
  if ( P[1] )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
    P[1] = 0;
  }
  if ( ((unsigned __int64)v48 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v48);
  if ( ((unsigned __int64)v49 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v49);
  if ( ((v10 & 1) == 0 || (v10 & 6) == 0 || v41 || v18) && ((v10 & 6) == 0 || (v10 & 1) != 0 || v41) )
  {
    if ( (v10 & 1) != 0 && (v10 & 6) == 0 )
      v14 &= -(v18 != 0);
    if ( v14 )
      RCConfig = 0;
  }
  else
  {
    v14 = 0;
  }
  BaseSetLastNTError((unsigned int)RCConfig);
  return v14;
}

```

## disassembly

```asm
0x18004437c  mov     r11, rsp
0x18004437f  push    rbx
0x180044380  push    rsi
0x180044381  push    rdi
0x180044382  push    r12
0x180044384  push    r13
0x180044386  push    r14
0x180044388  push    r15
0x18004438a  sub     rsp, 230h
0x180044391  mov     rax, cs:__security_cookie
0x180044398  xor     rax, rsp
0x18004439b  mov     [rsp+268h+var_48], rax
0x1800443a3  mov     [rsp+268h+var_1C0], r9
0x1800443ab  mov     r14, r8
0x1800443ae  mov     [rsp+268h+var_188], r8
0x1800443b6  mov     [rsp+268h+UnicodeString], rdx
0x1800443be  mov     r13, rcx
0x1800443c1  mov     [rsp+268h+var_1C8], rcx
0x1800443c9  xor     edi, edi
0x1800443cb  mov     [rsp+268h+Size], edi
0x1800443cf  mov     [r11-1D8h], rdi
0x1800443d6  mov     [r11-190h], rdi
0x1800443dd  mov     [r11-160h], rdi
0x1800443e4  mov     [r11-178h], rdi
0x1800443eb  xorps   xmm0, xmm0
0x1800443ee  movups  xmmword ptr [rsp+268h+P], xmm0
0x1800443f3  mov     [r11-1E0h], rdi
0x1800443fa  mov     [rsp+268h+var_1F8], rdi
0x1800443ff  mov     dword ptr [rsp+268h+Buffer], edi
0x180044406  mov     [rsp+268h+var_1F0], rdi
0x18004440b  mov     dword ptr [rsp+268h+var_220], edi
0x18004440f  mov     [r11-1E8h], rdi
0x180044416  mov     [rsp+268h+var_218], edi
0x18004441a  mov     ecx, [rsp+268h+arg_28]
0x180044421  test    ecx, 0FFFFFFE0h
0x180044427  jnz     loc_180044E59
0x18004442d  mov     eax, ecx
0x18004442f  and     eax, 8
0x180044432  mov     dword ptr [rsp+268h+var_200], eax
0x180044436  mov     ebx, ecx
0x180044438  and     ebx, 10h
0x18004443b  mov     r15d, ecx
0x18004443e  or      r15d, 3
0x180044442  test    cl, 17h
0x180044445  cmovnz  r15d, ecx
0x180044449  mov     eax, ecx
0x18004444b  and     eax, 6
0x18004444e  lea     r12d, [rdi+1]
0x180044452  cmp     al, 6
0x180044454  jz      loc_180044E7D
0x18004445a  test    ebx, ebx
0x18004445c  jnz     loc_180044E78
0x180044462  mov     eax, r12d
0x180044465  mov     [rsp+268h+arg_28], r15d
0x18004446d  test    eax, eax
0x18004446f  jz      loc_180044E59
0x180044475  mov     rcx, rdx
0x180044478  call    BaseDllMapResourceIdW
0x18004447d  mov     rsi, rax
0x180044480  mov     [rsp+268h+var_1B8], rax
0x180044488  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004448c  jz      loc_180044E59
0x180044492  mov     rcx, r14
0x180044495  call    BaseDllMapResourceIdW
0x18004449a  mov     [rsp+268h+var_1B0], rax
0x1800444a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800444a6  jz      loc_180044E51
0x1800444ac  mov     esi, edi
0x1800444ae  mov     [rsp+268h+var_214], edi
0x1800444b2  mov     [rsp+268h+var_224], edi
0x1800444b6  mov     r14d, r12d
0x1800444b9  mov     [rsp+268h+var_234], r12d
0x1800444be  mov     eax, edi
0x1800444c0  mov     [rsp+268h+var_230], eax
0x1800444c4  mov     [rsp+268h+var_228], edi
0x1800444c8  test    r13, r13
0x1800444cb  jnz     short loc_1800444DA
0x1800444cd  mov     rax, gs:60h
0x1800444d6  mov     r13, [rax+10h]
0x1800444da  and     [rsp+268h+arg_38], r12d
0x1800444e2  jnz     loc_180044B9C
0x1800444e8  test    ebx, ebx
0x1800444ea  mov     ebx, dword ptr [rsp+268h+var_200]
0x1800444ee  jz      loc_1800447D1
0x1800444f4  test    r15b, 6
0x1800444f8  jz      short loc_180044518
0x1800444fa  mov     rax, [rsp+268h+var_1E8]
0x180044502  test    rax, rax
0x180044505  jnz     loc_180044B0E
0x18004450b  mov     esi, 0C00B0001h
0x180044510  mov     [rsp+268h+var_238], esi
0x180044514  mov     [rsp+268h+var_228], edi
0x180044518  test    r12b, r15b
0x18004451b  jz      loc_180044613
0x180044521  mov     qword ptr [rsp+268h+Buffer], rdi
0x180044529  mov     [rsp+268h+var_220], rdi
0x18004452e  mov     [rsp+268h+var_224], edi
0x180044532  mov     r9d, 1000080h
0x180044538  xor     r8d, r8d
0x18004453b  lea     rdx, [rsp+268h+Buffer]; Buffer
0x180044543  mov     rcx, r13; Module
0x180044546  call    cs:__imp_LdrLoadAlternateResourceModule
0x18004454c  test    eax, eax
0x18004454e  jns     loc_1800449EF
0x180044554  test    [rsp+268h+var_218], 40000h
0x18004455c  jnz     loc_180044C0C
0x180044562  test    ebx, ebx
0x180044564  jnz     loc_180044CFC
0x18004456a  mov     rbx, [rsp+268h+var_1E0]
0x180044572  mov     [rsp+268h+var_170], rdi
0x18004457a  test    r13, r13
0x18004457d  jz      loc_180044C66
0x180044583  test    r15b, 8
0x180044587  jz      loc_180044A88
0x18004458d  test    rbx, rbx
0x180044590  jz      loc_180044C66
0x180044596  lea     rax, [rsp+268h+var_170]
0x18004459e  mov     [rsp+268h+var_248], rax
0x1800445a3  lea     r9, [rsp+268h+var_190]
0x1800445ab  mov     r8d, 1000h
0x1800445b1  mov     rdx, rbx
0x1800445b4  mov     rcx, r13
0x1800445b7  call    cs:__imp_LdrpResGetResourceDirectory
0x1800445bd  mov     esi, eax
0x1800445bf  cmp     eax, 0C000008Ah
0x1800445c4  jz      loc_180044C3B
0x1800445ca  mov     [rsp+268h+var_238], esi
0x1800445ce  test    esi, esi
0x1800445d0  js      short loc_180044613
0x1800445d2  mov     eax, r15d
0x1800445d5  bts     eax, 0Ah
0x1800445d9  xor     r9d, r9d
0x1800445dc  lea     rcx, [rsp+268h+var_1D8]
0x1800445e4  mov     [rsp+268h+var_240], rcx
0x1800445e9  mov     dword ptr [rsp+268h+var_248], eax
0x1800445ed  mov     r8, [rsp+268h+var_1B0]
0x1800445f5  mov     rdx, [rsp+268h+var_1B8]
0x1800445fd  mov     rcx, r13
0x180044600  call    EnumFindResource
0x180044605  mov     esi, eax
0x180044607  mov     [rsp+268h+var_238], eax
0x18004460b  test    eax, eax
0x18004460d  jns     loc_18004481B
0x180044613  mov     ebx, [rsp+268h+var_230]
0x180044617  jmp     loc_180044D2F
0x18004461c  mov     eax, [rsp+268h+var_224]
0x180044620  test    eax, eax
0x180044622  jnz     loc_1800447A9
0x180044628  test    r15b, 4
0x18004462c  jnz     loc_1800447A9
0x180044632  cmp     [rsp+268h+arg_30], di
0x18004463a  jnz     loc_1800447A9
0x180044640  mov     ebx, r12d
0x180044643  mov     [rsp+268h+var_224], ebx
0x180044647  mov     [rsp+268h+var_150], ebx
0x18004464e  test    ebx, ebx
0x180044650  jz      short loc_18004465F
0x180044652  lea     rdx, [rsp+268h+P]
0x180044657  mov     rcx, r13; Address
0x18004465a  call    GetInstalledMUILanguages
0x18004465f  cmp     dword ptr [rsp+268h+P], edi
0x180044663  jz      loc_180044CD9
0x180044669  mov     eax, dword ptr [rsp+268h+P]
0x18004466d  cmp     [rsp+268h+Size], eax
0x180044671  jnb     short loc_18004461C
0x180044673  cmp     [rsp+268h+arg_30], di
0x18004467b  jnz     loc_180044C1C
0x180044681  mov     ecx, [rsp+268h+Size]
0x180044685  mov     rax, [rsp+268h+P+8]
0x18004468a  movzx   ebx, word ptr [rax+rcx*2]
0x18004468e  mov     ecx, edi
0x180044690  mov     [rsp+268h+var_1A0], ecx
0x180044697  cmp     ecx, [rsp+268h+var_214]
0x18004469b  jnb     short loc_1800446AE
0x18004469d  mov     eax, ecx
0x18004469f  cmp     [rsp+rax*2+268h+var_148], bx
0x1800446a7  jz      short loc_1800446DE
0x1800446a9  add     ecx, r12d
0x1800446ac  jmp     short loc_180044690
0x1800446ae  mov     dword ptr [rsp+268h+var_248], 80h
0x1800446b6  xor     r9d, r9d
0x1800446b9  lea     r8, [rsp+268h+var_178]
0x1800446c1  movzx   edx, bx
0x1800446c4  mov     rcx, r13
0x1800446c7  call    cs:__imp_LdrLoadAlternateResourceModuleEx
0x1800446cd  mov     [rsp+268h+var_238], eax
0x1800446d1  test    eax, eax
0x1800446d3  jns     short loc_1800446E5
0x1800446d5  mov     esi, 0C00B0001h
0x1800446da  mov     [rsp+268h+var_238], esi
0x1800446de  add     [rsp+268h+Size], r12d
0x1800446e3  jmp     short loc_180044669
0x1800446e5  movzx   r9d, bx
0x1800446e9  mov     [rsp+268h+var_1A8], r9
0x1800446f1  lea     rax, [rsp+268h+var_160]
0x1800446f9  mov     [rsp+268h+var_240], rax
0x1800446fe  mov     dword ptr [rsp+268h+var_248], r15d
0x180044703  mov     r8, [rsp+268h+var_1B0]
0x18004470b  mov     rdx, [rsp+268h+var_1B8]
0x180044713  mov     rcx, [rsp+268h+var_178]
0x18004471b  call    EnumFindResource
0x180044720  mov     esi, eax
0x180044722  mov     [rsp+268h+var_238], eax
0x180044726  test    eax, eax
0x180044728  js      short loc_1800446DE
0x18004472a  mov     [rsp+268h+var_228], r12d
0x18004472f  mov     ecx, [rsp+268h+var_214]
0x180044733  mov     [rsp+rcx*2+268h+var_148], bx
0x18004473b  add     ecx, r12d
0x18004473e  mov     [rsp+268h+var_214], ecx
0x180044742  mov     [rsp+268h+var_168], ecx
0x180044749  mov     rax, [rsp+268h+arg_20]
0x180044751  movzx   r9d, bx
0x180044755  mov     rcx, [rsp+268h+var_1C8]
0x18004475d  mov     [rsp+268h+var_248], rax
0x180044762  mov     rax, [rsp+268h+var_1C0]
0x18004476a  cmp     [rsp+268h+arg_38], edi
0x180044771  jnz     loc_180044B8D
0x180044777  mov     r8, [rsp+268h+var_188]
0x18004477f  mov     rdx, [rsp+268h+UnicodeString]
0x180044787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004478c  test    eax, eax
0x18004478e  jnz     loc_1800446DE
0x180044794  mov     esi, 0C00B0007h
0x180044799  mov     [rsp+268h+var_238], esi
0x18004479d  mov     r14d, edi
0x1800447a0  mov     [rsp+268h+var_234], edi
0x1800447a4  jmp     loc_180044613
0x1800447a9  mov     rcx, gs:60h
0x1800447b2  mov     r8, [rsp+268h+P+8]; P
0x1800447b7  xor     edx, edx; Flags
0x1800447b9  mov     rcx, [rcx+30h]; HeapHandle
0x1800447bd  call    cs:__imp_RtlFreeHeap
0x1800447c3  mov     [rsp+268h+P+8], rdi
0x1800447c8  mov     ebx, dword ptr [rsp+268h+var_200]
0x1800447cc  jmp     loc_180044518
0x1800447d1  mov     byte ptr [rsp+268h+var_248], r12b
0x1800447d6  lea     r8, [rsp+268h+var_1E8]
0x1800447de  xor     edx, edx
0x1800447e0  mov     rcx, r13
0x1800447e3  test    ebx, ebx
0x1800447e5  jz      loc_180044AEA
0x1800447eb  xor     r9d, r9d
0x1800447ee  call    cs:__imp_LdrResGetRCConfig
0x1800447f4  mov     esi, eax
0x1800447f6  cmp     eax, 0C00B0003h
0x1800447fb  jz      loc_180044CA6
0x180044801  mov     [rsp+268h+var_238], esi
0x180044805  test    esi, esi
0x180044807  jns     loc_180044AB9
0x18004480d  cmp     esi, 0C000007Bh
0x180044813  jnz     loc_1800444F4
0x180044819  jmp     short loc_18004479D
0x18004481b  mov     eax, dword ptr [rsp+268h+var_200]
0x18004481f  test    eax, eax
0x180044821  jnz     loc_18004496B
0x180044827  mov     r8, [rsp+268h+var_1D8]
0x18004482f  lea     rbx, [r8+10h]
0x180044833  mov     [rsp+268h+var_158], rbx
0x18004483b  cmp     [r8+0Ch], di
0x180044840  jnz     loc_18004491A
0x180044846  test    eax, eax
0x180044848  jnz     loc_180044928
0x18004484e  mov     [rsp+268h+Size], edi
0x180044852  mov     edx, edi
0x180044854  mov     rax, [rsp+268h+var_1D8]
0x18004485c  movzx   ecx, word ptr [rax+0Eh]
0x180044860  cmp     edx, ecx
0x180044862  jnb     loc_1800449C3
0x180044868  movzx   r9d, word ptr [rbx]
0x18004486c  mov     ecx, edi
0x18004486e  mov     [rsp+268h+var_19C], ecx
0x180044875  cmp     ecx, [rsp+268h+var_214]
0x180044879  jb      short loc_1800448E4
0x18004487b  mov     eax, r12d
0x18004487e  mov     [rsp+268h+var_230], eax
0x180044882  mov     [rsp+268h+var_198], eax
0x180044889  mov     rax, [rsp+268h+arg_20]
0x180044891  mov     rcx, [rsp+268h+var_1C8]
0x180044899  mov     [rsp+268h+var_248], rax
0x18004489e  mov     rax, [rsp+268h+var_1C0]
0x1800448a6  cmp     [rsp+268h+arg_38], edi
0x1800448ad  jnz     short loc_1800448F9
0x1800448af  mov     r8, [rsp+268h+var_188]
0x1800448b7  mov     rdx, [rsp+268h+UnicodeString]
0x1800448bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448c4  test    eax, eax
0x1800448c6  jz      short loc_180044905
0x1800448c8  add     rbx, 8
0x1800448cc  mov     [rsp+268h+var_158], rbx
0x1800448d4  mov     edx, [rsp+268h+Size]
0x1800448d8  add     edx, r12d
0x1800448db  mov     [rsp+268h+Size], edx
0x1800448df  jmp     loc_180044854
0x1800448e4  mov     eax, ecx
0x1800448e6  cmp     [rsp+rax*2+268h+var_148], r9w
0x1800448ef  jz      short loc_1800448C8
0x1800448f1  add     ecx, r12d
0x1800448f4  jmp     loc_18004486E
0x1800448f9  mov     r8, [rsp+268h+var_1F0]
  ... truncated ...
```
