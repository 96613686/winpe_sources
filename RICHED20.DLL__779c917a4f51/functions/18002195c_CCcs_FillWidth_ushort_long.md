# CCcs::FillWidth(ushort,long &)

- ea: `0x18002195c`
- end: `0x180021d0f`
- name: `?FillWidth@CCcs@@AEAAHGAEAJ@Z`
- size: `947`
- prototype: `__int64 __fastcall(CCcs *__hidden this, unsigned __int16, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180021160`

## callees

- `0x18002195c`
- `0x180033af0`
- `0x18003b4e0`
- `0x1800475c4`
- `0x18008d830`
- `0x18009110a`
- `0x180091140`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180021be2`
- `KERNEL32!WideCharToMultiByte` at `0x180021be2`
- `GDI32!GetDeviceCaps` at `0x180021c2c`
- `GDI32!GetDeviceCaps` at `0x180021c2c`
- `GDI32!DeleteObject` at `0x180021aef`
- `GDI32!DeleteObject` at `0x180021aef`
- `GDI32!GetStockObject` at `0x180021c4f`
- `GDI32!GetStockObject` at `0x180021c4f`
- `GDI32!SelectObject` at `0x180021999`
- `GDI32!SelectObject` at `0x180021a44`
- `GDI32!SelectObject` at `0x180021ae6`
- `GDI32!SelectObject` at `0x180021c5b`
- `GDI32!SelectObject` at `0x180021caf`
- `GDI32!SelectObject` at `0x180021999`
- `GDI32!SelectObject` at `0x180021a44`
- `GDI32!SelectObject` at `0x180021ae6`
- `GDI32!SelectObject` at `0x180021c5b`
- `GDI32!SelectObject` at `0x180021caf`
- `GDI32!GetCharWidthW` at `0x180021ac1`
- `GDI32!GetCharWidthW` at `0x180021b83`
- `GDI32!GetCharWidthW` at `0x180021ac1`
- `GDI32!GetCharWidthW` at `0x180021b83`
- `GDI32!GetCharWidthA` at `0x180021a08`
- `GDI32!GetCharWidthA` at `0x180021c07`
- `GDI32!GetCharWidthA` at `0x180021a08`
- `GDI32!GetCharWidthA` at `0x180021c07`

## pseudocode

```c
__int64 __fastcall CCcs::FillWidth(CCcs *this, unsigned __int16 a2, int *a3)
{
  __int64 v3; // r14
  void *v5; // rdx
  HDC v6; // rcx
  __int64 result; // rax
  __int16 v8; // cx
  unsigned int v9; // r12d
  HDC v10; // r15
  __int64 v11; // rsi
  __int64 v12; // rbx
  WCHAR v13; // cx
  __int16 v14; // ax
  HFONT v15; // r13
  __int16 *v16; // rbx
  int v17; // eax
  unsigned __int16 v18; // cx
  HGDIOBJ StockObject; // rax
  HGDIOBJ v20; // r13
  BYTE v21; // cl
  int cbMultiByte; // [rsp+28h] [rbp-A1h]
  WCHAR WideCharStr; // [rsp+40h] [rbp-89h] BYREF
  int Buffer; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int16 MultiByteStr; // [rsp+4Ch] [rbp-7Dh] BYREF
  __int16 v26; // [rsp+50h] [rbp-79h]
  int v27; // [rsp+54h] [rbp-75h]
  BOOL UsedDefaultChar; // [rsp+58h] [rbp-71h] BYREF
  HGDIOBJ v29; // [rsp+60h] [rbp-69h]
  int *v30; // [rsp+68h] [rbp-61h]
  HGDIOBJ h; // [rsp+70h] [rbp-59h]
  struct tagLOGFONTW v32; // [rsp+80h] [rbp-49h] BYREF

  v3 = a2;
  v5 = (void *)*((_QWORD *)this + 9);
  v6 = (HDC)*((_QWORD *)this + 8);
  v30 = a3;
  result = (__int64)SelectObject(v6, v5);
  h = (HGDIOBJ)result;
  if ( result )
  {
    v8 = *((_WORD *)this + 48);
    v9 = *((unsigned __int16 *)this + 58);
    v10 = (HDC)*((_QWORD *)this + 8);
    v26 = v8;
    if ( (unsigned __int16)v3 >= 0x4E00u
      && ((unsigned int)(v3 - 19968) <= 0x51FF || (unsigned int)(v3 - 63744) <= 0x1FF) )
    {
      v16 = (__int16 *)((char *)this + 36);
      if ( (unsigned int)(v3 - 44032) > 0x2B9F )
        v16 = (__int16 *)((char *)this + 38);
      CW32System::REGetCharWidth(v10, v3, v16, v9, v8, cbMultiByte);
      v14 = *v16;
      goto LABEL_7;
    }
    v11 = *((_QWORD *)this + 6);
    v12 = v3 & *((int *)this + 4);
    Buffer = 0;
    v13 = v3;
    WideCharStr = v3;
    *(_WORD *)(v11 + 4 * v12 + 2) = 0;
    if ( v9 == 42 || (unsigned __int16)v3 <= 0x7Fu )
    {
      if ( GetCharWidthA(v10, v3, v3, &Buffer) )
        goto LABEL_5;
      v13 = WideCharStr;
    }
    v15 = 0;
    v27 = 0;
    v29 = 0;
    if ( v13 == 8364 )
    {
      if ( GetDeviceCaps(v10, 2) != 1 || (unsigned int)CW32System::IsEnhancedMetafileDC(v10) )
      {
        v27 = 1;
        StockObject = GetStockObject(12);
        v20 = SelectObject(v10, StockObject);
        v29 = v20;
        memset_0(&v32, 0, sizeof(v32));
        CW32System::GetObjectW(v20, 92, &v32);
        v21 = 9;
        if ( CW32System::_dwPlatformId == 1 )
          v21 = 7;
        v32.lfOutPrecision = v21;
        v15 = CW32System::CreateFontIndirect(&v32);
        SelectObject(v10, v15);
      }
      v13 = WideCharStr;
    }
    if ( CW32System::_dwPlatformId != 1
      || CW32System::_dwMajorVersion != 4
      || CW32System::_dwMinorVersion
      || (unsigned int)v13 - 128 <= 0x7F
      || v9 != 950 && v9 != 936 )
    {
      goto LABEL_11;
    }
    GetCharWidthW(v10, 0x4E00u, 0x4E00u, &Buffer);
    *(_WORD *)(v11 + 4 * v12 + 2) = Buffer;
    if ( (unsigned int)WideCharStr - 19968 <= 0x51FF )
    {
LABEL_6:
      *(_WORD *)(v11 + 4 * v12 + 2) -= v26;
      v14 = *(_WORD *)(v11 + 4 * v12 + 2);
      *(_WORD *)(v11 + 4 * v12) = v3;
LABEL_7:
      *v30 = v14;
      SelectObject(*((HDC *)this + 8), h);
      return 1;
    }
    UsedDefaultChar = 0;
    v17 = WideCharToMultiByte(v9, 0, &WideCharStr, 1, (LPSTR)&MultiByteStr, 2, 0, &UsedDefaultChar);
    v18 = (unsigned __int8)MultiByteStr;
    if ( v17 == 2 )
    {
      v18 = _byteswap_ushort(MultiByteStr);
    }
    else if ( v17 <= 0 )
    {
LABEL_29:
      v13 = WideCharStr;
LABEL_11:
      if ( v13 == 0xFFFF )
      {
        v13 = -2;
        WideCharStr = -2;
      }
      if ( GetCharWidthW(v10, v13, v13, &Buffer) )
        *(_WORD *)(v11 + 4 * v12 + 2) = Buffer;
      if ( v27 )
      {
        SelectObject(v10, v29);
        DeleteObject(v15);
      }
      goto LABEL_6;
    }
    if ( !GetCharWidthA(v10, v18, v18, &Buffer) )
      goto LABEL_29;
LABEL_5:
    *(_WORD *)(v11 + 4 * v12 + 2) = Buffer;
    goto LABEL_6;
  }
  return result;
}

