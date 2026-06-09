# VersionSPrintfHelper

- ea: `0x1800476ec`
- end: `0x180047ba1`
- name: `VersionSPrintfHelper`
- size: `1205`
- prototype: `__int64 __usercall@<rax>(wchar_t *Buffer@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180047ba8`

## callees

- `0x18001c5bc`
- `0x180041d48`
- `0x180046fb0`
- `0x180047178`
- `0x1800476ec`
- `0x180050300`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180047b38`
- `msvcrt!_vsnwprintf` at `0x180047b38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004775f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004775f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047781`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047781`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047b72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047b72`

## string_xrefs

- `0x1800477d4`: `Service Pack %d`

## pseudocode

```c
__int64 __fastcall VersionSPrintfHelper(
        wchar_t *Buffer,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5,
        va_list a6)
{
  unsigned __int64 v8; // rsi
  unsigned __int16 *v10; // r15
  int OSVersionFromFile; // ebx
  unsigned __int16 *v12; // r14
  unsigned int v13; // r9d
  __int64 v14; // r8
  unsigned __int16 *v15; // rax
  unsigned int v16; // esi
  unsigned __int16 *v17; // rcx
  unsigned __int16 *v18; // rdx
  const unsigned __int16 *v19; // r8
  bool v20; // zf
  int v21; // eax
  bool v22; // sf
  unsigned __int64 v23; // rdx
  int v24; // eax
  unsigned __int64 v25; // rdi
  int v26; // eax
  unsigned __int64 *v28; // [rsp+20h] [rbp-89h]
  unsigned __int16 *v29; // [rsp+30h] [rbp-79h]
  unsigned __int16 *v30; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v31; // [rsp+48h] [rbp-61h] BYREF
  int v32; // [rsp+4Ch] [rbp-5Dh] BYREF
  unsigned __int64 v33; // [rsp+50h] [rbp-59h] BYREF
  int v34; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int64 v35; // [rsp+60h] [rbp-49h]
  unsigned __int64 v36; // [rsp+68h] [rbp-41h]
  va_list Args; // [rsp+70h] [rbp-39h]
  HANDLE hHeap; // [rsp+78h] [rbp-31h]
  unsigned __int16 v39[16]; // [rsp+80h] [rbp-29h] BYREF

  v35 = a2;
  Args = a6;
  v32 = 0;
  v8 = a2;
  v31 = 0;
  v34 = 0;
  v33 = 0;
  memset(v39, 0, sizeof(v39));
  if ( !a2 )
    return (unsigned int)-2147418113;
  *Buffer = 0;
  if ( (hHeap = GetProcessHeap()) == 0 )
    return (unsigned int)-2147418113;
  v10 = (unsigned __int16 *)HeapAlloc(hHeap, 8u, 2 * a4);
  if ( v10 )
  {
    v30 = v10;
    v12 = v10;
    OSVersionFromFile = GetOSVersionFromFile(&v32, (_DWORD *)&v33 + 1, &v31, &v34, (unsigned int *)&v33);
    if ( OSVersionFromFile >= 0 )
    {
      v13 = v31;
      if ( v31 )
      {
        OSVersionFromFile = StringCchPrintfW(v39, 0x10u, L"Service Pack %d");
        if ( OSVersionFromFile < 0 )
          goto LABEL_76;
        v13 = v31;
      }
      v14 = a4;
      v36 = (unsigned __int64)&a3[a4 - 1];
      if ( (unsigned __int64)a3 > v36 )
      {
        v17 = v10;
        goto LABEL_58;
      }
      v15 = v10;
LABEL_11:
      LOWORD(v16) = *a3;
      v17 = v15;
      if ( *a3 )
      {
        v18 = &v10[v14 - 1];
        if ( v15 <= v18 )
        {
          if ( (_WORD)v16 != 37 )
            goto LABEL_55;
          v19 = a3++;
          while ( 1 )
          {
            v16 = *a3;
            if ( !(_WORD)v16 )
            {
LABEL_54:
              v14 = a4;
LABEL_55:
              v13 = v31;
              ++a3;
              *v12++ = v16;
              v15 = v12;
              v30 = v12;
              if ( (unsigned __int64)a3 > v36 )
              {
                v17 = v12;
                goto LABEL_57;
              }
              goto LABEL_11;
            }
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
                  StringCchPrintfExW(v12, a4 - (v12 - v10), &v30, 0, 0x800u, v19);
                  v22 = OSVersionFromFile < 0;
                  goto LABEL_43;
                }
                if ( v16 != 108 )
                {
                  if ( v16 == 109 )
                  {
                    *a3++ = 100;
                    v23 = a4 - (v12 - v10);
                    v24 = HIDWORD(v33);
LABEL_64:
                    LODWORD(v29) = v24;
LABEL_62:
                    LOWORD(v16) = *a3;
                    *a3 = 0;
                    v21 = StringCchPrintfExW(v12, v23, &v30, 0, 0x800u, v19, v29);
LABEL_42:
                    OSVersionFromFile = v21;
                    v22 = v21 < 0;
LABEL_43:
                    if ( v22 )
                      goto LABEL_76;
                    v12 = v30;
                    *a3 = v16;
                    goto LABEL_54;
                  }
                  if ( v16 == 115 )
                    goto LABEL_41;
                  v20 = v16 == 119;
LABEL_51:
                  if ( !v20 )
                    goto LABEL_41;
                }
              }
            }
            else
            {
              if ( v16 == 98 )
              {
                *a3++ = 100;
                v23 = a4 - (v12 - v10);
                v24 = v33;
                goto LABEL_64;
              }
              if ( v16 != 57 && v16 != 73 )
              {
                if ( v16 == 75 )
                {
                  *a3 = 100;
                  LODWORD(v29) = v13;
                  ++a3;
                  v23 = a4 - (v12 - v10);
                  goto LABEL_62;
                }
                if ( v16 != 76 )
                {
                  if ( v16 == 77 )
                  {
                    *a3++ = 100;
                    v23 = a4 - (v12 - v10);
                    v24 = v32;
                    goto LABEL_64;
                  }
                  if ( v16 == 80 )
                  {
                    *a3++ = 115;
                    v23 = a4 - (v12 - v10);
                    v29 = v39;
                    goto LABEL_62;
                  }
LABEL_41:
                  LOWORD(v16) = *++a3;
                  *a3 = 0;
                  v21 = StringCchCopyExW(v12, a4 - (v12 - v10), v19, &v30, v28, 0x800u);
                  goto LABEL_42;
                }
              }
            }
LABEL_52:
            ++a3;
            if ( v12 > v18 )
            {
              LOWORD(v16) = *a3;
              goto LABEL_54;
            }
          }
          if ( v16 == 56 )
            goto LABEL_52;
          if ( v16 > 0x31 )
          {
            if ( v16 == 50 || v16 == 51 || v16 == 52 || v16 == 53 || v16 == 54 )
              goto LABEL_52;
            v20 = v16 == 55;
          }
          else
          {
            if ( v16 == 49 || v16 == 32 || v16 == 35 || v16 == 42 || v16 == 43 || v16 == 45 || v16 == 46 )
              goto LABEL_52;
            v20 = v16 == 48;
          }
          goto LABEL_51;
        }
      }
