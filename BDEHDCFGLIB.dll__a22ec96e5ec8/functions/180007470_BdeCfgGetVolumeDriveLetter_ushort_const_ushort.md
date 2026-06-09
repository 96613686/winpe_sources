# BdeCfgGetVolumeDriveLetter(ushort const *,ushort *)

- ea: `0x180007470`
- end: `0x18000761c`
- name: `?BdeCfgGetVolumeDriveLetter@@YAJPEBGPEAG@Z`
- size: `428`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x18000202c`
- `0x180002460`
- `0x180002814`
- `0x180006860`
- `0x180006cbc`

## callees

- `0x180007470`
- `0x180008e1c`
- `0x180009880`
- `0x1800135c0`

## import_xrefs

- `msvcrt!iswalpha` at `0x1800075a3`
- `msvcrt!iswalpha` at `0x1800075a3`
- `KERNEL32!HeapAlloc` at `0x180007550`
- `KERNEL32!HeapAlloc` at `0x180007550`
- `KERNEL32!GetProcessHeap` at `0x18000753f`
- `KERNEL32!GetProcessHeap` at `0x18000753f`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800074ed`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800074ed`
- `KERNEL32!GetLastError` at `0x1800074f7`
- `KERNEL32!GetLastError` at `0x1800074f7`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180007524`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180007577`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180007524`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180007577`

## pseudocode

```c
__int64 __fastcall BdeCfgGetVolumeDriveLetter(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  WCHAR *v3; // rsi
  signed int v4; // edi
  signed int LastError; // eax
  SIZE_T v6; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v8; // rax
  wint_t *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  DWORD cchReturnLength[4]; // [rsp+20h] [rbp-458h] BYREF
  WCHAR szVolumeName[264]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR szVolumeMountPoint[264]; // [rsp+240h] [rbp-238h] BYREF

  cchReturnLength[0] = 0;
  if ( a1 && a2 )
  {
    v3 = 0;
    v4 = StringCbPrintfW(szVolumeMountPoint, 0x208u, L"%s\\", a1);
    if ( v4 >= 0 )
    {
      if ( !GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, szVolumeName, 0x104u) )
      {
LABEL_5:
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_23;
      }
      if ( GetVolumePathNamesForVolumeNameW(szVolumeName, 0, 0, cchReturnLength) )
      {
        v4 = -1063256037;
      }
      else
      {
        v6 = 2LL * cchReturnLength[0];
        ProcessHeap = GetProcessHeap();
        v8 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v6);
        v3 = v8;
        if ( v8 )
        {
          if ( GetVolumePathNamesForVolumeNameW(szVolumeName, v8, cchReturnLength[0], cchReturnLength) )
          {
            v9 = v3;
            if ( *v3 )
            {
              while ( 1 )
              {
                v10 = -1;
                do
                  ++v10;
                while ( v9[v10] );
                if ( v10 == 3 && iswalpha(*v9) && v9[1] == 58 && v9[2] == 92 )
                  break;
                v11 = -1;
                do
                  ++v11;
                while ( v9[v11] );
                v9 += v11 + 1;
                if ( !*v9 )
                  goto LABEL_22;
              }
              *a2 = *v9;
            }
            else
            {
LABEL_22:
              v4 = 1;
            }
            goto LABEL_23;
          }
          goto LABEL_5;
        }
        v4 = -2147024882;
      }
    }
LABEL_23:
    BdeCfgpFree(v3);
    return (unsigned int)v4;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180007470  mov     [rsp+arg_10], rbx
