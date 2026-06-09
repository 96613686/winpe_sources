# DoInfInstallA(_ADVPACKARGSA *)

- ea: `0x180005dc0`
- end: `0x180005e96`
- name: `?DoInfInstallA@@YAJPEAU_ADVPACKARGSA@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(struct _ADVPACKARGSA *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180005dc0`
- `0x180005ea0`
- `0x1800173a0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180005e60`
- `KERNEL32!LocalFree` at `0x180005e6a`
- `KERNEL32!LocalFree` at `0x180005e74`
- `KERNEL32!LocalFree` at `0x180005e7e`
- `KERNEL32!LocalFree` at `0x180005e60`
- `KERNEL32!LocalFree` at `0x180005e6a`
- `KERNEL32!LocalFree` at `0x180005e74`
- `KERNEL32!LocalFree` at `0x180005e7e`

## pseudocode

```c
__int64 __fastcall DoInfInstallA(struct _ADVPACKARGSA *a1)
{
  __int64 v1; // rax
  const CHAR *v3; // rcx
  int v4; // ebx
  __int64 v6; // [rsp+20h] [rbp-40h] BYREF
  HLOCAL v7; // [rsp+28h] [rbp-38h]
  HLOCAL v8[2]; // [rsp+30h] [rbp-30h]
  HLOCAL hMem[2]; // [rsp+40h] [rbp-20h]
  __int64 v10; // [rsp+50h] [rbp-10h]

  v10 = 0;
  v1 = *(_QWORD *)a1;
  *(_OWORD *)hMem = 0;
  v7 = 0;
  v6 = v1;
  LOWORD(hMem[1]) = *((_WORD *)a1 + 20);
  HIDWORD(hMem[1]) = *((_DWORD *)a1 + 11);
  LODWORD(v1) = *((_DWORD *)a1 + 12);
  v3 = (const CHAR *)*((_QWORD *)a1 + 1);
  *(_OWORD *)v8 = 0;
  LODWORD(v10) = v1;
  v4 = ThunkToUnicode(v3);
  if ( v4 >= 0 )
  {
    v4 = ThunkToUnicode(*((LPCCH *)a1 + 2));
    if ( v4 >= 0 )
    {
      v4 = ThunkToUnicode(*((LPCCH *)a1 + 3));
      if ( v4 >= 0 )
      {
        v4 = ThunkToUnicode(*((LPCCH *)a1 + 4));
        if ( v4 >= 0 )
        {
          v4 = DoInfInstallW((struct _ADVPACKARGSW *)&v6);
          LocalFree(hMem[0]);
        }
        LocalFree(v8[1]);
      }
      LocalFree(v8[0]);
    }
    LocalFree(v7);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180005dc0  mov     [rsp-8+arg_0], rbx; DoInfInstall
0x180005dc5  mov     [rsp-8+arg_8], rdi
0x180005dca  push    rbp
0x180005dcb  mov     rbp, rsp
0x180005dce  sub     rsp, 60h
0x180005dd2  xor     eax, eax
0x180005dd4  lea     rdx, [rbp+var_38]
0x180005dd8  mov     [rbp+var_10], rax
0x180005ddc  xorps   xmm0, xmm0
0x180005ddf  mov     rax, [rcx]
0x180005de2  mov     rdi, rcx
0x180005de5  movups  xmmword ptr [rbp+hMem], xmm0
0x180005de9  movups  xmmword ptr [rbp-40h], xmm0
0x180005ded  mov     [rbp+var_40], rax
0x180005df1  movzx   eax, word ptr [rcx+28h]
0x180005df5  mov     word ptr [rbp+hMem+8], ax
0x180005df9  mov     eax, [rcx+2Ch]
0x180005dfc  mov     dword ptr [rbp+hMem+0Ch], eax
0x180005dff  mov     eax, [rcx+30h]
0x180005e02  mov     rcx, [rcx+8]; lpMultiByteStr
0x180005e06  movups  xmmword ptr [rbp+var_30], xmm0
0x180005e0a  mov     dword ptr [rbp+var_10], eax
0x180005e0d  call    ThunkToUnicode
0x180005e12  mov     ebx, eax
0x180005e14  test    eax, eax
0x180005e16  js      short loc_180005E84
0x180005e18  mov     rcx, [rdi+10h]; lpMultiByteStr
0x180005e1c  lea     rdx, [rbp+var_30]
0x180005e20  call    ThunkToUnicode
0x180005e25  mov     ebx, eax
0x180005e27  test    eax, eax
0x180005e29  js      short loc_180005E7A
0x180005e2b  mov     rcx, [rdi+18h]; lpMultiByteStr
0x180005e2f  lea     rdx, [rbp+var_30+8]
0x180005e33  call    ThunkToUnicode
0x180005e38  mov     ebx, eax
0x180005e3a  test    eax, eax
0x180005e3c  js      short loc_180005E70
0x180005e3e  mov     rcx, [rdi+20h]; lpMultiByteStr
0x180005e42  lea     rdx, [rbp+hMem]
0x180005e46  call    ThunkToUnicode
0x180005e4b  mov     ebx, eax
0x180005e4d  test    eax, eax
0x180005e4f  js      short loc_180005E66
0x180005e51  lea     rcx, [rbp+var_40]; struct _ADVPACKARGSW *
0x180005e55  call    ?DoInfInstallW@@YAJPEAU_ADVPACKARGSW@@@Z; DoInfInstallW(_ADVPACKARGSW *)
0x180005e5a  mov     rcx, [rbp+hMem]; hMem
0x180005e5e  mov     ebx, eax
0x180005e60  call    cs:__imp_LocalFree
0x180005e66  mov     rcx, [rbp+var_30+8]; hMem
0x180005e6a  call    cs:__imp_LocalFree
0x180005e70  mov     rcx, [rbp+var_30]; hMem
0x180005e74  call    cs:__imp_LocalFree
0x180005e7a  mov     rcx, [rbp+var_38]; hMem
0x180005e7e  call    cs:__imp_LocalFree
0x180005e84  mov     rdi, [rsp+60h+arg_8]
0x180005e89  mov     eax, ebx
0x180005e8b  mov     rbx, [rsp+60h+arg_0]
0x180005e90  add     rsp, 60h
0x180005e94  pop     rbp
0x180005e95  retn
```
