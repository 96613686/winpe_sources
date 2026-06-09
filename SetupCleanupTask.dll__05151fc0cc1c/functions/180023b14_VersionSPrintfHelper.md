# VersionSPrintfHelper

- ea: `0x180023b14`
- end: `0x180023f72`
- name: `VersionSPrintfHelper`
- size: `1118`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180023f78`

## callees

- `0x180003850`
- `0x18000c4a8`
- `0x18001bfcc`
- `0x180022fa8`
- `0x180023170`
- `0x180023b14`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023ba0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023ba0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023b80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023b80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023f43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023f43`

## string_xrefs

- `0x180023bf3`: `Service Pack %d`

## pseudocode

```c
__int64 __fastcall VersionSPrintfHelper(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        __int64 a5,
        char *a6)
{
  unsigned __int16 *v8; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v10; // r13
  unsigned __int16 *v11; // r15
  int OSVersionFromFile; // esi
  unsigned __int16 *v13; // r14
  unsigned int v14; // r9d
  unsigned __int16 *v15; // rax
  unsigned int v16; // edi
  unsigned __int16 *v17; // rcx
  unsigned __int16 *v18; // rdx
  const unsigned __int16 *v19; // r8
  bool v20; // zf
  unsigned __int64 v21; // rdx
  char *v22; // r9
  unsigned __int64 v23; // rdx
  int v24; // eax
  int v25; // eax
  bool v26; // sf
  unsigned __int64 *v28; // [rsp+20h] [rbp-89h]
  unsigned __int16 *v29; // [rsp+30h] [rbp-79h]
  unsigned __int16 *v30; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v31; // [rsp+48h] [rbp-61h] BYREF
  int v32; // [rsp+4Ch] [rbp-5Dh] BYREF
  unsigned __int64 v33; // [rsp+50h] [rbp-59h] BYREF
  int v34; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int16 *v35; // [rsp+60h] [rbp-49h]
  unsigned __int16 *v36; // [rsp+68h] [rbp-41h]
  char *v37; // [rsp+70h] [rbp-39h]
  unsigned __int64 v38; // [rsp+78h] [rbp-31h]
  HANDLE hHeap; // [rsp+80h] [rbp-29h]
  unsigned __int16 v40[16]; // [rsp+88h] [rbp-21h] BYREF

  v38 = a2;
  v35 = a1;
  v37 = a6;
  v32 = 0;
  v8 = a1;
  v31 = 0;
  v34 = 0;
  v33 = 0;
  memset(v40, 0, sizeof(v40));
  if ( !a2 )
    return (unsigned int)-2147418113;
  *a1 = 0;
  ProcessHeap = GetProcessHeap();
  if ( (hHeap = ProcessHeap) == 0 )
    return (unsigned int)-2147418113;
  v10 = a4;
  v11 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * a4);
  if ( !v11 )
    return (unsigned int)-2147024882;
  v30 = v11;
  v13 = v11;
  OSVersionFromFile = GetOSVersionFromFile(&v32, (_DWORD *)&v33 + 1, &v31, &v34, (unsigned int *)&v33);
  if ( OSVersionFromFile < 0 )
    goto LABEL_69;
  v14 = v31;
  if ( v31 )
  {
    OSVersionFromFile = StringCchPrintfW(v40, 0x10u, L"Service Pack %d");
    if ( OSVersionFromFile < 0 )
      goto LABEL_69;
    v14 = v31;
  }
  v36 = &a3[v10 - 1];
  if ( a3 > v36 )
  {
    v17 = v11;
    goto LABEL_54;
  }
  v15 = v11;
  do
  {
    LOWORD(v16) = *a3;
    v17 = v15;
    if ( !*a3 )
      goto LABEL_53;
    v18 = &v11[v10 - 1];
    if ( v15 > v18 )
      goto LABEL_53;
    if ( (_WORD)v16 == 37 )
    {
      v19 = a3++;
      while ( 1 )
      {
        v16 = *a3;
        if ( !(_WORD)v16 )
          goto LABEL_51;
        if ( v16 <= 0x38 )
          break;
        if ( v16 > 0x62 )
        {
          if ( v16 != 104 )
          {
            if ( v16 == 107 )
            {
              *a3++ = 100;
              LOWORD(v16) = *a3;
              *a3 = 0;
              StringCchPrintfExW(v13, a4 - (v13 - v11), &v30, 0, 0x800u, v19);
              v26 = OSVersionFromFile < 0;
              goto LABEL_60;
            }
            if ( v16 != 108 )
            {
              if ( v16 == 109 )
              {
                *a3++ = 100;
                v21 = a4 - (v13 - v11);
                v24 = HIDWORD(v33);
LABEL_57:
                LODWORD(v29) = v24;
LABEL_58:
                LOWORD(v16) = *a3;
                *a3 = 0;
                v25 = StringCchPrintfExW(v13, v21, &v30, 0, 0x800u, v19, v29);
LABEL_59:
                OSVersionFromFile = v25;
                v26 = v25 < 0;
LABEL_60:
                if ( v26 )
                  goto LABEL_69;
                v13 = v30;
                *a3 = v16;
                goto LABEL_51;
              }
              if ( v16 == 115 )
                goto LABEL_64;
              v20 = v16 == 119;
LABEL_48:
              if ( !v20 )
                goto LABEL_64;
            }
          }
        }
        else
        {
          if ( v16 == 98 )
          {
            *a3++ = 100;
            v21 = a4 - (v13 - v11);
            v24 = v33;
            goto LABEL_57;
          }
          if ( v16 != 57 && v16 != 73 )
          {
            if ( v16 == 75 )
            {
              *a3 = 100;
              LODWORD(v29) = v14;
              ++a3;
              v21 = a4 - (v13 - v11);
              goto LABEL_58;
            }
            if ( v16 != 76 )
            {
              if ( v16 == 77 )
              {
                *a3++ = 100;
                v21 = a4 - (v13 - v11);
                v24 = v32;
                goto LABEL_57;
              }
              if ( v16 == 80 )
              {
                *a3++ = 115;
                v21 = a4 - (v13 - v11);
                v29 = v40;
                goto LABEL_58;
              }
LABEL_64:
              LOWORD(v16) = *++a3;
              *a3 = 0;
              v25 = StringCchCopyExW(v13, a4 - (v13 - v11), v19, &v30, v28, 0x800u);
              goto LABEL_59;
            }
          }
        }
LABEL_49:
        ++a3;
        if ( v13 > v18 )
        {
          LOWORD(v16) = *a3;
          goto LABEL_51;
        }
      }
      if ( v16 == 56 )
        goto LABEL_49;
      if ( v16 > 0x31 )
      {
        if ( v16 == 50 || v16 == 51 || v16 == 52 || v16 == 53 || v16 == 54 )
          goto LABEL_49;
        v20 = v16 == 55;
      }
      else
      {
        if ( v16 == 49 || v16 == 32 || v16 == 35 || v16 == 42 || v16 == 43 || v16 == 45 || v16 == 46 )
          goto LABEL_49;
        v20 = v16 == 48;
      }
      goto LABEL_48;
    }
LABEL_51:
    v14 = v31;
    ++a3;
    *v13++ = v16;
    v15 = v13;
    v30 = v13;
  }
  while ( a3 <= v36 );
  v17 = v13;
LABEL_53:
  v8 = v35;
LABEL_54:
  if ( v17 >= &v11[v10] )
  {
    OSVersionFromFile = -2147418113;
  }
  else
  {
    v22 = v37;
    v23 = v38;
    *v13 = 0;
    OSVersionFromFile = StringCchVPrintfW(v8, v23, v11, v22);
  }
LABEL_69:
  HeapFree(hHeap, 0, v11);
  return (unsigned int)OSVersionFromFile;
}

```

