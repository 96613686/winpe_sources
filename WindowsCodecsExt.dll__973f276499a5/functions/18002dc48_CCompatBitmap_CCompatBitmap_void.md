# CCompatBitmap::~CCompatBitmap(void)

- ea: `0x18002dc48`
- end: `0x18002dcd4`
- name: `??1CCompatBitmap@@UEAA@XZ`
- size: `140`
- prototype: `void __fastcall(CCompatBitmap *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002ddf0`
- `0x18002ea3c`

## callees

- `0x180008c00`
- `0x18002dc48`
- `0x18002ebec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002dc87`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002dc87`

## pseudocode

```c
void __fastcall CCompatBitmap::~CCompatBitmap(CCompatBitmap *this)
{
  CMILCOMBase *v2; // rcx

  *(_QWORD *)this = &CCompatBitmap::`vftable'{for `CMILCOMBase'};
  *((_QWORD *)this + 2) = &CCompatBitmap::`vftable'{for `IMILBitmap'};
  *((_QWORD *)this + 3) = &CCompatBitmap::`vftable'{for `IWICBitmap'};
  *((_QWORD *)this + 4) = &CCompatBitmap::`vftable'{for `CMILResourceCache'};
  free(*((void **)this + 19));
  v2 = (CMILCOMBase *)*((_QWORD *)this + 17);
  if ( v2 )
  {
    CMILCOMBase::InternalRelease(v2);
    *((_QWORD *)this + 17) = 0;
  }
  CMILResourceCache::~CMILResourceCache((CCompatBitmap *)((char *)this + 32));
  *(_QWORD *)this = &CMILCOMBase::`vftable';
  _InterlockedDecrement(&g_cActiveObjects);
}

```

## disassembly

```asm
0x18002dc48  mov     [rsp+arg_0], rbx
0x18002dc4d  push    rdi
0x18002dc4e  sub     rsp, 20h
0x18002dc52  lea     rax, ??_7CCompatBitmap@@6BCMILCOMBase@@@; const CCompatBitmap::`vftable'{for `CMILCOMBase'}
0x18002dc59  mov     rbx, rcx
0x18002dc5c  mov     [rcx], rax
0x18002dc5f  lea     rax, ??_7CCompatBitmap@@6BIMILBitmap@@@; const CCompatBitmap::`vftable'{for `IMILBitmap'}
0x18002dc66  mov     [rcx+10h], rax
0x18002dc6a  lea     rax, ??_7CCompatBitmap@@6BIWICBitmap@@@; const CCompatBitmap::`vftable'{for `IWICBitmap'}
0x18002dc71  mov     [rcx+18h], rax
0x18002dc75  lea     rax, ??_7CCompatBitmap@@6BCMILResourceCache@@@; const CCompatBitmap::`vftable'{for `CMILResourceCache'}
0x18002dc7c  mov     [rcx+20h], rax
0x18002dc80  mov     rcx, [rcx+98h]; Block
0x18002dc87  call    cs:__imp_free
0x18002dc8d  mov     rcx, [rbx+88h]; this
0x18002dc94  test    rcx, rcx
0x18002dc97  jz      short loc_18002DCA9
0x18002dc99  call    ?InternalRelease@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalRelease(void)
0x18002dc9e  mov     qword ptr [rbx+88h], 0
0x18002dca9  mov     eax, [rbx+90h]
0x18002dcaf  lea     rcx, [rbx+20h]; this
0x18002dcb3  call    ??1CMILResourceCache@@IEAA@XZ; CMILResourceCache::~CMILResourceCache(void)
0x18002dcb8  lea     rax, ??_7CMILCOMBase@@6B@; const CMILCOMBase::`vftable'
0x18002dcbf  mov     [rbx], rax
0x18002dcc2  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18002dcc9  mov     rbx, [rsp+28h+arg_0]
0x18002dcce  add     rsp, 20h
0x18002dcd2  pop     rdi
0x18002dcd3  retn
```
