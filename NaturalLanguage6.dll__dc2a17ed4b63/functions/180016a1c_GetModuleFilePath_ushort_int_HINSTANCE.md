# GetModuleFilePath(ushort *,int,HINSTANCE__ *)

- ea: `0x180016a1c`
- end: `0x180016b35`
- name: `?GetModuleFilePath@@YAHPEAGHPEAUHINSTANCE__@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(unsigned __int16 *, signed int, HINSTANCE)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180001dd0`
- `0x180016540`
- `0x18001681c`
- `0x18002e1b0`

## callees

- `0x180016258`
- `0x180016a1c`
- `0x18009e300`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x180016a91`
- `msvcrt!_wsplitpath_s` at `0x180016a91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180016a53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180016a53`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetModuleFilePath(unsigned __int16 *a1, signed int a2, HINSTANCE a3)
{
  unsigned __int64 v3; // rdi
  unsigned __int64 v5; // rdx
  __int64 v6; // r8
  wchar_t *v7; // r9
  unsigned __int64 v8; // rcx
  unsigned int v9; // edi
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // r8
  wchar_t Drive[8]; // [rsp+50h] [rbp-238h] BYREF
  wchar_t Dir[264]; // [rsp+60h] [rbp-228h] BYREF

  v3 = a2;
  if ( GetModuleFileNameW(g_hInst, a1, a2) )
  {
    _wsplitpath_s(a1, Drive, 4u, Dir, 0x105u, 0, 0, 0, 0);
    v5 = v3;
    if ( v3 > 0x7FFFFFFF )
    {
      *a1 = 0;
    }
    else
    {
      v6 = 2147483646;
      v7 = Drive;
      v8 = v3;
      v9 = 1;
      v10 = a1;
      do
      {
        if ( !v6 )
          break;
        if ( !*v7 )
          break;
        *v10++ = *v7++;
        --v6;
        --v8;
      }
      while ( v8 );
      v11 = v10 - 1;
      if ( v8 )
        v11 = v10;
      *v11 = 0;
      if ( v8 && StringCchCatW(a1, v5, Dir) >= 0 )
        return v9;
    }
    return 0;
  }
  *a1 = 0;
  return 0;
}

```

## disassembly

```asm
0x180016a1c  mov     [rsp+arg_10], rbx
0x180016a21  mov     [rsp+arg_18], rsi
0x180016a26  push    rdi
0x180016a27  sub     rsp, 280h
0x180016a2e  mov     rax, cs:__security_cookie
0x180016a35  xor     rax, rsp
0x180016a38  mov     [rsp+288h+var_18], rax
0x180016a40  movsxd  rdi, edx
0x180016a43  mov     rbx, rcx
0x180016a46  mov     rdx, rcx; lpFilename
0x180016a49  mov     r8d, edi; nSize
0x180016a4c  mov     rcx, cs:g_hInst; hModule
0x180016a53  call    cs:__imp_GetModuleFileNameW
0x180016a59  xor     esi, esi
0x180016a5b  test    eax, eax
0x180016a5d  jz      loc_180016B29
0x180016a63  mov     [rsp+288h+ExtCount], rsi; ExtCount
0x180016a68  lea     r9, [rsp+288h+Dir]; Dir
0x180016a6d  mov     [rsp+288h+Ext], rsi; Ext
0x180016a72  lea     r8d, [rsi+4]; DriveCount
0x180016a76  mov     [rsp+288h+FilenameCount], rsi; FilenameCount
0x180016a7b  lea     rdx, [rsp+288h+Drive]; Drive
0x180016a80  mov     [rsp+288h+Filename], rsi; Filename
0x180016a85  mov     rcx, rbx; FullPath
0x180016a88  mov     [rsp+288h+DirCount], 105h; DirCount
0x180016a91  call    cs:__imp__wsplitpath_s
0x180016a97  mov     rdx, rdi; unsigned __int64
0x180016a9a  cmp     rdi, 7FFFFFFFh
0x180016aa1  ja      loc_180016B30
0x180016aa7  mov     r8d, 7FFFFFFEh
0x180016aad  lea     r9, [rsp+288h+Drive]
0x180016ab2  mov     rcx, rdx
0x180016ab5  lea     edi, [rsi+1]
0x180016ab8  mov     rax, rbx
0x180016abb  test    r8, r8
0x180016abe  jz      short loc_180016ADE
0x180016ac0  movzx   r10d, word ptr [r9]
0x180016ac4  test    r10w, r10w
0x180016ac8  jz      short loc_180016ADE
0x180016aca  mov     [rax], r10w
0x180016ace  add     r9, 2
0x180016ad2  add     rax, 2
0x180016ad6  sub     r8, rdi
0x180016ad9  sub     rcx, rdi
0x180016adc  jnz     short loc_180016ABB
0x180016ade  test    rcx, rcx
0x180016ae1  lea     r8, [rax-2]
0x180016ae5  cmovnz  r8, rax
0x180016ae9  mov     [r8], si
0x180016aed  jz      short loc_180016B00
0x180016aef  lea     r8, [rsp+288h+Dir]; unsigned __int16 *
0x180016af4  mov     rcx, rbx; unsigned __int16 *
0x180016af7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016afc  test    eax, eax
0x180016afe  jns     short loc_180016B02
0x180016b00  mov     edi, esi
0x180016b02  mov     eax, edi
0x180016b04  mov     rcx, [rsp+288h+var_18]
0x180016b0c  xor     rcx, rsp; StackCookie
0x180016b0f  call    __security_check_cookie
0x180016b14  lea     r11, [rsp+288h+var_8]
0x180016b1c  mov     rbx, [r11+20h]
0x180016b20  mov     rsi, [r11+28h]
0x180016b24  mov     rsp, r11
0x180016b27  pop     rdi
0x180016b28  retn
0x180016b29  mov     [rbx], si
0x180016b2c  xor     eax, eax
0x180016b2e  jmp     short loc_180016B04
0x180016b30  mov     [rbx], si
0x180016b33  jmp     short loc_180016B00
```