## disassembly

```asm
0x180023b14  push    rbp
0x180023b16  push    rbx
0x180023b17  push    rsi
0x180023b18  push    rdi
0x180023b19  push    r12
0x180023b1b  push    r13
0x180023b1d  push    r14
0x180023b1f  push    r15
0x180023b21  lea     rbp, [rsp-0Fh]
0x180023b26  sub     rsp, 0B8h
0x180023b2d  mov     rax, cs:__security_cookie
0x180023b34  xor     rax, rsp
0x180023b37  mov     [rbp+47h+var_48], rax
0x180023b3b  mov     rax, [rbp+47h+arg_28]
0x180023b3f  xor     esi, esi
0x180023b41  mov     [rbp+47h+var_78], rdx
0x180023b45  xorps   xmm0, xmm0
0x180023b48  mov     [rbp+47h+var_90], rcx
0x180023b4c  mov     r12, r9
0x180023b4f  mov     [rbp+47h+var_80], rax
0x180023b53  mov     rbx, r8
0x180023b56  mov     [rbp+47h+var_A4], esi
0x180023b59  mov     rdi, rcx
0x180023b5c  mov     dword ptr [rbp+47h+var_A0+4], esi
0x180023b5f  mov     [rbp+47h+var_A8], esi
0x180023b62  mov     [rbp+47h+var_98], esi
0x180023b65  mov     dword ptr [rbp+47h+var_A0], esi
0x180023b68  mov     [rbp+47h+var_68], si
0x180023b6c  movups  xmmword ptr [rbp+47h+var_66], xmm0
0x180023b70  movups  xmmword ptr [rbp+47h+var_66+0Eh], xmm0
0x180023b74  test    rdx, rdx
0x180023b77  jz      loc_180023F4B
0x180023b7d  mov     [rcx], si
0x180023b80  call    cs:__imp_GetProcessHeap
0x180023b86  mov     [rbp+47h+hHeap], rax
0x180023b8a  test    rax, rax
0x180023b8d  jz      loc_180023F4B
0x180023b93  lea     r13, [r12+r12]
0x180023b97  mov     rcx, rax; hHeap
0x180023b9a  mov     r8, r13; dwBytes
0x180023b9d  lea     edx, [rsi+8]; dwFlags
0x180023ba0  call    cs:__imp_HeapAlloc
0x180023ba6  mov     r15, rax
0x180023ba9  test    rax, rax
0x180023bac  jnz     short loc_180023BB8
0x180023bae  mov     esi, 8007000Eh
0x180023bb3  jmp     loc_180023F50
0x180023bb8  lea     rax, [rbp+47h+var_A0]
0x180023bbc  mov     [rbp+47h+var_B0], r15
0x180023bc0  lea     r9, [rbp+47h+var_98]
0x180023bc4  mov     [rsp+0F0h+var_D0], rax; unsigned __int64 *
0x180023bc9  lea     r8, [rbp+47h+var_A8]
0x180023bcd  mov     r14, r15
0x180023bd0  lea     rdx, [rbp+47h+var_A0+4]
0x180023bd4  lea     rcx, [rbp+47h+var_A4]
0x180023bd8  call    GetOSVersionFromFile
0x180023bdd  xor     r10d, r10d
0x180023be0  mov     esi, eax
0x180023be2  test    eax, eax
0x180023be4  js      loc_180023F3A
0x180023bea  mov     r9d, [rbp+47h+var_A8]
0x180023bee  test    r9d, r9d
0x180023bf1  jz      short loc_180023C18
0x180023bf3  lea     r8, aServicePackD; "Service Pack %d"
0x180023bfa  lea     edx, [r10+10h]; unsigned __int64
0x180023bfe  lea     rcx, [rbp+47h+var_68]; unsigned __int16 *
0x180023c02  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023c07  xor     r10d, r10d
0x180023c0a  mov     esi, eax
0x180023c0c  test    eax, eax
0x180023c0e  js      loc_180023F3A
0x180023c14  mov     r9d, [rbp+47h+var_A8]
0x180023c18  lea     rax, [rbx-2]
0x180023c1c  add     rax, r13
0x180023c1f  mov     [rbp+47h+var_88], rax
0x180023c23  cmp     rbx, rax
0x180023c26  ja      loc_180023F2D
0x180023c2c  mov     rax, r15
0x180023c2f  mov     r11d, 64h ; 'd'
0x180023c35  movzx   edi, word ptr [rbx]
0x180023c38  mov     rcx, rax
0x180023c3b  test    di, di
0x180023c3e  jz      loc_180023DC7
0x180023c44  lea     rdx, [r13-2]
0x180023c48  add     rdx, r15
0x180023c4b  cmp     rax, rdx
0x180023c4e  ja      loc_180023DC7
0x180023c54  mov     eax, 25h ; '%'
0x180023c59  cmp     ax, di
0x180023c5c  jnz     loc_180023DA3
0x180023c62  mov     r8, rbx; unsigned __int16 *
0x180023c65  add     rbx, 2
0x180023c69  movzx   edi, word ptr [rbx]
0x180023c6c  test    di, di
0x180023c6f  jz      loc_180023DA3
0x180023c75  cmp     edi, 38h ; '8'
0x180023c78  ja      loc_180023D06
0x180023c7e  jz      loc_180023D93
0x180023c84  cmp     edi, 31h ; '1'
0x180023c87  ja      short loc_180023CCF
0x180023c89  jz      loc_180023D93
0x180023c8f  mov     ecx, edi
0x180023c91  sub     ecx, 20h ; ' '
0x180023c94  jz      loc_180023D93
0x180023c9a  sub     ecx, 3
0x180023c9d  jz      loc_180023D93
0x180023ca3  sub     ecx, 7
0x180023ca6  jz      loc_180023D93
0x180023cac  sub     ecx, 1
0x180023caf  jz      loc_180023D93
0x180023cb5  sub     ecx, 2
0x180023cb8  jz      loc_180023D93
0x180023cbe  sub     ecx, 1
0x180023cc1  jz      loc_180023D93
0x180023cc7  cmp     ecx, 2
0x180023cca  jmp     loc_180023D8D
0x180023ccf  mov     ecx, edi
0x180023cd1  sub     ecx, 32h ; '2'
0x180023cd4  jz      loc_180023D93
0x180023cda  sub     ecx, 1
0x180023cdd  jz      loc_180023D93
0x180023ce3  sub     ecx, 1
0x180023ce6  jz      loc_180023D93
0x180023cec  sub     ecx, 1
0x180023cef  jz      loc_180023D93
0x180023cf5  sub     ecx, 1
0x180023cf8  jz      loc_180023D93
0x180023cfe  cmp     ecx, 1
0x180023d01  jmp     loc_180023D8D
0x180023d06  cmp     edi, 62h ; 'b'
0x180023d09  ja      short loc_180023D63
0x180023d0b  jz      loc_180023E74
0x180023d11  mov     ecx, edi
0x180023d13  sub     ecx, 39h ; '9'
0x180023d16  jz      short loc_180023D93
0x180023d18  sub     ecx, 10h
0x180023d1b  jz      short loc_180023D93
0x180023d1d  sub     ecx, 2
0x180023d20  jz      loc_180023E56
0x180023d26  sub     ecx, 1
0x180023d29  jz      short loc_180023D93
0x180023d2b  sub     ecx, 1
0x180023d2e  jz      loc_180023DF6
0x180023d34  sub     ecx, 3
0x180023d37  jnz     loc_180023E90
0x180023d3d  mov     rax, r14
0x180023d40  mov     word ptr [rbx], 73h ; 's'
0x180023d45  sub     rax, r15
0x180023d48  add     rbx, 2
0x180023d4c  sar     rax, 1
0x180023d4f  mov     rdx, r12
0x180023d52  sub     rdx, rax
0x180023d55  lea     rax, [rbp+47h+var_68]
0x180023d59  mov     [rsp+0F0h+var_C0], rax
0x180023d5e  jmp     loc_180023E14
0x180023d63  mov     ecx, edi
0x180023d65  sub     ecx, 68h ; 'h'
0x180023d68  jz      short loc_180023D93
0x180023d6a  sub     ecx, 3
0x180023d6d  jz      loc_180023EE2
0x180023d73  sub     ecx, 1
0x180023d76  jz      short loc_180023D93
0x180023d78  sub     ecx, 1
0x180023d7b  jz      loc_180023EC3
0x180023d81  sub     ecx, 6
0x180023d84  jz      loc_180023E90
0x180023d8a  cmp     ecx, 4
0x180023d8d  jnz     loc_180023E90
0x180023d93  add     rbx, 2
0x180023d97  cmp     r14, rdx
0x180023d9a  jbe     loc_180023C69
0x180023da0  movzx   edi, word ptr [rbx]
0x180023da3  mov     r9d, [rbp+47h+var_A8]
0x180023da7  add     rbx, 2
0x180023dab  mov     [r14], di
0x180023daf  add     r14, 2
0x180023db3  mov     rax, r14
0x180023db6  mov     [rbp+47h+var_B0], r14
0x180023dba  cmp     rbx, [rbp+47h+var_88]
0x180023dbe  jbe     loc_180023C35
0x180023dc4  mov     rcx, rax
0x180023dc7  mov     rdi, [rbp+47h+var_90]
0x180023dcb  lea     rax, [r15+r13]
0x180023dcf  cmp     rcx, rax
0x180023dd2  jnb     loc_180023F35
0x180023dd8  mov     r9, [rbp+47h+var_80]; char *
0x180023ddc  mov     r8, r15; unsigned __int16 *
0x180023ddf  mov     rdx, [rbp+47h+var_78]; unsigned __int64
0x180023de3  mov     rcx, rdi; unsigned __int16 *
0x180023de6  mov     [r14], r10w
0x180023dea  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x180023def  mov     esi, eax
0x180023df1  jmp     loc_180023F3A
0x180023df6  mov     rax, r14
0x180023df9  mov     [rbx], r11w
0x180023dfd  sub     rax, r15
0x180023e00  add     rbx, 2
0x180023e04  sar     rax, 1
0x180023e07  mov     rdx, r12
0x180023e0a  sub     rdx, rax; unsigned __int64
0x180023e0d  mov     eax, [rbp+47h+var_A4]
0x180023e10  mov     dword ptr [rsp+0F0h+var_C0], eax
0x180023e14  movzx   edi, word ptr [rbx]
0x180023e17  xor     r9d, r9d; unsigned __int64 *
0x180023e1a  mov     [rsp+0F0h+var_C8], r8; unsigned __int16 *
0x180023e1f  mov     rcx, r14; Buffer
0x180023e22  lea     r8, [rbp+47h+var_B0]; unsigned __int16 **
0x180023e26  mov     [rbx], r10w
0x180023e2a  mov     dword ptr [rsp+0F0h+var_D0], 800h; unsigned int
0x180023e32  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180023e37  xor     r10d, r10d
0x180023e3a  mov     esi, eax
0x180023e3c  test    eax, eax
0x180023e3e  js      loc_180023F3A
0x180023e44  mov     r14, [rbp+47h+var_B0]
0x180023e48  mov     r11d, 64h ; 'd'
0x180023e4e  mov     [rbx], di
0x180023e51  jmp     loc_180023DA3
0x180023e56  mov     rax, r14
0x180023e59  mov     [rbx], r11w
0x180023e5d  sub     rax, r15
0x180023e60  mov     dword ptr [rsp+0F0h+var_C0], r9d
0x180023e65  sar     rax, 1
0x180023e68  add     rbx, 2
0x180023e6c  mov     rdx, r12
0x180023e6f  sub     rdx, rax
0x180023e72  jmp     short loc_180023E14
0x180023e74  mov     rax, r14
0x180023e77  mov     [rbx], r11w
0x180023e7b  sub     rax, r15
0x180023e7e  add     rbx, 2
0x180023e82  sar     rax, 1
0x180023e85  mov     rdx, r12
0x180023e88  sub     rdx, rax
0x180023e8b  mov     eax, dword ptr [rbp+47h+var_A0]
0x180023e8e  jmp     short loc_180023E10
0x180023e90  add     rbx, 2
0x180023e94  mov     dword ptr [rsp+0F0h+var_C8], 800h; unsigned int
0x180023e9c  mov     rax, r14
0x180023e9f  lea     r9, [rbp+47h+var_B0]; unsigned __int16 **
0x180023ea3  sub     rax, r15
0x180023ea6  mov     rdx, r12
0x180023ea9  sar     rax, 1
0x180023eac  mov     rcx, r14; unsigned __int16 *
0x180023eaf  movzx   edi, word ptr [rbx]
0x180023eb2  sub     rdx, rax; unsigned __int64
0x180023eb5  mov     [rbx], r10w
0x180023eb9  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180023ebe  jmp     loc_180023E37
0x180023ec3  mov     rax, r14
0x180023ec6  mov     [rbx], r11w
0x180023eca  sub     rax, r15
0x180023ecd  add     rbx, 2
0x180023ed1  sar     rax, 1
0x180023ed4  mov     rdx, r12
0x180023ed7  sub     rdx, rax
0x180023eda  mov     eax, dword ptr [rbp+47h+var_A0+4]
0x180023edd  jmp     loc_180023E10
0x180023ee2  mov     [rbx], r11w
0x180023ee6  mov     rax, r14
0x180023ee9  sub     rax, r15
0x180023eec  add     rbx, 2
0x180023ef0  sar     rax, 1
0x180023ef3  mov     rdx, r12
0x180023ef6  sub     rdx, rax; unsigned __int64
0x180023ef9  xor     r9d, r9d; unsigned __int64 *
0x180023efc  mov     eax, [rbp+47h+var_98]
0x180023eff  mov     rcx, r14; Buffer
0x180023f02  movzx   edi, word ptr [rbx]
0x180023f05  mov     dword ptr [rsp+0F0h+var_C0], eax
0x180023f09  mov     [rsp+0F0h+var_C8], r8; unsigned __int16 *
0x180023f0e  lea     r8, [rbp+47h+var_B0]; unsigned __int16 **
0x180023f12  mov     [rbx], r10w
0x180023f16  mov     dword ptr [rsp+0F0h+var_D0], 800h; unsigned int
0x180023f1e  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180023f23  xor     r10d, r10d
0x180023f26  test    esi, esi
0x180023f28  jmp     loc_180023E3E
0x180023f2d  mov     rcx, r15
0x180023f30  jmp     loc_180023DCB
0x180023f35  mov     esi, 8000FFFFh
0x180023f3a  mov     rcx, [rbp+47h+hHeap]; hHeap
0x180023f3e  mov     r8, r15; lpMem
0x180023f41  xor     edx, edx; dwFlags
0x180023f43  call    cs:__imp_HeapFree
0x180023f49  jmp     short loc_180023F50
0x180023f4b  mov     esi, 8000FFFFh
0x180023f50  mov     eax, esi
0x180023f52  mov     rcx, [rbp+47h+var_48]
0x180023f56  xor     rcx, rsp; StackCookie
0x180023f59  call    __security_check_cookie
0x180023f5e  add     rsp, 0B8h
0x180023f65  pop     r15
0x180023f67  pop     r14
0x180023f69  pop     r13
0x180023f6b  pop     r12
0x180023f6d  pop     rdi
0x180023f6e  pop     rsi
0x180023f6f  pop     rbx
0x180023f70  pop     rbp
  ... truncated ...
```
