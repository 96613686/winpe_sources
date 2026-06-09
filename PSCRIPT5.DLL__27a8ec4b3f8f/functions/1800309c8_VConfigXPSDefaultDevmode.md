# VConfigXPSDefaultDevmode

- ea: `0x1800309c8`
- end: `0x180030c1a`
- name: `VConfigXPSDefaultDevmode`
- size: `594`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800299d4`

## callees

- `0x1800309c8`
- `0x180030fb0`
- `0x180031044`

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
  unsigned int *KeywordMatchFeature; // rax
  unsigned int v11; // ecx
  __int64 v12; // rdx
  char *v13; // rdx
  char *v14; // r8
  int v15; // ecx
  int v16; // eax
  int v17; // ebp
  unsigned int *v18; // rax
  unsigned int v19; // ecx
  __int64 v20; // rdx
  const char *v21; // rdx
  char *v22; // r8
  int v23; // ecx
  int v24; // eax
  int v25; // eax
  int v26; // ebx
  unsigned int v27; // eax
  __int64 result; // rax
  unsigned int v29; // [rsp+40h] [rbp+8h] BYREF

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
  KeywordMatchFeature = PInternalGetKeywordMatchFeature(a1, "PageDeviceFontSubstitution", 1, &v29);
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
    v18 = PInternalGetKeywordMatchFeature(a1, "PageTrueTypeFontMode", 1, &v29);
    if ( v18 )
    {
      v19 = v18[5];
      if ( v19 < v18[13] )
      {
        v20 = *v3 + v18[14] + v18[12] * v19;
        if ( v20 )
        {
          if ( *(_DWORD *)(v20 + 4) )
          {
            v21 = (const char *)(*(unsigned int *)(v20 + 4) + *(_QWORD *)(a1 + 320));
            if ( v21 )
            {
              v17 = 1;
              if ( !strcmp(v21, "DownloadAsOutlineFont") )
              {
                *(_WORD *)(a2 + 98) = 4;
              }
              else if ( !strcmp(v21, "RenderAsBitmap") )
              {
                *(_WORD *)(a2 + 98) = 1;
              }
              else
              {
                if ( !strcmp(v21, "Automatic") || !strcmp(v21, "DownloadAsRasterFont") )
                  goto LABEL_35;
                v22 = (char *)("DownloadAsNativeTrueTypeFont" - v21);
                do
                {
                  v23 = (unsigned __int8)v22[(_QWORD)v21];
                  v24 = *(unsigned __int8 *)v21 - v23;
                  if ( v24 )
                    break;
                  ++v21;
                }
                while ( v23 );
                if ( !v24 )
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
  v25 = *(_DWORD *)(a2 + 72);
  v26 = v25 | 0x4000;
  v27 = v25 & 0xFFFFBFFF;
  if ( !v17 )
    v26 = v27;
  *(_DWORD *)(a2 + 72) = v26;
  result = DwXPSGetNupCap(a1);
  if ( !(_DWORD)result )
    *(_DWORD *)(a2 + 72) = v26 & 0xFFFFFFBF;
  return result;
}

```

## disassembly

