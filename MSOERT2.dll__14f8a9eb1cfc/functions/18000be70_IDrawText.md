# IDrawText

- ea: `0x18000be70`
- end: `0x18000bfee`
- name: `IDrawText`
- size: `382`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, unsigned __int16 *@<rdx>, RECT *lprect@<r8>, int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004640`
- `0x180009de0`
- `0x18000be70`
- `0x180012f82`
- `0x180012fc0`

## import_xrefs

- `GDI32!GetTextExtentPoint32W` at `0x18000bef8`
- `GDI32!GetTextExtentPoint32W` at `0x18000bef8`
- `GDI32!ExtTextOutW` at `0x18000bfbe`
- `GDI32!ExtTextOutW` at `0x18000bfbe`
- `USER32!IsRectEmpty` at `0x18000bec5`
- `USER32!IsRectEmpty` at `0x18000bec5`

## pseudocode

```c
void __fastcall IDrawText(HDC hdc, unsigned __int16 *a2, RECT *lprect, int a4, int a5)
{
  WCHAR *lpString; // r14
  int v9; // esi
  __int64 c; // rsi
  int v11; // r8d
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  struct tagSIZE psizl; // [rsp+48h] [rbp-B8h] BYREF
  int x[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 String[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( a2 )
  {
    v12 = 0;
    psizl = 0;
    lpString = a2;
    if ( !IsRectEmpty(lprect) )
    {
      *(RECT *)x = *lprect;
      if ( a4
        && (GetTextExtentPoint32W(hdc, L"...", 3, &psizl),
            (unsigned int)NeedsEllipses(hdc, lpString, (struct tagRECT *)x, &v12, psizl.cx)) )
      {
        v9 = v12;
        if ( (unsigned __int64)v12 >= 0x104 )
          v9 = 259;
        memcpy_0(String, lpString, 2LL * v9);
        StringCchCopyW(&String[v9], 263LL - v9, L"...");
        LODWORD(c) = v9 + 3;
        lpString = String;
      }
      else
      {
        c = -1;
        do
          ++c;
        while ( lpString[c] );
      }
      v11 = x[1];
      if ( a5 )
        v11 = (x[3] - x[1] - a5) / 2 + x[1];
      ExtTextOutW(hdc, x[0], v11, 0, lprect, lpString, c, 0);
    }
  }
}

```

## disassembly

```asm
0x18000be70  test    rdx, rdx
0x18000be73  jz      locret_18000BFED
0x18000be79  mov     [rsp-8+arg_18], rbx
0x18000be7e  push    rbp
0x18000be7f  push    rsi
0x18000be80  push    rdi
0x18000be81  push    r12
0x18000be83  push    r13
0x18000be85  push    r14
0x18000be87  push    r15
0x18000be89  lea     rbp, [rsp-180h]
0x18000be91  sub     rsp, 280h
0x18000be98  mov     rax, cs:__security_cookie
0x18000be9f  xor     rax, rsp
0x18000bea2  mov     [rbp+1B0h+var_40], rax
0x18000bea9  mov     r12, rcx
0x18000beac  xor     r13d, r13d
0x18000beaf  mov     rcx, r8; lprc
0x18000beb2  mov     [rsp+2B0h+var_270], r13d
0x18000beb7  mov     qword ptr [rsp+2B0h+psizl.cx], r13
0x18000bebc  mov     ebx, r9d
0x18000bebf  mov     r15, r8
0x18000bec2  mov     r14, rdx
0x18000bec5  call    cs:__imp_IsRectEmpty
0x18000becb  test    eax, eax
0x18000becd  jnz     loc_18000BFC4
0x18000bed3  movups  xmm0, xmmword ptr [r15]
0x18000bed7  movdqu  xmmword ptr [rsp+2B0h+x], xmm0
0x18000bedd  test    ebx, ebx
0x18000bedf  jz      loc_18000BF70
0x18000bee5  lea     r9, [rsp+2B0h+psizl]; psizl
0x18000beea  mov     rcx, r12; hdc
0x18000beed  lea     r8d, [r13+3]; c
0x18000bef1  lea     rdx, g_wszEllipsis; "..."
0x18000bef8  call    cs:__imp_GetTextExtentPoint32W
0x18000befe  mov     eax, [rsp+2B0h+psizl.cx]
0x18000bf02  lea     r9, [rsp+2B0h+var_270]; int *
0x18000bf07  lea     r8, [rsp+2B0h+x]; struct tagRECT *
0x18000bf0c  mov     dword ptr [rsp+2B0h+lprect], eax; int
0x18000bf10  mov     rdx, r14; unsigned __int16 *
0x18000bf13  mov     rcx, r12; hdc
0x18000bf16  call    ?NeedsEllipses@@YAHPEAUHDC__@@PEBGPEAUtagRECT@@PEAHH@Z; NeedsEllipses(HDC__ *,ushort const *,tagRECT *,int *,int)
0x18000bf1b  test    eax, eax
0x18000bf1d  jz      short loc_18000BF70
0x18000bf1f  movsxd  rsi, [rsp+2B0h+var_270]
0x18000bf24  mov     ecx, 103h
0x18000bf29  cmp     rsi, 104h
0x18000bf30  mov     rdx, r14; Src
0x18000bf33  cmovnb  esi, ecx
0x18000bf36  lea     rcx, [rsp+2B0h+String]; void *
0x18000bf3b  movsxd  rbx, esi
0x18000bf3e  lea     rdi, [rbx+rbx]
0x18000bf42  mov     r8, rdi; Size
0x18000bf45  call    memcpy_0
0x18000bf4a  mov     edx, 107h
0x18000bf4f  lea     rcx, [rsp+2B0h+String]
0x18000bf54  sub     rdx, rbx; unsigned __int64
0x18000bf57  lea     r8, g_wszEllipsis; "..."
0x18000bf5e  add     rcx, rdi; unsigned __int16 *
0x18000bf61  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bf66  add     esi, 3
0x18000bf69  lea     r14, [rsp+2B0h+String]
0x18000bf6e  jmp     short loc_18000BF7E
0x18000bf70  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000bf74  inc     rsi
0x18000bf77  cmp     [r14+rsi*2], r13w
0x18000bf7c  jnz     short loc_18000BF74
0x18000bf7e  mov     ecx, [rbp+1B0h+arg_20]
0x18000bf84  mov     r8d, [rsp+2B0h+x+4]
0x18000bf89  test    ecx, ecx
0x18000bf8b  jz      short loc_18000BFA1
0x18000bf8d  mov     eax, [rsp+2B0h+x+0Ch]
0x18000bf91  sub     eax, r8d
0x18000bf94  sub     eax, ecx
0x18000bf96  mov     ecx, 2
0x18000bf9b  cdq
0x18000bf9c  idiv    ecx
0x18000bf9e  add     r8d, eax; y
0x18000bfa1  mov     edx, [rsp+2B0h+x]; x
0x18000bfa5  xor     r9d, r9d; options
0x18000bfa8  mov     [rsp+2B0h+lpDx], r13; lpDx
0x18000bfad  mov     rcx, r12; hdc
0x18000bfb0  mov     [rsp+2B0h+c], esi; c
0x18000bfb4  mov     [rsp+2B0h+lpString], r14; lpString
0x18000bfb9  mov     [rsp+2B0h+lprect], r15; lprect
0x18000bfbe  call    cs:__imp_ExtTextOutW
0x18000bfc4  mov     rcx, [rbp+1B0h+var_40]
0x18000bfcb  xor     rcx, rsp; StackCookie
0x18000bfce  call    __security_check_cookie
0x18000bfd3  mov     rbx, [rsp+2B0h+arg_18]
0x18000bfdb  add     rsp, 280h
0x18000bfe2  pop     r15
0x18000bfe4  pop     r14
0x18000bfe6  pop     r13
0x18000bfe8  pop     r12
0x18000bfea  pop     rdi
0x18000bfeb  pop     rsi
0x18000bfec  pop     rbp
0x18000bfed  retn
```
