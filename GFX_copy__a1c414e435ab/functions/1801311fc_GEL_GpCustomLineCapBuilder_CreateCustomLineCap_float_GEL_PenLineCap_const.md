# GEL::GpCustomLineCapBuilder::CreateCustomLineCap(float,GEL::PenLineCap const *)

- ea: `0x1801311fc`
- end: `0x1801312de`
- name: `?CreateCustomLineCap@GpCustomLineCapBuilder@GEL@@QEBA?AV?$TGpHolder@VGpCustomLineCap@Gdiplus@@@GDIPlus@ARC@@MPEBW4PenLineCap@2@@Z`
- size: `226`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1801310a8`
- `0x180131148`
- `0x1801c953c`
- `0x1801c9738`

## callees

- `0x180062394`
- `0x1801311fc`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18013129c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18013129c`
- `gdiplus!GdipSetCustomLineCapStrokeCaps` at `0x1801312b8`
- `gdiplus!GdipSetCustomLineCapStrokeCaps` at `0x1801312b8`
- `gdiplus!GdipCreateCustomLineCap` at `0x180131248`
- `gdiplus!GdipCreateCustomLineCap` at `0x180131269`
- `gdiplus!GdipCreateCustomLineCap` at `0x180131248`
- `gdiplus!GdipCreateCustomLineCap` at `0x180131269`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall GEL::GpCustomLineCapBuilder::CreateCustomLineCap(__int64 a1, _QWORD *a2, __int64 a3, _BYTE *a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int CustomLineCap; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rcx

  v6 = 0;
  *a2 = 0;
  v7 = *(_QWORD *)(a1 + 8);
  if ( v7 )
  {
    if ( a4 )
    {
      CustomLineCap = GdipCreateCustomLineCap(0, v7, 2);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(CustomLineCap, v13, v14, 38322322);
      if ( *a4 )
      {
        if ( *a4 == 1 )
        {
          v6 = 1;
        }
        else if ( *a4 != 2 )
        {
          v15 = 3954184;
          if ( *a4 == 3 )
            v15 = 3954183;
          MsoShipAssertTagProc(v15);
        }
      }
      else
      {
        v6 = 2;
      }
      v8 = GdipSetCustomLineCapStrokeCaps(*a2, v6, v6);
      v11 = 38322323;
    }
    else
    {
      v8 = GdipCreateCustomLineCap(v7, 0, 2);
      v11 = 38322321;
    }
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v8, v9, v10, v11);
  }
  return a2;
}

```

## disassembly

```asm
0x1801311fc  mov     rax, rsp
0x1801311ff  mov     [rax+8], rbx
0x180131203  mov     [rax+18h], rsi
0x180131207  mov     [rax+10h], rdx
0x18013120b  push    rdi
0x18013120c  sub     rsp, 40h
0x180131210  mov     rsi, r9
0x180131213  mov     rdi, rdx
0x180131216  xor     ebx, ebx
0x180131218  mov     [rax-18h], ebx
0x18013121b  mov     [rdx], rbx
0x18013121e  mov     dword ptr [rax-18h], 1
0x180131225  mov     rax, [rcx+8]
0x180131229  test    rax, rax
0x18013122c  jz      loc_1801312CB
0x180131232  test    r9, r9
0x180131235  jnz     short loc_180131256
0x180131237  mov     [rsp+48h+var_28], rdx
0x18013123c  movaps  xmm3, xmm2
0x18013123f  xor     edx, edx
0x180131241  lea     r8d, [r9+2]
0x180131245  mov     rcx, rax
0x180131248  call    cs:__imp_GdipCreateCustomLineCap
0x18013124e  mov     r9d, 248C091h
0x180131254  jmp     short loc_1801312C4
0x180131256  mov     [rsp+48h+var_28], rdi
0x18013125b  movaps  xmm3, xmm2
0x18013125e  mov     r8d, 2
0x180131264  mov     rdx, rax
0x180131267  xor     ecx, ecx
0x180131269  call    cs:__imp_GdipCreateCustomLineCap
0x18013126f  mov     r9d, 248C092h
0x180131275  mov     ecx, eax
0x180131277  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18013127c  movzx   ecx, byte ptr [rsi]
0x18013127f  test    ecx, ecx
0x180131281  jz      short loc_1801312AB
0x180131283  sub     ecx, 1
0x180131286  jz      short loc_1801312A4
0x180131288  sub     ecx, 1
0x18013128b  jz      short loc_1801312B0
0x18013128d  cmp     ecx, 1
0x180131290  mov     ecx, 3C5608h
0x180131295  jnz     short loc_18013129C
0x180131297  mov     ecx, 3C5607h
0x18013129c  call    cs:__imp_MsoShipAssertTagProc
0x1801312a2  jmp     short loc_1801312B0
0x1801312a4  mov     ebx, 1
0x1801312a9  jmp     short loc_1801312B0
0x1801312ab  mov     ebx, 2
0x1801312b0  mov     r8d, ebx
0x1801312b3  mov     edx, ebx
0x1801312b5  mov     rcx, [rdi]
0x1801312b8  call    cs:__imp_GdipSetCustomLineCapStrokeCaps
0x1801312be  mov     r9d, 248C093h
0x1801312c4  mov     ecx, eax
0x1801312c6  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801312cb  mov     rax, rdi
0x1801312ce  mov     rbx, [rsp+48h+arg_0]
0x1801312d3  mov     rsi, [rsp+48h+arg_10]
0x1801312d8  add     rsp, 40h
0x1801312dc  pop     rdi
0x1801312dd  retn
```
