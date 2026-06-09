# CBitmap::CopyPixelsHelper(MilPixelFormat::Enum,uint,uint,uint,uint,uchar *,uint,uint,uchar *)

- ea: `0x1800199d8`
- end: `0x180019afc`
- name: `?CopyPixelsHelper@CBitmap@@AEAAJW4Enum@MilPixelFormat@@IIIIPEAEII1@Z`
- size: `292`
- prototype: `int __high(enum MilPixelFormat::Enum, unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001a730`

## callees

- `0x180006cc8`
- `0x1800171c4`
- `0x1800199d8`
- `0x180019b04`
- `0x180019b64`
- `0x180032dc1`

## pseudocode

```c
__int64 __fastcall CBitmap::CopyPixelsHelper(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        void *Src,
        unsigned int a8,
        int a9,
        __int64 a10)
{
  unsigned int v11; // esi
  unsigned int v12; // ebp
  unsigned __int8 PixelFormatSize; // al
  int v14; // eax
  int v15; // ebx
  int v16; // ecx
  unsigned int v17; // r15d
  unsigned int v18; // ebp
  unsigned int v19; // r14d
  __int64 v20; // r12
  char *v21; // rsi
  unsigned int Size; // [rsp+60h] [rbp+8h] BYREF
  int Size_4; // [rsp+64h] [rbp+Ch]

  Size_4 = HIDWORD(a1);
  Size = 0;
  v11 = a3;
  v12 = a2;
  PixelFormatSize = GetPixelFormatSize((unsigned int)a2, a2, a3);
  v14 = HrCalcByteAlignedScanlineStride(v11, PixelFormatSize, &Size);
  v15 = v14;
  if ( v14 < 0 || (v14 = HrCheckBufferSize(v12, a5, v11, a4, a6), v15 = v14, v14 < 0) )
  {
    if ( g_doStackCaptures )
    {
      v16 = v14;
LABEL_11:
      DoStackCapture(v16);
    }
  }
  else
  {
    v17 = a8;
    v15 = HrCheckBufferSize(v12, a8, v11, a4, a9);
    if ( v15 < 0 )
    {
      if ( !g_doStackCaptures )
        return (unsigned int)v15;
      goto LABEL_10;
    }
    if ( Size <= v17 )
    {
      v18 = 0;
      v19 = 0;
      if ( a4 )
      {
        v20 = a5;
        v21 = (char *)Src;
        do
        {
          memcpy_0((void *)(a10 + v18), v21, Size);
          v18 += v17;
          v21 += v20;
          ++v19;
        }
        while ( v19 < a4 );
      }
    }
    else
    {
      v15 = -2147024809;
      if ( g_doStackCaptures )
      {
LABEL_10:
        v16 = v15;
        goto LABEL_11;
      }
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800199d8  mov     rax, rsp
0x1800199db  mov     [rax+10h], rbx
0x1800199df  mov     [rax+18h], rbp
0x1800199e3  mov     [rax+8], rcx
0x1800199e7  push    rsi
0x1800199e8  push    rdi
0x1800199e9  push    r12
0x1800199eb  push    r14
0x1800199ed  push    r15
0x1800199ef  sub     rsp, 30h
0x1800199f3  xor     r12d, r12d
0x1800199f6  mov     ecx, edx
0x1800199f8  mov     [rax+8], r12d
0x1800199fc  mov     edi, r9d
0x1800199ff  mov     esi, r8d
0x180019a02  mov     ebp, edx
0x180019a04  call    ?GetPixelFormatSize@@YAEW4Enum@MilPixelFormat@@@Z; GetPixelFormatSize(MilPixelFormat::Enum)
0x180019a09  movzx   edx, al; unsigned int
0x180019a0c  lea     r8, [rsp+58h+Size]; unsigned int *
0x180019a11  mov     ecx, esi; unsigned int
0x180019a13  call    ?HrCalcByteAlignedScanlineStride@@YAJIIAEAI@Z; HrCalcByteAlignedScanlineStride(uint,uint,uint &)
0x180019a18  mov     ebx, eax
0x180019a1a  test    eax, eax
0x180019a1c  jns     short loc_180019A2F
0x180019a1e  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180019a25  jz      loc_180019AE3
0x180019a2b  mov     ecx, eax
0x180019a2d  jmp     short loc_180019A9D
0x180019a2f  mov     eax, [rsp+58h+arg_28]
0x180019a36  mov     r9d, edi
0x180019a39  mov     edx, [rsp+58h+arg_20]
0x180019a40  mov     r8d, esi
0x180019a43  mov     ecx, ebp
0x180019a45  mov     [rsp+58h+var_38], eax
0x180019a49  call    ?HrCheckBufferSize@@YAJW4Enum@MilPixelFormat@@IIII@Z; HrCheckBufferSize(MilPixelFormat::Enum,uint,uint,uint,uint)
0x180019a4e  mov     ebx, eax
0x180019a50  test    eax, eax
0x180019a52  js      short loc_180019A1E
0x180019a54  mov     eax, [rsp+58h+arg_40]
0x180019a5b  mov     r9d, edi
0x180019a5e  mov     r15d, [rsp+58h+arg_38]
0x180019a66  mov     r8d, esi
0x180019a69  mov     edx, r15d
0x180019a6c  mov     [rsp+58h+var_38], eax
0x180019a70  mov     ecx, ebp
0x180019a72  call    ?HrCheckBufferSize@@YAJW4Enum@MilPixelFormat@@IIII@Z; HrCheckBufferSize(MilPixelFormat::Enum,uint,uint,uint,uint)
0x180019a77  mov     ebx, eax
0x180019a79  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180019a7f  test    ebx, ebx
0x180019a81  jns     short loc_180019A8B
0x180019a83  test    eax, eax
0x180019a85  jnz     short loc_180019A9B
0x180019a87  test    ebx, ebx
0x180019a89  js      short loc_180019AE3
0x180019a8b  cmp     dword ptr [rsp+58h+Size], r15d
0x180019a90  jbe     short loc_180019AA4
0x180019a92  mov     ebx, 80070057h
0x180019a97  test    eax, eax
0x180019a99  jz      short loc_180019AE3
0x180019a9b  mov     ecx, ebx; int
0x180019a9d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180019aa2  jmp     short loc_180019AE3
0x180019aa4  mov     ebp, r12d
0x180019aa7  mov     r14d, r12d
0x180019aaa  test    edi, edi
0x180019aac  jz      short loc_180019AE3
0x180019aae  mov     r12d, [rsp+58h+arg_20]
0x180019ab6  mov     rsi, [rsp+58h+Src]
0x180019abe  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x180019ac3  mov     rdx, rsi; Src
0x180019ac6  mov     ecx, ebp
0x180019ac8  add     rcx, [rsp+58h+arg_48]; void *
0x180019ad0  call    memcpy_0
0x180019ad5  add     ebp, r15d
0x180019ad8  add     rsi, r12
0x180019adb  inc     r14d
0x180019ade  cmp     r14d, edi
0x180019ae1  jb      short loc_180019ABE
0x180019ae3  mov     rbp, [rsp+58h+arg_10]
0x180019ae8  mov     eax, ebx
0x180019aea  mov     rbx, [rsp+58h+arg_8]
0x180019aef  add     rsp, 30h
0x180019af3  pop     r15
0x180019af5  pop     r14
0x180019af7  pop     r12
0x180019af9  pop     rdi
0x180019afa  pop     rsi
0x180019afb  retn
```
