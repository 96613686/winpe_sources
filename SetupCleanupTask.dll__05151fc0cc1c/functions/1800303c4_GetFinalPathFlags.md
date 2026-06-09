# GetFinalPathFlags

- ea: `0x1800303c4`
- end: `0x180030588`
- name: `GetFinalPathFlags`
- size: `452`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x180030590`

## callees

- `0x180002ecf`
- `0x1800303c4`
- `0x1800322ea`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003055d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003055d`

## pseudocode

```c
__int64 __fastcall GetFinalPathFlags(wchar_t *String1, _QWORD *a2, __int64 *a3)
{
  wchar_t v6; // si
  unsigned int v7; // r15d
  __int64 v8; // rbx
  __int64 v9; // rbp
  wchar_t v10; // cx
  wchar_t *v11; // rsi
  wchar_t String2[8]; // [rsp+20h] [rbp-98h] BYREF
  wchar_t v14[8]; // [rsp+30h] [rbp-88h] BYREF
  wchar_t v15[12]; // [rsp+40h] [rbp-78h] BYREF
  wchar_t v16[16]; // [rsp+58h] [rbp-60h] BYREF

  wcscpy(String2, L"\\\\?\\");
  wcscpy(v16, L"\\\\?\\GLBALROOT");
  wcscpy(v15, L"\\\\?\\Volume{");
  wcscpy(v14, L"\\Device");
  if ( !String1 || (v6 = *String1) == 0 )
  {
    SetLastError(0x57u);
    return 4;
  }
  v7 = 0;
  v8 = 0;
  v9 = 0;
  if ( wcsncmp_0(String1, String2, 4u)
    || (v10 = String1[4], (unsigned __int16)(v10 - 97) > 0x19u) && (unsigned __int16)(v10 - 65) > 0x19u
    || String1[5] != 58 )
  {
    if ( (unsigned __int16)(v6 - 97) > 0x19u && (unsigned __int16)(v6 - 65) > 0x19u || String1[1] != 58 )
    {
      v8 = wcsnicmp_0(String1, v16, 0xEu) == 0 ? 0xE : 0;
      v11 = &String1[v8];
      if ( !wcsnicmp_0(v11, v15, 0xBu) )
      {
        v7 = 1;
        goto LABEL_19;
      }
      if ( !wcsnicmp_0(&String1[v8], v14, 7u) )
      {
        v7 = 2;
        goto LABEL_19;
      }
      if ( (unsigned __int16)(*v11 - 97) > 0x19u && (unsigned __int16)(*v11 - 65) > 0x19u || v11[1] != 58 )
      {
        v7 = 4;
        v9 = -1;
        goto LABEL_19;
      }
    }
    v9 = 4;
  }
LABEL_19:
  if ( a2 )
    *a2 = v8;
  if ( a3 )
    *a3 = v9;
  return v7;
}

```

## disassembly

