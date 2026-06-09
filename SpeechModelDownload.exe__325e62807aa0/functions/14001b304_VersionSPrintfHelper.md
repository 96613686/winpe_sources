# VersionSPrintfHelper

- ea: `0x14001b304`
- end: `0x14001b7a8`
- name: `VersionSPrintfHelper`
- size: `1188`
- prototype: `__int64 __usercall@<rax>(wchar_t *Buffer@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x14001b7b0`

## callees

- `0x140002600`
- `0x1400030f4`
- `0x140008e98`
- `0x140019c34`
- `0x14001accc`
- `0x14001b230`
- `0x14001b304`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001b399`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001b399`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b377`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b377`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001b779`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001b779`

## string_xrefs

- `0x14001b3ec`: `Service Pack %d`

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
  unsigned __int16 *v19; // r8
  bool v20; // zf
  int v21; // eax
  bool v22; // sf
  unsigned __int64 v23; // rdx
  int v24; // eax
  unsigned __int64 v25; // rdi
  int v26; // eax
  unsigned __int16 *v28; // [rsp+30h] [rbp-79h]
  unsigned __int16 *v29; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v30; // [rsp+48h] [rbp-61h] BYREF
  int v31; // [rsp+4Ch] [rbp-5Dh] BYREF
  unsigned __int64 v32; // [rsp+50h] [rbp-59h] BYREF
  int v33; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int64 v34; // [rsp+60h] [rbp-49h]
  unsigned __int64 v35; // [rsp+68h] [rbp-41h]
  va_list Args; // [rsp+70h] [rbp-39h]
  HANDLE hHeap; // [rsp+78h] [rbp-31h]
  unsigned __int16 v38[16]; // [rsp+80h] [rbp-29h] BYREF

  v34 = a2;
  Args = a6;
  v31 = 0;
  v8 = a2;
  v30 = 0;
  v33 = 0;
  v32 = 0;
  memset(v38, 0, sizeof(v38));
  if ( !a2 )
    return (unsigned int)-2147418113;
  *Buffer = 0;
  if ( (hHeap = GetProcessHeap()) == 0 )
    return (unsigned int)-2147418113;
  v10 = (unsigned __int16 *)HeapAlloc(hHeap, 8u, 2 * a4);
  if ( v10 )
  {
    v29 = v10;
    v12 = v10;
    OSVersionFromFile = GetOSVersionFromFile(&v31, (_DWORD *)&v32 + 1, &v30, &v33, (unsigned int *)&v32);
    if ( OSVersionFromFile >= 0 )
    {
      v13 = v30;
      if ( v30 )
      {
        OSVersionFromFile = StringCchPrintfW(v38, 0x10u, L"Service Pack %d");
        if ( OSVersionFromFile < 0 )
          goto LABEL_76;
        v13 = v30;
      }
      v14 = a4;
      v35 = (unsigned __int64)&a3[a4 - 1];
      if ( (unsigned __int64)a3 > v35 )
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
              v13 = v30;
              ++a3;
              *v12++ = v16;
              v15 = v12;
              v29 = v12;
              if ( (unsigned __int64)a3 > v35 )
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
                  LODWORD(v28) = v33;
                  *a3 = 0;
                  StringCchPrintfExW(v12, a4 - (v12 - v10), &v29, 0, 0x800u, v19, v28);
                  v22 = OSVersionFromFile < 0;
                  goto LABEL_43;
                }
                if ( v16 != 108 )
                {
                  if ( v16 == 109 )
                  {
                    *a3++ = 100;
                    v23 = a4 - (v12 - v10);
                    v24 = HIDWORD(v32);
LABEL_64:
                    LODWORD(v28) = v24;
LABEL_62:
                    LOWORD(v16) = *a3;
                    *a3 = 0;
                    v21 = StringCchPrintfExW(v12, v23, &v29, 0, 0x800u, v19, v28);
LABEL_42:
                    OSVersionFromFile = v21;
                    v22 = v21 < 0;
LABEL_43:
                    if ( v22 )
                      goto LABEL_76;
                    v12 = v29;
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
                v24 = v32;
                goto LABEL_64;
              }
              if ( v16 != 57 && v16 != 73 )
              {
                if ( v16 == 75 )
                {
                  *a3 = 100;
                  LODWORD(v28) = v13;
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
                    v24 = v31;
                    goto LABEL_64;
                  }
                  if ( v16 == 80 )
                  {
                    *a3++ = 115;
                    v23 = a4 - (v12 - v10);
                    v28 = v38;
                    goto LABEL_62;
                  }
LABEL_41:
                  LOWORD(v16) = *++a3;
                  *a3 = 0;
                  v21 = StringCchCopyExW(v12, a4 - (v12 - v10), v19, &v29);
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
      v8 = v34;
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
          v26 = vsnwprintf(Buffer, v8 - 1, v10, Args);
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
0x14001b304  push    rbp
0x14001b306  push    rbx
0x14001b307  push    rsi
0x14001b308  push    rdi
0x14001b309  push    r12
0x14001b30b  push    r13
0x14001b30d  push    r14
0x14001b30f  push    r15
0x14001b311  lea     rbp, [rsp-0Fh]
0x14001b316  sub     rsp, 0B8h
0x14001b31d  mov     rax, cs:__security_cookie
0x14001b324  xor     rax, rsp
0x14001b327  mov     [rbp+47h+var_50], rax
0x14001b32b  mov     rax, [rbp+47h+arg_28]
0x14001b32f  xor     r14d, r14d
0x14001b332  mov     [rbp+47h+var_90], rdx
0x14001b336  xorps   xmm0, xmm0
0x14001b339  mov     [rbp+47h+Args], rax
0x14001b33d  mov     r13, r9
0x14001b340  mov     [rbp+47h+var_A4], r14d
0x14001b344  mov     rdi, r8
0x14001b347  mov     dword ptr [rbp+47h+var_A0+4], r14d
0x14001b34b  mov     rsi, rdx
0x14001b34e  mov     [rbp+47h+var_A8], r14d
0x14001b352  mov     r12, rcx
0x14001b355  mov     [rbp+47h+var_98], r14d
0x14001b359  mov     dword ptr [rbp+47h+var_A0], r14d
0x14001b35d  mov     [rbp+47h+var_70], r14w
0x14001b362  movups  xmmword ptr [rbp+47h+var_6E], xmm0
0x14001b366  movups  xmmword ptr [rbp+47h+var_6E+0Eh], xmm0
0x14001b36a  test    rdx, rdx
0x14001b36d  jz      loc_14001B781
0x14001b373  mov     [rcx], r14w
0x14001b377  call    cs:__imp_GetProcessHeap
0x14001b37d  mov     [rbp+47h+hHeap], rax
0x14001b381  mov     rcx, rax; hHeap
0x14001b384  test    rax, rax
0x14001b387  jz      loc_14001B781
0x14001b38d  lea     r8, ds:0[r13*2]; dwBytes
0x14001b395  lea     edx, [r14+8]; dwFlags
0x14001b399  call    cs:__imp_HeapAlloc
0x14001b39f  mov     r15, rax
0x14001b3a2  test    rax, rax
0x14001b3a5  jnz     short loc_14001B3B1
0x14001b3a7  mov     ebx, 8007000Eh
0x14001b3ac  jmp     loc_14001B786
0x14001b3b1  lea     rax, [rbp+47h+var_A0]
0x14001b3b5  mov     [rbp+47h+var_B0], r15
0x14001b3b9  lea     r9, [rbp+47h+var_98]
0x14001b3bd  mov     [rsp+0F0h+var_D0], rax; unsigned __int64 *
0x14001b3c2  lea     r8, [rbp+47h+var_A8]
0x14001b3c6  mov     r14, r15
0x14001b3c9  lea     rdx, [rbp+47h+var_A0+4]
0x14001b3cd  lea     rcx, [rbp+47h+var_A4]
0x14001b3d1  call    GetOSVersionFromFile
0x14001b3d6  xor     r10d, r10d
0x14001b3d9  mov     ebx, eax
0x14001b3db  test    eax, eax
0x14001b3dd  js      loc_14001B770
0x14001b3e3  mov     r9d, [rbp+47h+var_A8]
0x14001b3e7  test    r9d, r9d
0x14001b3ea  jz      short loc_14001B411
0x14001b3ec  lea     r8, aServicePackD; "Service Pack %d"
0x14001b3f3  lea     edx, [r10+10h]; unsigned __int64
0x14001b3f7  lea     rcx, [rbp+47h+var_70]; unsigned __int16 *
0x14001b3fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001b400  xor     r10d, r10d
0x14001b403  mov     ebx, eax
0x14001b405  test    eax, eax
0x14001b407  js      loc_14001B770
0x14001b40d  mov     r9d, [rbp+47h+var_A8]
0x14001b411  lea     r8, ds:0[r13*2]
0x14001b419  lea     rax, [rdi-2]
0x14001b41d  add     rax, r8
0x14001b420  mov     [rbp+47h+var_88], rax
0x14001b424  cmp     rdi, rax
0x14001b427  ja      loc_14001B727
0x14001b42d  mov     rax, r15
0x14001b430  mov     r11d, 64h ; 'd'
0x14001b436  movzx   esi, word ptr [rdi]
0x14001b439  mov     rcx, rax
0x14001b43c  test    si, si
0x14001b43f  jz      loc_14001B5EC
0x14001b445  lea     rdx, [r15-2]
0x14001b449  add     rdx, r8
0x14001b44c  cmp     rax, rdx
0x14001b44f  ja      loc_14001B5EC
0x14001b455  mov     eax, 25h ; '%'
0x14001b45a  cmp     ax, si
0x14001b45d  jnz     loc_14001B5C8
0x14001b463  mov     r8, rdi; unsigned __int16 *
0x14001b466  add     rdi, 2
0x14001b46a  movzx   esi, word ptr [rdi]
0x14001b46d  test    si, si
0x14001b470  jz      loc_14001B5C0
0x14001b476  cmp     esi, 38h ; '8'
0x14001b479  ja      loc_14001B507
0x14001b47f  jz      loc_14001B5B0
0x14001b485  cmp     esi, 31h ; '1'
0x14001b488  ja      short loc_14001B4D0
0x14001b48a  jz      loc_14001B5B0
0x14001b490  mov     ecx, esi
0x14001b492  sub     ecx, 20h ; ' '
0x14001b495  jz      loc_14001B5B0
0x14001b49b  sub     ecx, 3
0x14001b49e  jz      loc_14001B5B0
0x14001b4a4  sub     ecx, 7
0x14001b4a7  jz      loc_14001B5B0
0x14001b4ad  sub     ecx, 1
0x14001b4b0  jz      loc_14001B5B0
0x14001b4b6  sub     ecx, 2
0x14001b4b9  jz      loc_14001B5B0
0x14001b4bf  sub     ecx, 1
0x14001b4c2  jz      loc_14001B5B0
0x14001b4c8  cmp     ecx, 2
0x14001b4cb  jmp     loc_14001B5AE
0x14001b4d0  mov     ecx, esi
0x14001b4d2  sub     ecx, 32h ; '2'
0x14001b4d5  jz      loc_14001B5B0
0x14001b4db  sub     ecx, 1
0x14001b4de  jz      loc_14001B5B0
0x14001b4e4  sub     ecx, 1
0x14001b4e7  jz      loc_14001B5B0
0x14001b4ed  sub     ecx, 1
0x14001b4f0  jz      loc_14001B5B0
0x14001b4f6  sub     ecx, 1
0x14001b4f9  jz      loc_14001B5B0
0x14001b4ff  cmp     ecx, 1
0x14001b502  jmp     loc_14001B5AE
0x14001b507  cmp     esi, 62h ; 'b'
0x14001b50a  ja      short loc_14001B588
0x14001b50c  jz      loc_14001B6A4
0x14001b512  mov     ecx, esi
0x14001b514  sub     ecx, 39h ; '9'
0x14001b517  jz      loc_14001B5B0
0x14001b51d  sub     ecx, 10h
0x14001b520  jz      loc_14001B5B0
0x14001b526  sub     ecx, 2
0x14001b529  jz      loc_14001B686
0x14001b52f  sub     ecx, 1
0x14001b532  jz      short loc_14001B5B0
0x14001b534  sub     ecx, 1
0x14001b537  jz      loc_14001B666
0x14001b53d  sub     ecx, 3
0x14001b540  jz      loc_14001B61D
0x14001b546  add     rdi, 2
0x14001b54a  lea     r9, [rbp+47h+var_B0]; unsigned __int16 **
0x14001b54e  mov     rax, r14
0x14001b551  mov     rdx, r13
0x14001b554  sub     rax, r15
0x14001b557  mov     rcx, r14; unsigned __int16 *
0x14001b55a  sar     rax, 1
0x14001b55d  movzx   esi, word ptr [rdi]
0x14001b560  sub     rdx, rax; unsigned __int64
0x14001b563  mov     [rdi], r10w
0x14001b567  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x14001b56c  xor     r10d, r10d
0x14001b56f  mov     ebx, eax
0x14001b571  test    eax, eax
0x14001b573  js      loc_14001B770
0x14001b579  mov     r14, [rbp+47h+var_B0]
0x14001b57d  mov     r11d, 64h ; 'd'
0x14001b583  mov     [rdi], si
0x14001b586  jmp     short loc_14001B5C0
0x14001b588  mov     ecx, esi
0x14001b58a  sub     ecx, 68h ; 'h'
0x14001b58d  jz      short loc_14001B5B0
0x14001b58f  sub     ecx, 3
0x14001b592  jz      loc_14001B6DC
0x14001b598  sub     ecx, 1
0x14001b59b  jz      short loc_14001B5B0
0x14001b59d  sub     ecx, 1
0x14001b5a0  jz      loc_14001B6C0
0x14001b5a6  sub     ecx, 6
0x14001b5a9  jz      short loc_14001B546
0x14001b5ab  cmp     ecx, 4
0x14001b5ae  jnz     short loc_14001B546
0x14001b5b0  add     rdi, 2
0x14001b5b4  cmp     r14, rdx
0x14001b5b7  jbe     loc_14001B46A
0x14001b5bd  movzx   esi, word ptr [rdi]
0x14001b5c0  lea     r8, ds:0[r13*2]
0x14001b5c8  mov     r9d, [rbp+47h+var_A8]
0x14001b5cc  add     rdi, 2
0x14001b5d0  mov     [r14], si
0x14001b5d4  add     r14, 2
0x14001b5d8  mov     rax, r14
0x14001b5db  mov     [rbp+47h+var_B0], r14
0x14001b5df  cmp     rdi, [rbp+47h+var_88]
0x14001b5e3  jbe     loc_14001B436
0x14001b5e9  mov     rcx, rax
0x14001b5ec  mov     rsi, [rbp+47h+var_90]
0x14001b5f0  lea     rax, [r8+r15]
0x14001b5f4  cmp     rcx, rax
0x14001b5f7  jnb     loc_14001B76B
0x14001b5fd  mov     [r14], r10w
0x14001b601  cmp     rsi, 7FFFFFFFh
0x14001b608  jbe     loc_14001B72F
0x14001b60e  mov     ebx, 80070057h
0x14001b613  mov     [r12], r10w
0x14001b618  jmp     loc_14001B770
0x14001b61d  mov     rax, r14
0x14001b620  mov     word ptr [rdi], 73h ; 's'
0x14001b625  sub     rax, r15
0x14001b628  add     rdi, 2
0x14001b62c  sar     rax, 1
0x14001b62f  mov     rdx, r13
0x14001b632  sub     rdx, rax; unsigned __int64
0x14001b635  lea     rax, [rbp+47h+var_70]
0x14001b639  mov     [rsp+0F0h+var_C0], rax
0x14001b63e  movzx   esi, word ptr [rdi]
0x14001b641  xor     r9d, r9d; unsigned __int64 *
0x14001b644  mov     [rsp+0F0h+var_C8], r8; unsigned __int16 *
0x14001b649  mov     rcx, r14; Buffer
0x14001b64c  lea     r8, [rbp+47h+var_B0]; unsigned __int16 **
0x14001b650  mov     [rdi], r10w
0x14001b654  mov     dword ptr [rsp+0F0h+var_D0], 800h; unsigned int
0x14001b65c  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x14001b661  jmp     loc_14001B56C
0x14001b666  mov     rax, r14
0x14001b669  mov     [rdi], r11w
0x14001b66d  sub     rax, r15
0x14001b670  add     rdi, 2
0x14001b674  sar     rax, 1
0x14001b677  mov     rdx, r13
0x14001b67a  sub     rdx, rax
0x14001b67d  mov     eax, [rbp+47h+var_A4]
0x14001b680  mov     dword ptr [rsp+0F0h+var_C0], eax
0x14001b684  jmp     short loc_14001B63E
0x14001b686  mov     rax, r14
0x14001b689  mov     [rdi], r11w
0x14001b68d  sub     rax, r15
0x14001b690  mov     dword ptr [rsp+0F0h+var_C0], r9d
0x14001b695  sar     rax, 1
0x14001b698  add     rdi, 2
0x14001b69c  mov     rdx, r13
0x14001b69f  sub     rdx, rax
0x14001b6a2  jmp     short loc_14001B63E
0x14001b6a4  mov     rax, r14
0x14001b6a7  mov     [rdi], r11w
0x14001b6ab  sub     rax, r15
0x14001b6ae  add     rdi, 2
0x14001b6b2  sar     rax, 1
0x14001b6b5  mov     rdx, r13
0x14001b6b8  sub     rdx, rax
0x14001b6bb  mov     eax, dword ptr [rbp+47h+var_A0]
0x14001b6be  jmp     short loc_14001B680
0x14001b6c0  mov     rax, r14
0x14001b6c3  mov     [rdi], r11w
0x14001b6c7  sub     rax, r15
0x14001b6ca  add     rdi, 2
0x14001b6ce  sar     rax, 1
0x14001b6d1  mov     rdx, r13
0x14001b6d4  sub     rdx, rax
0x14001b6d7  mov     eax, dword ptr [rbp+47h+var_A0+4]
0x14001b6da  jmp     short loc_14001B680
0x14001b6dc  mov     [rdi], r11w
0x14001b6e0  mov     rax, r14
0x14001b6e3  sub     rax, r15
0x14001b6e6  add     rdi, 2
0x14001b6ea  sar     rax, 1
0x14001b6ed  mov     rdx, r13
0x14001b6f0  sub     rdx, rax; unsigned __int64
0x14001b6f3  xor     r9d, r9d; unsigned __int64 *
0x14001b6f6  mov     eax, [rbp+47h+var_98]
0x14001b6f9  mov     rcx, r14; Buffer
0x14001b6fc  movzx   esi, word ptr [rdi]
0x14001b6ff  mov     dword ptr [rsp+0F0h+var_C0], eax
0x14001b703  mov     [rsp+0F0h+var_C8], r8; unsigned __int16 *
0x14001b708  lea     r8, [rbp+47h+var_B0]; unsigned __int16 **
0x14001b70c  mov     [rdi], r10w
0x14001b710  mov     dword ptr [rsp+0F0h+var_D0], 800h; unsigned int
0x14001b718  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x14001b71d  xor     r10d, r10d
0x14001b720  test    ebx, ebx
0x14001b722  jmp     loc_14001B573
0x14001b727  mov     rcx, r15
0x14001b72a  jmp     loc_14001B5F0
0x14001b72f  mov     r9, [rbp+47h+Args]; Args
0x14001b733  lea     rdi, [rsi-1]
0x14001b737  mov     rdx, rdi; BufferCount
0x14001b73a  mov     r8, r15; Format
0x14001b73d  mov     rcx, r12; Buffer
0x14001b740  call    _vsnwprintf
0x14001b745  xor     r14d, r14d
0x14001b748  test    eax, eax
0x14001b74a  js      short loc_14001B75F
0x14001b74c  cdqe
0x14001b74e  cmp     rax, rdi
0x14001b751  ja      short loc_14001B75F
0x14001b753  mov     ebx, r14d
0x14001b756  jnz     short loc_14001B770
0x14001b758  mov     [r12+rdi*2], r14w
0x14001b75d  jmp     short loc_14001B770
0x14001b75f  mov     [r12+rdi*2], r14w
0x14001b764  mov     ebx, 8007007Ah
0x14001b769  jmp     short loc_14001B770
0x14001b76b  mov     ebx, 8000FFFFh
0x14001b770  mov     rcx, [rbp+47h+hHeap]; hHeap
0x14001b774  mov     r8, r15; lpMem
  ... truncated ...
```
