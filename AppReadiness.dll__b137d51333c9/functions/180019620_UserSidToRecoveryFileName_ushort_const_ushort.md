# UserSidToRecoveryFileName(ushort const *,ushort * *)

- ea: `0x180019620`
- end: `0x180019778`
- name: `?UserSidToRecoveryFileName@@YAJPEBGPEAPEAG@Z`
- size: `344`
- prototype: `__int64 __fastcall(PCWSTR pszMore, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x18001abb0`

## callees

- `0x180019620`
- `0x18003e210`
- `0x180074158`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800196ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800196ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019750`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019750`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001966d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001966d`

## pseudocode

```c
int __fastcall UserSidToRecoveryFileName(PCWSTR pszMore, unsigned __int16 **a2)
{
  int result; // eax
  __int64 v5; // rcx
  WCHAR *i; // rax
  __int64 v7; // rbx
  unsigned __int16 *v8; // r10
  unsigned __int64 v9; // rdx
  __int64 v10; // rax
  WCHAR *v11; // r8
  unsigned __int16 *v12; // r9
  unsigned __int16 *v13; // rcx
  int v14; // ebx
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  *a2 = 0;
  result = GetAppReadinessDirectory(pszPath, (__int64)a2);
  if ( result >= 0 )
  {
    result = PathCchAppend(pszPath, 0x104u, pszMore);
    if ( result >= 0 )
    {
      v5 = 260;
      for ( i = pszPath; *i; ++i )
      {
        if ( !--v5 )
          return -2147024809;
      }
      v7 = 260 - v5;
      v8 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (260 - v5) + 2);
      if ( !v8 )
        return -2147024882;
      v9 = v7 + 1;
      if ( v7 == -1 )
      {
        v14 = -2147024809;
        if ( !v9 )
          goto LABEL_17;
      }
      else
      {
        if ( v9 <= 0x7FFFFFFF )
        {
          v10 = 2147483646;
          v11 = pszPath;
          v12 = v8;
          do
          {
            if ( !v10 )
              break;
            if ( !*v11 )
              break;
            *v12++ = *v11++;
            --v10;
            --v9;
          }
          while ( v9 );
          v13 = v12 - 1;
          v14 = -2147024774;
          if ( v9 )
          {
            v13 = v12;
            v14 = 0;
          }
          *v13 = 0;
LABEL_17:
          if ( v14 >= 0 )
          {
            *a2 = v8;
            return v14;
          }
LABEL_21:
          LocalFree(v8);
          return v14;
        }
        v14 = -2147024809;
      }
      *v8 = 0;
      goto LABEL_21;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019620  mov     [rsp+arg_10], rbx
0x180019625  push    rdi
0x180019626  sub     rsp, 240h
0x18001962d  mov     rax, cs:__security_cookie
0x180019634  xor     rax, rsp
0x180019637  mov     [rsp+248h+var_18], rax
0x18001963f  mov     rbx, rcx
0x180019642  mov     qword ptr [rdx], 0
0x180019649  lea     rcx, [rsp+248h+pszPath]; lpPathName
0x18001964e  mov     rdi, rdx
0x180019651  call    ?GetAppReadinessDirectory@@YAJPEAG_K@Z; GetAppReadinessDirectory(ushort *,unsigned __int64)
0x180019656  test    eax, eax
0x180019658  js      loc_18001972C
0x18001965e  mov     r8, rbx; pszMore
0x180019661  lea     rcx, [rsp+248h+pszPath]; pszPath
0x180019666  mov     ebx, 104h
0x18001966b  mov     edx, ebx; cchPath
0x18001966d  call    cs:__imp_PathCchAppend
0x180019673  test    eax, eax
0x180019675  js      loc_18001972C
0x18001967b  mov     ecx, ebx
0x18001967d  lea     rax, [rsp+248h+pszPath]
0x180019682  cmp     word ptr [rax], 0
0x180019686  jz      short loc_18001969C
0x180019688  add     rax, 2
0x18001968c  sub     rcx, 1
0x180019690  jnz     short loc_180019682
0x180019692  mov     eax, 80070057h
0x180019697  jmp     loc_18001972C
0x18001969c  sub     rbx, rcx
0x18001969f  mov     ecx, 40h ; '@'; uFlags
0x1800196a4  lea     rdx, ds:2[rbx*2]; uBytes
0x1800196ac  call    cs:__imp_LocalAlloc
0x1800196b2  mov     r10, rax
0x1800196b5  test    rax, rax
0x1800196b8  jz      loc_180019758
0x1800196be  lea     rdx, [rbx+1]
0x1800196c2  test    rdx, rdx
0x1800196c5  jz      loc_180019766
0x1800196cb  cmp     rdx, 7FFFFFFFh
0x1800196d2  ja      loc_18001975F
0x1800196d8  mov     eax, 7FFFFFFEh
0x1800196dd  lea     r8, [rsp+248h+pszPath]
0x1800196e2  mov     r9, r10
0x1800196e5  test    rax, rax
0x1800196e8  jz      short loc_180019708
0x1800196ea  movzx   ecx, word ptr [r8]
0x1800196ee  test    cx, cx
0x1800196f1  jz      short loc_180019708
0x1800196f3  mov     [r9], cx
0x1800196f7  add     r8, 2
0x1800196fb  add     r9, 2
0x1800196ff  dec     rax
0x180019702  sub     rdx, 1
0x180019706  jnz     short loc_1800196E5
0x180019708  test    rdx, rdx
0x18001970b  lea     rcx, [r9-2]
0x18001970f  mov     ebx, 8007007Ah
0x180019714  cmovnz  rcx, r9
0x180019718  xor     eax, eax
0x18001971a  test    rdx, rdx
0x18001971d  cmovnz  ebx, eax
0x180019720  mov     [rcx], ax
0x180019723  test    ebx, ebx
0x180019725  js      short loc_18001974D
0x180019727  mov     [rdi], r10
0x18001972a  mov     eax, ebx
0x18001972c  mov     rcx, [rsp+248h+var_18]
0x180019734  xor     rcx, rsp; StackCookie
0x180019737  call    __security_check_cookie
0x18001973c  mov     rbx, [rsp+248h+arg_10]
0x180019744  add     rsp, 240h
0x18001974b  pop     rdi
0x18001974c  retn
0x18001974d  mov     rcx, r10; hMem
0x180019750  call    cs:__imp_LocalFree
0x180019756  jmp     short loc_18001972A
0x180019758  mov     eax, 8007000Eh
0x18001975d  jmp     short loc_18001972C
0x18001975f  mov     ebx, 80070057h
0x180019764  jmp     short loc_180019770
0x180019766  mov     ebx, 80070057h
0x18001976b  test    rdx, rdx
0x18001976e  jz      short loc_180019723
0x180019770  xor     eax, eax
0x180019772  mov     [r10], ax
0x180019776  jmp     short loc_18001974D
```
