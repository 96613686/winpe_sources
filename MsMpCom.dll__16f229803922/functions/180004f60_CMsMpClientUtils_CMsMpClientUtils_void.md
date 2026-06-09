# CMsMpClientUtils::~CMsMpClientUtils(void)

- ea: `0x180004f60`
- end: `0x180004fab`
- name: `??1CMsMpClientUtils@@UEAA@XZ`
- size: `75`
- prototype: `void __fastcall(CMsMpClientUtils *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002e20`

## callees

- `0x180004f60`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180004f9f`
- `KERNEL32!DeleteCriticalSection` at `0x180004f9f`
- `mpclient!MpHandleClose` at `0x180004f72`
- `mpclient!MpHandleClose` at `0x180004f81`
- `mpclient!MpHandleClose` at `0x180004f72`
- `mpclient!MpHandleClose` at `0x180004f81`

## pseudocode

```c
void __fastcall CMsMpClientUtils::~CMsMpClientUtils(CMsMpClientUtils *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  v2 = *((_QWORD *)this + 10);
  if ( v2 )
    MpHandleClose(v2);
  v3 = *((_QWORD *)this + 9);
  if ( v3 )
    MpHandleClose(v3);
  *(_QWORD *)this = &MP_CComObjectRootEx::`vftable';
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x180004f60  push    rbx
0x180004f62  sub     rsp, 20h
0x180004f66  mov     rbx, rcx
0x180004f69  mov     rcx, [rcx+50h]
0x180004f6d  test    rcx, rcx
0x180004f70  jz      short loc_180004F78
0x180004f72  call    cs:__imp_MpHandleClose
0x180004f78  mov     rcx, [rbx+48h]
0x180004f7c  test    rcx, rcx
0x180004f7f  jz      short loc_180004F87
0x180004f81  call    cs:__imp_MpHandleClose
0x180004f87  lea     rax, ??_7MP_CComObjectRootEx@@6B@; const MP_CComObjectRootEx::`vftable'
0x180004f8e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004f92  mov     [rbx], rax
0x180004f95  cmp     byte ptr [rcx+28h], 0
0x180004f99  jz      short loc_180004FA5
0x180004f9b  mov     byte ptr [rcx+28h], 0
0x180004f9f  call    cs:__imp_DeleteCriticalSection
0x180004fa5  add     rsp, 20h
0x180004fa9  pop     rbx
0x180004faa  retn
```
