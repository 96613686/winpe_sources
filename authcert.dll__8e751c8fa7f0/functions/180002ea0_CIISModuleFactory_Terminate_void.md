# CIISModuleFactory::Terminate(void)

- ea: `0x180002ea0`
- end: `0x180002f1b`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `123`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180002ea0`

## import_xrefs

- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002ebd`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002ebd`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180002eeb`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180002eeb`

## pseudocode

```c
void __fastcall CIISModuleFactory::Terminate(CIISModuleFactory *this)
{
  void *v1; // rbx

  v1 = s_pCertmapAuthProvider;
  if ( s_pCertmapAuthProvider )
  {
    BUFFER::~BUFFER((BUFFER *)((char *)s_pCertmapAuthProvider + 16));
    operator delete(v1);
    s_pCertmapAuthProvider = 0;
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
0x180002ea0  mov     [rsp+arg_0], rbx
0x180002ea5  push    rdi
0x180002ea6  sub     rsp, 20h
0x180002eaa  mov     rbx, cs:?s_pCertmapAuthProvider@@3PEAVCERTMAP_AUTH_PROVIDER@@EA; CERTMAP_AUTH_PROVIDER * s_pCertmapAuthProvider
0x180002eb1  mov     rdi, rcx
0x180002eb4  test    rbx, rbx
0x180002eb7  jz      short loc_180002ED6
0x180002eb9  lea     rcx, [rbx+10h]
0x180002ebd  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002ec3  mov     rcx, rbx; Block
0x180002ec6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ecb  mov     cs:?s_pCertmapAuthProvider@@3PEAVCERTMAP_AUTH_PROVIDER@@EA, 0; CERTMAP_AUTH_PROVIDER * s_pCertmapAuthProvider
0x180002ed6  mov     rcx, cs:g_pDebug
0x180002edd  test    rcx, rcx
0x180002ee0  jz      short loc_180002EF8
0x180002ee2  cmp     dword ptr [rcx+280h], 0
0x180002ee9  jz      short loc_180002EF8
0x180002eeb  call    cs:__imp_PuDeleteDebugPrintsObject
0x180002ef1  mov     cs:g_pDebug, rax
0x180002ef8  test    rdi, rdi
0x180002efb  jz      short loc_180002F10
0x180002efd  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x180002f04  mov     rcx, rdi; Block
0x180002f07  mov     [rdi+8], rax
0x180002f0b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002f10  mov     rbx, [rsp+28h+arg_0]
0x180002f15  add     rsp, 20h
0x180002f19  pop     rdi
0x180002f1a  retn
```