0x180007475  mov     [rsp+arg_18], rbp
0x18000747a  push    rsi
0x18000747b  push    rdi
0x18000747c  push    r14
0x18000747e  sub     rsp, 460h
0x180007485  mov     rax, cs:__security_cookie
0x18000748c  xor     rax, rsp
0x18000748f  mov     [rsp+478h+var_28], rax
0x180007497  xor     ebp, ebp
0x180007499  mov     r14, rdx
0x18000749c  mov     [rsp+478h+cchReturnLength], ebp
0x1800074a0  test    rcx, rcx
0x1800074a3  jz      loc_1800075EF
0x1800074a9  test    rdx, rdx
0x1800074ac  jz      loc_1800075EF
0x1800074b2  mov     r9, rcx
0x1800074b5  lea     r8, aS; "%s\\"
0x1800074bc  lea     rcx, [rsp+478h+szVolumeMountPoint]; unsigned __int16 *
0x1800074c4  mov     edx, 208h; unsigned __int64
0x1800074c9  mov     esi, ebp
0x1800074cb  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800074d0  mov     edi, eax
0x1800074d2  test    eax, eax
0x1800074d4  js      loc_1800075DA
0x1800074da  mov     r8d, 104h; cchBufferLength
0x1800074e0  lea     rdx, [rsp+478h+szVolumeName]; lpszVolumeName
0x1800074e5  lea     rcx, [rsp+478h+szVolumeMountPoint]; lpszVolumeMountPoint
0x1800074ed  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800074f3  test    eax, eax
0x1800074f5  jnz     short loc_180007515
0x1800074f7  call    cs:__imp_GetLastError
0x1800074fd  mov     edi, eax
0x1800074ff  test    eax, eax
0x180007501  jle     loc_1800075DA
0x180007507  movzx   edi, ax
0x18000750a  or      edi, 80070000h
0x180007510  jmp     loc_1800075DA
0x180007515  lea     r9, [rsp+478h+cchReturnLength]; lpcchReturnLength
0x18000751a  xor     r8d, r8d; cchBufferLength
0x18000751d  xor     edx, edx; lpszVolumePathNames
0x18000751f  lea     rcx, [rsp+478h+szVolumeName]; lpszVolumeName
0x180007524  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18000752a  test    eax, eax
0x18000752c  jz      short loc_180007538
0x18000752e  mov     edi, 0C0A0001Bh
0x180007533  jmp     loc_1800075DA
0x180007538  mov     ebx, [rsp+478h+cchReturnLength]
0x18000753c  add     rbx, rbx
0x18000753f  call    cs:__imp_GetProcessHeap
0x180007545  mov     r8, rbx; dwBytes
0x180007548  mov     edx, 8; dwFlags
0x18000754d  mov     rcx, rax; hHeap
0x180007550  call    cs:__imp_HeapAlloc
0x180007556  mov     rsi, rax
0x180007559  test    rax, rax
0x18000755c  jnz     short loc_180007565
0x18000755e  mov     edi, 8007000Eh
0x180007563  jmp     short loc_1800075DA
0x180007565  mov     r8d, [rsp+478h+cchReturnLength]; cchBufferLength
0x18000756a  lea     r9, [rsp+478h+cchReturnLength]; lpcchReturnLength
0x18000756f  mov     rdx, rsi; lpszVolumePathNames
0x180007572  lea     rcx, [rsp+478h+szVolumeName]; lpszVolumeName
0x180007577  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18000757d  test    eax, eax
0x18000757f  jz      loc_1800074F7
0x180007585  mov     rbx, rsi
0x180007588  cmp     [rsi], bp
0x18000758b  jz      short loc_1800075D5
0x18000758d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007591  inc     rax
0x180007594  cmp     [rbx+rax*2], bp
0x180007598  jnz     short loc_180007591
0x18000759a  cmp     rax, 3
0x18000759e  jnz     short loc_1800075BB
0x1800075a0  movzx   ecx, word ptr [rbx]; C
0x1800075a3  call    cs:__imp_iswalpha
0x1800075a9  test    eax, eax
0x1800075ab  jz      short loc_1800075BB
0x1800075ad  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1800075b2  jnz     short loc_1800075BB
0x1800075b4  cmp     word ptr [rbx+4], 5Ch ; '\'
0x1800075b9  jz      short loc_1800075E6
0x1800075bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800075bf  inc     rax
0x1800075c2  cmp     [rbx+rax*2], bp
0x1800075c6  jnz     short loc_1800075BF
0x1800075c8  lea     rbx, [rbx+rax*2]
0x1800075cc  add     rbx, 2
0x1800075d0  cmp     [rbx], bp
0x1800075d3  jnz     short loc_18000758D
0x1800075d5  mov     edi, 1
0x1800075da  mov     rcx, rsi; lpMem
0x1800075dd  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x1800075e2  mov     eax, edi
0x1800075e4  jmp     short loc_1800075F4
0x1800075e6  movzx   eax, word ptr [rbx]
0x1800075e9  mov     [r14], ax
0x1800075ed  jmp     short loc_1800075DA
0x1800075ef  mov     eax, 80004003h
0x1800075f4  mov     rcx, [rsp+478h+var_28]
0x1800075fc  xor     rcx, rsp; StackCookie
0x1800075ff  call    __security_check_cookie
0x180007604  lea     r11, [rsp+478h+var_18]
0x18000760c  mov     rbx, [r11+30h]
0x180007610  mov     rbp, [r11+38h]
0x180007614  mov     rsp, r11
0x180007617  pop     r14
0x180007619  pop     rdi
0x18000761a  pop     rsi
0x18000761b  retn
```
