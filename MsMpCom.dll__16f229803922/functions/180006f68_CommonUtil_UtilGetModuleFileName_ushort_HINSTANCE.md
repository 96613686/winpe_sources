# CommonUtil::UtilGetModuleFileName(ushort * *,HINSTANCE__ *)

- ea: `0x180006f68`
- end: `0x1800070b2`
- name: `?UtilGetModuleFileName@CommonUtil@@YAJPEAPEAGPEAUHINSTANCE__@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned __int16 **, HINSTANCE)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800071ac`

## callees

- `0x180006ce4`
- `0x180006e04`
- `0x180006f68`
- `0x180007d9c`
- `0x180009440`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180006fff`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007059`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007094`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800070a8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006fff`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007059`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007094`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800070a8`

## pseudocode

```c
int __fastcall CommonUtil::UtilGetModuleFileName(
        CommonUtil *this,
        unsigned __int16 **a2,
        unsigned __int16 *a3,
        HINSTANCE a4)
{
  int ModuleFileName; // edx
  const unsigned __int16 *v6; // r8
  int result; // eax
  unsigned __int64 v8; // rcx
  unsigned __int16 **v9; // rbx
  unsigned __int64 v10; // rdi
  int v11; // ebx
  unsigned __int16 *v12; // r8
  HINSTANCE v13; // r9
  int v14; // eax
  const unsigned __int16 *v15; // r8
  int v16; // edi
  unsigned __int64 v17; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 **v18; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v19[66]; // [rsp+30h] [rbp-D0h] BYREF

  v17 = 260;
  ModuleFileName = CommonUtil::HrGetModuleFileName((CommonUtil *)&v17, (unsigned __int64 *)v19, a3, a4);
  if ( ModuleFileName >= 0 )
    return CommonUtil::HrDuplicateStringW(this, v19, v6);
  result = 0;
  if ( ModuleFileName != -2147024774 )
    result = ModuleFileName;
  if ( result >= 0 )
  {
    v8 = v17;
    v9 = 0;
    v18 = 0;
    if ( v17 >= (3 * v17) >> 1 )
    {
      return -2147024882;
    }
    else
    {
      while ( 1 )
      {
        v10 = (3 * v8) >> 1;
        v17 = v10;
        if ( v9 )
        {
          operator delete[](v9);
          v18 = 0;
        }
        v11 = CommonUtil::MpNewBuffer<unsigned short>(&v18, v10);
        if ( v11 < 0 )
          break;
        v9 = v18;
        v14 = CommonUtil::HrGetModuleFileName((CommonUtil *)&v17, (unsigned __int64 *)v18, v12, v13);
        v16 = v14;
        if ( v14 >= 0 )
        {
          v16 = CommonUtil::HrDuplicateStringW(this, v9, v15);
LABEL_18:
          if ( v9 )
            operator delete[](v9);
          return v16;
        }
        if ( v14 != -2147024774 )
          goto LABEL_18;
        v8 = v17;
        if ( v17 >= (3 * v17) >> 1 )
        {
          if ( v9 )
            operator delete[](v9);
          return -2147024882;
        }
      }
      if ( v18 )
        operator delete[](v18);
      return v11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006f68  push    rbp
0x180006f6a  push    rbx
0x180006f6b  push    rsi
0x180006f6c  push    rdi
0x180006f6d  lea     rbp, [rsp-158h]
0x180006f75  sub     rsp, 258h
0x180006f7c  mov     rax, cs:__security_cookie
0x180006f83  xor     rax, rsp
0x180006f86  mov     [rbp+170h+var_30], rax
0x180006f8d  mov     rsi, rcx
0x180006f90  mov     [rsp+270h+var_250], 104h
0x180006f99  lea     rcx, [rsp+270h+var_250]; this
0x180006f9e  lea     rdx, [rsp+270h+var_240]; unsigned __int64 *
0x180006fa3  call    ?HrGetModuleFileName@CommonUtil@@YAJPEA_KPEAGPEAUHINSTANCE__@@@Z; CommonUtil::HrGetModuleFileName(unsigned __int64 *,ushort *,HINSTANCE__ *)
0x180006fa8  mov     edx, eax
0x180006faa  test    eax, eax
0x180006fac  js      short loc_180006FC0
0x180006fae  lea     rdx, [rsp+270h+var_240]; unsigned __int16 **
0x180006fb3  mov     rcx, rsi; this
0x180006fb6  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x180006fbb  jmp     loc_180007064
0x180006fc0  xor     eax, eax
0x180006fc2  cmp     edx, 8007007Ah
0x180006fc8  cmovnz  eax, edx
0x180006fcb  test    eax, eax
0x180006fcd  js      loc_180007064
0x180006fd3  mov     rcx, [rsp+270h+var_250]
0x180006fd8  xor     ebx, ebx
0x180006fda  mov     [rsp+270h+var_248], rbx
0x180006fdf  lea     rax, [rcx+rcx*2]
0x180006fe3  shr     rax, 1
0x180006fe6  cmp     rcx, rax
0x180006fe9  jnb     short loc_18000705F
0x180006feb  lea     rdi, [rcx+rcx*2]
0x180006fef  shr     rdi, 1
0x180006ff2  mov     [rsp+270h+var_250], rdi
0x180006ff7  test    rbx, rbx
0x180006ffa  jz      short loc_18000700E
0x180006ffc  mov     rcx, rbx
0x180006fff  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007005  mov     [rsp+270h+var_248], 0
0x18000700e  mov     rdx, rdi
0x180007011  lea     rcx, [rsp+270h+var_248]
0x180007016  call    ??$MpNewBuffer@G@CommonUtil@@YAJPEAPEAG_K@Z; CommonUtil::MpNewBuffer<ushort>(ushort * *,unsigned __int64)
0x18000701b  mov     ebx, eax
0x18000701d  test    eax, eax
0x18000701f  js      short loc_18000709E
0x180007021  mov     rbx, [rsp+270h+var_248]
0x180007026  lea     rcx, [rsp+270h+var_250]; this
0x18000702b  mov     rdx, rbx; unsigned __int64 *
0x18000702e  call    ?HrGetModuleFileName@CommonUtil@@YAJPEA_KPEAGPEAUHINSTANCE__@@@Z; CommonUtil::HrGetModuleFileName(unsigned __int64 *,ushort *,HINSTANCE__ *)
0x180007033  mov     edi, eax
0x180007035  test    eax, eax
0x180007037  jns     short loc_18000707F
0x180007039  cmp     eax, 8007007Ah
0x18000703e  jnz     short loc_18000708C
0x180007040  mov     rcx, [rsp+270h+var_250]
0x180007045  lea     rax, [rcx+rcx*2]
0x180007049  shr     rax, 1
0x18000704c  cmp     rcx, rax
0x18000704f  jb      short loc_180006FEB
0x180007051  test    rbx, rbx
0x180007054  jz      short loc_18000705F
0x180007056  mov     rcx, rbx
0x180007059  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000705f  mov     eax, 8007000Eh
0x180007064  mov     rcx, [rbp+170h+var_30]
0x18000706b  xor     rcx, rsp; StackCookie
0x18000706e  call    __security_check_cookie
0x180007073  add     rsp, 258h
0x18000707a  pop     rdi
0x18000707b  pop     rsi
0x18000707c  pop     rbx
0x18000707d  pop     rbp
0x18000707e  retn
0x18000707f  mov     rdx, rbx; unsigned __int16 **
0x180007082  mov     rcx, rsi; this
0x180007085  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x18000708a  mov     edi, eax
0x18000708c  test    rbx, rbx
0x18000708f  jz      short loc_18000709A
0x180007091  mov     rcx, rbx
0x180007094  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000709a  mov     eax, edi
0x18000709c  jmp     short loc_180007064
0x18000709e  mov     rcx, [rsp+270h+var_248]
0x1800070a3  test    rcx, rcx
0x1800070a6  jz      short loc_1800070AE
0x1800070a8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800070ae  mov     eax, ebx
0x1800070b0  jmp     short loc_180007064
```
