# std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>::~unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>(void)

- ea: `0x14000f9a8`
- end: `0x14000f9d8`
- name: `??1?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400176d6`

## callees

- `0x1400088f4`
- `0x14000f9a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f9bf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f9bf`

## pseudocode

```c
void __fastcall std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>::~unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  HMODULE v2; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v2 = (HMODULE)v1[2];
    if ( v2 )
      FreeLibrary(v2);
    operator delete(v1, 0x18u);
  }
}

```

## disassembly

```asm
0x14000f9a8  push    rbx
0x14000f9aa  sub     rsp, 20h
0x14000f9ae  mov     rbx, [rcx]
0x14000f9b1  test    rbx, rbx
0x14000f9b4  jz      short loc_14000F9D2
0x14000f9b6  mov     rcx, [rbx+10h]; hLibModule
0x14000f9ba  test    rcx, rcx
0x14000f9bd  jz      short loc_14000F9C5
0x14000f9bf  call    cs:__imp_FreeLibrary
0x14000f9c5  mov     edx, 18h; unsigned __int64
0x14000f9ca  mov     rcx, rbx; void *
0x14000f9cd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f9d2  add     rsp, 20h
0x14000f9d6  pop     rbx
0x14000f9d7  retn
```
