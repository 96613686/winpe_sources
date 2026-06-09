# Apx::ApfIpcLink::~ApfIpcLink(void)

- ea: `0x18002963c`
- end: `0x1800296d3`
- name: `??1ApfIpcLink@Apx@@MEAA@XZ`
- size: `151`
- prototype: `void __fastcall(Apx::ApfIpcLink *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180027520`
- `0x1800296e0`
- `0x180029ad2`

## callees

- `0x18000a12c`
- `0x18002963c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002968b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002968b`

## pseudocode

```c
void __fastcall Apx::ApfIpcLink::~ApfIpcLink(Apx::ApfIpcLink *this)
{
  *(_QWORD *)this = &Apx::ApfIpcLink::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_749d1720de943cdcac02263c8ddb543c_Traceguids);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_749d1720de943cdcac02263c8ddb543c_Traceguids);
  }
  *(_QWORD *)this = &Apx::ApfObject::`vftable';
}

```

## disassembly

```asm
0x18002963c  mov     [rsp+arg_0], rbx
0x180029641  push    rdi
0x180029642  sub     rsp, 20h
0x180029646  lea     rax, ??_7ApfIpcLink@Apx@@6B@; const Apx::ApfIpcLink::`vftable'
0x18002964d  mov     rbx, rcx
0x180029650  mov     [rcx], rax
0x180029653  mov     rcx, cs:WPP_GLOBAL_Control
0x18002965a  lea     rdi, WPP_GLOBAL_Control
0x180029661  cmp     rcx, rdi
0x180029664  jz      short loc_180029687
0x180029666  test    byte ptr [rcx+1Ch], 1
0x18002966a  jz      short loc_180029687
0x18002966c  cmp     byte ptr [rcx+19h], 5
0x180029670  jb      short loc_180029687
0x180029672  mov     rcx, [rcx+10h]
0x180029676  lea     r8, WPP_749d1720de943cdcac02263c8ddb543c_Traceguids
0x18002967d  mov     edx, 0Ch
0x180029682  call    WPP_SF_
0x180029687  lea     rcx, [rbx+10h]; lpCriticalSection
0x18002968b  call    cs:__imp_DeleteCriticalSection
0x180029691  mov     rcx, cs:WPP_GLOBAL_Control
0x180029698  cmp     rcx, rdi
0x18002969b  jz      short loc_1800296BE
0x18002969d  test    byte ptr [rcx+1Ch], 1
0x1800296a1  jz      short loc_1800296BE
0x1800296a3  cmp     byte ptr [rcx+19h], 5
0x1800296a7  jb      short loc_1800296BE
0x1800296a9  mov     rcx, [rcx+10h]
0x1800296ad  lea     r8, WPP_749d1720de943cdcac02263c8ddb543c_Traceguids
0x1800296b4  mov     edx, 0Dh
0x1800296b9  call    WPP_SF_
0x1800296be  lea     rax, ??_7ApfObject@Apx@@6B@; const Apx::ApfObject::`vftable'
0x1800296c5  mov     [rbx], rax
0x1800296c8  mov     rbx, [rsp+28h+arg_0]
0x1800296cd  add     rsp, 20h
0x1800296d1  pop     rdi
0x1800296d2  retn
```
