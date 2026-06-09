# FvepConvertVolumeNameToCacheValueName

- ea: `0x180050ea4`
- end: `0x18005126d`
- name: `FvepConvertVolumeNameToCacheValueName`
- size: `969`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH psz)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18005156c`
- `0x18005186c`

## callees

- `0x18004ca58`
- `0x180050a28`
- `0x180050ea4`
- `0x1800519c8`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005104c`
- `KERNEL32!GetLastError` at `0x1800510a7`
- `KERNEL32!GetLastError` at `0x18005104c`
- `KERNEL32!GetLastError` at `0x1800510a7`
- `KERNEL32!HeapFree` at `0x1800510e8`
- `KERNEL32!HeapFree` at `0x180051200`
- `KERNEL32!HeapFree` at `0x180051219`
- `KERNEL32!HeapFree` at `0x180051237`
- `KERNEL32!HeapFree` at `0x1800510e8`
- `KERNEL32!HeapFree` at `0x180051200`
- `KERNEL32!HeapFree` at `0x180051219`
- `KERNEL32!HeapFree` at `0x180051237`
- `KERNEL32!HeapAlloc` at `0x180050f80`
- `KERNEL32!HeapAlloc` at `0x18005110f`
- `KERNEL32!HeapAlloc` at `0x18005116c`
- `KERNEL32!HeapAlloc` at `0x180050f80`
- `KERNEL32!HeapAlloc` at `0x18005110f`
- `KERNEL32!HeapAlloc` at `0x18005116c`
- `KERNEL32!GetProcessHeap` at `0x180050f6f`
- `KERNEL32!GetProcessHeap` at `0x1800510da`
- `KERNEL32!GetProcessHeap` at `0x180051101`
- `KERNEL32!GetProcessHeap` at `0x18005115b`
- `KERNEL32!GetProcessHeap` at `0x1800511f2`
- `KERNEL32!GetProcessHeap` at `0x18005120b`
- `KERNEL32!GetProcessHeap` at `0x180051229`
- `KERNEL32!GetProcessHeap` at `0x180050f6f`
- `KERNEL32!GetProcessHeap` at `0x1800510da`
- `KERNEL32!GetProcessHeap` at `0x180051101`
- `KERNEL32!GetProcessHeap` at `0x18005115b`
- `KERNEL32!GetProcessHeap` at `0x1800511f2`
- `KERNEL32!GetProcessHeap` at `0x18005120b`
- `KERNEL32!GetProcessHeap` at `0x180051229`
- `KERNEL32!CreateFileW` at `0x18005103b`
- `KERNEL32!CreateFileW` at `0x18005103b`
- `KERNEL32!CloseHandle` at `0x1800511db`
- `KERNEL32!CloseHandle` at `0x1800511db`
- `KERNEL32!DeviceIoControl` at `0x180051099`
- `KERNEL32!DeviceIoControl` at `0x180051099`

## pseudocode

