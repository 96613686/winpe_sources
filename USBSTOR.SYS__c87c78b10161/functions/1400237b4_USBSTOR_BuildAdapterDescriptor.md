# USBSTOR_BuildAdapterDescriptor

- ea: `0x1400237b4`
- end: `0x1400238f9`
- name: `USBSTOR_BuildAdapterDescriptor`
- size: `325`
- prototype: `__int64 __fastcall(__int64, _DWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400232d0`

## callees

- `0x1400105e8`
- `0x140010664`
- `0x140013a40`
- `0x1400237b4`

## pseudocode

```c
__int64 __fastcall USBSTOR_BuildAdapterDescriptor(__int64 a1, _DWORD *a2, unsigned int *a3)
{
  unsigned int v6; // r8d
  unsigned int v8; // edx
  __int64 v9; // r9
  bool v10; // zf
  __int16 v11; // ax
  int Src; // [rsp+20h] [rbp-20h] BYREF
  int v13; // [rsp+24h] [rbp-1Ch]
  int v14; // [rsp+28h] [rbp-18h]
  int v15; // [rsp+2Ch] [rbp-14h]
  __int64 v16; // [rsp+30h] [rbp-10h]
  char v17; // [rsp+38h] [rbp-8h]
  char v18; // [rsp+39h] [rbp-7h]
  __int16 v19; // [rsp+3Ah] [rbp-6h]
  __int16 v20; // [rsp+3Ch] [rbp-4h]
  __int16 v21; // [rsp+3Eh] [rbp-2h]

  v13 = 0;
  v21 = 0;
  v18 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  v6 = *a3;
  if ( *a3 >= 8 )
  {
    v8 = 30;
    if ( v6 >= 0x1E )
    {
      v9 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 16LL) + 64LL);
      if ( v6 >= 0x20 )
      {
        Src = 32;
        v8 = 32;
        v13 = 32;
      }
      else
      {
        Src = 30;
        v13 = 30;
      }
      v10 = *(_BYTE *)(v9 + 1813) == 0;
      v14 = *(_DWORD *)(v9 + 1816);
      v15 = *(_DWORD *)(v9 + 1820);
      v11 = 2;
      v16 = 0;
      v17 = 7;
      if ( v10 )
        v11 = 1;
      v19 = v11;
      *a3 = v8;
      v20 = 0;
      memmove(a2, &Src, v8);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
    }
    else
    {
      *a3 = 8;
      *a2 = 32;
      a2[1] = 32;
    }
    return 0;
  }
  else
  {
    *a3 = 32;
    return 3221225507LL;
  }
}

```

## disassembly

```asm
0x1400237b4  push    rbp
0x1400237b6  push    rbx
0x1400237b7  push    rsi
0x1400237b8  push    rdi
0x1400237b9  push    r15
0x1400237bb  mov     rbp, rsp
0x1400237be  sub     rsp, 40h
0x1400237c2  xor     eax, eax
0x1400237c4  mov     [rbp+var_1C], 0
0x1400237cb  mov     [rbp+var_2], ax
0x1400237cf  mov     rdi, r8
0x1400237d2  mov     rsi, rdx
0x1400237d5  mov     [rbp+var_7], 0
0x1400237d9  mov     rbx, rcx
0x1400237dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400237e3  lea     r15, WPP_GLOBAL_Control
0x1400237ea  cmp     rcx, r15
0x1400237ed  jz      short loc_140023811
0x1400237ef  mov     eax, [rcx+2Ch]
0x1400237f2  test    al, 10h
0x1400237f4  jz      short loc_140023811
0x1400237f6  cmp     byte ptr [rcx+29h], 4
0x1400237fa  jb      short loc_140023811
0x1400237fc  mov     rcx, [rcx+18h]
0x140023800  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140023807  mov     edx, 1Fh
0x14002380c  call    WPP_SF_
0x140023811  mov     r8d, [rdi]
0x140023814  cmp     r8d, 8
0x140023818  jnb     short loc_14002382A
0x14002381a  mov     dword ptr [rdi], 20h ; ' '
0x140023820  mov     eax, 0C0000023h
0x140023825  jmp     loc_1400238ED
0x14002382a  mov     edx, 1Eh
0x14002382f  cmp     r8d, edx
0x140023832  jnb     short loc_140023847
0x140023834  lea     ebx, [rdx+2]
0x140023837  mov     dword ptr [rdi], 8
0x14002383d  mov     [rsi], ebx
0x14002383f  mov     [rsi+4], ebx
0x140023842  jmp     loc_1400238EB
0x140023847  mov     rax, [rbx+40h]
0x14002384b  mov     ebx, 20h ; ' '
0x140023850  mov     rcx, [rax+10h]
0x140023854  mov     r9, [rcx+40h]
0x140023858  cmp     r8d, ebx
0x14002385b  jnb     short loc_140023865
0x14002385d  mov     [rbp+Src], edx
0x140023860  mov     [rbp+var_1C], edx
0x140023863  jmp     short loc_14002386D
0x140023865  mov     [rbp+Src], ebx
0x140023868  mov     edx, ebx
0x14002386a  mov     [rbp+var_1C], ebx
0x14002386d  cmp     byte ptr [r9+715h], 0
0x140023875  mov     eax, [r9+718h]
0x14002387c  mov     [rbp+var_18], eax
0x14002387f  mov     eax, [r9+71Ch]
0x140023886  mov     [rbp+var_14], eax
0x140023889  mov     eax, 2
0x14002388e  mov     [rbp+var_10], 0
0x140023896  mov     [rbp+var_8], 7
0x14002389a  jnz     short loc_1400238A1
0x14002389c  mov     eax, 1
0x1400238a1  mov     r8d, edx; Size
0x1400238a4  mov     rcx, rsi; void *
0x1400238a7  mov     [rbp+var_6], ax
0x1400238ab  lea     rdx, [rbp+Src]; Src
0x1400238af  xor     eax, eax
0x1400238b1  mov     [rdi], r8d
0x1400238b4  mov     [rbp+var_4], ax
0x1400238b8  call    memmove
0x1400238bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400238c4  cmp     rcx, r15
0x1400238c7  jz      short loc_1400238EB
0x1400238c9  mov     eax, [rcx+2Ch]
0x1400238cc  test    al, 10h
0x1400238ce  jz      short loc_1400238EB
0x1400238d0  cmp     byte ptr [rcx+29h], 5
0x1400238d4  jb      short loc_1400238EB
0x1400238d6  mov     rcx, [rcx+18h]
0x1400238da  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400238e1  mov     edx, ebx
0x1400238e3  xor     r9d, r9d
0x1400238e6  call    WPP_SF_d
0x1400238eb  xor     eax, eax
0x1400238ed  add     rsp, 40h
0x1400238f1  pop     r15
0x1400238f3  pop     rdi
0x1400238f4  pop     rsi
0x1400238f5  pop     rbx
0x1400238f6  pop     rbp
0x1400238f7  retn
```
