# KERBEROS_INFO::~KERBEROS_INFO(void)

- ea: `0x180001c34`
- end: `0x180001ca1`
- name: `??1KERBEROS_INFO@@QEAA@XZ`
- size: `109`
- prototype: `void __fastcall(KERBEROS_INFO *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002084`
- `0x180003ed4`
- `0x180006120`

## callees

- `0x180001c34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001c66`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001c66`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001c7e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001c8b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001c7e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001c8b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001c9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180001c49`
- `OLEAUT32!__imp_SysFreeString` at `0x180001c49`

## pseudocode

```c
void __fastcall KERBEROS_INFO::~KERBEROS_INFO(KERBEROS_INFO *this)
{
  OLECHAR *v2; // rcx
  HMODULE v3; // rcx

  v2 = (OLECHAR *)*((_QWORD *)this + 70);
  if ( v2 )
  {
    SysFreeString(v2);
    *((_QWORD *)this + 70) = 0;
  }
  v3 = (HMODULE)*((_QWORD *)this + 71);
  if ( v3 )
  {
    FreeLibrary(v3);
    *((_QWORD *)this + 71) = 0;
  }
  STRU::~STRU((KERBEROS_INFO *)((char *)this + 376));
  STRU::~STRU((KERBEROS_INFO *)((char *)this + 192));
  STRU::~STRU((KERBEROS_INFO *)((char *)this + 8));
}

```

## disassembly

```asm
0x180001c34  push    rbx
0x180001c36  sub     rsp, 20h
0x180001c3a  mov     rbx, rcx
0x180001c3d  mov     rcx, [rcx+230h]; bstrString
0x180001c44  test    rcx, rcx
0x180001c47  jz      short loc_180001C5A
0x180001c49  call    cs:__imp_SysFreeString
0x180001c4f  mov     qword ptr [rbx+230h], 0
0x180001c5a  mov     rcx, [rbx+238h]; hLibModule
0x180001c61  test    rcx, rcx
0x180001c64  jz      short loc_180001C77
0x180001c66  call    cs:__imp_FreeLibrary
0x180001c6c  mov     qword ptr [rbx+238h], 0
0x180001c77  lea     rcx, [rbx+178h]
0x180001c7e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001c84  lea     rcx, [rbx+0C0h]
0x180001c8b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001c91  lea     rcx, [rbx+8]
0x180001c95  add     rsp, 20h
0x180001c99  pop     rbx
0x180001c9a  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
