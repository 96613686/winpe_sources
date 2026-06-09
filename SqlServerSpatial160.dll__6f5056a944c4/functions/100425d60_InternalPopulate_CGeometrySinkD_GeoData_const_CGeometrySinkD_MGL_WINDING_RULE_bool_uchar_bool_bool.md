# InternalPopulate<CGeometrySinkD>(GeoData const &,CGeometrySinkD *,MGL_WINDING_RULE,bool,uchar,bool,bool)

- ea: `0x100425d60`
- end: `0x100425eb1`
- name: `??$InternalPopulate@VCGeometrySinkD@@@@YAJAEBUGeoData@@PEAVCGeometrySinkD@@W4MGL_WINDING_RULE@@_NE33@Z`
- size: `337`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned __int8, char, char, char)`
- caller_count: `41`
- callee_count: `3`
- tags: ``

## callers

- `0x10040db80`
- `0x10040dc20`
- `0x10040ee80`
- `0x1004102d0`
- `0x100411400`
- `0x100413da0`
- `0x100413e50`
- `0x100414ae0`
- `0x100415550`
- `0x100416110`
- `0x1004162a0`
- `0x100416a80`
- `0x100416de0`
- `0x100417030`
- `0x100417640`
- `0x100417750`
- `0x1004187a0`
- `0x100418d90`
- `0x1004190d0`
- `0x100419770`
- `0x100419a00`
- `0x100419bd0`
- `0x100419ef0`
- `0x10041a1c0`
- `0x10041a490`
- `0x10041a990`
- `0x10041aca0`
- `0x10041bd30`
- `0x10041c160`
- `0x10041c2d0`
- `0x10041c400`
- `0x10041c700`
- `0x10041d5a0`
- `0x10041d6b0`
- `0x10041d8c0`
- `0x1004201a0`
- `0x100422970`
- `0x100423450`
- `0x100428230`
- `0x1004284a0`
- `0x100428800`

## callees

- `0x100422820`
- `0x100425810`
- `0x100425d60`

## pseudocode

```c
__int64 __fastcall InternalPopulate<CGeometrySinkD>(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int8 a4,
        char a5,
        char a6,
        char a7)
{
  __int64 result; // rax
  int v11; // ebx
  char v12; // bp
  int ShapeOfGeometry; // esi
  int v14[10]; // [rsp+40h] [rbp-28h] BYREF

  result = 0;
  v11 = 0;
  v14[0] = 0;
  if ( !a6 )
  {
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL))(a2, a3, 0);
    if ( (int)result < 0 )
      goto LABEL_20;
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 48) + 8LL) == 11 )
  {
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 8LL))(a2, 6);
    if ( (int)result < 0 )
      goto LABEL_20;
  }
  v12 = a6 && a7 && *(_BYTE *)(*(_QWORD *)(a1 + 48) + 8LL) == 7;
  if ( *(int *)(a1 + 56) > 0 )
  {
    do
    {
      if ( v11 == -1 )
        break;
      if ( *(_BYTE *)(*(_QWORD *)(a1 + 48) + 12LL * v11 + 8) == 7 )
      {
        ShapeOfGeometry = v11;
      }
      else
      {
        ShapeOfGeometry = GeoData::IndexOfLastShapeOfGeometry((GeoData *)a1, v11);
        result = PopulateShapes<CMultipleUnionD>(a1, a2, v11, ShapeOfGeometry, a5, v14, v12);
        if ( (int)result < 0 )
          goto LABEL_20;
      }
      v11 = ShapeOfGeometry + 1;
    }
    while ( ShapeOfGeometry + 1 < *(_DWORD *)(a1 + 56) );
  }
  if ( !a6 )
  {
    result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, a4);
    if ( (int)result < 0 )
LABEL_20:
      _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x100425d60  mov     [rsp+arg_18], rbx
