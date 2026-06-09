# CPortClient::~CPortClient(void)

- ea: `0x140002e24`
- end: `0x140002e65`
- name: `??1CPortClient@@UEAA@XZ`
- size: `65`
- prototype: `void __fastcall(CPortClient *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400023dc`
- `0x140002c64`
- `0x1400035ac`
- `0x14000da40`

## callees

- `0x140002e24`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002e46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002e46`

## pseudocode

```c
void __fastcall CPortClient::~CPortClient(CPortClient *this)
{
  bool v1; // zf
  void *v3; // rcx

  v1 = *((_BYTE *)this + 24) == 0;
  *(_QWORD *)this = &CPortClient::`vftable';
  if ( !v1 )
  {
    v3 = (void *)*((_QWORD *)this + 2);
    if ( v3 )
    {
      CloseHandle(v3);
      *((_BYTE *)this + 24) = 0;
    }
  }
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x140002e24  push    rbx
0x140002e26  sub     rsp, 20h
0x140002e2a  cmp     byte ptr [rcx+18h], 0
0x140002e2e  lea     rax, ??_7CPortClient@@6B@; const CPortClient::`vftable'
0x140002e35  mov     [rcx], rax
0x140002e38  mov     rbx, rcx
0x140002e3b  jz      short loc_140002E50
0x140002e3d  mov     rcx, [rcx+10h]; hObject
0x140002e41  test    rcx, rcx
0x140002e44  jz      short loc_140002E50
0x140002e46  call    cs:__imp_CloseHandle
0x140002e4c  mov     byte ptr [rbx+18h], 0
0x140002e50  mov     dword ptr [rbx+8], 0
0x140002e57  mov     qword ptr [rbx+10h], 0
0x140002e5f  add     rsp, 20h
0x140002e63  pop     rbx
0x140002e64  retn
```
