# LogPropertySanityCheck

- ea: `0x180005130`
- end: `0x18000527d`
- name: `LogPropertySanityCheck`
- size: `333`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005050`
- `0x180005420`

## callees

- `0x180005130`
- `0x18000a5f0`
- `0x18000b080`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180005220`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180005220`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800051b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800051b3`

## pseudocode

```c
__int64 __fastcall LogPropertySanityCheck(int a1, __int64 a2, unsigned int a3)
{
  unsigned int v5; // ebx
  _WORD *v6; // rax
  const wchar_t *v7; // rax
  const wchar_t *v8; // rdx
  unsigned int v9; // ebx
  __int64 v10; // rax
  DWORD nSize; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v12; // [rsp+24h] [rbp-44h]
  const wchar_t *v13; // [rsp+28h] [rbp-40h]
  WCHAR Buffer[16]; // [rsp+30h] [rbp-38h] BYREF

  if ( a1 != 1 || !a2 )
    return 0;
  if ( a3 < 0x48 )
    return 87;
  v5 = *(unsigned __int16 *)(a2 + 18) >> 1;
  v12 = v5;
  if ( v5 <= 2 )
    return 0;
  v6 = *(_WORD **)(a2 + 24);
  if ( *v6 != 92 || v6[1] != 92 )
    return 0;
  nSize = 16;
  if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
    return 87;
  if ( !nSize )
    return 87;
  v7 = (const wchar_t *)(*(_QWORD *)(a2 + 24) + 4LL);
  v13 = v7;
  v8 = v7;
  v9 = v5 - 2;
  v12 = v9;
  while ( v9 && *v7 && *v7 != 92 )
  {
    v13 = ++v7;
    v12 = --v9;
  }
  v10 = v7 - v8;
  if ( nSize == (_DWORD)v10 && !_wcsnicmp(Buffer, v8, (unsigned int)v10) )
    return 50;
  else
    return 0;
}

```

## disassembly

```asm
0x180005130  mov     [rsp+arg_0], rbx
0x180005135  mov     [rsp+arg_10], rsi
0x18000513a  push    rdi
0x18000513b  sub     rsp, 60h
0x18000513f  mov     rax, cs:__security_cookie
0x180005146  xor     rax, rsp
0x180005149  mov     [rsp+68h+var_18], rax
0x18000514e  mov     rdi, rdx
0x180005151  cmp     ecx, 1
0x180005154  jnz     loc_18000525C
0x18000515a  xor     esi, esi
0x18000515c  test    rdx, rdx
0x18000515f  jz      loc_18000525C
0x180005165  cmp     r8d, 48h ; 'H'
0x180005169  jnb     short loc_180005173
0x18000516b  lea     eax, [rcx+56h]
0x18000516e  jmp     loc_18000525E
0x180005173  movzx   ebx, word ptr [rdx+12h]
0x180005177  shr     ebx, 1
0x180005179  mov     [rsp+68h+var_44], ebx
0x18000517d  cmp     ebx, 2
0x180005180  jbe     loc_180005231
0x180005186  mov     rax, [rdx+18h]
0x18000518a  cmp     word ptr [rax], 5Ch ; '\'
0x18000518e  jnz     loc_180005231
0x180005194  cmp     word ptr [rax+2], 5Ch ; '\'
0x180005199  jnz     loc_180005231
0x18000519f  mov     [rsp+68h+nSize], 10h
0x1800051a7  lea     r8, [rsp+68h+nSize]; nSize
0x1800051ac  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x1800051b1  xor     ecx, ecx; NameType
0x1800051b3  call    cs:__imp_GetComputerNameExW
0x1800051b9  test    eax, eax
0x1800051bb  jnz     short loc_1800051C7
0x1800051bd  mov     eax, 57h ; 'W'
0x1800051c2  jmp     loc_18000525E
0x1800051c7  mov     ecx, [rsp+68h+nSize]
0x1800051cb  test    ecx, ecx
0x1800051cd  jnz     short loc_1800051D7
0x1800051cf  lea     eax, [rcx+57h]
0x1800051d2  jmp     loc_18000525E
0x1800051d7  mov     rax, [rdi+18h]
0x1800051db  add     rax, 4
0x1800051df  mov     [rsp+68h+var_40], rax
0x1800051e4  mov     rdx, rax; String2
0x1800051e7  add     ebx, 0FFFFFFFEh
0x1800051ea  mov     [rsp+68h+var_44], ebx
0x1800051ee  test    ebx, ebx
0x1800051f0  jz      short loc_18000520E
0x1800051f2  cmp     [rax], si
0x1800051f5  jz      short loc_18000520E
0x1800051f7  cmp     word ptr [rax], 5Ch ; '\'
0x1800051fb  jz      short loc_18000520E
0x1800051fd  add     rax, 2
0x180005201  mov     [rsp+68h+var_40], rax
0x180005206  dec     ebx
0x180005208  mov     [rsp+68h+var_44], ebx
0x18000520c  jmp     short loc_1800051EE
0x18000520e  sub     rax, rdx
0x180005211  sar     rax, 1
0x180005214  cmp     ecx, eax
0x180005216  jnz     short loc_180005231
0x180005218  mov     r8d, eax; MaxCount
0x18000521b  lea     rcx, [rsp+68h+Buffer]; String1
0x180005220  call    cs:__imp__wcsnicmp
0x180005226  test    eax, eax
0x180005228  jnz     short loc_180005231
0x18000522a  mov     eax, 32h ; '2'
0x18000522f  jmp     short loc_18000525E
0x180005231  jmp     short loc_18000525C
0x180005233  test    cs:byte_180012693, 4
0x18000523a  jz      short loc_180005255
0x18000523c  mov     r9d, eax
0x18000523f  mov     edx, 0Ah
0x180005244  mov     ecx, 21Ah
0x180005249  lea     r8, WPP_55e47224c694357c3f55ac6b1be9ef3f_Traceguids
0x180005250  call    WPP_SF_d
0x180005255  mov     eax, 57h ; 'W'
0x18000525a  jmp     short loc_18000525E
0x18000525c  xor     eax, eax
0x18000525e  mov     rcx, [rsp+68h+var_18]
0x180005263  xor     rcx, rsp; StackCookie
0x180005266  call    __security_check_cookie
0x18000526b  lea     r11, [rsp+68h+var_8]
0x180005270  mov     rbx, [r11+10h]
0x180005274  mov     rsi, [r11+20h]
0x180005278  mov     rsp, r11
0x18000527b  pop     rdi
0x18000527c  retn
```
