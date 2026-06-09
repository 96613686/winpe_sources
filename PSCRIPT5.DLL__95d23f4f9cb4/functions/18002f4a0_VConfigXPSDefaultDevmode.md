# VConfigXPSDefaultDevmode

- ea: `0x18002f4a0`
- end: `0x18002f6f1`
- name: `VConfigXPSDefaultDevmode`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002888c`

## callees

- `0x18002f4a0`
- `0x18002fa6c`
- `0x18002fac0`

## pseudocode

```c
__int64 __fastcall VConfigXPSDefaultDevmode(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  _QWORD *v3; // rbx
  _DWORD *v6; // rax
  int v7; // ecx
  unsigned int v8; // ecx
  __int64 v9; // rax
  _DWORD *KeywordMatchFeature; // rax
  unsigned int v11; // ecx
  __int64 v12; // rdx
  char *v13; // rdx
  char *v14; // r8
  int v15; // ecx
  int v16; // eax
  int v17; // ebp
  _DWORD *v18; // rax
  unsigned int v19; // ecx
  char *v20; // r8
  int v21; // ecx
  int v22; // eax
  int v23; // eax
  int v24; // ebx
  unsigned int v25; // eax
  __int64 result; // rax
  char v27; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(unsigned int *)(a1 + 244);
  v3 = (_QWORD *)(a1 + 328);
  if ( (_DWORD)v2 )
    v6 = (_DWORD *)(*v3 + v2);
  else
    v6 = 0;
  v7 = *(_DWORD *)(a2 + 72);
  if ( v6 )
  {
    *(_DWORD *)(a2 + 72) = v7 | 0x8000;
    v8 = v6[5];
    if ( v8 < v6[13] )
    {
      v9 = v6[14] + v6[12] * v8 + *v3;
      if ( v9 )
        *(_WORD *)(a2 + 100) = *(_WORD *)(v9 + 56);
    }
  }
  else
  {
    *(_DWORD *)(a2 + 72) = v7 & 0xFFFF7FFF;
  }
  KeywordMatchFeature = (_DWORD *)PInternalGetKeywordMatchFeature(a1, "PageDeviceFontSubstitution", 1, &v27);
  if ( !KeywordMatchFeature )
    goto LABEL_19;
  v11 = KeywordMatchFeature[5];
  if ( v11 >= KeywordMatchFeature[13] )
    goto LABEL_19;
  v12 = *v3 + KeywordMatchFeature[14] + KeywordMatchFeature[12] * v11;
  if ( !v12 )
    goto LABEL_19;
  if ( !*(_DWORD *)(v12 + 4) )
    goto LABEL_19;
  v13 = (char *)(*(unsigned int *)(v12 + 4) + *(_QWORD *)(a1 + 320));
  if ( !v13 )
    goto LABEL_19;
  v14 = (char *)("On" - v13);
  do
  {
    v15 = (unsigned __int8)v14[(_QWORD)v13];
    v16 = (unsigned __int8)*v13 - v15;
    if ( v16 )
      break;
    ++v13;
  }
  while ( v15 );
  if ( !v16 )
  {
    *(_WORD *)(a2 + 98) = 3;
    v17 = 1;
  }
  else
  {
LABEL_19:
    v17 = 0;
    v18 = (_DWORD *)PInternalGetKeywordMatchFeature(a1, "PageTrueTypeFontMode", 1, &v27);
    if ( v18 )
    {
      v19 = v18[5];
      if ( v19 < v18[13] )
      {
        v13 = (char *)(*v3 + v18[14] + v18[12] * v19);
        if ( v13 )
        {
          if ( *((_DWORD *)v13 + 1) )
          {
            v13 = (char *)(*((unsigned int *)v13 + 1) + *(_QWORD *)(a1 + 320));
            if ( v13 )
            {
              v17 = 1;
              if ( !strcmp(v13, "DownloadAsOutlineFont") )
              {
                *(_WORD *)(a2 + 98) = 4;
              }
              else if ( !strcmp(v13, "RenderAsBitmap") )
              {
                *(_WORD *)(a2 + 98) = 1;
              }
              else
              {
                if ( !strcmp(v13, "Automatic") || !strcmp(v13, "DownloadAsRasterFont") )
                  goto LABEL_35;
                v20 = (char *)("DownloadAsNativeTrueTypeFont" - v13);
                do
                {
                  v21 = (unsigned __int8)v20[(_QWORD)v13];
                  v22 = (unsigned __int8)*v13 - v21;
                  if ( v22 )
                    break;
                  ++v13;
                }
                while ( v21 );
                if ( !v22 )
LABEL_35:
                  *(_WORD *)(a2 + 98) = 2;
                else
                  v17 = 0;
              }
            }
          }
        }
      }
    }
  }
  v23 = *(_DWORD *)(a2 + 72);
  v24 = v23 | 0x4000;
  v25 = v23 & 0xFFFFBFFF;
  if ( !v17 )
    v24 = v25;
  *(_DWORD *)(a2 + 72) = v24;
  result = DwXPSGetNupCap(a1, v13);
  if ( !(_DWORD)result )
    *(_DWORD *)(a2 + 72) = v24 & 0xFFFFFFBF;
  return result;
}

