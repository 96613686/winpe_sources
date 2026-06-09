# CW32System::REGetCharWidth(HDC__ *,ushort,short *,uint,short,int)

- ea: `0x18003b4e0`
- end: `0x18003b798`
- name: `?REGetCharWidth@CW32System@@SAXPEAUHDC__@@GPEAFIFH@Z`
- size: `696`
- prototype: `void __usercall(HDC hdc@<rcx>, unsigned __int16@<dx>, __int16 *@<r8>, unsigned int@<r9d>, __int16, int)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a0b0`
- `0x1800124f0`
- `0x18002195c`
- `0x180033b90`

## callees

- `0x180033af0`
- `0x18003b4e0`
- `0x1800475c4`
- `0x18008d830`
- `0x18009110a`
- `0x180091140`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18003b66d`
- `KERNEL32!WideCharToMultiByte` at `0x18003b66d`
- `GDI32!GetDeviceCaps` at `0x18003b723`
- `GDI32!GetDeviceCaps` at `0x18003b723`
- `GDI32!DeleteObject` at `0x18003b5df`
- `GDI32!DeleteObject` at `0x18003b5df`
- `GDI32!GetStockObject` at `0x18003b6b5`
- `GDI32!GetStockObject` at `0x18003b6b5`
- `GDI32!SelectObject` at `0x18003b5d6`
- `GDI32!SelectObject` at `0x18003b6c1`
- `GDI32!SelectObject` at `0x18003b70b`
- `GDI32!SelectObject` at `0x18003b5d6`
- `GDI32!SelectObject` at `0x18003b6c1`
- `GDI32!SelectObject` at `0x18003b70b`
- `GDI32!GetCharWidthW` at `0x18003b5b5`
- `GDI32!GetCharWidthW` at `0x18003b618`
- `GDI32!GetCharWidthW` at `0x18003b5b5`
- `GDI32!GetCharWidthW` at `0x18003b618`
- `GDI32!GetCharWidthA` at `0x18003b532`
- `GDI32!GetCharWidthA` at `0x18003b692`
- `GDI32!GetCharWidthA` at `0x18003b532`
- `GDI32!GetCharWidthA` at `0x18003b692`

## pseudocode

```c
void __fastcall CW32System::REGetCharWidth(HDC hdc, WCHAR a2, __int16 *a3, UINT a4, __int16 a5)
{
  int v8; // r14d
  HFONT v9; // r15
  HGDIOBJ v10; // r12
  int v11; // eax
  unsigned __int16 v12; // cx
  HGDIOBJ StockObject; // rax
  WCHAR WideCharStr; // [rsp+40h] [rbp-89h] BYREF
  int Buffer; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int16 MultiByteStr; // [rsp+4Ch] [rbp-7Dh] BYREF
  BOOL UsedDefaultChar; // [rsp+50h] [rbp-79h] BYREF
  struct tagLOGFONTW v18; // [rsp+60h] [rbp-69h] BYREF

  WideCharStr = a2;
  Buffer = 0;
  *a3 = 0;
  if ( a4 == 42 || a2 <= 0x7Fu )
  {
    if ( GetCharWidthA(hdc, a2, a2, &Buffer) )
      goto LABEL_3;
    a2 = WideCharStr;
  }
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( a2 == 8364 )
  {
    if ( GetDeviceCaps(hdc, 2) != 1 || (unsigned int)CW32System::IsEnhancedMetafileDC(hdc) )
    {
      v8 = 1;
      StockObject = GetStockObject(12);
      v10 = SelectObject(hdc, StockObject);
      memset_0(&v18, 0, sizeof(v18));
      CW32System::GetObjectW(v10, 92, &v18);
      if ( CW32System::_dwPlatformId == 1 )
        v18.lfOutPrecision = 7;
      else
        v18.lfOutPrecision = 9;
      v9 = CW32System::CreateFontIndirect(&v18);
      SelectObject(hdc, v9);
    }
    a2 = WideCharStr;
  }
  if ( CW32System::_dwPlatformId != 1
    || CW32System::_dwMajorVersion != 4
    || CW32System::_dwMinorVersion
    || (unsigned int)a2 - 128 <= 0x7F
    || a4 != 950 && a4 != 936 )
  {
    goto LABEL_8;
  }
  GetCharWidthW(hdc, 0x4E00u, 0x4E00u, &Buffer);
  *a3 = Buffer;
  if ( (unsigned int)WideCharStr - 19968 <= 0x51FF )
    goto LABEL_4;
  UsedDefaultChar = 0;
  v11 = WideCharToMultiByte(a4, 0, &WideCharStr, 1, (LPSTR)&MultiByteStr, 2, 0, &UsedDefaultChar);
  v12 = (unsigned __int8)MultiByteStr;
  if ( v11 == 2 )
  {
    v12 = _byteswap_ushort(MultiByteStr);
LABEL_20:
    if ( !GetCharWidthA(hdc, v12, v12, &Buffer) )
      goto LABEL_21;
LABEL_3:
    *a3 = Buffer;
    goto LABEL_4;
  }
  if ( v11 > 0 )
    goto LABEL_20;
LABEL_21:
  a2 = WideCharStr;
LABEL_8:
  if ( a2 == 0xFFFF )
  {
    a2 = -2;
    WideCharStr = -2;
  }
  if ( GetCharWidthW(hdc, a2, a2, &Buffer) )
    *a3 = Buffer;
  if ( v8 )
  {
    SelectObject(hdc, v10);
    DeleteObject(v9);
  }
LABEL_4:
  *a3 -= a5;
}

