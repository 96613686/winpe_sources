# DllGetActivationFactory

- ea: `0x180015840`
- end: `0x1800159d0`
- name: `DllGetActivationFactory`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18000a830`
- `0x18000c8d4`
- `0x18000f2b4`
- `0x180015840`
- `0x180017f70`
- `0x18001d0a1`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180015930`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180015930`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(__int64 a1, __int64 *a2)
{
  __int64 *v3; // rbx
  __int64 v4; // rdi
  __int64 *v5; // rax
  __int64 *v6; // rcx
  __int64 *v7; // r8
  _QWORD *v8; // rax
  __int64 v9; // rax
  _DWORD *v11; // r8
  unsigned int v12; // ebx
  int v13; // [rsp+20h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-60h] BYREF
  int v15; // [rsp+30h] [rbp-58h]
  int v16; // [rsp+34h] [rbp-54h]
  __int64 v17; // [rsp+38h] [rbp-50h] BYREF
  _DWORD *v18; // [rsp+40h] [rbp-48h]
  _DWORD v19[4]; // [rsp+48h] [rbp-40h] BYREF
  __int64 *v20; // [rsp+58h] [rbp-30h]
  int v21; // [rsp+60h] [rbp-28h] BYREF
  const char *v22; // [rsp+68h] [rbp-20h]
  __int64 v23; // [rsp+70h] [rbp-18h]

  if ( a1 )
  {
    v3 = *(__int64 **)(a1 + 16);
    v4 = *(unsigned int *)(a1 + 4);
  }
  else
  {
    v3 = &qword_1800253B8;
    v4 = 0;
  }
  v5 = (__int64 *)((char *)v3 + 2 * v4);
  if ( 2 * v4 != 60 )
  {
LABEL_11:
    *a2 = 0;
    goto LABEL_12;
  }
  if ( v5 != v3 )
  {
    v6 = (__int64 *)((char *)v5 - 2);
    do
    {
      v7 = v6;
      if ( *(_WORD *)v6 != *(_WORD *)((char *)v6 + (char *)L"" - (char *)v5) )
        goto LABEL_11;
      v6 = (__int64 *)((char *)v6 - 2);
    }
    while ( v7 != v3 );
  }
  v8 = (_QWORD *)sub_180017F70(0x18u);
  *v8 = 0;
  v8[1] = 0;
  v8[2] = off_180025718;
  _InterlockedIncrement(&dword_18002FF20);
  v8[1] = 1;
  *v8 = &off_1800256D8;
  v9 = (unsigned __int64)(v8 + 2) & -(__int64)(v8 != 0);
  *a2 = v9;
  if ( v9 )
    return 0;
LABEL_12:
  v21 = 62;
  v22 = "C:\\__w\\1\\s\\FFmpegDecoder\\Generated Files\\module.g.cpp";
  v23 = 0;
  if ( (_DWORD)v4 )
  {
    if ( *((_WORD *)v3 + (unsigned int)v4) )
      abort();
    v19[0] = 1;
    v19[1] = v4;
    v20 = v3;
    v11 = v19;
    v18 = v19;
  }
  else
  {
    v11 = 0;
    v18 = 0;
  }
  bstrString = 0;
  v15 = -1430532899;
  v16 = -2147221231;
  v17 = 0;
  sub_18000F2B4(&bstrString, 2147746065LL, v11, &v21);
  v12 = *(_DWORD *)sub_18000C8D4(&bstrString, &v13);
  if ( v17 )
    sub_18000A830(&v17);
  if ( bstrString )
    SysFreeString(bstrString);
  return v12;
}

```

## disassembly

