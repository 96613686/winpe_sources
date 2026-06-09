# IsGoodAdvancedInfVersion(ushort const *)

- ea: `0x180008330`
- end: `0x18000851b`
- name: `?IsGoodAdvancedInfVersion@@YAHPEBG@Z`
- size: `491`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004754`

## callees

- `0x180006af8`
- `0x180007454`
- `0x180008330`
- `0x180008a6c`
- `0x18000c574`

## import_xrefs

- `msvcrt!_wtol` at `0x180008494`
- `msvcrt!_wtol` at `0x1800084a5`
- `msvcrt!_wtol` at `0x180008494`
- `msvcrt!_wtol` at `0x1800084a5`
- `KERNEL32!LocalFree` at `0x1800084fc`
- `KERNEL32!LocalFree` at `0x1800084fc`
- `KERNEL32!LocalAlloc` at `0x18000838f`
- `KERNEL32!LocalAlloc` at `0x18000838f`

## string_xrefs

- `0x1800084ed`: `Advpack.dll Version check failed! InfFile=%1\n`

## pseudocode

```c
__int64 __fastcall IsGoodAdvancedInfVersion(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  DWORD v3; // ebx
  unsigned __int16 *v4; // rdi
  unsigned __int16 *StringField; // rbp
  unsigned __int16 *v6; // rsi
  unsigned __int16 *v7; // rbp
  unsigned __int16 *v8; // r15
  int v9; // ebp
  unsigned int v10; // eax
  unsigned __int16 *v12; // [rsp+68h] [rbp+10h] BYREF

  LODWORD(v12) = 0;
  if ( (int)GetTranslatedString(a1, L"Version", L"AdvancedINF", 0, 0, (unsigned int *)&v12) >= 0 )
  {
    v3 = (unsigned int)v12;
    v4 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (unsigned int)v12);
    if ( v4 )
    {
      if ( (int)GetTranslatedString(a1, L"Version", L"AdvancedINF", v4, v3, (unsigned int *)&v12) >= 0 )
      {
        v12 = v4;
        v2 = 1;
        StringField = GetStringField(&v12, L",", 39, 1);
        v6 = GetStringField(&v12, L",", 39, 1);
        if ( StringField )
        {
          if ( *StringField )
          {
            v12 = StringField;
            v7 = GetStringField(&v12, L".", 39, 1);
            v8 = GetStringField(&v12, L".", 39, 1);
            if ( v7 )
            {
              v9 = 100 * _wtol(v7);
              if ( v8 )
                v10 = v9 + _wtol(v8);
              else
                v10 = v9;
              if ( v10 > 0xCD )
              {
                v2 = 0;
                if ( v6 )
                {
                  if ( *v6 )
                  {
                    MsgBox2Param(hWnd, 0x3EAu, v6, 0, 0x10u, 0);
                    AdvWriteToLog(L"Advpack.dll Version check failed! InfFile=%1\r\n", a1);
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        v2 = 0;
      }
      LocalFree(v4);
    }
    else
    {
      MsgBox2Param(hWnd, 0x44Eu, 0, 0, 0x10u, 0);
      return 0;
    }
  }
  else
  {
    return 1;
  }
  return v2;
}

```

## disassembly

```asm
0x180008330  mov     r11, rsp
0x180008333  mov     [r11+8], rbx
0x180008337  mov     [r11+18h], rbp
0x18000833b  push    rsi
0x18000833c  push    rdi
0x18000833d  push    r12
0x18000833f  push    r14
0x180008341  push    r15
0x180008343  sub     rsp, 30h
0x180008347  lea     rax, [r11+10h]
0x18000834b  xor     r12d, r12d
0x18000834e  mov     [r11-30h], rax
0x180008352  lea     r8, aAdvancedinf; "AdvancedINF"
0x180008359  xor     r9d, r9d; unsigned __int16 *
0x18000835c  mov     [r11-38h], r12d
0x180008360  lea     rdx, aVersion_0; "Version"
0x180008367  mov     [r11+10h], r12d
0x18000836b  mov     r14, rcx
0x18000836e  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x180008373  test    eax, eax
0x180008375  jns     short loc_180008381
0x180008377  lea     ebx, [r12+1]
0x18000837c  jmp     loc_180008502
0x180008381  mov     ebx, dword ptr [rsp+58h+arg_8]
0x180008385  mov     ecx, 40h ; '@'; uFlags
0x18000838a  mov     edx, ebx
0x18000838c  add     rdx, rdx; uBytes
0x18000838f  call    cs:__imp_LocalAlloc
0x180008395  mov     rdi, rax
0x180008398  test    rax, rax
0x18000839b  jnz     short loc_1800083C9
0x18000839d  mov     rcx, cs:hWnd; hWnd
0x1800083a4  xor     r9d, r9d; unsigned __int16 *
0x1800083a7  mov     dword ptr [rsp+58h+var_30], r12d; unsigned int
0x1800083ac  xor     r8d, r8d; unsigned __int16 *
0x1800083af  mov     edx, 44Eh; uID
0x1800083b4  mov     [rsp+58h+var_38], 10h; unsigned int
0x1800083bc  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x1800083c1  mov     ebx, r12d
0x1800083c4  jmp     loc_180008502
0x1800083c9  lea     rax, [rsp+58h+arg_8]
0x1800083ce  mov     r9, rdi; unsigned __int16 *
0x1800083d1  mov     [rsp+58h+var_30], rax; unsigned int *
0x1800083d6  lea     r8, aAdvancedinf; "AdvancedINF"
0x1800083dd  lea     rdx, aVersion_0; "Version"
0x1800083e4  mov     [rsp+58h+var_38], ebx; unsigned int
0x1800083e8  mov     rcx, r14; unsigned __int16 *
0x1800083eb  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x1800083f0  test    eax, eax
0x1800083f2  jns     short loc_1800083FC
0x1800083f4  mov     ebx, r12d
0x1800083f7  jmp     loc_1800084F9
0x1800083fc  mov     r15d, 27h ; '''
0x180008402  mov     [rsp+58h+arg_8], rdi
0x180008407  mov     r8d, r15d; unsigned __int16
0x18000840a  lea     rdx, asc_18001E134; ","
0x180008411  lea     rcx, [rsp+58h+arg_8]; unsigned __int16 **
0x180008416  lea     ebx, [r15-26h]
0x18000841a  mov     r9d, ebx; int
0x18000841d  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x180008422  mov     r8d, r15d; unsigned __int16
0x180008425  lea     rdx, asc_18001E134; ","
0x18000842c  mov     r9d, ebx; int
0x18000842f  lea     rcx, [rsp+58h+arg_8]; unsigned __int16 **
0x180008434  mov     rbp, rax
0x180008437  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x18000843c  mov     rsi, rax
0x18000843f  test    rbp, rbp
0x180008442  jz      loc_1800084F9
0x180008448  cmp     [rbp+0], r12w
0x18000844d  jz      loc_1800084F9
0x180008453  mov     r8d, r15d; unsigned __int16
0x180008456  mov     [rsp+58h+arg_8], rbp
0x18000845b  mov     r9d, ebx; int
0x18000845e  lea     rdx, asc_18001E860; "."
0x180008465  lea     rcx, [rsp+58h+arg_8]; unsigned __int16 **
0x18000846a  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x18000846f  mov     r8d, r15d; unsigned __int16
0x180008472  lea     rdx, asc_18001E860; "."
0x180008479  mov     r9d, ebx; int
0x18000847c  lea     rcx, [rsp+58h+arg_8]; unsigned __int16 **
0x180008481  mov     rbp, rax
0x180008484  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x180008489  mov     r15, rax
0x18000848c  test    rbp, rbp
0x18000848f  jz      short loc_1800084F9
0x180008491  mov     rcx, rbp; String
0x180008494  call    cs:__imp__wtol
0x18000849a  imul    ebp, eax, 64h ; 'd'
0x18000849d  test    r15, r15
0x1800084a0  jz      short loc_1800084AF
0x1800084a2  mov     rcx, r15; String
0x1800084a5  call    cs:__imp__wtol
0x1800084ab  add     eax, ebp
0x1800084ad  jmp     short loc_1800084B1
0x1800084af  mov     eax, ebp
0x1800084b1  cmp     eax, 0CDh
0x1800084b6  jbe     short loc_1800084F9
0x1800084b8  mov     ebx, r12d
0x1800084bb  test    rsi, rsi
0x1800084be  jz      short loc_1800084F9
0x1800084c0  cmp     [rsi], r12w
0x1800084c4  jz      short loc_1800084F9
0x1800084c6  mov     rcx, cs:hWnd; hWnd
0x1800084cd  xor     r9d, r9d; unsigned __int16 *
0x1800084d0  mov     dword ptr [rsp+58h+var_30], r12d; unsigned int
0x1800084d5  mov     r8, rsi; unsigned __int16 *
0x1800084d8  mov     edx, 3EAh; uID
0x1800084dd  mov     [rsp+58h+var_38], 10h; unsigned int
0x1800084e5  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x1800084ea  mov     rdx, r14
0x1800084ed  lea     rcx, aAdvpackDllVers; "Advpack.dll Version check failed! InfFi"...
0x1800084f4  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x1800084f9  mov     rcx, rdi; hMem
0x1800084fc  call    cs:__imp_LocalFree
0x180008502  mov     rbp, [rsp+58h+arg_10]
0x180008507  mov     eax, ebx
0x180008509  mov     rbx, [rsp+58h+arg_0]
0x18000850e  add     rsp, 30h
0x180008512  pop     r15
0x180008514  pop     r14
0x180008516  pop     r12
0x180008518  pop     rdi
0x180008519  pop     rsi
0x18000851a  retn
```
