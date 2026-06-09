# Apx::ApfIpcLinkMgr::~ApfIpcLinkMgr(void)

- ea: `0x180027250`
- end: `0x1800272e7`
- name: `??1ApfIpcLinkMgr@Apx@@MEAA@XZ`
- size: `151`
- prototype: `void __fastcall(Apx::ApfIpcLinkMgr *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800259d8`
- `0x1800272f0`

## callees

- `0x18000a12c`
- `0x180027250`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002729f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002729f`

## pseudocode

```c
void __fastcall Apx::ApfIpcLinkMgr::~ApfIpcLinkMgr(Apx::ApfIpcLinkMgr *this)
{
  *(_QWORD *)this = &Apx::ApfIpcLinkMgr::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_908fdabb6ad03a658653e342fffc33fd_Traceguids);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_908fdabb6ad03a658653e342fffc33fd_Traceguids);
  }
  *(_QWORD *)this = &Apx::ApfObject::`vftable';
}

```

## disassembly

```asm
0x180027250  mov     [rsp+arg_0], rbx
0x180027255  push    rdi
0x180027256  sub     rsp, 20h
0x18002725a  lea     rax, ??_7ApfIpcLinkMgr@Apx@@6B@; const Apx::ApfIpcLinkMgr::`vftable'
0x180027261  mov     rbx, rcx
0x180027264  mov     [rcx], rax
0x180027267  mov     rcx, cs:WPP_GLOBAL_Control
0x18002726e  lea     rdi, WPP_GLOBAL_Control
0x180027275  cmp     rcx, rdi
0x180027278  jz      short loc_18002729B
0x18002727a  test    byte ptr [rcx+1Ch], 1
0x18002727e  jz      short loc_18002729B
0x180027280  cmp     byte ptr [rcx+19h], 5
0x180027284  jb      short loc_18002729B
0x180027286  mov     rcx, [rcx+10h]
0x18002728a  lea     r8, WPP_908fdabb6ad03a658653e342fffc33fd_Traceguids
0x180027291  mov     edx, 0Ch
0x180027296  call    WPP_SF_
0x18002729b  lea     rcx, [rbx+10h]; lpCriticalSection
0x18002729f  call    cs:__imp_DeleteCriticalSection
0x1800272a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800272ac  cmp     rcx, rdi
0x1800272af  jz      short loc_1800272D2
0x1800272b1  test    byte ptr [rcx+1Ch], 1
0x1800272b5  jz      short loc_1800272D2
0x1800272b7  cmp     byte ptr [rcx+19h], 5
0x1800272bb  jb      short loc_1800272D2
0x1800272bd  mov     rcx, [rcx+10h]
0x1800272c1  lea     r8, WPP_908fdabb6ad03a658653e342fffc33fd_Traceguids
0x1800272c8  mov     edx, 0Dh
0x1800272cd  call    WPP_SF_
0x1800272d2  lea     rax, ??_7ApfObject@Apx@@6B@; const Apx::ApfObject::`vftable'
0x1800272d9  mov     [rbx], rax
0x1800272dc  mov     rbx, [rsp+28h+arg_0]
0x1800272e1  add     rsp, 20h
0x1800272e5  pop     rdi
0x1800272e6  retn
```
