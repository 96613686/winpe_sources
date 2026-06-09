# std::unique_ptr<ProvPackageInfo,std::default_delete<ProvPackageInfo>>::_Delete(void)

- ea: `0x18001ec4c`
- end: `0x18001ec78`
- name: `?_Delete@?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@AEAAXXZ`
- size: `44`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800108c4`
- `0x180010b5c`
- `0x180010c10`
- `0x180010d98`
- `0x180010eb0`
- `0x180010f3c`
- `0x180010ff0`
- `0x18001ecc0`
- `0x180021d3c`
- `0x180022f8c`
- `0x1800232d8`
- `0x1800235dc`
- `0x1800258e0`
- `0x18002ab65`

## callees

- `0x180011248`
- `0x18001ec4c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001ec65`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ec65`

## pseudocode

```c
void __fastcall std::unique_ptr<ProvPackageInfo>::_Delete(ProvPackageInfo **a1)
{
  ProvPackageInfo *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    ProvPackageInfo::~ProvPackageInfo(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18001ec4c  push    rbx
0x18001ec4e  sub     rsp, 20h
0x18001ec52  mov     rbx, [rcx]
0x18001ec55  test    rbx, rbx
0x18001ec58  jz      short loc_18001EC71
0x18001ec5a  mov     rcx, rbx; this
0x18001ec5d  call    ??1ProvPackageInfo@@QEAA@XZ; ProvPackageInfo::~ProvPackageInfo(void)
0x18001ec62  mov     rcx, rbx
0x18001ec65  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ec6c  nop     dword ptr [rax+rax+00h]
0x18001ec71  add     rsp, 20h
0x18001ec75  pop     rbx
0x18001ec76  retn
```