```c
__int64 __fastcall FvepConvertVolumeNameToCacheValueName(STRSAFE_PCNZWCH psz, wchar_t **a2)
{
  wchar_t *v4; // r12
  signed int v5; // ebx
  size_t v6; // r15
  SIZE_T v7; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v9; // rax
  WCHAR *v10; // r13
  unsigned __int64 v11; // rdi
  unsigned __int16 *v12; // r14
  __int64 v13; // rax
  WCHAR *v14; // rdx
  WCHAR *v15; // rcx
  SIZE_T v16; // rsi
  void *FileW; // rax
  signed int LastError; // eax
  DWORD v19; // edi
  signed int v20; // eax
  HANDLE v21; // rax
  HANDLE v22; // rax
  SIZE_T v23; // r15
  HANDLE v24; // rax
  unsigned __int64 v25; // rdi
  HANDLE v26; // rax
  HANDLE v27; // rax
  HANDLE v28; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  ULONGLONG pullResult; // [rsp+48h] [rbp-B8h] BYREF
  size_t pcchLength; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t **v33; // [rsp+58h] [rbp-A8h]
  _BYTE OutBuffer[272]; // [rsp+60h] [rbp-A0h] BYREF

  v33 = a2;
  memset_0(OutBuffer, 0, 0x104u);
  v4 = 0;
  BytesReturned = 0;
  pcchLength = 0;
  pullResult = 0;
  if ( psz )
  {
    if ( a2 )
    {
      v5 = StringCchLengthW(psz, 0x7FFFFFFFu, &pcchLength);
      if ( v5 >= 0 )
      {
        v6 = pcchLength;
        v5 = ULongLongMult(pcchLength, 2u, &pullResult);
        if ( v5 >= 0 )
        {
          v7 = pullResult + 2;
          if ( pullResult + 2 < pullResult )
          {
            return (unsigned int)-2147024362;
          }
          else
          {
            pullResult += 2LL;
            ProcessHeap = GetProcessHeap();
            v9 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v7);
            v10 = v9;
            if ( v9 )
            {
              v11 = v7 >> 1;
              v12 = (unsigned __int16 *)OutBuffer;
              if ( v11 )
              {
                if ( v11 <= 0x7FFFFFFF )
                {
                  v13 = 2147483646;
                  v14 = v10;
                  do
                  {
                    if ( !v13 )
                      break;
                    if ( !*psz )
                      break;
                    *v14++ = *psz++;
                    --v13;
                    --v11;
                  }
                  while ( v11 );
                  v15 = v14 - 1;
                  v16 = 0;
                  v5 = v11 == 0 ? 0x8007007A : 0;
                  if ( v11 )
                    v15 = v14;
                  *v15 = 0;
                  if ( v11 )
                  {
                    if ( v6 && v10[v6 - 1] == 92 )
                      v10[v6 - 1] = 0;
                    FileW = CreateFileW(v10, 0, 7u, 0, 3u, 0, 0);
                    pcchLength = (size_t)FileW;
                    if ( FileW == (void *)-1LL )
                    {
                      LastError = GetLastError();
                      v5 = LastError;
                      if ( LastError > 0 )
                        v5 = (unsigned __int16)LastError | 0x80070000;
                    }
                    else
                    {
                      v19 = 260;
                      while ( 1 )
                      {
                        BytesReturned = 0;
                        if ( DeviceIoControl(FileW, 0x4D0000u, 0, 0, v12, v19, &BytesReturned, 0) )
                          break;
                        v20 = GetLastError();
                        v5 = v20;
                        if ( v20 > 0 )
                          v5 = (unsigned __int16)v20 | 0x80070000;
                        if ( v5 != -2147024774 && v5 != -2147024662 )
                          goto LABEL_47;
                        if ( v12 != (unsigned __int16 *)OutBuffer )
                        {
                          v21 = GetProcessHeap();
                          HeapFree(v21, 0, v12);
                          v12 = 0;
                        }
                        if ( v19 + 260 < v19 )
                          goto LABEL_46;
                        v19 += 260;
                        v22 = GetProcessHeap();
                        v12 = (unsigned __int16 *)HeapAlloc(v22, 0, v19);
                        FileW = (void *)pcchLength;
                        if ( !v12 )
                          goto LABEL_36;
                      }
                      v5 = ULongLongMult(*v12, 4u, &pullResult);
                      if ( v5 < 0 )
                        goto LABEL_47;
                      v23 = pullResult + 2;
                      if ( pullResult + 2 < pullResult )
                      {
LABEL_46:
                        v5 = -2147024362;
                        goto LABEL_47;
                      }
                      v24 = GetProcessHeap();
                      v4 = (wchar_t *)HeapAlloc(v24, 8u, v23);
                      if ( !v4 )
                      {
LABEL_36:
                        v5 = -2147024882;
                        goto LABEL_47;
                      }
                      v25 = 0;
                      v5 = 0;
                      while ( v25 < *v12 && v16 < v23 >> 1 )
                      {
                        v5 = StringCbPrintfW(&v4[v16], v23 - 2 * v16, L"%02X", *((unsigned __int8 *)v12 + v25 + 2));
                        if ( v5 < 0 )
                          goto LABEL_47;
                        ++v25;
                        v16 += 2LL;
                      }
                      *v33 = v4;
                      v4 = 0;
LABEL_47:
                      CloseHandle((HANDLE)pcchLength);
                    }
                  }
                }
                else
                {
                  v5 = -2147024809;
                  *v9 = 0;
                }
              }
              else
              {
                v5 = -2147024809;
              }
              v26 = GetProcessHeap();
              HeapFree(v26, 0, v10);
              if ( v4 )
              {
                v27 = GetProcessHeap();
                HeapFree(v27, 0, v4);
              }
              if ( v12 != (unsigned __int16 *)OutBuffer )
              {
                v28 = GetProcessHeap();
                HeapFree(v28, 0, v12);
              }
            }
            else
            {
              return (unsigned int)-2147024882;
            }
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180050ea4  mov     [rsp-8+arg_10], rbx
0x180050ea9  push    rbp
0x180050eaa  push    rsi
0x180050eab  push    rdi
0x180050eac  push    r12
0x180050eae  push    r13
0x180050eb0  push    r14
0x180050eb2  push    r15
0x180050eb4  lea     rbp, [rsp-80h]
0x180050eb9  sub     rsp, 180h
0x180050ec0  mov     rax, cs:__security_cookie
0x180050ec7  xor     rax, rsp
0x180050eca  mov     [rbp+0B0h+var_40], rax
0x180050ece  mov     rbx, rdx
0x180050ed1  mov     [rsp+1B0h+var_158], rdx
0x180050ed6  mov     rsi, rcx
0x180050ed9  xor     edx, edx; Val
0x180050edb  lea     rcx, [rsp+1B0h+OutBuffer]; void *
0x180050ee0  mov     r8d, 104h; Size
0x180050ee6  call    memset_0
0x180050eeb  xor     r12d, r12d
0x180050eee  mov     [rsp+1B0h+BytesReturned], r12d
0x180050ef3  mov     [rsp+1B0h+pcchLength], r12
0x180050ef8  mov     [rsp+1B0h+pullResult], r12
0x180050efd  test    rsi, rsi
0x180050f00  jnz     short loc_180050F0C
0x180050f02  mov     ebx, 80070057h
0x180050f07  jmp     loc_180051244
0x180050f0c  test    rbx, rbx
0x180050f0f  jnz     short loc_180050F1B
0x180050f11  mov     ebx, 80004003h
0x180050f16  jmp     loc_180051244
0x180050f1b  lea     r8, [rsp+1B0h+pcchLength]; pcchLength
0x180050f20  mov     edx, 7FFFFFFFh; cchMax
0x180050f25  mov     rcx, rsi; psz
0x180050f28  call    StringCchLengthW
0x180050f2d  mov     ebx, eax
0x180050f2f  test    eax, eax
0x180050f31  js      loc_180051244
0x180050f37  mov     r15, [rsp+1B0h+pcchLength]
0x180050f3c  lea     r8, [rsp+1B0h+pullResult]; pullResult
0x180050f41  mov     rcx, r15; ullMultiplicand
0x180050f44  mov     edx, 2; ullMultiplier
0x180050f49  call    ULongLongMult
0x180050f4e  mov     ebx, eax
0x180050f50  test    eax, eax
0x180050f52  js      loc_180051244
0x180050f58  mov     rax, [rsp+1B0h+pullResult]
0x180050f5d  lea     rdi, [rax+2]
0x180050f61  cmp     rdi, rax
0x180050f64  jb      loc_18005123F
0x180050f6a  mov     [rsp+1B0h+pullResult], rdi
0x180050f6f  call    cs:__imp_GetProcessHeap
0x180050f75  mov     r8, rdi; dwBytes
0x180050f78  mov     edx, 8; dwFlags
0x180050f7d  mov     rcx, rax; hHeap
0x180050f80  call    cs:__imp_HeapAlloc
0x180050f86  mov     r13, rax
0x180050f89  test    rax, rax
0x180050f8c  jnz     short loc_180050F98
0x180050f8e  mov     ebx, 8007000Eh
0x180050f93  jmp     loc_180051244
0x180050f98  shr     rdi, 1
0x180050f9b  lea     r14, [rsp+1B0h+OutBuffer]
0x180050fa0  jz      loc_1800511E3
0x180050fa6  cmp     rdi, 7FFFFFFFh
0x180050fad  jbe     short loc_180050FBB
0x180050faf  mov     ebx, 80070057h
0x180050fb4  xor     esi, esi
0x180050fb6  jmp     loc_1800511EF
0x180050fbb  mov     eax, 7FFFFFFEh
0x180050fc0  mov     rdx, r13
0x180050fc3  test    rax, rax
0x180050fc6  jz      short loc_180050FE4
0x180050fc8  movzx   ecx, word ptr [rsi]
0x180050fcb  test    cx, cx
0x180050fce  jz      short loc_180050FE4
0x180050fd0  mov     [rdx], cx
0x180050fd3  add     rsi, 2
0x180050fd7  add     rdx, 2
0x180050fdb  dec     rax
0x180050fde  sub     rdi, 1
0x180050fe2  jnz     short loc_180050FC3
0x180050fe4  mov     rax, rdi
0x180050fe7  lea     rcx, [rdx-2]
0x180050feb  neg     rax
0x180050fee  sbb     ebx, ebx
0x180050ff0  xor     esi, esi
0x180050ff2  not     ebx
0x180050ff4  and     ebx, 8007007Ah
0x180050ffa  test    rdi, rdi
0x180050ffd  cmovnz  rcx, rdx
0x180051001  mov     [rcx], si
0x180051004  jz      loc_1800511F2
0x18005100a  test    r15, r15
0x18005100d  jz      short loc_18005101E
0x18005100f  cmp     word ptr [r13+r15*2-2], 5Ch ; '\'
0x180051016  jnz     short loc_18005101E
0x180051018  mov     [r13+r15*2-2], si
0x18005101e  xor     r9d, r9d; lpSecurityAttributes
0x180051021  mov     [rsp+1B0h+hTemplateFile], rsi; hTemplateFile
0x180051026  mov     [rsp+1B0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18005102a  xor     edx, edx; dwDesiredAccess
0x18005102c  mov     rcx, r13; lpFileName
0x18005102f  mov     [rsp+1B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180051037  lea     r8d, [r9+7]; dwShareMode
0x18005103b  call    cs:__imp_CreateFileW
0x180051041  mov     [rsp+1B0h+pcchLength], rax
0x180051046  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005104a  jnz     short loc_18005106A
0x18005104c  call    cs:__imp_GetLastError
0x180051052  mov     ebx, eax
0x180051054  test    eax, eax
0x180051056  jle     loc_1800511F2
0x18005105c  movzx   ebx, ax
0x18005105f  or      ebx, 80070000h
0x180051065  jmp     loc_1800511F2
0x18005106a  mov     edi, 104h
0x18005106f  mov     [rsp+1B0h+lpOverlapped], rsi; lpOverlapped
0x180051074  lea     rcx, [rsp+1B0h+BytesReturned]
0x180051079  mov     [rsp+1B0h+hTemplateFile], rcx; lpBytesReturned
0x18005107e  xor     r9d, r9d; nInBufferSize
0x180051081  mov     [rsp+1B0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x180051085  mov     rcx, rax; hDevice
0x180051088  xor     r8d, r8d; lpInBuffer
0x18005108b  mov     qword ptr [rsp+1B0h+dwCreationDisposition], r14; lpOutBuffer
0x180051090  mov     edx, 4D0000h; dwIoControlCode
0x180051095  mov     [rsp+1B0h+BytesReturned], esi
0x180051099  call    cs:__imp_DeviceIoControl
0x18005109f  test    eax, eax
0x1800510a1  jnz     loc_180051130
0x1800510a7  call    cs:__imp_GetLastError
0x1800510ad  mov     ebx, eax
0x1800510af  test    eax, eax
0x1800510b1  jle     short loc_1800510BC
0x1800510b3  movzx   ebx, ax
0x1800510b6  or      ebx, 80070000h
0x1800510bc  cmp     ebx, 8007007Ah
0x1800510c2  jz      short loc_1800510D0
0x1800510c4  cmp     ebx, 800700EAh
0x1800510ca  jnz     loc_1800511D6
0x1800510d0  lea     rax, [rsp+1B0h+OutBuffer]
0x1800510d5  cmp     r14, rax
0x1800510d8  jz      short loc_1800510F1
0x1800510da  call    cs:__imp_GetProcessHeap
0x1800510e0  mov     r8, r14; lpMem
0x1800510e3  xor     edx, edx; dwFlags
0x1800510e5  mov     rcx, rax; hHeap
0x1800510e8  call    cs:__imp_HeapFree
0x1800510ee  mov     r14, rsi
0x1800510f1  lea     eax, [rdi+104h]
0x1800510f7  cmp     eax, edi
0x1800510f9  jb      loc_1800511D1
0x1800510ff  mov     edi, eax
0x180051101  call    cs:__imp_GetProcessHeap
0x180051107  mov     r8d, edi; dwBytes
0x18005110a  xor     edx, edx; dwFlags
0x18005110c  mov     rcx, rax; hHeap
0x18005110f  call    cs:__imp_HeapAlloc
0x180051115  mov     r14, rax
0x180051118  test    rax, rax
0x18005111b  mov     rax, [rsp+1B0h+pcchLength]
0x180051120  jnz     loc_18005106F
0x180051126  mov     ebx, 8007000Eh
0x18005112b  jmp     loc_1800511D6
0x180051130  movzx   ecx, word ptr [r14]; ullMultiplicand
0x180051134  lea     r8, [rsp+1B0h+pullResult]; pullResult
0x180051139  mov     edx, 4; ullMultiplier
0x18005113e  call    ULongLongMult
0x180051143  mov     ebx, eax
0x180051145  test    eax, eax
0x180051147  js      loc_1800511D6
0x18005114d  mov     rax, [rsp+1B0h+pullResult]
0x180051152  lea     r15, [rax+2]
0x180051156  cmp     r15, rax
0x180051159  jb      short loc_1800511D1
0x18005115b  call    cs:__imp_GetProcessHeap
0x180051161  mov     r8, r15; dwBytes
0x180051164  mov     edx, 8; dwFlags
0x180051169  mov     rcx, rax; hHeap
0x18005116c  call    cs:__imp_HeapAlloc
0x180051172  mov     r12, rax
0x180051175  test    rax, rax
0x180051178  jz      short loc_180051126
0x18005117a  mov     rdi, rsi
0x18005117d  xor     ebx, ebx
0x18005117f  movzx   eax, word ptr [r14]
0x180051183  cmp     rdi, rax
0x180051186  jnb     short loc_1800511C2
0x180051188  mov     rax, r15
0x18005118b  shr     rax, 1
0x18005118e  cmp     rsi, rax
0x180051191  jnb     short loc_1800511C2
0x180051193  movzx   r9d, byte ptr [r14+rdi+2]
0x180051199  lea     rax, [rsi+rsi]
0x18005119d  mov     rdx, r15
0x1800511a0  lea     rcx, [rax+r12]; pszDest
0x1800511a4  sub     rdx, rax; cbDest
0x1800511a7  lea     r8, a02x; "%02X"
0x1800511ae  call    StringCbPrintfW
0x1800511b3  mov     ebx, eax
0x1800511b5  test    eax, eax
0x1800511b7  js      short loc_1800511D6
0x1800511b9  inc     rdi
0x1800511bc  add     rsi, 2
0x1800511c0  jmp     short loc_18005117F
0x1800511c2  mov     rax, [rsp+1B0h+var_158]
0x1800511c7  xor     esi, esi
0x1800511c9  mov     [rax], r12
0x1800511cc  mov     r12d, esi
0x1800511cf  jmp     short loc_1800511D6
0x1800511d1  mov     ebx, 80070216h
0x1800511d6  mov     rcx, [rsp+1B0h+pcchLength]; hObject
0x1800511db  call    cs:__imp_CloseHandle
0x1800511e1  jmp     short loc_1800511F2
0x1800511e3  xor     esi, esi
0x1800511e5  mov     ebx, 80070057h
0x1800511ea  test    rdi, rdi
0x1800511ed  jz      short loc_1800511F2
0x1800511ef  mov     [rax], si
0x1800511f2  call    cs:__imp_GetProcessHeap
0x1800511f8  mov     r8, r13; lpMem
0x1800511fb  xor     edx, edx; dwFlags
0x1800511fd  mov     rcx, rax; hHeap
0x180051200  call    cs:__imp_HeapFree
0x180051206  test    r12, r12
0x180051209  jz      short loc_18005121F
0x18005120b  call    cs:__imp_GetProcessHeap
0x180051211  mov     r8, r12; lpMem
0x180051214  xor     edx, edx; dwFlags
0x180051216  mov     rcx, rax; hHeap
0x180051219  call    cs:__imp_HeapFree
0x18005121f  lea     rax, [rsp+1B0h+OutBuffer]
0x180051224  cmp     r14, rax
0x180051227  jz      short loc_180051244
0x180051229  call    cs:__imp_GetProcessHeap
0x18005122f  mov     r8, r14; lpMem
0x180051232  xor     edx, edx; dwFlags
0x180051234  mov     rcx, rax; hHeap
0x180051237  call    cs:__imp_HeapFree
0x18005123d  jmp     short loc_180051244
0x18005123f  mov     ebx, 80070216h
0x180051244  mov     eax, ebx
0x180051246  mov     rcx, [rbp+0B0h+var_40]
0x18005124a  xor     rcx, rsp; StackCookie
0x18005124d  call    __security_check_cookie
0x180051252  mov     rbx, [rsp+1B0h+arg_10]
0x18005125a  add     rsp, 180h
0x180051261  pop     r15
0x180051263  pop     r14
0x180051265  pop     r13
0x180051267  pop     r12
0x180051269  pop     rdi
0x18005126a  pop     rsi
0x18005126b  pop     rbp
0x18005126c  retn
```
