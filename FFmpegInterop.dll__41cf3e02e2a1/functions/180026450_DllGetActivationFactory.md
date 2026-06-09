# DllGetActivationFactory

- ea: `0x180026450`
- end: `0x180026581`
- name: `DllGetActivationFactory`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180003f04`
- `0x180004474`
- `0x180007f3c`
- `0x180026190`
- `0x180026450`
- `0x18002cf71`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800264e1`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800264e1`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(__int64 a1, __int64 *a2)
{
  unsigned int v3; // edi
  OLECHAR *v4; // rbx
  __int64 v5; // rax
  _DWORD *v7; // r8
  unsigned int v8; // ebx
  int v9; // [rsp+20h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-60h] BYREF
  unsigned __int64 v11; // [rsp+30h] [rbp-58h]
  __int64 v12; // [rsp+38h] [rbp-50h] BYREF
  _DWORD *v13; // [rsp+40h] [rbp-48h]
  _DWORD v14[4]; // [rsp+48h] [rbp-40h] BYREF
  OLECHAR *v15; // [rsp+58h] [rbp-30h]
  int v16; // [rsp+60h] [rbp-28h] BYREF
  const char *v17; // [rsp+68h] [rbp-20h]
  __int64 v18; // [rsp+70h] [rbp-18h]

  bstrString = 0;
  if ( a1 )
  {
    v3 = *(_DWORD *)(a1 + 4);
    v4 = *(OLECHAR **)(a1 + 16);
    v11 = v3;
  }
  else
  {
    v4 = (OLECHAR *)&qword_180037EB8;
    v11 = 0;
    v3 = 0;
  }
  bstrString = v4;
  v5 = sub_180026190(&bstrString);
  *a2 = v5;
  if ( v5 )
    return 0;
  v16 = 80;
  v17 = "C:\\__w\\1\\s\\FFmpegInterop\\FFmpegInterop\\Generated Files\\module.g.cpp";
  v18 = 0;
  if ( v3 )
  {
    if ( v4[v3] )
      abort();
    v14[0] = 1;
    v14[1] = v3;
    v15 = v4;
    v7 = v14;
    v13 = v14;
  }
  else
  {
    v7 = 0;
    v13 = 0;
  }
  bstrString = 0;
  v11 = 0x80040111AABBCCDDuLL;
  v12 = 0;
  sub_180004474(&bstrString, 2147746065LL, v7, &v16);
  v8 = *(_DWORD *)sub_180007F3C(&bstrString, &v9);
  if ( v12 )
    sub_180003F04(&v12);
  if ( bstrString )
    SysFreeString(bstrString);
  return v8;
}

```

## disassembly

```asm
0x180026450  mov     rax, rsp
0x180026453  mov     [rax+8], rbx
0x180026457  mov     [rax+18h], rsi
0x18002645b  mov     [rax+20h], rdi
0x18002645f  push    r14
0x180026461  sub     rsp, 80h
0x180026468  mov     rsi, rdx
0x18002646b  xor     r14d, r14d
0x18002646e  mov     [rax-60h], r14
0x180026472  test    rcx, rcx
0x180026475  jz      short loc_180026484
0x180026477  mov     edi, [rcx+4]
0x18002647a  mov     rbx, [rcx+10h]
0x18002647e  mov     [rax-58h], rdi
0x180026482  jmp     short loc_180026493
0x180026484  lea     rbx, qword_180037EB8
0x18002648b  mov     [rsp+88h+var_58], r14
0x180026490  mov     rdi, r14
0x180026493  mov     [rsp+88h+bstrString], rbx
0x180026498  lea     rcx, [rsp+88h+bstrString]
0x18002649d  call    sub_180026190
0x1800264a2  mov     [rsi], rax
0x1800264a5  test    rax, rax
0x1800264a8  jz      short loc_1800264B1
0x1800264aa  xor     eax, eax
0x1800264ac  jmp     loc_180026566
0x1800264b1  mov     [rsp+88h+var_28], 50h ; 'P'
0x1800264b9  lea     rax, aCW1SFfmpeginte_28; "C:\\__w\\1\\s\\FFmpegInterop\\FFmpegInt"...
0x1800264c0  mov     [rsp+88h+var_20], rax
0x1800264c5  mov     [rsp+88h+var_18], r14
0x1800264ca  test    edi, edi
0x1800264cc  jnz     short loc_1800264D8
0x1800264ce  mov     r8, r14
0x1800264d1  mov     [rsp+88h+var_48], r14
0x1800264d6  jmp     short loc_180026503
0x1800264d8  mov     eax, edi
0x1800264da  cmp     [rbx+rax*2], r14w
0x1800264df  jz      short loc_1800264E8
0x1800264e1  call    cs:__imp_abort
0x1800264e8  mov     [rsp+88h+var_40], 1
0x1800264f0  mov     [rsp+88h+var_3C], edi
0x1800264f4  mov     [rsp+88h+var_30], rbx
0x1800264f9  lea     r8, [rsp+88h+var_40]
0x1800264fe  mov     [rsp+88h+var_48], r8
0x180026503  mov     edx, 80040111h
0x180026508  mov     [rsp+88h+bstrString], r14
0x18002650d  mov     dword ptr [rsp+88h+var_58], 0AABBCCDDh
0x180026515  mov     dword ptr [rsp+88h+var_58+4], edx
0x180026519  mov     [rsp+88h+var_50], r14
0x18002651e  lea     r9, [rsp+88h+var_28]
0x180026523  lea     rcx, [rsp+88h+bstrString]
0x180026528  call    sub_180004474
0x18002652d  lea     rdx, [rsp+88h+var_68]
0x180026532  lea     rcx, [rsp+88h+bstrString]
0x180026537  call    sub_180007F3C
0x18002653c  mov     ebx, [rax]
0x18002653e  cmp     [rsp+88h+var_50], r14
0x180026543  jz      short loc_18002654F
0x180026545  lea     rcx, [rsp+88h+var_50]
0x18002654a  call    sub_180003F04
0x18002654f  mov     rcx, [rsp+88h+bstrString]; bstrString
0x180026554  test    rcx, rcx
0x180026557  jz      short loc_18002655E
0x180026559  call    SysFreeString
0x18002655e  mov     eax, ebx
0x180026560  jmp     short loc_180026566
0x180026562  mov     eax, [rsp+88h+var_68]
0x180026566  lea     r11, [rsp+88h+var_8]
0x18002656e  mov     rbx, [r11+10h]
0x180026572  mov     rsi, [r11+20h]
0x180026576  mov     rdi, [r11+28h]
0x18002657a  mov     rsp, r11
0x18002657d  pop     r14
0x18002657f  retn
```
