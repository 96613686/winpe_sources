# CIISModuleFactory::Terminate(void)

- ea: `0x1800033e0`
- end: `0x180003464`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `132`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x1800033e0`

## import_xrefs

- `iisutil!PuDeleteDebugPrintsObject` at `0x180003439`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180003439`
- `CRYPTSP!CryptReleaseContext` at `0x180003413`
- `CRYPTSP!CryptReleaseContext` at `0x180003413`

## pseudocode

```c
void __fastcall CIISModuleFactory::Terminate(CIISModuleFactory *this)
{
  if ( s_pIisCertmapAuthProvider )
  {
    operator delete(s_pIisCertmapAuthProvider);
    s_pIisCertmapAuthProvider = 0;
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
0x1800033e0  push    rbx
0x1800033e2  sub     rsp, 20h
0x1800033e6  mov     rbx, rcx
0x1800033e9  mov     rcx, cs:?s_pIisCertmapAuthProvider@@3PEAVIISCERTMAP_AUTH_PROVIDER@@EA; Block
0x1800033f0  test    rcx, rcx
0x1800033f3  jz      short loc_180003405
0x1800033f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800033fa  mov     cs:?s_pIisCertmapAuthProvider@@3PEAVIISCERTMAP_AUTH_PROVIDER@@EA, 0; IISCERTMAP_AUTH_PROVIDER * s_pIisCertmapAuthProvider
0x180003405  mov     rcx, cs:?sm_hCryptProv@TOKEN_KEY@@0_KA; hProv
0x18000340c  test    rcx, rcx
0x18000340f  jz      short loc_180003424
0x180003411  xor     edx, edx; dwFlags
0x180003413  call    cs:__imp_CryptReleaseContext
0x180003419  mov     cs:?sm_hCryptProv@TOKEN_KEY@@0_KA, 0; unsigned __int64 TOKEN_KEY::sm_hCryptProv
0x180003424  mov     rcx, cs:g_pDebug
0x18000342b  test    rcx, rcx
0x18000342e  jz      short loc_180003446
0x180003430  cmp     dword ptr [rcx+280h], 0
0x180003437  jz      short loc_180003446
0x180003439  call    cs:__imp_PuDeleteDebugPrintsObject
0x18000343f  mov     cs:g_pDebug, rax
0x180003446  test    rbx, rbx
0x180003449  jz      short loc_18000345E
0x18000344b  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x180003452  mov     rcx, rbx; Block
0x180003455  mov     [rbx+8], rax
0x180003459  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000345e  add     rsp, 20h
0x180003462  pop     rbx
0x180003463  retn
```