```

## disassembly

```asm
0x18002f4a0  mov     [rsp+arg_8], rbx
0x18002f4a5  mov     [rsp+arg_10], rbp
0x18002f4aa  push    rsi
0x18002f4ab  push    rdi
0x18002f4ac  push    r14
0x18002f4ae  sub     rsp, 20h
0x18002f4b2  mov     eax, [rcx+0F4h]
0x18002f4b8  lea     rbx, [rcx+148h]
0x18002f4bf  mov     rdi, rdx
0x18002f4c2  mov     rsi, rcx
0x18002f4c5  test    eax, eax
0x18002f4c7  jz      short loc_18002F4CE
0x18002f4c9  add     rax, [rbx]
0x18002f4cc  jmp     short loc_18002F4D0
0x18002f4ce  xor     eax, eax
0x18002f4d0  mov     ecx, [rdx+48h]
0x18002f4d3  test    rax, rax
0x18002f4d6  jz      short loc_18002F500
0x18002f4d8  bts     ecx, 0Fh
0x18002f4dc  mov     [rdx+48h], ecx
0x18002f4df  mov     ecx, [rax+14h]
0x18002f4e2  cmp     ecx, [rax+34h]
0x18002f4e5  jnb     short loc_18002F507
0x18002f4e7  imul    ecx, [rax+30h]
0x18002f4eb  add     ecx, [rax+38h]
0x18002f4ee  mov     rax, [rbx]
0x18002f4f1  add     rax, rcx
0x18002f4f4  jz      short loc_18002F507
0x18002f4f6  movzx   eax, word ptr [rax+38h]
0x18002f4fa  mov     [rdx+64h], ax
0x18002f4fe  jmp     short loc_18002F507
0x18002f500  btr     ecx, 0Fh
0x18002f504  mov     [rdx+48h], ecx
0x18002f507  mov     r14d, 1
0x18002f50d  lea     r9, [rsp+38h+arg_0]
0x18002f512  mov     r8d, r14d
0x18002f515  lea     rdx, kstrSchema_DeviceFontSub; "PageDeviceFontSubstitution"
0x18002f51c  mov     rcx, rsi
0x18002f51f  call    PInternalGetKeywordMatchFeature
0x18002f524  test    rax, rax
0x18002f527  jz      short loc_18002F583
0x18002f529  mov     ecx, [rax+14h]
0x18002f52c  cmp     ecx, [rax+34h]
0x18002f52f  jnb     short loc_18002F583
0x18002f531  imul    ecx, [rax+30h]
0x18002f535  add     ecx, [rax+38h]
0x18002f538  mov     edx, ecx
0x18002f53a  add     rdx, [rbx]
0x18002f53d  jz      short loc_18002F583
0x18002f53f  cmp     dword ptr [rdx+4], 0
0x18002f543  jz      short loc_18002F583
0x18002f545  mov     ecx, [rdx+4]
0x18002f548  mov     rdx, [rsi+140h]
0x18002f54f  add     rdx, rcx
0x18002f552  jz      short loc_18002F583
0x18002f554  lea     r8, kstrSchema_Option_On; "On"
0x18002f55b  sub     r8, rdx
0x18002f55e  movzx   eax, byte ptr [rdx]
0x18002f561  movzx   ecx, byte ptr [rdx+r8]
0x18002f566  sub     eax, ecx
0x18002f568  jnz     short loc_18002F571
0x18002f56a  add     rdx, r14
0x18002f56d  test    ecx, ecx
0x18002f56f  jnz     short loc_18002F55E
0x18002f571  test    eax, eax
0x18002f573  jnz     short loc_18002F583
0x18002f575  mov     word ptr [rdi+62h], 3
0x18002f57b  mov     ebp, r14d
0x18002f57e  jmp     loc_18002F6B7
0x18002f583  lea     r9, [rsp+38h+arg_0]
0x18002f588  mov     r8d, r14d
0x18002f58b  lea     rdx, kstrSchema_TrueType; "PageTrueTypeFontMode"
0x18002f592  mov     rcx, rsi
0x18002f595  xor     ebp, ebp
0x18002f597  call    PInternalGetKeywordMatchFeature
0x18002f59c  test    rax, rax
0x18002f59f  jz      loc_18002F6B7
0x18002f5a5  mov     ecx, [rax+14h]
0x18002f5a8  cmp     ecx, [rax+34h]
0x18002f5ab  jnb     loc_18002F6B7
0x18002f5b1  imul    ecx, [rax+30h]
0x18002f5b5  add     ecx, [rax+38h]
0x18002f5b8  mov     edx, ecx
0x18002f5ba  add     rdx, [rbx]
0x18002f5bd  jz      loc_18002F6B7
0x18002f5c3  cmp     [rdx+4], ebp
0x18002f5c6  jz      loc_18002F6B7
0x18002f5cc  mov     ecx, [rdx+4]
0x18002f5cf  mov     rdx, [rsi+140h]
0x18002f5d6  add     rdx, rcx
0x18002f5d9  jz      loc_18002F6B7
0x18002f5df  lea     r8, kstrSchema_TrueType_Outline; "DownloadAsOutlineFont"
0x18002f5e6  mov     ebp, r14d
0x18002f5e9  sub     r8, rdx
0x18002f5ec  mov     rax, rdx
0x18002f5ef  movzx   ecx, byte ptr [rax]
0x18002f5f2  movzx   r9d, byte ptr [rax+r8]
0x18002f5f7  sub     ecx, r9d
0x18002f5fa  jnz     short loc_18002F604
0x18002f5fc  add     rax, r14
0x18002f5ff  test    r9d, r9d
0x18002f602  jnz     short loc_18002F5EF
0x18002f604  test    ecx, ecx
0x18002f606  jnz     short loc_18002F613
0x18002f608  mov     word ptr [rdi+62h], 4
0x18002f60e  jmp     loc_18002F6B7
0x18002f613  lea     r8, kstrSchema_TrueType_RenderAsBitmap; "RenderAsBitmap"
0x18002f61a  mov     rax, rdx
0x18002f61d  sub     r8, rdx
0x18002f620  movzx   ecx, byte ptr [rax]
0x18002f623  movzx   r9d, byte ptr [rax+r8]
0x18002f628  sub     ecx, r9d
0x18002f62b  jnz     short loc_18002F635
0x18002f62d  add     rax, r14
0x18002f630  test    r9d, r9d
0x18002f633  jnz     short loc_18002F620
0x18002f635  test    ecx, ecx
0x18002f637  jnz     short loc_18002F640
0x18002f639  mov     [rdi+62h], r14w
0x18002f63e  jmp     short loc_18002F6B7
0x18002f640  lea     r8, kstrSchema_TrueType_Automatic; "Automatic"
0x18002f647  mov     rax, rdx
0x18002f64a  sub     r8, rdx
0x18002f64d  movzx   ecx, byte ptr [rax]
0x18002f650  movzx   r9d, byte ptr [rax+r8]
0x18002f655  sub     ecx, r9d
0x18002f658  jnz     short loc_18002F662
0x18002f65a  add     rax, r14
0x18002f65d  test    r9d, r9d
0x18002f660  jnz     short loc_18002F64D
0x18002f662  test    ecx, ecx
0x18002f664  jz      short loc_18002F6B1
0x18002f666  lea     r8, kstrSchema_TrueType_Raster; "DownloadAsRasterFont"
0x18002f66d  mov     rax, rdx
0x18002f670  sub     r8, rdx
0x18002f673  movzx   ecx, byte ptr [rax]
0x18002f676  movzx   r9d, byte ptr [rax+r8]
0x18002f67b  sub     ecx, r9d
0x18002f67e  jnz     short loc_18002F688
0x18002f680  add     rax, r14
0x18002f683  test    r9d, r9d
0x18002f686  jnz     short loc_18002F673
0x18002f688  test    ecx, ecx
0x18002f68a  jz      short loc_18002F6B1
0x18002f68c  lea     r8, kstrSchema_TrueType_NativeTT; "DownloadAsNativeTrueTypeFont"
0x18002f693  sub     r8, rdx
0x18002f696  movzx   eax, byte ptr [rdx]
0x18002f699  movzx   ecx, byte ptr [rdx+r8]
0x18002f69e  sub     eax, ecx
0x18002f6a0  jnz     short loc_18002F6A9
0x18002f6a2  add     rdx, r14
0x18002f6a5  test    ecx, ecx
0x18002f6a7  jnz     short loc_18002F696
0x18002f6a9  test    eax, eax
0x18002f6ab  jz      short loc_18002F6B1
0x18002f6ad  xor     ebp, ebp
0x18002f6af  jmp     short loc_18002F6B7
0x18002f6b1  mov     word ptr [rdi+62h], 2
0x18002f6b7  mov     ebx, [rdi+48h]
0x18002f6ba  mov     rcx, rsi
0x18002f6bd  mov     eax, ebx
0x18002f6bf  bts     ebx, 0Eh
0x18002f6c3  btr     eax, 0Eh
0x18002f6c7  test    ebp, ebp
0x18002f6c9  cmovz   ebx, eax
0x18002f6cc  mov     [rdi+48h], ebx
0x18002f6cf  call    DwXPSGetNupCap
0x18002f6d4  test    eax, eax
0x18002f6d6  jnz     short loc_18002F6DE
0x18002f6d8  and     ebx, 0FFFFFFBFh
0x18002f6db  mov     [rdi+48h], ebx
0x18002f6de  mov     rbx, [rsp+38h+arg_8]
0x18002f6e3  mov     rbp, [rsp+38h+arg_10]
0x18002f6e8  add     rsp, 20h
0x18002f6ec  pop     r14
0x18002f6ee  pop     rdi
0x18002f6ef  pop     rsi
0x18002f6f0  retn
```
