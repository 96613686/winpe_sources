# try_get_function(`anonymous namespace'::function_id,char const * const,A0x37284e77::module_id const * const,A0x37284e77::module_id const * const)

- ea: `0x140013414`
- end: `0x1400135d0`
- name: `?try_get_function@@YAPEAXW4function_id@?A0x37284e77@@QEBDQEBW4module_id@2@2@Z`
- size: `444`
- prototype: `FARPROC __fastcall(unsigned int, const CHAR *, unsigned int *, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400135d0`
- `0x140013640`
- `0x1400136a4`
- `0x140013780`

## callees

- `0x140013414`
- `0x1400147bc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400134c6`
- `KERNEL32!GetLastError` at `0x1400134c6`
- `KERNEL32!FreeLibrary` at `0x140013590`
- `KERNEL32!FreeLibrary` at `0x140013590`
- `KERNEL32!GetProcAddress` at `0x14001359c`
- `KERNEL32!GetProcAddress` at `0x14001359c`
- `KERNEL32!LoadLibraryExW` at `0x1400134b4`
- `KERNEL32!LoadLibraryExW` at `0x140013508`
- `KERNEL32!LoadLibraryExW` at `0x1400134b4`
- `KERNEL32!LoadLibraryExW` at `0x140013508`

## pseudocode

```c
FARPROC __fastcall try_get_function(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // r15
  unsigned int *v6; // rbp
  uintptr_t v8; // r11
  __int64 v9; // r10
  FARPROC result; // rax
  __int64 v11; // rsi
  HMODULE Library; // rbx
  const WCHAR *v13; // r14

  v4 = a1;
  v6 = a3;
  v8 = _security_cookie;
  v9 = __ROR8__(_security_cookie ^ qword_1400D70D0[a1], _security_cookie & 0x3F);
  if ( v9 == -1 )
    return 0;
  if ( v9 )
    return (FARPROC)v9;
  if ( a3 == a4 )
  {
LABEL_16:
    _InterlockedExchange64(&qword_1400D70D0[v4], v8 ^ __ROR8__(-1, 64 - ((unsigned __int8)v8 & 0x3Fu)));
    return 0;
  }
  while ( 1 )
  {
    v11 = *v6;
    Library = (HMODULE)qword_1400D7020[v11];
    if ( Library )
    {
      if ( Library != (HMODULE)-1LL )
        goto LABEL_20;
      goto LABEL_14;
    }
    v13 = off_1400B1340[v11];
    Library = LoadLibraryExW(v13, 0, 0x800u);
    if ( Library )
      break;
    if ( GetLastError() == 87 )
    {
      if ( wcsncmp(v13, L"api-ms-", 7u) )
      {
        if ( wcsncmp(v13, L"ext-ms-", 7u) )
        {
          Library = LoadLibraryExW(v13, 0, 0);
          if ( Library )
            break;
        }
      }
    }
    _InterlockedExchange64(&qword_1400D7020[v11], -1);
LABEL_14:
    if ( ++v6 == a4 )
      goto LABEL_15;
  }
  if ( _InterlockedExchange64(&qword_1400D7020[v11], (__int64)Library) )
    FreeLibrary(Library);
LABEL_20:
  result = GetProcAddress(Library, a2);
  if ( !result )
  {
LABEL_15:
    v8 = _security_cookie;
    goto LABEL_16;
  }
  _InterlockedExchange64(
    &qword_1400D70D0[v4],
    _security_cookie ^ __ROR8__(result, 64 - ((unsigned __int8)_security_cookie & 0x3Fu)));
  return result;
}

```

## disassembly

