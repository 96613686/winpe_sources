# RfbShellFolderBase::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180014fa0`
- end: `0x1800150b9`
- name: `?CreateViewObject@RfbShellFolderBase@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `281`
- prototype: `__int64 __fastcall(unsigned __int64 this, HWND, const struct _GUID *, IShellView **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800070cc`
- `0x180014fa0`
- `0x180019010`

## import_xrefs

- `SHELL32!__imp_SHCreateShellFolderViewEx` at `0x180015052`
- `SHELL32!__imp_SHCreateShellFolderViewEx` at `0x180015052`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RfbShellFolderBase::CreateViewObject(
        unsigned __int64 this,
        HWND a2,
        const struct _GUID *a3,
        IShellView **a4)
{
  HRESULT v6; // eax
  unsigned int v7; // edi
  IShellView *v8; // rcx
  CSFV pcsfv; // [rsp+20h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  IShellView *ppsv; // [rsp+88h] [rbp+28h] BYREF

  if ( a4 )
  {
    *a4 = 0;
    if ( *(_OWORD *)a3 == *(_OWORD *)&IID_IShellView )
    {
      *(_QWORD *)&pcsfv.cbSize = 56;
      pcsfv.pshf = (IShellFolder *)(this & -(__int64)(this != 8));
      memset(&pcsfv.psvOuter, 0, 40);
      ppsv = 0;
      v6 = SHCreateShellFolderViewEx(&pcsfv, &ppsv);
      v7 = v6;
      if ( v6 >= 0 )
      {
        *a4 = ppsv;
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x295,
          (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
          (const char *)(unsigned int)v6,
          pcsfv.cbSize);
        v8 = ppsv;
        if ( ppsv )
        {
          ppsv = 0;
          ((void (__fastcall *)(IShellView *))v8->lpVtbl->Release)(v8);
        }
        return v7;
      }
    }
    else
    {
      return 2147500034LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x281,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
      (const char *)0x80070057LL,
      pcsfv.cbSize);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180014fa0  mov     [rsp-8+arg_0], rbx
0x180014fa5  mov     [rsp-8+arg_8], rdi
0x180014faa  push    rbp
0x180014fab  mov     rbp, rsp
0x180014fae  sub     rsp, 60h
0x180014fb2  mov     rbx, r9
0x180014fb5  mov     rdx, rcx
0x180014fb8  test    r9, r9
0x180014fbb  jnz     short loc_180014FE1
0x180014fbd  mov     rcx, [rbp+8]; this
0x180014fc1  mov     ebx, 80070057h
0x180014fc6  mov     r9d, ebx; char *
0x180014fc9  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x180014fd0  mov     edx, 281h; void *
0x180014fd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014fda  mov     eax, ebx
0x180014fdc  jmp     loc_1800150A9
0x180014fe1  mov     qword ptr [r9], 0
0x180014fe8  mov     rax, [r8]
0x180014feb  cmp     rax, qword ptr cs:IID_IShellView.Data1
0x180014ff2  jnz     loc_1800150A4
0x180014ff8  mov     rax, [r8+8]
0x180014ffc  cmp     rax, qword ptr cs:IID_IShellView.Data4
0x180015003  jnz     loc_1800150A4
0x180015009  mov     qword ptr [rbp+pcsfv.cbSize], 38h ; '8'
0x180015011  mov     qword ptr [rbp+pcsfv.lEvents], 0
0x180015019  mov     qword ptr [rbp+pcsfv.fvm], 0
0x180015021  lea     rax, [rcx-8]
0x180015025  neg     rax
0x180015028  sbb     rcx, rcx
0x18001502b  and     rcx, rdx
0x18001502e  mov     [rbp+pcsfv.pshf], rcx
0x180015032  xorps   xmm0, xmm0
0x180015035  movdqu  xmmword ptr [rbp+pcsfv.psvOuter], xmm0
0x18001503a  mov     [rbp+pcsfv.pfnCallback], 0
0x180015042  mov     [rbp+ppsv], 0
0x18001504a  lea     rdx, [rbp+ppsv]; ppsv
0x18001504e  lea     rcx, [rbp+pcsfv]; pcsfv
0x180015052  call    cs:__imp_SHCreateShellFolderViewEx
0x180015058  mov     edi, eax
0x18001505a  test    eax, eax
0x18001505c  jns     short loc_180015099
0x18001505e  mov     rcx, [rbp+8]; this
0x180015062  mov     r9d, eax; char *
0x180015065  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x18001506c  mov     edx, 295h; void *
0x180015071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015076  nop
0x180015077  mov     rcx, [rbp+ppsv]
0x18001507b  test    rcx, rcx
0x18001507e  jz      short loc_180015095
0x180015080  mov     [rbp+ppsv], 0
0x180015088  mov     rax, [rcx]
0x18001508b  mov     rax, [rax+10h]
0x18001508f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015094  nop
0x180015095  mov     eax, edi
0x180015097  jmp     short loc_1800150A9
0x180015099  mov     rax, [rbp+ppsv]
0x18001509d  mov     [rbx], rax
0x1800150a0  xor     eax, eax
0x1800150a2  jmp     short loc_1800150A9
0x1800150a4  mov     eax, 80004002h
0x1800150a9  mov     rbx, [rsp+60h+arg_0]
0x1800150ae  mov     rdi, [rsp+60h+arg_8]
0x1800150b3  add     rsp, 60h
0x1800150b7  pop     rbp
0x1800150b8  retn
```
