# IsFileKnownGood(ushort *,ushort)

- ea: `0x18000ca04`
- end: `0x18000cb29`
- name: `?IsFileKnownGood@@YAHPEAGG@Z`
- size: `293`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c630`

## callees

- `0x18000ca04`
- `0x18001623a`
- `0x180016280`

## import_xrefs

- `apphelp!SdbQueryFlagMask` at `0x18000cae1`
- `apphelp!SdbQueryFlagMask` at `0x18000cae1`
- `apphelp!SdbGetPathSystemSdb` at `0x18000ca74`
- `apphelp!SdbGetPathSystemSdb` at `0x18000ca74`
- `apphelp!SdbInitDatabase` at `0x18000ca8d`
- `apphelp!SdbInitDatabase` at `0x18000ca8d`
- `apphelp!SdbGetMatchingExe` at `0x18000cab9`
- `apphelp!SdbGetMatchingExe` at `0x18000cab9`
- `apphelp!SdbReleaseDatabase` at `0x18000cafc`
- `apphelp!SdbReleaseDatabase` at `0x18000cafc`

## pseudocode

```c
__int64 __fastcall IsFileKnownGood(unsigned __int16 *a1, __int16 a2)
{
  __int64 v3; // rbx
  __int64 inited; // rdi
  int v6; // [rsp+30h] [rbp-408h] BYREF
  unsigned __int64 v7; // [rsp+38h] [rbp-400h] BYREF
  _BYTE v8[464]; // [rsp+40h] [rbp-3F8h] BYREF
  _BYTE v9[528]; // [rsp+210h] [rbp-228h] BYREF

  LOWORD(v6) = a2;
  LODWORD(v3) = 0;
  memset_0(v8, 0, 0x1C8u);
  memset_0(v9, 0, 0x208u);
  v7 = 0;
  if ( (unsigned int)SdbGetPathSystemSdb(v9, 260, 2, &v6) )
  {
    inited = SdbInitDatabase(3, v9);
    if ( inited )
    {
      LODWORD(v3) = SdbGetMatchingExe(inited, a1, 0, 0, 2, v8, v6);
      if ( (_DWORD)v3 )
      {
        LODWORD(v3) = SdbQueryFlagMask(inited, v8, 20495, &v7, 0);
        if ( (_DWORD)v3 )
          v3 = (v7 >> 31) & 1;
      }
      SdbReleaseDatabase(inited);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ca04  mov     [rsp+arg_10], rbx
0x18000ca09  mov     [rsp+arg_18], rsi
0x18000ca0e  push    rdi
0x18000ca0f  sub     rsp, 430h
0x18000ca16  mov     rax, cs:__security_cookie
0x18000ca1d  xor     rax, rsp
0x18000ca20  mov     [rsp+438h+var_18], rax
0x18000ca28  mov     rsi, rcx
0x18000ca2b  mov     word ptr [rsp+438h+var_408], dx
0x18000ca30  xor     edx, edx; Val
0x18000ca32  lea     rcx, [rsp+438h+var_3F8]; void *
0x18000ca37  mov     r8d, 1C8h; Size
0x18000ca3d  xor     ebx, ebx
0x18000ca3f  call    memset_0
0x18000ca44  xor     edx, edx; Val
0x18000ca46  lea     rcx, [rsp+438h+var_228]; void *
0x18000ca4e  mov     r8d, 208h; Size
0x18000ca54  call    memset_0
0x18000ca59  lea     r9, [rsp+438h+var_408]
0x18000ca5e  mov     [rsp+438h+var_400], rbx
0x18000ca63  mov     edx, 104h
0x18000ca68  lea     r8d, [rbx+2]
0x18000ca6c  lea     rcx, [rsp+438h+var_228]
0x18000ca74  call    cs:__imp_SdbGetPathSystemSdb
0x18000ca7a  test    eax, eax
0x18000ca7c  jz      loc_18000CB02
0x18000ca82  lea     rdx, [rsp+438h+var_228]
0x18000ca8a  lea     ecx, [rbx+3]
0x18000ca8d  call    cs:__imp_SdbInitDatabase
0x18000ca93  mov     rdi, rax
0x18000ca96  test    rax, rax
0x18000ca99  jz      short loc_18000CB02
0x18000ca9b  lea     rax, [rsp+438h+var_3F8]
0x18000caa0  xor     r9d, r9d
0x18000caa3  mov     [rsp+438h+var_410], rax
0x18000caa8  xor     r8d, r8d
0x18000caab  mov     rdx, rsi
0x18000caae  mov     dword ptr [rsp+438h+var_418], 2
0x18000cab6  mov     rcx, rdi
0x18000cab9  call    cs:__imp_SdbGetMatchingExe
0x18000cabf  mov     ebx, eax
0x18000cac1  test    eax, eax
0x18000cac3  jz      short loc_18000CAF9
0x18000cac5  mov     r8d, 500Fh
0x18000cacb  mov     [rsp+438h+var_418], 0
0x18000cad4  lea     r9, [rsp+438h+var_400]
0x18000cad9  mov     rcx, rdi
0x18000cadc  lea     rdx, [rsp+438h+var_3F8]
0x18000cae1  call    cs:__imp_SdbQueryFlagMask
0x18000cae7  mov     ebx, eax
0x18000cae9  test    eax, eax
0x18000caeb  jz      short loc_18000CAF9
0x18000caed  mov     rbx, [rsp+438h+var_400]
0x18000caf2  shr     rbx, 1Fh
0x18000caf6  and     ebx, 1
0x18000caf9  mov     rcx, rdi
0x18000cafc  call    cs:__imp_SdbReleaseDatabase
0x18000cb02  mov     eax, ebx
0x18000cb04  mov     rcx, [rsp+438h+var_18]
0x18000cb0c  xor     rcx, rsp; StackCookie
0x18000cb0f  call    __security_check_cookie
0x18000cb14  lea     r11, [rsp+438h+var_8]
0x18000cb1c  mov     rbx, [r11+20h]
0x18000cb20  mov     rsi, [r11+28h]
0x18000cb24  mov     rsp, r11
0x18000cb27  pop     rdi
0x18000cb28  retn
```
