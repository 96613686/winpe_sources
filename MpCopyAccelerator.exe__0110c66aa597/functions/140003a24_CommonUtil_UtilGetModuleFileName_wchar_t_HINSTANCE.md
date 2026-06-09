# CommonUtil::UtilGetModuleFileName(wchar_t * *,HINSTANCE__ *)

- ea: `0x140003a24`
- end: `0x140003ba5`
- name: `?UtilGetModuleFileName@CommonUtil@@YAJPEAPEA_WPEAUHINSTANCE__@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, wchar_t **, HINSTANCE)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003414`

## callees

- `0x140003054`
- `0x1400036e0`
- `0x140003a24`
- `0x140005c20`
- `0x140005c40`
- `0x140024bcc`

## pseudocode

```c
int __fastcall CommonUtil::UtilGetModuleFileName(CommonUtil *this, wchar_t **a2, HINSTANCE a3, HINSTANCE a4)
{
  int ModuleFileName; // eax
  int v7; // r8d
  int result; // eax
  unsigned __int64 v9; // rcx
  wchar_t **v10; // rbx
  unsigned __int64 v11; // rdi
  int v12; // ebx
  HINSTANCE v13; // r9
  int v14; // eax
  const wchar_t *v15; // r8
  int v16; // edi
  unsigned __int64 v17; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t **v18; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t *v19[66]; // [rsp+30h] [rbp-D0h] BYREF

  v17 = 260;
  ModuleFileName = CommonUtil::HrGetModuleFileName((CommonUtil *)&v17, (unsigned __int64 *)v19, (wchar_t *)a2, a4);
  v7 = ModuleFileName;
  if ( ModuleFileName >= 0 )
    return CommonUtil::HrDuplicateStringW(this, v19, (const wchar_t *)(unsigned int)ModuleFileName);
  result = 0;
  if ( v7 != -2147024774 )
    result = v7;
  if ( result >= 0 )
  {
    v9 = v17;
    v10 = 0;
    v18 = 0;
    if ( v17 >= (3 * v17) >> 1 )
    {
      return -2147024882;
    }
    else
    {
      while ( 1 )
      {
        v11 = (3 * v9) >> 1;
        v17 = v11;
        if ( v10 )
        {
          operator delete(v10);
          v18 = 0;
        }
        v12 = CommonUtil::MpNewBuffer<wchar_t>(&v18, v11);
        if ( v12 < 0 )
          break;
        v10 = v18;
        v14 = CommonUtil::HrGetModuleFileName((CommonUtil *)&v17, (unsigned __int64 *)v18, (wchar_t *)a2, v13);
        v16 = v14;
        if ( v14 >= 0 )
        {
          v16 = CommonUtil::HrDuplicateStringW(this, v10, v15);
LABEL_18:
          if ( v10 )
            operator delete(v10);
          return v16;
        }
        if ( v14 != -2147024774 )
          goto LABEL_18;
        v9 = v17;
        if ( v17 >= (3 * v17) >> 1 )
        {
          if ( v10 )
            operator delete(v10);
          return -2147024882;
        }
      }
      if ( v18 )
        operator delete(v18);
      return v12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003a24  mov     [rsp-8+arg_10], rbx
0x140003a29  mov     [rsp-8+arg_18], rsi
0x140003a2e  push    rbp
0x140003a2f  push    rdi
0x140003a30  push    r14
0x140003a32  lea     rbp, [rsp-150h]
0x140003a3a  sub     rsp, 250h
0x140003a41  mov     rax, cs:__security_cookie
0x140003a48  xor     rax, rsp
0x140003a4b  mov     [rbp+160h+var_20], rax
0x140003a52  mov     r14, rdx
0x140003a55  mov     [rsp+260h+var_240], 104h
0x140003a5e  mov     rsi, rcx
0x140003a61  mov     r8, rdx; wchar_t *
0x140003a64  lea     rdx, [rsp+260h+var_230]; unsigned __int64 *
0x140003a69  lea     rcx, [rsp+260h+var_240]; this
0x140003a6e  call    ?HrGetModuleFileName@CommonUtil@@YAJPEA_KPEA_WPEAUHINSTANCE__@@@Z; CommonUtil::HrGetModuleFileName(unsigned __int64 *,wchar_t *,HINSTANCE__ *)
0x140003a73  mov     r8d, eax; wchar_t *
0x140003a76  shr     eax, 1Fh
0x140003a79  test    al, al
0x140003a7b  jnz     short loc_140003A8F
0x140003a7d  lea     rdx, [rsp+260h+var_230]; wchar_t **
0x140003a82  mov     rcx, rsi; this
0x140003a85  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::HrDuplicateStringW(wchar_t * *,wchar_t const *)
0x140003a8a  jmp     loc_140003B4D
0x140003a8f  xor     eax, eax
0x140003a91  cmp     r8d, 8007007Ah
0x140003a98  cmovnz  eax, r8d
0x140003a9c  mov     ecx, eax
0x140003a9e  shr     ecx, 1Fh
0x140003aa1  test    cl, cl
0x140003aa3  jnz     loc_140003B4D
0x140003aa9  mov     rcx, [rsp+260h+var_240]
0x140003aae  xor     ebx, ebx
0x140003ab0  mov     [rsp+260h+var_238], rbx
0x140003ab5  lea     rax, [rcx+rcx*2]
0x140003ab9  shr     rax, 1
0x140003abc  cmp     rcx, rax
0x140003abf  jnb     loc_140003B48
0x140003ac5  lea     rdi, [rcx+rcx*2]
0x140003ac9  shr     rdi, 1
0x140003acc  mov     [rsp+260h+var_240], rdi
0x140003ad1  test    rbx, rbx
0x140003ad4  jz      short loc_140003AE7
0x140003ad6  mov     rcx, rbx; void *
0x140003ad9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003ade  mov     [rsp+260h+var_238], 0
0x140003ae7  mov     rdx, rdi
0x140003aea  lea     rcx, [rsp+260h+var_238]
0x140003aef  call    ??$MpNewBuffer@_W@CommonUtil@@YAJPEAPEA_W_K@Z; CommonUtil::MpNewBuffer<wchar_t>(wchar_t * *,unsigned __int64)
0x140003af4  mov     ecx, eax
0x140003af6  mov     ebx, eax
0x140003af8  shr     ecx, 1Fh
0x140003afb  test    cl, cl
0x140003afd  jnz     loc_140003B92
0x140003b03  mov     rbx, [rsp+260h+var_238]
0x140003b08  lea     rcx, [rsp+260h+var_240]; this
0x140003b0d  mov     rdx, rbx; unsigned __int64 *
0x140003b10  mov     r8, r14; wchar_t *
0x140003b13  call    ?HrGetModuleFileName@CommonUtil@@YAJPEA_KPEA_WPEAUHINSTANCE__@@@Z; CommonUtil::HrGetModuleFileName(unsigned __int64 *,wchar_t *,HINSTANCE__ *)
0x140003b18  mov     ecx, eax
0x140003b1a  mov     edi, eax
0x140003b1c  shr     ecx, 1Fh
0x140003b1f  test    cl, cl
0x140003b21  jz      short loc_140003B74
0x140003b23  cmp     eax, 8007007Ah
0x140003b28  jnz     short loc_140003B81
0x140003b2a  mov     rcx, [rsp+260h+var_240]
0x140003b2f  lea     rax, [rcx+rcx*2]
0x140003b33  shr     rax, 1
0x140003b36  cmp     rcx, rax
0x140003b39  jb      short loc_140003AC5
0x140003b3b  test    rbx, rbx
0x140003b3e  jz      short loc_140003B48
0x140003b40  mov     rcx, rbx; void *
0x140003b43  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003b48  mov     eax, 8007000Eh
0x140003b4d  mov     rcx, [rbp+160h+var_20]
0x140003b54  xor     rcx, rsp; StackCookie
0x140003b57  call    __security_check_cookie
0x140003b5c  lea     r11, [rsp+260h+var_10]
0x140003b64  mov     rbx, [r11+30h]
0x140003b68  mov     rsi, [r11+38h]
0x140003b6c  mov     rsp, r11
0x140003b6f  pop     r14
0x140003b71  pop     rdi
0x140003b72  pop     rbp
0x140003b73  retn
0x140003b74  mov     rdx, rbx; wchar_t **
0x140003b77  mov     rcx, rsi; this
0x140003b7a  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::HrDuplicateStringW(wchar_t * *,wchar_t const *)
0x140003b7f  mov     edi, eax
0x140003b81  test    rbx, rbx
0x140003b84  jz      short loc_140003B8E
0x140003b86  mov     rcx, rbx; void *
0x140003b89  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003b8e  mov     eax, edi
0x140003b90  jmp     short loc_140003B4D
0x140003b92  mov     rcx, [rsp+260h+var_238]; void *
0x140003b97  test    rcx, rcx
0x140003b9a  jz      short loc_140003BA1
0x140003b9c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003ba1  mov     eax, ebx
0x140003ba3  jmp     short loc_140003B4D
```
