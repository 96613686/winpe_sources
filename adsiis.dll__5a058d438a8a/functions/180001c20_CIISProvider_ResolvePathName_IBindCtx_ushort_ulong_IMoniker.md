# CIISProvider::ResolvePathName(IBindCtx *,ushort *,ulong *,IMoniker * *)

- ea: `0x180001c20`
- end: `0x180001cb9`
- name: `?ResolvePathName@CIISProvider@@QEAAJPEAUIBindCtx@@PEAGPEAKPEAPEAUIMoniker@@@Z`
- size: `153`
- prototype: `int(CIISProvider *__hidden this, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct IMoniker **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001b30`

## callees

- `0x180001c20`
- `0x180015664`
- `0x180019590`
- `0x18001984c`
- `0x18001e010`

## import_xrefs

- `ole32!CreatePointerMoniker` at `0x180001c73`
- `ole32!CreatePointerMoniker` at `0x180001c73`

## pseudocode

```c
__int64 __fastcall CIISProvider::ResolvePathName(
        CIISProvider *this,
        struct IBindCtx *a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        struct IMoniker **ppmk)
{
  HRESULT ObjectW; // ebx
  __int64 v8; // rax
  _BYTE v10[72]; // [rsp+20h] [rbp-48h] BYREF
  LPUNKNOWN punk; // [rsp+78h] [rbp+10h] BYREF

  punk = 0;
  CCredentials::Initialize((CCredentials *)v10, 0, 0, 0);
  *a4 = 0;
  ObjectW = GetObjectW(a3, (struct CCredentials *)v10, (void **)&punk);
  if ( ObjectW >= 0 )
  {
    ObjectW = CreatePointerMoniker(punk, ppmk);
    if ( ObjectW >= 0 )
    {
      v8 = -1;
      do
        ++v8;
      while ( a3[v8] );
      *a4 += v8;
    }
  }
  if ( punk )
    ((void (__fastcall *)(LPUNKNOWN))punk->lpVtbl->Release)(punk);
  CCredentials::~CCredentials((CCredentials *)v10);
  return (unsigned int)ObjectW;
}

```

## disassembly

```asm
0x180001c20  mov     [rsp+punk], rdx
0x180001c25  push    rbx
0x180001c26  push    rbp
0x180001c27  push    rsi
0x180001c28  push    rdi
0x180001c29  sub     rsp, 48h
0x180001c2d  mov     rdi, r9
0x180001c30  lea     rcx, [rsp+68h+var_48]; this
0x180001c35  mov     rsi, r8
0x180001c38  xor     ebp, ebp
0x180001c3a  xor     r9d, r9d; unsigned int
0x180001c3d  mov     [rsp+68h+punk], rbp
0x180001c42  xor     r8d, r8d; unsigned __int16 *
0x180001c45  xor     edx, edx; unsigned __int16 *
0x180001c47  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x180001c4c  lea     r8, [rsp+68h+punk]; void **
0x180001c51  mov     [rdi], ebp
0x180001c53  lea     rdx, [rsp+68h+var_48]; struct CCredentials *
0x180001c58  mov     rcx, rsi; unsigned __int16 *
0x180001c5b  call    ?GetObjectW@@YAJPEAGAEAVCCredentials@@PEAPEAX@Z; GetObjectW(ushort *,CCredentials &,void * *)
0x180001c60  mov     ebx, eax
0x180001c62  test    eax, eax
0x180001c64  js      short loc_180001C8E
0x180001c66  mov     rdx, [rsp+68h+ppmk]; ppmk
0x180001c6e  mov     rcx, [rsp+68h+punk]; punk
0x180001c73  call    cs:__imp_CreatePointerMoniker
0x180001c79  mov     ebx, eax
0x180001c7b  test    eax, eax
0x180001c7d  js      short loc_180001C8E
0x180001c7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001c83  inc     rax
0x180001c86  cmp     [rsi+rax*2], bp
0x180001c8a  jnz     short loc_180001C83
0x180001c8c  add     [rdi], eax
0x180001c8e  mov     rcx, [rsp+68h+punk]
0x180001c93  test    rcx, rcx
0x180001c96  jz      short loc_180001CA4
0x180001c98  mov     rax, [rcx]
0x180001c9b  mov     rax, [rax+10h]
0x180001c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ca4  lea     rcx, [rsp+68h+var_48]; this
0x180001ca9  call    ??1CCredentials@@QEAA@XZ; CCredentials::~CCredentials(void)
0x180001cae  mov     eax, ebx
0x180001cb0  add     rsp, 48h
0x180001cb4  pop     rdi
0x180001cb5  pop     rsi
0x180001cb6  pop     rbp
0x180001cb7  pop     rbx
0x180001cb8  retn
```
