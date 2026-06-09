# CAVIFileCF::CI::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180008a80`
- end: `0x180008b64`
- name: `?CreateInstance@CI@CAVIFileCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `228`
- prototype: `int(CAVIFileCF::CI *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005cb8`
- `0x180008a80`
- `0x180008db8`
- `0x18000d49c`
- `0x1800120bc`
- `0x18001574c`

## pseudocode

```c
__int64 __fastcall CAVIFileCF::CI::CreateInstance(
        struct IUnknown *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  struct IUnknownVtbl *lpVtbl; // r10

  lpVtbl = this[1].lpVtbl;
  if ( *(_OWORD *)&lpVtbl[1].Release == *(_OWORD *)&CLSID_AVIFile )
    return CAVIFile::Create(a2, a3, a4);
  if ( lpVtbl[1].Release == *(ULONG (__stdcall **)(IUnknown *))&CLSID_AVICmprsStream.Data1
    && lpVtbl[2].QueryInterface == *(HRESULT (__stdcall **)(IUnknown *, const IID *const, void **))CLSID_AVICmprsStream.Data4 )
  {
    return CAVICmpStream::Create(a2, a3, a4);
  }
  if ( lpVtbl[1].Release == *(ULONG (__stdcall **)(IUnknown *))&CLSID_ACMCmprs.Data1
    && lpVtbl[2].QueryInterface == *(HRESULT (__stdcall **)(IUnknown *, const IID *const, void **))CLSID_ACMCmprs.Data4 )
  {
    return CACMCmpStream::MakeInst(a2, a3, a4);
  }
  if ( lpVtbl[1].Release == *(ULONG (__stdcall **)(IUnknown *))&CLSID_AVIWaveFileReader.Data1
    && lpVtbl[2].QueryInterface == *(HRESULT (__stdcall **)(IUnknown *, const IID *const, void **))CLSID_AVIWaveFileReader.Data4 )
  {
    return WaveFileCreate(a2, a3, a4);
  }
  if ( lpVtbl[1].Release == *(ULONG (__stdcall **)(IUnknown *))&CLSID_EditStream.Data1
    && lpVtbl[2].QueryInterface == *(HRESULT (__stdcall **)(IUnknown *, const IID *const, void **))CLSID_EditStream.Data4 )
  {
    return CEditStream::NewInstance(this, a3, a4);
  }
  *a4 = 0;
  return 2147746290LL;
}

```

## disassembly

```asm
0x180008a80  push    rbx
0x180008a82  mov     r10, [rcx+8]
0x180008a86  mov     r11, r8
0x180008a89  mov     rbx, rdx
0x180008a8c  mov     rax, [r10+28h]
0x180008a90  cmp     rax, qword ptr cs:CLSID_AVIFile.Data1
0x180008a97  jnz     short loc_180008AB5
0x180008a99  mov     rax, [r10+30h]
0x180008a9d  cmp     rax, qword ptr cs:CLSID_AVIFile.Data4
0x180008aa4  jnz     short loc_180008AB5
0x180008aa6  mov     r8, r9; void **
0x180008aa9  mov     rdx, r11; struct _GUID *
0x180008aac  mov     rcx, rbx; struct IUnknown *
0x180008aaf  pop     rbx
0x180008ab0  jmp     ?Create@CAVIFile@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CAVIFile::Create(IUnknown *,_GUID const &,void * *)
0x180008ab5  mov     rax, [r10+28h]
0x180008ab9  cmp     rax, qword ptr cs:CLSID_AVICmprsStream.Data1
0x180008ac0  jnz     short loc_180008ADE
0x180008ac2  mov     rax, [r10+30h]
0x180008ac6  cmp     rax, qword ptr cs:CLSID_AVICmprsStream.Data4
0x180008acd  jnz     short loc_180008ADE
0x180008acf  mov     r8, r9; void **
0x180008ad2  mov     rdx, r11; struct _GUID *
0x180008ad5  mov     rcx, rbx; struct IUnknown *
0x180008ad8  pop     rbx
0x180008ad9  jmp     ?Create@CAVICmpStream@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CAVICmpStream::Create(IUnknown *,_GUID const &,void * *)
0x180008ade  mov     rax, [r10+28h]
0x180008ae2  cmp     rax, qword ptr cs:CLSID_ACMCmprs.Data1
0x180008ae9  jnz     short loc_180008B07
0x180008aeb  mov     rax, [r10+30h]
0x180008aef  cmp     rax, qword ptr cs:CLSID_ACMCmprs.Data4
0x180008af6  jnz     short loc_180008B07
0x180008af8  mov     r8, r9; void **
0x180008afb  mov     rdx, r11; struct _GUID *
0x180008afe  mov     rcx, rbx; struct IUnknown *
0x180008b01  pop     rbx
0x180008b02  jmp     ?MakeInst@CACMCmpStream@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CACMCmpStream::MakeInst(IUnknown *,_GUID const &,void * *)
0x180008b07  mov     rax, [r10+28h]
0x180008b0b  cmp     rax, qword ptr cs:CLSID_AVIWaveFileReader.Data1
0x180008b12  jnz     short loc_180008B30
0x180008b14  mov     rax, [r10+30h]
0x180008b18  cmp     rax, qword ptr cs:CLSID_AVIWaveFileReader.Data4
0x180008b1f  jnz     short loc_180008B30
0x180008b21  mov     r8, r9
0x180008b24  mov     rdx, r11
0x180008b27  mov     rcx, rbx; struct IUnknown *
0x180008b2a  pop     rbx
0x180008b2b  jmp     WaveFileCreate
0x180008b30  mov     rax, [r10+28h]
0x180008b34  cmp     rax, qword ptr cs:CLSID_EditStream.Data1
0x180008b3b  jnz     short loc_180008B56
0x180008b3d  mov     rax, [r10+30h]
0x180008b41  cmp     rax, qword ptr cs:CLSID_EditStream.Data4
0x180008b48  jnz     short loc_180008B56
0x180008b4a  mov     r8, r9; void **
0x180008b4d  mov     rdx, r11; struct _GUID *
0x180008b50  pop     rbx
0x180008b51  jmp     ?NewInstance@CEditStream@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CEditStream::NewInstance(IUnknown *,_GUID const &,void * *)
0x180008b56  mov     qword ptr [r9], 0
0x180008b5d  mov     eax, 800401F2h
0x180008b62  pop     rbx
0x180008b63  retn
```