LABEL_57:
      v8 = v35;
LABEL_58:
      if ( v17 >= &v10[v14] )
      {
        OSVersionFromFile = -2147418113;
      }
      else
      {
        *v12 = 0;
        if ( v8 <= 0x7FFFFFFF )
        {
          v25 = v8 - 1;
          v26 = _vsnwprintf(Buffer, v8 - 1, v10, Args);
          if ( v26 < 0 || v26 > v25 )
          {
            Buffer[v25] = 0;
            OSVersionFromFile = -2147024774;
          }
          else
          {
            OSVersionFromFile = 0;
            if ( v26 == v25 )
              Buffer[v25] = 0;
          }
        }
        else
        {
          OSVersionFromFile = -2147024809;
          *Buffer = 0;
        }
      }
    }
LABEL_76:
    HeapFree(hHeap, 0, v10);
    return (unsigned int)OSVersionFromFile;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x1800476ec  push    rbp
0x1800476ee  push    rbx
0x1800476ef  push    rsi
0x1800476f0  push    rdi
0x1800476f1  push    r12
0x1800476f3  push    r13
0x1800476f5  push    r14
0x1800476f7  push    r15
0x1800476f9  lea     rbp, [rsp-0Fh]
0x1800476fe  sub     rsp, 0B8h
0x180047705  mov     rax, cs:__security_cookie
0x18004770c  xor     rax, rsp
0x18004770f  mov     [rbp+47h+var_50], rax
0x180047713  mov     rax, [rbp+47h+arg_28]
0x180047717  xor     r14d, r14d
0x18004771a  mov     [rbp+47h+var_90], rdx
0x18004771e  xorps   xmm0, xmm0
0x180047721  mov     [rbp+47h+Args], rax
0x180047725  mov     r13, r9
0x180047728  mov     [rbp+47h+var_A4], r14d
0x18004772c  mov     rdi, r8
0x18004772f  mov     dword ptr [rbp+47h+var_A0+4], r14d
0x180047733  mov     rsi, rdx
0x180047736  mov     [rbp+47h+var_A8], r14d
0x18004773a  mov     r12, rcx
0x18004773d  mov     [rbp+47h+var_98], r14d
0x180047741  mov     dword ptr [rbp+47h+var_A0], r14d
0x180047745  mov     [rbp+47h+var_70], r14w
0x18004774a  movups  xmmword ptr [rbp+47h+var_6E], xmm0
0x18004774e  movups  xmmword ptr [rbp+47h+var_6E+0Eh], xmm0
0x180047752  test    rdx, rdx
0x180047755  jz      loc_180047B7A
0x18004775b  mov     [rcx], r14w
0x18004775f  call    cs:__imp_GetProcessHeap
0x180047765  mov     [rbp+47h+hHeap], rax
0x180047769  mov     rcx, rax; hHeap
0x18004776c  test    rax, rax
0x18004776f  jz      loc_180047B7A
0x180047775  lea     r8, ds:0[r13*2]; dwBytes
0x18004777d  lea     edx, [r14+8]; dwFlags
0x180047781  call    cs:__imp_HeapAlloc
0x180047787  mov     r15, rax
0x18004778a  test    rax, rax
0x18004778d  jnz     short loc_180047799
0x18004778f  mov     ebx, 8007000Eh
0x180047794  jmp     loc_180047B7F
0x180047799  lea     rax, [rbp+47h+var_A0]
0x18004779d  mov     [rbp+47h+var_B0], r15
0x1800477a1  lea     r9, [rbp+47h+var_98]
0x1800477a5  mov     [rsp+0F0h+var_D0], rax; unsigned __int64 *
0x1800477aa  lea     r8, [rbp+47h+var_A8]
0x1800477ae  mov     r14, r15
0x1800477b1  lea     rdx, [rbp+47h+var_A0+4]
0x1800477b5  lea     rcx, [rbp+47h+var_A4]
0x1800477b9  call    GetOSVersionFromFile
0x1800477be  xor     r10d, r10d
0x1800477c1  mov     ebx, eax
0x1800477c3  test    eax, eax
0x1800477c5  js      loc_180047B69
0x1800477cb  mov     r9d, [rbp+47h+var_A8]
0x1800477cf  test    r9d, r9d
0x1800477d2  jz      short loc_1800477F9
0x1800477d4  lea     r8, aServicePackD; "Service Pack %d"
0x1800477db  lea     edx, [r10+10h]; unsigned __int64
0x1800477df  lea     rcx, [rbp+47h+var_70]; unsigned __int16 *
0x1800477e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800477e8  xor     r10d, r10d
0x1800477eb  mov     ebx, eax
0x1800477ed  test    eax, eax
0x1800477ef  js      loc_180047B69
0x1800477f5  mov     r9d, [rbp+47h+var_A8]
0x1800477f9  lea     r8, ds:0[r13*2]
0x180047801  lea     rax, [rdi-2]
0x180047805  add     rax, r8
0x180047808  mov     [rbp+47h+var_88], rax
0x18004780c  cmp     rdi, rax
0x18004780f  ja      loc_180047B1F
0x180047815  mov     rax, r15
0x180047818  mov     r11d, 64h ; 'd'
0x18004781e  movzx   esi, word ptr [rdi]
0x180047821  mov     rcx, rax
0x180047824  test    si, si
0x180047827  jz      loc_1800479E4
0x18004782d  lea     rdx, [r15-2]
0x180047831  add     rdx, r8
0x180047834  cmp     rax, rdx
0x180047837  ja      loc_1800479E4
0x18004783d  mov     eax, 25h ; '%'
0x180047842  cmp     ax, si
0x180047845  jnz     loc_1800479C0
0x18004784b  mov     r8, rdi; unsigned __int16 *
0x18004784e  add     rdi, 2
0x180047852  movzx   esi, word ptr [rdi]
0x180047855  test    si, si
0x180047858  jz      loc_1800479B8
0x18004785e  cmp     esi, 38h ; '8'
0x180047861  ja      loc_1800478EF
0x180047867  jz      loc_1800479A8
0x18004786d  cmp     esi, 31h ; '1'
0x180047870  ja      short loc_1800478B8
0x180047872  jz      loc_1800479A8
0x180047878  mov     ecx, esi
0x18004787a  sub     ecx, 20h ; ' '
0x18004787d  jz      loc_1800479A8
0x180047883  sub     ecx, 3
0x180047886  jz      loc_1800479A8
0x18004788c  sub     ecx, 7
0x18004788f  jz      loc_1800479A8
0x180047895  sub     ecx, 1
0x180047898  jz      loc_1800479A8
0x18004789e  sub     ecx, 2
0x1800478a1  jz      loc_1800479A8
0x1800478a7  sub     ecx, 1
0x1800478aa  jz      loc_1800479A8
0x1800478b0  cmp     ecx, 2
0x1800478b3  jmp     loc_1800479A6
0x1800478b8  mov     ecx, esi
0x1800478ba  sub     ecx, 32h ; '2'
0x1800478bd  jz      loc_1800479A8
0x1800478c3  sub     ecx, 1
0x1800478c6  jz      loc_1800479A8
0x1800478cc  sub     ecx, 1
0x1800478cf  jz      loc_1800479A8
0x1800478d5  sub     ecx, 1
0x1800478d8  jz      loc_1800479A8
0x1800478de  sub     ecx, 1
0x1800478e1  jz      loc_1800479A8
0x1800478e7  cmp     ecx, 1
0x1800478ea  jmp     loc_1800479A6
0x1800478ef  cmp     esi, 62h ; 'b'
0x1800478f2  ja      loc_180047980
0x1800478f8  jz      loc_180047A9C
0x1800478fe  mov     ecx, esi
0x180047900  sub     ecx, 39h ; '9'
0x180047903  jz      loc_1800479A8
0x180047909  sub     ecx, 10h
0x18004790c  jz      loc_1800479A8
0x180047912  sub     ecx, 2
0x180047915  jz      loc_180047A7E
0x18004791b  sub     ecx, 1
0x18004791e  jz      loc_1800479A8
0x180047924  sub     ecx, 1
0x180047927  jz      loc_180047A5E
0x18004792d  sub     ecx, 3
0x180047930  jz      loc_180047A15
0x180047936  add     rdi, 2
0x18004793a  mov     dword ptr [rsp+0F0h+var_C8], 800h; unsigned int
0x180047942  mov     rax, r14
0x180047945  lea     r9, [rbp+47h+var_B0]; unsigned __int16 **
0x180047949  sub     rax, r15
0x18004794c  mov     rdx, r13
0x18004794f  sar     rax, 1
0x180047952  mov     rcx, r14; pszDest
0x180047955  movzx   esi, word ptr [rdi]
0x180047958  sub     rdx, rax; unsigned __int64
0x18004795b  mov     [rdi], r10w
0x18004795f  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180047964  xor     r10d, r10d
0x180047967  mov     ebx, eax
0x180047969  test    eax, eax
0x18004796b  js      loc_180047B69
0x180047971  mov     r14, [rbp+47h+var_B0]
0x180047975  mov     r11d, 64h ; 'd'
0x18004797b  mov     [rdi], si
0x18004797e  jmp     short loc_1800479B8
0x180047980  mov     ecx, esi
0x180047982  sub     ecx, 68h ; 'h'
0x180047985  jz      short loc_1800479A8
0x180047987  sub     ecx, 3
0x18004798a  jz      loc_180047AD4
0x180047990  sub     ecx, 1
0x180047993  jz      short loc_1800479A8
0x180047995  sub     ecx, 1
0x180047998  jz      loc_180047AB8
0x18004799e  sub     ecx, 6
0x1800479a1  jz      short loc_180047936
0x1800479a3  cmp     ecx, 4
0x1800479a6  jnz     short loc_180047936
0x1800479a8  add     rdi, 2
0x1800479ac  cmp     r14, rdx
0x1800479af  jbe     loc_180047852
0x1800479b5  movzx   esi, word ptr [rdi]
0x1800479b8  lea     r8, ds:0[r13*2]
0x1800479c0  mov     r9d, [rbp+47h+var_A8]
0x1800479c4  add     rdi, 2
0x1800479c8  mov     [r14], si
0x1800479cc  add     r14, 2
0x1800479d0  mov     rax, r14
0x1800479d3  mov     [rbp+47h+var_B0], r14
0x1800479d7  cmp     rdi, [rbp+47h+var_88]
0x1800479db  jbe     loc_18004781E
0x1800479e1  mov     rcx, rax
0x1800479e4  mov     rsi, [rbp+47h+var_90]
0x1800479e8  lea     rax, [r8+r15]
0x1800479ec  cmp     rcx, rax
0x1800479ef  jnb     loc_180047B64
0x1800479f5  mov     [r14], r10w
0x1800479f9  cmp     rsi, 7FFFFFFFh
0x180047a00  jbe     loc_180047B27
0x180047a06  mov     ebx, 80070057h
0x180047a0b  mov     [r12], r10w
0x180047a10  jmp     loc_180047B69
0x180047a15  mov     rax, r14
0x180047a18  mov     word ptr [rdi], 73h ; 's'
0x180047a1d  sub     rax, r15
0x180047a20  add     rdi, 2
0x180047a24  sar     rax, 1
0x180047a27  mov     rdx, r13
0x180047a2a  sub     rdx, rax; unsigned __int64
0x180047a2d  lea     rax, [rbp+47h+var_70]
0x180047a31  mov     [rsp+0F0h+var_C0], rax
0x180047a36  movzx   esi, word ptr [rdi]
0x180047a39  xor     r9d, r9d; unsigned __int64 *
0x180047a3c  mov     [rsp+0F0h+var_C8], r8; unsigned __int16 *
0x180047a41  mov     rcx, r14; Buffer
0x180047a44  lea     r8, [rbp+47h+var_B0]; unsigned __int16 **
0x180047a48  mov     [rdi], r10w
0x180047a4c  mov     dword ptr [rsp+0F0h+var_D0], 800h; unsigned int
0x180047a54  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180047a59  jmp     loc_180047964
0x180047a5e  mov     rax, r14
0x180047a61  mov     [rdi], r11w
0x180047a65  sub     rax, r15
0x180047a68  add     rdi, 2
0x180047a6c  sar     rax, 1
0x180047a6f  mov     rdx, r13
0x180047a72  sub     rdx, rax
0x180047a75  mov     eax, [rbp+47h+var_A4]
0x180047a78  mov     dword ptr [rsp+0F0h+var_C0], eax
0x180047a7c  jmp     short loc_180047A36
0x180047a7e  mov     rax, r14
0x180047a81  mov     [rdi], r11w
0x180047a85  sub     rax, r15
0x180047a88  mov     dword ptr [rsp+0F0h+var_C0], r9d
0x180047a8d  sar     rax, 1
0x180047a90  add     rdi, 2
0x180047a94  mov     rdx, r13
0x180047a97  sub     rdx, rax
0x180047a9a  jmp     short loc_180047A36
0x180047a9c  mov     rax, r14
0x180047a9f  mov     [rdi], r11w
0x180047aa3  sub     rax, r15
0x180047aa6  add     rdi, 2
0x180047aaa  sar     rax, 1
0x180047aad  mov     rdx, r13
0x180047ab0  sub     rdx, rax
0x180047ab3  mov     eax, dword ptr [rbp+47h+var_A0]
0x180047ab6  jmp     short loc_180047A78
0x180047ab8  mov     rax, r14
0x180047abb  mov     [rdi], r11w
0x180047abf  sub     rax, r15
0x180047ac2  add     rdi, 2
0x180047ac6  sar     rax, 1
0x180047ac9  mov     rdx, r13
0x180047acc  sub     rdx, rax
0x180047acf  mov     eax, dword ptr [rbp+47h+var_A0+4]
0x180047ad2  jmp     short loc_180047A78
0x180047ad4  mov     [rdi], r11w
0x180047ad8  mov     rax, r14
0x180047adb  sub     rax, r15
0x180047ade  add     rdi, 2
0x180047ae2  sar     rax, 1
0x180047ae5  mov     rdx, r13
0x180047ae8  sub     rdx, rax; unsigned __int64
0x180047aeb  xor     r9d, r9d; unsigned __int64 *
0x180047aee  mov     eax, [rbp+47h+var_98]
0x180047af1  mov     rcx, r14; Buffer
0x180047af4  movzx   esi, word ptr [rdi]
0x180047af7  mov     dword ptr [rsp+0F0h+var_C0], eax
0x180047afb  mov     [rsp+0F0h+var_C8], r8; unsigned __int16 *
0x180047b00  lea     r8, [rbp+47h+var_B0]; unsigned __int16 **
0x180047b04  mov     [rdi], r10w
0x180047b08  mov     dword ptr [rsp+0F0h+var_D0], 800h; unsigned int
0x180047b10  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180047b15  xor     r10d, r10d
0x180047b18  test    ebx, ebx
0x180047b1a  jmp     loc_18004796B
0x180047b1f  mov     rcx, r15
0x180047b22  jmp     loc_1800479E8
0x180047b27  mov     r9, [rbp+47h+Args]; Args
0x180047b2b  lea     rdi, [rsi-1]
0x180047b2f  mov     rdx, rdi; BufferCount
0x180047b32  mov     r8, r15; Format
0x180047b35  mov     rcx, r12; Buffer
0x180047b38  call    cs:__imp__vsnwprintf
0x180047b3e  xor     r14d, r14d
0x180047b41  test    eax, eax
0x180047b43  js      short loc_180047B58
0x180047b45  cdqe
0x180047b47  cmp     rax, rdi
0x180047b4a  ja      short loc_180047B58
0x180047b4c  mov     ebx, r14d
0x180047b4f  jnz     short loc_180047B69
0x180047b51  mov     [r12+rdi*2], r14w
0x180047b56  jmp     short loc_180047B69
0x180047b58  mov     [r12+rdi*2], r14w
0x180047b5d  mov     ebx, 8007007Ah
0x180047b62  jmp     short loc_180047B69
0x180047b64  mov     ebx, 8000FFFFh
0x180047b69  mov     rcx, [rbp+47h+hHeap]; hHeap
  ... truncated ...
```
