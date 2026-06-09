# SiGetArcPathMnemonicKey

- ea: `0x14001c9e4`
- end: `0x14001cb0e`
- name: `SiGetArcPathMnemonicKey`
- size: `298`
- prototype: `char __fastcall(wchar_t *Str, wchar_t *, unsigned int *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001cc8c`

## callees

- `0x140001738`
- `0x14001c9e4`
- `0x140026650`

## import_xrefs

- `msvcrt!wcsstr` at `0x14001ca67`
- `msvcrt!wcsstr` at `0x14001ca7f`
- `msvcrt!wcsstr` at `0x14001ca67`
- `msvcrt!wcsstr` at `0x14001ca7f`
- `msvcrt!wcstoul` at `0x14001cafb`
- `msvcrt!wcstoul` at `0x14001cafb`

## pseudocode

```c
char __fastcall SiGetArcPathMnemonicKey(wchar_t *Str, wchar_t *a2, unsigned int *a3, int a4)
{
  unsigned int i; // ebx
  wchar_t v8; // ax
  __int64 v9; // rcx
  __int64 v10; // rdi
  wchar_t *v11; // rdx
  __int64 v13; // rcx
  wchar_t *v14; // rdx
  wchar_t v15; // r9
  wchar_t String[12]; // [rsp+20h] [rbp-78h] BYREF
  wchar_t v17; // [rsp+38h] [rbp-60h] BYREF
  wchar_t SubStr[15]; // [rsp+3Ah] [rbp-5Eh] BYREF

  v17 = 41;
  for ( i = 1; *a2 && i < 0xE; ++i )
  {
    v8 = *a2++;
    v9 = i;
    SubStr[v9 - 1] = v8;
  }
  v10 = i + 1;
  SubStr[i - 1] = 40;
  if ( (unsigned __int64)(2 * v10) >= 0x20 )
    goto LABEL_18;
  SubStr[v10 - 1] = 0;
  v11 = wcsstr(Str, SubStr);
  if ( v11 != Str )
  {
    ++i;
    v11 = wcsstr(Str, &v17);
  }
  if ( !v11 )
    return 0;
  v13 = 0;
  v14 = &v11[i];
  while ( 1 )
  {
    v15 = *v14;
    if ( *v14 == 41 )
      break;
    ++v14;
    String[v13] = v15;
    v13 = (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= 8 )
      goto LABEL_16;
  }
  if ( (unsigned __int64)(2 * v13) >= 0x12 )
    goto LABEL_18;
  String[v13] = 0;
LABEL_16:
  if ( (unsigned __int64)(2 * v13) >= 0x12 )
LABEL_18:
    _report_rangecheckfailure();
  String[v13] = 0;
  *a3 = wcstoul(String, 0, a4);
  return 1;
}

```

## disassembly

```asm
0x14001c9e4  push    rbx
0x14001c9e6  push    rbp
0x14001c9e7  push    rsi
0x14001c9e8  push    rdi
0x14001c9e9  push    r12
0x14001c9eb  push    r14
0x14001c9ed  push    r15
0x14001c9ef  sub     rsp, 60h
0x14001c9f3  mov     rax, cs:__security_cookie
0x14001c9fa  xor     rax, rsp
0x14001c9fd  mov     [rsp+98h+var_40], rax
0x14001ca02  mov     r12d, 29h ; ')'
0x14001ca08  mov     ebp, r9d
0x14001ca0b  mov     r14, r8
0x14001ca0e  mov     [rsp+98h+var_60], r12w
0x14001ca14  mov     rsi, rcx
0x14001ca17  xor     r15d, r15d
0x14001ca1a  lea     ebx, [r12-28h]
0x14001ca1f  jmp     short loc_14001CA36
0x14001ca21  cmp     ebx, 0Eh
0x14001ca24  jnb     short loc_14001CA3C
0x14001ca26  movzx   eax, word ptr [rdx]
0x14001ca29  add     rdx, 2
0x14001ca2d  mov     ecx, ebx
0x14001ca2f  inc     ebx
0x14001ca31  mov     [rsp+rcx*2+98h+var_60], ax
0x14001ca36  cmp     [rdx], r15w
0x14001ca3a  jnz     short loc_14001CA21
0x14001ca3c  mov     eax, ebx
0x14001ca3e  lea     edi, [rbx+1]
0x14001ca41  lea     rdx, [rdi+rdi]
0x14001ca45  mov     ecx, 28h ; '('
0x14001ca4a  mov     [rsp+rax*2+98h+var_60], cx
0x14001ca4f  cmp     rdx, 20h ; ' '
0x14001ca53  jnb     loc_14001CB08
0x14001ca59  mov     [rsp+rdx+98h+var_60], r15w
0x14001ca5f  mov     rcx, rsi; Str
0x14001ca62  lea     rdx, [rsp+98h+SubStr]; SubStr
0x14001ca67  call    cs:__imp_wcsstr
0x14001ca6d  mov     rdx, rax
0x14001ca70  cmp     rax, rsi
0x14001ca73  jz      short loc_14001CA88
0x14001ca75  lea     rdx, [rsp+98h+var_60]; SubStr
0x14001ca7a  mov     rcx, rsi; Str
0x14001ca7d  mov     ebx, edi
0x14001ca7f  call    cs:__imp_wcsstr
0x14001ca85  mov     rdx, rax
0x14001ca88  test    rdx, rdx
0x14001ca8b  jnz     short loc_14001CAAB
0x14001ca8d  xor     al, al
0x14001ca8f  mov     rcx, [rsp+98h+var_40]
0x14001ca94  xor     rcx, rsp; StackCookie
0x14001ca97  call    __security_check_cookie
0x14001ca9c  add     rsp, 60h
0x14001caa0  pop     r15
0x14001caa2  pop     r14
0x14001caa4  pop     r12
0x14001caa6  pop     rdi
0x14001caa7  pop     rsi
0x14001caa8  pop     rbp
0x14001caa9  pop     rbx
0x14001caaa  retn
0x14001caab  mov     eax, ebx
0x14001caad  mov     ecx, r15d
0x14001cab0  lea     rdx, [rdx+rax*2]
0x14001cab4  movzx   r9d, word ptr [rdx]
0x14001cab8  lea     r8, [rcx+rcx]
0x14001cabc  cmp     r9w, r12w
0x14001cac0  jz      short loc_14001CAD5
0x14001cac2  add     rdx, 2
0x14001cac6  mov     [rsp+r8+98h+String], r9w
0x14001cacc  inc     ecx
0x14001cace  cmp     ecx, 8
0x14001cad1  jb      short loc_14001CAB4
0x14001cad3  jmp     short loc_14001CAE1
0x14001cad5  cmp     r8, 12h
0x14001cad9  jnb     short loc_14001CB08
0x14001cadb  mov     [rsp+r8+98h+String], r15w
0x14001cae1  lea     rdx, [rcx+rcx]
0x14001cae5  cmp     rdx, 12h
0x14001cae9  jnb     short loc_14001CB08
0x14001caeb  mov     [rsp+rdx+98h+String], r15w
0x14001caf1  lea     rcx, [rsp+98h+String]; String
0x14001caf6  xor     edx, edx; EndPtr
0x14001caf8  mov     r8d, ebp; Radix
0x14001cafb  call    cs:__imp_wcstoul
0x14001cb01  mov     [r14], eax
0x14001cb04  mov     al, 1
0x14001cb06  jmp     short loc_14001CA8F
0x14001cb08  call    __report_rangecheckfailure
```