```asm
0x140013414  mov     [rsp+arg_0], rbx
0x140013419  mov     [rsp+arg_8], rbp
0x14001341e  mov     [rsp+arg_10], rsi
0x140013423  push    rdi
0x140013424  push    r12
0x140013426  push    r13
0x140013428  push    r14
0x14001342a  push    r15
0x14001342c  sub     rsp, 20h
0x140013430  mov     r15d, ecx
0x140013433  lea     r14, cs:140000000h
0x14001343a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14001343e  mov     r12, r9
0x140013441  mov     rbp, r8
0x140013444  mov     r13, rdx
0x140013447  mov     r10, rva qword_1400D70D0[r14+r15*8]
0x14001344f  nop
0x140013450  mov     r11, cs:__security_cookie
0x140013457  xor     r10, r11
0x14001345a  mov     ecx, r11d
0x14001345d  and     ecx, 3Fh
0x140013460  ror     r10, cl
0x140013463  cmp     r10, rdi
0x140013466  jz      loc_140013557
0x14001346c  test    r10, r10
0x14001346f  jz      short loc_140013479
0x140013471  mov     rax, r10
0x140013474  jmp     loc_140013559
0x140013479  cmp     r8, r12
0x14001347c  jz      loc_14001353C
0x140013482  mov     esi, [rbp+0]
0x140013485  mov     rbx, rva qword_1400D7020[r14+rsi*8]
0x14001348d  nop
0x14001348e  test    rbx, rbx
0x140013491  jz      short loc_1400134A1
0x140013493  cmp     rbx, rdi
0x140013496  jnz     loc_140013596
0x14001349c  jmp     loc_140013528
0x1400134a1  mov     r14, ds:rva off_1400B1340[r14+rsi*8]
0x1400134a9  xor     edx, edx; hFile
0x1400134ab  mov     rcx, r14; lpLibFileName
0x1400134ae  mov     r8d, 800h; dwFlags
0x1400134b4  call    cs:LoadLibraryExW
0x1400134ba  mov     rbx, rax
0x1400134bd  test    rax, rax
0x1400134c0  jnz     loc_140013576
0x1400134c6  call    cs:GetLastError
0x1400134cc  cmp     eax, 57h ; 'W'
0x1400134cf  jnz     short loc_140013516
0x1400134d1  lea     ebx, [rax-50h]
0x1400134d4  mov     rcx, r14; Str1
0x1400134d7  mov     r8d, ebx; MaxCount
0x1400134da  lea     rdx, aApiMs
0x1400134e1  call    wcsncmp
0x1400134e6  test    eax, eax
0x1400134e8  jz      short loc_140013516
0x1400134ea  mov     r8d, ebx; MaxCount
0x1400134ed  lea     rdx, aExtMs
0x1400134f4  mov     rcx, r14; Str1
0x1400134f7  call    wcsncmp
0x1400134fc  test    eax, eax
0x1400134fe  jz      short loc_140013516
0x140013500  xor     r8d, r8d; dwFlags
0x140013503  xor     edx, edx; hFile
0x140013505  mov     rcx, r14; lpLibFileName
0x140013508  call    cs:LoadLibraryExW
0x14001350e  mov     rbx, rax
0x140013511  test    rax, rax
0x140013514  jnz     short loc_140013576
0x140013516  mov     rax, rdi
0x140013519  lea     r14, cs:140000000h
0x140013520  xchg    rax, rva qword_1400D7020[r14+rsi*8]
0x140013528  add     rbp, 4
0x14001352c  cmp     rbp, r12
0x14001352f  jnz     loc_140013482
0x140013535  mov     r11, cs:__security_cookie
0x14001353c  mov     eax, r11d
0x14001353f  mov     ecx, 40h ; '@'
0x140013544  and     eax, 3Fh
0x140013547  sub     ecx, eax
0x140013549  ror     rdi, cl
0x14001354c  xor     rdi, r11
0x14001354f  xchg    rdi, rva qword_1400D70D0[r14+r15*8]
0x140013557  xor     eax, eax
0x140013559  mov     rbx, [rsp+48h+arg_0]
0x14001355e  mov     rbp, [rsp+48h+arg_8]
0x140013563  mov     rsi, [rsp+48h+arg_10]
0x140013568  add     rsp, 20h
0x14001356c  pop     r15
0x14001356e  pop     r14
0x140013570  pop     r13
0x140013572  pop     r12
0x140013574  pop     rdi
0x140013575  retn
0x140013576  mov     rax, rbx
0x140013579  lea     r14, cs:140000000h
0x140013580  xchg    rax, rva qword_1400D7020[r14+rsi*8]
0x140013588  test    rax, rax
0x14001358b  jz      short loc_140013596
0x14001358d  mov     rcx, rbx; hLibModule
0x140013590  call    cs:FreeLibrary
0x140013596  mov     rdx, r13; lpProcName
0x140013599  mov     rcx, rbx; hModule
0x14001359c  call    cs:GetProcAddress
0x1400135a2  test    rax, rax
0x1400135a5  jz      short loc_140013535
0x1400135a7  mov     r8, cs:__security_cookie
0x1400135ae  mov     edx, 40h ; '@'
0x1400135b3  mov     ecx, r8d
0x1400135b6  and     ecx, 3Fh
0x1400135b9  sub     edx, ecx
0x1400135bb  mov     cl, dl
0x1400135bd  mov     rdx, rax
0x1400135c0  ror     rdx, cl
0x1400135c3  xor     rdx, r8
0x1400135c6  xchg    rdx, rva qword_1400D70D0[r14+r15*8]
0x1400135ce  jmp     short loc_140013559
```