0x100425d65  push    rdi
0x100425d66  push    r13
0x100425d68  push    r14
0x100425d6a  sub     rsp, 50h
0x100425d6e  xor     eax, eax
0x100425d70  movzx   r13d, r9b
0x100425d74  mov     r11d, r8d
0x100425d77  mov     r14, rdx
0x100425d7a  mov     rdi, rcx
0x100425d7d  mov     ebx, eax
0x100425d7f  mov     [rsp+68h+var_28], eax
0x100425d83  cmp     [rsp+68h+arg_28], al
0x100425d8a  jnz     short loc_100425DB5
0x100425d8c  mov     r10, [rdx]
0x100425d8f  mov     r8d, eax
0x100425d92  mov     edx, r11d
0x100425d95  mov     rcx, r14
0x100425d98  call    qword ptr [r10+18h]
0x100425d9c  test    eax, eax
0x100425d9e  jns     short loc_100425DB5
0x100425da0  lfence
0x100425da3  mov     rbx, [rsp+68h+arg_18]
0x100425dab  add     rsp, 50h
0x100425daf  pop     r14
0x100425db1  pop     r13
0x100425db3  pop     rdi
0x100425db4  retn
0x100425db5  mov     rcx, [rdi+30h]
0x100425db9  cmp     byte ptr [rcx+8], 0Bh
0x100425dbd  jnz     short loc_100425DD3
0x100425dbf  mov     rax, [r14]
0x100425dc2  xor     r8d, r8d
0x100425dc5  mov     rcx, r14
0x100425dc8  lea     edx, [r8+6]
0x100425dcc  call    qword ptr [rax+8]
0x100425dcf  test    eax, eax
0x100425dd1  js      short loc_100425DA0
0x100425dd3  mov     [rsp+68h+arg_0], rbp
0x100425dd8  cmp     [rsp+68h+arg_28], bl
0x100425ddf  jz      short loc_100425DF9
0x100425de1  cmp     [rsp+68h+arg_30], bl
0x100425de8  jz      short loc_100425DF9
0x100425dea  mov     rcx, [rdi+30h]
0x100425dee  cmp     byte ptr [rcx+8], 7
0x100425df2  jnz     short loc_100425DF9
0x100425df4  mov     bpl, 1
0x100425df7  jmp     short loc_100425DFC
0x100425df9  xor     bpl, bpl
0x100425dfc  mov     [rsp+68h+arg_8], rsi
0x100425e01  mov     [rsp+68h+arg_10], r12
0x100425e09  cmp     [rdi+38h], ebx
0x100425e0c  jle     short loc_100425E6F
0x100425e0e  movzx   r12d, [rsp+68h+arg_20]
0x100425e17  cmp     ebx, 0FFFFFFFFh
0x100425e1a  jz      short loc_100425E6F
0x100425e1c  movsxd  rcx, ebx
0x100425e1f  lea     rdx, [rcx+rcx*2]
0x100425e23  mov     rcx, [rdi+30h]
0x100425e27  cmp     byte ptr [rcx+rdx*4+8], 7
0x100425e2c  jz      short loc_100425E65
0x100425e2e  mov     edx, ebx; int
0x100425e30  mov     rcx, rdi; this
0x100425e33  call    ?IndexOfLastShapeOfGeometry@GeoData@@QEBAHH@Z; GeoData::IndexOfLastShapeOfGeometry(int)
0x100425e38  mov     esi, eax
0x100425e3a  mov     [rsp+68h+var_38], bpl; char
0x100425e3f  lea     rax, [rsp+68h+var_28]
0x100425e44  mov     r9d, esi; int
0x100425e47  mov     [rsp+68h+var_40], rax; int *
0x100425e4c  mov     r8d, ebx; int
0x100425e4f  mov     rdx, r14; int
0x100425e52  mov     [rsp+68h+var_48], r12b; char
0x100425e57  mov     rcx, rdi; int
0x100425e5a  call    ??$PopulateShapes@VCMultipleUnionD@@@@YAJAEBUGeoData@@PEAVCMultipleUnionD@@HHEAEAH_N@Z; PopulateShapes<CMultipleUnionD>(GeoData const &,CMultipleUnionD *,int,int,uchar,int &,bool)
0x100425e5f  test    eax, eax
0x100425e61  js      short loc_100425E8A
0x100425e63  jmp     short loc_100425E67
0x100425e65  mov     esi, ebx
0x100425e67  lea     ebx, [rsi+1]
0x100425e6a  cmp     ebx, [rdi+38h]
0x100425e6d  jl      short loc_100425E17
0x100425e6f  cmp     [rsp+68h+arg_28], 0
0x100425e77  jnz     short loc_100425E8D
0x100425e79  mov     rax, [r14]
0x100425e7c  movzx   edx, r13b
0x100425e80  mov     rcx, r14
0x100425e83  call    qword ptr [rax+48h]
0x100425e86  test    eax, eax
0x100425e88  jns     short loc_100425E8D
0x100425e8a  lfence
0x100425e8d  mov     rsi, [rsp+68h+arg_8]
0x100425e92  mov     r12, [rsp+68h+arg_10]
0x100425e9a  mov     rbp, [rsp+68h+arg_0]
0x100425e9f  mov     rbx, [rsp+68h+arg_18]
0x100425ea7  add     rsp, 50h
0x100425eab  pop     r14
0x100425ead  pop     r13
0x100425eaf  pop     rdi
0x100425eb0  retn
```
