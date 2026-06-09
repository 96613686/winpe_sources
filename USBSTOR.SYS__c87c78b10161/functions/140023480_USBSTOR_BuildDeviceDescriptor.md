# USBSTOR_BuildDeviceDescriptor

- ea: `0x140023480`
- end: `0x1400236b3`
- name: `USBSTOR_BuildDeviceDescriptor`
- size: `563`
- prototype: `__int64 __fastcall(__int64, _DWORD *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400232d0`

## callees

- `0x140010664`
- `0x140013a40`
- `0x140013d40`
- `0x140023480`

## pseudocode

```c
__int64 __fastcall USBSTOR_BuildDeviceDescriptor(__int64 a1, _DWORD *a2, int *a3)
{
  int v6; // ebp
  __int64 v7; // r15
  int v8; // eax
  unsigned __int8 v9; // cl
  char v10; // al
  int v11; // eax
  int v12; // edi
  size_t v13; // r8
  int v14; // eax
  size_t v15; // r8
  int v16; // edi
  size_t v17; // r8
  int v18; // edi
  size_t v19; // r8
  int v20; // edi
  int v21; // ecx
  int v22; // eax
  int v23; // edi
  int Src; // [rsp+20h] [rbp-58h] BYREF
  int v26; // [rsp+24h] [rbp-54h]
  char v27; // [rsp+28h] [rbp-50h]
  char v28; // [rsp+29h] [rbp-4Fh]
  char v29; // [rsp+2Ah] [rbp-4Eh]
  __int128 v30; // [rsp+2Bh] [rbp-4Dh]
  char v31; // [rsp+3Bh] [rbp-3Dh]
  int v32; // [rsp+3Ch] [rbp-3Ch]
  __int64 v33; // [rsp+40h] [rbp-38h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  v6 = *a3;
  v7 = *(_QWORD *)(a1 + 64);
  memset(a2, 0, (unsigned int)*a3);
  v8 = *(_DWORD *)(v7 + 64);
  v31 = 0;
  v33 = 0;
  Src = 40;
  v26 = 103;
  v30 = 0;
  if ( v8 )
    v26 = v8 + 104;
  v9 = *(_BYTE *)(v7 + 73);
  v10 = *(_BYTE *)(v7 + 72) & 0x1F;
  v32 = 7;
  v27 = v10;
  v28 = v9 & 0x7F;
  v11 = 36;
  v29 = v9 >> 7;
  if ( v6 < 36 )
    v11 = v6;
  memmove(a2, &Src, v11);
  v12 = v6 - 36;
  if ( v6 - 36 > 0 )
  {
    v13 = (unsigned int)v12;
    if ( v12 >= 36 )
      v13 = 36;
    a2[8] = v13;
    memmove(a2 + 9, (const void *)(v7 + 72), v13);
    v14 = v6 - 72;
    if ( v6 - 72 > 0 )
    {
      v15 = 8;
      if ( (unsigned __int64)v14 < 8 )
        v15 = v14;
      memmove(a2 + 18, (const void *)(v7 + 80), v15);
      v16 = v6 - 81;
      if ( v6 - 81 >= 0 )
        a2[3] = 72;
      if ( v16 > 0 )
      {
        v17 = 16;
        if ( (unsigned __int64)v16 < 0x10 )
          v17 = v16;
        memmove((char *)a2 + 81, (const void *)(v7 + 88), v17);
        v18 = v6 - 98;
        if ( v6 - 98 >= 0 )
          a2[4] = 81;
        if ( v18 > 0 )
        {
          v19 = 4;
          if ( (unsigned __int64)v18 < 4 )
            v19 = v18;
          memmove((char *)a2 + 98, (const void *)(v7 + 104), v19);
          v20 = v6 - 103;
          if ( v6 - 103 >= 0 )
            a2[5] = 98;
          a2[6] = 0;
          if ( v20 > 0 )
          {
            v21 = *(_DWORD *)(v7 + 64);
            if ( v21 )
            {
              v22 = v6 - 103;
              if ( v20 >= v21 )
                v22 = *(_DWORD *)(v7 + 64);
              memmove((char *)a2 + 103, (const void *)(v7 + 108), v22);
              v23 = v20 - *(_DWORD *)(v7 + 64) - 1;
              if ( v23 >= 0 )
              {
                a2[6] = 103;
                *a3 = v6 - v23;
              }
            }
            else
            {
              *a3 = 103;
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140023480  mov     [rsp+arg_8], rbx
0x140023485  mov     [rsp+arg_10], rbp
0x14002348a  push    rsi
0x14002348b  push    rdi
0x14002348c  push    r12
0x14002348e  push    r13
0x140023490  push    r15
0x140023492  sub     rsp, 50h
0x140023496  mov     r12, r8
0x140023499  mov     rbx, rdx
0x14002349c  mov     rdi, rcx
0x14002349f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400234a6  lea     rax, WPP_GLOBAL_Control
0x1400234ad  cmp     rcx, rax
0x1400234b0  jnz     loc_14002367A
0x1400234b6  mov     ebp, [r12]
0x1400234ba  xor     edx, edx; Val
0x1400234bc  mov     r15, [rdi+40h]
0x1400234c0  mov     r8d, ebp; Size
0x1400234c3  mov     rcx, rbx; void *
0x1400234c6  call    memset
0x1400234cb  mov     eax, [r15+40h]
0x1400234cf  xorps   xmm0, xmm0
0x1400234d2  mov     [rsp+78h+var_3D], 0
0x1400234d7  mov     [rsp+78h+var_38], 0
0x1400234e0  mov     [rsp+78h+Src], 28h ; '('
0x1400234e8  mov     [rsp+78h+var_54], 67h ; 'g'
0x1400234f0  movdqu  [rsp+78h+var_4D], xmm0
0x1400234f6  test    eax, eax
0x1400234f8  jz      short loc_140023501
0x1400234fa  add     eax, 68h ; 'h'
0x1400234fd  mov     [rsp+78h+var_54], eax
0x140023501  movzx   ecx, byte ptr [r15+49h]
0x140023506  lea     rdx, [rsp+78h+Src]; Src
0x14002350b  movzx   eax, byte ptr [r15+48h]
0x140023510  mov     r13d, 24h ; '$'
0x140023516  and     al, 1Fh
0x140023518  mov     [rsp+78h+var_3C], 7
0x140023520  mov     [rsp+78h+var_50], al
0x140023524  movzx   eax, cl
0x140023527  and     al, 7Fh
0x140023529  shr     cl, 7
0x14002352c  mov     [rsp+78h+var_4F], al
0x140023530  mov     eax, r13d
0x140023533  cmp     ebp, eax
0x140023535  mov     [rsp+78h+var_4E], cl
0x140023539  mov     rcx, rbx; void *
0x14002353c  cmovl   eax, ebp
0x14002353f  movsxd  r8, eax; Size
0x140023542  call    memmove
0x140023547  lea     edi, [rbp-24h]
0x14002354a  test    edi, edi
0x14002354c  jle     loc_14002365E
0x140023552  mov     r8d, edi
0x140023555  mov     [rsp+78h+arg_0], r14
0x14002355d  cmp     edi, r13d
0x140023560  lea     r14, [rbx+24h]
0x140023564  lea     rdx, [r15+48h]; Src
0x140023568  mov     rcx, r14; void *
0x14002356b  cmovge  r8d, r13d; Size
0x14002356f  mov     [rbx+20h], r8d
0x140023573  call    memmove
0x140023578  lea     eax, [rdi-24h]
0x14002357b  test    eax, eax
0x14002357d  jle     loc_140023656
0x140023583  cdqe
0x140023585  lea     rdx, [r15+50h]; Src
0x140023589  mov     r8d, 8
0x14002358f  lea     rcx, [r14+24h]; void *
0x140023593  cmp     rax, r8
0x140023596  cmovb   r8, rax; Size
0x14002359a  call    memmove
0x14002359f  add     edi, 0FFFFFFD3h
0x1400235a2  js      short loc_1400235AD
0x1400235a4  lea     eax, [r14+24h]
0x1400235a8  sub     eax, ebx
0x1400235aa  mov     [rbx+0Ch], eax
0x1400235ad  test    edi, edi
0x1400235af  jle     loc_140023656
0x1400235b5  movsxd  rax, edi
0x1400235b8  lea     rdx, [r15+58h]; Src
0x1400235bc  mov     r8d, 10h
0x1400235c2  lea     rcx, [r14+2Dh]; void *
0x1400235c6  cmp     rax, r8
0x1400235c9  cmovb   r8, rax; Size
0x1400235cd  call    memmove
0x1400235d2  add     edi, 0FFFFFFEFh
0x1400235d5  js      short loc_1400235E0
0x1400235d7  lea     eax, [r14+2Dh]
0x1400235db  sub     eax, ebx
0x1400235dd  mov     [rbx+10h], eax
0x1400235e0  test    edi, edi
0x1400235e2  jle     short loc_140023656
0x1400235e4  movsxd  rax, edi
0x1400235e7  lea     rdx, [r15+68h]; Src
0x1400235eb  mov     r8d, 4
0x1400235f1  lea     rcx, [r14+3Eh]; void *
0x1400235f5  cmp     rax, r8
0x1400235f8  cmovb   r8, rax; Size
0x1400235fc  call    memmove
0x140023601  add     edi, 0FFFFFFFBh
0x140023604  js      short loc_14002360F
0x140023606  lea     eax, [r14+3Eh]
0x14002360a  sub     eax, ebx
0x14002360c  mov     [rbx+14h], eax
0x14002360f  mov     dword ptr [rbx+18h], 0
0x140023616  test    edi, edi
0x140023618  jle     short loc_140023656
0x14002361a  mov     ecx, [r15+40h]
0x14002361e  test    ecx, ecx
0x140023620  jz      loc_1400236A9
0x140023626  add     r14, 43h ; 'C'
0x14002362a  lea     rdx, [r15+6Ch]; Src
0x14002362e  cmp     edi, ecx
0x140023630  mov     eax, edi
0x140023632  cmovge  eax, ecx
0x140023635  mov     rcx, r14; void *
0x140023638  movsxd  r8, eax; Size
0x14002363b  call    memmove
0x140023640  sub     edi, [r15+40h]
0x140023644  sub     edi, 1
0x140023647  js      short loc_140023656
0x140023649  sub     r14d, ebx
0x14002364c  sub     ebp, edi
0x14002364e  mov     [rbx+18h], r14d
0x140023652  mov     [r12], ebp
0x140023656  mov     r14, [rsp+78h+arg_0]
0x14002365e  lea     r11, [rsp+78h+var_28]
0x140023663  xor     eax, eax
0x140023665  mov     rbx, [r11+38h]
0x140023669  mov     rbp, [r11+40h]
0x14002366d  mov     rsp, r11
0x140023670  pop     r15
0x140023672  pop     r13
0x140023674  pop     r12
0x140023676  pop     rdi
0x140023677  pop     rsi
0x140023678  retn
0x14002367a  mov     eax, [rcx+2Ch]
0x14002367d  test    al, 10h
0x14002367f  jz      loc_1400234B6
0x140023685  cmp     byte ptr [rcx+29h], 4
0x140023689  jb      loc_1400234B6
0x14002368f  mov     rcx, [rcx+18h]
0x140023693  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14002369a  mov     edx, 1Eh
0x14002369f  call    WPP_SF_
0x1400236a4  jmp     loc_1400234B6
0x1400236a9  mov     dword ptr [r12], 67h ; 'g'
0x1400236b1  jmp     short loc_140023656
```
