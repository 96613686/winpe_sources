# CIISModuleFactory::Terminate(void)

- ea: `0x1800038c0`
- end: `0x180003944`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `132`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x1800038c0`

## import_xrefs

- `iisutil!PuDeleteDebugPrintsObject` at `0x180003919`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180003919`
- `CRYPTSP!CryptReleaseContext` at `0x1800038f3`
- `CRYPTSP!CryptReleaseContext` at `0x1800038f3`

## pseudocode

```c
void __fastcall CIISModuleFactory::Terminate(CIISModuleFactory *this)
{
  if ( s_pBasicAuthProvider )
  {
    operator delete(s_pBasicAuthProvider);
    s_pBasicAuthProvider = 0;
  }
  if ( TOKEN_KEY::sm_hCryptProv )
  {
    CryptReleaseContext(TOKEN_KEY::sm_hCryptProv, 0);
    TOKEN_KEY::sm_hCryptProv = 0;
  }
  if ( g_pDebug && *(_DWORD *)(g_pDebug + 640) )
    g_pDebug = PuDeleteDebugPrintsObject();
  if ( this )
  {
    *((_QWORD *)this + 1) = &CHttpModule::`vftable';
    operator delete(this);
  }
}

```

## disassembly

```asm
0x1800038c0  push    rbx
0x1800038c2  sub     rsp, 20h
0x1800038c6  mov     rbx, rcx
0x1800038c9  mov     rcx, cs:?s_pBasicAuthProvider@@3PEAVBASIC_AUTH_PROVIDER@@EA; Block
0x1800038d0  test    rcx, rcx
0x1800038d3  jz      short loc_1800038E5
0x1800038d5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800038da  mov     cs:?s_pBasicAuthProvider@@3PEAVBASIC_AUTH_PROVIDER@@EA, 0; BASIC_AUTH_PROVIDER * s_pBasicAuthProvider
0x1800038e5  mov     rcx, cs:?sm_hCryptProv@TOKEN_KEY@@0_KA; hProv
0x1800038ec  test    rcx, rcx
0x1800038ef  jz      short loc_180003904
0x1800038f1  xor     edx, edx; dwFlags
0x1800038f3  call    cs:__imp_CryptReleaseContext
0x1800038f9  mov     cs:?sm_hCryptProv@TOKEN_KEY@@0_KA, 0; unsigned __int64 TOKEN_KEY::sm_hCryptProv
0x180003904  mov     rcx, cs:g_pDebug
0x18000390b  test    rcx, rcx
0x18000390e  jz      short loc_180003926
0x180003910  cmp     dword ptr [rcx+280h], 0
0x180003917  jz      short loc_180003926
0x180003919  call    cs:__imp_PuDeleteDebugPrintsObject
0x18000391f  mov     cs:g_pDebug, rax
0x180003926  test    rbx, rbx
0x180003929  jz      short loc_18000393E
0x18000392b  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x180003932  mov     rcx, rbx; Block
0x180003935  mov     [rbx+8], rax
0x180003939  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000393e  add     rsp, 20h
0x180003942  pop     rbx
0x180003943  retn
```
