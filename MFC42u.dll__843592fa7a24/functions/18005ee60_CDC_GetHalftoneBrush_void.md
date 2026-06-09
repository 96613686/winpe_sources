# CDC::GetHalftoneBrush(void)

- ea: `0x18005ee60`
- end: `0x18005ef11`
- name: `?GetHalftoneBrush@CDC@@SAPEAVCBrush@@XZ`
- size: `177`
- prototype: `struct CBrush *(void)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18004aef0`
- `0x180052950`
- `0x18005eb20`
- `0x180064d90`

## callees

- `0x180016330`
- `0x180017020`
- `0x18001dbd0`
- `0x18005ee60`
- `0x1800d1fe0`

## import_xrefs

- `GDI32!CreatePatternBrush` at `0x18005eed2`
- `GDI32!CreatePatternBrush` at `0x18005eed2`
- `GDI32!CreateBitmap` at `0x18005eec1`
- `GDI32!CreateBitmap` at `0x18005eec1`
- `GDI32!DeleteObject` at `0x18005eee2`
- `GDI32!DeleteObject` at `0x18005eee2`

## pseudocode

```c
struct CBrush *CDC::GetHalftoneBrush(void)
{
  __int64 v0; // r9
  HBITMAP Bitmap; // rax
  HBITMAP v2; // rbx
  _WORD Bits[8]; // [rsp+30h] [rbp-28h] BYREF

  AfxLockGlobals(8);
  if ( !_afxHalftoneBrush )
  {
    v0 = 0;
    do
    {
      Bits[v0] = 21845 << (v0 & 1);
      v0 = (unsigned int)(v0 + 1);
    }
    while ( (int)v0 < 8 );
    Bitmap = CreateBitmap(8, 8, 1u, 1u, Bits);
    v2 = Bitmap;
    if ( Bitmap )
    {
      _afxHalftoneBrush = CreatePatternBrush(Bitmap);
      DeleteObject(v2);
    }
  }
  AfxUnlockGlobals(8);
  return CGdiObject::FromHandle(_afxHalftoneBrush);
}

```

## disassembly

```asm
0x18005ee60  push    rbx
0x18005ee62  sub     rsp, 50h
0x18005ee66  mov     rax, cs:__security_cookie
0x18005ee6d  xor     rax, rsp
0x18005ee70  mov     [rsp+58h+var_18], rax
0x18005ee75  mov     ecx, 8; int
0x18005ee7a  call    ?AfxLockGlobals@@YAXH@Z; AfxLockGlobals(int)
0x18005ee7f  cmp     cs:?_afxHalftoneBrush@@3PEAUHBRUSH__@@EA, 0; HBRUSH__ * _afxHalftoneBrush
0x18005ee87  jnz     short loc_18005EEE8
0x18005ee89  xor     r9d, r9d
0x18005ee8c  lea     r8d, [r9+1]; nPlanes
0x18005ee90  mov     ecx, r9d
0x18005ee93  mov     edx, 5555h
0x18005ee98  and     ecx, r8d
0x18005ee9b  shl     dx, cl
0x18005ee9e  mov     [rsp+r9*2+58h+Bits], dx
0x18005eea4  add     r9d, r8d
0x18005eea7  cmp     r9d, 8
0x18005eeab  jl      short loc_18005EE90
0x18005eead  mov     edx, 8; nHeight
0x18005eeb2  lea     rax, [rsp+58h+Bits]
0x18005eeb7  mov     ecx, edx; nWidth
0x18005eeb9  mov     [rsp+58h+lpBits], rax; lpBits
0x18005eebe  mov     r9d, r8d; nBitCount
0x18005eec1  call    cs:__imp_CreateBitmap
0x18005eec7  mov     rbx, rax
0x18005eeca  test    rax, rax
0x18005eecd  jz      short loc_18005EEE8
0x18005eecf  mov     rcx, rax; hbm
0x18005eed2  call    cs:__imp_CreatePatternBrush
0x18005eed8  mov     rcx, rbx; ho
0x18005eedb  mov     cs:?_afxHalftoneBrush@@3PEAUHBRUSH__@@EA, rax; HBRUSH__ * _afxHalftoneBrush
0x18005eee2  call    cs:__imp_DeleteObject
0x18005eee8  mov     ecx, 8; int
0x18005eeed  call    ?AfxUnlockGlobals@@YAXH@Z; AfxUnlockGlobals(int)
0x18005eef2  mov     rcx, cs:?_afxHalftoneBrush@@3PEAUHBRUSH__@@EA; void *
0x18005eef9  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18005eefe  mov     rcx, [rsp+58h+var_18]
0x18005ef03  xor     rcx, rsp; StackCookie
0x18005ef06  call    __security_check_cookie
0x18005ef0b  add     rsp, 50h
0x18005ef0f  pop     rbx
0x18005ef10  retn
```