```asm
0x1800309c8  mov     [rsp+arg_8], rbx
0x1800309cd  mov     [rsp+arg_10], rbp
0x1800309d2  push    rsi
0x1800309d3  push    rdi
0x1800309d4  push    r14
0x1800309d6  sub     rsp, 20h
0x1800309da  mov     eax, [rcx+0F4h]
0x1800309e0  lea     rbx, [rcx+148h]
0x1800309e7  mov     rdi, rdx
0x1800309ea  mov     rsi, rcx
0x1800309ed  test    eax, eax
0x1800309ef  jz      short loc_1800309F6
0x1800309f1  add     rax, [rbx]
0x1800309f4  jmp     short loc_1800309F8
0x1800309f6  xor     eax, eax
0x1800309f8  mov     ecx, [rdx+48h]
0x1800309fb  test    rax, rax
0x1800309fe  jz      short loc_180030A28
0x180030a00  bts     ecx, 0Fh
0x180030a04  mov     [rdx+48h], ecx
0x180030a07  mov     ecx, [rax+14h]
0x180030a0a  cmp     ecx, [rax+34h]
0x180030a0d  jnb     short loc_180030A2F
0x180030a0f  imul    ecx, [rax+30h]
0x180030a13  add     ecx, [rax+38h]
0x180030a16  mov     rax, [rbx]
0x180030a19  add     rax, rcx
0x180030a1c  jz      short loc_180030A2F
0x180030a1e  movzx   eax, word ptr [rax+38h]
0x180030a22  mov     [rdx+64h], ax
0x180030a26  jmp     short loc_180030A2F
0x180030a28  btr     ecx, 0Fh
0x180030a2c  mov     [rdx+48h], ecx
0x180030a2f  mov     r14d, 1
0x180030a35  lea     r9, [rsp+38h+arg_0]
0x180030a3a  mov     r8d, r14d
0x180030a3d  lea     rdx, kstrSchema_DeviceFontSub; "PageDeviceFontSubstitution"
0x180030a44  mov     rcx, rsi
0x180030a47  call    PInternalGetKeywordMatchFeature
0x180030a4c  test    rax, rax
0x180030a4f  jz      short loc_180030AAB
0x180030a51  mov     ecx, [rax+14h]
0x180030a54  cmp     ecx, [rax+34h]
0x180030a57  jnb     short loc_180030AAB
0x180030a59  imul    ecx, [rax+30h]
0x180030a5d  add     ecx, [rax+38h]
0x180030a60  mov     edx, ecx
0x180030a62  add     rdx, [rbx]
0x180030a65  jz      short loc_180030AAB
0x180030a67  cmp     dword ptr [rdx+4], 0
0x180030a6b  jz      short loc_180030AAB
0x180030a6d  mov     ecx, [rdx+4]
0x180030a70  mov     rdx, [rsi+140h]
0x180030a77  add     rdx, rcx
0x180030a7a  jz      short loc_180030AAB
0x180030a7c  lea     r8, kstrSchema_Option_On; "On"
0x180030a83  sub     r8, rdx
0x180030a86  movzx   eax, byte ptr [rdx]
0x180030a89  movzx   ecx, byte ptr [rdx+r8]
0x180030a8e  sub     eax, ecx
0x180030a90  jnz     short loc_180030A99
0x180030a92  add     rdx, r14
0x180030a95  test    ecx, ecx
0x180030a97  jnz     short loc_180030A86
0x180030a99  test    eax, eax
0x180030a9b  jnz     short loc_180030AAB
0x180030a9d  mov     word ptr [rdi+62h], 3
0x180030aa3  mov     ebp, r14d
0x180030aa6  jmp     loc_180030BDF
0x180030aab  lea     r9, [rsp+38h+arg_0]
0x180030ab0  mov     r8d, r14d
0x180030ab3  lea     rdx, kstrSchema_TrueType; "PageTrueTypeFontMode"
0x180030aba  mov     rcx, rsi
0x180030abd  xor     ebp, ebp
0x180030abf  call    PInternalGetKeywordMatchFeature
0x180030ac4  test    rax, rax
0x180030ac7  jz      loc_180030BDF
0x180030acd  mov     ecx, [rax+14h]
0x180030ad0  cmp     ecx, [rax+34h]
0x180030ad3  jnb     loc_180030BDF
0x180030ad9  imul    ecx, [rax+30h]
0x180030add  add     ecx, [rax+38h]
0x180030ae0  mov     edx, ecx
0x180030ae2  add     rdx, [rbx]
0x180030ae5  jz      loc_180030BDF
0x180030aeb  cmp     [rdx+4], ebp
0x180030aee  jz      loc_180030BDF
0x180030af4  mov     ecx, [rdx+4]
0x180030af7  mov     rdx, [rsi+140h]
0x180030afe  add     rdx, rcx
0x180030b01  jz      loc_180030BDF
0x180030b07  lea     r8, kstrSchema_TrueType_Outline; "DownloadAsOutlineFont"
0x180030b0e  mov     ebp, r14d
0x180030b11  sub     r8, rdx
0x180030b14  mov     rax, rdx
0x180030b17  movzx   ecx, byte ptr [rax]
0x180030b1a  movzx   r9d, byte ptr [rax+r8]
0x180030b1f  sub     ecx, r9d
0x180030b22  jnz     short loc_180030B2C
0x180030b24  add     rax, r14
0x180030b27  test    r9d, r9d
0x180030b2a  jnz     short loc_180030B17
0x180030b2c  test    ecx, ecx
0x180030b2e  jnz     short loc_180030B3B
0x180030b30  mov     word ptr [rdi+62h], 4
0x180030b36  jmp     loc_180030BDF
0x180030b3b  lea     r8, kstrSchema_TrueType_RenderAsBitmap; "RenderAsBitmap"
0x180030b42  mov     rax, rdx
0x180030b45  sub     r8, rdx
0x180030b48  movzx   ecx, byte ptr [rax]
0x180030b4b  movzx   r9d, byte ptr [rax+r8]
0x180030b50  sub     ecx, r9d
0x180030b53  jnz     short loc_180030B5D
0x180030b55  add     rax, r14
0x180030b58  test    r9d, r9d
0x180030b5b  jnz     short loc_180030B48
0x180030b5d  test    ecx, ecx
0x180030b5f  jnz     short loc_180030B68
0x180030b61  mov     [rdi+62h], r14w
0x180030b66  jmp     short loc_180030BDF
0x180030b68  lea     r8, kstrSchema_TrueType_Automatic; "Automatic"
0x180030b6f  mov     rax, rdx
0x180030b72  sub     r8, rdx
0x180030b75  movzx   ecx, byte ptr [rax]
0x180030b78  movzx   r9d, byte ptr [rax+r8]
0x180030b7d  sub     ecx, r9d
0x180030b80  jnz     short loc_180030B8A
0x180030b82  add     rax, r14
0x180030b85  test    r9d, r9d
0x180030b88  jnz     short loc_180030B75
0x180030b8a  test    ecx, ecx
0x180030b8c  jz      short loc_180030BD9
0x180030b8e  lea     r8, kstrSchema_TrueType_Raster; "DownloadAsRasterFont"
0x180030b95  mov     rax, rdx
0x180030b98  sub     r8, rdx
0x180030b9b  movzx   ecx, byte ptr [rax]
0x180030b9e  movzx   r9d, byte ptr [rax+r8]
0x180030ba3  sub     ecx, r9d
0x180030ba6  jnz     short loc_180030BB0
0x180030ba8  add     rax, r14
0x180030bab  test    r9d, r9d
0x180030bae  jnz     short loc_180030B9B
0x180030bb0  test    ecx, ecx
0x180030bb2  jz      short loc_180030BD9
0x180030bb4  lea     r8, kstrSchema_TrueType_NativeTT; "DownloadAsNativeTrueTypeFont"
0x180030bbb  sub     r8, rdx
0x180030bbe  movzx   eax, byte ptr [rdx]
0x180030bc1  movzx   ecx, byte ptr [rdx+r8]
0x180030bc6  sub     eax, ecx
0x180030bc8  jnz     short loc_180030BD1
0x180030bca  add     rdx, r14
0x180030bcd  test    ecx, ecx
0x180030bcf  jnz     short loc_180030BBE
0x180030bd1  test    eax, eax
0x180030bd3  jz      short loc_180030BD9
0x180030bd5  xor     ebp, ebp
0x180030bd7  jmp     short loc_180030BDF
0x180030bd9  mov     word ptr [rdi+62h], 2
0x180030bdf  mov     ebx, [rdi+48h]
0x180030be2  mov     rcx, rsi
0x180030be5  mov     eax, ebx
0x180030be7  bts     ebx, 0Eh
0x180030beb  btr     eax, 0Eh
0x180030bef  test    ebp, ebp
0x180030bf1  cmovz   ebx, eax
0x180030bf4  mov     [rdi+48h], ebx
0x180030bf7  call    DwXPSGetNupCap
0x180030bfc  test    eax, eax
0x180030bfe  jnz     short loc_180030C06
0x180030c00  and     ebx, 0FFFFFFBFh
0x180030c03  mov     [rdi+48h], ebx
0x180030c06  mov     rbx, [rsp+38h+arg_8]
0x180030c0b  mov     rbp, [rsp+38h+arg_10]
0x180030c10  add     rsp, 20h
0x180030c14  pop     r14
0x180030c16  pop     rdi
0x180030c17  pop     rsi
0x180030c18  retn
```
