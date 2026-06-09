# CMsMpSimpleConfig::~CMsMpSimpleConfig(void)

- ea: `0x180004bbc`
- end: `0x180004c81`
- name: `??1CMsMpSimpleConfig@@UEAA@XZ`
- size: `197`
- prototype: `void __fastcall(CMsMpSimpleConfig *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002ed0`

## callees

- `0x180004bbc`
- `0x18000a010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180004c75`
- `KERNEL32!DeleteCriticalSection` at `0x180004c75`
- `mpclient!MpConfigUninitialize` at `0x180004c0b`
- `mpclient!MpConfigUninitialize` at `0x180004c57`
- `mpclient!MpConfigUninitialize` at `0x180004c0b`
- `mpclient!MpConfigUninitialize` at `0x180004c57`

## pseudocode

```c
void __fastcall CMsMpSimpleConfig::~CMsMpSimpleConfig(CMsMpSimpleConfig *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  v2 = *((_QWORD *)this + 10);
  if ( v2 )
  {
    if ( *(_DWORD *)(v2 + 8) == 1 )
    {
      *(_DWORD *)(v2 + 8) = 0;
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 8), 0xFFFFFFFF) > 1 )
    {
LABEL_6:
      *((_QWORD *)this + 10) = 0;
      goto LABEL_7;
    }
    (**(void (__fastcall ***)(__int64, __int64))v2)(v2, 1);
    goto LABEL_6;
  }
LABEL_7:
  if ( *((_QWORD *)this + 9) )
  {
    MpConfigUninitialize();
    *((_QWORD *)this + 9) = 0;
  }
  v3 = *((_QWORD *)this + 10);
  if ( v3 )
  {
    if ( *(_DWORD *)(v3 + 8) == 1 )
    {
      *(_DWORD *)(v3 + 8) = 0;
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 8), 0xFFFFFFFF) > 1 )
    {
      goto LABEL_14;
    }
    (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
  }
LABEL_14:
  if ( *((_QWORD *)this + 9) )
    MpConfigUninitialize();
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
0x180004bbc  push    rbx
0x180004bbe  sub     rsp, 20h
0x180004bc2  mov     rbx, rcx
0x180004bc5  mov     rcx, [rcx+50h]
0x180004bc9  test    rcx, rcx
0x180004bcc  jz      short loc_180004C04
0x180004bce  mov     eax, [rcx+8]
0x180004bd1  cmp     eax, 1
0x180004bd4  jnz     short loc_180004BDF
0x180004bd6  mov     dword ptr [rcx+8], 0
0x180004bdd  jmp     short loc_180004BEC
0x180004bdf  or      eax, 0FFFFFFFFh
0x180004be2  lock xadd [rcx+8], eax
0x180004be7  sub     eax, 1
0x180004bea  jg      short loc_180004BFC
0x180004bec  mov     rax, [rcx]
0x180004bef  mov     edx, 1
0x180004bf4  mov     rax, [rax]
0x180004bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bfc  mov     qword ptr [rbx+50h], 0
0x180004c04  cmp     qword ptr [rbx+48h], 0
0x180004c09  jz      short loc_180004C19
0x180004c0b  call    cs:__imp_MpConfigUninitialize
0x180004c11  mov     qword ptr [rbx+48h], 0
0x180004c19  mov     rcx, [rbx+50h]
0x180004c1d  test    rcx, rcx
0x180004c20  jz      short loc_180004C50
0x180004c22  mov     eax, [rcx+8]
0x180004c25  cmp     eax, 1
0x180004c28  jnz     short loc_180004C33
0x180004c2a  mov     dword ptr [rcx+8], 0
0x180004c31  jmp     short loc_180004C40
0x180004c33  or      eax, 0FFFFFFFFh
0x180004c36  lock xadd [rcx+8], eax
0x180004c3b  sub     eax, 1
0x180004c3e  jg      short loc_180004C50
0x180004c40  mov     rax, [rcx]
0x180004c43  mov     edx, 1
0x180004c48  mov     rax, [rax]
0x180004c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c50  cmp     qword ptr [rbx+48h], 0
0x180004c55  jz      short loc_180004C5D
0x180004c57  call    cs:__imp_MpConfigUninitialize
0x180004c5d  lea     rax, ??_7MP_CComObjectRootEx@@6B@; const MP_CComObjectRootEx::`vftable'
0x180004c64  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004c68  mov     [rbx], rax
0x180004c6b  cmp     byte ptr [rcx+28h], 0
0x180004c6f  jz      short loc_180004C7B
0x180004c71  mov     byte ptr [rcx+28h], 0
0x180004c75  call    cs:__imp_DeleteCriticalSection
0x180004c7b  add     rsp, 20h
0x180004c7f  pop     rbx
0x180004c80  retn
```