```

## disassembly

```asm
0x18003b4e0  push    rbp
0x18003b4e2  push    rbx
0x18003b4e3  push    rsi
0x18003b4e4  push    rdi
0x18003b4e5  push    r12
0x18003b4e7  push    r13
0x18003b4e9  push    r14
0x18003b4eb  push    r15
0x18003b4ed  lea     rbp, [rsp-0Fh]
0x18003b4f2  sub     rsp, 0D8h
0x18003b4f9  mov     rax, cs:__security_cookie
0x18003b500  xor     rax, rsp
0x18003b503  mov     [rbp+47h+var_50], rax
0x18003b507  xor     r13d, r13d
0x18003b50a  mov     [rsp+110h+WideCharStr], dx
0x18003b50f  mov     [rsp+110h+Buffer], r13d
0x18003b514  mov     edi, r9d
0x18003b517  mov     [r8], r13w
0x18003b51b  mov     rbx, r8
0x18003b51e  mov     rsi, rcx
0x18003b521  cmp     r9d, 2Ah ; '*'
0x18003b525  jnz     short loc_18003B56F
0x18003b527  movzx   edx, dx; iFirst
0x18003b52a  lea     r9, [rsp+110h+Buffer]; lpBuffer
0x18003b52f  mov     r8d, edx; iLast
0x18003b532  call    cs:__imp_GetCharWidthA
0x18003b538  test    eax, eax
0x18003b53a  jz      loc_18003B5EA
0x18003b540  movzx   eax, word ptr [rsp+110h+Buffer]
0x18003b545  mov     [rbx], ax
0x18003b548  movzx   eax, [rbp+47h+arg_20]
0x18003b54c  sub     [rbx], ax
0x18003b54f  mov     rcx, [rbp+47h+var_50]
0x18003b553  xor     rcx, rsp; StackCookie
0x18003b556  call    __security_check_cookie
0x18003b55b  add     rsp, 0D8h
0x18003b562  pop     r15
0x18003b564  pop     r14
0x18003b566  pop     r13
0x18003b568  pop     r12
0x18003b56a  pop     rdi
0x18003b56b  pop     rsi
0x18003b56c  pop     rbx
0x18003b56d  pop     rbp
0x18003b56e  retn
0x18003b56f  cmp     dx, 7Fh
0x18003b573  jbe     short loc_18003B527
0x18003b575  mov     eax, 20ACh
0x18003b57a  mov     r14d, r13d
0x18003b57d  mov     r15, r13
0x18003b580  mov     r12, r13
0x18003b583  cmp     dx, ax
0x18003b586  jz      loc_18003B71B
0x18003b58c  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18003b593  jz      loc_18003B749
0x18003b599  mov     eax, 0FFFFh
0x18003b59e  cmp     dx, ax
0x18003b5a1  jz      loc_18003B789
0x18003b5a7  movzx   edx, dx; iFirst
0x18003b5aa  lea     r9, [rsp+110h+Buffer]; lpBuffer
0x18003b5af  mov     r8d, edx; iLast
0x18003b5b2  mov     rcx, rsi; hdc
0x18003b5b5  call    cs:__imp_GetCharWidthW
0x18003b5bb  test    eax, eax
0x18003b5bd  jz      short loc_18003B5C7
0x18003b5bf  movzx   eax, word ptr [rsp+110h+Buffer]
0x18003b5c4  mov     [rbx], ax
0x18003b5c7  test    r14d, r14d
0x18003b5ca  jz      loc_18003B548
0x18003b5d0  mov     rdx, r12; h
0x18003b5d3  mov     rcx, rsi; hdc
0x18003b5d6  call    cs:__imp_SelectObject
0x18003b5dc  mov     rcx, r15; ho
0x18003b5df  call    cs:__imp_DeleteObject
0x18003b5e5  jmp     loc_18003B548
0x18003b5ea  movzx   edx, [rsp+110h+WideCharStr]
0x18003b5ef  jmp     short loc_18003B575
0x18003b5f1  movzx   eax, dx
0x18003b5f4  add     eax, 0FFFFFF80h
0x18003b5f7  cmp     eax, 7Fh
0x18003b5fa  jbe     short loc_18003B599
0x18003b5fc  cmp     edi, 3B6h
0x18003b602  jnz     loc_18003B768
0x18003b608  mov     edx, 4E00h; iFirst
0x18003b60d  lea     r9, [rsp+110h+Buffer]; lpBuffer
0x18003b612  mov     r8d, edx; iLast
0x18003b615  mov     rcx, rsi; hdc
0x18003b618  call    cs:__imp_GetCharWidthW
0x18003b61e  movzx   eax, word ptr [rsp+110h+Buffer]
0x18003b623  mov     [rbx], ax
0x18003b626  movzx   eax, [rsp+110h+WideCharStr]
0x18003b62b  sub     eax, 4E00h
0x18003b630  cmp     eax, 51FFh
0x18003b635  jbe     loc_18003B548
0x18003b63b  lea     rax, [rbp+47h+UsedDefaultChar]
0x18003b63f  mov     [rbp+47h+UsedDefaultChar], r13d
0x18003b643  mov     [rsp+110h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18003b648  lea     r8, [rsp+110h+WideCharStr]; lpWideCharStr
0x18003b64d  mov     [rsp+110h+lpDefaultChar], r13; lpDefaultChar
0x18003b652  lea     rax, [rbp+47h+MultiByteStr]
0x18003b656  mov     [rsp+110h+cbMultiByte], 2; cbMultiByte
0x18003b65e  mov     r9d, 1; cchWideChar
0x18003b664  xor     edx, edx; dwFlags
0x18003b666  mov     [rsp+110h+lpMultiByteStr], rax; lpMultiByteStr
0x18003b66b  mov     ecx, edi; CodePage
0x18003b66d  call    cs:__imp_WideCharToMultiByte
0x18003b673  movzx   ecx, byte ptr [rbp+47h+MultiByteStr]
0x18003b677  cmp     eax, 2
0x18003b67a  jz      loc_18003B779
0x18003b680  test    eax, eax
0x18003b682  jle     short loc_18003B6A0
0x18003b684  movzx   edx, cx; iFirst
0x18003b687  lea     r9, [rsp+110h+Buffer]; lpBuffer
0x18003b68c  mov     r8d, edx; iLast
0x18003b68f  mov     rcx, rsi; hdc
0x18003b692  call    cs:__imp_GetCharWidthA
0x18003b698  test    eax, eax
0x18003b69a  jnz     loc_18003B540
0x18003b6a0  movzx   edx, [rsp+110h+WideCharStr]
0x18003b6a5  jmp     loc_18003B599
0x18003b6aa  mov     ecx, 0Ch; i
0x18003b6af  mov     r14d, 1
0x18003b6b5  call    cs:__imp_GetStockObject
0x18003b6bb  mov     rdx, rax; h
0x18003b6be  mov     rcx, rsi; hdc
0x18003b6c1  call    cs:__imp_SelectObject
0x18003b6c7  xor     edx, edx; Val
0x18003b6c9  lea     rcx, [rbp+47h+var_B0]; void *
0x18003b6cd  mov     r8d, 5Ch ; '\'; Size
0x18003b6d3  mov     r12, rax
0x18003b6d6  call    memset_0
0x18003b6db  lea     r8, [rbp+47h+var_B0]; void *
0x18003b6df  mov     edx, 5Ch ; '\'; int
0x18003b6e4  mov     rcx, r12; void *
0x18003b6e7  call    ?GetObjectW@CW32System@@SAHPEAXH0@Z; CW32System::GetObjectW(void *,int,void *)
0x18003b6ec  cmp     cs:?_dwPlatformId@CW32System@@0KA, r14d; ulong CW32System::_dwPlatformId
0x18003b6f3  jz      short loc_18003B743
0x18003b6f5  mov     [rbp+47h+var_B0.lfOutPrecision], 9
0x18003b6f9  lea     rcx, [rbp+47h+var_B0]; struct tagLOGFONTW *
0x18003b6fd  call    ?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z; CW32System::CreateFontIndirect(tagLOGFONTW const *)
0x18003b702  mov     rdx, rax; h
0x18003b705  mov     rcx, rsi; hdc
0x18003b708  mov     r15, rax
0x18003b70b  call    cs:__imp_SelectObject
0x18003b711  movzx   edx, [rsp+110h+WideCharStr]
0x18003b716  jmp     loc_18003B58C
0x18003b71b  mov     edx, 2; index
0x18003b720  mov     rcx, rsi; hdc
0x18003b723  call    cs:__imp_GetDeviceCaps
0x18003b729  cmp     eax, 1
0x18003b72c  jnz     loc_18003B6AA
0x18003b732  mov     rcx, rsi; hdc
0x18003b735  call    ?IsEnhancedMetafileDC@CW32System@@SAHPEAUHDC__@@@Z; CW32System::IsEnhancedMetafileDC(HDC__ *)
0x18003b73a  test    eax, eax
0x18003b73c  jz      short loc_18003B711
0x18003b73e  jmp     loc_18003B6AA
0x18003b743  mov     [rbp+47h+var_B0.lfOutPrecision], 7
0x18003b747  jmp     short loc_18003B6F9
0x18003b749  cmp     cs:?_dwMajorVersion@CW32System@@2KA, 4; ulong CW32System::_dwMajorVersion
0x18003b750  jnz     loc_18003B599
0x18003b756  cmp     cs:?_dwMinorVersion@CW32System@@2KA, r13d; ulong CW32System::_dwMinorVersion
0x18003b75d  jnz     loc_18003B599
0x18003b763  jmp     loc_18003B5F1
0x18003b768  cmp     edi, 3A8h
0x18003b76e  jnz     loc_18003B599
0x18003b774  jmp     loc_18003B608
0x18003b779  movzx   eax, byte ptr [rbp+47h+MultiByteStr+1]
0x18003b77d  shl     cx, 8
0x18003b781  or      cx, ax
0x18003b784  jmp     loc_18003B684
0x18003b789  mov     edx, 0FFFEh
0x18003b78e  mov     [rsp+110h+WideCharStr], dx
0x18003b793  jmp     loc_18003B5A7
```
