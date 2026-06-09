# Mpeg2DemuxTrace::CeHomeETWDLL::UnloadeHomeETWDll(void)

- ea: `0x180012a58`
- end: `0x180012ac5`
- name: `?UnloadeHomeETWDll@CeHomeETWDLL@Mpeg2DemuxTrace@@AEAAXXZ`
- size: `109`
- prototype: `void __fastcall(Mpeg2DemuxTrace::CeHomeETWDLL *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180010870`
- `0x1800110d4`

## callees

- `0x180012a58`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180012a6a`
- `KERNEL32!FreeLibrary` at `0x180012a6a`

## pseudocode

```c
void __fastcall Mpeg2DemuxTrace::CeHomeETWDLL::UnloadeHomeETWDll(Mpeg2DemuxTrace::CeHomeETWDLL *this)
{
  HMODULE v2; // rcx

  v2 = (HMODULE)*((_QWORD *)this + 9);
  if ( v2 )
  {
    FreeLibrary(v2);
    *((_QWORD *)this + 9) = 0;
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x180012a58  push    rbx
0x180012a5a  sub     rsp, 20h
0x180012a5e  mov     rbx, rcx
0x180012a61  mov     rcx, [rcx+48h]; hLibModule
0x180012a65  test    rcx, rcx
0x180012a68  jz      short loc_180012ABF
0x180012a6a  call    cs:__imp_FreeLibrary
0x180012a70  mov     qword ptr [rbx+48h], 0
0x180012a78  mov     qword ptr [rbx], 0
0x180012a7f  mov     qword ptr [rbx+8], 0
0x180012a87  mov     qword ptr [rbx+10h], 0
0x180012a8f  mov     qword ptr [rbx+18h], 0
0x180012a97  mov     qword ptr [rbx+20h], 0
0x180012a9f  mov     qword ptr [rbx+28h], 0
0x180012aa7  mov     qword ptr [rbx+30h], 0
0x180012aaf  mov     qword ptr [rbx+38h], 0
0x180012ab7  mov     qword ptr [rbx+40h], 0
0x180012abf  add     rsp, 20h
0x180012ac3  pop     rbx
0x180012ac4  retn
```