```asm
0x180015840  mov     [rsp+arg_0], rbx
0x180015845  mov     [rsp+arg_10], rsi
0x18001584a  mov     [rsp+arg_18], rdi
0x18001584f  push    r14
0x180015851  sub     rsp, 80h
0x180015858  mov     rsi, rdx
0x18001585b  xor     r14d, r14d
0x18001585e  test    rcx, rcx
0x180015861  jz      short loc_18001586C
0x180015863  mov     rbx, [rcx+10h]
0x180015867  mov     edi, [rcx+4]
0x18001586a  jmp     short loc_180015876
0x18001586c  lea     rbx, qword_1800253B8
0x180015873  mov     rdi, r14
0x180015876  lea     rcx, [rdi+rdi]
0x18001587a  lea     rax, [rcx+rbx]
0x18001587e  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180015882  cmp     rcx, 3Ch ; '<'
0x180015886  jnz     short loc_1800158FD
0x180015888  cmp     rax, rbx
0x18001588b  jz      short loc_1800158B0
0x18001588d  lea     rcx, [rax-2]
0x180015891  lea     rdx, aFfmpegdecoderF+3Ch; ""
0x180015898  sub     rdx, rax
0x18001589b  mov     r8, rcx
0x18001589e  movzx   eax, word ptr [rdx+rcx]
0x1800158a2  cmp     [rcx], ax
0x1800158a5  jnz     short loc_1800158FD
0x1800158a7  sub     rcx, 2
0x1800158ab  cmp     r8, rbx
0x1800158ae  jnz     short loc_18001589B
0x1800158b0  mov     ecx, 18h; Size
0x1800158b5  call    sub_180017F70
0x1800158ba  mov     [rax], r14
0x1800158bd  mov     [rax+8], r14
0x1800158c1  lea     rcx, [rax+10h]
0x1800158c5  lea     rdx, off_180025718
0x1800158cc  mov     [rcx], rdx
0x1800158cf  lock inc cs:dword_18002FF20
0x1800158d6  mov     qword ptr [rax+8], 1
0x1800158de  lea     rdx, off_1800256D8
0x1800158e5  mov     [rax], rdx
0x1800158e8  neg     rax
0x1800158eb  sbb     rax, rax
0x1800158ee  and     rax, rcx
0x1800158f1  mov     [rsi], rax
0x1800158f4  jz      short loc_180015900
0x1800158f6  xor     eax, eax
0x1800158f8  jmp     loc_1800159B5
0x1800158fd  mov     [rsi], r14
0x180015900  mov     [rsp+88h+var_28], 3Eh ; '>'
0x180015908  lea     rax, aCW1SFfmpegdeco_7; "C:\\__w\\1\\s\\FFmpegDecoder\\Generated"...
0x18001590f  mov     [rsp+88h+var_20], rax
0x180015914  mov     [rsp+88h+var_18], r14
0x180015919  test    edi, edi
0x18001591b  jnz     short loc_180015927
0x18001591d  mov     r8, r14
0x180015920  mov     [rsp+88h+var_48], r14
0x180015925  jmp     short loc_180015952
0x180015927  mov     eax, edi
0x180015929  cmp     [rbx+rax*2], r14w
0x18001592e  jz      short loc_180015937
0x180015930  call    cs:__imp_abort
0x180015937  mov     [rsp+88h+var_40], 1
0x18001593f  mov     [rsp+88h+var_3C], edi
0x180015943  mov     [rsp+88h+var_30], rbx
0x180015948  lea     r8, [rsp+88h+var_40]
0x18001594d  mov     [rsp+88h+var_48], r8
0x180015952  mov     edx, 80040111h
0x180015957  mov     [rsp+88h+bstrString], r14
0x18001595c  mov     [rsp+88h+var_58], 0AABBCCDDh
0x180015964  mov     [rsp+88h+var_54], edx
0x180015968  mov     [rsp+88h+var_50], r14
0x18001596d  lea     r9, [rsp+88h+var_28]
0x180015972  lea     rcx, [rsp+88h+bstrString]
0x180015977  call    sub_18000F2B4
0x18001597c  lea     rdx, [rsp+88h+var_68]
0x180015981  lea     rcx, [rsp+88h+bstrString]
0x180015986  call    sub_18000C8D4
0x18001598b  mov     ebx, [rax]
0x18001598d  cmp     [rsp+88h+var_50], r14
0x180015992  jz      short loc_18001599E
0x180015994  lea     rcx, [rsp+88h+var_50]
0x180015999  call    sub_18000A830
0x18001599e  mov     rcx, [rsp+88h+bstrString]; bstrString
0x1800159a3  test    rcx, rcx
0x1800159a6  jz      short loc_1800159AD
0x1800159a8  call    SysFreeString
0x1800159ad  mov     eax, ebx
0x1800159af  jmp     short loc_1800159B5
0x1800159b1  mov     eax, [rsp+88h+var_68]
0x1800159b5  lea     r11, [rsp+88h+var_8]
0x1800159bd  mov     rbx, [r11+10h]
0x1800159c1  mov     rsi, [r11+20h]
0x1800159c5  mov     rdi, [r11+28h]
0x1800159c9  mov     rsp, r11
0x1800159cc  pop     r14
0x1800159ce  retn
```
