# GEL::GpCustomLineCapBuilder::CreateCustomLineCap(float,GEL::PenLineCap const *)

- ea: `0x18012ed2c`
- end: `0x18012ee0e`
- name: `?CreateCustomLineCap@GpCustomLineCapBuilder@GEL@@QEBA?AV?$TGpHolder@VGpCustomLineCap@Gdiplus@@@GDIPlus@ARC@@MPEBW4PenLineCap@2@@Z`
- size: `226`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18012ebd8`
- `0x18012ec78`
- `0x1801ce1dc`
- `0x1801ce3d8`

## callees

- `0x18007f754`
- `0x18012ed2c`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18012edcc`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18012edcc`
- `gdiplus!GdipSetCustomLineCapStrokeCaps` at `0x18012ede8`
- `gdiplus!GdipSetCustomLineCapStrokeCaps` at `0x18012ede8`
- `gdiplus!GdipCreateCustomLineCap` at `0x18012ed78`
- `gdiplus!GdipCreateCustomLineCap` at `0x18012ed99`
- `gdiplus!GdipCreateCustomLineCap` at `0x18012ed78`
- `gdiplus!GdipCreateCustomLineCap` at `0x18012ed99`

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
0x18012ed2c  mov     rax, rsp
0x18012ed2f  mov     [rax+8], rbx
0x18012ed33  mov     [rax+18h], rsi
0x18012ed37  mov     [rax+10h], rdx
0x18012ed3b  push    rdi
0x18012ed3c  sub     rsp, 40h
0x18012ed40  mov     rsi, r9
0x18012ed43  mov     rdi, rdx
0x18012ed46  xor     ebx, ebx
0x18012ed48  mov     [rax-18h], ebx
0x18012ed4b  mov     [rdx], rbx
0x18012ed4e  mov     dword ptr [rax-18h], 1
0x18012ed55  mov     rax, [rcx+8]
0x18012ed59  test    rax, rax
0x18012ed5c  jz      loc_18012EDFB
0x18012ed62  test    r9, r9
0x18012ed65  jnz     short loc_18012ED86
0x18012ed67  mov     [rsp+48h+var_28], rdx
0x18012ed6c  movaps  xmm3, xmm2
0x18012ed6f  xor     edx, edx
0x18012ed71  lea     r8d, [r9+2]
0x18012ed75  mov     rcx, rax
0x18012ed78  call    cs:__imp_GdipCreateCustomLineCap
0x18012ed7e  mov     r9d, 248C091h
0x18012ed84  jmp     short loc_18012EDF4
0x18012ed86  mov     [rsp+48h+var_28], rdi
0x18012ed8b  movaps  xmm3, xmm2
0x18012ed8e  mov     r8d, 2
0x18012ed94  mov     rdx, rax
0x18012ed97  xor     ecx, ecx
0x18012ed99  call    cs:__imp_GdipCreateCustomLineCap
0x18012ed9f  mov     r9d, 248C092h
0x18012eda5  mov     ecx, eax
0x18012eda7  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012edac  movzx   ecx, byte ptr [rsi]
0x18012edaf  test    ecx, ecx
0x18012edb1  jz      short loc_18012EDDB
0x18012edb3  sub     ecx, 1
0x18012edb6  jz      short loc_18012EDD4
0x18012edb8  sub     ecx, 1
0x18012edbb  jz      short loc_18012EDE0
0x18012edbd  cmp     ecx, 1
0x18012edc0  mov     ecx, 3C5608h
0x18012edc5  jnz     short loc_18012EDCC
0x18012edc7  mov     ecx, 3C5607h
0x18012edcc  call    cs:__imp_MsoShipAssertTagProc
0x18012edd2  jmp     short loc_18012EDE0
0x18012edd4  mov     ebx, 1
0x18012edd9  jmp     short loc_18012EDE0
0x18012eddb  mov     ebx, 2
0x18012ede0  mov     r8d, ebx
0x18012ede3  mov     edx, ebx
0x18012ede5  mov     rcx, [rdi]
0x18012ede8  call    cs:__imp_GdipSetCustomLineCapStrokeCaps
0x18012edee  mov     r9d, 248C093h
0x18012edf4  mov     ecx, eax
0x18012edf6  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012edfb  mov     rax, rdi
0x18012edfe  mov     rbx, [rsp+48h+arg_0]
0x18012ee03  mov     rsi, [rsp+48h+arg_10]
0x18012ee08  add     rsp, 40h
0x18012ee0c  pop     rdi
0x18012ee0d  retn
```