```asm
0x1800303c4  push    rbx
0x1800303c6  push    rbp
0x1800303c7  push    rsi
0x1800303c8  push    r12
0x1800303ca  push    r13
0x1800303cc  push    r14
0x1800303ce  push    r15
0x1800303d0  sub     rsp, 80h
0x1800303d7  mov     rax, cs:__security_cookie
0x1800303de  xor     rax, rsp
0x1800303e1  mov     [rsp+0B8h+var_40], rax
0x1800303e6  movsd   xmm0, qword ptr cs:asc_18003D740; "\\\\?\\"
0x1800303ee  mov     r12, r8
0x1800303f1  movzx   eax, word ptr cs:asc_18003D740+8; ""
0x1800303f8  mov     r13, rdx
0x1800303fb  movsd   qword ptr [rsp+0B8h+String2], xmm0
0x180030401  mov     r14, rcx
0x180030404  mov     [rsp+0B8h+var_90], ax
0x180030409  movups  xmm0, xmmword ptr cs:aGlobalroot; "\\\\?\\GLOBALROOT"
0x180030410  movups  xmm1, xmmword ptr cs:aGlobalroot+0Eh; "BALROOT"
0x180030417  movups  xmmword ptr [rsp+0B8h+var_60], xmm0
0x18003041c  movups  xmm0, xmmword ptr cs:aVolume_0; "\\\\?\\Volume{"
0x180030423  movups  xmmword ptr [rsp+0B8h+var_60+0Eh], xmm1
0x180030428  movsd   xmm1, qword ptr cs:aVolume_0+10h; "me{"
0x180030430  movsd   [rsp+0B8h+var_68], xmm1
0x180030436  movups  xmmword ptr [rsp+0B8h+var_78], xmm0
0x18003043b  movups  xmm0, xmmword ptr cs:aDevice; "\\Device"
0x180030442  movdqu  xmmword ptr [rsp+0B8h+var_88], xmm0
0x180030448  test    rcx, rcx
0x18003044b  jz      loc_180030558
0x180030451  movzx   esi, word ptr [rcx]
0x180030454  xor     eax, eax
0x180030456  cmp     ax, si
0x180030459  jz      loc_180030558
0x18003045f  lea     r8d, [rax+4]; MaxCount
0x180030463  xor     r15d, r15d
0x180030466  lea     rdx, [rsp+0B8h+String2]; String2
0x18003046b  xor     ebx, ebx
0x18003046d  xor     ebp, ebp
0x18003046f  call    wcsncmp_0
0x180030474  mov     dx, 19h
0x180030478  test    eax, eax
0x18003047a  jnz     short loc_18003049E
0x18003047c  movzx   ecx, word ptr [r14+8]
0x180030481  lea     eax, [rcx-61h]
0x180030484  cmp     ax, dx
0x180030487  jbe     short loc_180030492
0x180030489  sub     cx, 41h ; 'A'
0x18003048d  cmp     cx, dx
0x180030490  ja      short loc_18003049E
0x180030492  cmp     word ptr [r14+0Ah], 3Ah ; ':'
0x180030498  jz      loc_180030541
0x18003049e  lea     eax, [rsi-61h]
0x1800304a1  cmp     ax, dx
0x1800304a4  jbe     short loc_1800304AF
0x1800304a6  sub     si, 41h ; 'A'
0x1800304aa  cmp     si, dx
0x1800304ad  ja      short loc_1800304B7
0x1800304af  cmp     word ptr [r14+2], 3Ah ; ':'
0x1800304b5  jz      short loc_180030530
0x1800304b7  mov     r8d, 0Eh; MaxCount
0x1800304bd  lea     rdx, [rsp+0B8h+var_60]; String2
0x1800304c2  mov     rcx, r14; String1
0x1800304c5  call    _wcsnicmp_0
0x1800304ca  neg     eax
0x1800304cc  lea     rdx, [rsp+0B8h+var_78]; String2
0x1800304d1  mov     r8d, 0Bh; MaxCount
0x1800304d7  sbb     rbx, rbx
0x1800304da  not     rbx
0x1800304dd  and     ebx, 0Eh
0x1800304e0  lea     rsi, [r14+rbx*2]
0x1800304e4  mov     rcx, rsi; String1
0x1800304e7  call    _wcsnicmp_0
0x1800304ec  test    eax, eax
0x1800304ee  jnz     short loc_1800304F6
0x1800304f0  lea     r15d, [rax+1]
0x1800304f4  jmp     short loc_180030541
0x1800304f6  mov     r8d, 7; MaxCount
0x1800304fc  lea     rdx, [rsp+0B8h+var_88]; String2
0x180030501  mov     rcx, rsi; String1
0x180030504  call    _wcsnicmp_0
0x180030509  test    eax, eax
0x18003050b  jnz     short loc_180030513
0x18003050d  lea     r15d, [rax+2]
0x180030511  jmp     short loc_180030541
0x180030513  movzx   ecx, word ptr [rsi]
0x180030516  lea     eax, [rcx-61h]
0x180030519  cmp     ax, 19h
0x18003051d  jbe     short loc_180030529
0x18003051f  sub     cx, 41h ; 'A'
0x180030523  cmp     cx, 19h
0x180030527  ja      short loc_180030537
0x180030529  cmp     word ptr [rsi+2], 3Ah ; ':'
0x18003052e  jnz     short loc_180030537
0x180030530  mov     ebp, 4
0x180030535  jmp     short loc_180030541
0x180030537  mov     r15d, 4
0x18003053d  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180030541  test    r13, r13
0x180030544  jz      short loc_18003054A
0x180030546  mov     [r13+0], rbx
0x18003054a  test    r12, r12
0x18003054d  jz      short loc_180030553
0x18003054f  mov     [r12], rbp
0x180030553  mov     eax, r15d
0x180030556  jmp     short loc_180030568
0x180030558  mov     ecx, 57h ; 'W'; dwErrCode
0x18003055d  call    cs:__imp_SetLastError
0x180030563  mov     eax, 4
0x180030568  mov     rcx, [rsp+0B8h+var_40]
0x18003056d  xor     rcx, rsp; StackCookie
0x180030570  call    __security_check_cookie
0x180030575  add     rsp, 80h
0x18003057c  pop     r15
0x18003057e  pop     r14
0x180030580  pop     r13
0x180030582  pop     r12
0x180030584  pop     rsi
0x180030585  pop     rbp
0x180030586  pop     rbx
0x180030587  retn
```