```

## disassembly

```asm
0x18002195c  mov     [rsp-8+arg_18], rbx
0x180021961  push    rbp
0x180021962  push    rsi
0x180021963  push    rdi
0x180021964  push    r12
0x180021966  push    r13
0x180021968  push    r14
0x18002196a  push    r15
0x18002196c  lea     rbp, [rsp-27h]
0x180021971  sub     rsp, 0F0h
0x180021978  mov     rax, cs:__security_cookie
0x18002197f  xor     rax, rsp
0x180021982  mov     [rbp+57h+var_40], rax
0x180021986  movzx   r14d, dx
0x18002198a  mov     rdi, rcx
0x18002198d  mov     rdx, [rcx+48h]; h
0x180021991  mov     rcx, [rcx+40h]; hdc
0x180021995  mov     [rbp+57h+var_B8], r8
0x180021999  call    cs:__imp_SelectObject
0x18002199f  mov     [rbp+57h+h], rax
0x1800219a3  test    rax, rax
0x1800219a6  jz      loc_180021C1F
0x1800219ac  movzx   ecx, word ptr [rdi+60h]
0x1800219b0  mov     eax, 4E00h
0x1800219b5  movzx   r12d, word ptr [rdi+74h]
0x1800219ba  mov     edx, r14d; unsigned __int16
0x1800219bd  mov     r15, [rdi+40h]
0x1800219c1  mov     [rbp+57h+var_D0], cx
0x1800219c5  cmp     r14w, ax
0x1800219c9  jnb     loc_180021B04
0x1800219cf  movsxd  rbx, dword ptr [rdi+10h]
0x1800219d3  xor     eax, eax
0x1800219d5  mov     rsi, [rdi+30h]
0x1800219d9  and     rbx, r14
0x1800219dc  mov     [rsp+120h+Buffer], 0
0x1800219e4  movzx   ecx, r14w
0x1800219e8  mov     [rsp+120h+WideCharStr], cx
0x1800219ed  mov     [rsi+rbx*4+2], ax
0x1800219f2  mov     eax, 7Fh
0x1800219f7  cmp     r12d, 2Ah ; '*'
0x1800219fb  jnz     short loc_180021A76
0x1800219fd  lea     r9, [rsp+120h+Buffer]; lpBuffer
0x180021a02  mov     r8d, edx; iLast
0x180021a05  mov     rcx, r15; hdc
0x180021a08  call    cs:__imp_GetCharWidthA
0x180021a0e  test    eax, eax
0x180021a10  jz      loc_180021AFA
0x180021a16  movzx   eax, word ptr [rsp+120h+Buffer]
0x180021a1b  mov     [rsi+rbx*4+2], ax
0x180021a20  movzx   eax, [rbp+57h+var_D0]
0x180021a24  sub     [rsi+rbx*4+2], ax
0x180021a29  movzx   eax, word ptr [rsi+rbx*4+2]
0x180021a2e  mov     [rsi+rbx*4], r14w
0x180021a33  mov     rdx, [rbp+57h+var_B8]
0x180021a37  movsx   ecx, ax
0x180021a3a  mov     [rdx], ecx
0x180021a3c  mov     rdx, [rbp+57h+h]; h
0x180021a40  mov     rcx, [rdi+40h]; hdc
0x180021a44  call    cs:__imp_SelectObject
0x180021a4a  mov     eax, 1
0x180021a4f  mov     rcx, [rbp+57h+var_40]
0x180021a53  xor     rcx, rsp; StackCookie
0x180021a56  call    __security_check_cookie
0x180021a5b  mov     rbx, [rsp+120h+arg_18]
0x180021a63  add     rsp, 0F0h
0x180021a6a  pop     r15
0x180021a6c  pop     r14
0x180021a6e  pop     r13
0x180021a70  pop     r12
0x180021a72  pop     rdi
0x180021a73  pop     rsi
0x180021a74  pop     rbp
0x180021a75  retn
0x180021a76  cmp     r14w, ax
0x180021a7a  jbe     short loc_1800219FD
0x180021a7c  xor     r13d, r13d
0x180021a7f  mov     [rbp+57h+var_CC], 0
0x180021a86  mov     eax, 20ACh
0x180021a8b  mov     [rbp+57h+var_C0], r13
0x180021a8f  cmp     cx, ax
0x180021a92  jz      loc_180021C24
0x180021a98  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x180021a9f  jz      loc_180021CBF
0x180021aa5  mov     eax, 0FFFFh
0x180021aaa  cmp     cx, ax
0x180021aad  jz      loc_180021D00
0x180021ab3  movzx   edx, cx; iFirst
0x180021ab6  lea     r9, [rsp+120h+Buffer]; lpBuffer
0x180021abb  mov     r8d, edx; iLast
0x180021abe  mov     rcx, r15; hdc
0x180021ac1  call    cs:__imp_GetCharWidthW
0x180021ac7  test    eax, eax
0x180021ac9  jz      short loc_180021AD5
0x180021acb  movzx   eax, word ptr [rsp+120h+Buffer]
0x180021ad0  mov     [rsi+rbx*4+2], ax
0x180021ad5  cmp     [rbp+57h+var_CC], 0
0x180021ad9  jz      loc_180021A20
0x180021adf  mov     rdx, [rbp+57h+var_C0]; h
0x180021ae3  mov     rcx, r15; hdc
0x180021ae6  call    cs:__imp_SelectObject
0x180021aec  mov     rcx, r13; ho
0x180021aef  call    cs:__imp_DeleteObject
0x180021af5  jmp     loc_180021A20
0x180021afa  movzx   ecx, [rsp+120h+WideCharStr]
0x180021aff  jmp     loc_180021A7C
0x180021b04  lea     eax, [r14-4E00h]
0x180021b0b  cmp     eax, 51FFh
0x180021b10  jbe     short loc_180021B24
0x180021b12  lea     eax, [r14-0F900h]
0x180021b19  cmp     eax, 1FFh
0x180021b1e  ja      loc_1800219CF
0x180021b24  lea     eax, [r14-0AC00h]
0x180021b2b  lea     rbx, [rdi+24h]
0x180021b2f  cmp     eax, 2B9Fh
0x180021b34  jbe     short loc_180021B3A
0x180021b36  lea     rbx, [rdi+26h]
0x180021b3a  mov     word ptr [rsp+120h+lpMultiByteStr], cx; __int16
0x180021b3f  mov     r9d, r12d; unsigned int
0x180021b42  mov     rcx, r15; hdc
0x180021b45  mov     r8, rbx; __int16 *
0x180021b48  call    ?REGetCharWidth@CW32System@@SAXPEAUHDC__@@GPEAFIFH@Z; CW32System::REGetCharWidth(HDC__ *,ushort,short *,uint,short,int)
0x180021b4d  movzx   eax, word ptr [rbx]
0x180021b50  jmp     loc_180021A33
0x180021b55  movzx   eax, cx
0x180021b58  add     eax, 0FFFFFF80h
0x180021b5b  cmp     eax, 7Fh
0x180021b5e  jbe     loc_180021AA5
0x180021b64  cmp     r12d, 3B6h
0x180021b6b  jnz     loc_180021CDE
0x180021b71  mov     eax, 4E00h
0x180021b76  lea     r9, [rsp+120h+Buffer]; lpBuffer
0x180021b7b  mov     r8d, eax; iLast
0x180021b7e  mov     edx, eax; iFirst
0x180021b80  mov     rcx, r15; hdc
0x180021b83  call    cs:__imp_GetCharWidthW
0x180021b89  movzx   eax, word ptr [rsp+120h+Buffer]
0x180021b8e  mov     [rsi+rbx*4+2], ax
0x180021b93  movzx   eax, [rsp+120h+WideCharStr]
0x180021b98  sub     eax, 4E00h
0x180021b9d  cmp     eax, 51FFh
0x180021ba2  jbe     loc_180021A20
0x180021ba8  lea     rax, [rbp+57h+UsedDefaultChar]
0x180021bac  mov     [rbp+57h+UsedDefaultChar], 0
0x180021bb3  mov     [rsp+120h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180021bb8  lea     r8, [rsp+120h+WideCharStr]; lpWideCharStr
0x180021bbd  mov     [rsp+120h+lpDefaultChar], 0; lpDefaultChar
0x180021bc6  lea     rax, [rbp+57h+MultiByteStr]
0x180021bca  mov     [rsp+120h+cbMultiByte], 2; cbMultiByte
0x180021bd2  mov     r9d, 1; cchWideChar
0x180021bd8  xor     edx, edx; dwFlags
0x180021bda  mov     [rsp+120h+lpMultiByteStr], rax; lpMultiByteStr
0x180021bdf  mov     ecx, r12d; CodePage
0x180021be2  call    cs:__imp_WideCharToMultiByte
0x180021be8  movzx   ecx, byte ptr [rbp+57h+MultiByteStr]
0x180021bec  cmp     eax, 2
0x180021bef  jz      loc_180021CF0
0x180021bf5  test    eax, eax
0x180021bf7  jle     short loc_180021C15
0x180021bf9  movzx   edx, cx; iFirst
0x180021bfc  lea     r9, [rsp+120h+Buffer]; lpBuffer
0x180021c01  mov     r8d, edx; iLast
0x180021c04  mov     rcx, r15; hdc
0x180021c07  call    cs:__imp_GetCharWidthA
0x180021c0d  test    eax, eax
0x180021c0f  jnz     loc_180021A16
0x180021c15  movzx   ecx, [rsp+120h+WideCharStr]
0x180021c1a  jmp     loc_180021AA5
0x180021c1f  jmp     loc_180021A4F
0x180021c24  mov     edx, 2; index
0x180021c29  mov     rcx, r15; hdc
0x180021c2c  call    cs:__imp_GetDeviceCaps
0x180021c32  cmp     eax, 1
0x180021c35  jnz     short loc_180021C43
0x180021c37  mov     rcx, r15; hdc
0x180021c3a  call    ?IsEnhancedMetafileDC@CW32System@@SAHPEAUHDC__@@@Z; CW32System::IsEnhancedMetafileDC(HDC__ *)
0x180021c3f  test    eax, eax
0x180021c41  jz      short loc_180021CB5
0x180021c43  mov     ecx, 0Ch; i
0x180021c48  mov     [rbp+57h+var_CC], 1
0x180021c4f  call    cs:__imp_GetStockObject
0x180021c55  mov     rdx, rax; h
0x180021c58  mov     rcx, r15; hdc
0x180021c5b  call    cs:__imp_SelectObject
0x180021c61  xor     edx, edx; Val
0x180021c63  lea     rcx, [rbp+57h+var_A0]; void *
0x180021c67  mov     r13, rax
0x180021c6a  mov     [rbp+57h+var_C0], rax
0x180021c6e  lea     r8d, [rdx+5Ch]; Size
0x180021c72  call    memset_0
0x180021c77  lea     r8, [rbp+57h+var_A0]; void *
0x180021c7b  mov     edx, 5Ch ; '\'; int
0x180021c80  mov     rcx, r13; void *
0x180021c83  call    ?GetObjectW@CW32System@@SAHPEAXH0@Z; CW32System::GetObjectW(void *,int,void *)
0x180021c88  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x180021c8f  mov     ecx, 9
0x180021c94  lea     eax, [rcx-2]
0x180021c97  cmovz   ecx, eax
0x180021c9a  mov     [rbp+57h+var_A0.lfOutPrecision], cl
0x180021c9d  lea     rcx, [rbp+57h+var_A0]; struct tagLOGFONTW *
0x180021ca1  call    ?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z; CW32System::CreateFontIndirect(tagLOGFONTW const *)
0x180021ca6  mov     rdx, rax; h
0x180021ca9  mov     rcx, r15; hdc
0x180021cac  mov     r13, rax
0x180021caf  call    cs:__imp_SelectObject
0x180021cb5  movzx   ecx, [rsp+120h+WideCharStr]
0x180021cba  jmp     loc_180021A98
0x180021cbf  cmp     cs:?_dwMajorVersion@CW32System@@2KA, 4; ulong CW32System::_dwMajorVersion
0x180021cc6  jnz     loc_180021AA5
0x180021ccc  cmp     cs:?_dwMinorVersion@CW32System@@2KA, 0; ulong CW32System::_dwMinorVersion
0x180021cd3  jnz     loc_180021AA5
0x180021cd9  jmp     loc_180021B55
0x180021cde  cmp     r12d, 3A8h
0x180021ce5  jnz     loc_180021AA5
0x180021ceb  jmp     loc_180021B71
0x180021cf0  movzx   eax, byte ptr [rbp+57h+MultiByteStr+1]
0x180021cf4  shl     cx, 8
0x180021cf8  or      cx, ax
0x180021cfb  jmp     loc_180021BF9
0x180021d00  mov     ecx, 0FFFEh
0x180021d05  mov     [rsp+120h+WideCharStr], cx
0x180021d0a  jmp     loc_180021AB3
```
